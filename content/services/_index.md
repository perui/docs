---
title: Services
---

__TODO: hur sätter man upp en tjänst. länka till repo för service__

## Flöde

När en användare vill använda en tjänst sker det genom ett antal steg. Flera av dessa är osynliga för användaren och, om Tjänsten använder använder befintliga kodbibliotek, ingenting som Tjänstens systemutvecklare ser då de sker i bakgrunden. Flödet för anslutning till en tjänst, medgivande för dataläsning/-skrivning och uppdateringar beskrivs här översiktligt och på djupet (för den som är intresserad).

### För användaren

1. Användaren går in på en Tjänst och erbjuds registrera sig/logga in med Egendata. Detta sker genom att antingen scanna en QR-kod med Egendata-appen eller, om hen använder mobilen, klicka på en länk.

2. Egendata-appen frågar användaren om hen vill logga in om registrering redan har skett, eller skapa en relation med Tjänsten om detta är första besöket. Användaren får, i det senare fallet, även möjligheten att godkänna Tjänstens begäran om att läsa/skriva data.

3. När användaren har svarat, än hen inloggad på Tjänsten och kan börja använda den.

### Så här går det till i bakgrunden

1. Tjänsten presenterar en länk, vilken också kodas som en QR-kod. Länken beskriver tjänsten med id för tjänsten och ett sessionsid för att kunna koppla svaret till rätt användarsession. All information är signerad med tjänstens signeringsnyckel.

2. Egendata-appen kontaktar tjänsten och begär signeringsnyckeln. Den verifierar sedan informationen.

3. Egendata-appen kontrollerar om användaren och tjänsten redan har en relation eller om en sådan måste skapas.
