---
description: MULTIPROGRAMAZIOA
icon: '1'
---

# Prozesu anitzeko programazioa

<details>

<summary><mark style="color:purple;"><strong>Ikaskuntza Emaitza</strong></mark></summary>

### <mark style="color:purple;">IE 1. Hainbat prozesuz osatutako aplikazioak garatzea, eta programazio paraleloko printzipioak ezagutzen eta aplikatzen.</mark>

<mark style="color:purple;">Ondoko lorpen-adierazleekin frogatuta:</mark>

<mark style="color:purple;">a) Programazio konkurrentearen ezaugarriak eta aplikazio-esparruak ezagutu ditu.</mark>&#x20;

<mark style="color:purple;">b) Programazio paraleloaren eta programazio banatuaren arteko desberdintasunak eta horien alde onak eta txarrak identifikatu ditu.</mark>&#x20;

<mark style="color:purple;">c) Prozesuen ezaugarriak aztertu ditu, baita sistema eragileak horiek exekutatzearen ezaugarriak ere.</mark>&#x20;

<mark style="color:purple;">d) Exekuzio-hariak ezaugarritu ditu, eta prozesuekin duten erlazioa deskribatu du.</mark>&#x20;

<mark style="color:purple;">**e) Klaseak erabili ditu azpiprozesuak sortzen dituzten aplikazioak programatzeko.**</mark>&#x20;

<mark style="color:purple;">**f) Hasitako azpiprozesuek itzulitako balioa lortzeko eta sinkronizatzeko mekanismoak erabili ditu.**</mark>&#x20;

<mark style="color:purple;">**g) Hainbat ataza aldi berean exekutatzeko prozesuak kudeatzen eta erabiltzen dituzten aplikazioak garatu ditu.**</mark>&#x20;

<mark style="color:purple;">h) Garatutako aplikazioak araztu eta dokumentatu ditu.</mark>

</details>

***

Lehenengo kapituluan aztertuko dugu zer den programazio konkurrentea, zer prozesu diren, zer egoera izan ditzaketen, eta nola garatu eta exekutatu Windows ingurune batean Java lengoaia erabiliz. Linux ingurunerako ere C lengoaiarekin adibide batzuk ikusiko ditugu.&#x20;

## Zer da prozesu bat?

Prozesu informatiko bat ordenagailu baten sistema eragilean exekutatzen ari den programa bati edo programa-multzo bati dagokio. Prozesu bat programa informatiko baten adibide bat da, martxan dagoena eta identitate bakarra duena (ID), bere memoria espazioa, sarrera/irteerako datu korronteak eta egoera barne.

Sistema eragile baten prozesuak kudeatzeko sistema prozesu horien exekuzioa kudeatzeaz arduratzen da, sistemaren baliabideak esleituz, hala nola denbora, memoria eta sarrera-/irteera-gailuak. Sistema eragilearen nukleoak prozesu desberdinen exekuzioa programatzen du, haien lehentasunen arabera, eta haien arteko elkarrekintzak eta komunikazioa kudeatzen ditu.

Prozesuak hainbat kategoriatan sailka daitezke, portaeraren eta ezaugarrien arabera, hala nola, lehen planoko eta atzeko prozesuak, sistema eta erabiltzaile-prozesuak, eta prozesu elkarreragileak eta loteak.

Prozesu batek, eskuarki, bere bizitzan zehar hainbat etapa igaro ohi ditu, besteak beste, sorkuntza, exekuzioa, etendura eta amaiera.

<figure><img src="https://737682242-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F1fkTiBk8oxbo9vMUdfVS%2Fuploads%2Fgit-blob-d61bd60c9d2d7cdd5f0498115476765ea1d1ffc7%2FProcess%20States.drawio.svg?alt=media" alt=""><figcaption><p>Prozesuen egoerak</p></figcaption></figure>

Estatuen arteko trantsizioak honako hauek dira:

* Exekutatu - Itxaron/Blokeatu: prozesu-trantsizio bat, korrika egitetik itxarotera/blokeatzera, kanpoko gertaera bat noiz gertatuko zain dagoenean.
* Itxaron/Blokeatu - Prest: Itxaron/blokeatu prozesu-trantsizio bat, espero den kanpo-gertaera gertatzen denean prest egoteko.
* Prest, martxan: prozesu-trantsizio bat prest, sistemak CPUko denbora esleitzen dionean.
* Exekutatu - Prest: prozesu-trantsizio bat, prozesurako sistema eragileak esleitutako denbora igaro denean.

<details>

<summary><em>Deabruak</em> edo zerbitzuak</summary>

Deabrua edo _Daemon_ prozesu bat sakoneko prozesu mota bat da, etengabe bigarren planoan doana eta sistema batean lan batzuk egiten dituena. Erabiltzaileekin elkarreraginean aritzeko eta kontroleko terminal bat izateko diseinatuta dauden lehen planoko prozesu erregularrak ez bezala, daemon prozesuak erabiltzailearen interakziorik edo kontroleko terminalik gabe funtzionatzeko diseinatuta daude.

Daemon prozesuak sistema-mailako zereginetarako erabili ohi dira, hala nola sare-eskaerak kudeatzeko, sistemaren baliabideak kudeatzeko eta segurtasun-kopia automatizatuak egiteko. Askotan automatikoki hasten dira sistema martxan jartzen den unean eta etengabe funtzionatzen dute sistema itxi arte.

Daemon prozesu baten ezaugarri nagusietako bat da terminaletik askatuta dagoela eta edozein erabiltzaile-saiotatik aparte funtzionatzen duela. Horrek esan nahi du erabiltzaileak saioa eten edo itxi arren, daemon prozesuak bigarren mailan jarraitzen duela. Gainera, daemon prozesuek pribilegio handiak izaten dituzte sistema-mailako zereginak egiteko, hala nola sistema babestuen fitxategietara sartzeko edo maila baxuko hardware-baliabideekin elkarreragiteko.

Unix-antzeko sistemetako daemon prozesuen adibide batzuk hauek dira: `sshd` (SSH daemon), `pdpd` (Apache web zerbitzaria daemon) eta `cron` (programatutako lanak egiten dituen daemon prozesua). Windows sistemetan, ostera, zerbitzu izena jasotzen dute eta _Windows Task Manager_ (CTRL+ALT+SUP) kontsultatu daitezke. Esaterako: **Active Directory Service** edo **Prefetch and Superfetch Service.**

</details>

### Prozesuen sarrera eta irteera estandarrak

Prozesu batek sarrera estandarra du (`stdin`), irteera estandarra (`stdout`) eta irteera estandarra errorea (`stderr`).

<figure><img src="https://737682242-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F1fkTiBk8oxbo9vMUdfVS%2Fuploads%2Fgit-blob-9b35987e0752c0c6694d4bb30ac1224fe193cf7b%2Fstandard%20streams.svg?alt=media" alt=""><figcaption><p>Komunikabide estandarrak</p></figcaption></figure>
