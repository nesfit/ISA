# ISA 2021: Odpovědní arch pro cvičení č. 3: DNS

## (1.) Seznámení s DNS

A a MX záznamy domény *vutbr.cz*:\
  \
  \
&nbsp;

## (2.) Překlad DNS dotazů

Jaké jsou autoritativní DNS servery pro doménu *vutbr.cz*?\
  \
  \
  \
*Display filter* pro zobrazení pouze DNS provozu:

Počet zachycených paketů souvisejících s vyhledáním NS pro doménu *vutbr.cz*:

Provedený DNS dotaz (vyberte správnou variantu): **rekurzivní** — **iterativní**

Podle čeho jste zjistili zakroužkovaný typ DNS dotazu v zachyceném paketu?

Cílová IP adresa paketu s DNS dotazem:

Jakému zařízení náleží zapsaná IP adresa?


## (3.) Zabezpečení a překlad pomocí DNS over HTTPS

Dokážete zjistit ze zachyceného DNS provozu, jaké domény jste předtím navštívili? Proč?   
  \
  \
  \
*Display filter* pro zobrazení pouze TLS provozu:

Jeden řádek z položky *Answers* z libovolné DoH odpovědi:  
  \
  \
IP adresa, na kterou směřovaly pakety s DoH dotazem:

Doménové jméno patřící k doplněné IP adrese:


## (4.) Zabezpečení a resolving pomocí DNS over TLS

*Display filter* pro zobrazení pouze provozu využívající TCP port 853:

*Display filter* pro zobrazení pouze provozu využívající TCP nebo UDP port 53:

Služba běžící nad portem 53:

Počet zachycených paketů se zdrojovým nebo cílovým portem 53:


## (5.) Blokování reklam

Jaký rozdíl jste zpozorovali na webu *idnes.cz* při jeho načtení s aktivním nástrojem *pi-hole*?
