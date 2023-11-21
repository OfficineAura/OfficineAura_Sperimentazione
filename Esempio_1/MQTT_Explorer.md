# Guida all'Utilizzo del Biofiltro con MQTT Explorer
<p align="center">
  <img src="https://github.com/OfficineAura/OfficineAuraEsempi/blob/main/Esempio_1/Gruppo-FOS_Officine-AURA_startup_logo_03.11.png" alt="Logo del Progetto" width="150" height="150" border-radius:"50%;"">
</p>

Questa guida fornisce istruzioni passo-passo per:
1. Installare un client MQTT e connettersi a un broker MQTT ([AWS MQTT](https://aws.amazon.com/it/what-is/mqtt/)).
2. Visualizzare i valori rilevati da un sensore presente nel biofiltro.
3. Analizzare un gas rilevato da un sensore nel biofiltro.
4. Generare e visualizzare un grafico relativo a quel gas in un dato intervallo temporale.

## Prerequisiti

- [MQTT Explorer](http://mqtt-explorer.com/)
- [Test.mosquitto.org](https://test.mosquitto.org/)
- Serial number del dispositivo

## 1. Installazione del Client e Connessione al Broker

- Installare MQTT Explorer da [questo link](http://mqtt-explorer.com/).
- Avviare l'applicazione e aggiungere una connessione.
- Inserire il nome e l'indirizzo IP del broker MQTT, ad esempio, test.mosquitto.org [Scopri di più...](https://test.mosquitto.org/).
- Inserire la porta del broker MQTT (in questo caso è la 1883).
- Lasciare vuoti i campi Username e Password.
- Connettersi al broker.

## 2. Visualizzazione dei Valori di un Sensore

- Conoscere il serial number del dispositivo.
- Nella barra di ricerca, inserire il seguente topic: `device name_serial number` (ad esempio: `BSAV00_SerialNumber` del tuo dispositivo).
- Attendere la pubblicazione dei valori del sensore SEN5x.
- Espandere il sotto-topic `SEN5`.
- Troverai i valori di tutti i gas inviati via MQTT da questo sensore. Cliccare su uno qualsiasi.

## 3. Analisi di un Gas e Generazione del Grafico

- A destra, troverai un formato contenente diverse chiavi-valori.
- La struttura è la seguente: {
"key1": value1,
"key2": value2,
// ...
}
-  Le chiavi che ci intressano sono: "p" che indica il nome del gas, "v" che indica il suo valore e "u" che indica l'unità di misura.
-  Cliccare sull'icona posta a destra del valore "v" per visualizzare quel specifico valore su un grafico in un intervallo temporale specifico.

## 4. Visualizzazione del grafico

-  Una volta aperto il grafico sulla sinistra potrai gestirne le diverse funzionalità cliccando sull'icona settings.
-  Puoi cambiare il colore.
-  Puoi cambiare l'arco temporale per visualizzare i vari valori in quello specifico lasso temporale, etc..
-  Il grafico si aggiorna in tempo reale, per cui ogni volta il sensore invia i dati via MQTT il grafico si aggiornerà con i nuovi dati. 

## 5. Note Aggiuntive

Seguendo questi passaggi, dovresti essere in grado di connetterti ai dati inviati dal tuo biofiltro via MQTT, visualizzare i dati dei sensori e analizzare i gas rilevati tramite visualizzazione grafica.

## 6. Conclusione 

Ecco come dovrebbe appararire la tua schermata alla fine di questa lezione: 

![Esempio Finale](https://github.com/OfficineAura/OfficineAuraEsempi/blob/main/Esempio_1/Mqtt_exampler_example.png)