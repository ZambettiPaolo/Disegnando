+++
date = '2026-09-01T17:42:26+02:00'
draft = true
math = true
title = 'Dal cuneo alla camma'

description = "Prendi un cuneo e avvolgilo intorno ad un asse ottieni una camma"
summary = ""

categories = ["Meccanismi"]
tags = ["attrito"]

author = "Paolo Zambetti"

[cover]
image = "camma_copertina.svg"
alt = "Descrizione"
caption = ""
relative = true
hidden = false

ShowToc = true
TocOpen = false
+++
Nel post [Il cuneo]({{< ref "posts/il_cuneo/index.md" >}}) abbiamo approfondito il funzionamento di un semplice dispositivo azionato tramite un cuneo. Ora immagina di deformare quel cuneo avvolgendolo intorno ad un perno. Ottieni una camma che aziona il cursore! Scopriamo quali sono le analogie tra i due sistemi. Usiamo questa nuova geometria per estendere quell'analisi e le sue conclusioni.

### Il profilo
Esattamente quale profilo di camma replica efficacemente il cuneo? 
Per rispondere alla domanda dobbiamo capire quale proprietà del cuneo vogliamo replicare. Nel funzionamento del cuneo rimane costante il rapporto tra la forza in ingresso e quella in uscita. Ora, invece, abbiamo una coppia in ingresso e una forza in uscita. Se vogliamo mantenere anche qui un rapporto costante tra ingresso e uscita, dobbiamo trovare una curva che ci permetta di mantenere costante il braccio della forza. Questa curva è proprio l'evolvente di un cerchio. Vediamo perché.

Ecco l'equazione parametrica dell'evolvente:
$$
x = r(\cos(\alpha)+\alpha \sin(\alpha))
$$
$$
y = r(\sin(\alpha)-\alpha \cos(\alpha))
$$
l'equazione si deduce direttamente dal disegno di costruzione:

Per definizione la lunghezza del segmento $ \overline{AP}$ è uguale alla lunghezza dell'arco $ \widehat{AB} $ quindi: 
$$ |AP| = r\alpha $$

![Costruzione evolvente](/costruzione_evolvente.svg)
Immagina di avere un rocchetto di filo di raggio r con legata all'estremità una matita. Tenendo fermo il rocchetto e teso il filo disegna con la matita una curva sul foglio. Questa è un'evolvente. Ha due proprietà che ci sono molto utili: il filo è sempre tangente al rocchetto e perpendicolare alla curva.
Quindi quando diamo corpo alla curva trasformandola in un profilo di camma questa avrà la seguente proprietà: Essendo la forza di contatto con il cursore perpendicolare al profilo allora questa forza,sarà anche tangente al cerchio di base e quindi genererà sempre una coppia $ M = rF $.
Per la stessa ragione l'evolvente viene usata anche per il profilo dei denti degli ingranaggi.
la forza di attrito tra camma e cursore sarà tangente al profilo quindi genera una coppia $M_a=r \alpha \mu F $

