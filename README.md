# Frontend-testiranje
Ovaj projekt sastoji se od 5 testova koji testiraju različite web stranice i njihove funkcionalnosti.
Za izradu projekta korišten je program IntelliJ, pluginovi testng, selenium-java, maven-surefire-report-plugin i maven-compiler-plugin. Korišteni programski jezik je Java.
Prvi test testira web aplikaciju sofascore, točnije njezinu funkciju pretraživanja nogometnog kluba. Test započinje otvaranjem google tražilice i upisivanjem riječi sofascore koji su realizirani funkcijom sendKeys(). Koristila se implicitna wait naredba Selenium WebDriver-a kako bi se pričekalo učitavanje cijele stranice. Funkcijom findElement(By.xpath) pronađen je element koji otvara sofascore web aplikaciju pozivom funkcije .click(). Ulaskom u aplikaciju pronađen je search bar istom funkcijom i poslan je string "chelsea" koji bi trebao klikom odvesti na profil nogometnog kluba Chelsea. Prelazak na profil kluba iz search bara automatski postignuto je korištenjem klase Action. Action klasa je klasa Seleniuma koja omogućuje korištenje tipkovnice i miša, u slučaju testa koristile su se funkcije za strelicu dolje (jer je chelsea prvi izbor pa se prebacuje na njega) i enter. Prelaskom na profil kluba uspoređuje se Chelsea string sa body tagom kako bi pronašli radi li se o Chelsea nogometnom klubu.

Drugi test testira nazali li se dobar link na Ferit stranici ulaskom sa google tražilice. Test je uspješan ako funkcija assertEquals vrati true vrijednost, tj. ako su link https://www.ferit.unios.hr i tekst pronađen na elementu isti.

Treći test testira funkcionira li raspored nastave i sati za grupu DRC na Ferit stranici. Korištene su također naredbe wait i findElementById. Nova funkcionalnost WebDriver-a koja je korištena je getCurrentUrl(), koja dohvaća trenutni url na kojem se nalazi. Test prolazi ako su url rasporeda grupe DRC i dohvaćenog Urla isti funkcijom assertEquals().

Četvrti test testira responzivnost stranice nogometnog središta Beli Manastir. U ovom testu  odmah je otvorena stranica nogometnog središta te se nakon čekanja 10 sekundi prozor smanjuje na definirane vrijednosti za pregled preko mobilnog uređaja. Ovo je postignuto pozivanjem funkcije window() i pozivanjem funkcije setSize kako bi se koristila klasa Dimension u kojoj se instancira novi objekt sa definiranim širinama i visinama za pregled preko mobilnih uređaja. Test je prošao ako je na ekranu prikazan "hamburger" ikona koja klikom prikazuje navigacijsku traku kada su ekrani manji nego za računala.

Peti test testira radi li funkcionalnost gumbova za pokretanje/pauziranje videa i za mute/unmute.
