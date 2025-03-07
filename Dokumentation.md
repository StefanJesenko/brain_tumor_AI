# Projekt-Dokumentation



Julius Burlet, Stefan Jesenko

| Datum | Version | Zusammenfassung                                              |
| ----- | ------- | ------------------------------------------------------------ |
|10.01.2025| 0.0.1 |Heute haben wir uns dafür entschieden was wir für ein Projekt machen und den Projektantrag abgegeben.|
|17.01.2025| 0.1.3|Heute haben wir das Konvertieren der JPG Bilder in CSV Dateien die zum trainieren des Models benutzt werden können implementiert.|
|24.01.2025| 0.5.0|Heute haben wir Activation Functions zu unserem Projekt hinzugefügt und definiert mit wie vielen Layern das Model trainiert werden soll.|
|31.01.2025| 0.7.1|Heute haben wir die Forward und die Backward propogation Funktion definiert und mit dem trainieren begonnen. Das Model hatte noch nicht die gewünschte Treffsicherheit, dies hoffen wir beim nächsten mal zu verbessen.|
|21.02.2025| 0.10.0|Heute haben wir unser Model weiter trainiert, es hat jetzt eine erhoffte Treffsicherheit von über 90%|
|28.02.2025| 1.0.0| Heute haben wir das Model fertiggsetellt und eine Funktion hinzugefügt die das Model speichert, um es später erneut abzurufen.|

## 1 Informieren

### 1.1 Ihr Projekt

In unserem Projekt werden wir ein NN (Neural Network) erstellen, dass anhand eines MRT Scanns klassifizieren kann welche Art von Gehirntumor auf dem Bild zu sehen ist.

### 1.2 User Stories

| US-№ | Verbindlichkeit | Typ  | Beschreibung                       |
| ---- | --------------- | ---- | ---------------------------------- |
| 1    |Funktional|Muss|Als Benutzer möchte ich, dass das Model anhand eines Bildes erkennen kann, ob es ein Gliomagehirntumor ist.|
| 2    |Funktional|Muss|Als Benutzer möchte ich, dass das Model anhand eines Bildes erkennen kann, ob es ein Meningiomagehirntumor ist.|
| 3    |Funktional|Muss|Als Benutzer möchte ich, dass das Model anhand eines Bildes erkennen kann, ob es ein normales Gehirn ist.|
| 4    |Funktional|Muss|Als Benutzer möchte ich, dass das Model anhand eines Bildes erkennen kann, ob es ein Hypophysengehirntumor ist.|
| 5    |Funktional|Muss|Die Daten sollen vor dem Trainieren normalisiert werden, damit das Model korrekt lernen kann.|
| 6    |Funktional|Muss|Eine Forward Propogation Funktion soll implementiert werden, damit anhand von Gewichten und errechnet werden kann welche Art von Tumor es ist.|
| 7    |Funktional|Muss|Eine Backward Propogation Funktion soll implementiert werden, damit ausgerechnet werden kann, welches Gewicht wie angepass werden muss um den Fehler zwischen dem Output des Modells und des Eigentlichen Outputs zu minimieren.|
| 8    |Qualität|Kann|Als Benutzer möchte ich, dass ein Bild mit dem dazugehörigen Output angezeigt wird, damit ich die Ergebnisse des Models Visualisieren kann.|
| 9    |Rand|Muss|Als Programmierer möchte ich, das für das Model nur numpy als externe Bibliothek verwendet wird, damit ich die Mathematik hinter eines NN(Neural Network) besser verinnerlichen kann.|




### 1.3 Testfälle

| TC-№ | Ausgangslage | Eingabe | Erwartete Ausgabe |
| ---- | ------------ | ------- | ----------------- |
| 1.1  |Projekt wurde gestartet und Model wurde trainiert.|MRT Scan eines Glioma Gehirntumors|Gliomatumor|
| 2.1  |Projekt wurde gestartet und Model wurde trainiert.|MRT Scan eines Meningioma Gehirntumors|Meningiomatumor|
| 3.1  |Projekt wurde gestartet und Model wurde trainiert.|MRT Scan eines Normalen Gehirns|Normales Gehirn|
| 4.1  |Projekt wurde gestartet und Model wurde trainiert.|MRT Scan eines Hypophysengehirntumors|Hypophysentumor|
| 5.1  |Projekt wurde gestartet.|JPG eines MRT Scans.|CSV Datei des JPGs|
| 6.1  |Projekt wurde gestartet.|CSV eines Gliomatumors wird der Forward Propogation Funktion als Input gegeben.| 0 (Laybel des Gliomatumors)|
| 7.1  |Projekt wurde gestartet.|Output des Models stimmt nicht mit dem erwarteten Output überein.|Back Propogation Funktion errechnet den Error für jede Layer|
| 8.1  |Projekt wurde gestartet und Model wurde trainiert.|Gliomatumor|MRT eines Gliomtumors mit Output des Models wird ausgegeben.|




## 2 Planen

| AP-№ | Frist | Zuständig | Beschreibung | geplante Zeit |
| ---- | ----- | --------- | ------------ | ------------- |
| 5.A  |17.01.2025|Stefan Jesenko|JPGs der Tumore werden in CSVs konvertiert|120min|
| 6.A |24.01.2025|Julius Burlet|Activation Funktionen werden definiert|60min|
| 6.B |24.01.2025|Stefan Jesenko|Anzahl Layers wird definiert.|120min|
| 6.C |31.01.2025|Julius Burlet|Forward Propogation Funktion wird erstellt.|120min|
| 7.A |31.01.2025|Stefan Jesenko|Back Propogation Funktion wird definiert|180min|
| 1.A |31.01.2025|Stefan Jesenko & Julius Burlet|Model wird auf Gliomatumore trainiert.|180min|
| 2.A |21.02.2025|Stefan Jesenko & Julius Burlet|Model wird auf Meningiomatumore trainiert.|180min|
| 3.A |21.02.2025|Stefan Jesenko & Julius Burlet|Model wird auf normale Gehirne trainert.|120min|
| 4.A |28.02.2025|Stefan Jesenko & Julius Burlet|Model wird auf Hypothysentumore trainert.|180min|

Total: 1260min

Die Zusätzliche Zeit ist als Puffer eingeplant.



## 3 Entscheiden

Wir haben uns dafür entschieden, unser Projekt nach den zuvor genannten Arbeitspaketen durchzuführen.

## 4 Realisieren

| AP-№ | Datum | Zuständig | geplante Zeit | tatsächliche Zeit |
| ---- | ----- | --------- | ------------- | ----------------- |
| 5.A  |17.01.2025|Stefan Jesenko|120min|240min|
| 6.A  |24.01.2025|Julius Burlet|60min|90min|
| 6.B  |24.01.2025|Stefan Jesenko|120min|180min|
| 6.C  |31.01.2025|Julius Burlet|120min|110min|
| 7.A  |31.01.2025|Stefan Jesenko|180min|200min|
| 1.A  |31.01.2025|Stefan Jesenko & Julius Burlet|180min|230min|
| 2.A  |21.02.2025|Stefan Jesenko & Julius Burlet|180min|200min|
| 3.A  |21.02.2025|Stefan Jesenko & Julius Burlet|120min|180min|
| 4.A  |28.02.2025|Stefan Jesenko & Julius Burlet|180min|180min|

Tatsächliche Zeit Total: 1610min

## 5 Kontrollieren

| TC-№ | Datum | Resultat | Tester |
| ---- | ----- | -------- | ------ |
| 1.1  |06.03.2025|OK|Stefan Jesenko|
| 2.1  |06.03.2025|OK|Stefan Jesenko|
| 3.1  |06.03.2025|OK|Stefan Jesenko|
| 4.1  |06.03.2025|OK|Stefan Jesenko|
| 5.1  |06.03.2025|OK|Stefan Jesenko|
| 6.1  |06.03.2025|OK|Stefan Jesenko|
| 7.1  |06.03.2025|OK|Stefan Jesenko|
| 8.1  |06.03.2025|OK|Stefan Jesenko|



## 6 Auswerten

✍️ Fügen Sie hier eine Verknüpfung zu Ihrem Lern-Bericht ein.

