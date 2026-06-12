# ARCHITEKTURA MEDBAY (CZ)

## Účel systému

MedBay je modulární medicínský systém, který kombinuje:
- klinické rozhodování
- umělou inteligenci
- fyzická zařízení
- nemocniční workflow

Cílem není nahradit nemocnici, ale rozšířit její kapacitu, dostupnost a rychlost zásahu.

---

## Základní princip

- 1 zařízení = 1 pacient v 1 okamžiku
- více pacientů = více paralelních jednotek MedBay

Systém se škáluje horizontálně, ne vertikálně.

---

## Hlavní vrstvy systému

### 1. Klinická vrstva
- příjem pacienta
- triáž
- klinické protokoly
- akutní rozhodování

### 2. AI rozhodovací vrstva
- analýza dat pacienta
- vyhodnocení rizik
- návrh postupu
- podpora nebo autonomní rozhodnutí dle režimu

Autonomie je řízena stavem pacienta:
- bezvědomí / akutní ohrožení = vyšší autonomie
- vědomý pacient = informovaný souhlas

---

### 3. Vrstva zařízení
- senzory
- diagnostické moduly
- terapeutické nástroje
- chirurgické a intervenční nástroje (dle konfigurace)

---

### 4. Produktová vrstva
- sanitní MedBay
- nemocniční MedBay
- mobilní / krizový MedBay

---

### 5. Ekosystémová vrstva
- integrace externích open-source modulů
- standardy (DICOM, HL7, FHIR)
- výměna dat s nemocničními systémy

---

## Mobilita systému

MedBay může existovat jako:
- nemocniční jednotka
- sanitní jednotka
- mobilní krizové pracoviště (např. autobus)

Cílem je přesunout část zdravotní péče blíže pacientovi.

---

## Designové principy

- minimalizace závislosti na lidské obsluze
- maximální integrace modulů
- jednoduché ovládání (jako tiskárna)
- škálovatelná architektura

---

## Role AI

AI v MedBay:
- asistuje při diagnostice
- navrhuje postupy
- v akutních stavech může jednat autonomně v definovaných mezích

---

## Realita nasazení (Gen 1)

- zdravotnický personál je stále přítomen
- AI je podpůrná i rozhodovací vrstva
- plná autonomie je postupný proces

---

## Cíl architektury

Vytvořit systém, který:
- zvyšuje dostupnost péče
- zrychluje zásah
- standardizuje rozhodování
- učí se z každého zákroku v síti MedBay
