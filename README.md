# xml-python
## UF2A1 - Documentació amb Markdown - control

## Índex
- Què és el Dom?
- Treballant amb el DOM a Python


<a name="Què és el Dom?"></a>
El **DOM** és una API *(Interfície de Programació d’Aplicacions)* que permet **accedir i modificar documents XML**. Representa un document XML com una estructura d’arbre, la qual cosa facilita la manipulació dels seus elements. A continuació, presento alguns punts clau sobre el DOM:

- El DOM és útil per a aplicacions que requereixen accés aleatori a parts específiques del document XML.
- A diferència de SAX *(Simple API for XML)*, que només permet veure una part del document a la vegada, el DOM proporciona accés a tota l’estructura de l’arbre.
- El DOM és estàndard i es defineix en nivells pel W3C *(World Wide Web Consortium)*.

![esquema estructural de Dom](Document.jpg)

<a name="Treballant amb el DOM a Python"></a>

**1. Importar el mòdul xml.dom.minidom:**

``` import xml.dom.minidom ```

**2. Parsejar un fitxer XML:**

``` doc = xml.dom.minidom.parse("fitxer.xml") ```

**3. Accedir als elements:**

``` staff_elements = doc.getElementsByTagName("staff") ```

**4. Accedir als atributs d’un element:**

```
for staff in staff_elements:
    staff_id = staff.getAttribute("id")
    print(f"Staff ID: {staff_id}")
 ```
**5. Accedir al contingut d’un node de text:**

```
for staff in staff_elements:
    name_element = staff.getElementsByTagName("name")[0]
    staff_name = name_element.firstChild.data
    print(f"Staff Name: {staff_name}")
```

**6. Exemple complet:**

Partim d'aquest XML:
```
<?xml version="1.0"?>
<company>
    <staff id="1">
        <name>Amar Pandey</name>
        <salary>8.5 LPA</salary>
    </staff>
    <staff id="2">
        <name>Akbhar Khan</name>
        <salary>9.0 LPA</salary>
    </staff>
</company>
```

Aqui l'arxiu Python:

```
import xml.dom.minidom

# Parsejar el fitxer XML
doc = xml.dom.minidom.parse("sample.xml")

# Obtenir tots els elements <staff>
staff_elements = doc.getElementsByTagName("staff")

# Accedir als atributs i contingut dels elements
for staff in staff_elements:
    staff_id = staff.getAttribute("id")
    name_element = staff.getElementsByTagName("name")[0]
    staff_name = name_element.firstChild.data
    print(f"Staff ID: {staff_id}, Name: {staff_name}")
```

Fins aqui, tot aixó és una introducció bàsica al mon de DOM en Python. 
