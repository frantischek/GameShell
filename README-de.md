GameShell: ein "Spiel" zum Erlernen der Unix-Shell
==================================================

![Vom Spiel inspirierte Illustration](Images/illustration-small.png)

Erstsemesterstudenten oder Schülern die Verwendung einer Unix-Shell 
beizubringen, ist nicht immer die einfachste oder unterhaltsamste Aufgabe. 
GameShell wurde als Werkzeug entwickelt, um Studenten an der 
[Université Savoie Mont Blanc](https://univ-smb.fr) dabei zu helfen, 
mit einer *echten* Shell zu arbeiten – auf eine Weise, die das Lernen 
fördert und gleichzeitig Spaß macht.

Die ursprüngliche Idee stammt von Rodolphe Lepigre: Eine Standard-Bash-Sitzung 
mit einer entsprechenden Konfigurationsdatei auszuführen, die "Missionen" 
definiert, welche "geprüft" werden müssen, um im Spiel voranzukommen.

Hier ist das Ergebnis...

![GameShells erste Mission](Images/gameshell_first_mission_small.gif)

GameShell ist auf Englisch, Französisch, Italienisch und Deutsch verfügbar.

Senden Sie uns gerne Ihre Anmerkungen, Fragen oder Vorschläge, indem Sie 
[Issues](https://github.com/frantischek/GameShell/issues) eröffnen oder 
[Pull Requests](https://github.com/frantischek/GameShell/pulls) einreichen. 
Wir sind besonders an neuen Missionen interessiert, die Sie erstellen könnten!


Erste Schritte
--------------

GameShell sollte auf jedem Standard-Linux-System funktionieren, sowie auf 
macOS und BSD (obwohl wir auf letzteren Systemen weniger Tests durchgeführt 
haben). Unter Debian oder Ubuntu sind die einzigen Abhängigkeiten (neben 
`bash`) die Pakete `gettext-base` und `awk` (letzteres ist in der Regel 
standardmäßig installiert). Einige Missionen haben zusätzliche 
Abhängigkeiten: Diese Missionen werden übersprungen, wenn die 
Abhängigkeiten nicht erfüllt sind. Unter Debian oder Ubuntu führen Sie 
folgenden Befehl aus, um alle Spiel- und Missionsabhängigkeiten zu 
installieren:
```sh
$ sudo apt install gettext man-db procps psmisc nano tree ncal x11-apps wget
```
Lesen Sie das [Benutzerhandbuch](doc/user_manual.md) (auf Englisch), um zu 
erfahren, wie Sie die Spielabhängigkeiten auf anderen Systemen (macOS, 
BSD, ...) installieren.

Angenommen, alle Abhängigkeiten sind installiert, können Sie die neueste 
Version des Spiels ausprobieren, indem Sie die folgenden zwei Befehle in 
einem Terminal ausführen:
```sh
$ wget https://github.com/frantischek/GameShell/releases/download/latest/gameshell.sh
$ bash gameshell.sh
```
Der erste Befehl lädt die neueste Version des Spiels als selbstextrahierendes 
Archiv herunter, und der zweite Befehl initialisiert und startet das Spiel 
aus dem heruntergeladenen Archiv. Anleitungen zum Spielen werden direkt im 
Spiel bereitgestellt.

Beachten Sie, dass beim Beenden des Spiels (mit `Control-d` oder dem Befehl 
`gsh exit`) Ihr Fortschritt in einem neuen Archiv (genannt `gameshell-save.sh`) 
gespeichert wird. Führen Sie dieses Archiv aus, um das Spiel dort 
fortzusetzen, wo Sie aufgehört haben.


Wenn Sie es vorziehen, keine fremden Shell-Skripte auf Ihrem Computer 
auszuführen, können Sie ein Docker-Image mit folgendem erstellen:
```sh
$ mkdir GameShell; cd GameShell
$ wget --quiet https://github.com/frantischek/GameShell/releases/download/latest/Dockerfile
$ docker build -t gsh .
$ docker run -it gsh
```
Das Spiel wird NICHT gespeichert, wenn Sie es beenden, und zusätzliche 
Flags sind erforderlich, wenn Sie X-Programme von innerhalb von GameShell 
ausführen möchten. Weitere Informationen finden Sie in 
[diesem Abschnitt](./doc/deps.md#running-GameShell-from-a-docker-container) 
des Benutzerhandbuchs.


Dokumentation
-------------

Um mehr über GameShell zu erfahren, lesen Sie die folgenden Dokumente 
(auf Englisch):
- Das [Benutzerhandbuch](doc/user_manual.md) enthält Informationen darüber, 
  wie Sie das Spiel auf allen unterstützten Plattformen (Linux, macOS, BSD) 
  ausführen, erklärt, wie Sie das Spiel aus den Quellen starten, zeigt 
  Ihnen, wie Sie benutzerdefinierte Spielarchive erstellen (was nützlich 
  ist, wenn Sie GameShell für den Unterricht verwenden möchten), und mehr.
- Das [Entwicklerhandbuch](doc/dev_manual.md) enthält Informationen darüber, 
  wie Sie neue Missionen erstellen, Missionen übersetzen und an der 
  Entwicklung des Spiels teilnehmen können.


Wer entwickelt GameShell?
-------------------------

### Entwickler

Das Spiel wird derzeit entwickelt von:
* [Pierre Hyvernat](http://www.lama.univ-smb.fr/~hyvernat) (Hauptentwickler,
  [pierre.hyvernat@univ-smb.fr](mailto:pierre.hyvernat@univ-smb.fr)),
* [Rodolphe Lepigre](https://lepigre.fr).

### Missionsmitwirkende

* Pierre Hyvernat
* Rodolphe Lepigre
* Christophe Raffalli
* Xavier Provencal
* Clovis Eberhart
* Sébastien Tavenas
* Tiemen Duvillard

### Übersetzung

#### Italienische Version

* Daniele Scasciafratte (@mte90)
* Paolo Mauri (@maupao)
* Marco Ciampa (@ciampix)
* Antonio Vivace (@avivace)
* Lorenzo Millucci (@lmillucci)
* Sirio Negri (@ziriuz84)
* Domenico Mammola (@domenicomammola)
* Leonardo Canello (@anulo2)
* @michirod
* @serhack
* WhiteShield (@wshield05)
* @gioisco

### Besonderer Dank

* Allen Studenten, die *viele* Fehler in den frühen Versionen gefunden haben.
* Joan Stark (auch bekannt als jgs), die in den späten 90ern Hunderte von 
  ASCII-Kunstwerken entworfen hat. Die meisten ASCII-Kunstwerke in 
  GameShell stammen von ihr.


Lizenz
------

GameShell wird unter der [GPLv3](https://www.gnu.org/licenses/gpl-3.0.en.html) 
veröffentlicht.

Bitte verlinken Sie auf dieses Repository, wenn Sie GameShell verwenden.

GameShell ist Open Source und kostenlos nutzbar. Eine Möglichkeit, die 
erforderliche Arbeit anzuerkennen, besteht darin, eine echte Postkarte zu 
senden an:

```
  Pierre Hyvernat
  Laboratoire de Mathématiques, CNRS UMR 5127
  Université de Savoie
  73376 Le Bourget du Lac
  FRANCE
```
