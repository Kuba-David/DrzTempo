# Drž tempo 🏋️

Minimalistická webová appka na jedinou věc: **dokopat se pravidelně do gymu.**

Žádné počítání kalorií, žádné výkonnostní tabulky. Jediná otázka zní: *dokopal ses tam?*
Když ano, orazítkuješ si den v kalendáři a držíš tempo.

![Drž tempo – screenshot](docs/screenshot.png)

## Co umí

- 📅 **Kalendář docházky** — kliknutím orazítkuješ den, kdy ses ukázal. Tréninkové dny jsou zvýrazněné, návštěva mimo plán se počítá jako bonus (+).
- ⚙️ **Nastavitelné tréninkové dny** — v nastavení (kolečko vpravo nahoře) si vybereš, které dny v týdnu cvičíš — klidně dva, klidně pět. Kalendář, streak i plány se přizpůsobí. Výchozí: Út · Čt · Ne. **Změna platí od dneška** — appka si pamatuje historii rozvrhu a minulost hodnotí podle rozvrhu platného v daný den, takže změna dnů nikdy nerozbije nastřádaný streak.
- 🔥 **Tempo (streak)** — počítá tréninky v řadě podle plánovaných dnů a povzbuzuje hláškami.
- 📝 **Choreografie pro každý den zvlášť** — každý tréninkový den má vlastní plán (Den A, Den B, …). Cviky přepíšeš, přeskládáš, doplníš — a když chceš všude stejný plán, jedním tlačítkem ho zkopíruješ do všech dnů. Plán vypnutého dne se neztrácí; po opětovném zapnutí dne se vrátí.
- 🔎 **Našeptávač cviků** — při psaní názvu cviku se přímo ve stránce otevře nabídka ~40 nejběžnějších cviků (dřepy, mrtvé tahy, přítahy, tlaky, core…), hledá i bez diakritiky; vybraný cvik rovnou předvyplní série × opakování a poznámku k technice.
- 📓 **Deník poznámek** — ke každému dni si uložíš postřeh z tréninku (váhy, pocity, co šlo a co ne). Poznámku otevřeš dlouhým podržením dne v kalendáři (na počítači i pravým tlačítkem), tlačítkem „+ Dnešek“ v sekci Deník, nebo ťuknutím na starší záznam v Deníku — všechny poznámky jsou tam chronologicky pod sebou, žádné listování kalendářem. Dny s poznámkou mají v kalendáři tečku.
- 🎨 **5 barevných témat** — Parket (tmavé), Sál (světlé), Vínová, Antracit a Námořní; při prvním spuštění se appka řídí nastavením systému.
- 💾 **Záloha a obnova** — data žijí jen v prohlížeči (localStorage), jedním klikem je vyexportuješ do JSON souboru a kdykoli zase nahraješ (třeba na novém telefonu).
- 📴 **Funguje offline** — po první návštěvě se appka uloží do cache (service worker) a jede i bez internetu.
- 📱 **Dá se nainstalovat** — na telefonu přes „Přidat na plochu“ se chová jako nativní appka.

## Jak to rozjet

Appka je čistě statická — žádný build, žádné závislosti.

**GitHub Pages (doporučeno):**
1. V repozitáři otevři **Settings → Pages**.
2. V sekci *Build and deployment* zvol **Deploy from a branch**, vyber hlavní větev a složku `/ (root)`.
3. Za chvíli appka poběží na `https://kuba-david.github.io/DrzTempo/`.
4. Na telefonu ji otevři v prohlížeči a dej **Přidat na plochu** — od té chvíle funguje i offline.

**Lokálně:** stačí otevřít `index.html` v prohlížeči. (Bez serveru nefunguje jen offline cache — na samotnou appku to nemá vliv.)

## Kde jsou moje data

Všechno (razítka, cviky, téma) se ukládá **jen lokálně v prohlížeči**. Nikam se nic neposílá.
Proto se hodí občas kliknout na **„zálohovat data“** dole na stránce — a při výměně telefonu zálohu nahrát přes **„obnovit zálohu“**.

## Struktura

| Soubor | K čemu je |
|---|---|
| `index.html` | celá appka (HTML + CSS + JS v jednom) |
| `manifest.webmanifest` | manifest pro instalaci na plochu |
| `sw.js` | service worker pro offline režim |
| `icons/` | ikony appky |
