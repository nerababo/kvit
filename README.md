# Kvit

**Besplatne fakture, predračuni i ponude za firme i obrte u Bosni i Hercegovini.**
Free, open source invoicing for small businesses in Bosnia and Herzegovina.

Kvit je jedan HTML fajl. Nema servera, nema registracije, nema pretplate. Svi podaci (firma, klijenti, proizvodi, fakture) ostaju u pregledniku korisnika.

## Mogućnosti

- **Drag & drop:** prevucite proizvod ili uslugu na fakturu, prevucite klijenta na polje „Kupac“, mijenjajte redoslijed stavki prevlačenjem, a stavku uklonite tako što je vratite u lijevi panel
- **Uvoz iz Excela:** ispustite CSV fajl na fakturu i sve stavke se dodaju odjednom
- Faktura, predračun i ponuda
- Automatski broj dokumenta, PDV po stopama, rabat po stavci
- Iznos slovima („dvije hiljade … KM i 50/100“)
- Podrška za firme izvan sistema PDV-a
- Arhiva s pregledom: fakturisano, naplaćeno, otvoreno, kasni
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

- **Podaci su samo u pregledniku.** Ako se obrišu podaci preglednika, brišu se i fakture. Izvoz i uvoz sigurnosne kopije je na planu razvoja.
- **Fiskalizacija i e-faktura:** Kvit trenutno nije povezan s fiskalnim sistemom. Novi Zakon o fiskalizaciji u FBiH uvodi obaveznu e-fakturu preko platforme Porezne uprave. Provjerite s računovođom šta važi za vašu djelatnost.
- Kvit nije pravni ni računovodstveni savjet.

## Plan razvoja

- [ ] Izvoz u PDF
- [ ] Sigurnosna kopija (izvoz i uvoz JSON fajla)
- [ ] Avansna i storno faktura
- [ ] Ponavljajuće fakture
- [ ] Izvještaji i KIF u Excelu
- [ ] Opcionalna sinhronizacija između uređaja
- [ ] Integracija e-fakture (FBiH)

## Doprinos

Prijave grešaka i prijedlozi su dobrodošli kroz Issues. Za veće izmjene prvo otvorite Issue da se dogovorimo.

## Licenca

[MIT](LICENSE)
