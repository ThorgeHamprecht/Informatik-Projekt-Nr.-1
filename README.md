
 # Informatik Projekt von Jannik und Thorge
 
 ## Inhaltsverzeichnis

1. [ToDo-Liste](#ToDo)
2. [Stundenprotokoll](#prot)

  
 
 ## :heavy_check_mark:ToDo-Liste<a name="ToDo"></a>
 
 Hier wird von nun an (Mittwoch, 4. August) eine ToDo-Liste geführt, in der wir unsere Ziele und Fortschritte auf einen Blick sehen können. Wir erhoffen uns damit mehr Übersicht während dieses Projekts zu behalten. Die ToDo-Liste wird aktuell gehalten werden und alte Beiträge werden der Übersichtlichkeit halber gelöscht. Gelöschte Beiträge finden sich aber in unserem Protokoll in dem Eintrag an ihrem Erstellungstag wieder.
 
- [x] *Mehr Struktur in unser Protokoll bringen*
- [ ] *Programm oder Plattform für unsere App auswählen*
- [ ] *Ersten Prototyp unseres projekts anfertigen*
 
 
 ## :ledger:Stundenprotokoll<a name="prot"></a>
 
 <details>
<summary>Übersicht: Alle Einträge</summary>
<br>
  | <a href=#eins>Dienstag, 3. August</a> |
  <a href=#zwei>Mittwoch, 4. August</a> |
  <a href=#drei>Dienstag, 10. August</a> |
  <a href=#vier>Mittwoch, 11. August</a> |
  <a href=#fünf>Dienstag, 17. August</a> |
 
  | <a href=#sechs>Mittwoch, 18. August</a> |
  <a href=#sieben>Dienstag, 24. August</a> |
  <a href=#acht>Mittwoch, 25. August</a> |
  <a href=#neun>Diesntag, 31. August</a> |
  <a href=#zehn>Mittwoch, 1. August</a> |
</details>

 
 ### Dienstag, 3. August<a name="eins"></a> 
 
Zunächst haben wir unseren GitHub Account erstellt. Danach haben wir dieses Repository ertsellt und uns über erste Möglichkeiten zur Bearbeitung auf GitHub anhand des Codes Ihres *GitHub Repositorys* informiert. Anschließend begann unser erstes Brainstorming zur Wahl eines Projekts. Dabei haben wir zunächst an die Entwicklung eines kleinen Spiels gedacht wollten anschließend jedoch leiber eine App entwicklen, da diese in unseren Augen langlebiger ist und nicht nur eine Art Gimick, dass einmal verwendung findet und danach überflüssig ist. Unsere erste Idee ist eine App mit deren Hilfe man seinen Kleiderschrank digital katalogisieren kann. Dabei wollten wir unter anderem das einspeichern von outfits, sowie einen Überblick über Kleidungsstücke, die sich zurzeit in der Wäsche befinden implementieren.

### Mittwoch, 4. August<a name="zwei"></a>

Heute haben wir uns weiter mit Markdown und unserem GitHub Directory beschäftigt. dabei haben wir gelernt,wie man Dropdowns einfügt:

```markdown
 <details>
    <summary>Zusammenfassung des Dropdowns</summary>
    <br>
     Hier gehören die Details und der weitere Inhalt hin.
    </details>
```
  
  Wie wir leider feststellen mussten, funktionieren eingebettete Links in Dropdowns nach normaler Markdown schreibweise (` [Dienstag, 3. August](#eins)`) nicht. Deshalb mussten wir stattdessen html verwenden. Der Code hierfür war durch eine Recherche allerdings schnell zu finden: 
      
```html
<a href=HierDenLinkEinfügen>HierDenNamenEinfügen</a>
``` 
  
Und im Verlauf der Stunde haben wir uns auch das Einbetten von Code in unser Directory angeiegnet.
  
Außerdem haben wir uns angeschaut, wie man einen Ordner in seinem Repository anlegt und Dateien in diesem speichert. Wir haben hier nun zur Demonstration ein Bild hochgeladen und in unser Repository eingefügt.
  
![ProfilbildThorge](images/ProfilbildThorge.png)
  
Um unsere Arbeit besser Überblicken zu können haben wir folgendermaßen eine [**ToDo-Liste**](#ToDo) in unser Repository eingefügt:
      
    - [x] *Eine **ToDo-Liste** in unser Repository einfügen*
    - [x] *Mehr Struktur in unser Protokoll bringen*
    - [ ] *Umsetzbarkeit unserer App prüfen*
    - [ ] *Ersten Prototyp unseres Projekts anfertigen*
      
- [x] *Eine **ToDo-Liste** in unser Repository einfügen*
- [x] *Mehr Struktur in unser Protokoll bringen*
- [ ] *Umsetzbarkeit unserer App prüfen*
- [ ] *Ersten Prototyp unseres Projekts anfertigen*

### Dienstag, 10. August<a name="drei"></a> 

**Findung des geeigneten Programms zum Programmieren unserer App**

Sollten wir unsere App mit Swift programmieren?

Pro| Contra
------------ | -------------
• vermutlich "einfach" zu bedienen | • die App wird nicht auf Android funktionieren
• Apple-Design grafisch ansprechend | • eventuelle Online-Verfügbarkeit muss geprüft werden

Nach der letzten Stunde haben wir uns Zuhause nochn ein paar Gedanken über unsere App gemacht, dabei wollen wir nun eine ausschließliche IOS App mit [*XCode*](https://apps.apple.com/de/app/xcode/id497799835?mt=12) entwickeln. Wir haben uns für dieses Tool entschieden, da es einerseits die Programmiersprache [*Swift*](https://www.apple.com/de/swift/) beinhaltet, die auf das Programm abgestimmt sowie sehr anfängerfreundlich ist. Außerdem ist *XCode* ein First Party Tool und unterstützt damit alle Features der *IOS-Entwicklung*. Des weiteren wollen wir die App nur für eine Plattform entwicklen, um uns auf den wesentlichen Inhalt und nicht das optimieren beschäftigen zu müssen.

Hier ein kleines Beispiel zum reskalieren von Bildern. Somit kann man eine Art Collage in seinem Repository einfügen.
Der Code dafür sieht folgendermaßen aus:

```html
    <img src="Link zum Bild" alt="Bezeichnung" width="höhe" height="breite">
```
    
<img src="images/ProfilbildThorge.png" alt="ProfilbildThorge" width="200" height="200"> <img src="images/ProfilbildThorge.png" alt="ProfilbildThorge" width="200" height="200">

Außerdem ist es auch möglich ein Bild als Link zu verwenden und somit Youtube Videos interaktiv in sein Repository einzufügen.<br> 
Das Video lässt sich also druch anklicken des Bilds aufrufen.

<a href="http://www.youtube.com/watch?feature=player_embedded&v=LXb3EKWsInQ&ab_channel=Jacob%2BKatieSchwarz
" target="_blank"><img src="images/Thumbnail COSTA RICA.PNG" 
alt="COSTA RICA Video" width="360" height="201" border="100" /></a>



### Mittwoch, 11. August<a name="vier"></a>



### Dienstag, 17. August<a name="fünf"></a>














