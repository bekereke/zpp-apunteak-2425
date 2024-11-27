---
icon: '4'
description: APLIKAZIO BANATUEN PROGRAMAZIOA
---

# Sare komunikazioak

<details>

<summary><mark style="background-color:purple;">Ikaskuntza emaitzak</mark></summary>

### <mark style="color:purple;">IE 3. Sareko komunikazioko mekanismoak programatzea, socketak erabiliz eta exekuzio-agertokia aztertuz.</mark>

<mark style="color:purple;">a) Hainbat aplikazioren artean sareko komunikazioa ezartzea eskatzen duten agertokiak identifikatu ditu.</mark>&#x20;

<mark style="color:purple;">b) Bezeroaren eta zerbitzariaren rolak eta horiekin lotzen diren funtzioak identifikatu ditu.</mark>&#x20;

<mark style="color:purple;">c) Sareko aplikazioak programatzeko aukera emango duten programazio-lengoaiaren mekanismoak eta liburutegiak ezagutu ditu.</mark>&#x20;

<mark style="color:purple;">d) “Socket” kontzeptua, motak eta ezaugarriak aztertu ditu.</mark>&#x20;

<mark style="color:purple;">e) Zerbitzari batekin komunikatzen den bezero-aplikazio bat programatzeko socketak erabili ditu.</mark>&#x20;

<mark style="color:purple;">f) Sareko zerbitzari-aplikazio bat garatu du, eta haren funtzionamendua egiaztatu du.</mark>&#x20;

<mark style="color:purple;">g) Informazioa trukatzeko socketak erabiltzen dituzten aplikazioak garatu ditu.</mark>&#x20;

<mark style="color:purple;">h) Sareko komunikazioari buruzko aplikazioen prozedurak inplementatzeko hariak erabili ditu.</mark>

</details>

***

Sareko komunikazioak dira gailuei eta konputagailuei konektatzeko, datuak partekatzeko eta baliabideetara sartzeko aukera ematen dien oinarrizko egitura. Mundu digitalaren oinarria da, eta web-nabigaziotik lineako jokoetara eta urrutiko lanera joateko aukera ematen du.

Sarearen komunikazioan protokoloak, hardwarea eta segurtasun-neurriak daude, eta, horiei esker, datuak truka daitezke. Osagai garrantzitsuen artean daude Interneteko Protokoloa (IP), Transmisioa Kontrolatzeko Protokoloa (TCP) eta Erabiltzailearen Datagrama Protokoloa (UDP). Eremu hori dinamikoa da, eta 5G sareek are konektagarritasun azkarragoa eskaintzen dute IoT eta errealitate areagotua bezalako berrikuntzetarako.

Sareko komunikazioei begiratzen diegun bitartean, haien oinarrizko printzipioak, datuen transmisioa eta administratzaileek eta garatzaileek sareko komunikazioen eraikuntzan eta ulermenean duten zeregina aztertuko ditugu.

{% hint style="success" %}
**Prozesuak eta hariak**

Ordenagailu-sare baten bidez konexioak eta komunikazioak erabiltzekoa den programa banatua egiteko, ez gara hutsetik abiatuko dagoeneko.

Sareko programazioa oso lotuta dago prozesu anitzeko programazioarekin ([1.gaia](../prozesu-anitzeko-programazioa/)). Batez ere, [prozesuen artean ikusi dugun komunikazio](../prozesu-anitzeko-programazioa/1.4-prozesuak-komunikatzea.md) moduarekin.

Bestalde, zerbitzari batek eskaintzen duen espezializazioa eta zerbitzua, aldi berean hainbat bezerori emateko gai dena, lana harietan banatuz egiten du ([2.gaia](../hari-anitzeko-programazioa/)).

Esandako guztiagatik, orain arte ikasitako kontzeptu eta ezagutza guztiak oinarri gisa erabiliko ditugu gai honen "haria" ez galtzeko.
{% endhint %}

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-type="content-ref"></th></tr></thead><tbody><tr><td><ol><li>GAIA Multiprogramazioa</li></ol></td><td>Prozesu anitzeko programazioa</td><td><a href="../prozesu-anitzeko-programazioa/">prozesu-anitzeko-programazioa</a></td></tr><tr><td>1.4 ATALA Prozesuen fluxuak nahieran maneiatzea</td><td>Prozesuen arteko komunikazioa</td><td><a href="../prozesu-anitzeko-programazioa/1.4-prozesuak-komunikatzea.md">1.4-prozesuak-komunikatzea.md</a></td></tr><tr><td><ol start="2"><li>GAIA Multiataza</li></ol></td><td>Hari anitzeko programazioa</td><td><a href="../hari-anitzeko-programazioa/">hari-anitzeko-programazioa</a></td></tr></tbody></table>



## `java.net` bilduma

Javako  `java.net` bilduma sareko aplikazioak inplementatzeko klaseak eskaintzen ditu. Pakete hau bi ataletan banatu daiteke:

### Maila baxuko APIa:

1. **Helbideak**: Sare-identifikatzaileekin jarduteko baliabideak biltzen ditu hemen, hala nola, IP helbideekin. Aipagarria da `InetAddress` klasea; horrek IP helbide bat adierazten du eta horri buruzko informazioa lortzeko metodoak eskaintzen ditu; esaterako, ekipo izenaren (_hostname_) ebazpena.
2. **Socketak**: Dagoeneko dakizunez, datuak bi norabidetan komunikatzeko oinarrizko mekanismoak dira socketak, eta oinarrizkoak dira sareetan. Javak `Socket` eta `ServerSocket` klaseak ematen ditu sareko komunikazioa inplementatzeko TCP (Transmission Control Protocol) sockets erabiliz eta `DatagramSocket`  UDP (User Datagram Protocol) oinarridun komunikaziorako.
3. **Interfazeak**: Klase hauek sare-interfazeak deskribatzen dituzte eta sisteman eskuragarri dauden sare-interfazeei buruzko informazioa ematen dute. Atal honetan `NetworkInterface` klaseko klase bat erakusten da.

### Goi mailako APIa:

1. **URI (Uniform Resource Identifier)**: Baliabide unibertsalen identifikatzaileen alorreko klaseak eta metodoak biltzen ditu. `URI` klaseak URIak sortzeko, banatzeko eta manipulatzeko metodoak eskaintzen ditu, webean eta beste sistema batzuetan baliabideak identifikatzeko erabiltzen direnak.
2. **URLak (Uniform Resource Locators)**: URLek baliabide unibertsalen lokalizatzaileak irudikatzen dituzte, eta webguneko baliabideetara sartzeko erabiltzen dira. `URL` klaseak URLak sortzeko eta manipulatzeko aukera ematen du.
3. **Konexioak**: URLetan adierazitako baliabideekiko konexioak biltzen ditu. URLC onnection bezalako klaseak erabil ditzakezu URLen bidez erreferentziatutako baliabideetarako konexioak ireki eta kudeatzeko, baliabide horietatik eta haietara datuak irakurri eta idazteko aukera emanez.

`java.net` paketeak eskaintzen dituen klase eta abstrakzio horiek funtsezkoak dira Javan sareko aplikazioak garatzeko. Socketen bidez komunikatzeko, IP helbideekin lan egiteko edo URLen bidez web baliabideetara sartzeko, sare-aplikazio ugari garatzeko beharrezko tresnak eskaintzen dituen paketea da.

## `URLConnection` adibidea

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStream;
import java.io.InputStreamReader;
import java.net.MalformedURLException;
import java.net.URL;
import java.net.URLConnection;
/**
 *
 * @author Urko
 */
public class WebPageCodeVisualize {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) throws MalformedURLException, IOException {
        // TODO code application logic here
        URLConnection urlCon;
        URL url;
        url = new URL("https://www.uni.eus");
        urlCon = url.openConnection();
        BufferedReader in;
        InputStream inputStream = urlCon.getInputStream();
        in = new BufferedReader(new InputStreamReader(inputStream));
        String inputLine;
        while ((inputLine = in.readLine()) != null) {
            System.out.println(inputLine);
        }
        in.close();
    }
}
```

<details>

<summary>Irteera:</summary>

```html
run:
<!doctype html><html lang="eu"><head><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0"><meta name="description" content="Uni Eibar-Ermua"><link rel="pingback" href="https://www.uni.eus/xmlrpc.php" /><link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css" integrity="sha512-iBBXm8fW90+nuLcSKlbmrPcLa0OT92xO1BIsZ+ywDWZCvqsWgccV3gFoRBv0z+8dLJgyAHIhR35VZc2oM/gI1w==" crossorigin="anonymous" /><title>Uni &#8211; Uni Eibar-Ermua</title><meta name='robots' content='max-image-preview:large' /><link rel="alternate" href="https://www.uni.eus/eu/" hreflang="eu" /><link rel="alternate" href="https://www.uni.eus/es/" hreflang="es" /><link rel="alternate" href="https://www.uni.eus/" hreflang="x-default" /><link rel='dns-prefetch' href='//fonts.googleapis.com' /><link rel="alternate" type="application/rss+xml" title="Uni &raquo; Jarioa" href="https://www.uni.eus/eu/feed/" /><link rel="alternate" type="application/rss+xml" title="Uni &raquo; Iruzkinen jarioa" href="https://www.uni.eus/eu/comments/feed/" /> <script type="text/javascript">window._wpemojiSettings = {"baseUrl":"https:\/\/s.w.org\/images\/core\/emoji\/14.0.0\/72x72\/","ext":".png","svgUrl":"https:\/\/s.w.org\/images\/core\/emoji\/14.0.0\/svg\/","svgExt":".svg","source":{"concatemoji":"https:\/\/www.uni.eus\/wp-includes\/js\/wp-emoji-release.min.js?ver=6.4.1"}};
/*! This file is auto-generated */
!function(i,n){var o,s,e;function c(e){try{var t={supportTests:e,timestamp:(new Date).valueOf()};sessionStorage.setItem(o,JSON.stringify(t))}catch(e){}}function p(e,t,n){e.clearRect(0,0,e.canvas.width,e.canvas.height),e.fillText(t,0,0);var t=new Uint32Array(e.getImageData(0,0,e.canvas.width,e.canvas.height).data),r=(e.clearRect(0,0,e.canvas.width,e.canvas.height),e.fillText(n,0,0),new Uint32Array(e.getImageData(0,0,e.canvas.width,e.canvas.height).data));return t.every(function(e,t){return e===r[t]})}function u(e,t,n){switch(t){case"flag":return n(e,"\ud83c\udff3\ufe0f\u200d\u26a7\ufe0f","\ud83c\udff3\ufe0f\u200b\u26a7\ufe0f")?!1:!n(e,"\ud83c\uddfa\ud83c\uddf3","\ud83c\uddfa\u200b\ud83c\uddf3")&&!n(e,"\ud83c\udff4\udb40\udc67\udb40\udc62\udb40\udc65\udb40\udc6e\udb40\udc67\udb40\udc7f","\ud83c\udff4\u200b\udb40\udc67\u200b\udb40\udc62\u200b\udb40\udc65\u200b\udb40\udc6e\u200b\udb40\udc67\u200b\udb40\udc7f");case"emoji":return!n(e,"\ud83e\udef1\ud83c\udffb\u200d\ud83e\udef2\ud83c\udfff","\ud83e\udef1\ud83c\udffb\u200b\ud83e\udef2\ud83c\udfff")}return!1}function f(e,t,n){var r="undefined"!=typeof WorkerGlobalScope&&self instanceof WorkerGlobalScope?new OffscreenCanvas(300,150):i.createElement("canvas"),a=r.getContext("2d",{willReadFrequently:!0}),o=(a.textBaseline="top",a.font="600 32px Arial",{});return e.forEach(function(e){o[e]=t(a,e,n)}),o}function t(e){var t=i.createElement("script");t.src=e,t.defer=!0,i.head.appendChild(t)}"undefined"!=typeof Promise&&(o="wpEmojiSettingsSupports",s=["flag","emoji"],n.supports={everything:!0,everythingExceptFlag:!0},e=new Promise(function(e){i.addEventListener("DOMContentLoaded",e,{once:!0})}),new Promise(function(t){var n=function(){try{var e=JSON.parse(sessionStorage.getItem(o));if("object"==typeof e&&"number"==typeof e.timestamp&&(new Date).valueOf()<e.timestamp+604800&&"object"==typeof e.supportTests)return e.supportTests}catch(e){}return null}();if(!n){if("undefined"!=typeof Worker&&"undefined"!=typeof OffscreenCanvas&&"undefined"!=typeof URL&&URL.createObjectURL&&"undefined"!=typeof Blob)try{var e="postMessage("+f.toString()+"("+[JSON.stringify(s),u.toString(),p.toString()].join(",")+"));",r=new Blob([e],{type:"text/javascript"}),a=new Worker(URL.createObjectURL(r),{name:"wpTestEmojiSupports"});return void(a.onmessage=function(e){c(n=e.data),a.terminate(),t(n)})}catch(e){}c(n=f(s,u,p))}t(n)}).then(function(e){for(var t in e)n.supports[t]=e[t],n.supports.everything=n.supports.everything&&n.supports[t],"flag"!==t&&(n.supports.everythingExceptFlag=n.supports.everythingExceptFlag&&n.supports[t]);n.supports.everythingExceptFlag=n.supports.everythingExceptFlag&&!n.supports.flag,n.DOMReady=!1,n.readyCallback=function(){n.DOMReady=!0}}).then(function(){return e}).then(function(){var e;n.supports.everything||(n.readyCallback(),(e=n.source||{}).concatemoji?t(e.concatemoji):e.wpemoji&&e.twemoji&&(t(e.twemoji),t(e.wpemoji)))}))}((window,document),window._wpemojiSettings);</script> <style id='wp-emoji-styles-inline-css' type='text/css'>img.wp-smiley, img.emoji {
		display: inline !important;
		border: none !important;
		box-shadow: none !important;
		height: 1em !important;
		width: 1em !important;
		margin: 0 0.07em !important;
		vertical-align: -0.1em !important;
		background: none !important;
		padding: 0 !important;
	}</style><link rel='stylesheet' id='wp-block-library-css' href='https://www.uni.eus/wp-includes/css/dist/block-library/style.min.css?ver=6.4.1' type='text/css' media='all' /><style id='wp-block-library-theme-inline-css' type='text/css'>.wp-block-audio figcaption{color:#555;font-size:13px;text-align:center}.is-dark-theme .wp-block-audio figcaption{color:hsla(0,0%,100%,.65)}.wp-block-audio{margin:0 0 1em}.wp-block-code{border:1px solid #ccc;border-radius:4px;font-family:Menlo,Consolas,monaco,monospace;padding:.8em 1em}.wp-block-embed figcaption{color:#555;font-size:13px;text-align:center}.is-dark-theme .wp-block-embed figcaption{color:hsla(0,0%,100%,.65)}.wp-block-embed{margin:0 0 1em}.blocks-gallery-caption{color:#555;font-size:13px;text-align:center}.is-dark-theme .blocks-gallery-caption{color:hsla(0,0%,100%,.65)}.wp-block-image figcaption{color:#555;font-size:13px;text-align:center}.is-dark-theme .wp-block-image figcaption{color:hsla(0,0%,100%,.65)}.wp-block-image{margin:0 0 1em}.wp-block-pullquote{border-bottom:4px solid;border-top:4px solid;color:currentColor;margin-bottom:1.75em}.wp-block-pullquote cite,.wp-block-pullquote footer,.wp-block-pullquote__citation{color:currentColor;font-size:.8125em;font-style:normal;text-transform:uppercase}.wp-block-quote{border-left:.25em solid;margin:0 0 1.75em;padding-left:1em}.wp-block-quote cite,.wp-block-quote footer{color:currentColor;font-size:.8125em;font-style:normal;position:relative}.wp-block-quote.has-text-align-right{border-left:none;border-right:.25em solid;padding-left:0;padding-right:1em}.wp-block-quote.has-text-align-center{border:none;padding-left:0}.wp-block-quote.is-large,.wp-block-quote.is-style-large,.wp-block-quote.is-style-plain{border:none}.wp-block-search .wp-block-search__label{font-weight:700}.wp-block-search__button{border:1px solid #ccc;padding:.375em .625em}:where(.wp-block-group.has-background){padding:1.25em 2.375em}.wp-block-separator.has-css-opacity{opacity:.4}.wp-block-separator{border:none;border-bottom:2px solid;margin-left:auto;margin-right:auto}.wp-block-separator.has-alpha-channel-opacity{opacity:1}.wp-block-separator:not(.is-style-wide):not(.is-style-dots){width:100px}.wp-block-separator.has-background:not(.is-style-dots){border-bottom:none;height:1px}.wp-block-separator.has-background:not(.is-style-wide):not(.is-style-dots){height:2px}.wp-block-table{margin:0 0 1em}.wp-block-table td,.wp-block-table th{word-break:normal}.wp-block-table figcaption{color:#555;font-size:13px;text-align:center}.is-dark-theme .wp-block-table figcaption{color:hsla(0,0%,100%,.65)}.wp-block-video figcaption{color:#555;font-size:13px;text-align:center}.is-dark-theme .wp-block-video figcaption{color:hsla(0,0%,100%,.65)}.wp-block-video{margin:0 0 1em}.wp-block-template-part.has-background{margin-bottom:0;margin-top:0;padding:1.25em 2.375em}</style><style id='classic-theme-styles-inline-css' type='text/css'>/*! This file is auto-generated */
.wp-block-button__link{color:#fff;background-color:#32373c;border-radius:9999px;box-shadow:none;text-decoration:none;padding:calc(.667em + 2px) calc(1.333em + 2px);font-size:1.125em}.wp-block-file__button{background:#32373c;color:#fff;text-decoration:none}</style><style id='global-styles-inline-css' type='text/css'>body{--wp--preset--color--black: #000000;--wp--preset--color--cyan-bluish-gray: #abb8c3;--wp--preset--color--white: #ffffff;--wp--preset--color--pale-pink: #f78da7;--wp--preset--color--vivid-red: #cf2e2e;--wp--preset--color--luminous-vivid-orange: #ff6900;--wp--preset--color--luminous-vivid-amber: #fcb900;--wp--preset--color--light-green-cyan: #7bdcb5;--wp--preset--color--vivid-green-cyan: #00d084;--wp--preset--color--pale-cyan-blue: #8ed1fc;--wp--preset--color--vivid-cyan-blue: #0693e3;--wp--preset--color--vivid-purple: #9b51e0;--wp--preset--gradient--vivid-cyan-blue-to-vivid-purple: linear-gradient(135deg,rgba(6,147,227,1) 0%,rgb(155,81,224) 100%);--wp--preset--gradient--light-green-cyan-to-vivid-green-cyan: linear-gradient(135deg,rgb(122,220,180) 0%,rgb(0,208,130) 100%);--wp--preset--gradient--luminous-vivid-amber-to-luminous-vivid-orange: linear-gradient(135deg,rgba(252,185,0,1) 0%,rgba(255,105,0,1) 100%);--wp--preset--gradient--luminous-vivid-orange-to-vivid-red: linear-gradient(135deg,rgba(255,105,0,1) 0%,rgb(207,46,46) 100%);--wp--preset--gradient--very-light-gray-to-cyan-bluish-gray: linear-gradient(135deg,rgb(238,238,238) 0%,rgb(169,184,195) 100%);--wp--preset--gradient--cool-to-warm-spectrum: linear-gradient(135deg,rgb(74,234,220) 0%,rgb(151,120,209) 20%,rgb(207,42,186) 40%,rgb(238,44,130) 60%,rgb(251,105,98) 80%,rgb(254,248,76) 100%);--wp--preset--gradient--blush-light-purple: linear-gradient(135deg,rgb(255,206,236) 0%,rgb(152,150,240) 100%);--wp--preset--gradient--blush-bordeaux: linear-gradient(135deg,rgb(254,205,165) 0%,rgb(254,45,45) 50%,rgb(107,0,62) 100%);--wp--preset--gradient--luminous-dusk: linear-gradient(135deg,rgb(255,203,112) 0%,rgb(199,81,192) 50%,rgb(65,88,208) 100%);--wp--preset--gradient--pale-ocean: linear-gradient(135deg,rgb(255,245,203) 0%,rgb(182,227,212) 50%,rgb(51,167,181) 100%);--wp--preset--gradient--electric-grass: linear-gradient(135deg,rgb(202,248,128) 0%,rgb(113,206,126) 100%);--wp--preset--gradient--midnight: linear-gradient(135deg,rgb(2,3,129) 0%,rgb(40,116,252) 100%);--wp--preset--font-size--small: 13px;--wp--preset--font-size--medium: 20px;--wp--preset--font-size--large: 36px;--wp--preset--font-size--x-large: 42px;--wp--preset--spacing--20: 0.44rem;--wp--preset--spacing--30: 0.67rem;--wp--preset--spacing--40: 1rem;--wp--preset--spacing--50: 1.5rem;--wp--preset--spacing--60: 2.25rem;--wp--preset--spacing--70: 3.38rem;--wp--preset--spacing--80: 5.06rem;--wp--preset--shadow--natural: 6px 6px 9px rgba(0, 0, 0, 0.2);--wp--preset--shadow--deep: 12px 12px 50px rgba(0, 0, 0, 0.4);--wp--preset--shadow--sharp: 6px 6px 0px rgba(0, 0, 0, 0.2);--wp--preset--shadow--outlined: 6px 6px 0px -3px rgba(255, 255, 255, 1), 6px 6px rgba(0, 0, 0, 1);--wp--preset--shadow--crisp: 6px 6px 0px rgba(0, 0, 0, 1);}:where(.is-layout-flex){gap: 0.5em;}:where(.is-layout-grid){gap: 0.5em;}body .is-layout-flow > .alignleft{float: left;margin-inline-start: 0;margin-inline-end: 2em;}body .is-layout-flow > .alignright{float: right;margin-inline-start: 2em;margin-inline-end: 0;}body .is-layout-flow > .aligncenter{margin-left: auto !important;margin-right: auto !important;}body .is-layout-constrained > .alignleft{float: left;margin-inline-start: 0;margin-inline-end: 2em;}body .is-layout-constrained > .alignright{float: right;margin-inline-start: 2em;margin-inline-end: 0;}body .is-layout-constrained > .aligncenter{margin-left: auto !important;margin-right: auto !important;}body .is-layout-constrained > :where(:not(.alignleft):not(.alignright):not(.alignfull)){max-width: var(--wp--style--global--content-size);margin-left: auto !important;margin-right: auto !important;}body .is-layout-constrained > .alignwide{max-width: var(--wp--style--global--wide-size);}body .is-layout-flex{display: flex;}body .is-layout-flex{flex-wrap: wrap;align-items: center;}body .is-layout-flex > *{margin: 0;}body .is-layout-grid{display: grid;}body .is-layout-grid > *{margin: 0;}:where(.wp-block-columns.is-layout-flex){gap: 2em;}:where(.wp-block-columns.is-layout-grid){gap: 2em;}:where(.wp-block-post-template.is-layout-flex){gap: 1.25em;}:where(.wp-block-post-template.is-layout-grid){gap: 1.25em;}.has-black-color{color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-color{color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-color{color: var(--wp--preset--color--white) !important;}.has-pale-pink-color{color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-color{color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-color{color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-color{color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-color{color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-color{color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-color{color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-color{color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-color{color: var(--wp--preset--color--vivid-purple) !important;}.has-black-background-color{background-color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-background-color{background-color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-background-color{background-color: var(--wp--preset--color--white) !important;}.has-pale-pink-background-color{background-color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-background-color{background-color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-background-color{background-color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-background-color{background-color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-background-color{background-color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-background-color{background-color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-background-color{background-color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-background-color{background-color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-background-color{background-color: var(--wp--preset--color--vivid-purple) !important;}.has-black-border-color{border-color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-border-color{border-color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-border-color{border-color: var(--wp--preset--color--white) !important;}.has-pale-pink-border-color{border-color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-border-color{border-color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-border-color{border-color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-border-color{border-color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-border-color{border-color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-border-color{border-color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-border-color{border-color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-border-color{border-color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-border-color{border-color: var(--wp--preset--color--vivid-purple) !important;}.has-vivid-cyan-blue-to-vivid-purple-gradient-background{background: var(--wp--preset--gradient--vivid-cyan-blue-to-vivid-purple) !important;}.has-light-green-cyan-to-vivid-green-cyan-gradient-background{background: var(--wp--preset--gradient--light-green-cyan-to-vivid-green-cyan) !important;}.has-luminous-vivid-amber-to-luminous-vivid-orange-gradient-background{background: var(--wp--preset--gradient--luminous-vivid-amber-to-luminous-vivid-orange) !important;}.has-luminous-vivid-orange-to-vivid-red-gradient-background{background: var(--wp--preset--gradient--luminous-vivid-orange-to-vivid-red) !important;}.has-very-light-gray-to-cyan-bluish-gray-gradient-background{background: var(--wp--preset--gradient--very-light-gray-to-cyan-bluish-gray) !important;}.has-cool-to-warm-spectrum-gradient-background{background: var(--wp--preset--gradient--cool-to-warm-spectrum) !important;}.has-blush-light-purple-gradient-background{background: var(--wp--preset--gradient--blush-light-purple) !important;}.has-blush-bordeaux-gradient-background{background: var(--wp--preset--gradient--blush-bordeaux) !important;}.has-luminous-dusk-gradient-background{background: var(--wp--preset--gradient--luminous-dusk) !important;}.has-pale-ocean-gradient-background{background: var(--wp--preset--gradient--pale-ocean) !important;}.has-electric-grass-gradient-background{background: var(--wp--preset--gradient--electric-grass) !important;}.has-midnight-gradient-background{background: var(--wp--preset--gradient--midnight) !important;}.has-small-font-size{font-size: var(--wp--preset--font-size--small) !important;}.has-medium-font-size{font-size: var(--wp--preset--font-size--medium) !important;}.has-large-font-size{font-size: var(--wp--preset--font-size--large) !important;}.has-x-large-font-size{font-size: var(--wp--preset--font-size--x-large) !important;}
.wp-block-navigation a:where(:not(.wp-element-button)){color: inherit;}
:where(.wp-block-post-template.is-layout-flex){gap: 1.25em;}:where(.wp-block-post-template.is-layout-grid){gap: 1.25em;}
:where(.wp-block-columns.is-layout-flex){gap: 2em;}:where(.wp-block-columns.is-layout-grid){gap: 2em;}
.wp-block-pullquote{font-size: 1.5em;line-height: 1.6;}</style><link rel='stylesheet' id='contact-form-7-css' href='https://www.uni.eus/wp-content/cache/autoptimize/css/autoptimize_single_3fd2afa98866679439097f4ab102fe0a.css?ver=5.8.3' type='text/css' media='all' /><link rel='stylesheet' id='rs-plugin-settings-css' href='https://www.uni.eus/wp-content/cache/autoptimize/css/autoptimize_single_6965137b6996c7953be805866df582ed.css?ver=6.2.22' type='text/css' media='all' /><style id='rs-plugin-settings-inline-css' type='text/css'>#rs-demo-id {}</style><link rel='stylesheet' id='cmplz-general-css' href='https://www.uni.eus/wp-content/plugins/complianz-gdpr/assets/css/cookieblocker.min.css?ver=6.5.5' type='text/css' media='all' /><link rel='stylesheet' id='parent-style-css' href='https://www.uni.eus/wp-content/cache/autoptimize/css/autoptimize_single_ef976c490115b8b921abbcfb0de344ab.css?ver=6.4.1' type='text/css' media='all' /><link rel='stylesheet' id='js_composer_front-css' href='https://www.uni.eus/wp-content/plugins/js_composer/assets/css/js_composer.min.css?ver=6.5.0' type='text/css' media='all' /><link rel='stylesheet' id='ebor-google-font-css' href='//fonts.googleapis.com/css?family=Rubik%3A300%2C300i%2C400%2C400i%2C500%2C500i%2C700%2C700i&#038;ver=1.0.0' type='text/css' media='all' /><link rel='stylesheet' id='bootstrap-css' href='https://www.uni.eus/wp-content/themes/creatink/style/css/bootstrap.min.css?ver=1.0.0' type='text/css' media='all' /><link rel='stylesheet' id='ebor-icons-css' href='https://www.uni.eus/wp-content/cache/autoptimize/css/autoptimize_single_ec0809b93ad54c110269940c85d954e3.css?ver=1.0.0' type='text/css' media='all' /><link rel='stylesheet' id='ebor-plugins-css' href='https://www.uni.eus/wp-content/cache/autoptimize/css/autoptimize_single_19a75660ccf5bba18092227a1c5daf5b.css?ver=1.0.0' type='text/css' media='all' /><link rel='stylesheet' id='ebor-style-css' href='https://www.uni.eus/wp-content/cache/autoptimize/css/autoptimize_single_3e500a8f83ad5ea1a3b06ca5fbbd65f2.css?ver=1.0.0' type='text/css' media='all' /><style id='ebor-style-inline-css' type='text/css'>.cat118 { background-color: #70aed2 !important; }
			
				.cat60 { background-color: #70aed2 !important; }
			
			
			.disc:after {
			    background: rgba(76,152,201, 0.7)
			}
			.overlay.color span.bg {
			    background: rgba(76,152,201, 0.8);
			}
			.overlay6.color:after,
			.overlay6.color:before {
			    background: rgba(76,152,201, 0.5);
			}
			.overlay8.color figcaption {
			    background: rgba(76,152,201, 0.8);
			}
			.page-loading .spinner,
			.tp-loader.spinner,
			.lg-outer .lg-item:after,
			.fotorama__wrap--css3 .fotorama__spinner {
			    border-left: 3px solid rgba(76,152,201, .15);
			    border-right: 3px solid rgba(76,152,201, .15);
			    border-bottom: 3px solid rgba(76,152,201, .15);
			    border-top: 3px solid rgba(76,152,201, .8);
			}
			#scrollUp .btn {
			    background: rgba(76,152,201, 0.8);
			}
			#scrollUp .btn:hover,
			#scrollUp .btn:focus,
			#scrollUp .btn:active,
			#scrollUp .btn.active {
			    background: rgba(76,152,201, 1);
			}
			a.hover:hover {
			    border-bottom: 1px solid #4c98c9;
			}
			a {
			    color: #4c98c9;
			}
			a:hover,
			a:focus {
			    text-decoration: none;
			    color: #4c98c9;
			}
			.color-wrapper {
			    background: #4c98c9;
			}
			.navbar .nav > li > a:hover,
			.navbar .nav > li.active > a,
			.navbar .navbar-other a.nav-link:hover {
			    background: none;
			    color: #4c98c9
			}
			.btn-group .dropdown-menu > li > a:hover,
			.btn-group .dropdown-menu > li > a:focus {
			    color: #4c98c9;
			}
			.btn {
			    background: #4c98c9;
			}
			.btn-border {
			    border: 2px solid #4c98c9;
			    background: none;
			    color: #4c98c9;
			}
			.btn:hover,
			.btn:focus,
			.btn:active,
			.btn.active {
			    background: #19aaca;
			}
			.btn-border:hover,
			.btn-border:focus,
			.btn-border:active,
			.btn-border.active {
			    border: 2px solid #4c98c9;
			    background: #4c98c9;
			}
			.fotorama__nav__frame.fotorama__nav__frame--thumb.fotorama__active:before {
			    border: 2px solid #4c98c9;
			}
			.isotope-filter ul li a:hover,
			.isotope-filter ul li a.active {
			    color: #4c98c9;
			}
			.size-picker span.active {
			    background: #4c98c9;
			}
			.post-title a:hover,
			.more:hover,
			.meta a:hover {
			    color: #4c98c9;
			}
			.meta.price {
			    color: #4c98c9;
			}
			.post-nav-wrapper a:hover {
			    color: #4c98c9;
			}
			.sidebox a:hover {
			    color: #4c98c9
			}
			#comments .info h5 a:hover {
			    color: #4c98c9;
			}
			.image-list li a:hover {
			    color: #4c98c9
			}
			.icon-color,
			.text-color,
			.circle .progressbar-text {
			    color: #4c98c9
			}
			.icon-border {
			    border: 3px solid #4c98c9;
			}
			.icon-bg {
			    background: #4c98c9;
			}
			.nav-tabs > li > a:hover,
			.nav-tabs > li > a:hover *,
			.nav-tabs > li.active > a,
			.nav-tabs > li.active > a *,
			.nav-tabs > li.active > a:hover,
			.nav-tabs > li.active > a:focus {
			    color: #4c98c9;
			}
			.nav-tabs-lined.nav-tabs-lined-bottom > li.active > a:after {
			    border-bottom: 1px solid #4c98c9;
			}
			.nav-tabs-lined.nav-tabs-lined-top > li.active > a:after {
			    border-top: 1px solid #4c98c9;
			}
			.panel-group-lined .panel-active .panel-heading .panel-title {
			    border-bottom: 1px solid #4c98c9;
			    color: #4c98c9;
			}
			.panel-group-lined .panel-title > a:active {
			    color: #4c98c9;
			}
			.timeline.dot .timeline-icon:before {
				background: #4c98c9;
			}
			.tooltip-inner {
			    background-color: #4c98c9;
			}
			.tooltip.top .tooltip-arrow,
			.tooltip.top-left .tooltip-arrow,
			.tooltip.top-right .tooltip-arrow {
			    border-top-color: #4c98c9
			}
			.tooltip.right .tooltip-arrow {
			    border-right-color: #4c98c9
			}
			.tooltip.left .tooltip-arrow {
			    border-left-color: #4c98c9
			}
			.tooltip.bottom .tooltip-arrow,
			.tooltip.bottom-left .tooltip-arrow,
			.tooltip.bottom-right .tooltip-arrow {
			    border-bottom-color: #4c98c9
			}
			.pagination ul > li > a:hover,
			.pagination ul > .active > a span {
			    color: #4c98c9
			}
			textarea:focus,
			textarea.form-control:focus,
			input[type="text"]:focus,
			input[type="password"]:focus,
			input[type="datetime"]:focus,
			input[type="datetime-local"]:focus,
			input[type="date"]:focus,
			input[type="month"]:focus,
			input[type="time"]:focus,
			input[type="week"]:focus,
			input[type="number"]:focus,
			input[type="email"]:focus,
			input[type="url"]:focus,
			input[type="search"]:focus,
			input[type="tel"]:focus,
			input[type="color"]:focus,
			.uneditable-input:focus {
			    border-color: #4c98c9
			}
			input[type="radio"]:focus + span,
			input[type="checkbox"]:focus + span,
			input[type="radio"]:active + span,
			input[type="checkbox"]:active + span {
			    border-color: #4c98c9
			}
			input[type="radio"].error + span,
			input[type="checkbox"].error + span {
			    border-color: #4c98c9
			}
			input[type="radio"] + span::after {
			    background-color: #4c98c9;
			    border-color: #4c98c9;
			}
			input[type="radio"]:checked + span,
			input[type="checkbox"]:checked + span {
			    border: 1px solid #4c98c9
			}
			input[type="checkbox"] + span::after {
			    border: 0 solid #4c98c9;
			}
			.bg-default {
			    background: #4c98c9
			}
			.progressbar.border {
				border-color: #4c98c9;
			}
			.progressbar svg path:last-child {
			    stroke: #4c98c9;
			}
			.page-loading .caption {
			    color: #4c98c9;
			}
			.inverse-text.dark-wrapper .pagination:not(.boxed):not(.round) ul > li > a:hover,
			.inverse-text.dark-wrapper .pagination.round-simple ul > li > a:hover,
			.inverse-text a:not(.btn):not([class*="color-s-"]):hover,
			.inverse-text .isotope-filter ul li a:hover,
			.inverse-text .isotope-filter ul li a.active,
			.inverse-text .text-color {
			    color: #4c98c9 !important;
			}
			.inverse-text .post-title a:hover,
			.inverse-text .bg-white .meta a:hover,
			.inverse-text .bg-white a.more:hover,
			.inverse-text .pagination:not(.boxed):not(.round) ul > li > a:hover,
			.inverse-text .pagination.round-simple ul > li > a:hover {
			    color: #4c98c9 !important;
			}
			.inverse-text:not(.navbar):not(.nav-wrapper) textarea:focus,
			.inverse-text:not(.navbar):not(.nav-wrapper) input[type="text"]:focus,
			.inverse-text:not(.navbar):not(.nav-wrapper) input[type="password"]:focus,
			.inverse-text:not(.navbar):not(.nav-wrapper) input[type="datetime"]:focus,
			.inverse-text:not(.navbar):not(.nav-wrapper) input[type="datetime-local"]:focus,
			.inverse-text:not(.navbar):not(.nav-wrapper) input[type="date"]:focus,
			.inverse-text:not(.navbar):not(.nav-wrapper) input[type="month"]:focus,
			.inverse-text:not(.navbar):not(.nav-wrapper) input[type="time"]:focus,
			.inverse-text:not(.navbar):not(.nav-wrapper) input[type="week"]:focus,
			.inverse-text:not(.navbar):not(.nav-wrapper) input[type="number"]:focus,
			.inverse-text:not(.navbar):not(.nav-wrapper) input[type="email"]:focus,
			.inverse-text:not(.navbar):not(.nav-wrapper) input[type="url"]:focus,
			.inverse-text:not(.navbar):not(.nav-wrapper) input[type="search"]:focus,
			.inverse-text:not(.navbar):not(.nav-wrapper) input[type="tel"]:focus,
			.inverse-text:not(.navbar):not(.nav-wrapper) input[type="color"]:focus,
			.inverse-text:not(.navbar):not(.nav-wrapper) .uneditable-input:focus {
			    border-color: #4c98c9;
			}
			.inverse-text:not(.navbar):not(.nav-wrapper) input[type="radio"]:checked + span,
			.inverse-text:not(.navbar):not(.nav-wrapper) input[type="checkbox"]:checked + span {
			    border-color: #4c98c9
			}
			@media (min-width: 992px) {
			    .navbar .navbar-nav > li > a.highlighted {
				    color: #4c98c9
				}
				.inverse-text .navbar-nav > li:not(.active) > a:not(.highlighted):hover,
				.inverse-text .navbar-nav > li > a:hover {
					color: #4c98c9 !important
				}
			}
			footer.image-footer {
				background-image: url();
				padding-bottom: 369px;				
			}
			body,
			footer a,
			.map-info p,
			.icon p,
			label.custom-select,
			.checkbox label,
			.radio label,
			select,
			textarea,
			textarea.form-control,
			input[type="text"]:not(.qty),
			input[type="password"],
			input[type="datetime"],
			input[type="datetime-local"],
			input[type="date"],
			input[type="month"],
			input[type="time"],
			input[type="week"],
			input[type="number"],
			input[type="email"],
			input[type="url"],
			input[type="search"],
			input[type="tel"],
			input[type="color"],
			.uneditable-input,
			.search-form:before,
			.color-text,
			.inverse-text .bg-white select,
			.inverse-text .bg-white textarea,
			.inverse-text .bg-white textarea.form-control,
			.inverse-text .bg-white input[type="text"]:not(.qty),
			.inverse-text .bg-white input[type="password"],
			.inverse-text .bg-white input[type="datetime"],
			.inverse-text .bg-white input[type="datetime-local"],
			.inverse-text .bg-white input[type="date"],
			.inverse-text .bg-white input[type="month"],
			.inverse-text .bg-white input[type="time"],
			.inverse-text .bg-white input[type="week"],
			.inverse-text .bg-white input[type="number"],
			.inverse-text .bg-white input[type="email"],
			.inverse-text .bg-white input[type="url"],
			.inverse-text .bg-white input[type="search"],
			.inverse-text .bg-white input[type="tel"],
			.inverse-text .bg-white input[type="color"],
			.inverse-text .bg-white .uneditable-input {
			    color: #707070;
			}
			.form-control::-webkit-input-placeholder {
			    color: #707070;
			    font-weight: normal;
			}
			.form-control:-moz-placeholder {
			    color: #707070;
			    font-weight: normal;
			    opacity: 1;
			}
			.form-control::-moz-placeholder {
			    color: #707070;
			    font-weight: normal;
			    opacity: 1;
			}
			.form-control:-ms-input-placeholder {
			    color: #707070;
			    font-weight: normal;
			}
			.inverse-text .bg-white p,
			.inverse-text .bg-white li,
			.inverse-text .panel-group-bg p,
			.inverse-text .bg-white table,
			.inverse-text .popover,
			.inverse-text .bg-white .color-text {
			    color: #707070 !important;
			}
			h1,
			h2,
			h3,
			h4,
			h5,
			h6,
			h5 a {
			    color: #404040;
			}
			.text-muted,
			.meta,
			a.more,
			.meta span:after,
			.meta *,
			.meta.breadcrumbs a,
			.meta.price .quantity,
			.meta.price del {
			    color: #aaaaaa;
			}
			.inverse-text:not(.navbar):not(.nav-wrapper) select {
			    color: #aaaaaa;
			}
			.inverse-text .form-control::-webkit-input-placeholder {
			    color: #aaaaaa;
			}
			.inverse-text .form-control:-moz-placeholder {
			    color: #aaaaaa;
			}
			.inverse-text .form-control::-moz-placeholder {
			    color: #aaaaaa;
			}
			.inverse-text .form-control:-ms-input-placeholder {
			    color: #aaaaaa;
			}
			footer.dark-wrapper a {
				color: #fff;
			}
			.light-wrapper {
			    background: #f6f7f8;
			}
			.dark-wrapper {
			    background: #2b2b2b;
			}
			footer.dark-wrapper,
			.navbar.dark-wrapper,
			.nav-wrapper.dark-wrapper,
			.navbar.narrow:not(.fixed) .nav-wrapper.dark-wrapper .container {
			    background: #272727;
			}
			.sub-footer.dark-wrapper {
			    background: #232323;
			}</style> <script type="text/javascript" src="https://www.uni.eus/wp-includes/js/jquery/jquery.min.js?ver=3.7.1" id="jquery-core-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-includes/js/jquery/jquery-migrate.min.js?ver=3.4.1" id="jquery-migrate-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/plugins/revslider/public/assets/js/rbtools.min.js?ver=6.2.22" id="tp-tools-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/plugins/revslider/public/assets/js/rs6.min.js?ver=6.2.22" id="revmin-js"></script> <link rel="https://api.w.org/" href="https://www.uni.eus/wp-json/" /><link rel="alternate" type="application/json" href="https://www.uni.eus/wp-json/wp/v2/pages/1798" /><link rel="EditURI" type="application/rsd+xml" title="RSD" href="https://www.uni.eus/xmlrpc.php?rsd" /><meta name="generator" content="WordPress 6.4.1" /><link rel="canonical" href="https://www.uni.eus/eu/" /><link rel='shortlink' href='https://www.uni.eus/' /><link rel="alternate" type="application/json+oembed" href="https://www.uni.eus/wp-json/oembed/1.0/embed?url=https%3A%2F%2Fwww.uni.eus%2Feu%2F" /><link rel="alternate" type="text/xml+oembed" href="https://www.uni.eus/wp-json/oembed/1.0/embed?url=https%3A%2F%2Fwww.uni.eus%2Feu%2F&#038;format=xml" />  <script type="text/plain" data-service="google-analytics" data-category="statistics" async data-cmplz-src="//www.googletagmanager.com/gtag/js?id=G-MBCP5Y9TFB"></script> <script>window.dataLayer = window.dataLayer || [];
function gtag(){dataLayer.push(arguments);}
gtag('js', new Date());

gtag('config', 'G-MBCP5Y9TFB');</script> <style>.cmplz-hidden{display:none!important;}</style><meta name="generator" content="Powered by WPBakery Page Builder - drag and drop page builder for WordPress."/><meta name="generator" content="Powered by Slider Revolution 6.2.22 - responsive, Mobile-Friendly Slider Plugin for WordPress with comfortable drag and drop interface." /><link rel="icon" href="https://www.uni.eus/wp-content/uploads/2021/05/cropped-favicon-32x32.png" sizes="32x32" /><link rel="icon" href="https://www.uni.eus/wp-content/uploads/2021/05/cropped-favicon-192x192.png" sizes="192x192" /><link rel="apple-touch-icon" href="https://www.uni.eus/wp-content/uploads/2021/05/cropped-favicon-180x180.png" /><meta name="msapplication-TileImage" content="https://www.uni.eus/wp-content/uploads/2021/05/cropped-favicon-270x270.png" /> <script type="text/javascript">function setREVStartSize(e){
			//window.requestAnimationFrame(function() {				 
				window.RSIW = window.RSIW===undefined ? window.innerWidth : window.RSIW;	
				window.RSIH = window.RSIH===undefined ? window.innerHeight : window.RSIH;	
				try {								
					var pw = document.getElementById(e.c).parentNode.offsetWidth,
						newh;
					pw = pw===0 || isNaN(pw) ? window.RSIW : pw;
					e.tabw = e.tabw===undefined ? 0 : parseInt(e.tabw);
					e.thumbw = e.thumbw===undefined ? 0 : parseInt(e.thumbw);
					e.tabh = e.tabh===undefined ? 0 : parseInt(e.tabh);
					e.thumbh = e.thumbh===undefined ? 0 : parseInt(e.thumbh);
					e.tabhide = e.tabhide===undefined ? 0 : parseInt(e.tabhide);
					e.thumbhide = e.thumbhide===undefined ? 0 : parseInt(e.thumbhide);
					e.mh = e.mh===undefined || e.mh=="" || e.mh==="auto" ? 0 : parseInt(e.mh,0);		
					if(e.layout==="fullscreen" || e.l==="fullscreen") 						
						newh = Math.max(e.mh,window.RSIH);					
					else{					
						e.gw = Array.isArray(e.gw) ? e.gw : [e.gw];
						for (var i in e.rl) if (e.gw[i]===undefined || e.gw[i]===0) e.gw[i] = e.gw[i-1];					
						e.gh = e.el===undefined || e.el==="" || (Array.isArray(e.el) && e.el.length==0)? e.gh : e.el;
						e.gh = Array.isArray(e.gh) ? e.gh : [e.gh];
						for (var i in e.rl) if (e.gh[i]===undefined || e.gh[i]===0) e.gh[i] = e.gh[i-1];
											
						var nl = new Array(e.rl.length),
							ix = 0,						
							sl;					
						e.tabw = e.tabhide>=pw ? 0 : e.tabw;
						e.thumbw = e.thumbhide>=pw ? 0 : e.thumbw;
						e.tabh = e.tabhide>=pw ? 0 : e.tabh;
						e.thumbh = e.thumbhide>=pw ? 0 : e.thumbh;					
						for (var i in e.rl) nl[i] = e.rl[i]<window.RSIW ? 0 : e.rl[i];
						sl = nl[0];									
						for (var i in nl) if (sl>nl[i] && nl[i]>0) { sl = nl[i]; ix=i;}															
						var m = pw>(e.gw[ix]+e.tabw+e.thumbw) ? 1 : (pw-(e.tabw+e.thumbw)) / (e.gw[ix]);					
						newh =  (e.gh[ix] * m) + (e.tabh + e.thumbh);
					}				
					if(window.rs_init_css===undefined) window.rs_init_css = document.head.appendChild(document.createElement("style"));					
					document.getElementById(e.c).height = newh+"px";
					window.rs_init_css.innerHTML += "#"+e.c+"_wrapper { height: "+newh+"px }";				
				} catch(e){
					console.log("Failure at Presize of Slider:" + e)
				}					   
			//});
		  };</script> <style type="text/css" id="wp-custom-css">.navbar-brand img{
    width: 200px;
    height: 91px;
    object-fit: contain;
}

.inverse-text .navbar-nav > li:not(.active) > a:not(.highlighted):hover, .inverse-text .navbar-nav > li > a:hover {
    color: #fff !important;
}
.cmplz-cookiebanner .cmplz-message {
  margin-bottom: 0;
  font-size: 20px;
  line-height: 200%;
}

.cmplz-btn.cmplz-deny{
  background: #5e43847d !important;
  color: #fff !important;
}

.cmplz-btn.cmplz-view-preferences{
  background: #fff !important;
  border-color: #5e43847d !important;
  color:#5e43847d !important;
}
.inverse-text.dark-wrapper .pagination:not(.boxed):not(.round) ul > li > a:hover, .inverse-text.dark-wrapper .pagination.round-simple ul > li > a:hover, .inverse-text a:not(.btn):not([class*="color-s-"]):hover, .inverse-text .isotope-filter ul li a:hover, .inverse-text .isotope-filter ul li a.active, .inverse-text .text-color {
    color: #fff !important;
}

.zoom a,
a .vc_single_image-img {
  transition: transform .2s; /* Animation */
  margin: 0 auto;

}

.zoom a:hover,
a:hover .vc_single_image-img {
  transform: scale(.99); /* (150% zoom - Note: if the zoom is too large, it will go outside of the viewport) */
	
}</style><style type="text/css" data-type="vc_shortcodes-custom-css">.vc_custom_1620888464571{padding-top: 0px !important;padding-bottom: 0px !important;}.vc_custom_1622201717975{margin-bottom: 0px !important;padding-bottom: 0px !important;}.vc_custom_1620998394186{margin-top: 44px !important;margin-bottom: 0px !important;padding-top: 0px !important;padding-bottom: 0px !important;}.vc_custom_1621442487141{margin-top: 0px !important;padding-bottom: 36px !important;background-color: #20123b !important;}.vc_custom_1622201867899{margin-top: 0px !important;}.vc_custom_1622201694543{margin-top: 0px !important;margin-bottom: 32px !important;}.vc_custom_1622201010661{background-position: center !important;background-repeat: no-repeat !important;background-size: cover !important;border-radius: 35px !important;}.vc_custom_1620899894255{padding-top: 36px !important;padding-bottom: 36px !important;}.vc_custom_1622202395435{padding-top: 0px !important;background-color: #5e4384 !important;background-position: center !important;background-repeat: no-repeat !important;background-size: cover !important;}.vc_custom_1621442520793{padding-top: 36px !important;}.vc_custom_1623927400902{margin-top: 0px !important;margin-bottom: 36px !important;}.vc_custom_1624893479193{margin-top: 0px !important;margin-bottom: 36px !important;}.vc_custom_1621333571639{margin-top: 32px !important;padding-bottom: 44px !important;}.vc_custom_1620996062173{margin-top: 0px !important;padding-top: 0px !important;}.vc_custom_1624003970765{background-color: rgba(255,255,255,0.01) !important;*background-color: rgb(255,255,255) !important;}.vc_custom_1622201560983{padding-top: 0px !important;}.vc_custom_1620998042808{margin-bottom: 0px !important;padding-bottom: 0px !important;}.vc_custom_1629705933000{margin-bottom: 18px !important;}.vc_custom_1626171440660{margin-bottom: 0px !important;padding-bottom: 0px !important;}.vc_custom_1622107445108{border-top-width: 150px !important;}</style><noscript><style>.wpb_animate_when_almost_visible { opacity: 1; }</style></noscript></head><body data-cmplz=1 class="home page-template-default page page-id-1798 wpb-js-composer js-comp-ver-6.5.0 vc_responsive"><div class="content-wrapper"><nav class="navbar extended"><div class="top-bar gray-wrapper"><div class="container flex-it"><div class="align-right text-right"><ul class='top-menu'><li><a href="https://www.uni.eus/eu/ikasleak/" title="Ikasleak">Ikasleak <i class="fas fa-chevron-right"></i> </a></li><li><a href="https://www.uni.eus/eu/irakasleak/" title="Irakasleak">Irakasleak <i class="fas fa-chevron-right"></i> </a></li><li><select name="lang_choice_1" id="lang_choice_1" class="pll-switcher-select"><option value="https://www.uni.eus/eu/" lang="eu" selected='selected'>Euskara</option><option value="https://www.uni.eus/es/" lang="es-ES">Español</option> </select> <script type="text/javascript">document.getElementById( "lang_choice_1" ).addEventListener( "change", function ( event ) { location.href = event.currentTarget.value; } )</script></li></ul></div></div></div><div class="container"><div class="navbar-header flex-it"><div class="navbar-brand"> <a href="https://www.uni.eus/eu/"> <img 
 src="#" 
 srcset="https://www.uni.eus/wp-content/uploads/2021/05/infogramak-UNI-45-e1620890341119-1.png 1x, https://www.uni.eus/wp-content/uploads/2021/05/infogramak-UNI-45-e1620890341119-1.png 2x" 
 alt="Uni" 
 /> </a></div><div class="align-right text-right"><ul class='lateral-menu'><li><a href="https://www.uni.eus/eu/ikastetxea/" title="Ikastetxea">Ikastetxea <i class="fas fa-chevron-right"></i> </a></li><li><a href="https://www.uni.eus/eu/proiektuak/" title="Proiektuak">Proiektuak <i class="fas fa-chevron-right"></i> </a></li></ul></div><div class="nav-bars-wrapper"><div class="nav-bars-inner"><div class="nav-bars" data-toggle="collapse" data-target=".navbar-collapse"> <span></span></div></div></div><div class="navbar-other"><ul class="nav"><li><div class="btn-group btn-search"> <a href="#" data-toggle="dropdown" class="nav-link"> <i class="et-magnifying-glass"></i> </a><div class="dropdown-menu dropdown-menu-right"><form class="search-form" method="get" id="searchform" action="https://www.uni.eus/eu/"><div class="form-group mb-0"> <input type="text" name="s" class="form-control" placeholder="Bilatu" /></div></form></div></div></li></ul></div></div></div><div class="nav-wrapper dark-wrapper inverse-text"><div class="container flex-it"><div class="navbar-collapse collapse"><ul class="nav navbar-nav"><li id="menu-item-8" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-8"><a href="https://www.uni.eus/eu/informatika/">Informatika</a></li><li id="menu-item-35" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-35"><a href="https://www.uni.eus/eu/merkataritza/">Merkataritza</a></li><li id="menu-item-1930" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-1930"><a href="https://www.uni.eus/eu/administrazioa-eta-kudeaketa/">Administrazioa</a></li><li id="menu-item-37" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-37"><a href="https://www.uni.eus/eu/gorputz-eta-kirol-jarduerak/">Gorputz eta Kirol Jarduerak</a></li><li id="menu-item-38" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-38"><a href="https://www.uni.eus/eu/lanerako-prestakuntza/">Lanerako prestakuntza</a></li></ul><div class="show-in-mobile"><ul class='nav navbar-nav sm-collapsible'><li class="menu-item menu-item-type-post_type menu-item-object-page"><a href="https://www.uni.eus/eu/ikastetxea/" title="Ikastetxea">Ikastetxea</a></li><li class="menu-item menu-item-type-post_type menu-item-object-page"><a href="https://www.uni.eus/eu/proiektuak/" title="Proiektuak">Proiektuak</a></li></ul><ul class='nav navbar-nav sm-collapsible'><li class="menu-item menu-item-type-post_type menu-item-object-page"><a href="https://www.uni.eus/eu/ikasleak/" title="Ikasleak">Ikasleak</a></li><li class="menu-item menu-item-type-post_type menu-item-object-page"><a href="https://www.uni.eus/eu/irakasleak/" title="Irakasleak">Irakasleak</a></li></ul><ul><li class="lang-item lang-item-3 lang-item-eu current-lang lang-item-first"><a  lang="eu" hreflang="eu" href="https://www.uni.eus/eu/">Euskara</a></li><li class="lang-item lang-item-6 lang-item-es"><a  lang="es-ES" hreflang="es-ES" href="https://www.uni.eus/es/">Español</a></li></ul></div></div><div class="navbar-other"><ul class="nav"><li><div class="btn-group btn-search"> <a href="#" data-toggle="dropdown" class="nav-link"> <i class="et-magnifying-glass"></i> </a><div class="dropdown-menu dropdown-menu-right"><form class="search-form" method="get" id="searchform" action="https://www.uni.eus/eu/"><div class="form-group mb-0"> <input type="text" name="s" class="form-control" placeholder="Bilatu" /></div></form></div></div></li></ul></div></div></div></nav><div class="wrapper page-title-wrapper"></div><div class="container"><section class="vc_section vc_custom_1620888464571"><div class="vc_row wpb_row vc_row-fluid"><div class="wpb_column vc_column_container vc_col-sm-12"><div class="vc_column-inner"><div class="wpb_wrapper"><p class="rs-p-wp-fix"></p> <rs-module-wrap id="rev_slider_1_1_wrapper" data-source="gallery" style="background:transparent;padding:0;margin:0px auto;margin-top:0;margin-bottom:0;"> <rs-module id="rev_slider_1_1" style="" data-version="6.2.22"> <rs-slides> <rs-slide data-key="rs-1" data-title="BarrukoGradak" data-anim="ei:d;eo:d;s:1000;r:0;t:fade;sl:0;"> <img fetchpriority="high" decoding="async" src="//www.uni.eus/wp-content/uploads/2022/01/EB_0514GradenHallaEskuinekoaGalduta.jpg" title="EB_0514GradenHallaEskuinekoaGalduta" width="839" height="561" data-bg="p:center top;" class="rev-slidebg" data-no-retina><h1
 id="slider-1-slide-1-layer-0" 
 class="rs-layer"
 data-type="shape"
 data-rsp_ch="on"
 data-xy="x:827px;y:-259px;"
 data-text="w:normal;"
 data-dim="w:300px;h:609px;"
 data-vbility="f,f,f,f"
 data-padding="t:30;r:30;b:150;l:30;"
 data-border="bor:0,0px,150px,150px;"
 data-frame_1="e:none;sp:0;"
 data-frame_1_sfx="se:blocktobottom;"
 data-frame_999="o:0;st:w;sR:9000;"
 style="z-index:8;background-color:rgba(94,67,132,0.9);"
 ></h1><rs-layer
 id="slider-1-slide-1-layer-1" 
 data-type="text"
 data-color="#ffffff"
 data-rsp_ch="on"
 data-xy="x:864px;y:158px;"
 data-text="w:normal;s:16;"
 data-dim="w:242px;"
 data-vbility="f,f,f,f"
 data-frame_999="o:0;st:w;sR:8700;"
 style="z-index:9;font-family:Arial, Helvetica, sans-serif;"
 >Irailaren 9an Uniko 2021-22 ikasturtearen  aurkezpena egin da. </rs-layer><rs-layer
 id="slider-1-slide-1-layer-2" 
 data-type="text"
 data-color="#ffffff"
 data-rsp_ch="on"
 data-xy="x:863px;y:26px;"
 data-text="w:normal;s:36;l:42;fw:700;"
 data-dim="w:242px;"
 data-vbility="f,f,f,f"
 data-frame_999="o:0;st:w;sR:8700;"
 style="z-index:10;font-family:Nunito Sans;"
 >Ikasturte Hasiera </rs-layer><a
 id="slider-1-slide-1-layer-3" 
 class="rs-layer rev-btn"
 href="ikasturte-hasiera" target="_self" rel="nofollow"
 data-type="button"
 data-color="#ffffff"
 data-rsp_ch="on"
 data-xy="x:865px;y:242px;"
 data-text="w:normal;s:16;l:40;"
 data-dim="minh:0px;"
 data-vbility="f,f,f,f"
 data-padding="r:30;l:30;"
 data-border="bos:solid;boc:#ffffff;bow:1px,1px,1px,1px;bor:25px,25px,25px,25px;"
 data-frame_999="o:0;st:w;sR:8700;"
 data-frame_hover="bgc:rgba(0,0,0,0);boc:rgba(255,255,255,0.75);bor:25px,25px,25px,25px;bos:solid;bow:1px,1px,1px,1px;e:power1.inOut;"
 style="z-index:11;background-color:rgba(0,0,0,0);font-family:Arial, Helvetica, sans-serif;"
 >Zehaztasunak<br /> </a><rs-layer
 id="slider-1-slide-1-layer-4" 
 data-type="shape"
 data-rsp_ch="on"
 data-xy="x:867px;y:134px;"
 data-text="w:normal;"
 data-dim="w:200px;h:3px;"
 data-vbility="f,f,f,f"
 data-frame_999="o:0;st:w;sR:8700;"
 style="z-index:12;background-color:#ffffff;"
 > </rs-layer> </rs-slide> </rs-slides> <rs-static-layers></rs-static-layers> </rs-module> <script type="text/javascript">setREVStartSize({c: 'rev_slider_1_1',rl:[1240,1024,778,480],el:[500],gw:[1240],gh:[500],type:'standard',justify:'',layout:'fullwidth',mh:"0"});
					var	revapi1,
						tpj;
					function revinit_revslider11() {
					jQuery(function() {
						tpj = jQuery;
						revapi1 = tpj("#rev_slider_1_1");
						if(revapi1==undefined || revapi1.revolution == undefined){
							revslider_showDoubleJqueryError("rev_slider_1_1");
						}else{
							revapi1.revolution({
								sliderLayout:"fullwidth",
								visibilityLevels:"1240,1024,778,480",
								gridwidth:1240,
								gridheight:500,
								spinner:"spinner0",
								perspective:600,
								perspectiveType:"global",
								editorheight:"500,768,960,420",
								responsiveLevels:"1240,1024,778,480",
								progressBar:{disableProgressBar:true},
								navigation: {
									onHoverStop:false
								},
								fallbacks: {
									allowHTML5AutoPlayOnAndroid:true
								},
							});
						}
						
					});
					} // End of RevInitScript
				var once_revslider11 = false;
				if (document.readyState === "loading") {document.addEventListener('readystatechange',function() { if((document.readyState === "interactive" || document.readyState === "complete") && !once_revslider11 ) { once_revslider11 = true; revinit_revslider11();}});} else {once_revslider11 = true; revinit_revslider11();}</script> </rs-module-wrap></div></div></div></div><div class="vc_row wpb_row vc_row-fluid topSpacer vc_custom_1622201867899"><div class="wpb_column vc_column_container vc_col-sm-12"><div class="vc_column-inner vc_custom_1622201694543"><div class="wpb_wrapper"><div class="wpb_text_column wpb_content_element  topSpace" ><div class="wpb_wrapper"><h5 style="text-align: center;">Uni eibar ermua</h5><h2 style="text-align: center;">Lanbide Heziketako ikastetxea</h2></div></div></div></div></div></div><div class="vc_row wpb_row vc_row-fluid valores"><div class="wpb_column vc_column_container vc_col-sm-4"><div class="vc_column-inner"><div class="wpb_wrapper"><div class="wpb_text_column wpb_content_element  align-right" ><div class="wpb_wrapper"><h3><a href="https://www.uni.eus/eu/proiektuak/erasmus-emeu/">Nazioartekotzea</a></h3><p>Praktikak egiteko nahiz unitate didaktiko bat egiteko atzerrira joateko aukera</p><p>&nbsp;</p><h3><a href="https://www.uni.eus/eu/informatika/plataforma-anitzeko-aplikazioen-garapena/">Eleanitza</a></h3><p>Irakasgai batzuk ingelesez egiteko aukera</p></div></div></div></div></div><div class="wpb_column vc_column_container vc_col-sm-4"><div class="vc_column-inner"><div class="wpb_wrapper"><div  class="wpb_single_image wpb_content_element vc_align_left  wpb_animate_when_almost_visible wpb_bounceIn bounceIn vc_custom_1622201010661  show-in-desktop"><figure class="wpb_wrapper vc_figure"><div class="vc_single_image-wrapper vc_box_circle  vc_box_border_grey"><img decoding="async" class="vc_single_image-img " src="https://www.uni.eus/wp-content/uploads/2021/05/Uni-obrak-eginda-e1622116781798-877x877.jpg" width="877" height="877" alt="Uni-obrak-eginda" title="Uni-obrak-eginda" /></div></figure></div><div class="wpb_text_column wpb_content_element  align-right" ><div class="wpb_wrapper"><h3 style="text-align: center;"><a href="https://www.uni.eus/eu/ikastetxea/zerbitzuak/">Hezkuntza-campusa</a></h3><p style="text-align: center;">Autobus/tren geralekuak, jangela, egoitza, kirol-instalazioak eta aisialdirako guneak</p></div></div></div></div></div><div class="wpb_column vc_column_container vc_col-sm-4"><div class="vc_column-inner"><div class="wpb_wrapper"><div class="wpb_text_column wpb_content_element " ><div class="wpb_wrapper"><h3><a href="https://www.uni.eus/eu/ikastetxea/prestakuntza-duala/">Duala</a></h3><p>Enpresan eta ikastetxean ikaskuntza-prozesuak konbinatzea, lanaren bidez ikasteko</p><p>&nbsp;</p><h3><a href="https://www.uni.eus/eu/ikastetxea/lan-poltsa/">Lan-poltsa</a></h3><p>UNIan ikasketak egin dituzten pertsonei zuzendutako zerbitzua</p></div></div></div></div></div></div></section><section data-vc-full-width="true" data-vc-full-width-init="false" data-vc-stretch-content="true" class="vc_section vc_custom_1622201717975"><div data-vc-full-width="true" data-vc-full-width-init="false" data-vc-stretch-content="true" class="vc_row wpb_row vc_row-fluid noticias vc_custom_1620899894255"><div class="wpb_column vc_column_container vc_col-sm-12" id="albisteak"><div class="vc_column-inner"><div class="wpb_wrapper"><div class="wpb_text_column wpb_content_element " ><div class="wpb_wrapper"><h2 style="text-align: center;"><a href="/eu/albisteak/">Albisteak</a></h2></div></div><div class="vc_row wpb_row vc_inner vc_row-fluid vc_custom_1621442520793"><div class="wpb_column vc_column_container vc_col-sm-2"><div class="vc_column-inner"><div class="wpb_wrapper"></div></div></div><div class="wpb_column vc_column_container vc_col-sm-8"><div class="vc_column-inner"><div class="wpb_wrapper"><div class="vc_grid-container-wrapper vc_clearfix"><div class="vc_grid-container vc_clearfix wpb_content_element vc_basic_grid" data-initial-loading-animation="fadeIn" data-vc-grid-settings="{&quot;page_id&quot;:1798,&quot;style&quot;:&quot;all&quot;,&quot;action&quot;:&quot;vc_get_vc_grid_data&quot;,&quot;shortcode_id&quot;:&quot;1634317860251-8fef2583-1d32-2&quot;,&quot;tag&quot;:&quot;vc_basic_grid&quot;}" data-vc-request="https://www.uni.eus/wp-admin/admin-ajax.php" data-vc-post-id="1798" data-vc-public-nonce="4c8fa991c6"><style data-type="vc_shortcodes-custom-css">.vc_custom_1621253598652{padding-top: 0px !important;padding-right: 0px !important;padding-bottom: 0px !important;padding-left: 0px !important;}</style><div class="vc_grid vc_row vc_grid-gutter-30px vc_pageable-wrapper vc_hook_hover" data-vc-pageable-content="true"><div class="vc_pageable-slide-wrapper vc_clearfix" data-vc-grid-content="true"><div class="vc_grid-item vc_clearfix vc_col-sm-4 vc_grid-item-zone-c-top"><div class="vc_grid-item-mini vc_clearfix "><div class="vc_gitem-zone vc_gitem-zone-c"><div class="vc_gitem-zone-mini"><div class="vc_gitem_row vc_row vc_gitem-row-position-top"><div class="vc_col-sm-12 vc_gitem-col vc_gitem-col-align- vc_custom_1621253598652"><div class="wpb_single_image wpb_content_element vc_align_"><figure class="wpb_wrapper vc_figure"> <a href="https://www.uni.eus/eu/albisteak/poloniako-rzeszow/" class="vc_gitem-link vc_single_image-wrapper vc_box_border_grey" title="Poloniako Rzeszów"><img decoding="async" class="vc_single_image-img " src="https://www.uni.eus/wp-content/uploads/2023/11/Rzeszow-350x210.png" width="350" height="210" alt="Rzeszów" title="Rzeszów" /></a></figure></div><div class="vc_custom_heading vc_gitem-post-data vc_gitem-post-data-source-post_title" ><h3 style="text-align: left;font-family:Nunito;font-weight:400;font-style:normal" ><a href="https://www.uni.eus/eu/albisteak/poloniako-rzeszow/" class="vc_gitem-link" title="Poloniako Rzeszów">Poloniako Rzeszów</a></h3></div><div class="vc_custom_heading vc_gitem-post-data vc_gitem-post-data-source-post_date" ><p style="text-align: left;font-family:Nunito;font-weight:300;font-style:normal" ><a href="https://www.uni.eus/eu/albisteak/poloniako-rzeszow/" class="vc_gitem-link" title="Poloniako Rzeszów">2023/11/20</a></p></div></div></div></div></div><div class="vc_gitem-animated-block " "></div></div><div class="vc_clearfix"></div></div><div class="vc_grid-item vc_clearfix vc_col-sm-4 vc_grid-item-zone-c-top"><div class="vc_grid-item-mini vc_clearfix "><div class="vc_gitem-zone vc_gitem-zone-c"><div class="vc_gitem-zone-mini"><div class="vc_gitem_row vc_row vc_gitem-row-position-top"><div class="vc_col-sm-12 vc_gitem-col vc_gitem-col-align- vc_custom_1621253598652"><div class="wpb_single_image wpb_content_element vc_align_"><figure class="wpb_wrapper vc_figure"> <a href="https://www.uni.eus/eu/albisteak/on-ekin/" class="vc_gitem-link vc_single_image-wrapper vc_box_border_grey" title="On Ekin"><img loading="lazy" decoding="async" class="vc_single_image-img " src="https://www.uni.eus/wp-content/uploads/2023/11/2023-ONEKIN-350x210.jpg" width="350" height="210" alt="JON IRAOLA EIBARKO ALKATEA ETA ANA TELLERIA ZINEGOTZIA &quot;KOMUNIKAZIOA ETA GARDENTASUNA ADMINISTRAZIO PUBLIKOETAN&quot; JARDUNALDIAREN AURKEZPENEAN EIBARKO UDALETXEAN" title="2023-ONEKIN" /></a></figure></div><div class="vc_custom_heading vc_gitem-post-data vc_gitem-post-data-source-post_title" ><h3 style="text-align: left;font-family:Nunito;font-weight:400;font-style:normal" ><a href="https://www.uni.eus/eu/albisteak/on-ekin/" class="vc_gitem-link" title="On Ekin">On Ekin</a></h3></div><div class="vc_custom_heading vc_gitem-post-data vc_gitem-post-data-source-post_date" ><p style="text-align: left;font-family:Nunito;font-weight:300;font-style:normal" ><a href="https://www.uni.eus/eu/albisteak/on-ekin/" class="vc_gitem-link" title="On Ekin">2023/11/12</a></p></div></div></div></div></div><div class="vc_gitem-animated-block " "></div></div><div class="vc_clearfix"></div></div><div class="vc_grid-item vc_clearfix vc_col-sm-4 vc_grid-item-zone-c-top"><div class="vc_grid-item-mini vc_clearfix "><div class="vc_gitem-zone vc_gitem-zone-c"><div class="vc_gitem-zone-mini"><div class="vc_gitem_row vc_row vc_gitem-row-position-top"><div class="vc_col-sm-12 vc_gitem-col vc_gitem-col-align- vc_custom_1621253598652"><div class="wpb_single_image wpb_content_element vc_align_"><figure class="wpb_wrapper vc_figure"> <a href="https://www.uni.eus/eu/albisteak/emeu-valentzia/" class="vc_gitem-link vc_single_image-wrapper vc_box_border_grey" title="EMEU Valentzia"><img loading="lazy" decoding="async" class="vc_single_image-img " src="https://www.uni.eus/wp-content/uploads/2023/11/0_Valentzia-350x210.jpg" width="350" height="210" alt="0_Valentzia" title="0_Valentzia" /></a></figure></div><div class="vc_custom_heading vc_gitem-post-data vc_gitem-post-data-source-post_title" ><h3 style="text-align: left;font-family:Nunito;font-weight:400;font-style:normal" ><a href="https://www.uni.eus/eu/albisteak/emeu-valentzia/" class="vc_gitem-link" title="EMEU Valentzia">EMEU Valentzia</a></h3></div><div class="vc_custom_heading vc_gitem-post-data vc_gitem-post-data-source-post_date" ><p style="text-align: left;font-family:Nunito;font-weight:300;font-style:normal" ><a href="https://www.uni.eus/eu/albisteak/emeu-valentzia/" class="vc_gitem-link" title="EMEU Valentzia">2023/11/10</a></p></div></div></div></div></div><div class="vc_gitem-animated-block " "></div></div><div class="vc_clearfix"></div></div></div></div></div></div></div></div></div><div class="wpb_column vc_column_container vc_col-sm-2"><div class="vc_column-inner"><div class="wpb_wrapper"></div></div></div></div></div></div></div></div><div class="vc_row-full-width vc_clearfix"></div><div class="vc_row wpb_row vc_row-fluid estudiosContainer vc_custom_1622202395435 vc_row-has-fill"><div class="wpb_column vc_column_container vc_col-sm-12"><div class="vc_column-inner"><div class="wpb_wrapper"><div class="wpb_text_column wpb_content_element  vc_custom_1623927400902 topSpace2" ><div class="wpb_wrapper"><h5 style="text-align: center;">Zatoz gurekin!</h5><h2 style="text-align: center;">Ikasketak</h2></div></div><div class="wpb_text_column wpb_content_element  vc_custom_1624893479193 topSpace2" ><div class="wpb_wrapper"><p style="text-align: center;"><a class="btn vc_general vc_btn3 vc_btn3-size-md vc_btn3-shape-round vc_btn3-style-outline vc_btn3-color-white" href="https://www.uni.eus/eu/goi-mailako-zikloak/">Goi Mailako Zikloak</a> <a class="btn vc_general vc_btn3 vc_btn3-size-md vc_btn3-shape-round vc_btn3-style-outline vc_btn3-color-white" href="https://www.uni.eus/eu/erdi-maila/">Erdi Mailako Zikloak</a> <a class="btn vc_general vc_btn3 vc_btn3-size-md vc_btn3-shape-round vc_btn3-style-outline vc_btn3-color-white" href="https://www.uni.eus/eu/espezializazioak/">Espezializazioak</a></p></div></div><div class="vc_row wpb_row vc_inner vc_row-fluid container vc_custom_1621333571639"><div class="wpb_column vc_column_container vc_col-sm-3"><div class="vc_column-inner"><div class="wpb_wrapper"><div  class="wpb_single_image wpb_content_element vc_align_left   no-show-in-mobile zoom"><figure class="wpb_wrapper vc_figure"> <a href="/eu/informatika/" target="_self" class="vc_single_image-wrapper   vc_box_border_grey"><img loading="lazy" decoding="async" width="591" height="591" src="https://www.uni.eus/wp-content/uploads/2021/05/infogramak-UNI-09.png" class="vc_single_image-img attachment-full" alt="" srcset="https://www.uni.eus/wp-content/uploads/2021/05/infogramak-UNI-09.png 591w, https://www.uni.eus/wp-content/uploads/2021/05/infogramak-UNI-09-300x300.png 300w, https://www.uni.eus/wp-content/uploads/2021/05/infogramak-UNI-09-150x150.png 150w, https://www.uni.eus/wp-content/uploads/2021/05/infogramak-UNI-09-60x60.png 60w" sizes="(max-width: 591px) 100vw, 591px" /></a></figure></div><div  class="wpb_single_image wpb_content_element vc_align_left   zoom"><figure class="wpb_wrapper vc_figure"> <a href="/eu/informatika/" target="_self" class="vc_single_image-wrapper   vc_box_border_grey"><img loading="lazy" decoding="async" class="vc_single_image-img " src="https://www.uni.eus/wp-content/uploads/2021/05/Sin-titulo-4-06-e1622039699377-100x100.png" width="100" height="100" alt="Sin título-4-06" title="Sin título-4-06" /></a></figure></div><div class="wpb_text_column wpb_content_element " ><div class="wpb_wrapper"><h4 class="estudios"><a href="/eu/informatika/">Informatika eta Komunikazioak</a></h4></div></div></div></div></div><div class="wpb_column vc_column_container vc_col-sm-3"><div class="vc_column-inner"><div class="wpb_wrapper"><div  class="wpb_single_image wpb_content_element vc_align_left   no-show-in-mobile zoom"><figure class="wpb_wrapper vc_figure"> <a href="/eu/merkataritza/" target="_self" class="vc_single_image-wrapper   vc_box_border_grey"><img loading="lazy" decoding="async" width="591" height="591" src="https://www.uni.eus/wp-content/uploads/2021/05/infogramak-UNI-07.png" class="vc_single_image-img attachment-full" alt="" /></a></figure></div><div  class="wpb_single_image wpb_content_element vc_align_left   zoom"><figure class="wpb_wrapper vc_figure"> <a href="/eu/merkataritza/" target="_self" class="vc_single_image-wrapper   vc_box_border_grey"><img loading="lazy" decoding="async" class="vc_single_image-img " src="https://www.uni.eus/wp-content/uploads/2021/05/komertzioaZ-e1622051395634-100x100.png" width="100" height="100" alt="komertzioaZ" title="komertzioaZ" /></a></figure></div><div class="wpb_text_column wpb_content_element " ><div class="wpb_wrapper"><h4 class="estudios"><a href="/eu/merkataritza/">Merkataritza</a></h4></div></div></div></div></div><div class="wpb_column vc_column_container vc_col-sm-3"><div class="vc_column-inner"><div class="wpb_wrapper"><div  class="wpb_single_image wpb_content_element vc_align_left   no-show-in-mobile zoom"><figure class="wpb_wrapper vc_figure"> <a href="/eu/administrazioa-eta-kudeaketa/" target="_self" class="vc_single_image-wrapper   vc_box_border_grey"><img loading="lazy" decoding="async" width="150" height="150" src="https://www.uni.eus/wp-content/uploads/2021/05/infogramak-UNI-08.png" class="vc_single_image-img attachment-thumbnail" alt="" /></a></figure></div><div  class="wpb_single_image wpb_content_element vc_align_left"><figure class="wpb_wrapper vc_figure"> <a href="/eu/administrazioa-eta-kudeaketa/" target="_self" class="vc_single_image-wrapper   vc_box_border_grey"><img loading="lazy" decoding="async" class="vc_single_image-img " src="https://www.uni.eus/wp-content/uploads/2021/05/AdministazioaZ-e1622032918865-100x100.png" width="100" height="100" alt="AdministazioaZ" title="AdministazioaZ" /></a></figure></div><div class="wpb_text_column wpb_content_element " ><div class="wpb_wrapper"><h4 class="estudios"><a href="/eu/administrazioa-eta-kudeaketa/">Administrazioa eta Kudeaketa</a></h4></div></div></div></div></div><div class="wpb_column vc_column_container vc_col-sm-3"><div class="vc_column-inner"><div class="wpb_wrapper"><div  class="wpb_single_image wpb_content_element vc_align_left   no-show-in-mobile"><figure class="wpb_wrapper vc_figure"> <a href="/eu/gorputz-eta-kirol-jarduerak/" target="_self" class="vc_single_image-wrapper   vc_box_border_grey"><img loading="lazy" decoding="async" width="150" height="150" src="https://www.uni.eus/wp-content/uploads/2021/05/infogramak-UNI-10.png" class="vc_single_image-img attachment-thumbnail" alt="" /></a></figure></div><div  class="wpb_single_image wpb_content_element vc_align_left"><figure class="wpb_wrapper vc_figure"> <a href="/eu/gorputz-eta-kirol-jarduerak/" target="_self" class="vc_single_image-wrapper   vc_box_border_grey"><img loading="lazy" decoding="async" class="vc_single_image-img " src="https://www.uni.eus/wp-content/uploads/2021/05/Sin-titulo-4-05-e1622032873850-100x100.png" width="100" height="100" alt="Sin título-4-05" title="Sin título-4-05" /></a></figure></div><div class="wpb_text_column wpb_content_element " ><div class="wpb_wrapper"><h4 class="estudios"><a href="/eu/gorputz-eta-kirol-jarduerak/">Gorputz eta Kirol Jarduerak</a></h4></div></div></div></div></div></div><div class="vc_row wpb_row vc_inner vc_row-fluid vc_row-o-content-middle vc_row-flex"><div class="wpb_column vc_column_container vc_col-sm-12"><div class="vc_column-inner vc_custom_1620996062173"><div class="wpb_wrapper"><section class="vc_cta3-container"><div class="vc_general vc_cta3 vc_cta3-style-flat vc_cta3-shape-square vc_cta3-align-center vc_cta3-color-classic vc_cta3-icon-size-md vc_cta3-actions-bottom vc_custom_1624003970765"><div class="vc_cta3_content-container"><div class="vc_cta3-content"><header class="vc_cta3-content-header"></header><p class="text-align: center; color: white !important;">Langile eta langabetuei zuzendutako ikastaroak</p></div><div class="vc_cta3-actions"><div class="vc_btn3-container vc_btn3-inline" ><a class="vc_general vc_btn3 vc_btn3-size-md vc_btn3-shape-round vc_btn3-style-outline vc_btn3-color-white" href="http://uni.eus/eu/lanerako-prestakuntza/" title="Lanerako Prestakuntza">Lanerako prestakuntza</a></div></div></div></div></section></div></div></div></div></div></div></div></div></section><div class="vc_row-full-width vc_clearfix"></div><div data-vc-full-width="true" data-vc-full-width-init="false" class="vc_row wpb_row vc_row-fluid container vc_custom_1620998394186"><div class="wpb_column vc_column_container vc_col-sm-6"><div class="vc_column-inner vc_custom_1622201560983"><div class="wpb_wrapper"><div class="wpb_text_column wpb_content_element  vc_custom_1629705933000 topSpace" ><div class="wpb_wrapper"><h5>Uni eibar ermua</h5><h2>International students</h2><p>We offer stages for exchange students in the frame of Erasmus+ and EMEU projects.</p></div></div><div class="vc_btn3-container vc_btn3-inline vc_custom_1626171440660" ><a style="background-color:#705a88; color:#ffffff;" class="vc_general vc_btn3 vc_btn3-size-md vc_btn3-shape-round vc_btn3-style-custom" href="/eu/ikastetxea/international-students/" title="">More</a></div></div></div></div><div class="wpb_column vc_column_container vc_col-sm-6"><div class="vc_column-inner vc_custom_1620998042808"><div class="wpb_wrapper"><div  class="wpb_single_image wpb_content_element vc_align_left  vc_custom_1622107445108  borobildua"><figure class="wpb_wrapper vc_figure"><div class="vc_single_image-wrapper   vc_box_border_grey"><img loading="lazy" decoding="async" class="vc_single_image-img " src="https://www.uni.eus/wp-content/uploads/2021/05/UEB_0809-540x440.jpg" width="540" height="440" alt="UEB_0809" title="UEB_0809" /></div></figure></div></div></div></div></div><div class="vc_row-full-width vc_clearfix"></div><div data-vc-full-width="true" data-vc-full-width-init="false" data-vc-stretch-content="true" class="vc_row wpb_row vc_row-fluid vc_custom_1621442487141 vc_row-has-fill vc_row-no-padding"><div class="wpb_column vc_column_container vc_col-sm-12"><div class="vc_column-inner"><div class="wpb_wrapper"><div class="wpb_text_column wpb_content_element  estudiosContainer" ><div class="wpb_wrapper"><h2 style="text-align: center;"><a class="white" href="https://www.uni.eus/eu/kontaktua/">Kontaktua</a></h2><p style="text-align: center;"><a class="white" href="https://www.uni.eus/eu/lege-oharra/">Lege Oharra</a></p></div></div></div></div></div></div><div class="vc_row-full-width vc_clearfix"></div><div class="clearfix"></div></div></div><footer class="dark-wrapper inverse-text"><div class="container inner pt-60 pb-60"><div class="row"><div class="col-sm-4"><div id="block-8" class="widget widget_block widget_text"><p>Otaola Hiribidea, 29<br>20600 Eibar, Gipuzkoa<br>idazkaritza@uni.eus<br>943 89 92 11</p></div><div id="block-23" class="widget widget_block"><div class="wp-block-columns is-layout-flex wp-container-core-columns-layout-2 wp-block-columns-is-layout-flex"><div class="wp-block-column is-layout-flow wp-block-column-is-layout-flow" style="flex-basis:66.66%"><div class="wp-block-columns is-layout-flex wp-container-core-columns-layout-1 wp-block-columns-is-layout-flex"><div class="wp-block-column is-layout-flow wp-block-column-is-layout-flow"><figure class="wp-block-image size-full is-resized"><a href="https://www.instagram.com/uni.eus"><img loading="lazy" decoding="async" width="452" height="452" src="https://www.uni.eus/wp-content/uploads/2023/11/LogoInsta-1.png" alt="" class="wp-image-3957" style="width:58px;height:auto" srcset="https://www.uni.eus/wp-content/uploads/2023/11/LogoInsta-1.png 452w, https://www.uni.eus/wp-content/uploads/2023/11/LogoInsta-1-210x210.png 210w, https://www.uni.eus/wp-content/uploads/2023/11/LogoInsta-1-150x150.png 150w, https://www.uni.eus/wp-content/uploads/2023/11/LogoInsta-1-60x60.png 60w" sizes="(max-width: 452px) 100vw, 452px" /></a></figure></div><div class="wp-block-column is-layout-flow wp-block-column-is-layout-flow"><figure class="wp-block-image size-full is-resized"><a href="https://www.facebook.com/iesunibhi"><img loading="lazy" decoding="async" width="452" height="452" src="https://www.uni.eus/wp-content/uploads/2023/11/LogoFacebook-1.png" alt="" class="wp-image-3958" style="width:58px;height:auto" srcset="https://www.uni.eus/wp-content/uploads/2023/11/LogoFacebook-1.png 452w, https://www.uni.eus/wp-content/uploads/2023/11/LogoFacebook-1-210x210.png 210w, https://www.uni.eus/wp-content/uploads/2023/11/LogoFacebook-1-150x150.png 150w, https://www.uni.eus/wp-content/uploads/2023/11/LogoFacebook-1-60x60.png 60w" sizes="(max-width: 452px) 100vw, 452px" /></a></figure></div><div class="wp-block-column is-layout-flow wp-block-column-is-layout-flow"><figure class="wp-block-image size-full is-resized"><a href="https://www.youtube.com/@unieibar-ermua5517"><img loading="lazy" decoding="async" width="452" height="451" src="https://www.uni.eus/wp-content/uploads/2023/11/LogoYoutube.png" alt="" class="wp-image-3955" style="width:58px;height:auto" srcset="https://www.uni.eus/wp-content/uploads/2023/11/LogoYoutube.png 452w, https://www.uni.eus/wp-content/uploads/2023/11/LogoYoutube-210x210.png 210w, https://www.uni.eus/wp-content/uploads/2023/11/LogoYoutube-150x150.png 150w, https://www.uni.eus/wp-content/uploads/2023/11/LogoYoutube-60x60.png 60w" sizes="(max-width: 452px) 100vw, 452px" /></a></figure></div></div></div><div class="wp-block-column is-layout-flow wp-block-column-is-layout-flow" style="flex-basis:33.33%"></div></div></div></div><div class="col-sm-4"><div id="block-6" class="widget widget_block widget_media_image"><figure class="wp-block-image size-full"><img loading="lazy" decoding="async" width="390" height="177" src="https://www.uni.eus/wp-content/uploads/2021/05/infogramak-UNI-45-Z-e1621236664786.png" alt="UNI-logoa-zuria" class="wp-image-20" srcset="https://www.uni.eus/wp-content/uploads/2021/05/infogramak-UNI-45-Z-e1621236664786.png 390w, https://www.uni.eus/wp-content/uploads/2021/05/infogramak-UNI-45-Z-e1621236664786-300x136.png 300w" sizes="(max-width: 390px) 100vw, 390px" /></figure></div></div><div class="col-sm-4"><div id="block-5" class="widget widget_block widget_media_image"><figure class="wp-block-image size-full"><img loading="lazy" decoding="async" width="223" height="144" src="https://www.uni.eus/wp-content/uploads/2021/05/infogramak-UNI-46-Z-1-e1621236817248.png" alt="eusko-jaurlaritza-logoa" class="wp-image-396"/></figure></div></div><div class="clear"></div></div></div><div class="sub-footer dark-wrapper inverse-text"><div class="container inner text-center"><p><a href="https://www.uni.eus">Uni Eibar-Ermua</a></p></div></div></footer><div id="cmplz-cookiebanner-container"><div class="cmplz-cookiebanner cmplz-hidden banner-1 optin cmplz-bottom cmplz-categories-type-view-preferences" aria-modal="true" data-nosnippet="true" role="dialog" aria-live="polite" aria-labelledby="cmplz-header-1-optin" aria-describedby="cmplz-message-1-optin"><div class="cmplz-header"><div class="cmplz-logo"></div><div class="cmplz-title" id="cmplz-header-1-optin">Gestionar el Consentimiento de las Cookies</div><div class="cmplz-close" tabindex="0" role="button" aria-label="close-dialog"> <svg aria-hidden="true" focusable="false" data-prefix="fas" data-icon="times" class="svg-inline--fa fa-times fa-w-11" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 352 512"><path fill="currentColor" d="M242.72 256l100.07-100.07c12.28-12.28 12.28-32.19 0-44.48l-22.24-22.24c-12.28-12.28-32.19-12.28-44.48 0L176 189.28 75.93 89.21c-12.28-12.28-32.19-12.28-44.48 0L9.21 111.45c-12.28 12.28-12.28 32.19 0 44.48L109.28 256 9.21 356.07c-12.28 12.28-12.28 32.19 0 44.48l22.24 22.24c12.28 12.28 32.2 12.28 44.48 0L176 322.72l100.07 100.07c12.28 12.28 32.2 12.28 44.48 0l22.24-22.24c12.28-12.28 12.28-32.19 0-44.48L242.72 256z"></path></svg></div></div><div class="cmplz-divider cmplz-divider-header"></div><div class="cmplz-body"><div class="cmplz-message" id="cmplz-message-1-optin">Cookieak erabiltzen ditugu gure webgunea eta zerbitzua optimizatzeko.</div><div class="cmplz-categories"> <details class="cmplz-category cmplz-functional" > <summary> <span class="cmplz-category-header"> <span class="cmplz-category-title">Funcionala</span> <span class='cmplz-always-active'> <span class="cmplz-banner-checkbox"> <input type="checkbox"
 id="cmplz-functional-optin"
 data-category="cmplz_functional"
 class="cmplz-consent-checkbox cmplz-functional"
 size="40"
 value="1"/> <label class="cmplz-label" for="cmplz-functional-optin" tabindex="0"><span class="screen-reader-text">Funcionala</span></label> </span> Always active </span> <span class="cmplz-icon cmplz-open"> <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"  height="18" ><path d="M224 416c-8.188 0-16.38-3.125-22.62-9.375l-192-192c-12.5-12.5-12.5-32.75 0-45.25s32.75-12.5 45.25 0L224 338.8l169.4-169.4c12.5-12.5 32.75-12.5 45.25 0s12.5 32.75 0 45.25l-192 192C240.4 412.9 232.2 416 224 416z"/></svg> </span> </span> </summary><div class="cmplz-description"> <span class="cmplz-description-functional">The technical storage or access is strictly necessary for the legitimate purpose of enabling the use of a specific service explicitly requested by the subscriber or user, or for the sole purpose of carrying out the transmission of a communication over an electronic communications network.</span></div> </details> <details class="cmplz-category cmplz-preferences" > <summary> <span class="cmplz-category-header"> <span class="cmplz-category-title">Ezarpenak</span> <span class="cmplz-banner-checkbox"> <input type="checkbox"
 id="cmplz-preferences-optin"
 data-category="cmplz_preferences"
 class="cmplz-consent-checkbox cmplz-preferences"
 size="40"
 value="1"/> <label class="cmplz-label" for="cmplz-preferences-optin" tabindex="0"><span class="screen-reader-text">Ezarpenak</span></label> </span> <span class="cmplz-icon cmplz-open"> <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"  height="18" ><path d="M224 416c-8.188 0-16.38-3.125-22.62-9.375l-192-192c-12.5-12.5-12.5-32.75 0-45.25s32.75-12.5 45.25 0L224 338.8l169.4-169.4c12.5-12.5 32.75-12.5 45.25 0s12.5 32.75 0 45.25l-192 192C240.4 412.9 232.2 416 224 416z"/></svg> </span> </span> </summary><div class="cmplz-description"> <span class="cmplz-description-preferences">The technical storage or access is necessary for the legitimate purpose of storing preferences that are not requested by the subscriber or user.</span></div> </details> <details class="cmplz-category cmplz-statistics" > <summary> <span class="cmplz-category-header"> <span class="cmplz-category-title">Estatistikak</span> <span class="cmplz-banner-checkbox"> <input type="checkbox"
 id="cmplz-statistics-optin"
 data-category="cmplz_statistics"
 class="cmplz-consent-checkbox cmplz-statistics"
 size="40"
 value="1"/> <label class="cmplz-label" for="cmplz-statistics-optin" tabindex="0"><span class="screen-reader-text">Estatistikak</span></label> </span> <span class="cmplz-icon cmplz-open"> <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"  height="18" ><path d="M224 416c-8.188 0-16.38-3.125-22.62-9.375l-192-192c-12.5-12.5-12.5-32.75 0-45.25s32.75-12.5 45.25 0L224 338.8l169.4-169.4c12.5-12.5 32.75-12.5 45.25 0s12.5 32.75 0 45.25l-192 192C240.4 412.9 232.2 416 224 416z"/></svg> </span> </span> </summary><div class="cmplz-description"> <span class="cmplz-description-statistics">The technical storage or access that is used exclusively for statistical purposes.</span> <span class="cmplz-description-statistics-anonymous">The technical storage or access that is used exclusively for anonymous statistical purposes. Without a subpoena, voluntary compliance on the part of your Internet Service Provider, or additional records from a third party, information stored or retrieved for this purpose alone cannot usually be used to identify you.</span></div> </details> <details class="cmplz-category cmplz-marketing" > <summary> <span class="cmplz-category-header"> <span class="cmplz-category-title">Marketing</span> <span class="cmplz-banner-checkbox"> <input type="checkbox"
 id="cmplz-marketing-optin"
 data-category="cmplz_marketing"
 class="cmplz-consent-checkbox cmplz-marketing"
 size="40"
 value="1"/> <label class="cmplz-label" for="cmplz-marketing-optin" tabindex="0"><span class="screen-reader-text">Marketing</span></label> </span> <span class="cmplz-icon cmplz-open"> <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"  height="18" ><path d="M224 416c-8.188 0-16.38-3.125-22.62-9.375l-192-192c-12.5-12.5-12.5-32.75 0-45.25s32.75-12.5 45.25 0L224 338.8l169.4-169.4c12.5-12.5 32.75-12.5 45.25 0s12.5 32.75 0 45.25l-192 192C240.4 412.9 232.2 416 224 416z"/></svg> </span> </span> </summary><div class="cmplz-description"> <span class="cmplz-description-marketing">The technical storage or access is required to create user profiles to send advertising, or to track the user on a website or across several websites for similar marketing purposes.</span></div> </details></div></div><div class="cmplz-links cmplz-information"> <a class="cmplz-link cmplz-manage-options cookie-statement" href="#" data-relative_url="#cmplz-manage-consent-container">Manage options</a> <a class="cmplz-link cmplz-manage-third-parties cookie-statement" href="#" data-relative_url="#cmplz-cookies-overview">Manage services</a> <a class="cmplz-link cmplz-manage-vendors tcf cookie-statement" href="#" data-relative_url="#cmplz-tcf-wrapper">Manage {vendor_count} vendors</a> <a class="cmplz-link cmplz-external cmplz-read-more-purposes tcf" target="_blank" rel="noopener noreferrer nofollow" href="https://cookiedatabase.org/tcf/purposes/">Read more about these purposes</a></div><div class="cmplz-divider cmplz-footer"></div><div class="cmplz-buttons"> <button class="cmplz-btn cmplz-accept">Onartzen dut</button> <button class="cmplz-btn cmplz-deny">Baztertu</button> <button class="cmplz-btn cmplz-view-preferences">Ezarpenak</button> <button class="cmplz-btn cmplz-save-preferences">Gorde ezarpenak</button> <a class="cmplz-btn cmplz-manage-options tcf cookie-statement" href="#" data-relative_url="#cmplz-manage-consent-container">Ezarpenak</a></div><div class="cmplz-links cmplz-documents"> <a class="cmplz-link cookie-statement" href="#" data-relative_url="">{title}</a> <a class="cmplz-link privacy-statement" href="#" data-relative_url="">{title}</a> <a class="cmplz-link impressum" href="#" data-relative_url="">{title}</a></div></div></div><div id="cmplz-manage-consent" data-nosnippet="true"><button class="cmplz-btn cmplz-hidden cmplz-manage-consent manage-consent-1">Baimena kudeatu</button></div><link href="https://fonts.googleapis.com/css?family=Roboto:400%7CNunito+Sans:700" rel="stylesheet" property="stylesheet" media="all" type="text/css" > <script type="text/javascript">if(typeof revslider_showDoubleJqueryError === "undefined") {
			function revslider_showDoubleJqueryError(sliderID) {
				var err = "<div class='rs_error_message_box'>";
				err += "<div class='rs_error_message_oops'>Oops...</div>";
				err += "<div class='rs_error_message_content'>";
				err += "You have some jquery.js library include that comes after the Slider Revolution files js inclusion.<br>";
				err += "To fix this, you can:<br>&nbsp;&nbsp;&nbsp; 1. Set 'Module General Options' -> 'Advanced' -> 'jQuery & OutPut Filters' -> 'Put JS to Body' to on";
				err += "<br>&nbsp;&nbsp;&nbsp; 2. Find the double jQuery.js inclusion and remove it";
				err += "</div>";
			err += "</div>";
				var slider = document.getElementById(sliderID); slider.innerHTML = err; slider.style.display = "block";
			}
		}</script> <link rel='stylesheet' id='vc_animate-css-css' href='https://www.uni.eus/wp-content/plugins/js_composer/assets/lib/bower/animate-css/animate.min.css?ver=6.5.0' type='text/css' media='all' /><link rel='stylesheet' id='prettyphoto-css' href='https://www.uni.eus/wp-content/plugins/js_composer/assets/lib/prettyphoto/css/prettyPhoto.min.css?ver=6.5.0' type='text/css' media='all' /><link rel='stylesheet' id='vc_pageable_owl-carousel-css-css' href='https://www.uni.eus/wp-content/plugins/js_composer/assets/lib/owl-carousel2-dist/assets/owl.min.css?ver=6.5.0' type='text/css' media='all' /><link rel='stylesheet' id='vc_google_fonts_nunito300regular700-css' href='https://fonts.googleapis.com/css?family=Nunito%3A300%2Cregular%2C700&#038;ver=6.5.0' type='text/css' media='all' /><style id='core-block-supports-inline-css' type='text/css'>.wp-container-core-columns-layout-1.wp-container-core-columns-layout-1{flex-wrap:nowrap;}.wp-container-core-columns-layout-2.wp-container-core-columns-layout-2{flex-wrap:nowrap;}</style> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_a53a916adf48efefd5a2aa0861ebbc07.js?ver=5.8.3" id="swv-js"></script> <script type="text/javascript" id="contact-form-7-js-extra">var wpcf7 = {"api":{"root":"https:\/\/www.uni.eus\/wp-json\/","namespace":"contact-form-7\/v1"}};</script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_83a062cf6545b990c13b4398035a29d0.js?ver=5.8.3" id="contact-form-7-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/themes/creatink/style/js/bootstrap.min.js?ver=1.0.0" id="bootstrap-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_8cccb00f6290db316544b6e8e2e8b00e.js?ver=1.0.0" id="aos-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_20079d448b4a999631548dde5b88509f.js?ver=1.0.0" id="circleinfo-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_4e290f4d47ac29bc0a27667367f4a56c.js?ver=1.0.0" id="cocoen-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_26dd34e2402323f4453d4be25fec5398.js?ver=1.0.0" id="collage-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_06c613219216717f9161c78c84109d12.js?ver=1.0.0" id="countdown-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_ef36cca760bf1cd76cfcd0e4dc10cef1.js?ver=1.0.0" id="counterup-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_fd1a4462d8802221ac23b5039dc1ad94.js?ver=1.0.0" id="easing-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_40f2164154c217e99eaf751d1cb8e581.js?ver=1.0.0" id="flickr-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_fa07f10043b891dacdb82f26fd2b42bc.js?ver=1.0.0" id="fitvids-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_78cdd7c9574849cc14108e709c453ea4.js?ver=1.0.0" id="fotorama-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_204436b6ede5576caf4ec04246926070.js?ver=1.0.0" id="goodshare-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_6a1a46e15cacaa2df7428347c75f737e.js?ver=1.0.0" id="gtt-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-includes/js/imagesloaded.min.js?ver=5.0.0" id="imagesloaded-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_1b9d5439b41e462220f9e6937df15b60.js?ver=1.0.0" id="instafeed-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/plugins/js_composer/assets/lib/bower/isotope/dist/isotope.pkgd.min.js?ver=6.5.0" id="isotope-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_c5916620e03bbeb22a568721c0049529.js?ver=1.0.0" id="jribbble-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_9087d3e7b560feb4dac2397325af484b.js?ver=1.0.0" id="lightgallery-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_d5843dbdc71ff8014a5eafd346a262da.js?ver=1.0.0" id="mousewheel-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_d3325bc1d59dae5aedda1c5ead0cd1d6.js?ver=1.0.0" id="picturefill-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_0422ef2b6b0c2bd9f0b0fe22dd33ef0b.js?ver=1.0.0" id="plyr-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_e48937dc9af0828f7794a0759465b358.js?ver=1.0.0" id="prettify-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_1961cfaa8c7c85368d9993100137b1f4.js?ver=1.0.0" id="progressbar-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_674afbcf8fee3648604913abdfa2685f.js?ver=1.0.0" id="slick-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_563169b88a5c9463dbb9b0b63fdbdc47.js?ver=1.0.0" id="smartmenus-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_e4b4ccedf82fa8d5cebd6327c6191e0b.js?ver=1.0.0" id="stickyheader-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_12380ef34308867b226c62f1552a438a.js?ver=1.0.0" id="typer-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_dfe0eedf8da578f4a4c43b05448c51d9.js?ver=1.0.0" id="waypoints-js"></script> <script type="text/javascript" id="ebor-scripts-js-extra">var creatink_data = {"overlay_style":"overlay overlay1"};</script> <script type="text/javascript" src="https://www.uni.eus/wp-content/cache/autoptimize/js/autoptimize_single_e7b1bc85aeed7e7174df1094fbffed91.js?ver=1.0.0" id="ebor-scripts-js"></script> <script type="text/javascript" id="cmplz-cookiebanner-js-extra">var complianz = {"prefix":"cmplz_","user_banner_id":"1","set_cookies":[],"block_ajax_content":"","banner_version":"25","version":"6.5.5","store_consent":"","do_not_track_enabled":"1","consenttype":"optin","region":"eu","geoip":"","dismiss_timeout":"","disable_cookiebanner":"","soft_cookiewall":"","dismiss_on_scroll":"","cookie_expiry":"365","url":"https:\/\/www.uni.eus\/wp-json\/complianz\/v1\/","locale":"lang=eu&locale=eu","set_cookies_on_root":"","cookie_domain":"","current_policy_id":"13","cookie_path":"\/","categories":{"statistics":"statistics","marketing":"marketing"},"tcf_active":"","placeholdertext":"Click to accept {category} cookies and enable this content","aria_label":"Click to accept {category} cookies and enable this content","css_file":"https:\/\/www.uni.eus\/wp-content\/uploads\/complianz\/css\/banner-{banner_id}-{type}.css?v=25","page_links":{"eu":{"cookie-statement":{"title":"Cookien politika ","url":"https:\/\/www.uni.eus\/eu\/cookien-politika\/"},"privacy-statement":{"title":"Lege Oharra","url":"https:\/\/www.uni.eus\/eu\/lege-oharra\/"}}},"tm_categories":"","forceEnableStats":"","preview":"","clean_cookies":""};</script> <script defer type="text/javascript" src="https://www.uni.eus/wp-content/plugins/complianz-gdpr/cookiebanner/js/complianz.min.js?ver=6.5.5" id="cmplz-cookiebanner-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/plugins/js_composer/assets/js/dist/js_composer_front.min.js?ver=6.5.0" id="wpb_composer_front_js-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/plugins/js_composer/assets/lib/vc_waypoints/vc-waypoints.min.js?ver=6.5.0" id="vc_waypoints-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/plugins/js_composer/assets/lib/prettyphoto/js/jquery.prettyPhoto.min.js?ver=6.5.0" id="prettyphoto-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/plugins/js_composer/assets/lib/owl-carousel2-dist/owl.carousel.min.js?ver=6.5.0" id="vc_pageable_owl-carousel-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/plugins/js_composer/assets/lib/bower/imagesloaded/imagesloaded.pkgd.min.js?ver=6.5.0" id="vc_grid-js-imagesloaded-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-includes/js/underscore.min.js?ver=1.13.4" id="underscore-js"></script> <script type="text/javascript" src="https://www.uni.eus/wp-content/plugins/js_composer/assets/js/dist/vc_grid.min.js?ver=6.5.0" id="vc_grid-js"></script> <script type="text/plain" data-service="google-analytics" async data-category="statistics" data-cmplz-src="https://www.googletagmanager.com/gtag/js?id=G-MBCP5Y9TFB"></script> <script type="text/plain" data-category="statistics">window['gtag_enable_tcf_support'] = false;
window.dataLayer = window.dataLayer || [];
function gtag(){dataLayer.push(arguments);}
gtag('js', new Date());
gtag('config', 'G-MBCP5Y9TFB', {
	cookie_flags:'secure;samesite=none',
	
});</script></body></html>
BUILD SUCCESSFUL (total time: 1 second)

```

</details>
