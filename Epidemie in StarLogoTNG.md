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
Es ist übersichtlich aufgebaut und besteht aus zwei Feldern, dem Programmierfeld und dem Spaceland, wo man die Aktionen und Fortschritte der Agenten verfolgen kann. Die Agenten können mehrere Formen annehmen und so individuell eingestellt werden. Auch die Umgebung kann durch Gebäude, Pflanzen und andere Gegenstände ergänzt werden. Durch das Zusammensetzen verschiedener Böcke, die in Ordnern am Rande des Programmierfeldes untergebracht sind, kann man die Agenten zu verschiedenen Handlungen bewegen. Unten im Spaceland kann man bei Betätigung des "forever"- Buttons die aktuellen Änderungen sichern und die 

##Homogene Epidemie<a name="1"></a> 

https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Ansteckungsrate.PNG     
https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Giraffen.PNG      
https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Homogen.PNG       
https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/movement.PNG     

##Infektionsherd<a name="2"></a> 

https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Ansteckungsrate.PNG      
https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Infektionsherd.PNG     
https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Gleichung%20Infektionsherd.PNG      

##Ansteckung<a name="3"></a> 

https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Ansteckungsrate.PNG     
https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Ansteckung.PNG     

##Immunität<a name="4"></a> 

https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Homogen.PNG    
https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/movement.PNG     
https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Boolsche.PNG     
https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Heilungschance.PNG    

##Gesundheitszustand<a name="5"></a> 

https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Gesundheitszustand.PNG  

Die "Agenten" in der Epidemie-Simulation nehmen nun nach und nach unterschiedliche Farben an (rot, blau, grün).
Damit wir die Verteilung der unterschiedlichen Gesundheitszustäne (Gesund, Krank, Immun) im Blick haben können,
erstellten wir ein Säulendiagramm, in dem wir die Unterschielichen Mengen der Gesundheitszustände mittels Säulen
in den entsprechenden Farben ablesen können. 
Hierzu mussten wir zunächst einen "bar graph"-Block erstellen, den wir zuerst in "Gesundheitszustand" umbenannten. In den offenen "socks" konnten wir nun die Bedingungen für die einzelnen Säulen eingeben.
Wir erstellten zuerst die Säule, die die Menge der gesunden "Agenten" angibt. Hierzu setzten wir an der "Gesundheitszustand"-Block den Befehl "count Agent with" an. Die Bedingung sollte in diesem Fall sein, 
"red" "=" "color of ID""ID". Die Farbe des Agenten sollte also der Farbe rot entsprechen, um in dieser Säule gezählt zu werden. 
Ähnlich fuhren wir bei den weiteren freien Feldern des "Gesundheitszustand"-Blocks fort. Wir setzten wieder den Befehl "count Agent with" ein. In dieser Säule sollte aber die Anzahl der kranken "Agenten" dargestellt werden.
Hierzu setzten wir als Bedingung "blue" "=" "color of ID""ID" ein. 
Für die immunen Agenten fuhren wir genau so fort, setzten jedoch als Bedingung "yellow" "=" "color of ID""ID" ein.
Nun konnte man zu Beginn der Simulation und im laufe der Simulation die Anzahl der gesunden, kranken und immunen Agenten im "Kontrollzentrum" des "Spaceland" ablesen. Durch Anklicken der Grafik kann der Zahlenbereich der Y- bzw. X-Achse ablesen. 
 
https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Grafik.PNG   

Startet man die Simulation einer homogenen Epidemie sieht das Bild mit den gesunden(rot), kranken (blau), und immunen (gelb) "Agenten" im Spaceland so aus:
  
https://github.com/antoniatheresa/Epidemie-Projekt/blob/master/Epidemie%20Grafik.PNG    
