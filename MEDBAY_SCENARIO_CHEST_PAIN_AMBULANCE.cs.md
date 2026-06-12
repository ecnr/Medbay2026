# KLINICKÝ SCÉNÁŘ: BOLEST NA HRUDI – SANITNÍ MEDBAY (CZ)

## Účel scénáře

Tento dokument popisuje typickou akutní situaci, kdy je MedBay nasazen v sanitní verzi a řeší pacienta s bolestí na hrudi.

Nejde o medicínský návod.
Jde o popis chování systému MedBay v reálném čase.

---

## Vstupní situace

Pacient je převzat do sanitního MedBay s příznaky:
- bolest na hrudi
- dušnost
- zhoršený celkový stav

Stav může být:
- stabilní
- hraniční
- akutně ohrožující

---

## Inicializace systému

Po převzetí pacienta MedBay:

1. aktivuje senzorický režim
2. sbírá vitální data
3. vytváří počáteční rizikový profil
4. synchronizuje data s AI rozhodovací vrstvou

---

## Triage (automatické třídění)

AI vyhodnocuje:
- pravděpodobnost akutního ohrožení života
- potřebu okamžitého zásahu
- nutnost transportu do nemocnice

Systém pracuje s pravděpodobnostními modely, ne s jedním pevným závěrem.

---

## Režim autonomie

Rozhodování se řídí stavem pacienta:

### 1. Akutní ohrožení / bezvědomí
- vyšší míra autonomie MedBay
- systém může navrhnout nebo spustit stabilizační kroky

### 2. Vědomý pacient
- vyžaduje informovaný souhlas
- AI funguje jako podpora rozhodování

---

## Koordinace zařízení

MedBay koordinuje dostupné moduly:
- monitorování vitálních funkcí
- zobrazovací a diagnostické systémy
- stabilizační nástroje (dle konfigurace)

Cílem je stabilizace pacienta do bezpečného stavu pro další péči.

---

## Rozhodovací logika

AI nepracuje jako jedno rozhodnutí.
Funguje jako:
- vyhodnocení rizik
- simulace scénářů
- návrh prioritních kroků

Finální režim závisí na nastavení autonomie a klinických pravidlech.

---

## Přechod do nemocniční péče

Pokud stav pacienta vyžaduje další zásah:
- MedBay připraví data pro nemocnici
- předá strukturovaný klinický výstup
- umožní plynulý přechod péče

---

## Designový význam scénáře

Tento scénář slouží jako referenční model pro:
- návrh AI rozhodování
- integraci senzorů
- testování autonomních režimů
- návrh sanitní konfigurace MedBay

---

## Shrnutí

Sanitní MedBay není náhrada lékaře.
Je to systém, který:
- zrychluje reakci
- strukturuje data
- podporuje rozhodování
- umožňuje škálovat akutní péči