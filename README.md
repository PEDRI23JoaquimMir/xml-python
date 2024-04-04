# xml-python
## UF2A1 - Documentació amb Markdown - control

## Índex
- Què és el Dom?
- Treballant amb el DOM a Python


<a name="Què és el Dom?"></a>
El **DOM** és una API *(Interfície de Programació d’Aplicacions)* que permet **accedir i modificar documents XML**. Representa un document XML com una estructura d’arbre, la qual cosa facilita la manipulació dels seus elements. A continuació, presento alguns punts clau sobre el DOM:

- El DOM és útil per a aplicacions que requereixen accés aleatori a parts específiques del document XML.
- A diferència de SAX (Simple API for XML), que només permet veure una part del document a la vegada, el DOM proporciona accés a tota l’estructura de l’arbre.
- El DOM és estàndard i es defineix en nivells pel W3C (World Wide Web Consortium).

![esquema estructural de Dom](Document.jpg)

<a name="Treballant amb el DOM a Python"></a>

1. Importar el mòdul xml.dom.minidom:

``` import xml.dom.minidom ```

2.Parsejar un fitxer XML:

``` doc = xml.dom.minidom.parse("fitxer.xml") ```
