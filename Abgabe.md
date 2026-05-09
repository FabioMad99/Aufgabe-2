## Aufgabe 2

# Git-Quest

1.
Es wurden die Daten, die vom ```end``` Branch geändert wurden, auch zum ```master``` übernommen.
```
questlog.md | 6 ++++++
rucksack.md | 2 +-
stats.md    | 6 +++---
```
2.
Dasselbe, was auch in 1. passiert ist. 
```
questlog.md | 6 ++++++
rucksack.md | 2 +-
stats.md    | 6 +++---
```
Meine änderungen sind aber vorhanden, da es kein Merge Konflikt war.

3.
Bei einem anderen Text (bsp. im Questlog.md, hat ```end``` am Ende noch das Ende der Quest geschrieben, aber ich beim ```master``` was komplett anderes schreibe) entsteht ein Merge Conflict.
Bei dem müssen wir uns für 1 von 2 Entscheidungen entscheiden. 
- ```master``` änderungen vornehmen.
- ```end``` änderungen vornehmen.


Beim selbem Text:
Wird dieselbe Datei (mit demselben Text) nicht angezeigt, da es keine änderung nach dem Merge ist.
```
 rucksack.md | 2 +-
 stats.md    | 6 +++---
```
*TLDR*: Wenn anders = Merge Conflict

4.
Selbe Änderung wie in aufgabe 3. Jedoch diesmal vor dem Merge ein ```git rebase master```. Bei einem Konflikt ist dasselbe Spiel wieder. Entweder mache ich die Änderung vom end oder vom master.
Dann ach kann ich mit ```git rebase --continue``` weiter machen, falls es noch weiter geht.
Wenn ich dann wieder zu ```master``` checkout und dann ein ```git merge end``` ausführe. Passiert diese OHNE konflikte (solange es keine neuen änderungen gibt), auch wenn die anders sind.

Fazit zu 4:
Rebase macht die Branches von "Parallel" zu "Linear". In der Aufgabe war dann ```end``` nicht mehr parallel, sondern linear vorne vom ```master```


# Cat-Cafe

Gradle

1. Mit gradle run kann jetzt die main ```catcafe.Main``` ausgeführt werden.
``` 
Es schnurren 3 Samtpf´┐¢tchen.
Gewicht [3,4]: FelineOverLord[name=Gwenapurr Esmeralda, weight=3]
Name 'Miss Chief Sooky': FelineOverLord[name=Miss Chief Sooky, weight=2]
```
2. *gradle test* kann auch ausgeführt werden.
```
PS C:\Users\xxx\Desktop\HSBI\Semester2\PR2\Lesson-2\Cat-Cafe> & "C:\Gradle\gradle-9.5.0\bin\gradle.bat" test
Calculating task graph as configuration cache cannot be reused because file 'build.gradle' has changed.

BUILD SUCCESSFUL in 1s
3 actionable tasks: 2 executed, 1 up-to-date
Configuration cache entry stored.
```

3. Da spotless bereits integriert ist, könnte man es mit *gradle spotlessApply* ausführen, jedoch kann man den Default nicht auf 4 Leerzeichen umstellen. Es ist fest definiert und nicht änderbar.


# JUnit

1. Die Testfälle sind wichtig, weil sie prüfen, ob die Klasse CatCafe in den üblichen Situationen richtig funktioniert. Also ob Katzen richtig hinzugefügt werden, ob die Anzahl stimmt und ob man Katzen nach Namen oder Gewicht auch wirklich wiederfindet. Außerdem testen sie nicht nur die „einfachen“ Fälle, sondern auch Situationen, in denen z. B. keine passende Katze gefunden wird oder Grenzwerte beim Gewicht eine Rolle spielen. Dadurch sieht man, ob die Klasse auch dann noch korrekt arbeitet, wenn es nicht nur Standard-Eingaben sind.
2. Unterschiedliche Methoden, Eingaben, Szenarien werden getestet. Somit ist dann vieles abgedeckt, da wir nicht nur einzelne Verhalten testen, sondern verschiedene mögliche Zustände der Klasse.

# CI-Pipeline

Mit ```mkdir .github/workflows``` den pfad erstellt und eine ```ci.yml``` file erstellt.
In dieser Datei wurde dann alle 3 Anweisungen eingefügt. ```build / test / spotlessCheck```
Mit ```on: push``` wird es immer, bei einem push, ausgeführt. ```on push, do jobs```