# MEDBAY INDEX (CZ)

## Účel

Tento soubor slouží jako navigační vrstva MedBay repozitáře.
Definuje, jak systém číst, vstupovat do něj a jak se v něm orientovat.

MedBay není sbírka dokumentů.
Je to strukturovaný systém s více vstupními body.

---

# VSTUPNÍ BODY (JAK ČÍST REPOZITÁŘ)

## 1. Přehled systému (začít zde)

ARCHITECTURE.cs.md
- definuje celkovou strukturu systému
- základní koncepty MedBay
- hranice a principy systému

---

## 2. Definice produktu

MEDBAY_PRODUCT_ARCHITECTURE.cs.md
- definuje MedBay jako fyzický + softwarový produkt
- modulární all-in-one medicínský systém
- ambulance / nemocnice / mobilní varianty

---

## 3. Hardware struktura

MEDBAY_HARDWARE_ARCHITECTURE.cs.md
- senzory, moduly, zařízení
- bezpečnostní vrstvy
- fyzické nasazení systému

---

## 4. Klinické chování (reálné použití)

MEDBAY_SCENARIO_CHEST_PAIN_AMBULANCE.cs.md
- kompletní akutní workflow
- rozhodování v reálném čase
- interakce AI, zařízení a člověka

---

## 5. Ekosystém

GitHubMedicalCommunityLinks.cs.md
- open-source medicínský ekosystém
- kandidáti na moduly
- AI / imaging / robotika / nemocniční systémy

---

# STRUKTURA SYSTÉMU

MedBay se skládá z pěti vrstev:

1. Klinická vrstva
   - pacientské workflow
   - triáž
   - akutní protokoly

2. AI rozhodovací vrstva
   - analýza
   - doporučení
   - rizikové skóre

3. Vrstva zařízení
   - senzory
   - zobrazování
   - terapeutické moduly

4. Produktová vrstva
   - nemocniční jednotka
   - ambulantní jednotka
   - mobilní jednotka

5. Ekosystémová vrstva
   - externí open-source moduly
   - standardy (DICOM, HL7, FHIR)

---

# JAZYKOVÁ STRUKTURA

- .md = anglická technická verze
- .cs.md = česká komunikační verze

Angličtina je zdroj pravdy pro vývoj.
Čeština je vysvětlovací vrstva.

---

# PRINCIP NAVIGACE

Pokud se v systému ztratíš:

Vrať se sem.

Pak si vyber směr:
- systém
- produkt
- hardware
- klinický scénář
- ekosystém

MedBay je záměrně vrstvený systém, ne plochá dokumentace.