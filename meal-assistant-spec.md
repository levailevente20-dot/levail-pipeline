# Pipeline — étkezés-asszisztens spec

A napi agenda-appból személyes napi asszisztens lesz. Első nagy modul: **generatív
étkezés-tervező + kalória/makró-követő** (Yazio-szerű, személyre szabott).

## Döntések (véglegesítve)
- **Generátor:** most helyi JS-algoritmus, később AI. (Az AI kulcsot/backendet igényel,
  ezért külön fázis; a mostani statikus, offline, ingyenes app megmarad.)
- **Követés:** teljes makró — kcal + fehérje + szénhidrát + zsír, adagonként.
- **Kalória-cél:** fix szám, a beállításokban megadva (nincs TDEE-kalkulátor).
- **Batch/maradék:** kézi. A receptnek van „hány adag egy főzés" értéke; a heti terv
  ugyanazt a főételt több napra teheti, a felhasználó pipálja, mikor eszi. Nincs
  automatikus hűtő-leltár.
- **Étkezések/nap:** reggeli / ebéd / vacsora (3 fix).
- **Elrendezés:** új „Étrend" fül (heti terv + étel-adatbázis), ÉS az étel a napi
  agendában is megjelenik (reggel/dél/este) recepttel + kalóriával.
- **Kezdő adatbázis:** néhány magyar példa-étel (közelítő makrók, szerkeszthető).

## Adatmodell (localStorage)
- `pl-targets` — napi cél: `{kcal, p, c, f}` (fix, szerkeszthető).
- `pl-foods` — étel-adatbázis: `{id, name, meals:[reggeli|ebed|vacsora], portionsPerCook,
  perPortion:{kcal,p,c,f}, ingredients:[{name,qty,unit}], recipe}`.
- `pl-mealplan` — napi terv: `{ dateISO: { reggeli:[entry], ebed:[entry], vacsora:[entry] } }`,
  ahol `entry = {foodId, portions, eaten:bool}`.

## Fázisok
1. **Alap (most):** étel-adatbázis kezelése, „Étrend" fül heti kézi tervvel, napi cél a
   beállításokban, étkezés a napi agendában (recept + kcal), napi makró-összesítő
   (cél vs. terv vs. megevett).
2. **Generátor:** a listából automatikus heti reggeli/ebéd/vacsora a célra hangolva,
   batch-főételekkel, változatosan.
3. **Később:** AI-generálás, bevásárló-lista.
