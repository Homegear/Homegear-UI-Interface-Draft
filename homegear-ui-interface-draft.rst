RPC-Funktionen für die Generierung von Visualisierungen
#######################################################

Version: 17. Februar 2018


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

Allgemein muss zwischen einfachen und zusammengesetzten Elementen unterschieden werden. Ein einfaches Element ist maximal zwei Variablen zugeordnet, einer Eingangs- und/oder einer Ausgangsvariable. Zusammengesetzte Elemente setzen sich aus mehreren einfachen Elementen zusammen. Das zusammengesetzte Element besteht aus einer Gitterstrukter in welcher die einfachen Elemente angeordnet werden können. Als Beispiel sei eine Mediensteuerung genannt.

Folgende Informationen werden von der Visualisierung benötigt, um Visualisierungselemente zu erstellen:

* Raum oder Gewerk des Elementes
* Position des Elementes relativ zu anderen Elementen
* Art des Elementes
* Eingangs- und Ausgangsvariable des Elementes
* U. U. Wertebereich der visualisierten Variablen
* Drei Beschreibungstexte - über, auf und unter einem inneren Element
* U. U. Einheit (z. B. °C)
  
Für zusammengesetzte Elemente werden zusätzlich noch folgende Informationen benötigt:

* Art der inneren Gitterstrukter
* Referenz auf die verwendeten einfachen Elemente
    * Diese liefern als relative Position die Position innerhalb des zusammengesetzten Elementes
* Position des zusammengesetzten Elementes relativ zu anderen Elementen
  
Die oben genannten Informationen sollen in einer zusätzlichen Visualisierungs XML-Datei in der Homegearinstallation gespeichert sein. Abgerufen werden sollen die Informationen pro Raum oder pro Gewerk. Die dafür erforderlichen RPC-Funktionen sind noch zu implementieren.