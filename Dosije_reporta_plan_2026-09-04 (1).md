# Konacni dosije reporta - plan racionalizacije

> Datum: 2026-09-04 · Nomenklatura R1-R16 · Status: **DONE** (detaljno + prototip) / **PLAN** (plan definisan) / **WAIT** (ceka).

## Rezime po reportu

| Kod | Report | Status | Danas | Na kraju | Prototipi |
|---|---|---|---|---|---|
| R1 | Dashboard | DONE | 22 | ~8 strana | 4 |
| R2 | Payout Consolidated | DONE | 9 | ~3 strane | 2 |
| R3 | Tracking Platform Final | DONE | 17 | ~7 strana | 2 |
| R4 | Tracking Platform AM | PLAN | 6 | R4 ostaje zaseban report sa 4 strane: Ac | 0 |
| R5 | Support | PLAN | 10 | tanak Operational/Support report (~3-4 strane): System Health + DOD Operator Alert + negativni-GGR/RTP monitoring. | 0 |
| R6 | Business Overview | DONE | 5 | Rastvara se: Management Report (exec) +  | 2 |
| R7 | Promotions Preview AM | PLAN | 1 | R7 postaje Promo modul (4 moda): Schedul | 1 |
| R8 | Profit By Integration | PLAN | 1 | Ostaje 1 strana (jedina margin mera). Ce | 0 |
| R9 | Promotions Tracking Preview | WAIT | 1 | Rastvara se u Promo modul (potvrditi). | 0 |
| R10 | Competitor Analysis Historical | PLAN | 3 | Arhivira se (nevalidan). 0 strana. | 0 |
| R11 | New release dashboard | PLAN | 16 | Ostaje okosnica (16 -> ~12 posle 2 mini- | 2 |
| R12 | New Release - Metrics | PLAN | 5 | Ostaje 5 strana + prima launch strane +  | 1 |
| R13 | Distributivna mreza | PLAN | 3 | Ostaje 3 strane (uz dopune). | 0 |
| R14 | Client Performance (MBR & QBR) | PLAN | 1 | Gasi se (dup). 0 zasebnih strana. | 0 |
| R15 | PlayNet_Report_Live | PLAN | 7 | Ostaje 7 strana (klijentski, RLS). | 0 |
| R16 | Dashboard - Pracenje igrica | PLAN | 5 | Arhivira se. 0 strana. | 0 |

## Detaljno po reportu

### R1 - Dashboard  [DONE]  (C3P, 22 strana)

**Plan:** 3 konsolidacije (Trend 5->1, DARR 3->1, Game Performance 2->1) + 5 brisanja + 3 premestanja. Dashboard se svodi na komercijalno-analiticki sloj.

| Akcija | Sadrzaj | Kuda |
|---|---|---|
| MERGE | Monthly + Market/Operator/AM Trend (5->1) | Trend konsolidovano (param dimenzija + measure-grupe) |
| MERGE | DOD + Daily + DOD Operator Alert (3->1) | DARR daily (ceka F-01) |
| MERGE | Game DOD + Game Tracker (2->1) | Game Performance (toggle Matrica/Ribbon) |
| BRISATI | Custom Period Top N, Bridge, Game Details, Portal/Game analysis |  |
| PREBACI | System Health | -> Support |
| PREBACI | Operator Tax | -> Billing/reference |
| PREBACI | Jackpot Live | -> Player Tracking + RLS (row-level) |
| KEEP | Variable RTP (duplikat R3.16) | pravi Variable RTP na R1; DUPLIKAT R3.16, ostaje na obe (raniji privremeni duplikat sklonjen) |

**Sta ostaje na kraju:** MOM, New Business, Top N, Game Trend, Game Position Tracker + 3 konsolidovane (Trend/DARR/Game Performance) = ~8 strana

**Prototipi:** Prototip_Trend_drill, Prototip_DARR_drill, Prototip_Game_Performance, R1_plan_racionalizacije

### R2 - Payout Consolidated  [DONE]  (C3P, 9 strana)

**Plan:** Billing param-merge (4->1). R2 ostaje billing report (CFO/Billing home), svucen na ~3 strane.

| Akcija | Sadrzaj | Kuda |
|---|---|---|
| MERGE | Payout By Company + Payout By Operator + Details + Billing (4->1) | Billing konsolidovano (Grupisi po Company/Operator + Granulacija + measure-grupe) |
| PREBACI | Promotions | -> Promo modul |
| DEDUP | New Business | -> jedan home (New Casinos) |
| DEDUP | Business Overview | -> Management Report |

**Sta ostaje na kraju:** Billing konsolidovano + Payout By Operator First 12 months (time-pivot) + Free Rounds = ~3 strane

**Prototipi:** Prototip_Billing_konsolidovano, R2_plan_racionalizacije

### R3 - Tracking Platform Final  [DONE]  (C3P, 17 strana)

**Plan:** Objedinjeno Tracking/Retention/Sessions (6->1, isti skelet) + arhiva/dedup. Veljkov mehanizam: R3 <-> DataSet isti semanticki model.

| Akcija | Sadrzaj | Kuda |
|---|---|---|
| MERGE | Game/Company/Market Tracking + Game/Operator Retention + Players Sessions (6->1) | Objedinjeno (Dimenzija + Measure-grupa + Prateci grafik) |
| PREBACI | Promotions Tracking | -> Promo modul |
| PREBACI | New Game Since Launch | -> R12 (DataSet) |
| ARHIVA | Growth Tracking | -> arhiva (potvrditi) |
| PREBACI | System Health | -> Support |
| DEDUP | Accounting Dashboard | -> ostaje R4 (AM verzija, 126 pregleda) |

**Sta ostaje na kraju:** Objedinjeno + Operator Tracking (time-pivot) + Variable RTP + Traffic By Country + Customer Segmentation + Player Details (access-ctrl) + Basis of Presentation = ~7 strana

**Prototipi:** Prototip_Tracking_objedinjeno, R3_plan_racionalizacije

### R4 - Tracking Platform AM  [PLAN]  (C3P, 6 strana)

**Plan:** R4 OSTAJE zaseban AM report sa 4 strane (preuzima najkoriscenije AM strane; R3 dupove brise). AM aktivno koristi: Accounting 126 / Sessions 102 / Player Details 91.

| Akcija | Sadrzaj | Kuda |
|---|---|---|
| KEEP | Accounting Dashboard | ostaje R4 (AM home); R3 dup se brise |
| KEEP | Players Sessions | ostaje R4 (AM) + R3 lens objedinjene (na oba) |
| KEEP+CTRL | Player Details | ostaje R4 (access-ctrl/RLS) + R3 za BI (na oba) |
| KEEP | Basis of Presentation | ostaje (ne smeta) |
| PREBACI | New Game Since Launch | -> R12 |
| SKLONITI | System Health | -> Support (dedup) |

**Sta ostaje na kraju:** R4 ostaje zaseban report sa 4 strane: Accounting Dashboard + Players Sessions + Player Details (RLS) + Basis of Presentation.

### R5 - Support  [PLAN]  (C3P, 10 strana)

**Plan:** R5 postaje tanak OPERATIONAL/Support report. Support-distinktivno ostaje; dupli R1 trend strane se arhiviraju. Poklapa se sa Blueprint kategorijom Operational.

| Akcija | Sadrzaj | Kuda |
|---|---|---|
| KEEP | System Health | dom operativnog monitoringa (dedup iz R1/R3); moze push alert (Slack/mejl) |
| KEEP | DOD Operator Alert | anomalija / DARR alert |
| KEEP | Monthly/Daily (support-lens) | negativni GGR + RTP anomalije (support fokus) |
| ARHIVA | Market/Operator/Game Trend, Game Details, Portal/Game analysis, DOD | dupli R1 -> support koristi R1/konsolidovani Trend (Nora+Veljko) |

**Sta ostaje na kraju:** R5 = tanak Operational/Support report (~3-4 strane): System Health + DOD Operator Alert + negativni-GGR/RTP monitoring.

### R6 - Business Overview  [DONE]  (C3P, 5 strana)

**Plan:** R6 se RASTVARA - nije vise zaseban report. Exec strane -> Management Report (novi).

| Akcija | Sadrzaj | Kuda |
|---|---|---|
| MERGE | Daily Report + Business Overview | -> Management Report (novi) |
| KEEP | Budget Planning Tracker | ostaje, revitalizovati 2026 (jedini plan-vs-actual, veze ERP) |
| PREBACI | New Games | -> R12 |
| DEDUP | New Business | -> jedan home (New Casinos) |

**Sta ostaje na kraju:** Rastvara se: Management Report (exec) + Budget Planning Tracker (revitalizovan). 0 zasebnih strana.

**Prototipi:** Prototip_Management_Report, R6_plan_racionalizacije

### R7 - Promotions Preview AM  [PLAN]  (C3P, 1 strana)

**Plan:** POSTAJE Promo modul (home). R7 se prosiruje: ima vec Schedule (Gantt) + Performance po AM; dodaju se Billing/TBP (iz R11.10) i Register (iz R2). Promo strane sa R2/R3/R9/R11 se slivaju ovde. AM aktivno koristi -> ne menja se navika.

| Akcija | Sadrzaj | Kuda |
|---|---|---|
| PROSIRENJE | R7 -> Promo modul (home) | + Billing/TBP (R11.10) + Register (R2 Promotions) |
| PRIMA | promo strane | <- R2 Promotions, R3 Promotions Tracking, R9, R11 Promo/TBP |

**Sta ostaje na kraju:** R7 postaje Promo modul (4 moda): Schedule + Performance + Billing/TBP + Register. Nije nov report, nego prosiren R7.

**Prototipi:** Prototip_Promo_modul

### R8 - Profit By Integration  [PLAN]  (C3P, 1 strana)

**Plan:** Ostaje - jedina margin mera u portfoliju. Blokada: Profit definicija + vlasnik (recnik).

| Akcija | Sadrzaj | Kuda |
|---|---|---|
| KEEP | Profit by Integration | ostaje; definicija/vlasnik = blokada za resiti |

**Sta ostaje na kraju:** Ostaje 1 strana (jedina margin mera). Ceka definiciju Profit-a.

### R9 - Promotions Tracking Preview  [WAIT]  (C3P, 1 strana)

**Plan:** Promotion profitability -> Promo modul (Performance). Nemam pristup - potvrditi layout.

| Akcija | Sadrzaj | Kuda |
|---|---|---|
| PREBACI | Main page (profitability) | -> Promo modul (potvrditi) |

**Sta ostaje na kraju:** Rastvara se u Promo modul (potvrditi).

### R10 - Competitor Analysis Historical  [PLAN]  (C3P, 3 strana)

**Plan:** NEVALIDAN (korisnicka ocena + sumnja u tacnost podataka) -> arhivirati/brisati.

| Akcija | Sadrzaj | Kuda |
|---|---|---|
| BRISATI | Games, Games Details, Site Details | arhiva (nevalidan) |

**Sta ostaje na kraju:** Arhivira se (nevalidan). 0 strana.

### R11 - New release dashboard  [PLAN]  (Fazi-BI, 16 strana)

**Plan:** Okosnica go-forward. Preraspodela + 2 mini-merge-a + correction-pass (NE merge-away). Risk & Growth engine = osnova Management Report + alarmi.

| Akcija | Sadrzaj | Kuda |
|---|---|---|
| MERGE | GGR forecast daily + monthly (R11.05/06, 2->1) | 1 strana + param daily/monthly toggle |
| MERGE | Struktura prihoda operateri + igrice (R11.11/12, 2->1) | 1 strana + param dimenzija (operateri/igrice) |
| DORADA | Missing games (R11.03) | -> Last Releases Live (prototip gotov) |
| PREBACI | Promo/TBP % (R11.10) | -> Promo modul (Billing/TBP) |
| DEDUP | Client Performance (R11.09) | R14 se gasi (isti); strana ostaje ovde |
| KEEP+CTRL | Pracenje top 250 igraca (R11.04) | access-ctrl / RLS (row-level PlayerId) |
| OSNOVA | Monthly/Daily performance overview (R11.13/14) | Risk & Growth engine -> Management Report + sistem upozorenja |
| KEEP+FIX | ostale strane | correction-pass (Veljko flagovi) |

**Sta ostaje na kraju:** Ostaje okosnica (16 -> ~12 posle 2 mini-merge + 2 odlaska), uz dorade.

**Prototipi:** Prototip_Missing_Games_v2, Prototip_GGR_forecast

### R12 - New Release - Metrics  [PLAN]  (Fazi-BI, 5 strana)

**Plan:** Referentni obrazac. Prima Launch/New Games (iz R3/R6). Baza za Scan-all / Full Launched Report.

| Akcija | Sadrzaj | Kuda |
|---|---|---|
| KEEP | sve strane | referentni obrazac |
| PRIMA | Launch/New Games | <- R3 New Game Since Launch, R6 New Games |
| DORADA | -> Full Launched Report / Scan-all | launch-kohortna matrica (prototip gotov) |

**Sta ostaje na kraju:** Ostaje 5 strana + prima launch strane + osnova za Full Launched.

**Prototipi:** Prototip_Full_Launched_Report

### R13 - Distributivna mreza  [PLAN]  (Fazi-BI, 3 strana)

**Plan:** = Ivica Tab 1+2. Dopune: Other/Rest bucket + live brojevi + unique operators po igri.

| Akcija | Sadrzaj | Kuda |
|---|---|---|
| KEEP+DORADA | Distributivna + Missing operators | dopuna: Other/Rest, live, 15-dnevni OKR prozor |

**Sta ostaje na kraju:** Ostaje 3 strane (uz dopune).

### R14 - Client Performance (MBR & QBR)  [PLAN]  (Fazi-BI, 1 strana)

**Plan:** Duplikat R11.09 -> gasiti kao zaseban report.

| Akcija | Sadrzaj | Kuda |
|---|---|---|
| DEDUP | Main page | -> R11.09 Client Performance (isti) |

**Sta ostaje na kraju:** Gasi se (dup). 0 zasebnih strana.

### R15 - PlayNet_Report_Live  [PLAN]  (Fazi-BI, 7 strana)

**Plan:** Klijent-specifican (Playnet), eksterni pristup -> RLS scope. Ostaje kao klijentski report.

| Akcija | Sadrzaj | Kuda |
|---|---|---|
| KEEP+CTRL | 7 strana | RLS scope pre deljenja (eksterni pristup) |

**Sta ostaje na kraju:** Ostaje 7 strana (klijentski, RLS).

### R16 - Dashboard - Pracenje igrica  [PLAN]  (Fazi-BI, 5 strana)

**Plan:** Mrtvo (0 pregleda, Excel izvor) -> arhivirati.

| Akcija | Sadrzaj | Kuda |
|---|---|---|
| ARHIVA | 5 strana | 0 pregleda |

**Sta ostaje na kraju:** Arhivira se. 0 strana.

## Novi reporti / moduli (cross-report)

| Naziv | Opis | Prototip |
|---|---|---|
| Promo modul (= prosiren R7) | Schedule + Performance + Billing/TBP + Register (4 moda). Zivi NA R7 Promotions Preview AM (nije nov report). Spaja promo iz R2/R3/R9/R11. | Prototip_Promo_modul |
| Management Report | Exec sloj: KPI + period toggle + Markets Risk&Growth + Business Overview. Spaja R6 Daily+Business Overview + R2 Business Overview + R1 -4/5 exec. | Prototip_Management_Report |
| Navigation Hub | Centralni ulaz (6 kategorija, BRAGG-stil). NOVO - nedostaje. | - |
| Last Releases Live / Missing Games | Dorada R11.03: sort po velicini + poslednja igra prva + brojevi (0=crveno) + Top 30 mod. | Prototip_Missing_Games_v2 |
| vRTP alat | R3.16 baza: per-operater RTP + simulator efekta snizavanja RTP na GGR (elasticnost). | Prototype_vRTP_Tool_v2 |
| Full Launched Report / Scan-all | Launch-kohortna matrica (igra x period od lansiranja); Bet/Rounds/GGR; trend+sparkline. | Prototip_Full_Launched_Report |

## Otvorena pitanja / blokade

- F-01: DoD podaci nepouzdani -> blokira DARR familiju (Nemanja).
- Custom Period Top N: Veljko needed+correction vs Mladen nevalidan -> presuditi.
- 3 konflikta recnika: ARPU / RTP / Days Since Launch -> presuditi (Mladen + Veljko/Nemanja).
- New Business / New Casinos (R1/R2/R6): uskladiti kanonsku definiciju pre dedup-a.
- Profit (R8) definicija + vlasnik.
- R9 nema pristup - potvrditi layout (-> Promo modul).
- Performanse: report puca bez filtera -> default filter obavezan na konsolidovanim stranama.