Title: Script Python create xml file from csv file
Date: 2013-04-19 11:05
Author: ramborg
Category: Programming
Tags: python, script
Slug: script-python-create-xml-file-from-csv-file

It script create a custom xml file from a csv file. The format of the
csv is like [this file][].

[code language="python"]  
import csv  
\#import sys

from xml.etree import ElementTree  
from xml.dom import minidom

csvFileName = "Distribuidoras.csv"  
xmlFileName = "distribuidoras.xml"

def unicode\_csv\_reader(utf8\_data, dialect=csv.excel, \*\*kwargs):  
csv\_reader = csv.reader(utf8\_data, dialect=dialect, \*\*kwargs)  
for row in csv\_reader:  
yield [unicode(cell, 'utf-8') for cell in row]

with open(csvFileName, 'rU') as csvFile:  
\#reader = csv.reader(csvFile, delimiter=';')  
reader = unicode\_csv\_reader(csvFile, delimiter=';')

comercializadoras\_tag = ElementTree.Element('distribuidoras')  
for row in reader:  
\#print row

if(row[0]!='' or row[1]!='' or row[2]!='' or row[3]!='' or row[4] or
row[5]!='' or row[6]!=''):  
attrs = {'name': row[0],  
'tel': row[1],  
'cif': row[2],  
'direccion': row[3],  
'codigo': row[4],  
'division': row[5],  
'zona': row[6]  
}  
\#print attrs

ElementTree.SubElement(comercializadoras\_tag, 'distribuidora',
attrib=attrs)

resultXML =
minidom.parseString(ElementTree.tostring(comercializadoras\_tag)).toprettyxml()  
resultXML\_utf8 = resultXML.encode('UTF-8')  
\#print resultXML\_utf8

with open(xmlFileName, 'w+') as xmlFile:  
xmlFile.write(resultXML\_utf8)

[/code]

I add a gist [snippet link][].

  [this file]: http://blog.ramsys.es/ramborg/wp-content/uploads/2013/04/Distribuidoras.csv
  [snippet link]: https://gist.github.com/ramsys/5419656
