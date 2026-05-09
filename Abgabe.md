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


