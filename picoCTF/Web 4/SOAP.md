#### Descripcion

The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?

*Solución*
Para resolver este desafío, seguí estos pasos:

1. Lancé una instancia y visité el portal web que generó.
2. Cargué la página web en BurpSuite, ya que necesitaba ver un archivo.
3. Hice clic en , intercepté la solicitud con BurpSuite y vi que la solicitud devolvía una sección de`Details`


<?xml version="1.0" encoding="UTF-8"?><data><ID>2</ID></data>


4. Envié esta solicitud al Repetidor, y al enviarla, la respuesta devolvió una sección de


<strong>Special Info::::</strong> Created By security and privacy experts


5. A continuación, probé una vulnerabilidad XXE (inyección de entidades externas) cambiando el en la solicitud a . La respuesta devolvió .20Invalid ID: 0
6. Agregué el siguiente código


<!DOCTYPE replace [<!ENTITY example "Doe"> ]>


y cambió el ID a . Esto reemplazaría con en la respuesta. Establezco la sección de código en`&example;`&example;Doe


<!DOCTYPE replace [<!ENTITY example "0"> ]>


La respuesta devolvió . 7. Cambié la entidad a y el ID a . Reemplacé el original`Invalid ID: 0`exampletest&test;


<!DOCTYPE replace [<!ENTITY example "0"> ]>


con


<!DOCTYPE root [<!ENTITY test SYSTEM 'file:///etc/passwd'>]>


Esto recuperaría el contenido del archivo. La sección completa del código se convirtió en`/etc/passwd`


<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE root [<!ENTITY test SYSTEM 'file:///etc/passwd'>]><data><ID>&test;</ID></data>


8. Envié esta solicitud y la respuesta mostró la bandera


*Respuesta en el formato del concurso:*
picoCTF{XML_3xtern@l_3nt1t1ty_0dcf926e}