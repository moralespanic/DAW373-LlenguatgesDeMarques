# Markdown

Aquest és el primer llenguatge de marques que he estudiat a DAW.

És un llenguatge de marques amplament utilitzat, que es fa servir per formatar text de manera senzilla i fàcil de llegir. La seva simplicitat el fa molt popular, ja que requereix de molts pocs símbols per cada funcionalitat, al contrari d'altres llenguatges de marques com HTML, que requereixen d'escriure paraules llargues, i repetides vegades. S'utilitza sovint a documentació en general, però també s'implementa a molts llocs web/aplicacions, com ara GitHub, Discord, WhatsApp i ChatGPT.

Els documents escrits en Markdown tenen una extensió .**md** (**M**ark**d**own). Aquest mateix document (*README.md*) està escrit en Markdown. A més, Markdown té el seu propi tipus MIME (*Multipurpose Internet Mail Extensions*), que és `text/markdown`.

Per exemple, per escriure un text amb negreta, s'ha d'escriure de la següent forma:
```markdown
**Text en negreta**
```
I queda així: **Text en negreta**

## CommonMark

Markdown és un llenguatge que va ser creat per John Gruber a l'any 2004, que venía amb una [documentació](https://daringfireball.net/projects/markdown/syntax) bastant pobre i ambigua; no deixava clar com s'havía d'implementar Markdown. Això va portar a que cada aplicació implementès aquest llenguatge *a la seva manera*, cosa que va portar a inconsistències entre aplicacions.

Per solucionar aquest problema, va aparèixer **CommonMark**, que és un estàndard de Markdown pensat per ser fàcil d'entendre i implementar a les aplicacions. El [manual](https://commonmark.org/help/) d'aquest estàndard és més extens i fàcil d'entendre que l'original.

Tot i que CommonMark és l'estàndard actual de Markdown, les aplicacions no estan obligades a implementar-lo. Existeixen molts exemples d'aplicacions que no implementen Markdown seguint CommonMark, ja que no requereixen de totes les funcionalitats que aquest aporta. Un exemple molt clar és WhatsApp, que es basa en Markdown per donar alguns estils tipogràfics bàsics i crear blocs de codi, però no permet escollir el llenguatge de programació del bloc de codi, ni crear taules. A més, WhatsApp permet subratllar text i tatxar-lo, que no està definit a CommonMark.

Els documents Markdown que segueixen CommonMark tenen el seu propi tipus MIME, que és `text/markdown; variant=CommonMark`.

## Característiques principals de Markdown

Cal que per cada salt de línia, deixem una línia entre mig, ja que si no, les dues línies es renderitzaran compactades en una mateixa línia:

```markdown
Línia 1

Línia 2
Línia 3
```

Que es renderitza de la següent forma:

Línia 1

Línia 2
Línia 3

Això és una característica que podríem aprofitar per si tenim massa text, i el volem estructurar dins del fitxer md, però que a l'hora de renderitzar-lo, que es vegi tot al mateix paràgraf.

Cal recalcar que cada aplicació renderitza Markdown com tingui definit, ja que a Markdown només s'especifica l'estructura (capçaleres, taules, negretes, cursives...) del text, i no la font ni el color com a tal. Per tant, això que acabo de comentar no té per què aplicar-se a totes les aplicacions.

La forma en la que es renderitza Markdown és dependent de l'aplicació. Això vol dir que cada aplicació pot utilitzar una font tipogràfica diferent per renderitzar el text, i altres paràmetres com ara la mida del text, el color del text, el grossor de les línies, i qualsevol altre aspecte relacionat amb l'estètica.

Però hi ha una excepció; algunes aplicacions permeten incloure HTML dincs d'un document de Markdown, com per exemple:

```html
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

També, existeixen moltes altres funcionalitats de Markdown que algunes aplicacions implementen, i d'altres no. Jo em centraré principalment en les que GitHub implementa, ja que GitHub té una implementació de Markdown molt extensa.

## Funcionalitats bàsiques de Markdown

Aquestes són les funcionalitats més bàsiques de Markdown, i totes les aplicacions que segueixin CommonMark les hauríen d'implementar. No sé si hi són totes, però sí que n'hi ha una gran part (les més importants).

### Estils tipogràfics

Per aplicar *cursiva* o _itàlica_ a un text, podem envoltar-lo d'asteriscs o de guions baixos:

```markdown
*Text d'exemple 1.*

_Text d'exemple 2._
```

Que es renderitza de la següent forma:

*Text d'exemple 1.*

_Text d'exemple 2._

Per aplicar **negreta** a un text, podem envoltar-lo de dobles asteriscs, o de dobles guions baixos:

```markdown
**Text d'exemple 1.**

__Text d'exemple 2.__
```

Que es renderitza de la següent forma:

**Text d'exemple 1.**

__Text d'exemple 2.__

### Capçaleres

Les capçaleres s'utilitzen per estructurar un document, mitjançant títols o apartats.

Per crear una capçalera, s'ha d'escriure un coixinet (#) seguit del títol. Tenim fins a 6 nivells de capçalera:

```markdown
# Capçalera de nivell 1
## Capçalera de nivell 2
### Capçalera de nivell 3
#### Capçalera de nivell 4
##### Capçalera de nivell 5
###### Capçalera de nivell 6
####### Capçalera de nivell 7
```

Això es renderitza de la següent forma:

# Capçalera de nivell 1
## Capçalera de nivell 2
### Capçalera de nivell 3
#### Capçalera de nivell 4
##### Capçalera de nivell 5
###### Capçalera de nivell 6
####### Capçalera de nivell 7

A partir de la capçalera de nivell 6 (no inclòs), no es renderitzen més nivells de capçalera.

### Imatges

Podem inserir imatges, amb la següent sintaxi:

```markdown
![Pingüí Tux de Linux](https://www.kernel.org/theme/images/logos/tux.png)
```

Que es renderitza així:

![Pingüí Tux de Linux](https://www.kernel.org/theme/images/logos/tux.png)

El signe d'exclamació (`!`) indica que es tracta d'una imatge. Les imatges necessiten text alternatiu (definit amb `[text alternatiu]`), que és el que es renderitzarà si la imatge no s'ha pogut carregar, i el que es llegirà en TTS (*Text To Speech*), per a persones amb visibilitat reduïda.

Per últim, s'ha d'indicar des d'on volem carregar la imatge, amb els parèntesis [`(ruta/a/la/imatge)`]. Aquesta ruta pot ser tant local (relativa/absoluta), com externa, carregant-la mitjançant HTTPS per exemple.

Com a prova, podem veure què passa si no es pot carregar la imatge correctament, i la envoltem amb dobles asteriscs:

```markdown
**![text alternatiu, que es mostra en cas de problema al carregar la imatge](/ruta/intexistent/imatge.png)**
```

Es renderitza així, ja que la imatge no existeix:

**![text alternatiu, que es mostra en cas de problema al carregar la imatge](/ruta/intexistent/imatge.png)**

Però també veiem que el text està en negreta. Aquests asteriscs no tindríen efecte en el cas de que la imatge sí que s'haguès carregat correctament.

### Hipervincles

![cara amb somriure](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAIAAACQkWg2AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAdnJLH8AAAAgY0hSTQAAeiYAAICEAAD6AAAAgOgAAHUwAADqYAAAOpgAABdwnLpRPAAAAAlwSFlzAAAuIwAALiMBeKU/dgAAAAd0SU1FB+kJERIiEL2NkzsAAAB9SURBVCjP5ZCxDQQhDATNJZRABXQCPbiW7cCl4BrcAVWQUQA5F3yC7jnpgg9eusl215KlIfpXmFlVv3sREZG1Oei9iEgp5W5VVWa+Wso5b69baymlzdB7r7WuDYAxhpmZ2f71nHPdLvGDW4OZxRi990QUQnDOPRIAAMDPhJ7ecy8l7KILGQAAAABJRU5ErkJggg==)

### Llistes

### Taules

### Cites en bloc

### Codi

### Línies horitzontals

### Llistes de tasques

### Notes al peu

## Funcionalitats avançades de Markdown

Aquestes funcionalitats no tenen per què estar implementades a totes les aplicacions que suporten Markdown, ja que no estan a l'estàndard CommonMark.

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