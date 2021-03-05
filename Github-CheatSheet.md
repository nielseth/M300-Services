# Github Cheatsheet
**In diesem CheatSheet wird erklärt wie Github funktioniert und einige Commands werden zur Hilfe aufgelisted und erklärt**

## Git Storage Model 
![Git Storage Model](https://gitlab.com/mbe99/m300-git/-/raw/master/images/Git_StorageDataFlow1.png)

Das Repository wird Remote auf Github erstellt und danach mit Hilfe eines git clone wird ein Clone dieses Repositorys auf dem Rechner Lokal abgespeichert dieser Ort wird Workspace gennant. Dort können dann Script und weitere Dateien abgespeichert werden und via git add werden die im Workspace abgespeicherten Dateien in den Index gespeichert. Mit den git commit werden die Dateien auf dem Lokalen Repository abgespeichert. Wenn man nun noch die auf dem Lokalen Repository abgespeicherten Dateien auf das Repository auf Github bringen möchte so kann man dies mit dem git push Befehl machen. 

## Neues Git-Repository 
1. In Github eine neues leeres Repository erstellen
2. Im Dateisystem einen Ordner erstellen oder in einen bereits erstellten Ordner gehen
3. Im Ordner mit Rechtsklick die Git Bash öffnen (Für das sollte Git noch auf dem Rechner Lokal installiert werden)
4. Diese Unten stehenden Commands in der Git Bash eingeben
    * `echo "# test" >> README.md`
    * `git init`
    * `git add README.md`
    * `git commit -m "first commit"`
    * `git branch -M main`
    * `git remote add origin git@github.com:youraccount/test.git`
    * `git push -u origin main`

## Arbeiten mit Git
![Working with Github](https://gitlab.com/mbe99/m300-git/-/raw/master/images/Git_Data_Transport_Commands.jpg)

**von Änderungen zu Commit bis zum Push**
| Command | Workplace | Index (Stage) | local Repository | Remote Repository |
| -------- | -------- | -------- | -------- | -------- |
| vi, nano, vsc | File Änderung |  | | |
| git add | | Änderung staged | | |
| git commit | | | Änderung Versioniert | |
| git push | | | | Änderung auf Remote Repository|

## Arbeiten mit Workplace
File oder Verzeichnis unter Git Control löschen

`$ git rm {file} / $ git rm {dir}`

File oder Verzeichnis unter Git Control verschieben

`$ git mv {file} / $ git mv {dir}`

## Arbeiten mit dem Index (stage)
Zeigt den aktuellen File Status

`$ git status`

Neues oder geänderte File(s) unter Git Control bringen.

`$ git add {file}`

Zeigt was im Worsplace geändert, aber noch nicht im Index (staged) ist.

`$ git diff`

Zeigt was bereits zum Commit vorgemerkt wurde.

`$ git diff --cached  (auch -- staged)`

## Arbeiten mit dem lokalen Repository
Im Index vorgemerkte Änderungen in das lokale Repository committen

`git commit {file}`

Commit Historie ansehen

`$ git log`

Ein im Workplace modifiziertes File wieder auf den Stand des letzter Commit setzen

`$ git checkout -- {file}`

## Arbeiten mit dem Remote Repository
Remote Repository anzeigen

`$ git remote -v`

Alle Änderungen vom remote Repository (origin) in den Workplace laden

`$ git pull`

Änderungen vom lokalen Repository nach remote pushen

`$ git push origin`

*vor einem push immer zuerst ein pull ausführen*
