#### Descripción

Tenemos varias páginas ocultas. ¿Puedes encontrar el que tiene la bandera?El sitio web se está ejecutando [aquí](http://saturn.picoctf.net:58260/).

---
### Solución
1. Abrí el sitio web y vi el código fuente.
2. Agregue a la ruta /secret/
   [saturn.picoctf.net:56444/secret/](http://saturn.picoctf.net:56444/secret/)
3. Si navegamos a [http://saturn.picoctf.net:61481/secret/](http://saturn.picoctf.net:61481/secret/), encontrará la carpeta **/hidden**. Haciendo el mismo proceso que antes, puede obtener la URL final: [http://saturn.picoctf.net:61481/secret/hidden/superhidden/](http://saturn.picoctf.net:61481/secret/hidden/superhidden/). El indicador se almacena en las fuentes de página de **/superhidden**.

### Bandera
`picoCTF{succ3ss_@h3n1c@10n_39849bcf}`

### Referencias
[picoCTF — Secrets (Web Exploitation) Challenge Explained | by MoRoMeR | Medium](https://medium.com/@moromerx/picoctf-secrets-web-exploitation-explained-3e8d41b40a2a)

