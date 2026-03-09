<h1>
Kontekst
</h1>
I vitenskaplige beregninger prosjekt 2 dukket det opp en feil som vi ikke klarte å løse. 
Klarer du å løse oppgaven vil jeg betale 50 NOK ganger antall personer i repositoriet opptil 500. 
<h4>
Forklaring på feilen
</h4>
Mest sannsynlig ligger feilen kjorSimuleringOppg3:

```python

pPlus_all = current_probs[0, positions]

#Feilen ligger i denne linjen
pStay_all = current_probs[1, positions]
```
Ser vi hvilke verdier current_probs[1, positions] har har den 1 to steder
Dette er i nullpunktene til potensialet, resten er 1. Dette skal stemme i rachet potensial

MEN! I pStay_all er alle verdiene satt til 1 istedet. Dette gjør at vi ikke får noen strømninger.
<h4>
Teori
</h4>
Min nåværende teori er at pStay_all er en vektor full av 1 og så trekker vi fra 0 hele tiden. 
Eller at pStay lagrer data fra tidligere iterasjoner og plusser sammen nye verdier. 

