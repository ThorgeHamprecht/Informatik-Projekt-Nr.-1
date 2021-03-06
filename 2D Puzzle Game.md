# 2D Puzzle Game
## Links

1. [Blog](https://github.com/ThorgeHamprecht/Informatik-Projekt-Nr.-1)
2. [Das Spielkonzept](#Setup)
3. [Erklärung des Codes](#Erklärung)
5. [Spiel - Snap! Cummunity Site](https://snap.berkeley.edu/project?user=faiture&project=2D%20Puzzle%20Game)



<h1>1. Spielkonzept</h1> <a name="Setup"></a>
Bei unserem Spiel handelt es sich um ein 2D Adventure Spiel mit Puzzle und Plattform Elementen. Der Spieler hat dabei die Aufgabe das Ende des Levels durch das Lösen von "Rätseln" und durch das Bewältigen von Platform-Passagen zu erreichen bevor die zeit abläuft. Dabei muss er versuchen nicht an den diversen Fallen im Spiel zu sterben, um siegreich aus dem Spiel hervorzugehen.

Für das Progammieren des Spiels haben wir die Blockprogrammiersprache Snap! benutzt. Diese funktioniert vollkommen im Web und kann daher ohne Installation eines Programms auf jedem Gerät mit Internetzugang verwendet werden.


Hier einmal ein Video des gesamten Spiels mit allen seinen Funktionen:

https://user-images.githubusercontent.com/88385813/144759791-de17a98b-73cd-49a5-bfcf-f4a6e968e209.mp4

<h3>1.1 Das Setup</h3>

Bevor das Spiel startet, hat der Spieler die Möglichkeit, sich in dem Startmenü im Zuge der Anleitung über das Spielprinzip, das Spielziel und das Steuern der Spielfigur zu informieren.
Anschließend hat der Spieler die Möglichkeit sich über den Button "Charakter Wählen" eine beliebige Spielfigur auszusuchen.
Dabei gibt es drei Figuren zur Wahl.

<h3>1.2 Spielstart</h3>

Fühlt sich der Spieler bereit, so kann er über die Betätigung des Buttons "Spiel Starten" das Spiel beginnen.
Folglich befindet sich die Spielfigur in der Stage 0 sowie im ersten Level wieder.
Die Spielfigur kann auf der braunen Unterfläche nach rechts und links laufen. Zudem besteht die Möglichkeit mit Betätigung der Taste "S" oder dem Leerzeichen zu springen.
Oben links in der Ecke werden die drei Leben der Spielfigur angezeigt. Diese werden, z.B. bei Berührung der Lava oder der Speere weniger, bis die Spielfigur schließlich stirbt und das Spiel vorbei ist.


<h3>1.3 Spielkonzept/Spielziel</h3>


Der Spieler steuert anschließend die Spielfigur in die verschiedenen Richtungen. 
Das Ziel des Spiels ist es, das Level zu schaffen.
Dafür muss der Spieler die Fahne am Ende des Spiels erreichen. Wie der Spieler seine Spielfigur dort hinsteuert, muss er selbst herrausfinden.
Auf dem Weg zum Abschließen des Levels erwarten den Spieler viele Herausfoderungen. 
Beispielsweise muss an einer Stelle ein Schlüssel gefunden werden, um ein Tor zu öffnen. Zudem muss der Spieler es schaffen, dass seine Spielfigur nicht in die Lava tritt oder von den Speeren getroffen wird.
Des Weiteren ist die zeit zur Bewältigung des Leveles begrenzt. Der Spieler hat nur 60 Sekunden Zeit, um das level zu beenden! Schafft er dies nicht, verliert er.

Mit diesem Spielkonzept war unsere Absicht ein spannendes, kreatives und reizvolles 2D Spiel zu entwerfen, welches für den Spieler leicht fordernd, aber doch machbar ist.


<h1>Erklärung des Codes</h1> <a name="Erklärung"></a>

<h1>2.1 Grundeinstellungen für die Spielfigur </h1>

Die Spielfigur ist nicht zu sehen, wenn das Spiel gewonnen wurde, wenn die grüne Fahne gedrückt wird und wenn sich der Spieler im Menü befindet. Die grüne Fahne markiert dabei immer den Start des Programms und wird somit beim Öfnnen des Spiels aktiviert und es werden die dazugehörigen Scripte ausgeführt.

<details>
<summary>Sprite Spieler - hide </summary>
<br>
 <img width="178" alt="Bildschirmfoto 2021-11-27 um 17 29 08" src="https://user-images.githubusercontent.com/88385954/143689249-d62624d5-f297-4acd-9df0-fd9bedb13b88.png">
</details>

Wenn das Spiel gestartet wird, wird die Größe der Spielfigur auf 20% der Ursprungsgröße gesetzt, die X- und Y- Koordinaten werden mit 0;-60 festgelegt, die Blickrichtung ist nach links gerichtet. Die Spielfigur befindet sich im Vordergrund.
Zudem wird sie nun sichtbar.

<details>
<summary>Sprite Spieler - "when I receive SpielStartet"" </summary>
<br>
 <img width="178" alt="Bildschirmfoto 2021-11-27 um 17 21 59" src="https://user-images.githubusercontent.com/88385954/143688995-335dff8c-3050-432f-b5ae-83a9f0f751a1.png">
</details>

<h2>2.1.1 Bewegung der Spielfigur</h2>


<BODY>
  <IMG SRC="https://github.com/ThorgeHamprecht/Informatik-Projekt-Nr.-1/blob/main/GIFS/SpielerMovementGIF.gif">
</BODY>

 <h2> Horizontale Bewegung der Spielfigur </h2>


Immer wenn das Spiel gestartet wird ist die Bewegungsgeschwindigkeit = 10.

<details>
<summary>Sprite Spieler - Bewegungsgeschwindigkeit </summary>
<br>
 <img width="241" alt="Bildschirmfoto 2021-11-27 um 17 51 08" src="https://user-images.githubusercontent.com/88385954/143689957-7b96f220-3990-4b49-97e9-478abf444132.png">
</details>

Sobald das Spiel startet wird die Variable "SpielerBewegung" = 1 gesetzt. 
<details>
<summary>Sprite Spieler - Variable "SpielerBewegung" </summary>
<br>
 <img width="173" alt="Bildschirmfoto 2021-11-27 um 17 38 01" src="https://user-images.githubusercontent.com/88385954/143689544-097c831e-8b2c-4b90-a4ee-d61814c6121e.png">
</details>

Anschließend ist für die horizontale Bewegung der folgende Code relevant. Zunächst wird geprüft, ob die Variable "SpielerBewegung" = 1 ist. Wenn dies der Fall ist, werden folgende Bedingunen geprüft.
Zunächst wird die Bewegungsrichtung rechts betrachtet.
Hier ergibt sich im Code eine Besonderheit, weil die Spielfigur sich nur nach rechts bewegen darf, wenn das Tor, welches sich in Stage 2 befindet offen ist. Somit wird zunächst geprüft, ob das Tor offen ist. Dies wird später in der Tor Erklärung weiter erläutert.
Wenn das Tor offen ist und die rechte Pfeiltaste oder "D" auf der Tastatur gedrückt wird, dann wird die X-Koordinate mit der Bewegungsgeschwindigkeit 10 geändert. 
Dabei ändert sich an der Blickrichtung der Spielfigur nichts.

Die Bewgung nach links gestaltet sich leichter. Hier muss nicht geprüft werden, ob das Tor in Stage 2 offen ist.
Somit wird lediglich, wenn die "SpielerBewegung" = 1 ist, geprüft, ob der linke Pfeil auf der Tastatur gedrückt wird oder ob "A" auf der Tastatur betätigt wird.
Wenn dies der Fall ist, bewegt sich die Spielfigur in die negative Richtung auf der X-Achse mit der Bewegungsgeschwindigkeit 10.

<details>
<summary>Sprite Spieler - Horizontale Bewegung </summary>
<br>
<img width="331" alt="Bildschirmfoto 2021-11-27 um 17 37 47" src="https://user-images.githubusercontent.com/88385954/143689535-51b77eed-a0be-4431-a248-d7611ba95315.png">
</details>

<h2> 2.1.2 Die Sprungeigenschaft der Spielfigur</h2>

Sobald das Spiel gestartet wird, werden folgende Variablen definiert, die für den Sprung der Spielfigur wichtig sind:

<details>
<summary>Sprite Spieler - "when I recive "BerühreBoden"" </summary>
<br>
<img width="188" alt="Bildschirmfoto 2021-11-27 um 14 56 28" src="https://user-images.githubusercontent.com/88385954/143684429-1d1b15b0-bc6e-47e9-b04f-dd87c387dc42.png">
 </details>

Um das Springen der Spielfigur zu ermöglichen, haben wir uns einige Dinge überlegt:
Zunächst wird mit dem ersten Codeblock, sobald das Spiel gestartet wird, geprüft, ob die Spielfigur die BodenHitbox berührt. Dieses Objekt ist ein sehr dünner, grüner Streifen welcher nicht sichtbar ist:

 <details>
<summary><b>Erklärung Sprite Bodenhitbox</b></summary>
<br>
 <mark> 
  
  Sobald das Spiel gestartet wird, wird das Kostüm zu dem dünnen, grünen Streifen geändert. 
Zudem wird eingestellt, dass die grüne Linie im Vordergrund ist, somit also Einfluss auf die Spielfigur hat. 

 
 Sprite BodenHitbox - grüne Linie:
 
<img width="90" alt="Bildschirmfoto 2021-11-27 um 15 01 24" src="https://user-images.githubusercontent.com/88385954/143684643-282d77f8-7e3c-4666-a45b-dab6d7c209ad.png">

Des Weiteren ist der "ghost effect" = 100. Somit ist die grüne Linie nicht zu sehen, führt aber trotzdem seine Scripte in Interaktion mit anderen Objekten aus.
Des Weiteren soll diese unsichtbare grüne Linie in jeder Stage Anwendung finden. Dabei gibt es eine BodenHitbox mit Loch, damit der Spieler in der linken Stage in das Loch, welches später erklärt wird, fallen kann. Dies ist mit den folgenden Codes eingestellt. Beim Game Over wird das Kostüm wieder zurückgesetzt, damit bei erneutem Spielstart nicht das Kostüm mit Loch aktiviert ist.
  

<img width="250" alt="Bildschirmfoto 2021-11-27 um 15 01 05" src="https://user-images.githubusercontent.com/88385954/143684625-acf1ec9f-484c-4a55-90f0-0a6b83771d89.png"> </mark>

------------------------------------------------------------------------------------------------------------------------------------------------------
</details>

Wenn diese Bedingung zutrifft, wenn also zutrifft, dass die Spielfigur die unsichtbare, grüne Linie berührt wird der Spieler auf die Y-Achse -60 gestellt und die Variable "BerührtBoden" = 1 gesetzt.
Zudem wird "BerühreBoden" ausgeführt.
Berührt die Spielfigur nicht die "BodenHitbox" so wird die Variable "BerührtBoden" = 0 gesetzt.

<details>
<summary>Code für "If touching BodenHitbox"</summary>
<br>
<img width="219" alt="Bildschirmfoto 2021-11-27 um 14 55 57" src="https://user-images.githubusercontent.com/88385954/143684411-3075cc95-155d-4b99-ae29-acaaa444b82b.png">

  </details>

Der folgende Code beschreibt die Auswirkungen, wenn die Spielfigur den Boden berührt, "BerühreBoden" also ausgeführt ist.
In diesem Fall wird die Fallgeschwindigkeit = -3 gesetzt. 
Mit den folgenden drei Bedingungen wird das Springen eingestellt. Egal ob der Spieler die Leertaste, den Pfeil nach oben oder die Taste "W" betätigt, wird der Y-Wert um die zuvor definierte Sprungkraft geändert. Zudem wird der Befehl "gesprungen" ausgeführt.

<details>
<summary>Sprite Spieler - "when I recive "BerühreBoden"" </summary>
<br>
<img width="196" alt="Bildschirmfoto 2021-11-27 um 14 33 00" src="https://user-images.githubusercontent.com/88385954/143683546-ea652c49-4d5e-403c-a630-90aaf655737a.png">
 
 </details>

Mit diesem Code werden die beiden vorherigen Bedingungen vorrausgesetzt. Der Code wird so lange ausgeführt wie die Variable "BerührtBoden" = 0 ist, die Spielfigur also nicht die "BodenHitbox" berührt.
Dann wird die Fallgeschwindigkeit mit 1,2 multipliziert und die Y-Koordinate wird entsprechend geändert.
Dadurch erhöhrt sich die Fallgeschwindigkeit, je länger sich die Spielfigur im Fall befindet. Dies soll die natürliche Beschleunigung im Fall der Spielfigur darstellen.

<details>
<summary>Sprite Spieler - "when I recive "BerühreBoden"" </summary>
<br>
<img width="359" alt="Bildschirmfoto 2021-11-27 um 14 25 49" src="https://user-images.githubusercontent.com/88385954/143683287-3a68c976-c91b-4e03-ae5c-1884d70dde74.png">
 </details>
 
 Hier mit sichtbar gemachter "BodenHitbox" der Code in seiner Ausführung im Spiel:
 
 ![BodenHitbox](https://user-images.githubusercontent.com/88385813/144720885-bff496aa-9340-4474-9f1b-0ee18f2dc0c9.gif)

 <h1> 2.2 Lebensverlust der Spielfigur </h1>

Im Folgenden wird das Prinzip des Lebensverlustes und des Erhaltens von Schaden beschrieben.
In unserem Spiel hat die Spielfigur drei Leben. Sind diese Leben verbraucht, so hat der Spieler verloren.
Die drei Leben befinden sich im oberen linken Eck des Spielrandes.


Der folgende Code soll beispielhaft die Funktion der Herzen erläutern.
Der Code codiert für die generellen Informationen des Herzens. Immer wenn das Spiel gestartet wird erscheint das Herz. Dies ist durch die Befehle "when I receive SpielStartet" und "switch costum to Herz" ausgedrückt. Durch den Befehl "set size to 20%" wird die Orginalgröße des Herzens auf dem ursprünglich eingefügten png-Bild auf 20% der Originalgröße herabgesetzt, damit alle drei Herzen nebeneinander passen.
Das Herz soll zudem im Vordergrund erscheinen. Um dies zu erreichen haben wir den Code "go to front layer" eingefügt. 
 
Ein weiterer wichtiger Teil dieses Code-Blockes ist die eingestellte Position des Herzens. Durch die X-Koordinate -140 und die Y-Koordinate 172 haben wir die Position am oberen linken Rand des Spieles eingestellt. Das dritte Herz ist dabei das Herz, welches sich von den drei Herzen am weitesten rechts befindet, weil dieses Herz bei einem Schaden zuerst reagieren und erlischen soll, damit die Leben von rechts nach links weniger werden. Der letzte Befehl in diesem Codeblock ist der Befehl "show". Damit erreichen wir, dass das Herz erst bei Spielstart angezeigt wird.

<details>
<summary>Sprite Leben 3 - "when I receive SpielStartet" </summary>
<br>
<img width="185" alt="Bildschirmfoto 2021-11-27 um 18 58 24" src="https://user-images.githubusercontent.com/88385954/143691819-6f7a1c0e-73fc-4a44-96af-5975d428d3d3.png">
</details>

Durch den folgenden Code haben wir den Kostüm-Wechsel programmiert. Wenn der Befehl "TestSchaden" ausgeführt wird, wird dieser Code ausgeführt. Dieses Ausführen des Codes ist allerdings an die Bedingung gekoppelt, dass sich die Lebenanzahl über 1,5 befindet. Diese Zahl startet bei Spielstart bei drei Leben. Das Event "TestSchaden" wird im Spieler-script erst nachdem bereits 0,5 von den ursprünglichen 3 abgezogen worden sind ausgeführt. Somit wird dieser Code in dem Script "Leben 3" genau 2 mal ausgeführt: Einmal bei 2,5 und das nächste mal bei 2. Sind diese Bedingungen erfüllt, so wird das Kostüm gewechselt.

<details>
<summary>Sprite Leben 3 - "when I receive TestSchaden" </summary>
<br>
<img width="216" alt="Bildschirmfoto 2021-11-27 um 19 01 34" src="https://user-images.githubusercontent.com/88385954/143691893-d98d60d2-0758-44bf-afb4-3db6e4d1e6b0.png">
</details>

Die drei erstellten Kostüme gelten für alle drei Herzen und sehen wie folgt aus:

1. Hier ist das Herz noch "ganz". Der Code wurde bisher nicht ausgeführt.

<img width="60" alt="Bildschirmfoto 2021-11-27 um 19 05 16" src="https://user-images.githubusercontent.com/88385954/143692053-3a56958a-cdf2-413f-be6f-c95372828242.png">

2. Hier ist ein halbes Herz zu sehen. Der Coder wurde bisher einmal, bei der Lebenanzahl von 2,5 ausgeführt.
<img width="61" alt="Bildschirmfoto 2021-11-27 um 19 05 49" src="https://user-images.githubusercontent.com/88385954/143692401-00180c6e-659d-4324-832e-9790dd3e914f.png">

3. Hier ist nur noch der Umriss des Herzens zu sehen. Der Code wurde zweimal ausgeführt und die Lebenanzahl ist nun nicht mehr größer als 1,5. Der Spielende hat somit ein ganzes Leben verloren.

<img width="58" alt="Bildschirmfoto 2021-11-27 um 19 06 02" src="https://user-images.githubusercontent.com/88385954/143692581-58476013-e18d-4ee5-84ee-fea8bb0a101f.png">


Damit das Herz nicht immer gezeigt wird, muss es in verschiedenen Stages versteckt werden. Dies gilt:
1. Wenn das Programm gestartet wird soll das Herz nicht zu sehen sein. Darum haben wir "When I receive flag hide" eingefügt.
2. Wenn Der Spielende auf das Menü klickt, nach Aufruf des Menüs soll das Leben noch nicht sichtbar sein. Darum haben wir den Code "When I receive Menu hide" eingefügt.
3. Außerdem soll das Herz verschwinden, wenn der Spielende das Level verloren hat und wieder zum Startmenü zurückgeleitet wird. Der Code dafür ist das dritte Script im folgenden Bild. 
4. Wenn die Stage "GameWon" ausgeführt wird, soll das Herz verschwunden sein.

<details>
<summary>Sprite Leben 3 - hide </summary>
<br>
<img width="172" alt="Bildschirmfoto 2021-11-27 um 19 14 19" src="https://user-images.githubusercontent.com/88385954/143699101-5cb4edfc-6c31-44e4-9538-6e8ed21adcc1.png">
</details>


Bei Leben 2 und bei Leben 1 ist der Code ähnlich wie bei Leben 3 aufgebaut. Der erste Unterschied liegt in den Koordinaten der Herzen. Die Herzen sollen nebeneinander oben links im Bild zu sehen sein.
Die Position des Herzens 2 wird durch die X-Koordinate -180 und die Y-Koordinate 172 eingestellt. Das zweite Herz befindet sich damit genau zwischen dem dritten Herz und dem zweiten Herz. 
Die Position des Herzens 1 wird durch die X-Koordinate -220 und die Y-Koordinate 172 auf den oberen linken Rand des Bildschirmes eingestellt. Das zweite Herz befindet sich damit genau zwischen dem dritten Leben und dem zweiten Leben. 
Der zweite Unterschied liegt in der Anzahl der Leben, bei denen die Funktionen ausgeführt werden. Logischerweise soll jedes halbes Leben angezeigt werden. Deshalb verschiebt sich auch der Bereich, bei dem die Funktionen ausgeführt werden, bei jedem Leben weiter nach unten.
Das Kostüm bei Herz 2 genau zwei mal geändert. Einmal wenn die Lebensanzahl genau 1,5 ist und das zweite mal wenn die Lebenanzahl genau 1 ist.
Das Kostüm bei Leben 1 wird bei der entsprechenden Lebenanzahl 0,5 und bei 0 ändert. Bei 0,5 wird nur, wie auch zuvor, ein halbes Herz abgezogen. Bei der Lebensanzahl 0 ist noch eine besonderheit vorzufinden. Der Spielende hat alle Leben verloren und somit ist das Spiel beendet. 
Deshalb wird nach Abzug des letzten halben Lebens "broadcast Tod" ausgeführt. Außerdem wird die Spielmusik gestoppt und die Titelmusik wird abgespielt.

Die Codes für Leben 2 und für Leben 1 sind hier dargestellt:

<details>
<summary>Sprite Leben 2 </summary>
<br>
 <img width="213" alt="Bildschirmfoto 2021-11-27 um 20 02 40" src="https://user-images.githubusercontent.com/88385954/143719046-a6b92b86-a03a-4ecf-a833-d83d2f6fa157.png">
<img width="186" alt="Bildschirmfoto 2021-11-27 um 20 02 54" src="https://user-images.githubusercontent.com/88385954/143719059-d4782ca1-47d5-4779-91cb-a20eeba545a0.png">
<img width="172" alt="Bildschirmfoto 2021-11-27 um 19 14 19" src="https://user-images.githubusercontent.com/88385954/143699101-5cb4edfc-6c31-44e4-9538-6e8ed21adcc1.png">
</details>

<details>
<summary>Sprite Leben 1 </summary>
<br>
 <img width="213" alt="Bildschirmfoto 2021-11-27 um 20 04 20" src="https://user-images.githubusercontent.com/88385954/143719110-cb3fe00d-fe67-484a-97e8-a40b665dfc38.png">
<img width="184" alt="Bildschirmfoto 2021-11-27 um 20 04 31" src="https://user-images.githubusercontent.com/88385954/143719119-fb05f635-a2a8-4959-b1b6-d235a12dadd7.png">
<img width="172" alt="Bildschirmfoto 2021-11-27 um 19 14 19" src="https://user-images.githubusercontent.com/88385954/143699101-5cb4edfc-6c31-44e4-9538-6e8ed21adcc1.png">
 </details>


Mit dem fogenden Code haben wir die Grundlage für den Lebensverlust geschaffen. Dieser Befehl wird nun ausgeführt wenn die Spielfigur sich auf dem "Sprite", in unserem Fall der Lava befindet. Wir wollen erreichen, dass mit der Berührung der Spielfigur Schaden hinzugefügt wird. Zunächst haben wir die Bedingung, dass dieser Code ausgeführt wird, auf 0,2 Sekunden eingestellt. Dadurch wird der Schaden bei erstmaligem Betreten der Lava quasi direkt ausgeführt.  Dann verliert die Spielfigur 0,5 Leben. Die Steuerung der Herzen erfolgt dann durch die Anweisung "broadcast TestSchaden". 
 
Dieser Schaden wird außerdem durch einen von uns eingefügten Sound unterstützt. Mit der Anweisung "set volume to 100%" und "play sound schaden" haben wir diese Anweisung in Code umgesetzt. 
 
Zum Schluss steht die Anweisung 0,65 Sekunden zu warten. Damit wollen wir bewirken, dass nicht dauerhaft ein halbes Leben abgezogen wird, sondern nur wenn die Spielfigur sich auf dem "Sprite" Lava befindet. Somit kann der Spieler die Figur beim erreichen der Lava auch wieder herausbewegen, um weiteren Schaden zu verhindern. Wenn sich der Spieler jedoch auch nach 0,65 Sekunden immer noch auf der Lava befindet wird dieser Code erneut ausgeführt. Der Spieler erhält wieder Schaden.

 <details>
<summary>Sprite Spieler - "when touching Sprite" </summary>
<br>
<img width="187" alt="Bildschirmfoto 2021-11-27 um 18 46 43" src="https://user-images.githubusercontent.com/88385954/143691508-09cc8e46-42e7-4b20-92eb-084805ea0579.png">
</details>
 
Die Lava selbst ist nur in Stage 0 zu sehen und sie ist immer aktiv.
 
 <details>
<summary>Sprite Lava - "when I receive menu"</summary>
<br>
  <img width="198" alt="Bildschirmfoto 2021-12-06 um 20 14 26" src="https://user-images.githubusercontent.com/88385954/144907751-d824259c-f5d4-4d5d-8003-dd2716e0e9c7.png">
</details>
 
 ![HerzenUndSchaden](https://user-images.githubusercontent.com/88385813/144721089-f77e5e48-34ad-4ea9-ae2c-d65b1ae354b9.gif)

Zudem wird auch ein Leben abgezogen wenn die Spielfigur mit den Speeren in Berührung kommt. Dabei ist zunächst wichtig, dass der Speer nur Schaden verursachen soll, während er fällt. Da das fallen mithilfe der "glide" Funktion stattfindet, kann einfach am Anfang und Ende der Funktion eine Vraiable verändert werden. Es handelt sich hierbei um die Variable "SpeerUnterwegs" hat diese den Wert 1, so ist der Speer unterwegs, der Speieler soll nun also bei Berührung Schaden erhalten können.

 <details>
<summary>Sprite Speer - Script</summary>
<br>
<img src="https://user-images.githubusercontent.com/88385813/144925284-64500692-e03c-4005-a14d-9d19aca6fad1.png" alt="https://user-images.githubusercontent.com/88385813/144925284-64500692-e03c-4005-a14d-9d19aca6fad1.png">
</details>

 
Wenn der Spieler jetzt den Speer berührt und die Variable "SpeerUnterwegs" den Wert 1 hat bekommt der Speieler ein Herz Schaden. Dafür wird wie zuvor bei der "Lava" Schaden gebroadcastet und das Script der Herzen aktiviert. Der einzige Unterschied ist hierbei, dass der Speer im Gegensatz zu der Lava ein ganzes Leben abzieht, deshalb wird die Variable "Leben" zu Anfang um 1 verringert:
 
 <details>
<summary>Sprite Speer - Lebensverlust</summary>
<br>
<img src="https://user-images.githubusercontent.com/88385813/144925757-8d5a85fd-b6f4-41e3-ad00-cb9ce95e64da.png" alt="https://user-images.githubusercontent.com/88385813/144925757-8d5a85fd-b6f4-41e3-ad00-cb9ce95e64da.png">
</details>
 

Des weiteren wird mit dem Broadcast "SpeerSchaden" der passende Sound im Spielerobjekt abgespielt:
 
 <details>
<summary>Sprite Spieler - Schadenssound</summary>
<br>
<img src="https://user-images.githubusercontent.com/88385813/144926017-c7699838-4960-4311-b5e7-82a2210edaa6.png" alt="https://user-images.githubusercontent.com/88385813/144926017-c7699838-4960-4311-b5e7-82a2210edaa6.png">
</details>


Auch der Speer erscheint natürlich nur in derdafür vorgesehenen Stage. Der Code dafür sieht folgendermaßen aus und funktioniert wie im folgenden bei der Stageauswahl erklärt:

  <details>
<summary>Sprite Speer - show bzw. hide </summary>
<br>
<img src="https://user-images.githubusercontent.com/88385813/144926449-e57b5c78-7918-49ed-8f0d-4213ca0b0116.png" alt="https://user-images.githubusercontent.com/88385813/144926449-e57b5c78-7918-49ed-8f0d-4213ca0b0116.png">
</details>



Dieser eine Speer wurde einfach dupliziert und die Variablen zur Bestimmung der Startposition der "glide" Funktion geändert, so dass am Ende mehrere Speere nebeneiannder sind. Zuletzt wird jedem 2. Speer noch eine Sekunde Verzögerung vor dem Ausführen der "glide" Funktion durch die "wait" Funktion gegeben, so dass die Speere in zwei Wellen fallen.

 <details>
<summary>Sprite Speer - !.Welle und 2. Welle </summary>
<br>
<img src="https://user-images.githubusercontent.com/88385813/144927166-a54eca51-2399-47d0-b4a1-43934edde769.png" alt="https://user-images.githubusercontent.com/88385813/144927166-a54eca51-2399-47d0-b4a1-43934edde769.png">
<img src="https://user-images.githubusercontent.com/88385813/144927186-a43a9328-b34d-4816-9043-182480c9b148.png" alt="https://user-images.githubusercontent.com/88385813/144927186-a43a9328-b34d-4816-9043-182480c9b148.png">
</details>

 Hier nun einmal die Speere in Aktion:

![HerzenUndSchaden - Speer](https://user-images.githubusercontent.com/88385813/144721271-7ddaa1a5-7132-497a-99cd-d8731c8134a9.gif)

<h2> 2.3 Wechsel der Spielfigur zwischen den Stages </h2>

Im Folgenden wird beschrieben, wie der Hintergrund, also die Stages wechseln, wenn die Spielfigur die Ränder der jeweiligen Stages erreicht.
Die Hauptschwierigkeit besteht darin, dass die Spielfigur, wenn sie beispielsweise am linken Rand das Bild verlässt, anschließend am rechten Rand der nächsten Stage erscheinen muss.
Zu Beginn des Spiels soll die Spielfigur bei Level 1 und Stage 0 erscheinen.

<details>
<summary>Sprite Stage - "when I receive SpielStartet" </summary>
<br>
<img width="217" alt="Bildschirmfoto 2021-11-28 um 10 09 18" src="https://user-images.githubusercontent.com/88385954/143745614-11c04f43-3e2b-47d4-9457-7122b6a214a7.png">
</details>

Nun kann sich der Spieler sowohl nach links, als auch nach rechts bewegen.
Es wird geprüft, ob die Spielfigur die unsichtbare Wand am linken Rand der Stage 0 berührt.
Dieser ist durch den ghost-effect unsichtbar.
Wenn die Spielfigur sowohl den linken Rand der Stage 0 berührt und dazu noch "A" oder den Linkspfeil betätigt, der Spieler die Spielfigur also noch weiter nach links bewegen möchte, dann werden zwei Befehle ausgeführt:

Zunächst wird Level 1 Stage 1 ausgeführt.
1. Der Befehl für die jeweilige Stage. Je nach dem in welcher Stage sich die Spielfigur befinden wird die Stage verändert.
2. Spieler rechts am Rand. Dieser Befehl ist wichtig, damit die Spielfigur in der neuen Stage am linken Rand erscheint.

Dies ist im folgenden Code dargestellt. Dort lässt sich erkennen, dass immer zunächst geprüft wird in welcher Stage sich die Spielfigur aktuell befindet und anschließend der Befehl für die jeweilige neue Stage ausgeführt wird.

<details>
<summary>Sprite RandLinks - "when touching Spieler" </summary>
<br>
<img width="362" alt="Bildschirmfoto 2021-11-28 um 10 16 23" src="https://user-images.githubusercontent.com/88385954/143750759-61b675f6-365e-462e-a246-3dd759d4ebc8.png"><img width="172" alt="Bildschirmfoto 2021-11-28 um 11 16 40" src="https://user-images.githubusercontent.com/88385954/143763914-8a1b07ac-339d-4c6b-8cb3-783c1bffbcc9.png">
</details>

Nun müssen die beiden aufgestellten Befehle ausgeführt werden.
Der erste Befehl wird ausgeführt, indem die Stage entsprechend verändert wird. Es gibt 6 verschiedene Stages im Spiel.

<details>
<summary>Sprite Stage - Costumes </summary>
<br>
 <img width="85" alt="Bildschirmfoto 2021-11-28 um 10 11 06" src="https://user-images.githubusercontent.com/88385954/143746958-bada372b-bb74-470c-992c-d1390a83123c.png">
</details>

Diese werden dann mit dem Auführen der entsprechenden Befehle umgesetzt.

<details>
<summary>Sprite Spieler - "when I receive Level x Stage y" </summary>
<br>
 <img width="227" alt="Bildschirmfoto 2021-11-28 um 11 36 26" src="https://user-images.githubusercontent.com/88385954/143764403-49a6dc91-05c2-4fa4-821f-3d0f731f54ca.png">
</details>

Der zweite Befehl wird ausgeführt, indem sich die Position der Spielfigur ändert. Während die Spielfigur zuvor noch ganz links im Rand zu sehen war muss sie in der neuen Stage ganz rechts zu sehen sein.

<details>
<summary>Sprite Spieler - "when I receive SpielerLinksAmRand" </summary>
<br>
 <img width="235" alt="Bildschirmfoto 2021-11-28 um 10 08 03" src="https://user-images.githubusercontent.com/88385954/143744713-d97f2bbc-9613-4825-af55-7078dc51d1cb.png">
</details>

Bei dem rechten Rand ist der Code ähnlich aufgebaut.
Auch hier wird zunächst geprüft in welcher Stage sich die Spielfigur befindet.
Anschließend wird:
 
 <h4> 1. Der Befehl für den Stagewechsel ausgegeben</h4>

Die angesteuerten Stages sind logischerweise die selben wie bei dem linken Rand

<details>
<summary>Sprite RandRechts - "when touching Spieler" </summary>
<br>
<img width="389" alt="Bildschirmfoto 2021-11-28 um 11 34 49" src="https://user-images.githubusercontent.com/88385954/143764349-9cea71a6-7a14-4053-9d54-c863d97eae84.png">
 <img width="172" alt="Bildschirmfoto 2021-11-28 um 11 16 40" src="https://user-images.githubusercontent.com/88385954/143763914-8a1b07ac-339d-4c6b-8cb3-783c1bffbcc9.png">
</details>

<details>
<summary>Sprite Spieler - "when I receive Level x Stage y" </summary>
<br>
 <img width="227" alt="Bildschirmfoto 2021-11-28 um 11 36 26" src="https://user-images.githubusercontent.com/88385954/143764403-49a6dc91-05c2-4fa4-821f-3d0f731f54ca.png">
</details>

 <h4> 2. Der Befehl für die neue Position der Spielfigur wird ausgegeben </h4>

<details>
<summary>Sprite Spieler - "when I receive SpielerRechtsAmRand" </summary>
<br>
 <img width="235" alt="Bildschirmfoto 2021-11-28 um 10 08 03" src="https://user-images.githubusercontent.com/88385954/143744713-d97f2bbc-9613-4825-af55-7078dc51d1cb.png">
</details>

So wird der Szenenwechsel im gesamten Projekt zuverlässig verwaltet.

<h2> 2.4 Das Startmenü </h2>

Wenn man das Spiel öffnet, so startet nicht direkt das Spiel. Der Spieler findet sich zunächst auf dem TitleScreen wieder. 
Es wird aus diesem Grund geprüft, ob der Kostümname der Stage = TitleScreen ist. Wenn dies der Fall ist, so kann der Spieler eine beliebige Taste auf der Tastatur drücken. 
Dann wird der Befehl zum Menü ausgeführt.
 
Auch der Kostümname wird entsprechend geändert, so dass das Menü nun auf dem Bildschirm angezeigt wird.
Dabei wird auch die Variable "SpielerBewegung" = 1 gesetzt.

<details>
<summary>Sprite Stage - "when Fahne clicked"</summary>
<br>
<img width="283" alt="Bildschirmfoto 2021-11-28 um 12 08 26" src="https://user-images.githubusercontent.com/88385954/143765324-75e23717-e99a-4b81-b66c-d2e7dde76d4c.png">
</details>

In diesem Menü lassen sich drei verschiedene Button clicken:


 <h2> 2.4.1 Spiel Starten </h2>

Zunächst wird der Button "SpielStartet" betrachtet.
Damit das Menü wie gewünscht funktioniert, haben wir uns folgendes überlegt.
Mit dem Programm Power-Point haben wir die verschiedenen Stages (siehe Ende Erklärung "Das Startmenü") erstellt.
Die schwärzliche Färbung von dem gewünschten Button soll nur dann erscheinen, wenn die Maus über diese Fläche fährt. Aus diesem Grund haben wir hinter die Buttons unsichtbare Flächen gelegt. Diese prüfen im Menü, ob die Maus über diese fährt. Nur wenn das der Fall ist, wird die hinterlegte Farbe schwarz, dafür wird das Kostüm der Stage enstsprechend durch den Szenenmanager geändert.
Die unsichtbare Fläche hinter den Button:

<img width="94" alt="Bildschirmfoto 2021-11-28 um 12 18 21" src="https://user-images.githubusercontent.com/88385954/143765601-30b71019-9350-4e6f-b277-a1e1f5fc952f.png">

Die hinterlegte Fläche soll nur im Menü Anwendung finden. Zudem soll aus den erläuterten Gründen der ghost-effect = 100% sein.

<details>
<summary>Sprite SpielStartenButton - "when Fahne clicked"</summary>
<br>
<img width="207" alt="Bildschirmfoto 2021-11-28 um 12 19 48" src="https://user-images.githubusercontent.com/88385954/143765644-0cadf072-7a08-4117-a2f2-c2a4ee2b7a24.png">
<img width="173" alt="Bildschirmfoto 2021-11-28 um 12 20 32" src="https://user-images.githubusercontent.com/88385954/143765665-fed39d84-eda5-41c2-b2b8-6bd2c7ea31ec.png">
 </details>
 
Nun soll erreicht werden, dass die Stage geändert wird, wenn der Spieler mit seiner Maus über die unsichtbare hinterlegte Fläche fährt.
Somit wird zunächst geprüft, ob die Maus über die hinterlegte Fläche fährt.
Wenn dies der Fall ist, wird des Weiteren geprüft, ob die aktuelle Stage = Menü ist, also die Fläche aktuell nicht schwarz hinterlegt ist.
Wenn dies der Fall ist, so wird der Befehl ausgegeben die Stage zu "MenüSpielStarten" zu ändern.
In dem zweiten Script wird, wenn die Maus nicht die unsichtbare hinterlegte Fläche berührt und die aktuelle Stage "enüSpielStarten" ist, die Fläche also schwarz hinterlegt ist, wieder der Befehl zum Wechsel der Stage zu "Menü" ausgegeben. Damit wird die hinterlegte Fläche wieder hell.

<img width="461" alt="Bildschirmfoto 2021-11-28 um 12 22 18" src="https://user-images.githubusercontent.com/88385954/143765704-be792a62-404a-4ebb-83a9-2e01e5456df9.png">

Die Befehle werden dann im Sprite (Objekt) Stage ausgeführt:
 
![MenüButtonHighlighting-_online-video-cutter com_](https://user-images.githubusercontent.com/88385813/144720525-86dd302c-d7dd-4d83-9853-dce43410ad63.gif)



<details>
<summary>Sprite Stage - "when I receive MenüSpielStartet" </summary>
<br>
<img width="230" alt="Bildschirmfoto 2021-11-28 um 12 28 35" src="https://user-images.githubusercontent.com/88385954/143765851-c056a018-4d4b-4a4b-913b-d23bc953d551.png"> 
</details>

Die Backgrounds für die Befehle:

<details>
<summary> "Sprite Stage - backgrounds" </summary>
<br>
<img width="95" alt="Bildschirmfoto 2021-11-28 um 12 30 37" src="https://user-images.githubusercontent.com/88385954/143765910-411a9b8e-64df-4e27-b5f3-86b5d40de4a7.png">
</details>

Wenn sich die Maus auf der unsichtbaren hinterlegten Fläche befindet und der Spieler anschließend mit der Maus klickt, so beginnt das Spiel.
Dann wird der Befehl "SpielStartet" ausgegeben.
Die Stage wird wie bereits beim Wechseln der Spielfigur zwischen den Stages gewechselt und die anderen Schritte zum Spielstart werden eingeleitet.

<details>
<summary>Sprite SpielStartenButton - "when I am clicked" </summary>
<br>
 <img width="310" alt="Bildschirmfoto 2021-11-28 um 12 33 14" src="https://user-images.githubusercontent.com/88385954/143765994-7720b1b0-3e4d-4bbd-b85d-71c18a34ecdc.png">
</details>
 
 ![SpielStartenKlick](https://user-images.githubusercontent.com/88385813/144720684-de5bb54d-76b8-483b-9664-66db899cd7a7.gif)




 
 
<h2> 2.4.2 Charakter Wählen </h2>
 
 https://user-images.githubusercontent.com/88385813/144719596-adcd7268-4e3b-4b53-bfeb-bcb51c721c39.mp4

Das Prinzip hinter der Charakterauswahl ist ähnlich. Durch eine hinterlegte Fläche wird ebenfalls zunächst geprüft, ob die Maus sich auf dem Button befindet. Durch das gleiche Prinzip wie bei "Spiel Starten" werden die Stages entsprechend angepasst.
Zudem ist der hinterlegte Button unsichtbar und findet nur im Menü Anwendung.

Code im Sprite Charakter Wählen:

<details>
<summary>Sprite Charakter Wählen - "when tocuhing mous-pointer"</summary>
<br>
<img width="201" alt="Bildschirmfoto 2021-11-28 um 12 56 39" src="https://user-images.githubusercontent.com/88385954/143766645-4d2fb7a9-e2e7-41d8-a632-c5d95f2ab47d.png">
<img width="464" alt="Bildschirmfoto 2021-11-28 um 12 57 04" src="https://user-images.githubusercontent.com/88385954/143766660-cd92ca84-5ea4-4ad4-bc6f-f8fb681366f9.png">
</details>

Entsprechende Ausführungen im Objekt Stage:

<details>
<summary>Sprite Stage - "when I receive MenüCharakterWählen" </summary>
<br>
<img width="251" alt="Bildschirmfoto 2021-11-28 um 12 59 12" src="https://user-images.githubusercontent.com/88385954/143766721-9b593808-459f-4957-8b1c-79140316b503.png">
<img width="90" alt="Bildschirmfoto 2021-11-28 um 13 00 13" src="https://user-images.githubusercontent.com/88385954/143766752-ac13bc80-7677-4257-9d32-014644ad4b60.png">
</details>

Wenn man sich auf dem Button "Charakter Wählen" befindet und dann ein Mausklick erfolgt, wird der Befehl "BlauerAbenteurer" ausgeführt.
Hier besteht der Unterschied zum Button "Spiel Starten". Während bei "Spiel Starten" das Spiel startet, wird man, wenn man Charakter wählen anklickt, in das Wahlmenü für die Spielfiguren geleitet.

<details>
<summary>Sprite CharakterWählen - "when I am clicked"</summary>
<br>
<img width="338" alt="Bildschirmfoto 2021-12-06 um 13 09 47" src="https://user-images.githubusercontent.com/88385954/144843687-d179038c-27e4-4393-918c-1bd2de8e3889.png">
 <img width="223" alt="Bildschirmfoto 2021-12-06 um 13 39 17" src="https://user-images.githubusercontent.com/88385954/144847538-6ce0da3b-5694-40e1-b515-54a13d4c37bb.png">
<img width="88" alt="Bildschirmfoto 2021-12-06 um 13 39 35" src="https://user-images.githubusercontent.com/88385954/144847570-a313a6a4-8009-4e95-ad39-80d23d29a078.png">
</details>


Dann wird die Stage angepasst, indem "Blauer Abenteurer" ausgeführt wird. Auf dem Bild sind alle drei möglichen Spielfiguren nebeneinander zu sehen.
Der Spieler hat die Möglichkeit je nach belieben eine Spielfigur auszuwählen. 
Zu Beginn ist standartmäßig die blaue Figur ausgewählt.

Nun besteht die Möglichkeit mit den Pfeiltasten die verschiedenen Charaktere auszuwählen.
Die Folgenden Codes beschreiben dieses Bedienen mit den Pfeiltasten.
Die Codes laufen dabei alle nach dem selben Prinzip.
Wenn der rechte Pfeil gedrückt wird, so wird der aktuelle Kostümname geprüft.
Zu Beginn ist die Stage logischerweise auf "CharakterWählen" eingestellt.
Wenn nun der rechte Pfeil gedrückt wird, so wird erkannt das die ausgewählte Stage "CharakterWählen" oder "CharakterWählenZurück" ist. Diese beiden Stages unterscheiden sich lediglich dadurch, dass bei "CharakterWählenZurück" der kleine Pfeil unten links rot hervorgehoben ist, indem die Maus über diesen fährt. Dies funktioniert wie zuvor bei dem schwarzen Markieren des "SpielStarten" Buttons. 
Aus diesem Grund müssen bei allen Codes für die Charakterauswahl mit Pfeiltasten zwei Stages geprüft werden.
Dann wird der "RoteAbenteurer" ausgeführt. Die rote Spielfigur befindet sich im Charakterwahlmenü rechts neben dem blauen Abenteurer.


<details>
<summary>Sprite Stage - "right arrow clicked" </summary>
<br>
<img width="363" alt="Bildschirmfoto 2021-12-06 um 13 20 11" src="https://user-images.githubusercontent.com/88385954/144844996-d15cc04b-f508-4161-a497-a138f8efeeea.png">
<img width="201" alt="Bildschirmfoto 2021-12-06 um 13 24 05" src="https://user-images.githubusercontent.com/88385954/144845515-f633c4c4-d5e9-4cbd-b3c5-67bad313a0a2.png">
 </details>
 
 Nach diesem Prinzip kann man durch die folgenden Scripts alle drei Charaktere beliebig mit der rechten und mit der linken Pfeiltaste ansteuern.
 
<details>
<summary>Sprite Stage - Charakterauswahl mit Pfeiltasten </summary>
<br>
<img width="622" alt="Bildschirmfoto 2021-12-06 um 13 29 47" src="https://user-images.githubusercontent.com/88385954/144846340-d4713c53-168b-4092-8ba3-fb8d1d4e671b.png">
 </details>
 
 Die entsprechenden Stages dazu:
 
<img width="90" alt="Bildschirmfoto 2021-12-06 um 13 31 02" src="https://user-images.githubusercontent.com/88385954/144846485-cbdd8ec0-4567-47ee-8856-3f47b2c3ffaf.png">
 
 Der angesprochene kleine rote Pfeil unten links ist nötig, damit der Spieler jederzeit wieder ins Homemenü zurückkommen kann. Auch dieser Pfeil ist durch eine unsichtbare Fläche hinterlegt. 
Zudem sind die Funktionen des kleine Pfeils nur im "Charakterwahlmenü" aktiv.

<details>
<summary>Sprite CharakterZurückButton - "when Fahne clicked" </summary>
<br>
 <img width="205" alt="Bildschirmfoto 2021-12-06 um 13 50 36" src="https://user-images.githubusercontent.com/88385954/144849035-27c8ed9e-b301-4e4f-91eb-a9322aa0efe3.png">
</details>

Wenn sich der Spieler also im Charakterwahlmenü befindet, wird zunächst geprüft, ob sich die Maus auf dem Pfeil befindet.
Es gibt für jeden der drei Charaktere die Möglichkeit, dass er ausgewählt ist ohne das die Maus die Pfeiltaste berührt und es gibt die Möglichkeit, dass er ausgewählt ist während die Pfeiltaste betätigt wird. Aus diesem Grund werden auch im Stage Menü immer zwei mögliche Stages geprüft, wenn die Charaktere mit den Pfeiltasten geändert werden sollen.
 
 <details>
<summary>Sprite CharakterZurückButton - "when touching mouse-pointer" </summary>
<br>
  <img width="485" alt="Bildschirmfoto 2021-12-06 um 14 58 04" src="https://user-images.githubusercontent.com/88385954/144858785-e7632e8a-fae9-4868-95ef-c7df0d8da642.png">
</details>
 
 Wenn der Pfeil geklickt wird und die Stage eine der entsprechenden Stages ist, bei der die Maus den PFeil berührt, wird der Spieler zurück zum Startmenü geleitet.

 <details>
<summary>Sprite CharakterZurückButton - "when touching mouse-pointer" </summary>
<br>
  <img width="394" alt="Bildschirmfoto 2021-12-06 um 14 59 29" src="https://user-images.githubusercontent.com/88385954/144859017-aea1c1e7-076e-42ea-b929-d9007abf1779.png">
</details>
 
 
<h3> 2.4.3 Charakterwahl mit Mausklick </h3>
 
 Zudem besteht die Möglichkeit, den Charakter per Maus auszuwählen. Auch hier ist hinter den Spielfiguren eine unsichtbare Fläche hinterlegt, welche das Klicken wahrnehmen kann. Diese Fläche ist genau dann aktiv, wenn das Charaktermenü geöffnet wird. 

 <details>
<summary>Sprite Charakter1Auswahl - "when I receive BlauerAbenteurer" </summary>
<br>
  <img width="211" alt="Bildschirmfoto 2021-12-06 um 15 07 24" src="https://user-images.githubusercontent.com/88385954/144860266-85b11e02-0d57-4b46-b7de-fd225c8f9de6.png">
</details>

 Ist bereits ein anderer Charakter ausgewählt und die hinterlegte Fläche wird geklickt, dann ändert sich die ausgewählte Spielfigur.
 
 <details>
<summary>Sprite Charakter1Auswahl - "when I am clicked"</summary>
<br>
  <img width="355" alt="Bildschirmfoto 2021-12-06 um 15 07 55" src="https://user-images.githubusercontent.com/88385954/144860344-5c14de68-407f-4a55-b55e-184aee9f0e17.png">
</details>

 Diese Scripts gibt es logischerweise auch für den Charakter 2 und den Charakter 3.
 
 <details>
<summary>Sprite Charakter 2</summary>
<br>
  <img width="324" alt="Bildschirmfoto 2021-12-06 um 15 11 22" src="https://user-images.githubusercontent.com/88385954/144860969-059f5313-09e2-4b01-9a7d-dad87999b9f4.png">
  </details>

  <details>
<summary>Sprite Charakter 2</summary>
<br>
  <img width="343" alt="Bildschirmfoto 2021-12-06 um 15 11 53" src="https://user-images.githubusercontent.com/88385954/144861058-d4525674-bcad-44ea-87a7-c2a69017af1f.png">
   </details>
 

 <h2> 2.4.3 Anleitung </h2>

Auch die Anleitung funktioniert nach dem bereits erläuterten Prinzip.
Der hinterlegte Button für die Anleitung ist nur während des aktiven Menüs zu sehen.

<details>
<summary>Sprite Anleitung - "when I receive Menü" </summary>
<br>
 <img width="391" alt="Bildschirmfoto 2021-12-06 um 19 37 48" src="https://user-images.githubusercontent.com/88385954/144902889-90f51e80-8796-4495-b06f-6ea095d08fe5.png">
</details>

 Anschließend wird geprüft, ob sich die Maus auf dem Button befindet. Ist dies der Fall, so wird das Kostüm entsprechend angepasst. Wird der Button betätigt, so öffnet sich der Menü-Unterpunkt: Anleitung.

<details>
<summary>Sprite Anleitung - "when touching mouse-pointer" </summary>
<br>
 <img width="461" alt="Bildschirmfoto 2021-12-06 um 19 40 41" src="https://user-images.githubusercontent.com/88385954/144903229-4e6f914d-015a-4c2a-b065-45e676154ea2.png">
</details>
 
 In dem Anleitungsmenü gibt es zwei verschiedene Folien mit jeweils zwei Pfeilen links und rechts unten.
Mit den Pfeiltasten kann nach dem gewohnten Prinzip der Charakterauswahl die Folie gewechselt werden. 

<details>
<summary>Sprite Stage - "when left arrow key pressed" </summary>
<br>
 <img width="377" alt="Bildschirmfoto 2021-12-06 um 19 44 27" src="https://user-images.githubusercontent.com/88385954/144903770-a2838148-a5d4-4d09-beb7-3d716681fb41.png">
<img width="255" alt="Bildschirmfoto 2021-12-06 um 19 46 12" src="https://user-images.githubusercontent.com/88385954/144903976-58d509c0-4949-4167-8570-096c70214b74.png">
</details>

Auch die kleinen Pfeile und das rote Färben dieser, wenn man mit der Maus darüber fährt funktioniert wie bei der Charakterauswahl.
Somit müssen auch immer drei Dinge im Stage-Menü geprüft werden, damit das Anleitungsmenü mit den Pfeiltasten funktioniert.
 
Die Pfeile werden ebenfalls nach dem bekannten Prinzip angesteuert. Es wird geprüft, was die Maus berührt. Wenn ein gewisses Objekt ausgewählt ist wird anschließend das Objekt entsprechend angepasst und einer der Pfeile erscheint rot oder wieder weiß.
Der einzige Unterschied zum Charakterwahlmenü ist, dass bei dem Anleitungsmenü über die Pfeile die Folie gewechselt wird.
Aus diesem Grund gibt es einen Pfeil, der zurück auf das vorherige Bild führt und einen anderen Pfeil rechts, der auf das nächste Bild führt.
Es wird somit immer geprüft, ob sich die Maus auf dem Pfeil befindet oder ob ein Pfeil geklickt wird.
Entsprechend wird dann das neue Kostüm ausgeführt.
Der Code für den linken Pfeil:

<details>
<summary>Sprite Anleitung Zurück Button- "when touching mouse-pointer"</summary>
<br>
 <img width="176" alt="Bildschirmfoto 2021-12-06 um 20 05 04" src="https://user-images.githubusercontent.com/88385954/144906531-39ba3fa8-d105-4f28-b892-ab4bfeeb2fdf.png">
<img width="489" alt="Bildschirmfoto 2021-12-06 um 19 49 12" src="https://user-images.githubusercontent.com/88385954/144904390-548425d2-1499-4df4-837d-57423efd4e1a.png">
</details>

 Der Code für den rechten Pfeil:

<details>
<summary>Sprite </summary>
<br>
 <img width="325" alt="Bildschirmfoto 2021-12-06 um 20 06 21" src="https://user-images.githubusercontent.com/88385954/144906676-715439fb-feed-491b-a62f-c61a932446cc.png">
<img width="488" alt="Bildschirmfoto 2021-12-06 um 20 06 34" src="https://user-images.githubusercontent.com/88385954/144906712-d0ae292b-1181-4301-86f9-37f85b885ea6.png">
 </details>




 <h1>2.5 Das Rätsel des geschlossenen Tores </h1>

Ein wichtiges Element unseres Spiels ist das verschlossene Tor, welches geöffnet werden muss, um dass Level abzuschließen. Dafür muss zunächst ein Schlüssel eingesammelt werden. 
Der Schlüssel kann eingesammlet werden, sobald der Spieler ihn berührt und sich auf der Stage befindet, auf der der Schlüssel angezeigt wird. Auch hier funktioniert das korrekte 
Anzeigen über den Szenenmanager und das Verstecken des Objekts beim Wechseln zu anderen Stages.
 
<details>
<summary>Schlüssel Objekt - show und hide</summary>
<br>
<img src="https://user-images.githubusercontent.com/88385813/144973151-bbcc02ca-2db6-4340-b86b-18880ab21b7e.png" alt="https://user-images.githubusercontent.com/88385813/144934520-9b899b5e-2048-46d2-8dbc-a95376cec713.png">
</details>
 
Sobald der Spieler nun also den Schlüssel berührt und sich auf der richtigen Stage befindet erscheint die "SchlüsselNachricht" welche den Spieler auffordert "F" zu drücken, um den Schlüssel einzusammlen. Drückt der Spieler nun "F" so verschwindet der Schlüssel durch das Wechseln des Kostüms zu einem leeren Kostüm. Dies stellt auch sicher, dass der Schlüssel beim erneuten betreten der Stage nicht wieder erschient, da das Kostüm nicht mehr "Schlüssel" heißt.
 
Außerdem wird die Variable "SchlüsselImInventar" auf 1 gestzet, damit im folgendem das Tor, sowie die Schlüssel-Anzeige über den erhalt des Schlüssels informiert werden.
 
<details>
<summary>Schlüssel Objekt - Einsammeln des Schlüssels</summary>
<br>
<img src="https://user-images.githubusercontent.com/88385813/144973233-2e5fe206-6d17-4b34-ac13-faed41a6c81a.png" alt="https://user-images.githubusercontent.com/88385813/144934520-9b899b5e-2048-46d2-8dbc-a95376cec713.png">
</details>
 
Die Schlüssel-Anzeige ändert lediglich das Kostüm von einer 0 auf eine 1, ween sie die Nachricht "SchlüsselErhalten" erhält.
 
<details>
 <summary>SchlüsselZähler Objekt - Anzeige der Schlüssel Anzahl</summary>
<br>
<img src="https://user-images.githubusercontent.com/88385813/144974641-985d8734-47f6-40c4-a665-a2d4d045aa91.png" alt="https://user-images.githubusercontent.com/88385813/144934520-9b899b5e-2048-46d2-8dbc-a95376cec713.png">
</details>
 
Etwas komplizierter wird es beim Tor selbst. Der Spieler soll nicht am Tor vorbeikommen, solange er selbiges nicht geöffnet hat. Dafür sorgt das Tor-Script.
 
<details>
<summary>Tor Objekt - Tor öffnen und Blockade</summary>
<br>
<img src="https://user-images.githubusercontent.com/88385813/144974848-a674cf36-f10e-4f90-9dab-cc0af354c6a6.png" alt="https://user-images.githubusercontent.com/88385813/144934520-9b899b5e-2048-46d2-8dbc-a95376cec713.png">
</details>
 
Normalerweise hat das Tor das Kostüm "Tor" solange der Spieler das Tor nicht berührt. Der Spieler darf sich hier frei bewegen, er wird ja nicht vom Tor blockiert. Berührt er das Tor, so wird nun das Kostüm "TorGeschlossen" aktiviert. Im Spielerobjekt ist an die Bewegung nach rechts nun das Kostüm des Tors "Tor" oder "TorOffen" gekoppelt, der Spieler kann sich also nicht mehr bewegen, wenn er an das Tor stößt und dieses geschlossen ist.
 <details>
<summary>Spieler Objekt - Tor Blockade</summary>
<br>
<img src="https://user-images.githubusercontent.com/88385813/144975314-6543276c-f7e4-40e4-bdd6-4cc821fc8c14.png" alt="https://user-images.githubusercontent.com/88385813/144934520-9b899b5e-2048-46d2-8dbc-a95376cec713.png">
</details>

Bei Berührung mit dem Tor erscheint nach dem selben Prinzip wie beim Schlüssel eine Nachricht, dass der Spieler einen Schlüssel benötigt.
Hat der Spieler nun den Schlüssel zuvor eingesammelt und die zugehörige Variable hat den passenden Wert, wird diese Nachricht geändert, der Spieler soll nun "F" drücken, um das Tor zu öfnnen. Hat der Spieler den Schlüssel und drückt nun "F", so wird folgende Funktion gestartet.

![image](https://user-images.githubusercontent.com/88385813/144976001-4fe91437-c806-4b83-8078-f47b2d4161b9.png)

 Das Tor öffnet sich schrittweise und sobald die Animation abgeschlossen ist hat das Tor das Kostüm "TorOffen" und der Spieler kann passieren.
 
 
<h1>2.6 Der Hintergrund </h1>
 
Damit das Spiel für den Spieler ansprechend aussieht, haben wir einen Hintergrund kreiert, welcher nicht nur still dasteht, sondern teilweise auch beweglich ist.
Die Wolken bewegen sich dabei im Hintergrund.
Die erste Wolke soll immer dann zu sehen sein, wenn das Spiel gestartet wird. Sonst ist sie nicht sichtbar. 
Wenn das Spiel gestartet wird, dann wird zunächst die Größe und die Position wie gewohnt festgelegt. Die Wolke befindet sich dabei im Hintergrund.
Zudem soll die Wolke jedoch beweglich sein. Dies wird durch die Funktion "forever" erreicht.
Die Wolke bewegt sich dabei nur in X-Richtung.

<details>
<summary>Sprite Wolke</summary>
<br>
 <img width="228" alt="Bildschirmfoto 2021-12-06 um 20 39 52" src="https://user-images.githubusercontent.com/88385954/144911228-b295e8b0-e12e-4733-8d24-47704aaa5e9b.png">
</details>

Die zweite und die dritte Wolke funktioniert nach dem gleichen Prinzip. Der Unterschied liegt in der Geschwindigkeit der Wolkenbewegung und in der generellen Position im Hintergrund.

 <details>
<summary>Sprite Wolke 2</summary>
<br>
  <img width="253" alt="Bildschirmfoto 2021-12-06 um 20 41 46" src="https://user-images.githubusercontent.com/88385954/144911488-a3d61558-d651-4150-8dcb-acbd1c6ca7aa.png">
</details>

 <details>
<summary>Sprite Wolke 3</summary>
<br>
  <img width="357" alt="Bildschirmfoto 2021-12-06 um 20 42 20" src="https://user-images.githubusercontent.com/88385954/144911565-d212c750-c32e-4ced-b8ff-5743ba3bd867.png">
</details>

Im Hintergrund verändern sich zudem die Bilder der Steine.
Es gibt in unserem Spiel drei Steine.
Der erste, kleine Stein befindet sich in der Stage 1.
Er ist folglich nur sichtbar, wenn sich die Spielfigur auf dieser Stage befindet.
Die Größe ist dabei 100%.
Die Steinanimationsvariable ist dann = 1.  
Die Animation ist darunter erklärt und wird so lange durchgeführt, bis die Variable 0 ist.
Die Animation beinhaltet, dass das Kostüm nach 2 Sekunden und nach 2,5 Sekunden geändert wird.
Dadurch sieht es so aus, als ob sich das Gras bewegen würde, es gibt aber bei drei verschiedenen Kostümen keinen sofort für den Spieler erkennbaren Rhythmus. Die Bewegung soll somit willkürlich erscheinen.

 <details>
<summary>Sprite SteinKlein </summary>
<br>
  <img width="462" alt="Bildschirmfoto 2021-12-06 um 21 07 24" src="https://user-images.githubusercontent.com/88385954/144914865-cdd90ad0-af73-4830-b099-3def9521b0a1.png">
</details>

Die beiden anderen Steine unterscheiden sich von diesem nur durch die Größe und durch kleine Unterschiede. 

 <details>
<summary>Sprite SteinRund</summary>
<br>
<img width="535" alt="Bildschirmfoto 2021-12-06 um 21 09 01" src="https://user-images.githubusercontent.com/88385954/144915053-f203b217-7fd9-4ff0-ab14-622dd81d0a73.png">
</details>

 <details>
<summary>Sprite SteinGroß</summary>
<br>
<img width="514" alt="Bildschirmfoto 2021-12-06 um 21 09 59" src="https://user-images.githubusercontent.com/88385954/144915185-2750c18f-0ad1-4dc0-bc0e-1acba09e0ca4.png">
</details>

Damit Performance verbessert wird, soll die Animation nicht durchgängig laufen.
Damit dies nicht der Fall ist, darf die Variable nicht durchgängig = 1 sein. 
Aus diesem Grund wird in dem Sprite der Stages die Variable für die jeweiligen Steine = 0 gesetzt, wenn die entsprechende Stage verlassen wurde.

<details>
<summary>Sprite </summary>
<br>
<img width="491" alt="Bildschirmfoto 2021-12-06 um 21 12 59" src="https://user-images.githubusercontent.com/88385954/144915576-db67608e-34b3-4289-934c-12899b55f1b2.png">
</details>

 
<h1>2.7 Die Zeit </h1>
 
 <h2>2.7.1 Ziffer 1 </h2>
In dem Spiel stellt eine entscheidende Schwierigkeit die Zeit da. Der Spieler muss das Spiel beenden, bevor diese abgelaufen ist.
Die Zeit besteht aus drei Ziffern.
Bei der ersten Stelle ist der Code einfach, da sich die Zahl 0 nicht verändert.
Diese Ziffer wird gezeigt, sobald das Spiel gestartet wird. Dabei wird die Größe entsprechend des Codes angepasst. Sobald die Zeit abgelaufen ist, wird die Zeit, das Spiel gewonnen wurde oder das Spiel verloren wurde, wird die Zahl wieder versteckt.

<details>
<summary>Sprite Ziffer 1</summary>
<br>
<img width="412" alt="Bildschirmfoto 2021-12-06 um 21 22 10" src="https://user-images.githubusercontent.com/88385954/144916712-81713010-b2f5-4c46-97ae-c275a207a4b9.png">
</details>

 <h2>2.7.2 Ziffer 3 </h2>
 
Die dritte Ziffer muss jede Sekunde wechseln, da sie die Einzelziffern anzeigt.
Zu Beginn des Spiels sind die Einstellungen genau wie bei der Ziffer 1.

<details>
<summary>Sprite Ziffer 3 - "wehen I receive SpielStarted"</summary>
<br>
<img width="188" alt="Bildschirmfoto 2021-12-06 um 21 24 03" src="https://user-images.githubusercontent.com/88385954/144916969-5704c03f-94ad-486f-b265-5878f8ed2eb8.png">
</details>

 Sobald das Spiel gestartet ist, wird das Kostüm 0 eingestellt. Nach 0,8 Sekunden wird "60Sekunden" ausgeführt. Sobald wiederum "60Sekunden" gebroadcastet wird, ändert sich auch das Kostüm der dritten Ziffer. Anschließend wird die Zahl immer nach einer Sekunde um 1 nach unten versetzt.
Ist die Ziffer 0 erreicht, wird nach 0,8 Sekunden "50Sekunden" ausgeführt. Somit verändert sich die Zahl immer wieder von 9 bis 0, insgesamt 60 Sekunden lang , also sechs mal.
Bei dem Wechsel von der Ziffer 0 zu der Ziffer 9 ist die Zeit immer nur 0,8 Sekunden, weil 0,2 Sekunden benönigt werden, dass alle Codes ausgeführt werden, auch die der Ziffer 2.

<details>
<summary>Sprite Timer 3. Stelle</summary>
<br>
  <img width="207" alt="Bildschirmfoto 2021-12-06 um 21 29 50" src="https://user-images.githubusercontent.com/88385954/144917800-c67a1e38-7bfe-4c8b-86f5-2b9184d9323e.png">
 <img width="195" alt="Bildschirmfoto 2021-12-06 um 21 30 21" src="https://user-images.githubusercontent.com/88385954/144917856-58d399f4-5619-4b60-b375-77a3abde7af1.png">
<img width="196" alt="Bildschirmfoto 2021-12-06 um 21 30 33" src="https://user-images.githubusercontent.com/88385954/144917882-997f5c27-0c2b-4aea-9eb2-8b7197f61b26.png">
</details>
 
Eine Besonderheit stellen die letzten drei Codeblocks da. Hier wird nachdem die Ziffer 0 erreicht ist nicht nur die erreichte neue Nummer ausgeführt, sondern es gibt eine Warnung an den Spieler, dass die Zeit fast abgelaufen ist.
Nach dem letzten Codeblock wird zudem "GameOver" ausgeführt.
 
<details>
<summary>Sprite Timer 3. Stelle</summary>
<br>
<img width="204" alt="Bildschirmfoto 2021-12-06 um 21 32 56" src="https://user-images.githubusercontent.com/88385954/144918191-6765f091-4beb-489e-818d-4bfad3f9161b.png">
<img width="206" alt="Bildschirmfoto 2021-12-06 um 21 33 12" src="https://user-images.githubusercontent.com/88385954/144918231-6c4953a8-6bcf-4b07-a4e9-bf572982d092.png">
<img width="208" alt="Bildschirmfoto 2021-12-06 um 21 33 21" src="https://user-images.githubusercontent.com/88385954/144918253-893cae31-2174-4bcb-a4ab-a0bdc0a84f4c.png">
</details>

 Die Warnung an den Spieler funktioniert wie folgt.
 Das Kostüm für diese Warnung ist ein roter Farbverlauf.
Sobald die Fahne geklickt wird, wird die "ZeitWarnungTransparenz"-Variable = 100 gesetzt.
 Zudem wird der ghost-effect = 100 gesetzt. Da die Warnung über den ganzen Bildschirm erscheinen soll, sind keine X- oder Y-Koordinaten angegeben.

<details>
<summary>Sprite ZeitläuftabWarnung</summary>
<br>
 <img width="212" alt="Bildschirmfoto 2021-12-06 um 21 37 27" src="https://user-images.githubusercontent.com/88385954/144918743-99603c4c-b674-42c9-9f71-ab75f8fbdd25.png">
</details>

Warnung 10 Sekunden vor Schluss:

 <details>
<summary>Spirte ZeitläuftabWarnung - "when I receive 10 Sekunden Warnung" </summary>
<br>
<img width="302" alt="Bildschirmfoto 2021-12-06 um 21 41 16" src="https://user-images.githubusercontent.com/88385954/144919263-3579bb4a-412c-49b9-8ca0-b79ed2b75102.png">

</details>


Warnung 20 Sekunden vor Schluss:
 
  <details>
<summary>Sprite ZeitläuftabWarnung - "when I receive 20 Sekunden Warnung" </summary>
<br>
<img width="305" alt="Bildschirmfoto 2021-12-06 um 21 41 37" src="https://user-images.githubusercontent.com/88385954/144919302-4f4a8ab8-fff2-469f-a2cc-84ad568f67ab.png">
</details>
Dieses Script wird durch den Timer bei verbleib von 10 oder 20 Sekunden durch die "broadcast" Funktion aktiviert.
Wenn nur noch 20 oder 10 Sekunden der Zeit verbleiben, so wird über die "ghost-effect" Funktion ein roter Impuls im Bild eingeblendet. Dieser funktioniert über das Verändern der Transparenz des "ZeitLäuftAb" Objekts. Zunächst wird die Transparenz, also der Wert des "ghost-effects", auch in einer Variable gespeichert, damit wir später die Transparenz des Objekts jederzeit per Code überüfen können. Dann werden Transparenz und Variable gleichmäßig verändert, bis die maximale Sichtbarkeit bei einem "ghost-effect" von 80 erreicht ist. Bei diesem "ghost-effect" ist noch deutlich das eigentliche Spiel zu sehen, der Spieler bekommt aber klar das Ablaufend der Zeit mit. Nun wartet das Script eine zehntel Sekunde und macht das Objekt langsam wieder vollkommen transparent. die Variable und der "ghost-effect" werden nun wieder auf ihre Anfangswerte gesetzt. Ein neuer Zyklus kann beginnen. 
 
Die 10 Sekunden Warnung funktioniert identisch, nur das die Transparenz des Objektes geringer, der Impuls also intensiver ist.

<h2>2.7.3 Ziffer 2 </h2>
 
Für die 2. Ziffer sind die Grundeinstellungen die selben, wie für die anderen beiden Ziffern.

<details>
<summary>Sprite Ziffer 2 </summary>
<br>
 <img width="191" alt="Bildschirmfoto 2021-12-06 um 21 45 06" src="https://user-images.githubusercontent.com/88385954/144919772-30ed21f6-9c0b-43d4-95ca-3e95965a59bf.png">
</details>
 
Die Ziffer 2 muss alle 10 Sekunden das Kostüm ändern. Sie reagiert auf die Befehle der Ziffer 3. Somit wird bei jedem neuen Befehl, als z.B. "50Sekunden" oder "40Sekunden" das Kostüm der Ziffer 2 geändert.
Somit können die Ziffern hier alle 10 Sekunden und zeitgleich mit der Ziffer 3 geändert werden.

<h1>2.8 Das Loch </h1>
 
Berührt der Spieler das Objekt Loch, welches über den Szenenmanager sichtbar gemacht wird, so fällt er in dieses Loch, da er mit der "gesprungen" Funktion im Spielerobjekt nach unten beschleunigt wird. Dies funktioniert allerdings nur, wenn er die "BodenHitbox" nicht berührt. Dieses Objekt ist notwendig, da der Spieler sonst über das Loch hinweg gehen könnte ohne zu fallen, da die Gravitation normalerweise nur nach einem Sprrung aktiviert wird. Hier wird sie also auch aktiviert, wenn der Spieler nur das Loch, aber nicht die "BodenHitbox" berührt, also eigentlich über dem Loch schwebt.

  <details>
<summary>Sprite Loch - Scripts </summary>
<br>
<img src="https://user-images.githubusercontent.com/88385813/144932896-06939209-cb89-4dc2-9198-b5a29f1d109a.png" alt="https://user-images.githubusercontent.com/88385813/144932896-06939209-cb89-4dc2-9198-b5a29f1d109a.png">
</details>

<h1>2.9 Ziel/Game Over </h1>
 
Das Spiel kann entweder verloren oder gewonnen werden. Läuft die Zeit aus oder der Spieler verliert alle seine 3 Leben, so wird "GameOver" gebroadcastet. Damit wird im Stage Objekt der Game Over Screen aktiviert, die dazugehörige Musik abgespielt und das Menü ist mittels eines Knopfes auf dem Game Over Screen zu erreichen, das Spiel kann nun erneut gestartet werden. Die Hintergründe hierfür wurden schon in der Stagewechsel Erklärung hinreichend erläutert. 
 
Neu ist allerdings der Victory Screen, welcher selbst wie der Game Over Screen funktioniert, aber nach dem Berühren der Zielfahne eine Art Animation auslöst.
 
  <details>
 <summary>Sprite Zielfahne - Animation nach Berührung</summary>
<br>
<img src="https://user-images.githubusercontent.com/88385813/144933874-720581e3-b5c1-4450-8359-6d1a8c553e2a.png" alt="https://user-images.githubusercontent.com/88385813/144933874-720581e3-b5c1-4450-8359-6d1a8c553e2a.png">
</details>


Nach der Berührung wird zunächst die Animation der Fahne abgespielt und die GameWonMusik gestartet. Dann startet ein Fade to Black, welcher nach dem selben Prinzip der 10 und 20 Sekunden Warnung im Zusammnenhang mit dem Timer funktioniert:
 
 <details>
 <summary>Sprite Zielfahne - Fado To Black</summary>
<br>
<img src="https://user-images.githubusercontent.com/88385813/144934198-c635efed-a96a-445a-9a5c-4325c68c1fec.png" alt="https://user-images.githubusercontent.com/88385813/144934198-c635efed-a96a-445a-9a5c-4325c68c1fec.png">
</details>
 

Nun wird der Spieler mit der Nachricht "SpielerAusBildschirm" aus dem Bildschirm bewegt. Dafür wird folgendes Script im Spielerobjekt aktiviert:
 
 <details>
<summary>Sprite Spieler - Bewegung aus dem Bildschirm</summary>
<br>
<img src="https://user-images.githubusercontent.com/88385813/144934520-9b899b5e-2048-46d2-8dbc-a95376cec713.png" alt="https://user-images.githubusercontent.com/88385813/144934520-9b899b5e-2048-46d2-8dbc-a95376cec713.png">
</details>


 Erst jetzt wird der Victory Screen angezeigt, bei dem auch wieder per Klick auf den Button ins Menü zurückgekehrt werden kann.
 
 
<h1>2.10 Musik </h1>
Auch das Abspielen der Musik ist an das Wechseln der Stages gekoppelt. Alle Musikdateien befinden sich im Stageobjekt:
 
 <details>
<summary>Stageobjekt - Musik</summary>
<br>
<img src="https://user-images.githubusercontent.com/88385813/144927845-a9b7487a-9df3-4286-94d7-28b8a9238565.png" alt="https://user-images.githubusercontent.com/88385813/144927845-a9b7487a-9df3-4286-94d7-28b8a9238565.png">
</details>
 

Die Titelmusik wird abgespielt, sobald das Spiel per Klick auf die Fahne gestartet wird und außerdem nach einem GameOver oder Sieg, sobald das Menü wieder geöffnet wird oder die Victory-Musik fertig abgespeilt ist. Dies wird mit den "Broadcast" Funktionen des Szenenmanagers gesteuert: 
 
 <details>
<summary>Stageobjekt - Musik-Loop</summary>
<br>
<img src="https://user-images.githubusercontent.com/88385813/144928328-71d0c629-ae36-4b31-9577-992c42ce7814.png" alt="https://user-images.githubusercontent.com/88385813/144928328-71d0c629-ae36-4b31-9577-992c42ce7814.png">
<img src="https://user-images.githubusercontent.com/88385813/144928346-170f2563-4d7c-4430-9fc0-0d250fd34a4f.png" alt="https://user-images.githubusercontent.com/88385813/144928346-170f2563-4d7c-4430-9fc0-0d250fd34a4f.png">
</details>

Wird "Titelmusik" gebroadcastet, so startet das Abspielen der Musik und die Variable der derzeitigen Musik wird demenstprechend geändert. Da es sich bei dem Stück um einen Loop handelt wird nach Ablauf der Zeit mithilfe der "wait" Funktion die Musik erneut gesartet, sollte die Stage noch nicht gewechselt sein. Dieser Loop funktioniert nur, solange die Variable den Wert 0 hat. Der Wert der Variable wird geändert, sobald ein anderes Stück gespielt wird. 
 
Auch die anderen Stücke werden nach diesem Prinzip abgespielt, haben jedoch aber keine Loops, da sie zeitlich begrenzt sind und nicht länger abgespielt werden müssen.

 
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

  
  




