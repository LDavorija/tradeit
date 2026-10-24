# 1. Opseg projekta

## 1.1 Problem i cilj projekta

TradeIt rješava problem pronalaska predmeta koji su korisniku potrebni samo privremeno. Očekivana korist je jednostavniji dogovor najma i veća iskoristivost postojećih predmeta; financijska ili okolišna korist nije izmjerena.

Projekt obuhvaća razvoj web-aplikacije koja korisnicima omogućuje iznajmljivanje i unajmljivanje predmeta koje ne koriste često, ali koji drugim osobama mogu biti potrebni za kratkotrajnu upotrebu. Primjeri takvih predmeta uključuju alate, bicikle, opremu za školu te razne kućanske uređaje. Umjesto kupnje predmeta koji će im možda trebati samo jednom ili nekoliko puta, korisnici ga mogu unajmiti od druge osobe po manjoj cijeni. S druge strane, vlasnici predmeta mogu ostvariti dodatnu zaradu iznajmljivanjem stvari koje bi inače većinu vremena stajale neiskorištene.

Cilj projekta je razviti jednostavnu i preglednu web platformu koja povezuje osobe koje žele iznajmiti svoje predmete s osobama koje ih žele privremeno koristiti. Aplikacija nastoji olakšati pronalazak odgovarajućih predmeta, dogovaranje najma i razmjenu informacija između korisnika, uz poticanje učinkovitijeg korištenja postojećih resursa i smanjenje nepotrebne kupnje.

Ciljana skupina korisnika uključuje pojedince koji žele smanjiti troškove povremenog korištenja različitih predmeta, kao i vlasnike koji žele iskoristiti predmete koje posjeduju, a rijetko koriste. Aplikacija je namijenjena svima koji žele jednostavno ponuditi svoje predmete za najam ili pronaći predmet koji im je potreban na ograničeno vrijeme.

## 1.2 Ciljani korisnici i dionici

| Skupina korisnika ili dionika | Potreba ili interes relevantan za ovaj projekt |
| --- | --- |
| Iznajmljivač | Objaviti vlastiti predmet, odrediti cijenu i raspoloživost te pratiti dogovor i stanje pri povratu. |
| Najmoprimac | Pronaći prikladan predmet za određeno razdoblje, razumjeti cijenu i uvjete te dogovoriti preuzimanje i povrat. |
| Administrator | Pregledati tickete i prijavljene oglase, komunicirati sa sudionicima i evidentirati obrazložen ishod obrade. |
| Poslovni korisnik | Ponuditi predmete ili usluge preko poslovnog profila; podatke i ovlasti zastupnika treba definirati. |
| Operater platforme i nadležna tijela (dionici) | Zaštita osobnih podataka i jasno definirane obveze pri najmu, naplati i obradi prigovora; nisu dodatne aplikacijske uloge. |
| Tim i nastavno osoblje (dionici) | Izvediv opseg, provjerljivi zahtjevi i dokumentirani doprinos članova. |

## 1.3 Granice projekta

**Uključeno:** Objava i pretraga predmeta, opreme i usluga; dogovor i praćenje najma; fotografije prije i poslije; recenzije korisnika; podrška administratora; prijava preko vanjskog pružatelja identiteta; lokacija i AI provjera prikladnosti oglasa. Detalje poslovnih profila, usluga i financijskog postupka treba potvrditi prema zahtjevima u poglavlju 2. 

**Izvan opsega ili odgođeno:** Dostava i skladištenje predmeta. Chatbot, gostujući račun i alternativna prijava iz izvornog opisa dodatne su mogućnosti ako vrijeme dopusti. Stvarna naplata, porezni postupak i eventualni pravni učinak odluke administratora zahtijevaju dodatnu specifikaciju; nisu prikazani kao ostvareni niti su bez dogovora izbrisani iz izvornog koncepta.

**Vanjske ovisnosti:** Planirani su vanjski pružatelj identiteta (Google OAuth/OIDC), Google Maps za lokaciju te AI servis za provjeru fotografija i kategorije. Za povezanu aplikaciju potrebni su baza podataka i trajna pohrana fotografija; PostgreSQL je prijedlog iz README-a. Pružatelj naplate uvodi se nakon potvrde financijskog opsega. Integracije nisu povezane u priloženom kodu.

## 1.4 Postojeći pristupi i opravdanost projekta

Dostavljeni opis projekta navodi korisnički scenarij traženja grafičkog kalkulatora preko više platformi i zasebnih razgovora s potencijalnim najmodavcima. Takav postupak omogućuje izravan dogovor, ali podaci o predmetu, raspoloživosti i stanju nisu objedinjeni u jednom zapisu najma. TradeIt predlaže povezati te korake i podršku na jednom mjestu. To je polazni scenarij iz projektnog opisa, a ne rezultat provedenog tržišnog istraživanja ili tvrdnja da slični proizvodi ne postoje.

---
