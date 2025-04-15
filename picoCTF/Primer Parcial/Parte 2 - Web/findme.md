#### Descripción

Ayúdenos a probar el formulario enviando el nombre de usuario como y la contraseña como `test``test!`El sitio web que se ejecuta [aquí](http://saturn.picoctf.net:55260/).

### Solución

> Con una pantalla de inicio de sesión. Como sugiere la descripción de la página, intenté ingresar y , pero obtuve la siguiente pantalla:`user=test``password=test`
> 

> Intento de inicio de sesión
> 
> Así que intenté ingresar y, como sugiere la pantalla, y logré iniciar sesión:`user=test``password=test!`

> 
> Iniciar sesión
> 
> Al inspeccionar la página, no había nada, pero al mirar el campo en el navegador en el momento de iniciar sesión, noté dos , así que decidí inspeccionar la solicitud. Pasemos a la explotación.`url``redirects`

> Para analizar la solicitud, no lo usé ya que eran solo dos redireccionamientos. Habilité la casilla de verificación en la sección de , que conserva todos los registros de solicitudes.`BurpSuite``Keep Log``Network``ChromeDevTools`

> Como podemos ver, al iniciar sesión nuevamente e inspeccionar la sección, logré interceptar las dos redirecciones:`Network`
> 

> Bandera Base64
> 
> A partir de aquí, noté un parámetro que contenía una cadena extraña, así que decidí decodificarlo:`id``base64`
> 
> [!
> Primera pieza
> 
> Encontrar la primera parte de la bandera. A continuación, decodifiqué el segundo:
> 
	echo bF90aGVfd2F5XzNkOWUzNjk3fQ== | base64 -d
> 

> Segunda pieza
> 
> Recuperando la segunda parte de la bandera. Luego los concatené y decodifiqué una vez más:
> 
echo cGljb0NURntwcm94aWVzX2FsbF90aGVfd2F5XzNkOWUzNjk3fQ== | base64 -d 
> Impresión de la bandera completa.
> 
### Bandera
picoCTF{proxies_all_the_way_d1c0b112}