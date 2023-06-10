# PRACTICA NIVEL DE AGUA de Diego Llampallas

En esta práctica dependiendo de el nivel de agua que hay se va encendiendo un foco que va de 0 a 100 ml, 100 a 200ml, 200 a 300 ml y de 300 a 400ml que al estar en 400ml esta lleno el tanque de agua.

## Programación
```
// defines pins numbers
const int trigPin = 4;
const int echoPin = 15;
const int led1 = 22;
const int led2 = 21;
const int led3 = 19;
const int led4 = 18;

// defines variables
long duration;
int distance;
int safetyDistance;


void setup() {
pinMode(trigPin, OUTPUT); // Sets the trigPin as an Output
pinMode(echoPin, INPUT); // Sets the echoPin as an Input
pinMode(led1, OUTPUT);
pinMode(led2, OUTPUT);
pinMode(led3, OUTPUT);
pinMode(led4, OUTPUT);
Serial.begin(9600); // Starts the serial communication
}


void loop() {
// Clears the trigPin
digitalWrite(trigPin, LOW);
delayMicroseconds(2);

// Sets the trigPin on HIGH state for 10 micro seconds
digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);

// Reads the echoPin, returns the sound wave travel time in microseconds
duration = pulseIn(echoPin, HIGH);

// Calculating the distance
distance= duration*0.034/2;

safetyDistance = distance;
if (safetyDistance>=0 && safetyDistance<=100)
{
  digitalWrite(led1, HIGH);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
}
else if(safetyDistance>=100 && safetyDistance<=200) 
{
  digitalWrite(led1, HIGH);
  digitalWrite(led2, HIGH);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
}
else if(safetyDistance>=200 && safetyDistance<=300) 
{
  digitalWrite(led1, HIGH);
  digitalWrite(led2, HIGH);
  digitalWrite(led3, HIGH);
  digitalWrite(led4, LOW);
}
else if(safetyDistance>=300) 
{
  digitalWrite(led1, HIGH);
  digitalWrite(led2, HIGH);
  digitalWrite(led3, HIGH);
  digitalWrite(led4, HIGH);
}
else
{
 digitalWrite(led1,  LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
}

// Prints the distance on the Serial Monitor
Serial.print("Distance: ");
Serial.println(distance);
delay (2000);
}

```
![](https://github.com/DiegoLlampallas/NIVELAGUA/blob/main/13.png?raw=true)

## Partes
![](https://github.com/DiegoLlampallas/NIVELAGUA/blob/main/14.png?raw=true)
![](https://github.com/DiegoLlampallas/NIVELAGUA/blob/main/15.png?raw=true)
![](https://github.com/DiegoLlampallas/NIVELAGUA/blob/main/16.png?raw=true)

## Conexión

![](https://github.com/DiegoLlampallas/NIVELAGUA/blob/main/17.png?raw=true)

## Funcionamiento del programa

![](https://github.com/DiegoLlampallas/NIVELAGUA/blob/main/18.png?raw=true)
![](https://github.com/DiegoLlampallas/NIVELAGUA/blob/main/19.png?raw=true)
![](https://github.com/DiegoLlampallas/NIVELAGUA/blob/main/20.png?raw=true)
![](https://github.com/DiegoLlampallas/NIVELAGUA/blob/main/21.png?raw=true)

## Evidencias

[Página](https://wokwi.com/projects/367169347147092993)


# Créditos

Desarrollado por Ing. Diego Alberto Llampallas Vega

- [GitHub](https://github.com/DiegoLlampallas)