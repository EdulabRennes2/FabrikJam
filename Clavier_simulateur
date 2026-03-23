// ===================================================== //
//                                                       //
// FABRIKJAM - Arduino Micro pro -- Interface de bouton  //
// Edulab Rennes 2 - 2026                                //
//                                                       //
// ===================================================== //

// --- Chargement du panel de boutons ---
#include <Keyboard.h>
struct Bouton {
  int pin;
  char touche;
  bool etatPrecedent;
};

// ------------------------------------- //
// --- Configure ici tes boutons.    --- //
// ------------------------------------- //

Bouton boutons[] = {
  { 0,  ' ',          false },  // Espace
  { 1,  KEY_RETURN,   false },  // Entrée
  { 2,  KEY_LEFT_SHIFT, false },// Maj
  { 3,  'z',          false },  // Z
  { 4,  'q',          false },  // Q
  { 5,  's',          false },  // S
  { 6,  'd',          false },  // D
  { 7,  'v',          false },  // V
  { 8,  'b',          false },  // B
  { 9,  'n',          false },  // N
  { 10, 'g',          false },  // G
  { 14, 'h',          false },  // H
  { 15, 'j',          false },  // J
  { 16, KEY_ESC,      false },  // Echap
};

// ------------------------------------- //
// ------------------------------------- //

const int NB_BOUTONS = sizeof(boutons) / sizeof(boutons[0]);

// Délai anti-rebond en millisecondes
const unsigned long DEBOUNCE_MS = 20;
unsigned long dernierChangement[14];

// --- Configuration de l'émulateur de clavier ------------- //

void setup() {
  // Initialise chaque pin en entrée avec pull-up interne
  for (int i = 0; i < NB_BOUTONS; i++) {
    pinMode(boutons[i].pin, INPUT_PULLUP);
    boutons[i].etatPrecedent = HIGH;
    dernierChangement[i] = 0;
  }

  // Démarre l'émulation clavier
  Keyboard.begin();

  // Petite pause pour laisser l'USB s'initialiser
  delay(1000);
}


// --- Lecture des boutons du clavier en boucle ------------- //

void loop() {
  unsigned long maintenant = millis();

  for (int i = 0; i < NB_BOUTONS; i++) {
    bool etatActuel = digitalRead(boutons[i].pin);

    // Détection d'un changement d'état avec anti-rebond
    if (etatActuel != boutons[i].etatPrecedent) {
      if ((maintenant - dernierChangement[i]) > DEBOUNCE_MS) {

        if (etatActuel == LOW) {
          // Bouton pressé → envoie la touche
          Keyboard.press(boutons[i].touche);
        } else {
          // Bouton relâché → relâche la touche
          Keyboard.release(boutons[i].touche);
        }

        boutons[i].etatPrecedent = etatActuel;
        dernierChangement[i] = maintenant;
      }
    }
  }
}
