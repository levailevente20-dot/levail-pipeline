# Napi pipeline app — spec

## Háttér
A videó (Evan Carmichael: "How to Make Money FAST | Lessons from Billionaires")
20 törvénye és az 5 lépéses életterv-módszer alapján összeállított akcióterv
napi/heti szokásokra bontva. A cél: egy egyszerű **napi pipeline / checklist app**,
ahol nem percre pontos időbeosztás van, hanem kipipálható napi tételek,
kategóriánként.

## Fő kategóriák és tételek

### 1. Vállalkozás (napi ~6 óra, de nem időzített — 3 al-tétel)
- [ ] Hideg hívás
- [ ] Felkészülés / előkészítő munka
- [ ] Telefonszám-gyűjtés — **heti cél: 4-5 óra**, nem napi kötelező tétel,
      hanem heti szinten követett, elosztható a napok között

### 2. Trade
- [ ] Napi trade-block (elemzés + végrehajtás) — cél: ~2 óra/nap

### 3. Mozgás
- [ ] Kondi — **heti 4 nap**
- [ ] Pihenőnap — **heti 3 nap** (aktív pihenő, nem kihagyható tétel, hanem
      tudatosan betervezett nap)

### 4. Étkezés
- [ ] Reggeli
- [ ] Ebéd
- [ ] Vacsora

### 5. Szokások (a videóból)
- [ ] Reggeli fókusz-rutin (rövid meditáció / tudatos kezdés)
- [ ] Napi tanulás / szakmai olvasás (min. 15-30 perc)
- [ ] Napi/heti cash flow áttekintés (Bezos-elv)
- [ ] Journaling / napi zárás, holnapi terv
- [ ] Heti vízió-átnézés (hétvégén)
- [ ] Heti pénzügyi áttekintés (hétvégén)
- [ ] Havi: profit visszaforgatás átgondolása, mentor/network kapcsolattartás

## App-koncepció

**Típus:** egyszerű napi checklist / pipeline tracker, heti nézettel.

**Nem kell:**
- Percre pontos időzítés
- Naptár-integráció (egyelőre)

**Kell:**
- Napi nézet: az adott nap tételei kipipálhatók
- Heti nézet: áttekintés, hogy mely napokon mi van kipipálva
- Heti aggregált célok követése (pl. telefonszám-gyűjtés 4-5 óra/hét,
  kondi 4x/hét, pihenőnap 3x/hét) — ezek nem napi checkbox, hanem heti
  progress bar / számláló
- Streak / konzisztencia mutató (hány napja pipálod ki folyamatosan)
- Adatmentés (perzisztencia) — helyi tárolás elegendő egyelőre

## Kategória-szín javaslat (a korábbi vizuális tervből)
- Vállalkozás — lila
- Trade — kék
- Mozgás — zöld
- Étkezés — sárga/amber
- Szokások — türkiz

## Következő lépés
Ezt a specifikációt Claude Code-ban folytatva egy webes/app felület épül belőle
(napi checklist + heti összesítő nézet).
