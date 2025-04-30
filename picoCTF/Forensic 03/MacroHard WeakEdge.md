### Descrición

> He escondido una bandera en este archivo. ¿Puedes encontrarlo? La ciencia forense es divertida.pptm

- [La ciencia forense es divertida.pptm](https://github.com/HHousen/PicoCTF-2021/blob/master/Forensics/MacroHard%20WeakEdge/Forensics%20is%20fun.pptm)
    
### Solución

1. Extraiga la presentación de PowerPoint como un archivo ZIP, ya que los archivos de PowerPoint son en realidad ZIP: `unzip Forensics\ is\ fun.pptm`
    
2. Mirando a través de los archivos extraídos, parece sospechoso.`ppt/slideMasters/hidden`
    
3. Al leer ese archivo () se muestra .`cat ppt/slideMasters/hidden``Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q`
    
4. Podemos decodificar eso como base64 usando [CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Base64\('A-Za-z0-9%2B/%3D',true\)&input=WiBtIHggaCBaIHogbyBnIGMgRyBsIGogYiAwIE4gVSBSIG4gdCBFIE0gVyBSIGYgZCBWIDkgciBiIGogQiAzIFggMyBCIHcgZCBIIE4gZiBjIGwgOSA2IE0gWCBBIDEgZiBR) para obtener la bandera.
    
### Bandera

`picoCTF{D1d_u_kn0w_ppts_r_z1p5}`