# TradeIt

**Najam predmeta i opreme od ljudi u blizini.** TradeIt povezuje vlasnike predmeta s osobama kojima su oni privremeno potrebni te objedinjuje pronalazak, dogovor najma, evidenciju stanja i korisničku podršku.

| Podatak            | Vrijednost                                                                |
| ------------------ | ------------------------------------------------------------------------- |
| Naziv aplikacije   | TradeIt                                                                   |
| Naziv tima         | Sibirski plavac                                                           |
| Nastavna grupa     | G03-01                                                                    |
| GitHub repozitorij | https://github.com/LDavorija/tradeit                                      |
| Početak čitanja    | [Dokumentacija](docs/Home.md) |

## Opis aplikacije

Osobi kojoj jednom treba grafički kalkulator, alat ili kamera kupnja može biti nepotrebna, a pronalazak najmodavca zahtijeva dogovor na više mjesta. TradeIt predlaže katalog najma s cijenama i raspoloživosti, dogovorom između korisnika te fotografijama pri preuzimanju i povratu. Očekivana korist je lakša ponovna uporaba predmeta; ušteda vremena, novca ili utjecaj na okoliš još nisu mjereni.

**Trenutačno stanje:** ovaj repozitorij sadrži početnu strukturu i dokumentaciju. `backend/src/app.js` je ogledni Node.js HTTP poslužitelj, a frontend build naredba generira samo stranicu „Frontend App”. Ranije izrađen zasebni frontend nije prenesen u ovaj ZIP. Poslovne funkcije, baza, autentikacija, naplata i AI integracije ovdje još nisu implementirani. [Ograničenja ispitivanja](docs/5-Ispitivanje.md#54-poznati-nedostaci-i-ogranicenja-ispitivanja).

Postupak lokalnog pokretanja i plan postavljanja opisani su u [poglavlju 6](docs/6-Postavljanje-instalacija-i-konfiguracija.md).

<a id="deployment"></a>
## Postavljanje

Javna poveznica na integriranu aplikaciju nije dostavljena. GitHub URL vodi na kod, a ne na pokrenutu aplikaciju. Stvarni URL i ograničenja postavljene inačice dodati nakon provjere.

<a id="quick-start"></a>
## Brzi početak

Za pokretanje **oglednog Node.js poslužitelja** potrebni su Node.js i npm. Iz korijena repozitorija:

```bash
cd backend
npm start
```

Prema kodu poslužitelj koristi port 10000 ili vrijednost `PORT`; `/health` vraća ogledni JSON status. Ova naredba ne pokreće funkcije najma, bazu ni puni frontend. Postupak nije potvrđen kao pokretanje cjelovite aplikacije; [pojedinosti](docs/6-Postavljanje-instalacija-i-konfiguracija.md).

## Tehnologije

| Tehnologija ili alat               | Uloga                                                 | Status i razlog                                                          |
| ---------------------------------- | ----------------------------------------------------- | ------------------------------------------------------------------------ |
| HTML5, CSS, JavaScript             | Zasloni, stilovi, navigacija i lokalne interakcije    | Planirani klijentski dio; raniji dizajn još nije prenesen u ovaj repozitorij              |
| Node.js i npm                | Izvođenje oglednog poslužitelja i naredbi iz predloška                           | Postojeći npm testovi samo ispisuju poruke; jsdom testovi nisu u ovom ZIP-u       |
| Python + FastAPI                   | Planirani HTTP API i poslovna pravila                 | Prijedlog za raspravu; API još nije implementiran                        |
| PostgreSQL                         | Planirana zajednička pohrana i integritet rezervacija | Prijedlog; shema i migracije još nisu primijenjene                       |
| SQLAlchemy + Alembic               | Planirano preslikavanje modela i migracije            | Uvesti uz prvi vertikalni tijek API-ja                                   |
| OAuth/OIDC, Google Maps, AI servis | Planirane prijava, lokacija i provjera oglasa         | Vanjske integracije još nisu povezane; pružatelje i troškovnik potvrditi |
| GitHub + GitHub Actions            | Verzije, pregled promjena i automatizirane provjere   | Repozitorij je naveden; workflow je predložak bez stvarne testne provjere           |

## Struktura

| Lokacija                                       | Namjena                                                                  |
| ---------------------------------------------- | ------------------------------------------------------------------------ |
| `docs/`                                        | Službena poglavlja dokumentacije, zadaci, problemi, sastanci i dokazi    |
| `frontend/package.json`                          | Ogledne build/test naredbe; cjelovit klijentski dio tek treba prenijeti                                               |
| `frontend/src/pages/`, `frontend/src/components/`, `frontend/src/services/`  | Pripremljeni direktoriji za stranice, komponente i API povezivanje                         |
| `frontend/src/assets/`, `frontend/public/` | Mjesta za buduće statičke resurse                                          |
| `backend/src/`                                 | Početni Node.js primjer i direktoriji; predložena Python izvedba još nije dodana |
| `db/`                                          | Mjesto budućih migracija i testnih podataka    |
| `tests/`, `frontend/tests/`                    | Početna struktura za buduće provjere; nema dovršenih poslovnih testova                          |
| `scripts/`, `build/`, `.github/`               | Pomoćne naredbe, izlazi gradnje i CI                                     |

<a id="team-members"></a>

## Članovi tima

Podjela rada preuzeta je iz dostavljenog projektnog dokumenta. R1–R7 povezuju članove s područjima odgovornosti. GitHub profile koji nisu navedeni članovi trebaju dopuniti; pojedinačne izvršene doprinose i sate evidentirati tek nakon rada.

| Član            | Oznaka | Glavna uloga ili doprinos      | Prvi konkretan zadatak                                            |
| --------------- | ------ | ------------------------------ | ----------------------------------------------------------------- |
| Adam Winkler    | R1     | Frontend i UI                  | Povezati katalog s budućim API-jem; provjeriti prikaz na mobitelu |
| Leon Zorko      | R2     | Dokumentacija i koordinacija   | Potvrditi zahtjeve, održavati issues i stvarne zapisnike          |
| Patrik Šinko    | R3     | Baza podataka                  | Model korisnika, oglasa i rezervacija te početne migracije        |
| Pavao Knez      | R4     | Autentikacija i AI             | OIDC prijava, serverske ovlasti; zatim AI provjera oglasa         |
| Viktor Lazić    | R5     | Vanjske usluge                 | Pohrana fotografija i integracija lokacije                        |
| Lukas Davorija  | R6     | API i integracija              | Katalog, ponuda cijene i zahtjev za najam                         |
| Matej Miličević | R7     | Deploy, testiranje i fullstack | CI, razvojna okolina i prvo postavljanje                          |

## Doprinos projektu

Za praćenje zadataka navedena je Jira ploča ispod. GitHub sadrži izvorni kod i dokumentaciju. Predloženo je povezivati promjene sa zadacima i provesti pregled drugog člana prije spajanja; stvarni ritam i pravila tim tek treba evidentirati u [pregledu aktivnosti](docs/A-Pregled-aktivnosti-grupe.md).

Poveznica na JIRU: https://trade-it.atlassian.net/jira/software/projects/SCRUM/boards/1?filter=&groupBy=none

<a id="license"></a>

## Licenca

Za izvorni kod aplikacije tim još nije odabrao licencu za javnu ponovnu uporabu; vidi [LICENSE](LICENSE). Prilagođena dokumentacija slijedi licencu predloška **CC BY-NC-SA 4.0**. Ta licenca ne dodjeljuje automatski licencu aplikacijskom kodu. Licence naknadno dodanih fontova, slika i programskih ovisnosti treba zasebno evidentirati; datoteka LICENSE u ovom ZIP-u odnosi se na dokumentacijski predložak.

<a id="ai-usage"></a>
## Uporaba umjetne inteligencije

ChatGPT/Codex korišten je za nacrt i doradu dokumentacije te ranije za zaseban prijedlog frontenda. Opseg pomoći, provjere i podaci koje članovi još trebaju potvrditi navedeni su u [Home.md](docs/Home.md#izjava-o-uporabi-umjetne-inteligencije). Neovisan pregled tima još nije evidentiran.

<a id="code-of-conduct-and-support"></a>

## Kodeks ponašanja i podrška

Primjenjuju se pravila timskog rada kolegija i priloženi [kodeks ponašanja](CODE_OF_CONDUCT.md). Timski kontakt za podršku još treba dopuniti; nastavne probleme prijaviti kroz službeni kanal kolegija.

---

Struktura dokumentacije prilagođena je [predlošku kolegija Programsko inženjerstvo](https://github.com/VladoSruk/Programsko-inzenjerstvo) autora Vlade Sruka. Izvorni citatni podaci nalaze se u [CITATION.cff](CITATION.cff), a prilagodbe i uporaba AI-ja opisane su u [Home.md](docs/Home.md#izjava-o-uporabi-umjetne-inteligencije).
