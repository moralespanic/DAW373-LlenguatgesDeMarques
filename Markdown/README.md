# Markdown

Aquest és el primer llenguatge de marques que he estudiat a DAW.

És un llenguatge de marques amplament utilitzat, que es fa servir per formatar text de manera senzilla i fàcil de llegir. La seva simplicitat el fa molt popular, ja que requereix de molts pocs símbols per cada funcionalitat, al contrari d'altres llenguatges de marques com HTML, que requereixen d'escriure paraules llargues, i repetides vegades. S'utilitza sovint a documentació en general, però també s'implementa a molts llocs web/aplicacions, com ara GitHub, Discord, WhatsApp i ChatGPT.

Els documents escrits en Markdown tenen una extensió .**md** (**M**ark**d**own). Aquest mateix document (*README.md*) està escrit en Markdown.

Per exemple, per escriure un text amb negreta, s'ha d'escriure de la següent forma:
```
**Text en negreta**
```
I queda així: **Text en negreta**

## CommonMark

Markdown és un llenguatge que va ser creat per John Gruber a l'any 2004, que venía amb una [documentació](https://daringfireball.net/projects/markdown/syntax) bastant pobre i ambigua; no deixava clar com s'havía d'implementar Markdown. Això va portar a que cada aplicació implementès aquest llenguatge *a la seva manera*, cosa que va portar a inconsistències entre aplicacions.

Per solucionar aquest problema, va aparèixer **CommonMark**, que és un estàndard de Markdown pensat per ser fàcil d'entendre i implementar a les aplicacions. El [manual](https://commonmark.org/help/) d'aquest estàndard és més extens i fàcil d'entendre que l'original.

Tot i que CommonMark és l'estàndard actual de Markdown, les aplicacions no estan obligades a implementar-lo. Existeixen molts exemples d'aplicacions que no implementen Markdown seguint CommonMark, ja que no requereixen de totes les funcionalitats que aquest aporta. Un exemple molt clar és WhatsApp, que es basa en Markdown per donar alguns estils tipogràfics bàsics i crear blocs de codi, però no permet escollir el llenguatge de programació del bloc de codi, ni crear taules.

## Característiques principals de Markdown

Cal que per cada salt de línia, deixem una línia entre mig, ja que si no, les dues línies es renderitzaran compactades en una mateixa línia:

```
Línia 1

Línia 2
Línia 3
```

Que es renderitza de la següent forma:

Línia 1

Línia 2
Línia 3

Això és una característica que podríem aprofitar per si tenim massa text, i el volem estructurar dins del fitxer md, però que a l'hora de renderitzar-lo, que es vegi tot al mateix paràgraf.

Cal recalcar que cada aplicació renderitza Markdown com tingui definit, ja que a Markdown només s'especifica l'estructura (capçaleres, taules, negretes, cursives...) del text, i no la font ni el color com a tal. Per tant, això que acabo de comentar no té per què aplicar-se a 

La forma en la que es renderitza Markdown és dependent de l'aplicació. Això vol dir que cada aplicació pot utilitzar una font tipogràfica diferent per renderitzar el text, i altres paràmetres com ara la mida del text, el color del text, el grossor de les línies, i qualsevol altre aspecte relacionat amb l'estètica.

Però hi ha una excepció; algunes aplicacions permeten incloure HTML dincs d'un document de Markdown, com per exemple:

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

Com es pot veure, a la paraula "gos", només s'aplica la negreta, i no el color de text, ni la font ni la mida. A la imatge, tampoc s'apliquen les esquines arrodonides, però sí la mida.

Això és degut a que GitHub (i moltes altres aplicacions) imposa l'ús de les seves pròpies fonts, mida de text, color i altres paràmetres dels elements del DOM (*Document Object Model*).

> La imatge del gos la he tret de [Flickr](https://www.flickr.com/photos/kb35/2578458103/).

També, existeixen moltes altres funcionalitats de Markdown que algunes aplicacions implementen, i d'altres no.

## Funcionalitats bàsiques de Markdown

Aquestes són les funcionalitats més bàsiques de Markdown, i totes les aplicacions que segueixin CommonMark les hauríen d'implementar. No sé si hi són totes, però sí que n'hi ha una gran part (les més importants).

### Estils tipogràfics

Per aplicar *cursiva* o _itàlica_ a un text, podem envoltar-lo d'asteriscs o de guions baixos:

```
*Text d'exemple 1.*

_Text d'exemple 2._
```

I queda així:

*Text d'exemple 1.*

_Text d'exemple 2._

Per aplicar **negreta** a un text, podem envoltar-lo de dobles asteriscs, o de dobles guions baixos:

```
**Text d'exemple 1.**

__Text d'exemple 2.__
```

Que queda així:

**Text d'exemple 1.**

__Text d'exemple 2.__

### Capçaleres

Les capçaleres s'utilitzen per estructurar un document, mitjançant títols o apartats.

Provant nivells de capçaleres:

# nivell 1

## nivell 2

### nivell 3

#### nivell 4

##### nivell 5

###### nivell 6

####### nivell 7

a partir d'aquí ja no se'm renderitza al previsualitzador

######## nivell 8

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

Aquestes funcionalitats no tenen per què estar implementades a totes les aplicacions que suporten Markdown, ja que no segueixen l'estàndard CommonMark.

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