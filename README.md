---
description: ikasturtea 2024-2025 | irakaslea AITOR ARETXAGA
cover: >-
  .gitbook/assets/Pink and Purple Gradient Playful Illustrative Computer Class
  Google Classroom Header(1).png
coverY: 0
layout:
  cover:
    visible: true
    size: full
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: false
  pagination:
    visible: true
---

# Atarikoa

[![GitBook](https://img.shields.io/static/v1?message=Documented%20on%20GitBook\&logo=gitbook\&logoColor=ffffff\&label=%20\&labelColor=5c5c5c\&color=3F89A1)](https://www.gitbook.com/preview?utm_source=gitbook_readme_badge\&utm_medium=organic\&utm_campaign=preview_documentation\&utm_content=link)

## Atarikoa

Atari honetan eskuragarri duzu dokumentazioa _UNI Eibar-Ermua_ ikastetxeko **Plataforma anitzeko aplikazioen garapena (PAAG)** zikloko bigarren mailakoa den **Zerbitzuen eta prozesuen programazioa** ikasgairako.

Bost ataletan bereiztuko dira edukiak, bi erronkatan integratzekoak:

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th data-type="content-ref"></th><th data-hidden data-card-cover data-type="files"></th></tr></thead><tbody><tr><td>Atal honetan sistema eragileetan prozesuak nola sortzen, exekutatzen eta kontrolatzen diren aztertuko da. Prozesuak dira sistemaren baliabideak erabiltzen dituzten unitate independenteak. Ikasiko duzue prozesu berriak sortzen (<code>fork</code>, <code>exec</code>, etab.), itxaroten haiek amaitu arte (<code>wait</code>), eta komunikatzen prozesuen artean (pipes, seinaleak, memoria partekatua). Gainera, prozesuen sinkronizazioa eta arteko erlazioak (guraso-haur prozesuak) aztertuko dira, baita komunikazioan sortu daitezkeen arazoak ere.</td><td><a href="prozesu-anitzeko-programazioa/">prozesu-anitzeko-programazioa</a></td><td><a href=".gitbook/assets/1 (1).png">1 (1).png</a></td></tr><tr><td>Hariak prozesu baten barruan exekutatzen diren unitate arinak dira, eta haiek ez bezala, baliabideak partekatzen dituzte. Komunikazioa errazten du horrek, baina datuen osotasuna konplikatzen. Atal honetan, hariak sortzeko eta kudeatzeko moduak aztertuko dituzue (esaterako, <code>pthread</code> liburutegia erabilita). Datuen osotasuna bermatzeko beharrezkoak diren sinkronizazio-mekanismoak landuko dituzue (semaforo, mutex), baita lehiaketa-baldintzak eta blokeoak saihesteko teknikak ere. Hari anitzeko programazioa aplikazioen errendimendua hobetzeko erabiltzen da, baina diseinu egokia behar du exekuzio garaiko arazoak saihesteko.</td><td><a href="hari-anitzeko-programazioa/">hari-anitzeko-programazioa</a></td><td><a href=".gitbook/assets/Pantaila-argazkia 2025-06-17 131135.png">Pantaila-argazkia 2025-06-17 131135.png</a></td></tr><tr><td>Softwarearen segurtasuna funtsezkoa da. Atal honek arrisku arruntak eta horiek saihesteko teknikak aztertzen ditu. Barne hartzen ditu sarrera-egiaztapena, buffer overflow saihestea, datuen zifratzea eta autentikazioa. Halaber, erabiltzailearen datuak babesteko praktika egokiak lantzen dira, eta segurtasun-arazoak saihesteko kodearen egituraketa gomendioak ematen dira. Helburua aplikazio sendo eta erasoei aurre egiteko gai direnak eraikitzea da. Baita ere kodigoa entregatzeko garairako bermeak; inork aldatu ez izanarenak, alegia. </td><td><a href="programazio-seguruko-teknikak/">programazio-seguruko-teknikak</a></td><td><a href=".gitbook/assets/3.png">3.png</a></td></tr><tr><td>Programa batek beste batekin sarearen bidez komunikatzeko gaitasuna aztertzen da hemen. Protokolo nagusiak (TCP, UDP) eta horien erabilera azaltzen dira. Socket bidezko komunikazioa nola ezarri eta kudeatu ikasten da: zerbitzariak eta bezeroak nola elkarreragin dezaketen. Blokeatze egoerak eta mezuen trukaketa eraginkorra lortzeko praktika onak lantzen dira, baita konexioak nola kudeatu eta itxi ere.</td><td><a href="sare-komunikazioak/">sare-komunikazioak</a></td><td><a href=".gitbook/assets/Zerbitzari konkurrenteak.png">Zerbitzari konkurrenteak.png</a></td></tr><tr><td>Atal honetan sarean oinarritutako zerbitzuak garatzeko eta erabiltzeko gaitasunak garatzen dira. Zerbitzu ezagunak, hala nola FTP, eta horien protokoloak aztertzen dira. Halaber, bezero-zerbitzari arkitektura oinarri hartuta, nola diseinatu eta inplementatu propioak diren sareko zerbitzuak. Konexio kudeaketa, erabiltzaileen identifikazioa eta datuen transferentzia eraginkorra dira gako nagusiak.</td><td><a href="sareko-zerbitzuak/">sareko-zerbitzuak</a></td><td><a href=".gitbook/assets/5.jpg">5.jpg</a></td></tr></tbody></table>
