---
icon: '3'
description: >-
  Protokolo kriptografikoak: hash funtzioak, zifraketa simetrikoa, zifraketa
  asimetrikoa
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

Oro har, socket-en bidez zerbait bidaltzen denean, «testu lau» gisa bidaltzen da; hau da, ez dakigu norbait dagoen sarean sniffer bat erabiltzen, eta, beraz, ez dakigu norbait datuak harrapatzen ari den. MitM (_Man in the Middle_) erasoa deritze. Are gehiago, sarean garraiatu gabe ere, lokalean bertan gordetako informazio zaurgarria ere babestu behar da sisteman sartu daitekeen erasotzaileengandik. Esate baterako, pasahitzak.&#x20;

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

    \-Eragiketa kriptografikoak ematea (sinaduran eta mezuen laburpenean erabilitakoak, adibidez)\
    \-Eragiketak egiteko behar den material kriptografikoa (gakoak edo parametroak) sortzea edo ematea. Gako kriptografikoak modu seguruan multzokatzen dituzten objektuak (gakoen edo ziurtagirien biltegiak) sortzea.

<!---->

* **Algoritmoa**: \
  Algoritmo bat motor baten inplementazioa da. Adibidez, MD5 algoritmoa mezuen laburpen algoritmoen motorraren inplementazioa da. Barne-inplementazioa MD5 klaseak ematen duen kodearen arabera aldatu daiteke.&#x20;
*   **Hornitzaileak**: \
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

## Zifraketa _simetrikoa_ edo gako ezkutukoa

Protokolo edo teknika kriptografikoa da. Sistema simetrikoak mezuak bihurtzen dituzte mezu zifratutara funtzioren bat erabiliz. Zerbait deszifratu nahi bada, alderantzizko prozesua aplikatzen da erabilitako gako berarekin.

Beraz, mezu zifratuak bidaltzeko, mekanismo edo algoritmoren bat behar da testu arrunta dena ulertzen zailagoa den beste batera bihurtzeko.

Metodo guztien eskema orokorra hau bezalako kodea izatea da:

```java
public String zifratu (String testua, String gakoa)
{
}

public String deszifratu(String testua,String gakoa)
{
}
```

### Zesar zifratze-sistema

Mezua etsaiak harrapatu arren ulerkaitza izateko eran adierazteko asmatu zuten, eta era errazean berreskuratzeko jatorrizkoa. Alfabetoko hizki guztiak posizio batean mugitzean datza eta ordenaren arabera mezuan sasi-alfabeto berrian transkribatzean:

ABCDEFGHIJKLMNÑOPQRSTUVWXYZ0123456789- BCDEFGHIJKLMNÑOPQRSTUVWXYZ0123456789-A

"KAIXOMUNDUA" mezua behin irristatutako gakoan litzateke:  LBKYPNVÑEVB

Deszifratzeak alderantzizko prozesua besterik ez luke ekarriko. Desplazamendua 1 ez den balio bat bada, egin behar den gauza bakarra da errotatutako alfabetoa eraikitzea desplazamendua adina aldiz.

Oinarrizko biraketa-sistema bat inplementatzen du, honako hauek egin ahal izateko:

```java
public class Cifrador {
        private String alfabeto=
                        "ABCDEFGHIJKLMNÑOPQRSTUVWXYZ"+
                        "0123456789 ";
        private String alfabetoCifrado;
        /* Dada una cadena como
         * "ABC" y un número (p.ej 2)
         * devuelve la cadena rotada a la izq
         * tantas veces como indique el numero,
         * en este caso "CAB"
         */
        public String rotar(String cad,int numVeces){
                char[] resultado=new char[cad.length()];
                for (int i=0; i<cad.length();i++){
                        int posParaExtraer=(i+numVeces)%cad.length();
                        resultado[i]=cad.charAt(posParaExtraer);
                }
                String cadResultado=String.copyValueOf(resultado);
                return cadResultado;
        }
        public String cifrar
                (String mensaje, String clave){
                String mensajeCifrado="";

                return mensajeCifrado;
        }
        public String descifrar
                (String mensajeCifrado, String clave){
                String mensajeDescifrado="";

                return mensajeDescifrado;
        }
        public static void main(String[] args){
                Cifrador c=new Cifrador();
                String cad=c.rotar("ABCDEFG", 0);
                System.out.println(cad);
        }
}
```

## Laburpen funtzioak edo _hash_ funtzioak

_Hashing_ esaten zaio funtzio kriptografiko bezala ezagutzen den algoritmo matematiko bat erabiliz mezu batetik hizki-kate edo hash bat sortzeko prozesuari.

Nahiz eta hash funtzio bat baino gehiago egon, pasahitzekin jardutera egokitzen direnek lau propietate nagusi izan behar dituzte seguruak izateko:

1. _Determinista_ izan behar da: hash funtzio berdinez prozesatutako mezuak beti sortu behar du hash bera. &#x20;
2. _Ez-itzulgarria_ izan behar da: ezinezkoa izan behar du hash-etik abiaturik hasierako mezura itzultzea.
3. _Entropia_ altua du: mezu batera aldaketa txiki batek oso hash desberdina eragin behar du.
4. _Talkei eutsi_ behar die (kolisioak): bi mezu desberdinek ezingo dute hash berdina sortu.&#x20;

Lau propietateak bateratzen dituen hash funtzio bat hautagai sendoa da pasahitzaren hashing iturri izateko, elkarrekin izugarri zailduko diotelako iruzurgileei alderantzizko ingeniaritza egin eta hashetik pasahitza eskuratzerik.

Gainera, pasahitzentzat diren hashing funtzioek motelak izan behar dute. Algoritmo azkar batek indar gordineko erasoei lagunduko lieke: hackerrak pasahitzak asmatzen saiatuko dira talka egitea bilatuz. Gai dira segundoko milaka milioi (edo bilioi) pasahitz potentzial alderatzeko eta hashing algoritmoa oso ona ez baldin bada, azkenerako matematikoki posiblea da hash berdina sortzea mezu desberdinetik.&#x20;

<details>

<summary><em>Rainbow table</em> erasoak eta haiengatiko babesa</summary>

Sistema informatiko bateko pasahitzak ez dira zuzenean gordetzen testu soil gisa, baizik eta zifratze bidez hash bihurtuta. Hash funtzio bat alde bakarrerako prozesu bat da, eta horrek esan nahi du ezin dela deszifratu. Erabiltzaileak pasahitza sartzen duenean, hash balio bihurtzen da eta ordurak sisteman gordeta dagoen hash balioarekin alderatzen da. Balioak bat badatoz, erabiltzailea autentifikatuta dago.

Rainbow table  datu-base erraldoi bat da indar gorria erabiltzeko hainbat testu sarreraren hashak gordeta dituena. Testu sinpleko pasahitzen eta horiei dagozkien hash balioen hiztegi prekalkulatua da. Hash partikular batek zein testu sinpleko pasahitz sortzen duen jakiteko erabil daiteke. Testu batek baino gehiagok hash bera sor dezakeenez, ez da garrantzitsua jakitea zein izan zen benetan jatorrizko pasahitza, betiere hash bera ekoizten badu.

Konponbiderik?&#x20;

#### `Salt` edo ausazko eransgarriak

Erasoak erraz prebenitu daitezke Salt teknikak erabiliz. Ausazko datu bat sortu eta hash funtziora pasatzen dena testu sinplearekin batera. Horrek bermatzen du pasahitz bakoitzak hash bakar bat duela sortua eta, beraz, Rainbow table erasoa, testu batek baino gehiagok hash balio bera izan dezakeela dioen printzipioaren gainean funtzionatzen duena, ekiditea.

</details>

Message digest edo mezuen laburpenak (hash funtzioak bezala ezagunagoak), datu-bloke baten (fitxategiak, Stringak,...) marka digitala direla esan da honezkero. Laburpen horiek prozesatzeko algoritmo ugari daude diseinatuta, SHA-1 eta MD5 dira ezagunenak.

Nabarmengarri ezaugarri hauek:

* Algoritmo bererako, laburpenak beti du tamaina bera, sortzeko erabili den datuen tamaina edozein dela ere.&#x20;
* Ezinezkoa da jatorrizko informazioa laburpen batetik berreskuratzea.&#x20;
* Hura sortzeko erabilitako daturik ez ditu sekula jasoko laburpenak.
* Konputazionalki bideraezina da laburpen bera duten bi mezu aurkitzea. Ikuspuntu matematikotik oso zaila den arren ez da ezinezkoa.&#x20;
* Laburtzeko diren datuen aldaketa txiki batek laburpen guztiz ezberdina sortuko du.

<mark style="background-color:blue;">Laburpenak identifikatzaile bakar eta fidagarriak sortzeko erabiltzen dira.</mark> Batzuetan, _checksum_ deitzen zaie. Deskarga bat ondo egin den egiaztatzeko erabiltzen dira, edo, inork manipulatu ez izanaren egiaztagiritzat: nahikoa da fitxategien jatorrizko laburpena eskuragai izatea eta jasotako fitxategiarekin sortu berriarekin alderatzea.

{% hint style="warning" %}
**Hash batek ez du zifratzeko balio. Konparaketak egiteko, bai ordea**

Garrantzitsua da nabarmentzea ezen, ezinezkoa denetik laburpenetik hura sortzeko erabilitako datuak berreskuratzea, laburpena ezin dela erabili informaziorik zifratzeko.

Bestelakoa da erabilera: konparaketak egitea. Pasahitzekin erabiltzen da gehien: datu-baseetan laburpena gordetzen baita, pasahitzaren ordez. Hala, pasahitz bat jasotzen denean, haren laburpena sortzen dute, eta gordetako balioarekin alderatzen!
{% endhint %}

<details>

<summary>Hashing algoritmo ezagunenak</summary>

*   **MD5**\
    Mezuak laburtzeko lehen algoritmoa, 1992koa. \
    Javaren MessageDigest klasearen bidez erabilterraza den arren, ez da kasu guztietan hautagai onena.

    Izan ere, azken urteetan, MD5 funtzioaren talkak izateko ahultasunaren berria zabal da.  Gainera, MD5 algoritmo azkarra denetik, ez du balio indar gordineko erasoen aurka. Ahulgune franko.&#x20;
*   **SHA-512**\
    1993an asmatu zen SHA familiko laburtzaileen familiako bertsio indartsuena da. \
    Ordenagailuen ahalmena handitu ahala, ahulguneak ere identifikatu zaizkie, eta garatzaileek SHA bertsio berritu izan dute maiz ahatik. Bertsio berrienek gero eta luzera handiagoa dute.&#x20;

    SHA-512 da hirugarren belaunaldia da, SHA familiako algoritmoen artetik gako luzeena duena.

    Hau baino SHA bertsio seguruagoak dauden arren, SHA-512 da Javan inplementatzen den indartsuena. `Salt` teknikarekin batera erabiliz gero, SHA-512 aukera ona den arren oraindik orain, honezkero badira aukera indartsuagoak eta motelagoak.
*   #### **PBKDF2,** BCrypt eta SCrypt <a href="#bd-2-implementing-pbkdf2-in-java" id="bd-2-implementing-pbkdf2-in-java"></a>

    Komunean daukaten ezaugarri nagusienak dira moteltasuna eta ezarpenak aldatzeko aukera. Horrela, sendotasun maila desberdinak lortu ditzakete egoeraren arabera. Gero, aurrenekoa Javan natiboki erabiltzeko klaseak dauden artean (`PBEKeySpec`), azken biak baliatzeko _Spring Security_ren `PasswordEncoder` interfazea lortu beharko da eta proiektuan erantsi erabili ahal izateko.&#x20;

</details>

### `MessageDigest` klasea

Aplikazioeetan kriptografikoki seguruak diren laburpen algoritmoak inplementatzeko klasea da: arestian aipatu berri diren SHA-256 edo SHA-512, eta enparauak. Egokiena aukeratu beharren arabera.

Ondoren, JCArekin hash bat sortzeko, hau egin behar da:

1. `MessageDigest` klaseko `getInstance()` metodo estatikoa erabiliz, `MessageDigest` instantzia edo objektua sortuko da parametro gisa aukeratu algoritmoaren izena zehaztuta. Nahi izanez gero, hornitzailearen izena zehaztuz egin daiteke.&#x20;
2. Datuak `update()` metodoarekin gehitzen dira. Byte bat edo byte-array bat gehi daiteke. Metodo hau behin baino gehiagotan erabil daiteke datu berriak gehitzeko.&#x20;
3. Hash balioa lortzeko `digest()` metodoa erabili.
4. Hash berri bat kalkulatu nahi izanez gero, `reset()` metodoa erabiltzea dago eta prozesua berriro hasi.

#### Testua zifratzea

```java
public class U6S2_MessageDigest {

    public static void main(String[] args) {
        String plaintext = "Esto es un texto plano.";
        try {
            // Obtenemos un ENGINE que implementa el algoritmo especificado
            // Se puede indicar cualquier algoritmo disponible en el sistema
            // SHA-224, SHA-512, SHA-256, SHA3-224, ...
            MessageDigest m = MessageDigest.getInstance("SHA-256");

            // Opcional - Reinicia el objeto para un nuevo uso 
            // Por si queremos poner este código en un bucle y procesar más
            // de un mensaje
            m.reset();

            // Realiza el resumen de los datos pasados por parámetro
            // Si queremos procesar la información poco a poco, 
            // debemos ir llamando al método update para cada bloque de datos
            m.update(plaintext.getBytes());

            // Completa el cálculo del valor del hash y devuelve el resumen
            byte[] digest = m.digest();

            // Mensaje de resumen
            System.out.println("Resumen (raw data): " + new String(digest));

            // Mensaje en formato hexadecimal
            System.out.println("Resumen (hex data): " + toHexadecimal(digest));
            
            
            // Información del proceso
            System.out.println("=> Algoritmo: " + m.getAlgorithm() + ", Provider: " + m.getProvider().getName() + " " + m.getProvider().getVersionStr());
        } catch (NoSuchAlgorithmException e) {
            System.err.println("No se ha encontrado la implementación del algoritmo MD5 en ningún Provider");
        }
    }

    static String toHexadecimal(byte[] hash) {
        String hex = "";
        for (int i = 0; i < hash.length; i++) {
            String h = Integer.toHexString(hash[i] & 0xFF);
            if (h.length() == 1) {
                hex += "0";
            }
            hex += h;
        }
        return hex.toUpperCase();
    }
}
```

Irteera:

```powershell
Resumen (raw data): �Y�"�3��`b����bs?;������~E
Resumen (hex data): FB59D31122913314111B92CD60628ED7E7DE62733F3B10DEDAF303AAABE57E45
=> Algoritmo: SHA-256, Provider: SUN 11
```

{% hint style="danger" %}
Javan zifratzen eta deszifratzen duten objektuek `byte[]` datu-motak baino ez dituzte onartzen (`raw` izenekoak). `String` bihurketak dira soilik irakurleak emaitzak ikusi ahal izateko.
{% endhint %}

<details>

<summary><code>Salt</code> praktikan (algoritmo ahulentzat konponbidea)</summary>

Hitz gutxitan, hash berri bakoitzerako sortzen den ausazko sekuentzia eransten zaio pasahitzari.

Ausazkotasun hori sartzean, hasharen entropia handitzen laguntzen digu, hiztegian eta zentzuko esaldietan oinarrituta prestatu diren Rainbow table zerrendei aurre egiteko eraginkortasuna areagotuz.

Hash laburpenerako pausoak honelako zerbaitetan geldituko dira:

`salt <- salt-sortzeko-deia;`&#x20;

`hash <- salt + ':' + nahi-den-algoritmoa(salt + pasahitza)`

`java.security` liburutegiko `SecureRandom` klasea erabiliz adibidea, hemen:

```java
SecureRandom random = new SecureRandom();
byte[] salt = new byte[16];
random.nextBytes(salt);
String password = "0123456789";
```

Ondoren, `MessageDigest` erabiliz, esaterako, SHA-512 indartuko da:

```java
MessageDigest md = MessageDigest.getInstance("SHA-512");
md.update(Bytes.concat(salt,password.getBytes()));
```

Eta behin erantsi dela, laburpena sortu daiteke aurretik ere ikusi den erara:

```java
byte[] hashedPassword = md.digest(passwordToHash.getBytes(StandardCharsets.UTF_8));
```

</details>

#### Fitxategien laburpena sortzea&#x20;

`GnuPG` metodo sortak  balio du testu soilen laburpenak baino fitxategi osoen hasha lortzeko.&#x20;

{% hint style="info" %}
**GnuPGn eskuragai dauden algoritmoak**

Erabili daitezkeen algoritmoen zerrenda ezagutzeko komando-lerroko aginduari eskatu behar zaio:

> gpg --help

Goikaldean ageriko dira zerbitzu bakoitzarentzat erabilgarri dituen algoritmoak.&#x20;

```shell
erabiltzailea@HZ129473:~$ gpg --help
gpg (GnuPG) 2.2.27
libgcrypt 1.9.4
Copyright (C) 2021 Free Software Foundation, Inc.
License GNU GPL-3.0-or-later <https://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

Home: /home/erabiltzailea/.gnupg
Supported algorithms:
Pubkey: RSA, ELG, DSA, ECDH, ECDSA, EDDSA
Cipher: IDEA, 3DES, CAST5, BLOWFISH, AES, AES192, AES256, TWOFISH,
        CAMELLIA128, CAMELLIA192, CAMELLIA256
Hash: SHA1, RIPEMD160, SHA256, SHA384, SHA512, SHA224
Compression: Uncompressed, ZIP, ZLIB, BZIP2

Syntax: gpg [options] [files]
Sign, check, encrypt or decrypt
Default operation depends on the input data
```

\
**Laburbilduz**: SHA1, RIPEMD160, SHA256, SHA384, SHA512, SHA224
{% endhint %}

Fitxategi baten laburpena edo hash kodea lortuko da komando hau sartuta (aukeran norberak nahi lukeen algoritmoa):

```powershell
gpg --print-md SHA256 fitxategia.luzapena
```

## Zifraketa _asimetrikoa_ edo gako pribatu eta publiko parea

Segurtasun sistema moderno nagusiek bi gako erabiltzen dituzte, bata zifratzeko eta bestea deszifratzeko. Hori hainbat modutan erabili daiteke.

Hots, sistema asimetrikoek zifratze-gako bat eta deszifratze-gako bat erabiltzen dituzte. Gako bat edukita ere, matematikoki ezinezkoa da beste gakoa zein den jakitea, beraz, mundu guztiari eman ahal zaio gakoetako bat (normalean gako publikoa deitzen dena) eta bestea gorde (gako pribatua deitzen dena). Gainera, gakoak nahi dugunerako erabil ditzakegu, eta, adibidez, kasu batzuetan gako publikoarekin zifratuko dugu, eta beste batzuetan, agian, gako pribatuarekin. Era batera lortuko dugu edonork mezua irakurtzea baina garbi edukitzea guk bakarrik idatzi izan ahal dugula; bestera, lortuko dugu edonork idatzi dezakeela mezua, baina irakurri, soilik guk.&#x20;

Gaur-gaurkoz, bermerik handiena asimetrikoek eskaintzen dute. Hori inplementatzeko hainbat sistema daude. Asimetrikoek izan dezaketen eragozpena da konputazionalki duten karga: motelagoak direla.

#### Testua zifratzea

RSA algoritmoa erabili da adibidean:

```java
public class GestorCifrado {
        KeyPair claves;
        KeyPairGenerator generadorClaves;
        Cipher cifrador;
        public GestorCifrado()
                        throws NoSuchAlgorithmException,
                        NoSuchPaddingException{
                generadorClaves=
                                KeyPairGenerator.getInstance("RSA");
                /*Usaremos una longitud de clave
                 * de 1024 bits */
                generadorClaves.initialize(1024);
                claves=generadorClaves.generateKeyPair();
                cifrador=Cipher.getInstance("RSA");
        }
        public PublicKey getPublica(){
                return claves.getPublic();
        }
        public PrivateKey getPrivada(){
                return claves.getPrivate();
        }

        public byte[] cifrar(byte[] paraCifrar,
                        Key claveCifrado
                        ) throws InvalidKeyException,
                        IllegalBlockSizeException,
                        BadPaddingException{
                byte[] resultado;
                /* Se pone el cifrador en modo cifrado*/
                cifrador.init(Cipher.ENCRYPT_MODE,
                                claveCifrado);
                resultado=cifrador.doFinal(paraCifrar);
                return resultado;
        }

        public byte[] descifrar(
                        byte[] paraDescifrar,
                        Key claveDescifrado)
                                        throws InvalidKeyException,
                                        IllegalBlockSizeException,
                                        BadPaddingException{
                byte[] resultado;
                /* Se pone el cifrador en modo descifrado*/
                cifrador.init(Cipher.DECRYPT_MODE,
                                claveDescifrado);
                resultado=cifrador.doFinal(paraDescifrar);
                return resultado;
        }



        public static void main(String[] args)
                        throws NoSuchAlgorithmException,
                        NoSuchPaddingException,
                        InvalidKeyException,
                        IllegalBlockSizeException,
                        BadPaddingException,
                        UnsupportedEncodingException
        {
                GestorCifrado gestorCifrado=
                                new GestorCifrado();
                String mensajeOriginal="Hola mundo";
                Key clavePublica=gestorCifrado.getPublica();

                byte[] mensajeCifrado=
                                gestorCifrado.cifrar(
                                                mensajeOriginal.getBytes(),
                                                clavePublica
                );
                String cadCifrada=
                                new String(mensajeCifrado, "UTF-8");

                System.out.println
                        ("Cadena original:"+mensajeOriginal);
                System.out.println
                        ("Cadena cifrada:"+cadCifrada);

                /* Cogemos la cadCifrada y la desciframos
                 * con la otra clave */
                Key clavePrivada;
                clavePrivada=gestorCifrado.getPrivada();
                byte[] descifrada=
                                gestorCifrado.descifrar(
                                                mensajeCifrado,clavePrivada);
                String mensajeDescifrado;
    /* E imprimimos el mensaje*/
                mensajeDescifrado=
                                new String(descifrada, "UTF-8");
                System.out.println(
                                "El mensaje descifrado es:"+
                                                mensajeDescifrado);
        }
}
```

Aplikazioak sinatzea

<details>

<summary>Ziurtagiri lokalak jalgitzea <code>keytool</code> metodoarekin</summary>

Praktikak egin ahal izateko segutasuneko ziurtagiri propioak sortu eta jalgiko ditugu.&#x20;

Gako asimetriko bikotea sortu daiteke eta biltegi batean gordeko `keytool` tresnarekin. Adibidean, gakobiltegia izeneko lekuan gordeko dugu eta izenordain batekin ordezkatuko errezago erabiltzeko:

```
keytool -genkeypair -keyalg RSA -alias zerbitzaria -keystore gakobiltegia
```

Biltegiak bere aldetik ere gako propioa izango du. Ondoren, gako bikote horretatik abiatuz ziurtagiri bat sortu daiteke:&#x20;

```
keytool -export -file zertifikatuak.cer -keystore gakobiltegia
```

</details>

Gako publikoko kriptografia erabiliz, aplikazioak «sinatu» daitezke. Sinadura mekanismo bat da, aukera ematen diona aplikazio baten erabiltzaileari egiaztatzeko aplikazioa ez dela aldatu programatzaileak sortu zuenetik (birusak edo programa gaiztoak, enpresarekin gustura ez dauden langileak, inbidia dizun ikaskideak, etab.).

Sinatu aurretik, arestian aipatutako `keytool` tresnarekin sortutako bi gakoak prest izan behar dira. Demagun gakoen biltegia sortuta dagoela eta bertan ezizen bat edo batzuk sortuta daudela. Hona hemen sinatze-prozesua:

1. Aplikazioa sortu, klase multzo batez osatua egon daitekeena baina azken finean `main` bat izango duena.
2. Bildu aplikazioa `jar cfe AplikazioIzena.jar unieibar.AplikazioIzena *` eginda. JAR formatudun fitxategia sortuko du unieibar paketean bilduta dagoen exekutagarria gordeko duena (bestalde `main` metodoak izango duen berdina).&#x20;
3. Egiazta daiteke JAR barruko aplikazioa behar bezala exekutatzen dela `java -jar Aplicacion.jar` eginda terminalean.
4. Orain `jarsigner -keystore AplikazioIzena.jar` exekutatuz egiaztagiria txeratutuko zaio fitxategiari.

Urrats horiekin aplikazioa sinatuta dago, eta erabiltzaileak nahi izanez gero egiazta dezake. Izan ere, JAR edukia ateratzen bada fitxategitik `jar -xf AplikazioIzena.jar` erabiliz, ateratzen dira `.class` fitxategiak (exekutagarriak) eta `META-INF/Manifest` fitxategia. Editore batekin ireki daiteke azken hori, eta sinadura egiaztatu.

Beste pertsona batzuek gure aplikazioa zuzena dela egiaztatu ahal izateko, programatzaileok erabiltzaileek inporta dezaketen ziurtagiri bat esportatu beharko dugu. Gogoan izan komandoa hau dela:&#x20;

```
keytool -exportcert -keystore ..\Biltegia.store -file ProgramatzaileIzena.cer -alias ProgramatzaileIzena
```

#### Aplikazioak edonork egiaztatzea

Orain beste erabiltzaile batek gure aplikazioa exekutatu nahi badu, gure ziurtagiria inportatu beharko du. Egiaztatze-prozesua erraza da:

1. Ziurtagiria inportatu.
2. Aplikazioa egiaztatu `jarsigner -verify -keystore AplikazioIzena.jar <programatzaile_izena>` erabiliz.

Komandoak _jar verified_ bezalako zerbaitekin erantzun beharko du. Hala ere, ziurtapen-agintaritzaren batek (CA) sinatutako ziurtagiririk ezean, tresna kexatu egingo da segurtasun-irizpide batzuk ez direlako betetzen. Norberak sinatutako egiaztagiria izanagatik.&#x20;

{% hint style="danger" %}
Sinadura eta egiaztatze prozesua norberak egindako ziurtagiriekin egitea, praktikatzeko baliagarria izan daitekeen arren, erabat alferrikakoa da segurtasunaren ikuspuntutik. Ziurtagiri bat segurua izan dadin, ziurtagiri-jaultitzaile (CA) batek sinatu behar digu lehenik (horretarako, ohikoa izaten da ordaindu behar izatea).
{% endhint %}
