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

Atari honetan eskuragarri duzu dokumentazioa UNI Eibar-Ermua ikastetxeko **Plataforma anitzeko aplikazioen garapena (PAAG)** zikloko bigarren mailakoa den **Zerbitzuen eta prozesuen programazioa** ikasgairako.&#x20;

## Programazio konkurrentea

Ikasturtean zehar presente egongo den kontzeptua da programazio konkurrentearena. Programazio konkurrenteaz ari garenean, bereizi egin behar ditugu nukleo bakarreko exekuzioa, makina bereko nukleo desberdinetako exekuzioa (programazio paraleloa) eta prozesadore edo makina desberdinetako nukleo bateko baino gehiagoko exekuzioa (programazio banatua).

Orain dela ez hainbeste arte, ordenagailuek nukleo bakarra zuten, eta prozesuak banan-banan exekutatzen ziren, nahiz eta prozesuen arteko testuinguru-aldaketa hain azkarra izan, non paraleloan funtzionatzen zutela iruditu zitzaigun, musika entzuten genuen bitartean dokumentu bat idazten genuenean bezala. Horregatik, prozesu batek, adibidez, 4 segundo behar baditu amaitzeko eta beste batek 6 segundo, bi prozesuek 10 segundo behar dituzte amaitzeko. Era konkretu honetako konkurrentzian ez dago denbora aurrerapenik, gauzak aldiberean dabiltzanaren irudikapena baizik.&#x20;

Gaur egun, nukleo anitzeko prozesadoreak erabiltzen ditugun ordenagailu edo sistema digital gehienetan daude, eta hainbat prozesuren exekuzio paraleloa exekuzio denbora laburtzen duen errealitate bat da. Aurreko adibideari dagokionez, bi prozesuen exekuzio paraleloaren kasuan, emandako denbora 6 segundokoa izan beharko litzateke, exekuzioa amaitzeko denbora gehiago beharko lukeen bigarren prozesua baita.

<figure><img src="https://737682242-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F1fkTiBk8oxbo9vMUdfVS%2Fuploads%2Fgit-blob-3babea7c132b401d949024985243a58ea855d983%2FConcurrent.drawio.svg?alt=media" alt=""><figcaption><p>Konkurrentzia nukleo bakarreko prozesadorean eta konkurrentzia paralelismoan nukleo ugaridun prozesadorean</p></figcaption></figure>

Bistakoa da aurrerapena nabarmena dela. Azaltzea baino hobe denez ikustea, eutsi hurrengoari!

<details>

<summary>Adibide praktikoa: kutxazainarena</summary>

## Multiataza eta hariak Javaz (Thread & Runnable)

Javako Threads edo hariekin lan egiteko moduak ikusiko ditugu, azaletik. Adibide praktiko bezala aukerkeztuko da, programazio konkurrentea (_multiprogramazioa_) eta programazio paraleloa (_multiataza_) teorikoki argitu ostean egin ere.

Funtsean, multiatazak hainbat prozesu aldi berean exekutatzeko aukera ematen digu; hau da, modu konkurrentean, eta, beraz, horrek aukera ematen digu denbora laburragoan exekutatzen diren eta eraginkorragoak diren programak egiteko. Ezin ditugu prozesu amaigabeak modu konkurrentean exekutatu, hardwareak bere mugak baititu, baina gaur egun nukleo bat baino gehiago dituzte ordenagailuak. Prozesadore bakoitzak prozesu bakarra hartu dezake. Beraz, bi nukleoko prozesadore batean bi prozesu batera exekutatu litezke. Programak kodetuko ditugu libutegi bereziekin ahalik eta etekin onena ateratzeko hardware baliabideeei. Azalpenak arintzearren irudietan dakusagu 4 prozesu exekutatu behar dituen programa sekuentzial bat dugula: eginbeharrak bata bestearen atzetik zerbitzatuko dira. Zeregin horietako bakoitzak denbora bat beharko duela aurreikusi daiteke:

<img src="https://jarroba.com/wp-content/uploads/2014/05/Threads_Un_unico_hilo.png" alt="" data-size="original">

Sekuentzialki egin beharrean, 4 harirekin egingo bagenu, programak 20 segundo baino ez lituzke beharko exekutatzeko, hau da, prozesurik luzeena exekutatzeko beharko lukeen denbora. Hori litzateke ideala (jakina!) baina errealitatean kode guztia ez dago paralelizatzerik. Traba da baita ere modu eraginkorrean abiaraz ditzakegun paraleloko prozesuen kopuruaren muga. Ez dugu sarrera honetan jardungo horretaz helburua ez baita besterik ikustea baino Java lengoian hariak martxan adibide argigarri batekin.

<img src="https://jarroba.com/wp-content/uploads/2014/05/Threads_Varios_hilos.png" alt="" data-size="original">

Javaz multiataza erabiltzeko, _**Thread**_ klasea erabili behar dugu (hau da, inplementatzen dugun klaseak Thread klasetik heredatu behar du), eta Thread klaseak _**Runnable**_ interfazea inplementatzen du. Hurrengo klase-diagraman, Runnable interfazea eta Thread klasea erakutsiko ditugu, metodo nagusiekin:

<img src="https://jarroba.com/wp-content/uploads/2014/05/MultiHilos_Jarroba_Diagrama_de_clases.jpg" alt="" data-size="original">

Lehen hurbilpena baino ez da honakoa programazio paraleloak ulertzeko, eta, horregatik, ez ditugu ikusiko Thread klaseko metodo guztiak nola erabili behar diren, baina erakutsiko dizkizuegu badaudela jakin dezazuen, eta, gainera, haien izenaz balia zaitezkete. Adibide bidez ikasiko ditugu aldeak, programa bat multiataza darabilena, eta, bestea ordea, gabe. Nola exekutatuko bakoitza?

### Supermerkatuan kutxazain bakarra zegoenekoa

Supermerkatu baten kobrantza-prozesua simulatuko dugu; hau da, bezero batzuk produktuz betetako orga batekin doaz eta kutxazain batek produktuak kobratzen dizkie, banan-banan kutxa erregistratzailearen eskanerretik pasatuz. Kasu horretan, kutxazainak bezeroari egindako erosketa prozesatu behar du, hau da, lehenengo 1 bezeroari kobratzen dio, gero 2 bezeroari, eta horrela hurrenez hurren. Horretarako, "Kutxazain" klase bat eta "Bezero" klase bat definituko ditugu. Klase horrek "osoko array" bat izango du, erosi dituen produktuak eta kutxazainak produktua eskanerretik pasatzeko behar duen denbora adierazteko; hau da, array bat badugu `[1,3,5]`, adierazteko da bezeroak 3 produktu erosi dituela eta kutxazainak lehen produktuan 'segundo 1' beharko duela, bigarren produktua pasatzeko '3 segundo'  beharko dituela eta hirugarren produktua prozesatzeko '5 segundo'. Beraz, bezeroari erosketa guztia kobratzeko "9 segundo" beharko ditu.

Adibide hau azalduta, klase hauek nola definitu ditugun ikusiko dug`Cajera.java` klasea:

```java
public class Cajera {

private String nombre;

// Constructor, getter y setter

public void procesarCompra(Cliente cliente, long timeStamp) {

	System.out.println("La cajera " + this.nombre + 
			" COMIENZA A PROCESAR LA COMPRA DEL CLIENTE " + cliente.getNombre() + 
			" EN EL TIEMPO: " + (System.currentTimeMillis() - timeStamp) / 1000	+
			"seg");

	for (int i = 0; i < cliente.getCarroCompra().length; i++) { 
			this.esperarXsegundos(cliente.getCarroCompra()[i]); 
			System.out.println("Procesado el producto " + (i + 1) +  
			" ->Tiempo: " + (System.currentTimeMillis() - timeStamp) / 1000 + 
			"seg");
	}

	System.out.println("La cajera " + this.nombre + " HA TERMINADO DE PROCESAR " + 
			cliente.getNombre() + " EN EL TIEMPO: " + 
			(System.currentTimeMillis() - timeStamp) / 1000 + "seg");

}


private void esperarXsegundos(int segundos) {
	try {
		Thread.sleep(segundos * 1000);
	} catch (InterruptedException ex) {
		Thread.currentThread().interrupt();
	}
}

}
```

`Cliente.java` klasea:

```java
public class Cliente {

private String nombre;
private int[] carroCompra;

// Constructor, getter y setter

}
```

Proposatutako programa hori bi bezerorekin eta prozesu bakarrarekin exekutatuko bagenu (hori da normalean egiten dena), lehenengo aurreneko bezeroaren erosketa prozesatuko litzateke eta, ondoren, bigarren bezeroarena. Hortik, 1. bezeroaren + 2. bezeroaren denbora batu beharra exekuzioa bukatzerako. Jarraian, programa abiarazteko `Main` metodoa nola programatzen dugun ikusiko dugu.&#x20;

`Main.java` klasea:

```java
public class Main {

public static void main(String[] args) {

	Cliente cliente1 = new Cliente("Cliente 1", new int[] { 2, 2, 1, 5, 2, 3 });
	Cliente cliente2 = new Cliente("Cliente 2", new int[] { 1, 3, 5, 1, 1 });

	Cajera cajera1 = new Cajera("Cajera 1");
	//Cajera cajera2 = new Cajera("Cajera 2");

	// Tiempo inicial de referencia
	long initialTime = System.currentTimeMillis();

	cajera1.procesarCompra(cliente1, initialTime);
	cajera1.procesarCompra(cliente2, initialTime);
	//cajera2.procesarCompra(cliente2, initialTime);
}
}
```

Jasoko dena ondorengoa litzateke:

```
La cajera Cajera 1 COMIENZA A PROCESAR LA COMPRA DEL CLIENTE Cliente 1 EN EL TIEMPO: 0seg
Procesado el producto 1 ->Tiempo: 2seg
Procesado el producto 2 ->Tiempo: 4seg
Procesado el producto 3 ->Tiempo: 5seg
Procesado el producto 4 ->Tiempo: 10seg
Procesado el producto 5 ->Tiempo: 12seg
Procesado el producto 6 ->Tiempo: 15seg
La cajera Cajera 1 HA TERMINADO DE PROCESAR Cliente 1 EN EL TIEMPO: 15seg
La cajera Cajera 2 COMIENZA A PROCESAR LA COMPRA DEL CLIENTE Cliente 2 EN EL TIEMPO: 15seg
Procesado el producto 1 ->Tiempo: 16seg
Procesado el producto 2 ->Tiempo: 19seg
Procesado el producto 3 ->Tiempo: 24seg
Procesado el producto 4 ->Tiempo: 25seg
Procesado el producto 5 ->Tiempo: 26seg
La cajera Cajera 2 HA TERMINADO DE PROCESAR Cliente 2 EN EL TIEMPO: 26seg
```

Ikusten denez, lehenengo 1. bezeroaren erosketa prozesatzen da, eta, gero, 2. bezeroarena. Bi erosketa horiek prozesatzeko, 26 segundo behar dira.

<img src="https://jarroba.com/wp-content/uploads/2014/05/Compra_1_cajera_1_hilo.png" alt="" data-size="original">

Eta lehenengo bezero bat eta gero beste bat prozesatu beharrean, biak batera prozesatuko bagenitu? Zenbat denbora beharko luke programak exekutatzeko?

### Bi kutxazain alboz albo dituen supermerkatuarena

Kutxazain bakarra egon beharrean (hau da, hari bakarra), bi kutxazain egongo balira (hau da, bi hari edo thread), bi bezeroak batera prozesatu ahal izango genituzke, eta denbora gutxiago behar izango genuke programa exekutatzeko. Horretarako, `Cajera.java` klasea aldatu behar dugu, eta klase hori `Thread` klasetik heredatu, haren metodo batzuk heredatzeko eta gainidazteko. Lehenik, `CajeraThread.java` klase berri hau nola kodetzen dugun ikusiko dugu, eta, ondoren, haren ezaugarriak azalduko ditugu.

```java
public class CajeraThread extends Thread {

private String nombre;

private Cliente cliente;

private long initialTime;

// Constructor, getter & setter

@Override
public void run() {

	System.out.println("La cajera " + this.nombre + " COMIENZA A PROCESAR LA COMPRA DEL CLIENTE " 
				+ this.cliente.getNombre() + " EN EL TIEMPO: " 
				+ (System.currentTimeMillis() - this.initialTime) / 1000 
				+ "seg");

	for (int i = 0; i < this.cliente.getCarroCompra().length; i++) { 
		this.esperarXsegundos(cliente.getCarroCompra()[i]); 
		System.out.println("Procesado el producto " + (i + 1) 
		+ " del cliente " + this.cliente.getNombre() + "->Tiempo: " 
		+ (System.currentTimeMillis() - this.initialTime) / 1000 
		+ "seg");
	}

	System.out.println("La cajera " + this.nombre + " HA TERMINADO DE PROCESAR " 
					+ this.cliente.getNombre() + " EN EL TIEMPO: " 
					+ (System.currentTimeMillis() - this.initialTime) / 1000 
					+ "seg");
}

private void esperarXsegundos(int segundos) {
	try {
		Thread.sleep(segundos * 1000);
	} catch (InterruptedException ex) {
		Thread.currentThread().interrupt();
	}
}

}
```

`CajeraThread` klaseak `Thread` klasetik heredatu behar du nahitanahiez `extends Thread` luzapenaren bidez. Garrantzitsua da baita gainidaztea jasotako `run()` metodoa: erabili beti `@Override` etiketa hartarako! Ezinbestekoa da horrela egitea (`Runnable` klasean dagoen metodo bat baita, eta `Thread` klaseak Interface hori inplementatzen du): hari batean exekutatu beharreko funtzionaltasuna kodetuko baita bertan; hots, hariak egin beharrekoa idatziko zaio. Hau da, `run()` metodoan programatzen dena hari batean modu sekuentzialean exekutatuko da. `CajeraThread` klase honetan, metodo gehiago erabil daitezke hariaren edo thread-aren gaineko ekintzak egiteko (adibidez, thread-a gelditzea, itxaronaraztea, etab.). Jarraian, Main metodoa nola programatzen dugun ikusiko dugu, bezeroak modu paraleloan prozesatzeko eta guztia prozesatzeko denbora gutxiago behar den frogatzeko. Main metodoa `MainThread.java` klasean dago, eta honako eduki hau du:

```java
public class MainThread {

public static void main(String[] args) {

	Cliente cliente1 = new Cliente("Cliente 1", new int[] { 2, 2, 1, 5, 2, 3 });
	Cliente cliente2 = new Cliente("Cliente 2", new int[] { 1, 3, 5, 1, 1 });

	// Tiempo inicial de referencia
	long initialTime = System.currentTimeMillis();
	CajeraThread cajera1 = new CajeraThread("Cajera 1", cliente1, initialTime);
	CajeraThread cajera2 = new CajeraThread("Cajera 2", cliente2, initialTime);

	cajera1.start();
	cajera2.start();
}
} 
```

Orain, ikusiko dugu zein izango litzatekeen exekuzio horren emaitza, eta egiaztatuko dugu programa modu paraleloan exekutatzen dela eta 15 segundo baino ez dituela behar exekuzioa amaitzeko:

```
La cajera Cajera 1 COMIENZA A PROCESAR LA COMPRA DEL CLIENTE Cliente 1 EN EL TIEMPO: 0seg
La cajera Cajera 2 COMIENZA A PROCESAR LA COMPRA DEL CLIENTE Cliente 2 EN EL TIEMPO: 0seg
Procesado el producto 1 del cliente Cliente 2->Tiempo: 1seg
Procesado el producto 1 del cliente Cliente 1->Tiempo: 2seg
Procesado el producto 2 del cliente Cliente 2->Tiempo: 4seg
Procesado el producto 2 del cliente Cliente 1->Tiempo: 4seg
Procesado el producto 3 del cliente Cliente 1->Tiempo: 5seg
Procesado el producto 3 del cliente Cliente 2->Tiempo: 9seg
Procesado el producto 4 del cliente Cliente 2->Tiempo: 10seg
Procesado el producto 4 del cliente Cliente 1->Tiempo: 10seg
Procesado el producto 5 del cliente Cliente 2->Tiempo: 11seg
La cajera Cajera 2 HA TERMINADO DE PROCESAR Cliente 2 EN EL TIEMPO: 11seg
Procesado el producto 5 del cliente Cliente 1->Tiempo: 12seg
Procesado el producto 6 del cliente Cliente 1->Tiempo: 15seg
La cajera Cajera 1 HA TERMINADO DE PROCESAR Cliente 1 EN EL TIEMPO: 15seg
```

Adibide honetan ikusten dugunez, bi kutxazainek bezeroen erosketa modu paraleloan prozesatuko balute bezala gertatzen da, eta aplikazioaren emaitzak ez du aldaketarik izango azken emaitzan, hau da, bezeroen erosketa guztiak modu independentean prozesatzean. Grafikoki ikusten da programak honako hau egin duela bi hari desberdinetan:

<img src="https://jarroba.com/wp-content/uploads/2014/05/Compra_2_hilos.png" alt="" data-size="original">

Gauza bera egiteko beste modu bat, baina `Thread` klasetik heredatu gabe, `Runnable` interfazea inplementatzea da. Kasu honetan, `Thread` klaseko metodoak ez ditugu erabiliko eta ezingo ditugu gehiegi idatzi, ez baitugu `run()` metodoa baino gehiago idatzi beharko. Probatu nahi? To, emaitzak berdina behar luke!

### Ondorioak

Multiataza (edo [_multiharitzea_](hari-anitzeko-programazioa/)) ulertzeko nahiko erraza da. Azken emaitza aldatu gabe hainbat gauza aldi berean egitean du gakoa. Sarreran esanda bezala, dena ezin da paralelizatu, eta askotan zaila izaten da aplikazio baten barruan prozesuak paralelizatzeko modua aurkitzea, aplikazio horrek aplikazio horren emaitzan eraginik izan gabe; beraz, kontzeptua ulerterraza izan arren, kasu praktiko batean aplikatzea zaila izan daiteke, aplikazioaren emaitzak eraginik izan ez dezan.

Bestalde, konkurrentziaren, multiatazaren eta gainerakoen gai horiek ikusten hasten zaretenontzat, ez kezkatu hasieran horrelako arazoak programatzea kostatzen baldin bazaizue. Izan ere, multiatazaz gain, herentzia eta interfazeak ere nahasten dira, hasieran asimilatzeko zailak direnak. Beraz, pixkanaka joatea baina oso argi izatea multiataza oso erabilgarria dela eta aplikazio eraginkorragoak eta errendimendu hobea ematen dutenak egiteko aplikatu behar dela.

</details>

{% hint style="warning" %}
`Cajera` _klaseko bi objektu jarri ditugun arren (1. kutxa eta 2. kutxa), horrek ez du esan nahi bi kutxazain independente ditugunik. Izan ere, hari beraren barruan, lehenik eta behin,_`cajera1`_en metodoak exekutatzen dira, eta, ondoren,_ `cajera2`_ren metodoak. Beraz, prozesamendu mailan, kutxazain bakarra izango bagenu bezala da (iruzkindutako kodea). Kutxazain bakarra jarri daiteke, beraz, sinplifikatze aldera; baina, ez legoke alderik bi erabilita ere!_
{% endhint %}

{% tabs %}
{% tab title="Main.java" %}
```java
package unieibar;
public class Main {

	public static void main(String[] args) {

		Cliente cliente1 = new Cliente("Cliente 1", new int[] { 2, 2, 1, 5, 2, 3 });
		Cliente cliente2 = new Cliente("Cliente 2", new int[] { 1, 3, 5, 1, 1 });

		Cajera cajera1 = new Cajera("Cajera 1");
		//Cajera cajera2 = new Cajera("Cajera 2");

		// Tiempo inicial de referencia
		long initialTime = System.currentTimeMillis();

		cajera1.procesarCompra(cliente1, initialTime);
		cajera1.procesarCompra(cliente2, initialTime);
		//cajera2.procesarCompra(cliente2, initialTime);
	}
}
```
{% endtab %}

{% tab title="Cliente.java" %}
```java
package unieibar;

public class Cliente {

	private String nombre;
	private int[] carroCompra;

	public Cliente() {
	}

	public Cliente(String nombre, int[] carroCompra) {
		this.nombre = nombre;
		this.carroCompra = carroCompra;
	}

	public String getNombre() {
		return nombre;
	}

	public void setNombre(String nombre) {
		this.nombre = nombre;
	}

	public int[] getCarroCompra() {
		return carroCompra;
	}

	public void setCarroCompra(int[] carroCompra) {
		this.carroCompra = carroCompra;
	}

}

```
{% endtab %}

{% tab title="Cajera.java" %}
```java
package unieibar;
public class Cajera {

	private String nombre;

	public Cajera() {
	}

	public Cajera(String nombre) {
		this.nombre = nombre;
	}

	public String getNombre() {
		return nombre;
	}

	public void setNombre(String nombre) {
		this.nombre = nombre;
	}

	public void procesarCompra(Cliente cliente, long timeStamp) {

		System.out.println("La cajera " + this.nombre + 
				" COMIENZA A PROCESAR LA COMPRA DEL CLIENTE " + cliente.getNombre() + 
				" EN EL TIEMPO: " + (System.currentTimeMillis() - timeStamp) / 1000	+
				"seg");

		for (int i = 0; i < cliente.getCarroCompra().length; i++) {
			this.esperarXsegundos(cliente.getCarroCompra()[i]);
			System.out.println("Procesado el producto " + (i + 1) + 
					" ->Tiempo: " + (System.currentTimeMillis() - timeStamp) / 1000 + 
					"seg");
		}

		System.out.println("La cajera " + this.nombre + " HA TERMINADO DE PROCESAR " + 
							cliente.getNombre() + " EN EL TIEMPO: " + 
							(System.currentTimeMillis() - timeStamp) / 1000 + "seg");

	}

	private void esperarXsegundos(int segundos) {
		try {
			Thread.sleep(segundos * 1000);
		} catch (InterruptedException ex) {
			Thread.currentThread().interrupt();
		}
	}

}package unieibar;
```
{% endtab %}

{% tab title="ClienteThread.java" %}
<pre class="language-java"><code class="lang-java">package unieibar;
public class CajeraThread extends Thread {
<strong>
</strong><strong>private String nombre;
</strong>
private Cliente cliente;

private long initialTime;


public CajeraThread() {
}

public CajeraThread(String nombre, Cliente cliente, long initialTime) {
	this.nombre = nombre;
	this.cliente = cliente;
	this.initialTime = initialTime;
}

public String getNombre() {
	return nombre;
}

public void setNombre(String nombre) {
	this.nombre = nombre;
}

public long getInitialTime() {
	return initialTime;
}

public void setInitialTime(long initialTime) {
	this.initialTime = initialTime;
}

public Cliente getCliente() {
	return cliente;
}

public void setCliente(Cliente cliente) {
	this.cliente = cliente;
}

@Override
public void run() {

	System.out.println("La cajera " + this.nombre + " COMIENZA A PROCESAR LA COMPRA DEL CLIENTE " 
				+ this.cliente.getNombre() + " EN EL TIEMPO: " 
				+ (System.currentTimeMillis() - this.initialTime) / 1000 
				+ "seg");

	for (int i = 0; i &#x3C; this.cliente.getCarroCompra().length; i++) {
		// Se procesa el pedido en X segundos
		this.esperarXsegundos(cliente.getCarroCompra()[i]);
		System.out.println("Procesado el producto " + (i + 1) 
					+ " del cliente " + this.cliente.getNombre() + "->Tiempo: " 
					+ (System.currentTimeMillis() - this.initialTime) / 1000 
					+ "seg");
	}

	System.out.println("La cajera " + this.nombre + " HA TERMINADO DE PROCESAR " 
					+ this.cliente.getNombre() + " EN EL TIEMPO: " 
					+ (System.currentTimeMillis() - this.initialTime) / 1000 
					+ "seg");
}

private void esperarXsegundos(int segundos) {
	try {
		Thread.sleep(segundos * 1000);
	} catch (InterruptedException ex) {
		Thread.currentThread().interrupt();
	}
}
</code></pre>

}
{% endtab %}

{% tab title="MainThread.java" %}
<pre class="language-java"><code class="lang-java">package unieibar;
public class MainThread {
	public static void main(String[] args) {
<strong>		Cliente cliente1 = new Cliente("Cliente 1", new int[] { 2, 2, 1, 5, 2, 3 });
</strong>		Cliente cliente2 = new Cliente("Cliente 2", new int[] { 1, 3, 5, 1, 1 });

		// Tiempo inicial de referencia
		long initialTime = System.currentTimeMillis();
		CajeraThread cajera1 = new CajeraThread("Cajera 1", cliente1, initialTime);
		CajeraThread cajera2 = new CajeraThread("Cajera 2", cliente2, initialTime);

		cajera1.start();
		cajera2.start();
<strong>	}
</strong>}
</code></pre>
{% endtab %}
{% endtabs %}
