# **Individualus kainyno importavimas**

Paskirtos užduoties PHP programavimo praktikai atlikimas, taikant apsipirkimo turinio valdymo sistemą svetainių kūrimui ir jos metodikoms realizuoti.

### **Užduoties aprašymas**

Pasitelkus svetainės serverį ir prisijungimo prie databazės galimybes, yra reikalaujama modifikuoti "OpenCart" administravimo panelę ir josveikimo principus, implementuojant šiuos svetainės komponentus:
-  Užduočiai atlikti naudokite OpenCart 3.X.X versiją ([https://www.opencart.com/](https://www.opencart.com/)). Nenaudokite modulių, kodą rašykite savarankiškai.
    
-  Administracinėje dalyje sukurkite kainų importo galimybę (į duomenų bazę) kiekvienam užsiregistravusiam vartotojui atskirai (Customers -> customers -> vartotojas). Užduoties tikslas, kad butų galimybė kiekvienam užsiregistravusiam vartotojui importuoti tik jam pritaikytas kainas (sukurti individualų kainyną).
-   Turi matytis informacija, kada buvo atliktas paskutinis importas, ir kas jį atliko.
    
-  Įkelti duomenys atvaizduojami lentelėje su redagavimo ir trynimo galimybe kiekvienam įrašui.
-  Dar kartą įkėlus .csv failą senieji duomenys ištrinami.
- Prekės pavadinimas lentelėje ir nuoroda į prekę (admin dalies) atvaizduojama automatiškai “susiriša” su importuotu prekės kodu.
- jeigu prie parduotuvės prisijungia lankytojas (customer), kuriam priskirtos/importuotos kainos, tuomet parduotuvėje kainos rodomos tokios, kokios yra jam priskirtos/importuotos (iš kainyno). Jeigu yra prekių, kurioms kainos nėra priskirtos (arba nulis), tuomet rodoma default kaina, kuri įvesta prie prekės.

### Užduoties atlikimas
Implementuojant CSV failo importą pirkėjų individualioms kainoms nustatyti, buvo pasitelkta MVC customers kodo praplėtimu, įdedant papildomą skiltį Customers dalyje, įsijungus redagavimo režimą, kur "Imports" dalyje yra rodoma failo įkėlimo sąsaja su funkcionalumu. Darbui su duomenimis yra naudojamasi Ajax užklausomis į kontrolerį, kur pagal gaunamus rezultatus yra manipuliuojamas turinys, pasitelkus JavaScript ir JQuery technologijomis.

Sąrašas modifikuotų projekto failų:
- admin/controller/customer/customer.php 			line 947
- admin/controller/customer/customer.php 			line 1506
- model/customer/customer.php 						line 487
- admin/language/en-gb/customer/customer.php		line 116
- admin/view/template/customer/customer_form.twig 	line 35
- admin/view/template/customer/customer_form.twig   line 892
- admin/view/template/customer/customer_form.twig   line 1481
- catalog/model/catalog/product.php					line 10
- catalog/model/catalog/product.php					line 552
- Added view/template/customer/customer_prices.twig


### Veikianti užduotis
http://orca.ddns.net/

admin prisijungimas:
username: admin
password: orcatask1

PHPMyAdmin prisijungimas:
username: root
password: ElitezInc420

### Kontaktiniai duomenys
Gabrielius Važnevičius
vaznevicius@gmail.com
+37060954632