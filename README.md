# biblikoteka
U ovom repozitorijumu nalazi se softverski sistem za izdavanje knjiga u biblioteci u Java okruzenju. 

Ideja je da u biblioteci mogu da se nalaze: bibliotekar (zaposleni), clanovi biblioteke, pozajmice (kreira ih bibliotekar za datog clana koji pozajmljuje knjige), data pozajmica u sebi sadrzi infomacije o bibliotekaru i clanu, datum pozajmljivanja i datum najkasnijeg povratka knjiga koji ima na raspolaganju (dva meseca od dana pozajmljivanja), kao i listu knjiga koje je clan pozajmio. Time smo pozajmicu povezali sa klasom Knjiga, koja se povezuje sa nekim od autora (moze biti jedan ili vise), primerkom (obzirom da svaka knjiga ima vise primeraka). 

Slucajevi koriscenja su:
1.Prijavljivanje zaposlenog bibliotekara na sistem pod korisnickim imenom i lozinkom
2.Kreiranje novog clana biblioteke
3.Pretrazivanej clanova
4.Izmena clana
5.Brisanje clana
6.Kreiranje autora (ukoliko npr u biblioteku pristigne knjiga nekog autora cije knjige biblioteka prethodno nije imala)
7.Kreiranje knjige (nove knjige koja je pristigla u biblioteku)
8.Pretrazivanje knjige
9.Izmena knjige (u slucaju da smo npr imali 50 primeraka neke knjige, pristizanjem novih primeraka te knjige povecavamo samo broj primeraka)
10.Kreiranje pozajmice (svakim kreiranjem pozajmice, clanu na mail adresu stize pdf fajl sa podacima: kad je pozajmio, kad mora da vrati, koje knjige je pozajmio). 
11.Pretrazivanje pozajmice
12.Izmena pozajmice (ako je clan vratio sve knjige iz date pozajmice, status "pozajmljeno" se menja na "vraceno")

POZAJMICA
-Pozajmica je dokument u sistemu kojeg kreira zaposleni. Ako NN clan biblioteke pozajmi neke knjige, bibliotekar kreira pozajmicu za NN clana i pozajmica sadrzi sve podatke koji su neophodni kako bi se znalo do kad moraju da se vrate date knjige i koje knjige su pozajmljene. Za datog clana moze se kreirati vise pozajmica. Pozajmice su medjusobno nezavisne. Jedna pozajmica se odnosi na jedan dolazak clana u biblioteku, sledeceg dana ukoliko odluci da opet poseti biblioteku i pozajmi nove knjige, kreirace mu se druga pozajmica i ona ne zavisi od prethodne. 
*Nakon kreiranja pozajmice, potrebno je sacekati desetak sekundi kako bi se mail sa podacima poslao clanu na njegovu email adresu. Nakon toga ce iskociti poporuka "Mail je uspesno poslat!".

Bibliotekar -> uloguje se na sistem pod korisnickom imenom i lozinkom. Ukoliko jedno od ta dva nije ispravno, sistemu se ne moze pristupiti. U bazi postoje sledeci bibliotekari
1. korisnicko ime = b1, lozinka = b1,
2. korisnicko ime = b2, lozinka = b2

**************************************************************KORISCENJE APLIKACIJA************************************************************************************************************
Softverski sistem je kreiran kao klijent-server aplikacija. Sastoji se iz tri projekta:
1.BibliotekaServer
2.BibliotekaKlijent
3.BibliotekaCommon

Prvo je potrebno podici server, odnosno pokrenuti aplikaciju BibliotekaServer. Nakon podizanja servera, moze se pokrenuti projekat BibliotekaKlijent i tada se bibliotekaru mogu ulogovati na sistem ispravnim kredencijalima. Nakon uspesnog logovanja, prikazuje se glavna forma za rad koja omogucava obradu gore navedenih slucajeva koriscenja.
