<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/kvit-logo-dark.svg">
  <img src="assets/kvit-logo.svg" alt="Kvit" width="240">
</picture>

# Kvit

**Besplatne fakture, predračuni i ponude za firme i obrte u Bosni i Hercegovini.**
Free, open source invoicing for small businesses in Bosnia and Herzegovina.

Kvit je jedan HTML fajl. Nema servera, nema registracije, nema pretplate. Svi podaci (firma, klijenti, proizvodi, fakture) ostaju u pregledniku korisnika.

## Mogućnosti

- **Drag & drop:** prevucite proizvod ili uslugu na fakturu, prevucite klijenta na polje „Kupac“, mijenjajte redoslijed stavki prevlačenjem, a stavku uklonite tako što je vratite u lijevi panel
- **Uvoz iz Excela:** ispustite CSV fajl na fakturu i sve stavke se dodaju odjednom
- Faktura, predračun i ponuda; ponuda ili predračun jednim klikom postaju faktura
- **Avansna faktura:** napravite je iz predračuna, a na konačnoj fakturi avans se odbija po stopama PDV-a
- **Storno faktura:** pogrešna faktura se ne briše nego stornira, storno dobija sljedeći broj i vezu na original
- Automatski broj dokumenta, PDV po stopama, rabat po stavci
- **Izgled dokumenata:** dugme „Uredi izgled“ – logo, boja, slova, tri gotova predloška (Klasični, Logo u centru, Minimalni), blokovi (logo, firma, dokument, kupac) se premještaju prevlačenjem, položaj ukupnog iznosa i potpisa, uključivanje iznosa slovima i podnožja
- **Kolone po izboru:** meni „Kolone“ sakriva redni broj, jedinicu mjere, količinu, cijenu, rabat ili PDV % na svim dokumentima. Kad je cijena skrivena, iznos stavke se upisuje direktno
- Iznos slovima („dvije hiljade … KM i 50/100“)
- Podrška za firme izvan sistema PDV-a
- Arhiva s pregledom: fakturisano, naplaćeno, otvoreno, kasni
- **Ponavljajuće fakture:** mjesečno, kvartalno, polugodišnje ili godišnje. Kad dođe datum, faktura čeka pri otvaranju Kvita i izdaje se jednim klikom, s obračunskim periodom na fakturi. U nazivu stavke radi `{mjesec}` i `{godina}`
- **Izvještaji:** promet po mjesecima, PDV po stopama, najbolji kupci i dugovanja po kašnjenju (1–30, 31–60, 61–90, preko 90 dana)
- **Excel (.xlsx):** knjiga izlaznih faktura (KIF), promet, PDV, kupci i dugovanja, s pravim datumima i formatom brojeva
- **e-KIF za UIO (.csv):** datoteka e-Isporuke za jedan mjesec, po tehničkom uputstvu UIO (zaglavlje, slogovi isporuka, zbirni slog)
- **PDF:** dugme „PDF / Štampa“ pravi čistu A4 fakturu (u dijalogu odaberite „Sačuvaj kao PDF“)
- **Sigurnosna kopija:** preuzmite sve podatke kao jedan fajl i vratite ih na bilo kojem računaru (kartica „Moja firma“)
- Radi na računaru i mobitelu (na mobitelu se stavke dodaju dugmetom +)

## Pokretanje

Otvorite `index.html` u pregledniku. To je sve.

### Besplatno objavljivanje

Kvit je statična stranica, pa se može besplatno hostati na:

- **GitHub Pages:** Settings → Pages → Deploy from branch → `main` / root
- **Cloudflare Pages** ili **Netlify:** povežite repozitorij, bez build komande, output folder `/`

## Format CSV fajla

Jedna stavka po redu, kolone odvojene tačka-zarezom:

```
naziv;količina;cijena;PDV
Izrada logotipa;1;350;17
Sat konsultacija;4;60;17
```

PDV kolona nije obavezna (zadano 17%). Red zaglavlja se automatski preskače. Primjer: [`primjer-stavke.csv`](primjer-stavke.csv).

## Važne napomene

- **Podaci su samo u pregledniku.** Ako se obrišu podaci preglednika, brišu se i fakture. Redovno preuzimajte sigurnosnu kopiju u kartici „Moja firma“.
- **Fiskalizacija i e-faktura:** Kvit trenutno nije povezan s fiskalnim sistemom. Novi Zakon o fiskalizaciji u FBiH uvodi obaveznu e-fakturu preko platforme Porezne uprave. Provjerite s računovođom šta važi za vašu djelatnost.
- **e-KIF:** napravljen po tehničkom uputstvu UIO za dostavljanje podataka iz knjigovodstvenih evidencija. Kupci s PDV brojem (12 cifara) idu u kolone za obveznike PDV-a, ostali u kolone za lica koja nisu obveznici i u polje 32, 33 ili 34 PDV prijave prema entitetu sjedišta firme. Iznos fakture je sa PDV-om, storno se iskazuje negativnim iznosima, a konačna faktura iznosom umanjenim za avans. Prije prve predaje neka datoteku provjeri vaš računovođa.
- Kvit nije pravni ni računovodstveni savjet.

## Plan razvoja

- [x] Izvoz u PDF
- [x] Sigurnosna kopija (izvoz i uvoz JSON fajla)
- [x] Avansna i storno faktura
- [x] Prilagođen izgled fakture: logo, boje, font i raspored blokova prevlačenjem (drag & drop), uz gotove predloške
- [ ] Ideja: okvir „Podaci za uplatu“ pored ukupnog iznosa i pečat „PLAĆENO“ na plaćenim fakturama
- [ ] Vodič za nove korisnike: kratki interaktivni tutorijal pri prvom pokretanju (unos firme, prva faktura, drag & drop, PDF, sigurnosna kopija)
- [x] Ponavljajuće fakture
- [x] Izvještaji i KIF u Excelu
- [x] e-KIF datoteka za UIO
- [ ] e-KUF (ulazne fakture)
- [ ] Opcionalna sinhronizacija između uređaja
- [ ] Integracija e-fakture (FBiH)

## Doprinos

Prijave grešaka i prijedlozi su dobrodošli kroz Issues. Za veće izmjene prvo otvorite Issue da se dogovorimo.

## Licenca

[MIT](LICENSE)
