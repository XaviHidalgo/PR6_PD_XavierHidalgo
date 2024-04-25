# PR6_PD_XavierHidalgo

## PRACTICA 6:  Buses de comunicación II (SPI)

### Ejercicio Practico 1 LECTURA/ESCRITURA DE MEMORIA SD

**PROGRAMA:**

``` cpp
#include <SPI.h>
#include <SD.h>
File myFile;
void setup()
{
 Serial.begin(9600);
 Serial.print("Iniciando SD ...");
 if (!SD.begin(4)) {
 Serial.println("No se pudo inicializar");
 return;
 }
Practica6.MD 2024-04-03
9 / 10
 Serial.println("inicializacion exitosa");
 myFile = SD.open("archivo.txt");//abrimos el archivo
 if (myFile) {
 Serial.println("archivo.txt:");
 while (myFile.available()) {
 Serial.write(myFile.read());
 }
 myFile.close(); //cerramos el archivo
 } else {
 Serial.println("Error al abrir el archivo");
 }
}
void loop()
{

}
```
