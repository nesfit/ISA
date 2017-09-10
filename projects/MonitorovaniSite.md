# Monitorování sítě
Vytvořte monitorovací nástroj isamon jehož cílem bude prohledat síť a nalézt aktivní klienty, případně otevřené porty.

## Usage
```sh
isamon [-h] [-i <interface>] [-t] [-u] [-p <port>] -n <net_address/mask>
   -h --help -- zobrazí nápovědu
   -i --interface <interface> -- rozhraní na kterém bude nástroj scanovat
   -n --network <net_address/mask> -- ip adresa síťe s maskou definující rozsah pro scanování
   -t --tcp -- použije TCP
   -u --udp -- použije UDP
   -p --port <port> -- specifikace scanovaného portu, pokud není zadaný, scanujte celý rozsah
   -w --wait <ms> -- dodatečná informace pro Váš nástroj jaké je maximální přípustné RTT
```

## Příklady použití
```sh
$ isamon -h # vypíše nápovědu
$ isamon -i eth0 -n 192.168.1.0/24 # provede scanování sítě a zobrazí aktivní klienty za použití rozhraní ethé
$ isamon -n 192.168.1.0/30 # provede scanování sítě a zobrazí aktivní klienty za použití všech rozhraní
$ isamon -n 192.168.1.0/28 -t -p 22 # provede scanování sítě a zobrazí aktivní klienty s otevřeným TCP portem 22 za použití všech rozhraní
$ isamon -n 192.168.1.0/30 -t -u -w 5  # provede scanování sítě a zobrazí aktivní klienty a všechny otevřené TCP a UDP porty za použití všech rozhraní, pokud klient neodpoví do 5ms, isamon jej bude považovat danný port za uzavřený 
```

## Výstup
### Stdout
Pokud je klient aktivní, vždy vypište IP adresu na stdout. V případě detekce otevřeného portu, vypište IP adresu, protokol a port.
```sh
$ isamon -n 192.168.1.0/30 -t -u -w 5 
192.168.1.1
192.168.1.1 TCP 80
192.168.1.1 TCP 22
192.168.1.1 UDP 53
```
Při scanování samotné síťe, vypisujte pouze IP adresy na samostatné řádky. Další detekce neprovádějte.
```sh
$ isamon -n 192.168.1.0/30
192.168.1.1
192.168.1.2
```
### Stderr
Libovolné debugovací hlášky, chybové zprávy týkající se problémů např. nelze otevří socket...

### Err code
* 0 -- úspěšné ukončení
* 1 a následující -- chybové stavy dokumentované v dokumentaci a README

## Tipy 
* Zapřemýšlejte jaký protokol zvolit pro scanování síťě, která je přímo připojená vs síťě, která není. V přímo připojení síťi musí být scan 100% přesný, v nepřímo připojené nemusí všichni klienti respektovat RFC 1122 jak by měli.
* Inspirací nechť Vám je nmap. 
* Nevymýšlejte kolo a podívejte se, jaké knihovny máte v referenčním stroji k dispozici.

## Referenční virtuální stroj
Abychom Vám zjednodušili přípravu testovacícho prostředí a jste řešili pouze projekt a né komplikace se spuštěním virtuálního stroje, byl pro Vás připraven [předpis](https://github.com/nesfit/ISA/tree/master/projects/vagrant) pro jeho nasazení v nástroji Vagrant. Jedná se o centos/7 s příslušnými knihovnami viz [vagrantfile](https://github.com/nesfit/ISA/blob/master/projects/vagrant/Vagrantfile). Využijte jednoduché možnosti smazání a vytvoření virtuální stanice, možnosti konfigurace připojených sítí a také [rychlé vytváření testovací síťe obsahujícící více virtuálních strojů](https://www.vagrantup.com/docs/multi-machine/). Referenční stroj byl zkoušen s virtualizačním providerem virtualbox. Případné [limitace](https://www.vagrantup.com/docs/hyperv/limitations.html) ostatních providerů vyřešte individuální změnou do Vagrantfile nebo přednastavením Vašeho prostředí. 

## Bonusové rozšíření
Automatizované testy Vaší aplikace popsané v README, které využívají *vagrant multi machine*. Způsob testování je ve Vaší režii, ale musí být automatizovaný s přehlednými výsledky. Pro testy jsou povoleny libovolné frameworky, knihovny, jazyky, atd. Testy se spustí shell scriptem test.sh který zajistí také uklizení a odstranění testovacího prostředí. Testy se však v referenčním stroji nespouští, abychom nezanášeli další úroveň komplexity vnořenou virtualizací. Můžete však počítat s přítomností BASH a vagrant.

