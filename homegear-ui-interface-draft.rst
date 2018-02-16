RPC-Funktionen für die Generierung von Visualisierungen
#######################################################

Version: 16. Februar 2018


Ziel
****

Generell ist das Ziel, dass sich eine Visualisierung ohne weitere Informationen vollständig aus Homegear heraus generieren kann. Dafür müssen in Homegear RPC-Funktionen implementiert werden, welche der Visualisierung sämtliche notwendigen Informationen zur Verfügung stellen.


Räume
*****

Räume können über die `Raum-RPC-Funktionen <https://ref.homegear.eu/rpc.html#affixSection16>`_ (mit ``getRooms()``) abgerufen werden. Aktuell lassen sich nur Geräte zu Räumen zuordnen. Dies wird geändert, so dass sich Variablen Räumen zuordnen lassen.


Gewerke
*******

Gewerke wie Licht, Heizung oder Rolläden können über über Kategorien realisiert werden (siehe die `Kategorie-RPC-Funktionen <https://ref.homegear.eu/rpc.html#affixSection16>`_). Wie bei den Räumen lassen sich aktuell nur Geräte zu Kategorien zuordnen. Dies wird dahingehend geändert, dass sich ebenso Variablen Kategorien zuordnen lassen.


Visualisierungs-Elemente
************************

Allgemein muss zwischen einfachen und zusammengesetzten Elementen unterschieden werden. Ein einfaches Element ist maximal zwei Variablen zugeordnet, einer Eingangs- und/oder einer Ausgangsvariable. Komplexe Elemente setzen sich aus mehreren einfachen Elementen zusammen. Als Beispiel sei eine Mediensteuerung genannt.