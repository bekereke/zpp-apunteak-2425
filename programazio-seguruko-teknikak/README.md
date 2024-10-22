---
icon: '3'
description: Hash funtzioak, zifraketa simetrikoa, zifraketa asimetrikoa
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

## Zifraketa _simetrikoa_ edo gako ezkutukoa

Mezu zifratuak bidaltzeko, mekanismo edo algoritmoren bat behar da testu arrunta ulertzen zailago bihurtzeko.

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



## ~~Zifraketa asimetrikoa edo gako pribatu/publiko parea~~



## Laburpen funtzioak edo _hash_

Message digest edo mezu-laburpenak (hash funtzioak bezala ezagunagoak), datu-bloke baten marka digitala dira. Laburpen horiek prozesatzeko algoritmo ugari daude diseinatuta, SHA-1 eta MD5 dira ezagunenak.

Nabarmengarri ezaugarri hauek:

* Algoritmo bererako, laburpenak beti du tamaina bera, sortzeko erabili den datuen tamaina edozein dela ere.&#x20;
* Ezinezkoa da jatorrizko informazioa laburpen batetik berreskuratzea.&#x20;
* Hura sortzeko erabilitako daturik ez ditu sekula jasoko laburpenak.
* Konputazionalki bideraezina da laburpen bera duten bi mezu aurkitzea. Ikuspuntu matematikotik oso zaila den arren ez da ezinezkoa.&#x20;
* Laburtzeko diren datuen aldaketa txiki batek laburpen guztiz ezberdina sortuko du.

<mark style="background-color:blue;">Laburpenak identifikatzaile bakar eta fidagarriak sortzeko erabiltzen dira.</mark> Batzuetan, _checksum_ deitzen zaie. Deskarga bat ondo egin den egiaztatzeko erabiltzen dira, edo, inork manipulatu ez izanaren egiaztagiritzat: nahikoa da fitxategien jatorrizko laburpena eskuragai izatea eta jasotako fitxategiarekin sortu berriarekin alderatzea.

{% hint style="warning" %}
**Hash batek ez du zifratzeko balio, konparaketentzako bai ordea**

Garrantzitsua da nabarmentzea ezen, ezinezkoa denetik laburpenetik hura sortzeko erabilitako datuak berreskuratzea, laburpena ezin dela erabili informaziorik zifratzeko.

Bestelakoa da erabilera: konparaketak egitea. Pasahitzekin erabiltzen da gehien: datu-baseetan laburpena gordetzen baita, pasahitzaren ordez. Hala, pasahitz bat jasotzen denean, haren laburpena sortzen dute, eta gordetako balioarekin alderatzen!
{% endhint %}

### `MessageDigest` klasea

Aplikazioeetan kriptografikoki seguruak diren laburpen algoritmoak inplementatzeko klasea da: hala nola SHA-256, edo, SHA-512.

JCArekin hash bat sortzeko, hau egin behar da:

1. `MessageDigest` klaseko `getInstance()` metodo estatikoa erabiliz, `MessageDigest` instantzia edo objektua sortuko da parametro gisa aukeratu algoritmoaren izena zehaztuta. Nahi izanez gero, hornitzailearen izena zehaztuz egin daiteke.&#x20;
2. Datuak `update()` metodoarekin gehitzen dira. Byte bat edo byte-array bat gehi daiteke. Metodo hau behin baino gehiagotan erabil daiteke datu berriak gehitzeko.&#x20;
3. Hash balioa lortzeko `digest()` metodoa erabili.
4. Hash berri bat kalkulatu nahi izanez gero, `reset()` metodoa erabiltzea dago eta prozesua berriro hasi.

Esaterako:

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

#### Fitxategien laburpenak&#x20;

`GnuPG` metodo sortak  balio du testu soilen laburpenak baino fitxategi osoen hasha lortzeko.&#x20;

{% hint style="info" %}
**GnuPGn eskuragai dauden algoritmoak**

Erabili daitezkeen algoritmoen zerrenda ezagutzeko komando-lerroko aginduari eskatu behar zaio:

> gpg --help

Goikaldean ageriko dira zerbitzu bakoitzarentzat erabilgarri dituen algoritmoak. Laburpenak sortzerako:\
Resumen: SHA1, RIPEMD160, SHA256, SHA384, SHA512, SHA224
{% endhint %}

Fitxategi baten laburpena edo hash kodea lortuko da komando hau sartuta (aukeran norberak nahi lukeen algoritmoa):

```powershell
gpg --print-md SHA256 fitxategia.luzapena
```
