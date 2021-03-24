# Dokumentation M300

## Teil 1: Vorbereitung

### Vortwort

Ich kan offen und ehrlich sagen das ich mich sehr auf das Modul 300 in der TBZ gefreut habe. Den ich habe im Geschäfft mit Git, Docker und Kybernetes zu tun und ausserdem gefähllt mir der Lehrer herr Källin sehr. Das das Modul zum teil im home office stattfinden wird sehe ich als kein grossen Verlust da es das Modul nicht wirklich negativ beinflusst. Das einzige was mir ein wenig sorgen bereitet ist der Ausstausch aber ich bin mir sicher mit Herr Kälin wird das schon gehen. 

### Wissensstand vor dem Modul 

Mein Persöhnlicher Wissestand auf dem Gebiet ist schon etwas ausgereifft da ich ja wie gesagt schon erfahrungen auf dem Gebiet gesammelt habe. 

#### Github
Mit Github arbeite ich mindestens einmal pro Woche um meine Dokumente an einen sicheren ort abzulegen. Allerdings benutzte ich Git immer mit dem Visual Studio Code zusammen da es so deutlich übersichtlicher für mich ist.

#### Systemsicherheit
Mit SSH keys habe ich auch schon gearbeitet allerdings eher im Zusammenhang mit Putty zusammen. Mit Firewalls und der Rules darauf habe ich schon bekantschafft im ÜK 182 gemacht. Dort mussten wir eine Opensense Firewall einrichten mit vielen Rules und auch Portweiterleitungen. 

#### Vagrant
Mit Vagrant hatte ich leider bis jetzt noch gar keine erfahrung. Es scheint mir aber ein Praktisches tool zu sein um seine VMs zu manatchen. 

#### Linux
Linux ken ich bereits wie meine rechte Hosentasche. Ich hatte bereits im ersten Lehrjahr konntakt damit und von da an wurde meine Kentnisse noch stark verbessert durch ÜKs, Arbeit und private Projekte. 

#### Docker/Kybernetes
Andere Themen die nacher noch dazu kommen sind noch Docker und Kybernetes. Die beiden Themen habe ich auch schon im Geschäfft behandelt und bin vorallem von Kybernetes sehr begeistert. Leider sind sie noch nicht in der LB01 enthalten aber ich nehme an das sie in Zukunft noch einfluss auf das Modul haben werden. 

### Git standart Befehle
![Git Spick](https://github.com/sandro832/M300-Services/blob/main/Pictures/Cheatsheet.png)

### Vagrant Standard Befehle 

 Befehl | Funktion | Beispiel
|----------|:-------------:|------:|
| vagrant init |Im aktuellen Vezeichniss wird Vagrant umgebung, und file inizialisiert | vagrant init D:\TBZ\Module\Modul_300\MeineVagrantVM |
| vagrant up | Fährt vm mit dem Vagrant config file hoch | vagrant up --virtualbox |
| vagrant ssh | Verbindet auf die VM im Verzeichniss | vagrant ssh 
| vagrant status | Zeigt der Status der VM im Verzeichniss | vagrant status D:\TBZ\Module\Modul_300\MeineVagrantVM
| vagrant port | Zeigt Portforwarding an | vagrant port D:\TBZ\Module\Modul_300\MeineVagrantVM


### Theorie

#### Umgebungsvariabeln
Als Umgebungsvariable bezeichnet man konfigurierbare Variablen in Betriebssystemen, die oft Pfade zu bestimmten Programmen oder Daten enthalten, sowie bestimmte Daten und Einstellungen, die von mehreren Programmen verwendet werden können. In der Regel handelt es sich um Zeichenketten.

#### Thread
In der Informatik bezeichnet Thread – auch Aktivitätsträger oder leichtgewichtiger Prozess genannt – einen Ausführungsstrang oder eine Ausführungsreihenfolge in der Abarbeitung eines Programms. Ein Thread ist Teil eines Prozesses. 

#### Prozess
Ein Prozess ist ein Computerprogramm zur Laufzeit. Genauer ist ein Prozess die konkrete Instanziierung eines Programms zu dessen Ausführung innerhalb eines Rechnersystems, ergänzt um weitere Informationen und Ressourcenzuteilungen des Betriebssystems für diese Ausführung.

## Teil 2: Umgebung einrichten

#### Account erstellen

- www.github.com aufrufen und sich dort registrieren
- Die Email du Verifizierung bestätigen

#### Respositorty

- Unter www.github.com einen neuen Repo machen
- Gescheider Namen und allenfalls beschreibung machen
- Rpository auf Public stellen
- Repository erstellen

#### SSH Key erstellen

- Bash Terminal öffnen und folgender command eingeben:   $  ssh-keygen -t rsa -b 4096 -C "beispiel@beispiel.com"
- Bei der Abfrage, unter welchem Namen der Schlüssel gespeichert werden soll, die Enter-Taste drücken (für Standard):
- Nun kan ein Passwort festgelet werden. Das muss nanach noch wiederholt werden damit es keine Fehler gibt. 

#### SSH-Key hinzufügen
  
- Unter www.github.com auf Benutzerkonten
- Unter SSH und GPG Keys auf "New SSH key klicken
- Titel und bezecihnung festlegen
- Erstellter key einfügen 
- safe

#### Client einrichten

- CLient unter https://git-scm.com/downloads herunterladen
- Über Bash mit dem Github account verbinden:  git config --global user.name "<username>" git config --global user.email "<e-mail>"

#### M300 Repository einrichten

- Im Git Bash folgendes eingeben um Repo zu klonen: git clone https://github.com/mc-b/M300
- Ins Repo Verzeichnis wechseln
- Repository aktualisieren
  
#### Repositor vorbereiten

- Ordner für Verzeichniss erstellen
- Repositiory mit ssh oder HTTP klonen
- Repository aktualisieren

#### eigene Vagrant VM aufsetzen

![Netzwerkplan](https://github.com/sandro832/M300-Services/blob/main/Pictures/Netzwerkplan.PNG)

Um eine Vagrant VM mit einer Box zu erstellen muss man zuerst in einem Ordner seiner Wahl das Vagrantfile erstellen für die Konfigurationen der VM. Dies geht mit dem command "vagrant init [VM-Aus-Cloud](https://app.vagrantup.com/ubuntu/boxes/)". Nachdem dieses Config File erstellt ist kann man dieses verändern. Die Config Files sehen je nach VM anders aus. Die wichtigstens änderungen, welche man vornehmen kann ist die IP adresse, die menge an RAM und Cores sowie commands welche beim Einrichten bereits in der Shell ausgeführt werden sollen beim erstellen der VM. Sobald mann alle Konfigurationen vorgenommen hat kann man mit dem Befehl vagrant up die VM erstellen. Wenn dies gemacht wurde, benutzt man den command vagrant ssh um sich mit dieser VM zu verbinden.

### Sicherheit
    Die VM ist nur ist über SSH erreichbar was einigermassen sicher ist.
    Der Web Server ist offen und mittels ungeschütztem HTTP Protokoll erreichbar.

### Testfälle

#### Testfall 1
![Testfall 1](https://github.com/sandro832/M300-Services/blob/main/Pictures/Fall1.PNG)

#### Testfall 2
![Testfall 2](https://github.com/sandro832/M300-Services/blob/main/Pictures/Fall2.PNG)

#### Testfall 3
![Testfall 3](https://github.com/sandro832/M300-Services/blob/main/Pictures/Fall3.PNG)

#### Testfall 4
![Testfall 4](https://github.com/sandro832/M300-Services/blob/main/Pictures/Fall4.PNG)


### VM Webserver testen 

![WebserverTesten](https://github.com/sandro832/M300-Services/blob/main/Pictures/Unbenannt.PNG)

### Port forwarding

![PortForwarding](https://github.com/sandro832/M300-Services/blob/main/Pictures/Permission%20denied.PNG)

## Teil 3: Vagrant File

Hier sind kommandos aufgelistet die im Vagrant konfigurationsfile vorhanden sind.

<mark> sudo ufw --force enable </mark>


Mit diesem Command wird die ufw Firewall dazu gezwungen sich zu aktivieren auch falls dies von etwas blockiert werden sollte.

<mark> sudo ufw allow 22 </mark>


Mit diesem Command wird der Port 22 auf der Firewall freigegeben.

<mark> sudo ufw allow 2222 </mark>


Mit diesem Command wird der Port 2222 auf der Firewall freigegeben.

<mark> sudo systemctl start ssh </mark>


Mit diesem Command wird der Dienst ssh gestartet

<mark>sudo sed -i "s/.*PasswordAuthentication.*/PasswordAuthentication yes/g" /etc/ssh/sshd_config </mark>


Mit diesem Command sucht man im File "/etc/ssh/sshd_config" nach ".PasswordAuthentication." und ersetzt dies durch "PasswordAuthentication yes".

    "/g" steht für global. Das heisst es ersetzt den Gesuchten Teil überall im genannten File und nicht nur an einem Ort

<mark> sudo sed -i "s/.*ChallengeResponseAuthentication.*/ChallengeResponseAuthentication yes/g" /etc/ssh/sshd_config </mark>
 

Mit diesem Command sucht man im File "/etc/ssh/sshd_config" nach ".ChallengeResponseAuthentication." und ersetzt dies durch "ChallengeResponseAuthentication yes".

    "/g" steht für global. Das heisst es ersetzt den Gesuchten Teil überall im genannten File und nicht nur an einem Ort

<mark> sudo chown -c vagrant /var/mail </mark>


Mit diesem Command werden die Rechte für den Ordner /var/mail an de User vagrant gegeben.

<mark> sudo chmod -R 700 /var/mail </mark>


Mit diesem Command setzt man die Rechte auf 700 --> User hat Read/Write/Execute. Group und Global haben keine Berechtigungen.

<mark> sudo apt-get -y install nginx </mark>


Mit diesem Command wird nginx für den Reverse-Proxy installiert.

<mark> sudo unlink /etc/nginx/sites-enabled/default </mark>


Mit diesem Command wird der Virtuelle Host unlinked.

<mark> sudo touch /etc/nginx/sites-available/reverse-proxy.conf </mark>


Mit diesem Command erstellt man das File für die Konfigurationen des Reverse-Proxy.

<mark> cat <<%EOF% | sudo tee -a /etc/nginx/sites-available/reverse-proxy.conf
	server {
		listen 187;
		location / {
			proxy_pass http://127.0.0.1;
		}
	}
%EOF%
</mark>

Dieser Abschnitt fügt den Inhalt im File "/etc/nginx/sites-available/reverse-proxy.conf" hinzu. Der Inhalt sagt, dass der Reverse Proxy über Port 187 für den Localhost (127.0.0.1) kommuniziert.

<mark> sudo ln -s /etc/nginx/sites-available/reverse-proxy.conf /etc/nginx/sites-enabled/reverse-proxy.conf </mark>


Mit diesem Command erstellt man einen Symlink von "/etc/nginx/sites-available/reverse-proxy.conf" nach "/etc/nginx/sites-enabled/reverse-proxy.conf".

<mark> sudo systemctl stop apache2 </mark>


Dieser Command stopt den Dienst "apache2".

<mark> sudo systemctl restart nginx </mark>


Dieser Command startet den Dienst "nginx" neu.

<mark> sudo reboot </mark>

## Teil 4: Arbeitschritte testen

### Berechtigungen prüfen
![Berechtigung](https://github.com/sandro832/M300-Services/blob/main/Pictures/Permission%20denied.PNG)

### Reverse Proxy prüfen

![ReverseProxy](https://github.com/sandro832/M300-Services/blob/main/Pictures/Reverse%20proxy.PNG)

### Test Firewall

![UFWTest](https://github.com/sandro832/M300-Services/blob/main/Pictures/test%20ufw.PNG)

## Fazit 
Vom der LB01 habe ich sicher einiges gelernnt. Ich hatte zwar schon erfahrungen mit den Themen aber das ganze mehr oder weniger über ein Logfile zu konfigurieren habe ich so noch nie gemacht. Auch die integration mit Git fand ich gut da ich so meine Git Kompetenzen gut gebrauchen konnte um anderen zu helfen. Wichtige skills die ich gelernt habe sind volgende:

- Erstellen von Vagrant VMs mit Virtual Box
- Erstellen von Vagrant VMs mit Boxes
- Text in Config files schreiben mit Ruby
- Port forwarding im VagrantFile einrichten
- Besserer umgang mit GitHub
- SSH-Key erstellen und einbinden
- VM Konfigurieren mit hilfe von Vagrant Fil
- Umgang mit Makrdown File
    