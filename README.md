# clever.direct

Statisk sajt utan byggsteg. Ren HTML och en CSS-fil – lägg upp filerna som de är.

## Filer

```
index.html              startsida
funktioner.html         alla funktioner, med ankarlänkar (#webbshop, #bokning …)
priser.html             paket, jämförelsetabell och vanliga frågor
tjanster.html           tjänster: konsulttimme, uppsättning, skräddarsytt, kursportal
kontakt.html            formulär för konto och offert
villkor.html            underlag, måste fyllas i
integritetspolicy.html  underlag, måste fyllas i
404.html                visas automatiskt av GitHub Pages
assets/style.css        allt utseende, alla färger och typsnitt
CNAME                   innehåller clever.direct
.nojekyll               stänger av Jekyll-bearbetning
robots.txt, sitemap.xml
```

## Lägg upp på GitHub Pages

1. Skapa ett nytt publikt repo, t.ex. `clever-direct`.
2. Ladda upp alla filer i repots rot (inte i en undermapp). Antingen via **Add file → Upload files** i webbläsaren, eller:

   ```bash
   git init
   git add .
   git commit -m "Första versionen"
   git branch -M main
   git remote add origin https://github.com/DITT-NAMN/clever-direct.git
   git push -u origin main
   ```

3. **Settings → Pages**: under *Build and deployment* väljer du Source `Deploy from a branch`, branch `main`, mapp `/ (root)`. Spara.
4. Fyll i `clever.direct` i fältet *Custom domain* och spara. Filen `CNAME` finns redan, så det ska stämma direkt.

## DNS hos din domänleverantör

För toppdomänen `clever.direct`, fyra A-poster mot GitHubs adresser:

```
A   @   185.199.108.153
A   @   185.199.109.153
A   @   185.199.110.153
A   @   185.199.111.153
```

Vill du ha IPv6 lägger du till fyra AAAA-poster: `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153`.

För `www`, en CNAME-post mot ditt GitHub-namn:

```
CNAME   www   DITT-NAMN.github.io
```

Ta bort eventuell parkeringspost som leverantören lagt in på `@` först. Spridningen tar oftast minuter men kan ta upp till ett dygn. När GitHub visar grön bock, kryssa i **Enforce HTTPS**.

## Innan du publicerar – byt ut det här

- **Citaten** på startsidan är markerade platshållare. Hittade omdömen är otillåten marknadsföring enligt marknadsföringslagen, så antingen riktiga citat eller ta bort sektionen.
- **Priserna** (199 / 449 / 899 kr) och jämförelsetabellen är exempel.
- **Formulären** i `kontakt.html` pekar mot `https://formspree.io/f/DITT-ID`. Byt till ditt eget formulär-ID, eller till din riktiga registreringssida. GitHub Pages kan inte ta emot formulärdata själv.
- **Villkor och integritetspolicy** är rubriklistor, inte färdig text.
- **Sidfoten** behöver bolagsnamn och organisationsnummer.
- **Uppgifter om datalagring, betalsätt och supporttider** i frågorna – skriv bara det som faktiskt gäller.

## Ändra utseendet

Färger och mått ligger överst i `assets/style.css`:

```css
--spruce:#0E3B33;   /* mörk bakgrund i hjältesektion och sidtoppar */
--cobalt:#2B45FF;   /* knappar och accenter */
--sand:#E7D8BC;     /* accent mot mörk bakgrund */
--paper:#ECEFF2;    /* sidbakgrund */
```

Byt värde där så följer hela sajten med. Typsnitten (Bricolage Grotesque, Karla, IBM Plex Mono) hämtas från Google Fonts i första raden av samma fil.
