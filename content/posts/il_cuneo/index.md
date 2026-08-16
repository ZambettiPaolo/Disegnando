+++
date = '2026-08-08T22:01:32+02:00'
draft = true
title = 'Il cuneo'
math = true
description = "Un semplice meccanismo applicabile in molti problemi"
summary = ""

categories = ["Mi sembra il minimo"]
tags = ["meccanismi"]

author = "Paolo Zambetti"

[cover]
image = "Cuneo1.svg"
alt = "cuneo"
caption = ""
relative = true
hidden = false



ShowToc = true
TocOpen = false
+++

### Introduzione

Probabilmente avrai già avuto a che fare con i cunei, vengono spesso usati per bloccare le porte aperte. E' un dispositivo molto diffuso semplice e multiforme che ho utilizzato frequentemente anche involontariamente. Partiamo dalla forma più comune, un sistema meccanico formato da un telaio, un  cursore e un cuneo. Lo scopo principale è usare la forza di uscita per bloccare o pinzare. Il funzionamento è abbastanza intuitivo ma per capirlo in modo approfondito e sfruttarne tutte le potenzialità sono necessarie un po di fisica e matematica. 

### Analisi del cuneo senza attrito

![cuneo senza attrito](/cuneo_senza_attrito.svg)

Procediamo analizzando prima il sistema senza attrito: applicando una forza $ F_1 $ al cuneo si ottiene il moto verso l'alto del cursore fino a quando la forza $ F_2 $ non riequilibra il sistema. A seconda dell'angolo $ \alpha $ si possono ottere in uscita una forza $ F_2 $ maggiore di $ F_1 $. Scriviamo le equazioni di equilibrio orizzontali e verticali che agiscono sul cuneo.

$$
F_1-F_3 sen(\alpha) = 0
$$
$$
F_2-F_3 cos(\alpha) = 0
$$
da cui otteniamo:
$$
\frac{F_2}{F_1} = \frac{cos(\alpha)}{sen(\alpha)}
$$
esprimendo $ F_2 $ in funzione di $ F_1 $ si ha:
$$
\boxed{F_2 = F_1cotg(\alpha)}
$$
Vediamo il grafico
![grafico della funzione cotg()](/cotg.png)
Come vedi per angoli $ \alpha $ che tendono a 0 allora $ F_2 $ tende a infinito. Con un anglo di 45° viene trasmessa la stessa forza e con un angolo di 90° non viene trasmessa alcuna forza. Da questa prima analisi sembra che si possano ottenere forze in uscita molto elevate. Per esempio con un angolo di 5,7°si ottiene una forza 10 volte superiore. Il moto retrogrado è semplicemente dato dalla funzione inversa. Tuttavia considerando gli attriti il risultato cambia  di molto.

### Analisi del cuneo con attrito e moto diretto

![cuneo con attrito](/cuneo_attrito_diretto.svg)
Le forze d'attrito hanno un ruolo fondamentale nel funzionamento del cuneo. Le superfici inclinate del cuneo e del cursore sono soggette a due forze tangenti uguali e opposte, proporzionali, tramite un coefficiente d'attrito $\mu$, alla forza di contatto normale $F_3$.

Trascuriamo ancora tutti gli altri attriti che esistono in un caso reale ma che complicherebbero inutilmente l'analisi. Procediamo quindi come prima, aggiungendo le componenti della forza d'attrito alle equazioni di equilibrio.

Le equazioni di equilibrio delle forze diventano:

$$
F_1-F_3\sin(\alpha)-\mu F_3\cos(\alpha)=0
$$

$$
F_2-F_3\cos(\alpha)+\mu F_3\sin(\alpha)=0
$$

Per semplificare i passaggi successivi introduciamo l'**angolo d'attrito** $\varphi$.

![angolo attrito](/angolo_attrito.png)

Per definizione è legato al coefficiente d'attrito $\mu$ dalla relazione:

$$
\varphi = \arctan(\mu)
$$

Da questa relazione segue immediatamente:

$$
\mu = \tan(\varphi)
$$

Questa sostituzione è particolarmente utile perché permette di combinare, attraverso le formule trigonometriche, i termini contenenti $\mu$ e quelli contenenti l'angolo del cuneo $\alpha$.

<details>
<summary><strong>Attraverso questi passaggi matematici si ottrine l'equazione finale: </strong></summary>

Dividendo $F_2$ per $F_1$ otteniamo:

$$
\frac{F_2}{F_1} = \frac{\cos(\alpha)-\mu\sin(\alpha)}
{\sin(\alpha)+\mu\cos(\alpha)}
$$

A questo punto sostituiamo $ \mu=\tan(\varphi) $ ottenendo:

$$
\frac{F_2}{F_1} = \frac{\cos(\alpha)-\tan(\varphi)\sin(\alpha)}{\sin(\alpha)+\tan(\varphi)\cos(\alpha)}
$$

Moltiplichiamo numeratore e denominatore per $\cos(\varphi)$:

$$
\frac{F_2}{F_1} =
\frac{\cos(\alpha)\cos(\varphi)-\sin(\alpha)\sin(\varphi)}
{\sin(\alpha)\cos(\varphi)+\cos(\alpha)\sin(\varphi)}
$$

Ora possiamo riconoscere le formule di addizione e sottrazione del seno e del coseno:

$$
\cos(\alpha+\varphi) =
\cos(\alpha)\cos(\varphi)-\sin(\alpha)\sin(\varphi)
$$

e

$$
\sin(\alpha+\varphi) =
\sin(\alpha)\cos(\varphi)+\cos(\alpha)\sin(\varphi)
$$

Pertanto:

$$
\frac{F_2}{F_1} =
\frac{\cos(\alpha+\varphi)}
{\sin(\alpha+\varphi)}
$$

ovvero:

$$
\frac{F_2}{F_1} =
\cotg(\alpha+\varphi)
$$

Infine, esprimendo $F_2$ in funzione di $F_1$:

</details>


$$
\boxed{F_2=F_1\cotg(\alpha+\varphi)}
$$

Il risultato mostra quindi che l'introduzione dell'attrito modifica la funzione precedente attraverso una **traslazione angolare** di ampiezza $\varphi$. In particolare, con $ \varphi >0 $, la funzione trasla a sinistra eliminando dalle soluzioni l'infinito e gli alti rapporti di trasmissione. Inoltre a destra la funzione diventa negativa che significa che il moto è possibile solo se $ F_2 $ è diretta verso l'alto.

![grafico cuneo con attrito](/cuneo_attrito.png)




### Analisi del cuneo con attrito e moto retrogrado

![cuneo con attrito](/cuneo_attrito_retrogrado.svg)
Nel caso del moto retrogrado cioè quando la forza è applicata al cursore e il cuneo esce verso sinistra allora la forza d'attrito si inverte e le equazioni di equilibrio diventano: 

$$
F_1-F_3\sin(\alpha)+\mu F_3\cos(\alpha)=0
$$

$$
F_2-F_3\cos(\alpha)-\mu F_3\sin(\alpha)=0
$$

da cui otteniamo con passaggi analoghi ai precedenti:

$$
\boxed{F_2=F_1\cotg(\alpha-\varphi)}
$$
Ora sovrapponiamo i grafici ma attenzione in questo caso il nostro input al sistema è $ F_2 $ quindi dobbiamo usare la funzione inversa

$$
\boxed{F_1=F_2\tg(\alpha-\varphi)}
$$
### Considerazioni sulla simmetria
### Rendimenti
### Attrito statico e dinamico






















