# **Proyecto: Alarma Despertador**
![Tinkercad](https://github.com/BrendaCandy/ProyectoSegundoParcial/blob/main/img/PracticoSegundoParcial.png)

## Integrantes 
- Brenda Candy

## Descripción
El objetivo de este proyecto es diseñar una alarma despertadora utilizando Arduino que pueda detectar la luz mediante una fotoresistencia y activar el despertador. Además, se subiran las cortinas utilizando un servomotor, el cual ira subiendo a medida que ingrese mas luz y parara en caso de que se desactive la alarma tambien se mostrara un mensaje por la pantalla LCD informando el estado de la alarma.

## Función principal
### LeerBotones()
Esta funcion se encarga de detectar el cambio de estado de la alarma. Devuelve si se encuentra activado o desactivado, permitiendo que el sistema entre en funcionamiento o no. 

~~~ C++ (lenguaje en el que esta escrito)
bool leerBotones()//LEE LOS BOTONES Y DEVUELVE SI FUE ACTIVADA O NO LA ALARMA
{
  int leerPrendido = digitalRead(BOTONPRENDIDO); //Lee el estado de los botones
  int leerApagado = digitalRead(BOTONAPAGADO);
  if(leerPrendido == 0)
  {
    prendido = 1;
  }                       //Verifico que se alla presionado algun boton
  if(leerApagado == 0)
  {
    apagado = 1;
  }
  
  if (leerPrendido == 1 && prendido == 1)//VERIFICO QUE SE HAYA PRESIONADO EL BOTON 
  {											   //Y NO SIGA PRESIONADO
    prendido = 0;
    estado = true;
  }
  if (leerApagado == 1 && apagado == 1)
  {
    apagado = 0;
    estado = false;
  }
  return estado;
}
~~~
## Componentes
### *Buzzer*
![buzzer](https://github.com/BrendaCandy/ProyectoSegundoParcial/blob/main/img/buzzer.png)

Un tipo de zumbador que emite ruido en distintas frecuencias. En este proyecto lo utilizamos como alarma una vez que empiece a amanecer.
### *Fotoresistencia*
![sensor](https://github.com/BrendaCandy/ProyectoSegundoParcial/blob/main/img/fotoresistencia.png)

Un sensor que genera voltajes segun la luz ambiente.
### *Pantalla LCD*
![display](https://github.com/BrendaCandy/ProyectoSegundoParcial/blob/main/img/lcd.png)

Una pantalla de cristal liquido con capacidad de mostrar dos lineas de 16 caracteres. Mostraremos el estado de la alarma y un breve mensaje al activarse la alarma.
### *Servomotor*
![leds](https://github.com/BrendaCandy/ProyectoSegundoParcial/blob/main/img/servomotor.png)

Un motor cuya posicion se puede controlar mediante un microcontrolador.Lo utilizamos para controlar unas cortinas de manera que al salir el sol se abran automaticamente. Y al momento de dormir y activar la alarma se cierren completamente.
### *Pulsadores*
![pulsador](https://github.com/BrendaCandy/ProyectoSegundoParcial/blob/main/img/botones.png)

Un conmutador que cierra un circuito cuando se presiona. Agregamos dos pulsadores para manejar el activamiento y desactivamiento de la alarma.

## :boom: Link al proyecto
- [Proyecto](https://www.tinkercad.com/things/kK7BGoleVby-practicosegundoparcial/editel?sharecode=Klez3afErZq4-ABn7w7rmUNJl8X16kMGyI0YXm-TdFs)

---
