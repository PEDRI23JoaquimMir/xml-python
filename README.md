# xml-python
## UF2A1 - Documentació amb Markdown - control

## Índex
1- Què és el Dom?
2- Treballant amb el DOM a Python


<a name="Què és el Dom?"></a>
El **DOM** és una API *(Interfície de Programació d’Aplicacions)* que permet **accedir i modificar documents XML**. Representa un document XML com una estructura d’arbre, la qual cosa facilita la manipulació dels seus elements. A continuació, presento alguns punts clau sobre el DOM:

- El DOM és útil per a aplicacions que requereixen accés aleatori a parts específiques del document XML.
- A diferència de SAX (Simple API for XML), que només permet veure una part del document a la vegada, el DOM proporciona accés a tota l’estructura de l’arbre.
- El DOM és estàndard i es defineix en nivells pel W3C (World Wide Web Consortium).

  
<a name="Treballant amb el DOM a Python"></a>

1- xml.dom: Aquest mòdul proporciona la definició de l’API DOM. Pots crear, modificar i accedir a documents XML utilitzant aquesta interfície. A continuació, es mostra un exemple bàsic:

```
import xml.dom.minidom

# Crear un nou document XML
doc = xml.dom.minidom.Document()

# Crear un element arrel
root = doc.createElement("llibreria")
doc.appendChild(root)

# Afegir un element fill
llibre = doc.createElement("llibre")
root.appendChild(llibre)

# Afegir atributs a l'element
llibre.setAttribute("categoria", "ficció")

# Crear un node de text
titol = doc.createElement("títol")
text_titol = doc.createTextNode("El Catcher in the Rye")
titol.appendChild(text_titol)
llibre.appendChild(titol)

# Imprimir el document XML
print(doc.toprettyxml())

```

2- xml.dom.minidom: Aquesta és una implementació mínima del DOM. És més senzilla i més petita que una implementació completa. Aquí tens un exemple similar al de dalt:

```
from xml.dom import minidom

doc = minidom.Document()
root = doc.createElement("llibreria")
doc.appendChild(root)

# ... Afegir elements i atributs ...

print(doc.toprettyxml())
