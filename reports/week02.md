1. SNMP on verkonhallinnassa käytettävä protokolla joka tulee sanoista Simple Network Management Protocol.
SNMP:tä käytetään keräämään ja valvomaan tietoa verkkolaitteista kuten kytkimistä, palvelimista, tai tulostimista.

2. SNMP asennusta varten kirjaudutaan halutulle palvelimelle ja suoritetaan ensin apt update, jonka jälkeen SNMP asennetaan komennolla apt install snmp snmpd -y.

2.3 
Järjestelmän nimi on web1 ja käyttöjärjestelmänä toimii linux, uptime tässä vaiheessa on 1 tunti, 50 minuuttia.

2.5 
Rajapintoja löytyy 3:

IF-MIB::ifDescr.1 = STRING: lo
IF-MIB::ifDescr.63 = STRING: eth0
IF-MIB::ifDescr.92 = STRING: eth1

eth1 yhdistää laitteen verkkoon.

2.6

sysName.0 on laitteen hostname.
sysDescr.0 on laitteen ja käyttöjärjestelmän kuvaus.
sysUpTime.0 on SNMP agentit käynnissäoloaika.
ifDescr on verkkokorttien ja liitäntöjen nimet ja kuvaukset.
ifOperStatus on verkkoliitänän hetkellinen tila, up(1) tai down(0).

2.7 

web1

sysName.0
SNMPv2-MIB::sysName.0 = STRING: web1

sysDescr.0
STRING: Linux web1 6.18.33.2-microsoft-standard-WSL2 #1 SMP PREEMPT_DYNAMIC Thu Jun 18 21:54:43 UTC 2026 x86_64

sysUpTime.0
DISMAN-EVENT-MIB::sysUpTimeInstance = Timeticks: (706774) 1:57:47.74


db1

sysName.0
SNMPv2-MIB::sysName.0 = STRING: db1

sysDescr.0
SNMPv2-MIB::sysDescr.0 = STRING: Linux db1 6.18.33.2-microsoft-standard-WSL2 #1 SMP PREEMPT_DYNAMIC Thu Jun 18 21:54:43 UTC 2026 x86_64

sysUpTime.0
DISMAN-EVENT-MIB::sysUpTimeInstance = Timeticks: (12155) 0:02:01.55

branch-client

sysName.0
SNMPv2-MIB::sysName.0 = STRING: branch-client

sysDescr.0
SNMPv2-MIB::sysDescr.0 = STRING: Linux branch-client 6.18.33.2-microsoft-standard-WSL2 #1 SMP PREEMPT_DYNAMIC Thu Jun 18 21:54:43 UTC 2026 x86_64

sysUpTime.0
DISMAN-EVENT-MIB::sysUpTimeInstance = Timeticks: (3868) 0:00:38.68

2.8

1. SNMP mahdollistaa verkon laitteiden automaattisen valvonnan ja hallinnan, sekä auttaa havaitsemaan toimintahäiriöt.
2. SNMP:llä voidaan kerätä tietoja laitteistosta, järjestelmänstä, verkosta ja resurssien käytöstä.
3. SNMPv2 lähettää community stringin plain textinä verkon yli, eikä siirrettävä data ole salattua.
4. Julkisissa verkossa tai käyttökohteissa joissa vaaditaan tarkkaa tietoturvaa.



1. SNMP on verkonhallinnassa käytettävä protokolla joka tulee sanoista Simple Network Management Protocol.
SNMP:tä käytetään keräämään ja valvomaan tietoa verkkolaitteista kuten kytkimistä, palvelimista, tai tulostimista.

2. SNMP asennusta varten kirjaudutaan halutulle palvelimelle ja suoritetaan ensin apt update, jonka jälkeen SNMP asennetaan komennolla apt install snmp snmpd -y.

3. 

web1

sysName.0
SNMPv2-MIB::sysName.0 = STRING: web1

sysDescr.0
STRING: Linux web1 6.18.33.2-microsoft-standard-WSL2 #1 SMP PREEMPT_DYNAMIC Thu Jun 18 21:54:43 UTC 2026 x86_64

sysUpTime.0
DISMAN-EVENT-MIB::sysUpTimeInstance = Timeticks: (706774) 1:57:47.74


db1

sysName.0
SNMPv2-MIB::sysName.0 = STRING: db1

sysDescr.0
SNMPv2-MIB::sysDescr.0 = STRING: Linux db1 6.18.33.2-microsoft-standard-WSL2 #1 SMP PREEMPT_DYNAMIC Thu Jun 18 21:54:43 UTC 2026 x86_64

sysUpTime.0
DISMAN-EVENT-MIB::sysUpTimeInstance = Timeticks: (12155) 0:02:01.55


branch-client

sysName.0
SNMPv2-MIB::sysName.0 = STRING: branch-client

sysDescr.0
SNMPv2-MIB::sysDescr.0 = STRING: Linux branch-client 6.18.33.2-microsoft-standard-WSL2 #1 SMP PREEMPT_DYNAMIC Thu Jun 18 21:54:43 UTC 2026 x86_64

sysUpTime.0
DISMAN-EVENT-MIB::sysUpTimeInstance = Timeticks: (3868) 0:00:38.68

4. 

Rajapintoja löytyy 3:

IF-MIB::ifDescr.1 = STRING: lo
IF-MIB::ifDescr.63 = STRING: eth0
IF-MIB::ifDescr.92 = STRING: eth1

eth1 yhdistää laitteen verkkoon.

5. OID eli Object Identifier on SNMP protokollassa käytettävä osoite, joka osoittaa tiettyyn laitteen hallintatietoon. OID:lla voidaan pyytää tietoja laitteelta.

6. SNMP mahdollistaa verkkolaitteiden automaattisen valvonnan ja hallinnan sekä vikatilanteiden havaitsemisen keräämällä tietoa järjestelmistä, verkosta ja resurssien käytöstä. Sen suurin rajoitus on tietoturva, koska SNMPv2 lähettää community stringin ja muun datan salaamattomana verkon yli. Tästä syystä julkisissa verkoissa ja korkean tietoturvan kohteissa on aina käytettävä suojattua SNMPv3-versiota.