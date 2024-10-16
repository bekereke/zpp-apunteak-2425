---
icon: '3'
---

# Programazio seguruko teknikak

<details>

<summary>Ikaskuntza emaitza</summary>

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

Oro har, segurua izan nahi duen edozein sistemak zifraketa teknikak erabili beharko ditu.

## Programazio segururako praktikak

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

## Zesar zifratze-sistema

Mezuak etsaiak harrapatu arren ulerkaitza izango zen eran adierazteko asmatu zuten, eta era errazean berreskuratu ahal izateko jatorrizkoa. Alfabetoko hizki guztiak posizio batean mugitzean datza eta ordenaren arabera mezuan sasi-alfabeto berrian transkribatzean:

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

