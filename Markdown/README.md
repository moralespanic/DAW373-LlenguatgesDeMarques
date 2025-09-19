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
Markdown és un llenguatge que va ser creat per John Gruber a l'any 2004, que venía amb una [documentació](https://daringfireball.net/projects/markdown/syntax) bastant pobre i ambigua; no deixava clar com s'havia d'implementar Markdown. Això va portar a que cada aplicació implementés aquest llenguatge *a la seva manera*, cosa que va portar a inconsistències entre aplicacions.

Per solucionar aquest problema, va aparèixer **CommonMark**, que és un estàndard de Markdown pensat per ser fàcil d'entendre i implementar a les aplicacions. El [manual](https://commonmark.org/help/) d'aquest estàndard és més extens i fàcil d'entendre que l'original.  
Tot i que CommonMark és l'estàndard actual de Markdown, les aplicacions no estan obligades a implementar-lo. Existeixen molts exemples d'aplicacions que no implementen aquest llenguatge seguint CommonMark, ja que no requereixen de totes les funcionalitats que aquest aporta. Un exemple molt clar és WhatsApp, que es basa en Markdown per donar alguns estils tipogràfics bàsics i crear blocs de codi, però no permet escollir el llenguatge de programació del bloc de codi, ni crear taules. A més, WhatsApp permet subratllar text i tatxar-lo, que no està definit a CommonMark.

Els documents Markdown que segueixen CommonMark tenen el seu propi tipus MIME, que és `text/markdown; variant=CommonMark`.

## Característiques principals de Markdown

### Salts de línia
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

Si volem fer que entre dues línies no hi hagi una de buida, ho podem fer afegint dos espais al final de la primera de les dues línies. Aquí va un exemple:

```mardown
Hola, bon dia.

Em dic Pau, i estudio 1er de DAW 
al Cendrassos.

Què diu una foca que li agraden molt les xarxes?  
ARP! ARP! ARP!
```

A la línia "Què diu una foca...", he posat dos espais al final:

---

Hola, bon dia.

Em dic Pau, i estudio 1er de DAW 
al Cendrassos.

Què diu una foca que li agraden molt les xarxes?  
ARP! ARP! ARP!

---

Això és una característica que podríem aprofitar per si tenim massa text, i el volem estructurar dins del fitxer md, però a l'hora de renderitzar-lo, que es vegi tot al mateix paràgraf.

> Nota: Només aplica per a paràgrafs.

### Markdown no es veu igual a tots arreu
Cal recalcar que cada aplicació renderitza Markdown com tingui definit, ja que a Markdown només s'especifica l'estructura (capçaleres, taules, negretes, cursives...) del text, i no la font ni el color com a tal. Per tant, això que acabo de comentar no té per què aplicar-se a totes les aplicacions.  
La forma en la que es renderitza Markdown és dependent de l'aplicació. Això vol dir que cada aplicació pot utilitzar una font tipogràfica diferent per renderitzar el text, i altres paràmetres com ara la mida del text, el color del text, el grossor de les línies, i qualsevol altre aspecte relacionat amb l'estètica.

Però hi ha una excepció; algunes aplicacions permeten incloure HTML dincs d'un document de Markdown, com per exemple:
```html
<html>
    <p>Aquesta és una imatge d'un <b style="font-family: sans-serif; font-size: 20px;color: red">gos</b>:</p>
    <img src="../assets/Gos.jpg" alt="gos goofy" style="width: 500px; height: auto; border-radius: 50px">
</html>
```

Que es renderitza així:

---
<html>
    <p>Aquesta és una imatge d'un <b style="font-family: sans-serif; font-size: 20px;color: red">gos</b>:</p>
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

Per crear una capçalera, es poden escriure coixinets (#) seguits del títol. Tenim fins a 6 nivells de capçalera:

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

Per les capçaleres de nivell 1 i 2, podem fer servir els símbols `=` (nivell 1) i `-` (nivell 2). De la següent forma:
```markdown
Capçalera de nivell 1
=====================
Capçalera de nivell 2
---------------------
```

El nombre de símbols (`=` i `-`) és indiferent; jo he posat tants per a que quedi més estètic, però no és necessari:

Capçalera de nivell 1
=====================
Capçalera de nivell 2
---------------------

### Imatges
Podem inserir imatges, amb la següent sintaxi:
```markdown
![Pingüí Tux de Linux](https://www.kernel.org/theme/images/logos/tux.png)
```

Que es renderitza així:

![Pingüí Tux de Linux](https://www.kernel.org/theme/images/logos/tux.png)

> El fet de que aquesta imatge sigui clickable és cosa de GitHub. Per protegir l'adreça IP del lector, GitHub fa que la imatge que es mostra es carregui des d'un domini de GitHub (`camo.githubusercontent.com`), que per darrere la carrega des del servidor real. Això fa que s'emmascari l'adreça IP del lector, i evita que el navegador faci peticions directament al servidor que hosteja la imatge. Però el fet de que sigui clickable no té gaire explicació, ja que amb carregar la imatge des d'un servidor de GitHub ja és suficient.

El signe d'exclamació (`!`) indica que es tracta d'una imatge. Les imatges necessiten text alternatiu (definit amb `[text alternatiu]`), que és el que es renderitzarà si la imatge no s'ha pogut carregar, i el que es llegirà en TTS (*Text To Speech*), per a persones amb visibilitat reduïda.

Per últim, s'ha d'indicar des d'on volem carregar la imatge, amb els parèntesis [`(ruta/a/la/imatge)`]. Aquesta ruta pot ser tant local (relativa/absoluta), com externa, carregant-la mitjançant HTTPS per exemple.

Com a prova, podem veure què passa si no es pot carregar la imatge correctament, i la envoltem amb dobles asteriscs:
```markdown
**![text alternatiu, que es mostra en cas de problema al carregar la imatge](/ruta/intexistent/imatge.png)**
```

Es renderitza així, ja que la imatge no existeix:

**![text alternatiu, que es mostra en cas de problema al carregar la imatge](/ruta/intexistent/imatge.png)**

Però també veiem que el text està en negreta. Aquests asteriscs no tindríen efecte en el cas de que la imatge sí que s'hagués carregat correctament.

### Hipervincles
Podem inserir hipervincles, amb la següent sintaxi:
```markdown
[Text de l'hipervincle](https://github.com/)
```

Es renderitzarà de la següent forma

[Text de l'hipervincle](https://github.com/)

Com que ja sabem inserir imatges, podem fer una imatge clickable:
```markdown
[![Pingüí Tux de Linux](https://www.kernel.org/theme/images/logos/tux.png)](https://kernel.org/)
```

Ara, tindrem al Tux, que ens redigirà amablement a la web del kernel de Linux:

[![Pingüí Tux de Linux](https://www.kernel.org/theme/images/logos/tux.png)](https://kernel.org/)

### Llistes
Tenim tres tipus de llistes:
* Llistes simples
* Llistes numerades
* Llistes de tasques

La llista de dalt és una llista simple. La seva sintaxi és la següent:
```markdown
* Llistes simples
* Llistes numerades
* Llistes de tasques
```

Les llistes numerades tenen la següent sintaxi, i poden començar per qualsevol número:
```markdown
0. Element 0
1. Primer element
2. Segon element
3. Tercer element
4. Quart element
5. Cinquè element
6. Sisè element
7. Setè element
8. Vuitè element
9. Novè element
10. Desè element
11. Onzè element
...
```

M'he saltat uns quants elements, i he barrejat números per veure què passava:
```markdown
0. Element 0
1. Primer element
2. Segon element
3. Tercer element
4. Quart element
0. Element 0
8. Vuité element
9. Novè element
1. Primer element
7. Setè element
```

Que es renderitza així:

0. Element 0
1. Primer element
2. Segon element
3. Tercer element
4. Quart element
0. Element 0
8. Vuité element
9. Novè element
1. Primer element
7. Setè element

Sembla que quan comença una llista numèrica, ignora completament la resta de números, i els renderitza com si fossin consecutius.

Per darrere, això deu funcionar amb algun tipus de regex, com aquesta: `^\d+\.\ .*$`

Per últim, comentaré les llistes de tasques, que inclouen un *checkbox* que pot estar marcat o no:
```markdown
- [ ] Tasca sense fer
- [X] Tasca feta 
```

- [ ] Tasca sense fer
- [X] Tasca feta 

### Taules
Les taules tenen una sintaxi molt senzilla i intuitiva:
```markdown
|  Columna 1  |  Columna 2  |  Columna 3  |
|-------------|-------------|-------------|
| Element 1a  | Element 2a  | Element 3a  |
| Element 1b  | Element 2b  | Element 3b  |
| Element 1c  | Element 2c  | Element 3c  |
```

|  Columna 1  |  Columna 2  |  Columna 3  |
|-------------|-------------|-------------|
| Element 1a  | Element 2a  | Element 3a  |
| Element 1b  | Element 2b  | Element 3b  |
| Element 1c  | Element 2c  | Element 3c  |

És indiferent si col·loquem els símbols (`|` i `-`) de forma diferent que a l'exemple, ja que la taula es renderitzarà exactament igual, col·loquem on col·loquem els símbols. Jo els he col·locat d'aquesta forma per a que sigui més fàcil de llegir a l'editar el fitxer MD.

També podem alinear el text de les columnes horitzontalment, mitjançant el símbol `:`. Per defecte, les columnes s'alineen a l'esquerra, però ho podem canviar, a la segona línia de la taula, la que té les sèries de guions (`|---|---|---|---|---|`):

- `|:-|` Alinea la columna a l'esquerra
- `|:-:|` Alinea la columna al centre
- `|-:|` Alinea la columna a la dreta
```markdown
|      Columna alineada a la dreta |  Columna alineada al centre  |  Columna alineada a l'esquerra      |
|---------------------------------:|:----------------------------:|:------------------------------------|
|                   Element dret A |      Element central A       | Element esquerre A                  |
|                   Element dret B |      Element central B       | Element esquerre B                  |
|                   Element dret C |      Element central C       | Element esquerre C                  |
|                   Element dret D |      Element central D       | Element esquerre D                  |
|                   Element dret E |      Element central E       | Element esquerre E                  |
|                   Element dret F |      Element central F       | Element esquerre F                  |
```

Observar que a les sèries de guions (`-`) he afegit el símbol `:` en base al que correspon a la columna. El text l'he alineat mitjançant espais per tenir-lo més "ordenat" a nivell d'editor, però, com en altres casos, no afecta en absolut a com es veurà el document al renderitzar-lo.

|                   Columna alineada a la dreta |               Columna al. centre                | Columna alineada a l'esquerra                     |
|----------------------------------------------:|:-----------------------------------------------:|:--------------------------------------------------|
|                                Element dret A |                Element central A                | Element esquerre A                                |
|                                Element dret B |                Element central B                | Element esquerre B................................|
|................................Element dret C |                Element central C                | Element esquerre C                                |
|                                Element dret D |                Element central D                | Element esquerre D                                |
|                                Element dret E |................Element central E                | Element esquerre E                                |
|                                Element dret F |                Element central F                | Element esquerre F                                |

El text de la primera fila també s'alinea. Per comprovar-ho, he afegit punts (`.`) per ampliar la mida d'algunes cel·les:

Cada columna s'adapta a la mida de la cel·la més gran per aquella columna, cosa que farà que per cada columna, sempre hi hagi, com a mínim, una cel·la que sembli no estar alineada, ja que l'amplada de la columna s'adaptará a aquesta/aquestes (poden ser vàries cel·les amb la mateixa mida).

### Cites en bloc

### Codi

### Línies horitzontals

### Notes al peu

## Funcionalitats avançades de Markdown
Aquestes funcionalitats no tenen per què estar implementades a totes les aplicacions que suporten Markdown, ja que no estan a l'estàndard CommonMark.

### HTML incrustat

Entitats de carácter, com ara `&nbsp;`, `&amp;`, `&gt;`

### Emojis

### Blocs de codi amb ressaltat de sintaxi

### Taules avançades amb alineació

### Contingut col·lapsable (detalls/resum)

### Resaltat de text

### Diagrames Mermaid

### Matemàtiques amb LaTeX

### Blocs especials (callouts, notes, alerts)

### Plantilles i extensions específiques de plataforma