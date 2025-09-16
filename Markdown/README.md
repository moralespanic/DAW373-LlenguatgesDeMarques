# Markdown

Aquest és el primer llenguatge de marques que he estudiat a DAW.

És un llenguatge de marques amplament utilitzat, que s'utilitza per formatar text de manera senzilla i fàcil de llegir. La seva simplicitat el fa molt popular, ja que requereix de molts pocs símbols per cada funcionalitat, al contrari d'altres llenguatges de marques com HTML, que requereixen d'escriure paraules llargues, i repetides vegades. S'utilitza sovint a documentació en general, però també s'implementa a molts llocs web/aplicacions, com ara GitHub, Discord, WhatsApp i ChatGPT.

Els documents escrits en Markdown tenen una extensió .**md** (**M**ark**d**own). Aquest mateix document (*README.md*) està escrit en Markdown.

Per exemple, per escriure un text amb negreta, s'ha d'escriure de la següent forma:
```
**Text en negreta**
```
I queda així: **Text en negreta**

## Característiques principals de Markdown

Cada aplicació renderitza Markdown com tingui definit, ja que a Markdown només s'especifica l'estructura (capçaleres, taules, negretes, cursives...) del text, i no la font ni el color com a tal.

La forma en la que es renderitza Markdown és dependent de l'aplicació. Això vol dir que cada aplicació pot utilitzar una font tipogràfica diferent per renderitzar el text, i altres paràmetres com ara la mida del text, el color del text, 

Moltes aplicacions (no totes) permeten incloure HTML dincs d'un document de Markdown, com per exemple:

```
<html>
    <p>Aquesta és una imatge d'un <b style="font-family: sans-seriff; font-size: 20px;color: red">gos</b>:</p>
    <img src="../assets/Gos.jpg" alt="gos goofy" style="width: 500px; height: auto; border-radius: 50px">
</html>
```

Que es renderitza així:

---

<html>
    <p>Aquesta és una imatge d'un <b style="font-family: sans-seriff; font-size: 20px;color: red">gos</b>:</p>
    <img src="../assets/Gos.jpg" alt="gos goofy" style="width: 500px; height: auto; border-radius: 50px">
</html>

---

> La imatge del gos la he tret de [Flickr](https://flic.kr/p/4VRgLc).

També, existeixen moltes altres funcionalitats de Markdown que algunes aplicacions implementen, i d'altres no.

Ara, detallaré unes quantes funcionalitats de Markdown. No sé si hi són totes, però sí que n'hi ha una gran part (les més importants).

## Funcionalitats bàsiques de Markdown

Aquestes són les funcionalitats més bàsiques de Markdown, i totes les aplicacions que utilitzin aquest llenguatge les hauríen d'implementar.

> Algunes aplicacions, com ara WhatsApp, implementen Markdown però de forma parcial, cosa que vol dir que no ofereixen totes les funcionalitats d'aquest llenguatge.

### Estils tipogràfics

### Hipervincles

### Llistes

### Taules

### Imatges

### Cites en bloc

### Codi

### Línies horitzontals

### Llistes de tasques

### Notes al peu

## Funcionalitats avançades de Markdown

Aquestes funcionalitats no tenen per què estar implementades a totes les aplicacions que suporten Markdown. I pot ser que n'existeixin més.

### HTML incrustat

### Emojis

### Blocs de codi amb ressaltat de sintaxi

### Taules avançades amb alineació

### Contingut col·lapsable (detalls/resum)

### Resaltat de text

### Diagrames Mermaid

### Matemàtiques amb LaTeX

### Blocs especials (callouts, notes, alerts)

### Plantilles i extensions específiques de plataforma