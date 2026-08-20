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

Procediamo analizzando prima il sistema senza attrito: applicando una forza $ F_1 $ al cuneo si ottiene il moto verso l'alto del cursore fino a quando la forza $ F_2 $ non riequilibra il sistema. Scriviamo le equazioni di equilibrio orizzontali e verticali che agiscono sul cuneo.

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
Vediamo il grafico di $F_2$ al variare di $\alpha$ per $F_1=1$
![grafico della funzione cotg()](/cotg.png)
Come vedi per angoli $ \alpha $ che tendono a 0 allora $ F_2 $ tende a infinito. Con un anglo di 45° viene trasmessa la stessa forza e con un angolo di 90° non viene trasmessa alcuna forza. Da questa prima analisi sembra che si possano ottenere forze in uscita molto elevate. Per esempio con un angolo di 5,7°si ottiene una forza 10 volte superiore. Il moto retrogrado è semplicemente dato dalla funzione inversa. Tuttavia considerando gli attriti il risultato cambia  di molto.






### Aggiungiamo gli attriti al moto diretto
![tutte le forze](/cuneo_completo.svg)
Le forze d'attrito hanno un ruolo fondamentale nel funzionamento del cuneo. Le superfici inclinate del cuneo e del cursore sono soggette a due forze tangenti uguali e opposte, proporzionali, tramite un coefficiente d'attrito $\mu$, alla forza di contatto normale $F_3$.

Trascuriamo ancora tutti gli altri attriti che esistono in un caso reale ma che complicherebbero inutilmente l'analisi. Procediamo quindi come prima, aggiungendo le componenti della forza d'attrito alle equazioni di equilibrio.

Le equazioni di equilibrio delle forze diventano:
Per completare l'analisi aggiungiamo tutte le forze di un sistema reale 
Questa volta ci servono anche le equazioni di equilibrio di tutto il sistema perche abbiamo due nuove forze incognite $ F_4 $ e $ F_5 $ proprio a causa dei nuovi attriti.

$$
F_1-F_4-\mu F_5= 0
$$

$$
F_2-F_5+\mu F_4 = 0
$$
mentre qui abbiamo le equazioni all'equilibrio sul cuneo
$$
F_1-F_3\sin(\alpha)-\mu F_3\cos(\alpha)-\mu F_5 =0
$$

$$
F_5-F_3\cos(\alpha)+\mu F_3\sin(\alpha)=0
$$

<details>
<summary><strong>Qui sotto trovi i passaggi matematici che portano all'equazione: </strong></summary>
procediamo con l'equilibrio del cuneo. Dalla quarta equazione:

$$
F_5-F_3\cos(\alpha)+\mu F_3\sin(\alpha)=0
$$

ricaviamo $F_5$:

$$
F_5=F_3\cos(\alpha)-\mu F_3\sin(\alpha)
$$

Raccogliendo $F_3$:

$$
\boxed{
F_5=F_3\left[\cos(\alpha)-\mu\sin(\alpha)\right]
}
$$

Sostituiamo questa espressione nella terza equazione:

$$
F_1-F_3\sin(\alpha)-\mu F_3\cos(\alpha)-\mu F_5=0
$$

ottenendo:

$$
F_1-F_3\sin(\alpha)-\mu F_3\cos(\alpha)
-\mu F_3\left[\cos(\alpha)-\mu\sin(\alpha)\right]=0
$$

Sviluppando:

$$
F_1-F_3\sin(\alpha)-\mu F_3\cos(\alpha)
-\mu F_3\cos(\alpha)+\mu^2F_3\sin(\alpha)=0
$$

Raccogliendo $F_3$:

$$
F_1-F_3\left[
(1-\mu^2)\sin(\alpha)+2\mu\cos(\alpha)
\right]=0
$$

da cui:

$$
\boxed{
F_3=
\frac{F_1}
{(1-\mu^2)\sin(\alpha)+2\mu\cos(\alpha)}
}
$$



Per il blocco superiore, dall'equilibrio orizzontale:

$$
F_3\sin(\alpha)+\mu F_3\cos(\alpha)-F_4=0
$$

quindi:

$$
\boxed{
F_4=F_3\left[\sin(\alpha)+\mu\cos(\alpha)\right]
}
$$

Dall'equilibrio verticale:

$$
F_3\cos(\alpha)-\mu F_3\sin(\alpha)-\mu F_4-F_2=0
$$

quindi:

$$
F_2=
F_3\cos(\alpha)-\mu F_3\sin(\alpha)-\mu F_4
$$

Sostituendo l'espressione di $F_4$:

$$
F_2=
F_3\cos(\alpha)-\mu F_3\sin(\alpha)
-\mu F_3\left[\sin(\alpha)+\mu\cos(\alpha)\right]
$$

Sviluppando:

$$
F_2=
F_3\cos(\alpha)-\mu F_3\sin(\alpha)
-\mu F_3\sin(\alpha)-\mu^2F_3\cos(\alpha)
$$

Raccogliendo $F_3$:

$$
F_2=
F_3\left[
(1-\mu^2)\cos(\alpha)-2\mu\sin(\alpha)
\right]
$$

Ora sostituiamo l'espressione trovata per $F_3$:

</details>

$$
\boxed{
F_2=
F_1
\frac{
(1-\mu^2)\cos(\alpha)-2\mu\sin(\alpha)
}{
(1-\mu^2)\sin(\alpha)+2\mu\cos(\alpha)
}
}
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
<details> <summary><strong>Passaggio all'angolo d'attrito fino all'equazione finale:</strong></summary>
Questa sostituzione è particolarmente utile perché permette di combinare, attraverso le formule trigonometriche, i termini contenenti $\mu$ e quelli contenenti l'angolo del cuneo $\alpha$.


Sostituendo $\mu=\tan(\varphi)$:
$$
\frac{(1-\tan^2\varphi)\cos(\alpha)-2\tan\varphi\sin(\alpha)}{(1-\tan^2\varphi)\sin(\alpha+2\tan\varphi\cos(\alpha)}
$$

Moltiplichiamo numeratore e denominatore per $\cos^2(\varphi)$:
$$
\frac{(\cos^2\varphi-\sin^2\varphi)\cos(\alpha)-2\sin\varphi\cos\varphi\sin(\alpha)}{(\cos^2\varphi-\sin^2\varphi)\sin(\alpha)+2\sin\varphi\cos\varphi\cos(\alpha)}
$$

Utilizziamo le identità:

$$
\cos^2\varphi-\sin^2\varphi=\cos(2\varphi)
$$

$$
2\sin\varphi\cos\varphi=\sin(2\varphi)
$$

ottenendo:
$$
\frac{\cos(\alpha)\cos(2\varphi)-\sin(\alpha)\sin(2\varphi)}{\sin(\alpha)\cos(2\varphi)+\cos(\alpha\sin(2\varphi)
}
$$

Riconosciamo ora le formule di addizione:

$$
\cos(a+b)=\cos(a)\cos(b)-\sin(a)\sin(b)
$$

$$
\sin(a+b)=\sin(a)\cos(b)+\cos(a)\sin(b)
$$

Pertanto:
$$
\frac{\cos(\alpha+2\varphi)}{\sin(\alpha+2\varphi)}
$$

ovvero:

$$
cot(\alpha+2\varphi)
$$

e quindi:

</details>
$$
(1)
\boxed{
F_2=F_1\cot(\alpha+2\varphi)
}
$$

Il risultato mostra quindi che l'introduzione dell'attrito modifica la funzione precedente attraverso una **traslazione angolare** di ampiezza $ 2\varphi $. In particolare, con $ \varphi >0 $, la funzione trasla a sinistra eliminando dalle soluzioni l'infinito e gli alti rapporti di trasmissione. Inoltre a destra la funzione diventa negativa che significa che il moto è possibile solo se $ F_2 $ è diretta verso l'alto.

![grafico cuneo con attrito](/cuneo_attrito.png)
Anche con bassi coefficenti d'attrito il rapporto di trasmissione crolla drasticamente  :

### Moto retrogrado con gli attriti
![tutte le forze moto retrogrado](/cuneo_completo_retrogrado.svg)
Nel caso del moto retrogrado cioè quando la forza è applicata al cursore e il cuneo si muuove verso sinistra allora la forza d'attrito si inverte e le equazioni di equilibrio diventano: 


$$
F_1-F_4+\mu F_5= 0
$$

$$
F_2-F_5-\mu F_4 = 0
$$
mentre qui abbiamo le equazioni all'equilibrio sul cuneo
$$
F_1-F_3\sin(\alpha)+\mu F_3\cos(\alpha)+\mu F_5 =0
$$

$$
F_5-F_3\cos(\alpha)-\mu F_3\sin(\alpha)=0
$$

per ottenere l'equazione finale potremmo procedere analogamente a quanto fatto nel moto diretto ma c'è una considerazione che semplifica tutto: Scegliendo l'angolo d'attrito opposto$ -\varphi $ otteniamo una forza d'attrito opposta che corrisponde proprio allo schema nel moto retrogrado. Quindi possiamo dedurre che l'equazione è:

![angolo attrito negativo](/angolo_attrito_negativo.png)

$$
\boxed{
F_2=F_1\cot(\alpha-2\varphi)
}
$$
>Negli schemi ho indicato sempre $F_1 $ con il verso a destra. Questo comporta l'esistenza di valori negativi di $ F_1 $. Il segno meno indica semplicemente che la forza deve essere applicata nel verso opposto rispetto allo schema.

### Considerazioni sulla simmetria

Come è chiaramente visibile dal grafico esiste una simmetria tra moto diretto e retrogrado. Infatti anche il meccanismo è simmetrico per $ \alpha = 45°$ e in effetti questo dimostra in parte la validità delle equazioni.
Possiamo quindi limitare lo studio all'intervallo tra 0 e 45° che è anche quello ci interessa applicare alla soluzione reale.
Sovrapponiamo i grafici delle sue funzioni considerando però che dobbiamo invertire la funzione perché la forza in ingresso è $ F_2 $

$$
(2) 
\boxed{
F_1=F_2\tg(\alpha-2\varphi)
}
$$
Grafico con le due funzioni sovrapposte
![Grafico delle funzioni](/grafico_retrogrado.png)
- In blu la funzione (1) del moto diretto con angolo d'attrito $\varphi=10°$
- In rosso la funzione (2) del moto retrogrado con angolo d'attrito $\varphi=10°$

Da notare la simmetria rispetto a 45° e gli zeri a 20° e 70°


### Attrito statico e dinamico
Come sapete ci sono due tipi di attrito radente: l'attrito statico e l'attrito dinamico. Il primo si genera quando dobbiamo mettere in movimento un corpo mentre il secondo agisce sui corpi in movimento. Entrambi hanno un effetto sul funzionamento del cuneo. Dipendono dai materiali, dalle finiture superficiali, dalla presenza o meno della lubrificazione e altro.

Ora per evitare confusione definiamo queste due nuove forze. La forza di blocco $ F_b $ e la forza di sblocco $ F_s $ che sostituiscono $F_1$ rispettivamente nella (1) e nella (2). Introduciamo anche i due angoli d'attrito statico $\varphi_s$ e dinamico $\varphi_d$  e otteniamo le seguenti equazioni:

$$
(3) F_2=F_b\cot(\alpha+2\varphi_d)
$$

$$
(4) F_s=F_2\tg(\alpha-2\varphi_s)
$$

Nel meccanismo che stiamo studiando ci aspettiamo queste quattro fasi: 
1. Posizione iniziale, il dispositivo non blocca il pezzo, il cuneo è estratto;
2. Il cuneo viene inserito con una una forza $ F_b $ il cursore sale fino ad annullare il gioco con il pezzo. La forza risultante $ F_2$ e data dall'eq.1 con un coefficiente d'attrito dinamico;
3. La rimozione della forza $ F_1 $. Il pezzo rimane bloccato anche applicando ulteriori carichi al pezzo. Questo però è possibile solo scegliendo un opportuno angolo  $ \alpha $;
4. Sblocco del pezzo. Rimuovendo il cuneo applicando una forza $ F_s $ di direzione opposta $ F_b $. Stavolta per muovere il cuneo dobbiamo vincere la forza d'attrito statico generata dal precarico $ F_2 $. Possiamo ricavare questa forza dall'eq. 2;

A seconda dei coefficienti d'attrito e dell'angolo $ \alpha $ la forza di sblocco $ F_s $ potrebbe essere maggiore di $ F_b $t. Questo potrebbe essere un problema se l'attuatore che genera le forze non riesce a generarne due diverse per il blocco e lo sblocco.
Aggiungiamo quindi il vincolo che $ F_s  < F_b $

### Conclusioni

Sostituendo $ F_2 $ nella (4) e otteniamo la forza di sblocco $ F_s $ in funzione della forza di blocco $ F_b $.

$$
(3) F_2=F_b\cot(\alpha+2\varphi_d)
$$

$$
(4) F_s=F_2\tg(\alpha-2\varphi_s)
$$

$$
(5)
\boxed{
F_s=F_b\cot(\alpha+2\varphi_d)\tg(\alpha-2\varphi_s)
}
$$

modo che Sostituendo
In questo questo grafico possiamo vedere le funzioni e i punti caratteristici del funzionamento.

![Grafico riassuntivo](/grafico_finale.png)

- La funzione (3) del moto diretto è in blu e rappresenta $F_2$ al variare di $\alpha $ per $F_b =1$ e con un angolo d'attrito dinamico di $\varphi=20°$.

- La funzione (5) è in rosso e rappresenta $F_s$ al variare di $ \alpha $ sempre con per $F_b =1$ e con un angolo d'attrito statico $\varphi=27.5° $.

- Il punto A (12°,078) rappresenta un ipotetico cuneo con $ \alpha =12° $ che spinto da una forza $F_b = 1$ genera una forza $F_2 = 0.78F_b$.

- Il punto B (12°, -0.73) rappresenta la forza necessaria per sbloccare il cuneo, con $ \alpha =12° $,che è stato bloccato con $F_b = 1 => F_s = 0.73F_b$.

- Il punto C (7.5°, -1) sulla funzione (5) è il limite sotto il quale è necessario applicare una forza, in modulo, maggiore di $ F_b $ per estrarre il cuneo di quella usata per inserirlo.

- Il punto D (7.5, 0.92) rappresenta un ipotetico cuneo al limite di sblocco con $ \alpha =7.5° $ che genera una forza $F_2 = 0.92F_b$.


Questo grafico ci aiuta a scegliere l'angolo $ \alpha $ per il nostro meccanismo. Ovviamente è bene tutelarsi dalle variazioni dei coefficienti d'attrito: Lo sporco, imprecisioni nella costruzione, variazione nella lubrificazione, temperatura, usura, ecc. possono alterare il funzionamento fino a bloccarlo. Le fasce che vedi intorno al grafico della (3) e della (5) rappresentano un intervallo di incertezza dei coefficienti di soli $ \pm 2.5°$. Quindi tieniti lontano da C.


























