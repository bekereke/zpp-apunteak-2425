---
icon: '2'
description: MULTIATAZA
---

# Hari anitzeko programazioa

<details>

<summary><mark style="color:purple;"><strong>Ikaskuntza Emaitza</strong></mark></summary>

### <mark style="color:purple;">IE 2. Hainbat exekuzio-hari dituzten aplikazioak garatzea, programazio-lengoaiaren berariazko liburutegiak aztertuz eta aplikatuz.</mark>

<mark style="color:purple;">Ondoko lorpen-adierazleekin frogatuta:</mark>

<mark style="color:purple;">a) Programa baten hainbat hari erabiltzea baliagarria den egoerak identifikatu ditu.</mark>&#x20;

<mark style="color:purple;">**b) Hariak sortzeko, hasteko eta amaitzeko mekanismoak ezagutu ditu.**</mark>&#x20;

<mark style="color:purple;">**c) Hainbat hari inplementatzen dituzten aplikazioak programatu ditu.**</mark>&#x20;

<mark style="color:purple;">d) Hari baten balizko exekuzio-egoerak identifikatu ditu eta horiek kudeatzen dituzten aplikazioak programatu ditu.</mark>&#x20;

<mark style="color:purple;">**e) Prozesu bereko hainbat hariren artean informazioa partekatzeko mekanismoak erabili ditu.**</mark>

<mark style="color:purple;">**f) Berariazko tekniken bitartez sinkronizatutako hainbat hari dituzten programak garatu ditu.**</mark>&#x20;

<mark style="color:purple;">g) Exekuzio-harietako bakoitzaren lehentasuna ezarri eta kontrolatu du.</mark>&#x20;

<mark style="color:purple;">h) Garatutako programak araztu eta dokumentatu ditu.</mark>

</details>

***

Hari bat da exekuzio unitate txikiena programa baten barruan. Hariak funtsezkoak dira programazio konkurrenterako, eta programa batek zeregin asko egin ditzake aldi berean, paraleloan, itxuraz. Hari bakoitza bere aldetik doa, bere kontrol- eta programa-kontagailuarekin, baina prozesu beraren barruko hariek oroimen-espazio eta baliabide berberak partekatzen dituzte. Baliabideen banaketa horrek exekuzio konkurrentea ekar dezake, non hari anitzek kode-segmentuak aldi berean exekutatu ditzaketen.

Harien erabilerak hainbat onura eskaintzen ditu:

1. **Paralelismoa**: Hariek aukera ematen diete programei aldi berean hainbat zeregin egiteko, eta horrek nabarmen hobetu dezake errendimendua nukleo anitzeko prozesadoreetan.
2. **Erantzun-gaitasuna**: Hariak erabiltzaileen interfazeetan erabiltzen dira, aplikazio batek erabiltzailearen ekarpenari erantzuten diola bermatzeko, atzeko lanak egiten dituen bitartean.
3. **Baliabideak partekatzea**: hariek modu eraginkorrean parteka ditzakete datuak eta baliabideak prozesu bakar batean, prozesuen arteko komunikazioaren gastu orokorrak saihestuz.
4. **Programazio sinplifikatua**: Hariek garatzaileei modu naturalagoan adierazteko aukera ematen diete, eta, horrela, errazagoa da lanak batera egiten dituzten programak idaztea.

Funtsezkoa da sinkronizazio eta koordinazio mekanismo egokiak erabiltzea hariekin lan egitean, programa konkurrente baten fidagarritasuna eta zuzentasuna bermatzeko. Hala ere, garrantzitsua da azpimarratzea hariak maneiatzea konplexua izan daitekeela, hainbat gai sar ditzaketelako: arrazaren baldintzak, blokeoak... eta programazioaren konplexutasuna handitzea.

Hona hemen hariei lotutako gai komun batzuk:

1. **Lasterketa baldintzak**: Arrazaren baldintzak gertatzen dira hari anitzak datu partekatuetara aldi berean sartzen direnean, eta emaitza exekuzio unearen eta ordenaren araberakoa da. Horrek pentsaezinezko portaera okerra ekar dezake.
2. **Blokeoak**: Bi hari edo gehiago ez daudenean gertatzen dira blokeoak, bakoitza bestearen zain dagoelako baliabide edo giltzarrapo bat askatzeko. Horrek programa bat erantzun gabe geratzea ekar dezake.
3. **Besarkadak**: _Livelocks_ gisa ezagutuak, blokeoen antzekoak dira, baina hariak elkarri eragitean jaso ohi dira: behin eta berriz sartzen dira aurrera egin ezin duten egoeran, bata bestearen itxaroan.
4. **Gosetea**: hari bat behar duen baliabide bat eskuratzeko gai ez denean gertatzen da, beste hari batzuek etengabe monopolizatzen dutelako. Horrek errendimendua murriztea edo blokeoa ere ekar dezake.
5. **Sarrailak**: Sarrailak bezalako sinkronizazio mekanismoak (adibidez, semaforoak) karga erantsia dira, eta errendimenduan gainbehera egin dezakete; programaren eraginkortasuna ahuldu.
6. **Konplexutasuna**: Programa multiharidunak konplexuagoak izaten dira diseinatu, inplementatu eta arazteko, programa isolatuekin alderatuta. Konplexutasun horrek errore joera handiagoa eman diezaieke.
7. **Egoera ez determinismista**: litekeena da erabakiorra ez izatea programa multiharidun batean haria exekutatzeko ordena, baina arazo iturri bihurtu daiteke, kodea arazteko garaian ere.
8. **Baliabideen eztabaida**: hariak baliabide finituak lortzeko lehiatu daitezke, hala nola CPU denbora, memoria edo S/I eragiketak, eraginkortasunik ezak eta errendimendu-itoguneak eragin ditzaketenak.
9. **Eskalagarritasuna**: hariek errendimendua hobetu dezaketen bitartean nukleo anitzeko prozesadoreetan, eskuragarri dauden nukleoak erabat erabil ditzaketen programak diseinatzea eta eraginkortasunez eskalatzea lan konplexua izan daiteke.

Arazo horiek arintzeko, garatzaileek sinkronizazio-teknika egokiak aplikatu behar dituzte, programa multiharidunak kontu handiz diseinatu, eta konmonuak kontrolatzeko mekanismoak erabili, hala nola sarrailak, semaforoak eta monitoreak. Gainera, programazio-lengoaia eta liburutegi modernoek tresnak eta abstrakzioak eskaintzen dituzte harien kudeaketa sinplifikatzeko eta gai horien egiantza murrizteko.

## Bizi-zikloa

Hari baten bizi-zikloa bere egoera ezberdinen arabera deskriba daiteke. Hariaren egoera honako hau da:

1. **NEW**: Haria `NEW` egoeran egongo da sortu denean baina oraindik ez denean abiarazi. Honela, instantzia edo kopia sortu da baina `start()` metodoa deitu arte zain jarraituko du.
2. **RUNNABLE**: Haria `RUNNABLE` egoeran dago abiatzeko prest dagoenean, baina sistemako planifikatzaileak oraindik ez du hautatu exekutatzera igarotzeko. CPUren zain egon daiteke, eragiketaren baten zain, edo, beste baliabide batzuen zain.
3. **BLOCKED**: Hari bat `BLOCKED` egoeran sartzen da lanpeturik dagoen baliabide bat lortu nahian dabilelarik. Zain egongo da harik eta askatu arte. Ondoren, `RUNNABLE` egoerara itzuliko da.
4. **WAITING**: Hari bat itxaronaldian sartzen da baldintza zehatzen baten zain dagoenean. `wait()`, `join()` edo `park()` metodoek eragin dezakete. Egoera honetan dauden hariak beste hari batzuekin iratzar daitezke, itxaronaldian zeuzkaten baldintzak asetzean.
5. **TIMED\_WAITING**: `WAITING` itxaronaldiaren antzekoa da, baina honakoan epemuga dauka: `TIMED_WAITING` egoeran baldintza zehatz baten zain egongo da haria, eta baldintza asetzean zein bestela epea agortzean itzuliko da `RUNNABLE` egoerara. Kasu honetan ere metodoen deiengatik sartu daiteke haria `TIME_WAITING` egoeran: `sleep()`, edo, `join()`; epemuga atributu gisa jasoz.
6. **TERMINATED**: Hari bat `TERMINATED` egoeran sartzen da exekuzioa amaitu duenean edo berariaz geldiarazi dutenean. Behin hari bat egoera honetan dagoelarik, ezin da berriro abiarazi.

Hona hemen hari baten bizi-zikloaren irudikapen sinplifikatua:

<img src="../.gitbook/assets/file.excalidraw (2).svg" alt="" class="gitbook-drawing">

Garrantzitsua da hari egoera horiek ulertzea harien portaera eraginkortasunez kudeatu eta kontrolatzeko. Sinkronizazio egokia, koordinazioa eta egoeren kudeaketa funtsezkoak dira aplikazio multiharitsu fidagarriak idazteko eta lasterketa baldintzak eta blokeoak bezalako arazoak saihesteko.

## Prozesuen eta harien arteko aldeak

| Alderdiak                 | Prozesua                                                                                                                            | Haria                                                                                                                  |
| ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| **Definizioa**            | Programa independentea baliabide eta memoria propioekin.                                                                            | Exekuzio unitaterik txikiena prozesu baten barruan, memoria eta baliabideak prozesu bereko beste hariekin partekatzen. |
| **Isolamentua**           | Prozesuak isolatuta daude. Exekuzio akatsek ez daukate besteengan eraginik.                                                         | Prozesu barruko hariak ez daude isolatuta. Hari baten erroreak prozesu osoa zapuztu dezake.                            |
| **Sorkuntza karga**       | Prozesu berri bat sortzeak baliabide asko eta denbora behar ditu.                                                                   | Hari berri bat sortzea azkarragoa da, eta ez du hainbeste eskatzen.                                                    |
| Komunikazioa              | Prozesuen arteko komunikaziorako mekanismoak (_IPC_) erabiltzen dira komunikaziorako.                                               | Hariak erraz komunikatzen dira memoria partekatuaren eta sinkronizazioaren bidez.                                      |
| **Konkurrentzia**         | Zeregin independenteak paraleloan egiteko egokia.                                                                                   | Programa bakar baten barruan konkurrentzia lortzeko eta datuak partekatzeko egokia.                                    |
| **Akatsei tolerantzia**   | <p>Akats gehiago. Prozesu bateko akats batek ez du besteengan eraginik izaten.</p><p></p>                                           | Hari bateko akatsak prozesu osoa zapuztu dezake.                                                                       |
| **Testuinguru aldaketak** | Prozesuen testuinguru aldatzeak egoera gorde zein berreskuratzeko karga astunagoak dakartza, memoria  bananduak izatearen ondorioz. | Harien testuinguru aldaketak bizkorragoak eta kargaz arinagoak izan ohi dira, memoria partekatzeagatik .               |

## Eragiketa atomikoak

Operazio atomikoa <mark style="background-color:blue;">lan unitate bakar eta zatiezin gisa gauzatzen den eragiketa</mark> da. Atomikotasunak ziurtatzen du eragiketa bere osotasunean tratatzen dela eta ez dela beste hari batzuen bidez eteten edo interferitzen. Ezaugarri hau funtsezkoa da ingurune multiharidunetan lasterketa baldintzak saihestu eta datuen osotasuna bermatzeko.

## Sekzio kritikoa

Sekzio kritikoa programa baten zati izendatua da, hari edo prozesu bakar batek aldi berean gauza dezakeena. Elkarri trabak ekiditzeko (besarkada egoera), datuen osotasuna eta sinkronizazioa bermatzeko erabiltzen da. Sekzio kritikoak sinkronizazio-mekanismoek babesten dituzte, adibidez, sarrailek (monitoreak eta semaforoak), lasterketa baldintzak saihesteko eta programaren zuzentasuna mantentzeko.
