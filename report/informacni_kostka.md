# Informační kostka – Report Rakety Hydra

Tento soubor slouží jako centralizovaná databáze všech sesbíraných informací pro finálový report.

## 1. Úvodní informace
- **Tým:** Hydra
- **Kategorie:** Začátečníci SŠ
- **Logo:** Bude dodáno později.

## 2. Letové a konstrukční parametry (z OpenRocket)
- **Předpokládané apogeum:** 558 m
- **Délka rakety:** 550 mm (0.1 m špička + 0.45 m trup)
- **Průměr trupu:** 63 mm
- **Očekávaná hmotnost bez motoru:** 897 g
- **Stabilita při opuštění rampy:** 1.05 cal.
- **Stabilita maximální:** 1.73 cal.
- **Maximální akcelerace:** 101.6 m/s²
- **Doba letu:** 91.9 s
- **Rychlost sestupu:** 8.0 m/s

## 3. Struktura a materiály
- **Hlavní trup:** Hotová uhlíková (carbonová) trubka od OXXO.
- **Hlavice (Nose cone):** 3D tisk z ASA, následně chemicky vyhlazeno parami acetonu.
- **Přepážky:** 3D tisk z ABS.
- **Stabilizátory:** Uhlíkové (carbon) pláty.

## 4. Výroba a montáž
- **CNC řezání:** Stabilizátory vyřezány CNC strojem ve spolupráci se SITPortem (Plzeň).
- **Laminace:** Stabilizátory zasunuty až dovnitř trupu a přilaminovány. Mezi každými dvěma stabilizátory je navíc pro zpevnění přelaminována skelná tkanina.
- **Uchycení motoru:** Motor se šroubuje do vlastního lože (do pojezdu), zasouvá se mezi vnitřní části stabilizátorů a zvenku se zavírá přišroubováním vnější klapky.

## 5. Pojezdy (Rail buttons)
- **Stav:** Fáze testování a návrhu (Draft).
- **Navrhované řešení:** 2x pojezdy z plastu Delrin.
- **Vnější průměr:** 15 mm.
- **Rozestup na trupu:** 280 mm.

## 6. Simulace
- **Software:** OpenRocket.
- **Obrázky k dispozici (v report/img/):** `design_rakety.png` (rozložení), `VerticalMotion_x_Time.png` (graf letu), `Stability_x_Time.png` (graf stability).

## 7. Elektronika a palubní systémy
- **Architektura avioniky (3 desky):**
  1. *Napěťová:* spínání palníků, INA čip (měření proudu/napětí), bzučák.
  2. *Logická:* RPi Pico, barometr ICP-10101, akcelerometr LSM6D.
  3. *GPS/Telemetrie:* u-blox SAM-M8Q GPS, modul HC-12.
- **Snímání statického tlaku:** Navrženy 3 otvory (3 mm průměr) po 120 stupních po obvodu.
- **Groundstation:** ESP mini + HC-12 modul (komunikace s HC-12 na palubě), připojení přes USB do PC.

## 8. Záchranný systém
- **Ejection charge:** 0.3 g střelného prachu na vyhození padáku.
- **Bezpečnostní pojistka:** RBF pin s červenou stuhou. Zasunutý pin drží stisknutý koncový přepínač a rozpojuje obvod palníku.
- **Logika odpalu (2 systémy):**
  - *Hlavní systém:* RPi Pico vyhodnocuje data filtrem. V apogeu odpálí hlavní palník.
  - *Záložní systém:* ATtiny402 detekuje start odtrhovým vodičem. Odpočítává fixní čas ze simulace + rezerva.

## 9. Challenge a nejlepší prvky
- **Ochrana vejce:** 2 polystyrenové poloválce zasunuté do trupu. Trup působí jako zámek proti rozevření.
- **Top prvky rakety pro Pitch:**
  1. Zcela nezávislý záložní mikrokontrolér záchrany (ATtiny402).
  2. Uhlíkové díly pro trup a stabilizátory (OXXO a SITPort).
  3. Geniálně jednoduchý a bezpečný polystyrenový systém ochrany vejce.

## 10. Procedury
- Sepsáno 38 bodů v checklistu (od registrace, přes kontrolu a odpal, po úklid).
