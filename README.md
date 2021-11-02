# wemos_d1_mini_4_relay_esphome
Modulo a 4 Relè controllato tramite wemos d1 mini con esphome
<img width="947" alt="Quattro" src="https://user-images.githubusercontent.com/52451350/139861683-6fcd0996-449f-4c2f-950e-7e6817e1b596.png">

Il modulo espone 5 ingressi a pulsante attivi bassi:

Pulsante_Uno    (GPIO1 TX) (Deve essere HIGH durante il boot).
Pulsante_Due    (GPIO3 RX) (Volendo su questo input si può cablare un interruttore e riprogrammare di conseguenza gestendo on_press e on_release)
Pulsante_Tre    (GPIO5 D1) (Volendo su questo input si può cablare un interruttore e riprogrammare di conseguenza gestendo on_press e on_release)
Pulsante_Quatro (GPIO0 D3) (Deve essere HIGH durante il boot)
  La pressione di uno di questi pulsanti attiva o disattiva il corrispondentre relè

Pulsante_Cinque
  Il timing delgi impulsi generati azionando il pulsante determina la variazione dello stato dei relè come indicato nel seguente schema:
  Un impulso breve  => toggle relè Uno
  Due impulsi brevi => toggle relè Due
  Tre impulsi brevi => toggle relè Tre
  Quattro impulsi brevi => toggle relè Quattro
  Un impulso lungo  => Spegne tutti i relè
  Un impulso breve seguito da uno lungo  => Accende tutti i relè
  
  Durata impulsi:
  Impulso breve da 0,1 a 1 secondi
  Impulso lungo da 1 a 2 secondi
  Pause tra due impulsi da 0,1 a 0,4 secondi

