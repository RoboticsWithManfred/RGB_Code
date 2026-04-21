//# RGB_Code
//This is a code on how to use an RGB led. Making it display many colors

#include "Arduino.h"

// RGB LED Pins
const int RED_PIN   = 13;
const int GREEN_PIN = 12;
const int BLUE_PIN  = 14;

// PWM settings
const int FREQ       = 5000;
const int RESOLUTION = 8;  // 8-bit: 0–255

void setColor(int r, int g, int b) {
  ledcWriteChannel(0, r);
  ledcWriteChannel(1, g);
  ledcWriteChannel(2, b);
}

void setup() {
  // New API: ledcAttach and ledcChangeFrequency
  ledcAttach(RED_PIN,   FREQ, RESOLUTION);
  ledcAttach(GREEN_PIN, FREQ, RESOLUTION);
  ledcAttach(BLUE_PIN,  FREQ, RESOLUTION);
}

void loop() {
  // --- Primary Colors ---
  setColor(255, 0,   0);    delay(700);  // Red
  setColor(0,   255, 0);    delay(700);  // Green
  setColor(0,   0,   255);  delay(700);  // Blue

  // --- Secondary Colors ---
  setColor(255, 255, 0);    delay(700);  // Yellow
  setColor(0,   255, 255);  delay(700);  // Cyan
  setColor(255, 0,   255);  delay(700);  // Magenta

  // --- Warm Colors ---
  setColor(255, 165, 0);    delay(700);  // Orange
  setColor(255, 69,  0);    delay(700);  // Orange Red
  setColor(255, 20,  147);  delay(700);  // Deep Pink
  setColor(255, 105, 180);  delay(700);  // Hot Pink
  setColor(220, 20,  60);   delay(700);  // Crimson
  setColor(255, 127, 80);   delay(700);  // Coral

  // --- Cool Colors ---
  setColor(75,  0,   130);  delay(700);  // Indigo
  setColor(148, 0,   211);  delay(700);  // Violet
  setColor(138, 43,  226);  delay(700);  // Blue Violet
  setColor(0,   191, 255);  delay(700);  // Deep Sky Blue
  setColor(30,  144, 255);  delay(700);  // Dodger Blue
  setColor(64,  224, 208);  delay(700);  // Turquoise

  // --- Earth / Nature Colors ---
  setColor(34,  139, 34);   delay(700);  // Forest Green
  setColor(0,   128, 128);  delay(700);  // Teal
  setColor(107, 142, 35);   delay(700);  // Olive Green
  setColor(139, 69,  19);   delay(700);  // Saddle Brown
  setColor(210, 105, 30);   delay(700);  // Chocolate
  setColor(188, 143, 143);  delay(700);  // Rosy Brown

  // --- Pastels ---
  setColor(255, 182, 193);  delay(700);  // Light Pink
  setColor(173, 216, 230);  delay(700);  // Light Blue
  setColor(144, 238, 144);  delay(700);  // Light Green
  setColor(255, 255, 153);  delay(700);  // Pale Yellow
  setColor(221, 160, 221);  delay(700);  // Plum
  setColor(176, 224, 230);  delay(700);  // Powder Blue

  // --- Whites & Neutrals ---
  setColor(255, 255, 255);  delay(700);  // White
  setColor(255, 253, 208);  delay(700);  // Warm White
  setColor(200, 220, 255);  delay(700);  // Cool White
  setColor(128, 128, 128);  delay(700);  // Gray
  setColor(64,  64,  64);   delay(700);  // Dark Gray

  // --- OFF ---
  setColor(0, 0, 0);        delay(1000); // Off
}
