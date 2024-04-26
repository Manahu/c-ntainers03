# containers03

## Utilizarea containerelor ca medii de execuție

### Scopul

Această lucrare de laborator are ca scop familiarizarea cu comenzile de bază ale OS Debian/Ubuntu. De asemenea, aceasta va permite să vă familiarizați cu Docker și comenzile sale de bază.

### Sarcina

Pornind de la imaginea oficială a sistemului de operare Ubuntu, să se creeze un container care să conțină un server web Apache. Să se creeze o pagină web care să conțină textul "Hello, World!" și să se afișeze într-un browser.

### Instrucțiuni

#### Pornirea și testarea:

Deschideți terminalul în directorul 'containers03' și executați următoarea comandă pentru a porni un container Ubuntu și a accesa terminalul sau interactiv:

docker run -ti -p 8000:80 --name containers03 ubuntu bash


În fereastra terminalului containerului, executați următoarele comenzi:

apt update
apt install apache2 -y
service apache2 start

### Testarea paginii web:
Deschideți un browser și accesați adresa http://localhost:8000. Ar trebui să vedeți pagina web implicită Apache.

### Pagina web implicită Apache
În continuare, executați următoarele comenzi în terminalul containerului:

ls -l /var/www/html/
echo '<h1>Hello, World!</h1>' > /var/www/html/index.html

Reîmprospătați pagina în browser. Ar trebui acum să vedeți textul "Hello, World!" afișat pe pagină.

#### Pagina web modificată
Explorarea configurării Apache:
Executați următoarele comenzi în terminalul containerului:
cd /etc/apache2/sites-enabled/
cat 000-default.conf
Afișează conținutul fișierului de configurare pentru site-ul implicit Apache.

#### Finalizare și curățare:
Închideți fereastra terminalului containerului cu comanda 'exit'.

Afișați lista de containere Docker în terminalul gazdă:

docker ps -a

### Ștergeți containerul creat anterior:

docker rm containers03

![web](C:\Users\Monahu\containers03\img\web.png)


