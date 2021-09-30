Login:

# ISA 2021: Protokol pro cvičení č. 3: DNS
Nehledejte v odpovědích složitosti. Většinou je odpověď naprosto přímočará. ;)
## (1.) Seznámení s DNS

A a MX záznamy domény *vutbr.cz*:\
  \
  \
&nbsp;

## (2.) Seznámení s Whois

Od jakého roku je doména *vutbr.cz* registrována?

Do jakého rozsahu patří Vaše veřejná IP adresa a komu je tento rozsah přidělen?\
  \
&nbsp;

## (3.) Prozkoumání protokolu DNS

Jaké jsou autoritativní DNS servery pro doménu *vutbr.cz*?\
  \
  \
  \
*Display filter* pro zobrazení pouze DNS provozu:

Počet zachycených paketů souvisejících s vyhledáním NS pro doménu *vutbr.cz*:

Provedený DNS dotaz (vyberte správnou variantu): **rekurzivní** — **iterativní**

Podle čeho jste zjistili zakroužkovaný typ DNS dotazu v zachyceném paketu?

Cílová IP adresa paketu s DNS dotazem:

Jakému zařízení náleží tato IP adresa?\
&nbsp;


## (4.) Blokování vybraných domén

Přidaný záznam do souboru */etc/hosts* pro přesměrování *youtube.com*:\
  \
&nbsp;


## (5.) Zabezpečení a resolving pomocí DNS over TLS

*Display filter* pro zobrazení pouze provozu využívající TCP port 853:

*Display filter* pro zobrazení pouze provozu využívající TCP nebo UDP port 53:\
  \
  \
Služba běžící standardně nad portem 53:

Počet zachycených paketů se zdrojovým nebo cílovým portem 53:\
&nbsp;


## (6.) Analýza komunikace DNS over HTTPS

*Display filter* pro zobrazení pouze TLS provozu:

Jeden řádek z položky *Answers* z libovolné DoH odpovědi:  
  \
  \
IP adresa, na kterou směřovaly pakety s DoH dotazem:

Doménové jméno patřící k doplněné IP adrese: