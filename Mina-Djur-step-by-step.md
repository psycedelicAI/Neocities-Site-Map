# Mina Djur — uppdateringsplan

**Arbetsläge:** 10 november 2026  
**Pilot:** `pages/02.html`  
**Mål:** Engelska som standardspråk, redigerbart innehåll och gemensamma inställningar — utan att bryta produkt-, SKU- eller kundvagnsflödet.

> Gör ändringar stegvis. Spara filerna som UTF-8, behåll tekniska nycklar och sökvägar och testa efter varje ändringsgrupp.

---

## Avklarat

- [x] En backup av sajten har tagits.
- [x] `site-loader.js` är redan kopplad till `02.html`.
- [x] Startsidan har kopplats till `content.txt`:
  - `content.js` laddas från `index.html`.
  - Startsidan är märkt med `data-content-page="00"`.
  - Bloggstartsidan använder sina `00`-fält i `content.txt`.
  - Uppdateringen har bekräftats fungera direkt.
- [x] Valutabeslutet är taget: sajten ska **inte** räkna om valutakurser. Sajten visar beloppet i den valda valutan; betaltjänsten hanterar betalning och eventuell omräkning.
- [x] Översättningsutkast har tagits fram här för bland annat `02.html`, produktdata och flera innehålls-/inställningsfiler. Utkast är inte automatiskt samma sak som uppladdat och testat innehåll.
- [x] Förslag till automatiskt klickbara länkar i bloggtexter och CSS-stil för dem har tagits fram. Installation och test är inte bekräftade.

---

# Del 1 — Slutför pilot på sida 02

## 1. Kontrollera filkopplingarna

- [ ] Kontrollera den aktuella `content.js` och att dess innehållsfilväg stämmer med filen som faktiskt finns på sajten.
- [ ] Bestäm ett enda kanoniskt namn för informationskortets textfil. Både `content-about.txt` och `products-about.txt` har förekommit:
  - välj vilken fil som ska användas;
  - ändra JavaScript eller filnamn så att de stämmer överens;
  - ta inte bort den äldre filen förrän kopplingen är testad.
- [ ] Kontrollera att `site-loader.js` laddar rätt version av `content.js` på sida 02, inklusive `content.js?v=6` om det är den aktuella versionen.
- [ ] Kontrollera att `palette-master.js` använder de fyra aktuella custom/default-paletterna och inte längre begär de gamla säsongs-/högtidsfilerna.
- [ ] Hårdladda `02.html` och kontrollera konsolen för felaktiga eller gamla TXT-sökvägar. Saknade bildkandidater kan ge separata 404-fel om filerna inte finns.

## 2. Gör klart sidans engelska texter

- [ ] Lägg in och granska den engelska versionen av hela `02.html`.
- [ ] Sätt sidans språk till:

  ```html
  <html lang="en">
  ```

- [ ] Översätt all besökarvänd text: rubriker, beskrivningar, knappar, menyfallbacks och tillgänglighetstexter.
- [ ] Behåll sökvägar, ID:n, klasser, `data-*`-attribut och produkt-/SKU-logik oförändrade.
- [ ] Kontrollera att den synliga sidtexten verkligen är engelsk efter uppladdning.

## 3. Slutför datafilerna för sida 02

- [ ] `identity.txt`: kontrollera varumärkes- och menynamn. Behåll **Mina Djur** tills du beslutar om namnbyte.
- [ ] `content.txt`: lägg in rätt engelska introduktionstexter för sida 02.
- [ ] Den valda informationskortfilen: lägg in engelska texter för produktinformationen.
- [ ] `Store020.txt`: kontrollera namn, beskrivningar, varianter och färger.
- [ ] Behåll produkt-ID:n, antal fält, avgränsare, priser, vikter och bildprefix.
- [ ] Säkerställ att färgvärden i `Store020.txt` stämmer exakt med färgnamnen som SKU-/variantkoden förväntar sig. Engelska färgnamn får inte göra så att färgval eller SKU slutar matcha.

## 4. Lägg till inställningar för produktgränssnittet

Skapa eller utöka en central inställningsfil för de generella texter som fortfarande kommer från JavaScript. Föreslaget filnamn: `settings/store-settings.txt`.

- [ ] Lägg redigerbara engelska UI-texter där, till exempel:
  - storleks- och färgval;
  - knapptexten “Add to Cart”;
  - fraktviktslabel;
  - SKU-hjälptext;
  - produktladdningens status- och felmeddelanden.
- [ ] Uppdatera berörda JavaScript-filer så att de läser texterna från inställningen i stället för att ha svenska strängar hårdkodade.
- [ ] Kontrollera särskilt produktens etikett/rubrik, exempelvis “Vila & bäddar 02 — Produkt 01”, och gör den redigerbar eller bygg den från redan redigerbara sidnamn och produktplats.

## 5. Lägg till en enkel valutainställning — ingen valutaväxling

- [ ] Lägg till valutakod och format i den gemensamma butiksinställningen, exempelvis:

  ```text
  CURRENCY_CODE=SEK
  CURRENCY_LOCALE=sv-SE
  ```

- [ ] Låt priserna i produktfilerna vara vanliga numeriska värden i den valuta som inställningen anger.
- [ ] Formatera samma valuta konsekvent på produktkort, varianter, rabatter, kundvagn och orderunderlag.
- [ ] Om butiken byter från SEK till USD eller EUR ska ägaren själv sätta produktpriserna i den nya valutan. Ingen växelkurs eller automatisk omräkning ska läggas in i webbplatsen.
- [ ] Säkerställ att den valda valutan även anges i orderunderlaget. Betaltjänsten hanterar själva betalningen och eventuell omräkning.

## 6. Testa pilotens funktioner

- [ ] Kontrollera att produktkort, bilder och galleri visas.
- [ ] Kontrollera storleks- och färgval samt knappar och statusmeddelanden på engelska.
- [ ] Kontrollera produktbeskrivning och informationskort.
- [ ] Kontrollera SKU för riktiga, icke-demovarianter.
- [ ] Kontrollera priser och totalsumma i vald valuta.
- [ ] Kontrollera fraktberäkningen.
- [ ] Kontrollera att kundvagn och orderunderlag visar samma belopp och valuta.
- [ ] Testa att ordermejlet öppnas med rätt information.
- [ ] Kontrollera Console och Network efter JavaScript-fel, 404-fel och gamla TXT-anrop.

---

# Del 2 — Rulla ut engelska på resten av webbplatsen

Gå vidare först när pilotens produktflöde och innehåll fungerar.

## Föreslagen ordning

1. `index.html` — slutför kvarvarande fasta gränssnittstexter; bloggstartsidan är redan kopplad till `content.txt`.
2. `pages/01.html`
3. `pages/03.html`–`pages/06.html`
4. `pages/07.html` och `pages/08.html`
5. `pages/09.html` och affiliateinnehållet
6. `pages/10.html`
7. `pages/information.html`
8. `not_found.html` — redan på engelska; granska främst varumärkestexten.

## För varje sida

- [ ] Översätt all besökarvänd HTML-text och sätt `lang="en"`.
- [ ] Översätt motsvarande innehålls- och produktdatafiler.
- [ ] Behåll tekniska nycklar, ID:n, fältkoder, avgränsare, sökvägar och SKU-relevanta värden.
- [ ] Kontrollera gemensam navigation och sidnamn från `identity.txt`.
- [ ] Hårdladda sidan och testa layout, bilder, länkar och relevanta funktioner.
- [ ] Gå inte vidare till nästa grupp förrän den aktuella gruppen är verifierad.

---

# Del 3 — Gör färg- och storlekskoder för SKU redigerbara

- [ ] Skapa `settings/product-color-codes.txt` med mappningar mellan färgnamn och SKU-koder.
- [ ] Skapa `settings/product-size-codes.txt` med mappningar mellan storleksnamn och SKU-koder.
- [ ] Använd tydligt och konsekvent format, till exempel:

  ```text
  Light Blue|LJBL
  Transparent|TRAN
  ```

- [ ] Begränsa SKU-koderna till högst fyra tecken från engelska alfabetet A–Z.
- [ ] Kontrollera att varje variantnamn i Store-filerna matchar en inställningsrad exakt och att koderna inte krockar.
- [ ] Behåll den befintliga SKU-kodningen och SKU-formatet; ändra inte befintliga SKU-resultat utan ett uttryckligt beslut.
- [ ] Uppdatera `product-sku.js` så att den läser båda TXT-filerna i stället för att ha färg- och storlekslistorna hårdkodade.
- [ ] Kontrollera aktuell `cart.js`. Ändra den bara om den aktuella versionen har en egen variant-/SKU-mappning i stället för att använda den gemensamma SKU-generatorn.
- [ ] Testa vanliga storlekar och färger samt den valda demofärgen, exempelvis `Transparent|TRAN`.
- [ ] Kontrollera att samma SKU följer med från produktsidan till kundvagnen och orderunderlaget.

---

# Del 4 — Gör ordermejlets mottagare redigerbar

- [ ] Lägg till separata `BUSINESS_EMAIL` och `ORDER_EMAIL` i `settings/information-settings.txt`, exempelvis:

  ```text
  BUSINESS_EMAIL=contact@shop.com
  ORDER_EMAIL=orders@shop.com
  ```

- [ ] Uppdatera `order-email.js` så att mottagaren hämtas från `ORDER_EMAIL` i inställningsfilen, inte från en hårdkodad adress.
- [ ] Behåll kontaktadressen och ordermottagaren som separata värden; de kan vara samma eller olika.
- [ ] Kontrollera att `site-loader.js` laddar den uppdaterade `order-email.js`.
- [ ] Ändra mottagaradressen tillfälligt och verifiera att ett nytt ordermejl riktas till den nya adressen.
- [ ] Bekräfta att ändringen bara påverkar mottagare för nya mejl; den skapar inte orderstatus eller automatisk vidarebefordran.

---

# Del 5 — Bloggförbättringar som återstår att verifiera

- [ ] Installera den föreslagna uppdateringen av `index-blogg.js` som gör `http://`, `https://` och `www.`-adresser klickbara.
- [ ] Uppdatera skriptets cacheversion i `index.html` till `index-blogg.js?v=2`.
- [ ] Lägg till den föreslagna CSS-stilen för blogg-URL:er så att de blir tydligt understrukna och fetstilta.
- [ ] Testa länkar med skiljetecken efter URL:en och kontrollera att de öppnas säkert i en ny flik.

---

# Avslutande dokumentation

- [ ] Uppdatera settings-indexet/README:n med de nya eller utökade inställningarna och vad de styr.
- [ ] Dokumentera valuta som vald prisvaluta, utan växelkurs eller omräkning i webbplatsen.
- [ ] Dokumentera filformat, tillåtna värden och vilka JavaScript-filer som läser respektive inställning.
- [ ] Testa en sista gång efter dokumentations- och cacheversionsändringar.

---

## Nästa praktiska stoppunkt

Red ut filnamnet för informationskortet och få `02.html` helt testad. Därefter tar vi de gemensamma produktgränssnitts- och valutainställningarna innan vi rullar vidare på fler sidor.
