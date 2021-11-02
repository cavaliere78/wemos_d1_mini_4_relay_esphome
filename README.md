# wemos_d1_mini_4_relay_esphome
Modulo a 4 Relè controllato tramite wemos d1 mini con esphome<BR>
<img width="947" alt="Quattro" src="https://user-images.githubusercontent.com/52451350/139861683-6fcd0996-449f-4c2f-950e-7e6817e1b596.png">

# Il modulo espone 5 ingressi a pulsante attivi bassi:<BR>
<BR>
Pulsante_Uno    (GPIO1 TX) (Deve essere HIGH durante il boot)<BR>
Pulsante_Due    (GPIO3 RX) (Questo input si può riprogrammare come interruttore gestendo on_press e on_release )<BR>
Pulsante_Tre    (GPIO5 D1) (Questo input si può riprogrammare come interruttore gestendo on_press e on_release )<BR>
Pulsante_Quatro (GPIO0 D3) (Deve essere HIGH durante il boot)<BR>
  La pressione di uno di questi pulsanti attiva o disattiva il corrispondentre relè<BR>
<BR>
Pulsante_Cinque
  Il timing delgi impulsi generati azionando il pulsante determina la variazione dello stato dei relè come indicato nel seguente schema:<BR>
  Un impulso breve  => toggle relè Uno<BR>
  Due impulsi brevi => toggle relè Due<BR>
  Tre impulsi brevi => toggle relè Tre<BR>
  Quattro impulsi brevi => toggle relè Quattro<BR>
  Un impulso lungo  => Spegne tutti i relè<BR>
  Un impulso breve seguito da uno lungo  => Accende tutti i relè<BR>
<BR>
  Durata impulsi:<BR>
  Impulso breve da 0,1 a 1 secondi<BR>
  Impulso lungo da 1 a 2 secondi<BR>
  Pause tra due impulsi da 0,1 a 0,4 secondi<BR>

Su ogni relè è possibile attivare un timer indipendente con durata compresa tra 1 e 100000 secondi
I timer possono essere cotrollati tramite i segunti switch:
  Timer Uno
  Timer Due
  Timer Tre
  Timer Quattro
  
  Qaundo un timer è attivo il corrispondente relè si disattiva automaticamnte trascorso il periodo di tempo indicato dal corrispondete parametro time in secondi:<BR>
  I paramtri time esposti sono: <BR>
  Time_Uno (default 600 secondi)<BR>
  Time_Due (default 600 secondi)<BR>
  Time_Tre (default 600 secondi)<BR>
  Time_Quattro (default 600 secondi)<BR>
  
  Il delay per i quattro timer può essere modificato e sopravvive al reboot del dispositivo<BR>
  
