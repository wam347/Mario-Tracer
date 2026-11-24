# Adressplan Mario Tracer (Stand 15.11.2026)

Gilt für `Gesamt 2026_11_15.pka`. Alle Netze haben die Maske 255.255.255.0, die seriellen Strecken 255.255.255.252. DNS-Server für alle Geräte ist 195.10.13.5.

## Netze von Call Me!

| Standort | Netz | Zweck | Router | Weitere Geräte |
|---|---|---|---|---|
| America | 195.10.13.0 | Server, Hauptswitch | .1 | Switch .2, DNS Server .5, HTTPS Server .6 |
| America | 195.10.23.0 | Server, Backup-Switch | .1 | Switch .2, DNS Server .5, HTTPS Server .6 |
| Philly | 195.10.11.0 | Server | .1 | Switch .2, Server Philly .5, Omas Server .50 |
| Philly | 195.15.11.0 | Kundenanschlüsse | .1 | Omas Router .10 |
| Brooklyn | 195.20.11.0 | Kundenanschlüsse Glasfaser | .1 | Router Marios .10 |
| Brooklyn | 195.25.11.0 | Kundenanschlüsse Kupfer (Peach) | .1 | DHCP ab .100 |
| Atlantic City | 195.50.11.0 | Server | .1 | Switch .2, Server Atlantic City .5, Online Casino .50 |
| Atlantic City | 195.55.11.0 | Kundenanschlüsse | .1 | Walugis Router .10 |

## Serielle Strecken

| Strecke | Netz | Adressen |
|---|---|---|
| America – Philly | 10.0.1.0 | America .1, Philly .2 |
| America – Brooklyn | 10.0.2.0 | America .1, Brooklyn .2 |
| America – Atlantic City | 10.50.1.0 | America .1, Atlantic City .2 |
| Atlantic City – Wario | 10.50.2.0 | Atlantic City .1, Wario .2 |

Router America kennt alle Standortnetze über statische Routen. Philly, Brooklyn und Atlantic City haben nur eine Standardroute zu America. Private Netze werden bei Call Me! nicht mehr geroutet, jeder Kunde nutzt NAT.

## Kundennetze

| Kunde | Netz | Router | Feste Adressen | DHCP |
|---|---|---|---|---|
| Mario (Pizzeria und Haus) | 192.168.2.0 | .1 | Switches .2 bis .6, MP Server .10, MH Server .11, Büro PC .23, Serverraum PC .24, Drucker .60 und .61 | .100 bis .139 vom MP Server |
| Oma | 192.168.1.0 | .1 | Switch .2, Laptop .23 | .100 bis .149 vom Router |
| Waluigi | 192.168.168.0 | .1 | Switch .2, Laptop .20, Server .50 | keines |
| Wario Superladen | 192.168.66.0 | .1 | Switch .2, Kasse .10, Laptop .11 | ab .100 vom Router |
| Wario Zentrale (öffentlich) | 195.60.11.0 | .1 | Switch .2, Webserver .10, Mailserver .11, NAT-Adresse .200 | keines |

Die Geräte der LAN-Party an der Hub-Kette (192.168.2.150 bis .175) sind unverändert.

## DNS-Namen

| Name | Adresse | Gerät |
|---|---|---|
| www.callme.com | 195.10.13.6 | HTTPS Server America |
| www2.callme.com | 195.10.23.6 | HTTPS Server America über den Backup-Switch |
| dns.callme.com, mail.callme.com | 195.10.13.5 | DNS Server America |
| dns2.callme.com | 195.10.13.6 | HTTPS Server America |
| philly.callme.com, www.marios-pizza.com | 195.10.11.5 | Server Philly |
| www.oma.com | 195.10.11.50 | Omas Server |
| atlantic-city.callme.com | 195.50.11.5 | Server Atlantic City |
| www.online-casino.com | 195.50.11.50 | Online Casino |
| www.wario-pizza.com | 195.60.11.10 | Wario Webserver |
| mail.wario-pizza.com | 195.60.11.11 | Wario Mailserver |
| www.test.de | wie bisher | unverändert auf beiden America-Servern |

## Zugangsdaten

| Wo | Benutzer | Passwort |
|---|---|---|
| Marios fünf Switches (Telnet) | mario | qwertzui |
| E-Mail callme.com | mario, luigi, peach, trooper, toad, boo, yoshi | qwertzui (unverändert) |
| E-Mail wario-pizza.com | wario / walugi | wario123 / walugi123 |
| Walugis Router | admin | qwertzui (unverändert) |
| WLAN Wario-Superladen | offen | ohne Passwort |

## Hostnamen

Router_America, Router_Philly, Router_Brooklyn, Router_AtlanticCity, Router_Marios, Router_Wario, WalugisRouter (Domain walugi.local). Die Switches heißen wie das Gerät, mit Unterstrichen statt Leerzeichen.
