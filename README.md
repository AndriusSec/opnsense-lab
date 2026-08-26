# Homelab OPENSense Firewall Configuration
Homelab tinklo infrastruktūra sukonfigūruota OPNsense firewall/router'io, veikiančio kaip virtuali mašina Proxmox VE hipervizoriuje, su vienu fiziniu tinklo portu ir VLAN segmentacija.

Apžvalga

Šis projektas parodo, kaip sukurti saugų, segmentuotą namų tinklą naudojant tik vieną fizinį Ethernet portą serveryje, be papildomos tinklo plokštės ar valdomo switch'o. Visi sukurti VLAN'ai egzistuoja Proxmox viduje, ant virtualaus VLAN-aware tilto (vmbr1), o OPNsense maršrutizuoja ir filtruoja srautą.

Pagrindiniai tikslai:
  1. Atskirti paslaugas pagal pasitikėjimo lygį (ugniasienės administravimas, serveriai, viešai pasiekiamos paslaugos, kurios izoliuotos DMZ VLAN'e).
  2. Įgyvendinti asimetrinį pasitikėjimą t.y. patikimesnis segmentas gali pasiekti mažiau patikimą segmentą, bet ne atvirkščiai.
  3. Užtikrinti, kad veikiančios paslaugos negalėtų būti laisvai pasiekiama iš viso tinklo, VLAN'ų.
  4. Išlaikyti galimybę saugiai eksperimentuoti (tobulinti žinias), nesugadinant pagrindinio namų tinklo srauto.
   
Architektūra
<img width="7720" height="11045" alt="Untitled-2026-08-18-1109" src="https://github.com/user-attachments/assets/fe5ec956-ec31-4904-9923-2b12be3007a7" />
