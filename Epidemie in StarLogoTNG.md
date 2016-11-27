# Epidemie-Projekt

##Gliederung

[StarLogoTNG](#Einführung)  
[1. Homogene Epidemie](#1)  
[2. Infektionsherd](#2)  
[3. Ansteckung](#3)  
[4. Immunität](#4)  
[5. Gesundheitszustand](#5) 

##StarLogoTNG<a name="Einführung"></a> 

StarLogoTNG ist ein Simulationsprogramm für die Blockprogrammiersprache.     
Es ist übersichtlich aufgebaut und besteht aus zwei Feldern, dem Programmierfeld und dem Spaceland, wo man die Aktionen und Fortschritte der Agenten verfolgen kann.     
     
Die Agenten können mehrere Formen annehmen und so individuell eingestellt werden.      
Auch die Umgebung kann durch Gebäude, Pflanzen und andere Gegenstände ergänzt werden.      
Durch das Zusammensetzen verschiedener Böcke, die in Ordnern am Rande des Programmierfeldes untergebracht sind, kann man die Agenten zu verschiedenen Handlungen bewegen.     
Diese Blöcke, welche man bei StarLogoTNG als "Variablen" bezeichnet, sind nach Verwendungszweck sortiert, zum Beispiel findet man Variablen für Gleichungssysteme im Ordner "math", der Ordner für Farben nennt sich "colors" etc.     

Dadurch hat man also diverse Möglichkeiten, dem Spiel eine bestimmte Richtung zu geben.

Man kann also wie in unserem folgenden Projekt Epedemien mit Infektionsherden, Ansteckungen, Immunität und Gesundheitszuständen entstehen zu lassen, den Agenten bestimmte Aufgaben zu geben, wie etwa einen Baum in der Umgebung hochzuklettern, oder Unterhaltungen zwischen Agenten bei einer Kollision zu starten.   
 
Zur vielfältigeren Gestaltung kann man die "Agenten" mischen und verschiedene Tiere und Farben einsetzen sowie im Spaceland die Sicht des Agenten und des Betrachters ein- und verstellen.    
Ebenfalls im Spaceland kann man bei Betätigung des "forever"- Buttons die aktuellen Änderungen sichern und die "Agenten" beliebig agieren lassen sowie die vorher im Programmierfeld eingestellten Aktionen beobachten und Verbesserungen vornehmen.     
 
Fehler in der Programmierung machen sich also gleich bemerkbar, wenn sich im Spaceland keine Änderungen zeigen oder eine Variable nicht kompatibel für einen bestimmten Block ist. Durch dieses "Schlüssel-Schloss- Prinzip" ist das Programm für Anfänger geeignet und gut verständlich.   
Auch die gut sortierten Variablen und Ordner machen das Programmieren einfach.   

Durch die vielen Gestaltungsmöglichkeiten ist StarLogoTNG sehr vielfältig nutzbar, wird aber nicht unübersichtlich, da das Programmierfeld am rechten oberen Rand nochmal in kleinerer Ausfühtung angezeigt wird, um den Überblick zu wahren, wenn die Variablen und Blöcke zu komplex werden. 




##Homogene Epidemie<a name="1"></a> 

https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Boolsche.PNG

Um eine homogene Epidemie zu erstellen, müssen wir zunächst eine boolsche Agentenvariable für den Zustand "ist krank" und "ist immun" einrichten.    
 
https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Ansteckungsrate.PNG   

Als nächsten Schritt muss eine Ansteckungswahrscheinlichkeit festgelegt werden, nach der ein gewisser Prozentsatz der Population erkrankt sein soll.     
Dazu erstellen wir einen "slider"- Block, mit dem wir die "Ansteckungsrate" festlegen können.
Danach setzen wir an den "slider"-Block die globale Variable "shared number" und benennen sie in "Ansteckungsrate" um.     
Den maximalen Wert setzten wir dazu auf "100".      
Im Kontrollzentrum des "Spacerland" kann man nun über einen Schieberegler die Ansteckungsrate einstellen.    

https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Giraffen.PNG      

Wie mit der Ansteckungsrate, fahren wir mit der Anzahl der Giraffen, also der Populationsgröße fort.     
Mithilfe eines "Slider"-Blocks und der Bedingung "Number Agents", setzen wir die maximale Populationsgröße auf 100 Giraffen/"Agenten".   
Dafür fügen wir an den "slider"-Block an die globale Variable "shared number" und benennen sie in "Number Agents" um.       
Wie die Ansteckungsrate kann die Populationsgröße im Kontrollzentrum des "Spaceland" eingestellt werden.    

https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Homogen.PNG    

Nun können wir mit der Programmierung der homogen verteilten Epidemie beginnen.      
Hierzu erstellen wir zunächst einen "setup"-Block, den wir in "Homogen" umbenennen.      
Damit wir bei jedem Neustart mit einer neuen Population beginnen können, setzen wir zuerst den Befehl 
"clear everyone" ein.    
Somit wird bei jedem Neustart über den "Homogen"-"setup"-Block im Kontrollzentrum die alte Population gelöscht.  
Als nächstes setzen wir einen "create Agent-number-do"-Block ein.     
Über das "number"-Feld können wir die Größe der kreierten "Agenten" einstellen.    
Dazu setzen wir den "number Agents"-Block ein, bei dem wir die Anzahl über den Schieberegler im "Spaceland" einstellen können.      
In das "do"-Feld setzen wir zuerst den Befehl "set color"-"red" ein, damit alle gesunden "Agenten" die Farbe rot annehmen.      
Danach haben wir die Befehle "set ist krank"-"false" und "set ist immun"-"false" verwendet, um die boolschen Agentenvariabeln zu initialisieren.      
Denn diese sollen für die gesunden/roten "Agenten" als falsch eingestellt sein.    
Damit ein bestimmter Prozentsatz, homogen über die Population verteilt, krank werden kann, setzen wir einen "if-test-then"-Block ein.     
In die "test"-Spalte setzen wir die Bedingung "random"-"100" "ist kleiner oder gleich" "Ansteckungsrate".     
In die "then"-Spalte setzen wir den Befehl "set color"-"blue" und setzen die boolsche Agentenvariabel mit "set ist krank"-"true" auf "wahr".      
Wenn also die Bedingung in der "test"-Spalte zutrifft wird der Agent krank/blau.    
 
https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/movement.PNG     

Damit sich die Krankheit ausbreiten kann, erstellen wir einen "forever"-Block und setzen einen Befehl für die Bewegung nach Vorne mit 1 bis 10 Schritten durch "forward"-"random"-"10" ein.     
Für die Drehung nach rechts in einem Winkel von 1-30 Grad setzen wir den Befehl "right"-"random"-"30" ein.      

##Infektionsherd<a name="2"></a> 

https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Ansteckungsrate.PNG      
https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Infektionsherd.PNG     
https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Gleichung%20Infektionsherd.PNG    

Um einen Agenten die Epedemie auslösen zu lassen, brauchten wir einen Infektionsherd. 
Zuerst erstellten wir einen neuen Block, den wir "Infektionsherd" nannten und fügten die Variablen "clear everyone" hinzu.    

Danach setzten wir unter diese Variable den Block "create agent", um den Auslöser der Epidemie zu kreieren.
Zu diesem Block kamen die Variablen "number Agent" und die Farbe des kranken Agenten. 

Außerdem war ein "if then test"- Block nötig, da die Farbe sich bei einer Ensteckung ändern sollte. 
Nachdem wir dies getan hatten, erstellten wir eine lange Variable nach Vorlage des des Satzes des Pythagoras.
Sie beschreibt die Aktion, dass ein kranker Agent einen gesunden bei einer Kollision infiziert und dann dessen Farbe annimmt, in Verbindung mit der Ansteckungsrate, welche wir ja im Spaceland variabel verwenden können. Wie diese Kollision zu programmieren ist, beschreiben wir im nächsten Schritt noch genauer. 


##Ansteckung<a name="3"></a> 
    
https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Ansteckung.PNG     

Um sich gegenseitig anstecken zu können, müssen sich ein kranker und ein gesunder "Agent" begegnen.     
Wir mussten also einen "Collisions"-Blog für eine Kollision zwischen zwei Agenten verwenden.     
Um eine Bedingung für die Ansteckung einstellen zu können, setzten wir einen "if-test-then"-Block in eine freies Feld des "Collision"-Blocks.     
Da sich nur "Agenten" unterschiedlicher Farbe, also unterschiedlicher Gesundheitszustände, anstecken sollen, setzten wir in das "test"-Feld die Bedingung "color of ID"-"collidee" "ungleich" "color of ID"-"ID".     
Als nächstes sollen sich die "Agenten" nur zu einer bestimmten Wahrscheinlichket anstecken. Also setzten wir einen weiteren "if-test-then"-Block in die "test"-Spalte des anderen "if-test-then"-Blocks.    
In die "test"-Spalte setzten wir die Bedingung "random"-"100" "ist kleiner oder gleich" "Ansteckungsrate".  
Somit erhalten wir eine Ansteckunswahrscheinlichkeit in Prozent.   
Trifft diese Bedingung zu, soll der "Agent" erkranken.   
Also setzten wir in die "then"-Spalte den Befehl "set color"-blue" und die boolsche Agentenvariable "ist krank" mit "set ist krank" auf "true".   

https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Ansteckungsrate.PNG      

Die Ansteckungsrate ist mit einem "slider"-Block im Kontrollzentrum des "Spaceland" durch einen Schieberegler einstellbar.   
Dafür setzen wir an den "slider"-Block die globale Variable "shared number" und benennen sie in "Ansteckungsrate" um.   

##Immunität<a name="4"></a> 

https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Homogen.PNG        
https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Boolsche.PNG    

Damit wir eine Immunität einrichten zu können müssen wir eine boolsche Agentenvariable für den Zustand "ist immun" erstellen. 

https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/movement.PNG     
   
Die kranken Agenten sollen nach einiger Zeit zu einer bestimmten Wahrscheinlickeit wieder gesund werden.   
Daraufhin sollen sie immun sein.   
Dazu setzen wir in den "forever"-Block einen "if-test-then"-Block ein.    
In die "test"-Spalte setzen wir die Bedingung "random"-"100" "ist kleiner oder gleich" "Heilingschance".    
Trifft dieser ZUstand bei einem "Agenten" ein, soll er die Befehle aus der "then"-Spalte ausführen.   
Diese wären:  
"Set color"-"green" und "set ist immun"-"true".  
Er soll also die Farbe grün für immun annehmen, weshalb wir die boolsche Agentenvariable für "ist immun" auf "true" eingestellt haben.

https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Heilungschance.PNG 

Die Heilungschance soll wieder mit einem Schieberegler im Spacland einstellbar sein.   
Hierzu erstellen wir einen "slider"-Block für die Heilunschance ein und setzen wieder den maximalen Wert auf "100".   
Dafür setzen wir an den "slider"-Block die globale Variable "shared number" und benennen sie in "Heilungschance" um.   

##Gesundheitszustand<a name="5"></a> 

https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Gesundheitszustand.PNG  

Die "Agenten" in der Epidemie-Simulation nehmen nun nach und nach unterschiedliche Farben an (rot, blau, grün).
Damit wir die Verteilung der unterschiedlichen Gesundheitszustände (Gesund, Krank, Immun) im Blick haben können,
erstellten wir ein Säulendiagramm, in dem wir die unterschiedlichen Mengen der Gesundheitszustände mittels Säulen
in den entsprechenden Farben ablesen können.    
Hierzu mussten wir zunächst einen "bar graph"-Block erstellen, den wir zuerst in "Gesundheitszustand" umbenannten.   
In den offenen "socks" konnten wir nun die Bedingungen für die einzelnen Säulen eingeben.  
Wir erstellten zuerst die Säule, die die Menge der gesunden "Agenten" angibt.   
Hierzu setzten wir an der "Gesundheitszustand"-Block den Befehl "count Agent with" an. 
Die Bedingung sollte in diesem Fall sein:    
"red" "=" "color of ID"-"ID". Die Farbe des Agenten sollte also der Farbe rot entsprechen, um in dieser Säule gezählt zu werden.    
Ähnlich fuhren wir bei den weiteren freien Feldern des "Gesundheitszustand"-Blocks fort.    
Wir setzten wieder den Befehl "count Agent with" ein.    
In dieser Säule sollte aber die Anzahl der kranken "Agenten" dargestellt werden.   
Hierzu setzten wir als Bedingung "blue" "=" "color of ID"-"ID" ein.    
Für die immunen Agenten fuhren wir genau so fort, setzten jedoch als Bedingung "yellow" "=" "color of ID"-"ID" ein.     
Nun konnte man zu Beginn der Simulation und im laufe der Simulation die Anzahl der gesunden, kranken und immunen Agenten im "Kontrollzentrum" des "Spaceland" ablesen.    
Durch Anklicken der Grafik kann der Zahlenbereich der Y- bzw. X-Achse ablesen.    
 
https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Grafik.PNG   

Startet man die Simulation einer homogenen Epidemie sieht das Bild mit den gesunden (rot), kranken (blau), und immunen (gelb) "Agenten" im "Spaceland" so aus: 
  
https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Epidemie%20Grafik.PNG    
