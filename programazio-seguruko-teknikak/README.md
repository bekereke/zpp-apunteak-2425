---
description: >-
  Protokolo kriptografikoak: hash funtzioak, zifraketa simetrikoa, zifraketa
  asimetrikoa
icon: '3'
---

# Programazio seguruko teknikak

<details>

<summary><mark style="color:purple;">Ikaskuntza emaitza</mark></summary>

### <mark style="color:purple;">IE 5. Aplikazioak eta datuak babesten ditu, eta, eginkizun horretan, segurtasun-irizpideak aplikatuko ditu informazioa atzitzean, biltegiratzean eta transmititzean.</mark>

<mark style="color:purple;">a) Programazio seguruko printzipioak eta praktikak identifikatu eta aplikatu ditu.</mark>&#x20;

<mark style="color:purple;">b) Teknika eta praktika kriptografiko nagusiak aztertu ditu.</mark>&#x20;

<mark style="color:purple;">c) Segurtasun-politikak definitu eta ezarri ditu, garatutako aplikazioetara erabiltzaileen sarrera mugatzeko eta kontrolatzeko.</mark>&#x20;

<mark style="color:purple;">d) Roletan oinarritutako segurtasun-eskemak erabili ditu.</mark>&#x20;

<mark style="color:purple;">**e) Biltegiratutako informazioaren atzipena babesteko algoritmo kriptografikoak erabili ditu.**</mark>&#x20;

<mark style="color:purple;">f) Transmititutako informazioa aseguratzeko metodoak identifikatu ditu.</mark>&#x20;

<mark style="color:purple;">g) Informazioa transmititzeko socket seguruak erabiltzen dituzten aplikazioak garatu ditu.</mark>&#x20;

<mark style="color:purple;">h) Garatutako aplikazioak araztu eta dokumentatu ditu.</mark>

</details>

***

Oro har, socket-en bidez zerbait bidaltzen denean, «testu lau» gisa bidaltzen da; hau da, ez dakigu norbait dagoen sarean sniffer bat erabiltzen, eta, beraz, ez dakigu norbait datuak harrapatzen ari den. MitM (_Man in the Middle_) erasoa deritze. Are gehiago, sarean garraiatu gabe ere, lokalean bertan gordetako informazio zaurgarria ere babestu behar da sisteman sartu daitekeen erasotzaileengandik. Esate baterako, pasahitzak. Sarean edo sarearen bidez partekatzen den kodearen kautotzea ere beharrezkoa da segurtasun ikuspuntutik. Nola bermatu daiteke bestela garatu den kodea dela bezeroak exekutatuko duena eta ez aldaketak jasan dituen bertsioa? Zein da bermea? Segurtasunagatik mintzo garelarik, beraz, _zenbat buru hainbat aburu_.&#x20;

Oro har, segurua izan nahi duen edozein sistemak zifraketa teknikak erabili beharko ditu. Kriptografia hitza grezierazko _kryptos_ hitzetik dator, ezkutukoa esan nahi du; eta, grafoak, idazkera esan nahi du. Kriptografiaren helburua mezu baten esanahia ezkutatzea da: mezua zifratzea edo kodetzea, alegia.

## Segurtasun digitalaren ezaugarriak

Komunikazio digitalen segurtasunaren funtsezko alderdiak hauek dira:

* **Osotasuna**: Hartzaile batek jasotzen dituen datuak eta igorleak bidalitakoak berdinak direla ziurtatzeko aukera ematen du. Hau da, ez da aldatu kanalaren erdiko puntu bakar batean ere; dakigunez, kanal partekatua da, eta, beraz, ez da segurua. Kanalaren bidezko transmisioan izandako akatsek edo hirugarren batek nahita egindako ekintza batek eragin ditzakete aldaketak.
* **Konfidentzialtasuna**: Ziurtatzen digu transmititutako datuak mezuaren hartzailearentzat bakarrik direla ulergarriak. Hedabidearen ezaugarriak direla eta, ezin dugu mezua beste hartzaile batzuengana iristea ekidin, baina mezuaren jatorrizko edukia ikustea ekidin dezakegu. Mezua zifratuz lortzen da hori.&#x20;
* **Autentifikazioa**: Mezu baten hartzaileari ziurtatzen dio mezuaren igorlea bera dela, eta ez beste edozein. Hori ziurtagiriekin eta sinadura digitalarekin lortzen da.
* **Gaitzezpenik eza**: Aurreko ezaugarriaren ondorio bat da, hartzaileak ziurtatu dezakeelako mezua esperotako igorlearena dela.

### Aplikazioak

* **Mezularitza segurua**: mundu guztiak ematen du bere zifratze-gakoa, baina deszifratze-gakoa mantentzen du (asimetrikoa denean). Norbaiti mezu bat bidali nahi badiogu, haren zifratze-gakoa hartu eta bidaltzen diogun mezua zifratzen dugu. Berak bakarrik deszifratu ahal izango du.
* **Sinadura digitalak**: merkataritza elektronikoaren zutabea. Fitxategi bat aldatu ez dela egiaztatzeko aukera ematen du.
* **Mezularitza segurua**: mezularitza mota honetan, erasotzaile batek (agian sniffer batekin) gure mezuak deszifratzea ekiditen saiatzen da.
* **Kautotzeak**: autentifikazio-sistemak informatikan funtsezkoa den gai bat konpontzen saiatzen dira: iruzurgilerik ez dabilela ordezkatzen solaskidea.&#x20;

## Javaren segurtasuna

Segurtasunaren ikuspegitik, Java 2ren SDK sistemarekin banatutako segurtasun klaseak bi azpimultzotan banatu daitezke:

* Sarbide-kontrolarekin eta baimenen kudeaketarekin lotutako klaseak.&#x20;
* Kriptografiarekin zerikusia duten klaseak.

Javak helburu orokorreko funtzio kriptografikoetara sartzeko APIak ditu, hala nola Javaren Arkitektura Kriptografikoa edo _Java Cryptography Architecture_ (JCA) eta Javaren Luzapen Kriptografikoa edo _Java Cryptography Extension_ (JCE).

JCA, JDK-rekin banatutako kriptografiarekin lotutako oinarrizko klaseez osatuta dago eta enkriptatzeko euskarria JCE luzapen paketeak ematen du.

Javak Interneteko komunikazio segururako pakete multzo bat ere badu, Java Sockets Seguruen Luzapena edo _Java Secure Socket Extension_ (JSSE) bezala ezagutzen direnak. SSL eta TLS protokoloen Java bertsio bat inplementatzen du, eta, gainera, zenbait funtzionalitate ditu, hala nola datuen zifratzea, zerbitzariaren autentifikazioa, mezuen osotasuna eta bezeroaren autentifikazioa.

Azkenik, Javak interfaze bat du, Java aplikazioek autentifikazio- eta sarbide-kontroleko zerbitzuak, Java autentifikatzeko eta baimentzeko zerbitzua edo Java Authentication and Authorization Service (JAAS) erabiltzeko aukera izan dezaten. Bi helbururekin erabil daiteke: erabiltzaileak autentifikatzea Java kodea nork exekutatzen duen jakiteko; eta erabiltzaileak baimentzea exekutatzen duenak hori egiteko behar diren baimenak dituela bermatzeko.

<details>

<summary>JCA: Engineak, algoritmoak eta hornitzaileak</summary>

Javak hornitzaileen arkitektura bat du, algoritmo kriptografikoen inplementazio anitzak (hau da, JCEren inplementazio anitzak) koexistitzea ahalbidetzen duena. Java 2 plataformak asko hedatzen du JCA; besteak beste, ziurtagiriak kudeatzeko azpiegitura hobetu da, X.509 V3 ziurtagiriei eusteko.

JCAren funtzionamendua ulertzeko, oinarrizko termino batzuk definitu behar ditugu:

*   **Engine**: \
    JCA testuinguruan, "motorra" (engine) terminoa erabiltzen dugu, inplementazio zehatzik ez duen zerbitzu kriptografiko baten irudikapen abstraktua adierazteko. Zerbitzu kriptografiko bat algoritmo batekin edo algoritmo-mota batekin lotuta dago beti, eta funtzio hauetakoren bat izan dezake:

    -Eragiketa kriptografikoak ematea (sinaduran eta mezuen laburpenean erabilitakoak, adibidez)\
    -Eragiketak egiteko behar den material kriptografikoa (gakoak edo parametroak) sortzea edo ematea. Gako kriptografikoak modu seguruan multzokatzen dituzten objektuak (gakoen edo ziurtagirien biltegiak) sortzea.

- **Algoritmoa**: \
  Algoritmo bat motor baten inplementazioa da. Adibidez, MD5 algoritmoa mezuen laburpen algoritmoen motorraren inplementazioa da. Barne-inplementazioa MD5 klaseak ematen duen kodearen arabera aldatu daiteke.&#x20;
-   **Hornitzaileak**: \
    Hornitzaile bat arduratzen da programatzaileari algoritmo baten edo batzuen inplementazioa emateaz (hau da, algoritmoen barne-inplementazio jakin baterako sarbidea emateaz). \
    \
    Adibidez: programatzaileak MD5 algoritmoaren inplementazioa behar baldin badu `java.security.Security` klaseko metodoari eskatuko dio objektua eta harkera berean eskuragarri dituen hornitzaile guztiei galdetuta jasoko du behingoz bueltan: \


    ```java
    MessageDigest m = MessageDigest.getInstance("MD5");
    ```

</details>

{% hint style="info" %}
`java.security` fitxategia

%JAVA\_HOME%/conf/security/java.security da JCAko klaseek erabiltzen duten segurtasun-konfigurazioaren informazioa duen fitxategia.

Hor deklaratuta daude eskuragarri dauden hornitzaile eta algoritmo guztiak, baita klaseek zein ordenatan bilatuko dituzten ere.
{% endhint %}
