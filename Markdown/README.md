# Markdown

Aquest és el primer llenguatge de marques que he estudiat a DAW.

És un llenguatge pensat per aplicar estils a documents de text pla, que normalment és documentació en general.

Els fitxers del llenguatge Markdown tenen una extensió .**md** (**M**ark**d**own). Aquest mateix document (*README.md*) està escrit en Markdown.

Moltes aplicacions l'implementen, GitHub n'és una.

Té una sintaxi molt senzilla, que permet que una persona l'escrigui i llegeixi amb molta facilitat.

Per exemple, per escriure un text amb negreta, s'ha d'escriure de la següent forma:
```
**Text en negreta**
```
I queda així: **Text en negreta**

## Estils

Cada aplicació renderitza Markdown com tingui definit, ja que a Markdown només s'especifica l'estructura (capçaleres, taules, negretes, cursives...) del text, i no la font ni el color com a tal.

Moltes aplicacions permeten incloure HTML dincs d'un document de Markdown, com per exemple:

```
<html>
    <p>Aquesta és una imatge d'un <b style="font-size: 20px;color: red">gos</b>:</p>
    <img src="../assets/Gos.jpg" style="max-width: 50%; border-radius: 50px">
</html>
```

Que es renderitza així:

---

<html>
    <p>Aquesta és una imatge d'un <b style="font-size: 20px;color: red">gos</b>:</p>
    <img src="../assets/Gos.jpg" style="max-width: 50%; border-radius: 50px">
</html>

---

> La imatge del gos la he tret de [Flickr](https://flic.kr/p/4VRgLc).

També, existeixen moltes altres funcionalitats de Markdown que algunes aplicacions implementen, i d'altres no. Em centraré principalment en les funcionalitats bàsiques de Markdown; les que totes les aplicacions suporten.