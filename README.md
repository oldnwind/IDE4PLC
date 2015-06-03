IDE4PLC
=======

A libre Programming Software for PLC comply with IEC 61131-3.

Copyright 2012-2015 Eric Nicolás Pernia.

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Lesser General Public License as published 
by the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.

--------------------------------------------------------------
Para más información acerca de la licencia lea los archivos 
COPYING.LESSER.txt y COPYING.txt ubicados en el directorio 
IDE4PLC_LICENSE
--------------------------------------------------------------

***************************************************************************
*                                                        *
*      BIENVENIDO AL PROYECTO IDE4PLC. AGRADECEMOS SU INTERÉS.           * 
*                                                        *
***************************************************************************


NOTAS DE LA VERSIÓN (release 1.0.0).   
   
   Este software se encuentra desarrollo. La presente versión puede 
   programar la plataforma EDU-CIAA-NXP en lenguaje LADDER DIAGRAM IEC 
   61131-3. 
   
   El programa generado corre en una única tarea periódica cada 20ms 
   llamada MAIN_TASK. Esta tarea dispara una Unidad de Organización de 
   programa (POU) del tipo Programa llamada MAIN_PROGRAM.

   MAIN_PROGRAM es la única POU que permite modificar el programa, 
   contiene declaradas previamente variables de interfaz de Entradas (los 
   4 pulsadores de la EDU-CIAA-NXP TEC1 a TEC4) y Salidas (los 6 leds, 
   LED_R, LED_G, LED_B, LED_1, LED_2 y LED_3) y algunas variables internas.
   Las variables del tipo instancia de POU Bloque de Función (ver 
   documentación en el sitio web), que se agregan automáticamente al 
   agregar un bloque FB (Bloque de Función) en el programa de usuario, 
   también se eliminan al eliminar dicho bloque. 
   
¿Cómo abrir el IDE4PLC?

   Para abrirlo debe ejecutar el entorno Pharo-Smalltak:

   - Mac: abrir Pharo3.0.app
   - Linux: abrir Pharo3.0.sh
   - Windows: abrir Pharo.exe
   
Utilización de IDE4PLC

   Abra IDE4PLC, cree un programa en lenguaje LADDER DIAGRAM mediante 
   el editor de POUs (que se abre desde el icono correspondiente), 
   presione el botón "Generar código C" que traducirá a lenguaje C el 
   programa Ladder (generando varios archivos con extensión .C y .H 
   dentro de la carpeta /Firmware/out/gen/).
      
   Conecte la placa EDU-CIAA-NXP a su computadora mediante USB (puerto 
   debug) y  presione el botón "Compilar código y Descargar al 
   dispositivo" en el Editor de POUs. Este botón realiza las 
   siguientes tareas:

      1 - Genera el código C correspondiente a la aplicación de 
	      IDE4PLC en la carpeta /Firmware/out/gen/.
   
      2 - Invoca mediante linea de comandos al compilador del Firmware 
	      de la CIAA e iniciar el proceso de build del proyecto 
	      "plc_application". De esta manera se obtiene un ejecutable 
	      compatible con el microcontrolador de la EDU-CIAA-NXP, 
		  LPC4337, para su núcleo Cortex-M4 llamado 
		  'plc_application.bin'. 
	   
      3 - Descarga el ejecutable 'plc_application.bin' a la memoria 
	      flash de la EDU-CIAA-NXP.
   
   NOTA: El botón "Compilar código y Descargar al dispositivo" del 
   editor de POUs no está disponible en la versión para MAC OS X. 
   En consecuencia, debe compilar y descargar el código C generado 
   por IDE4PLC programa desde una consola.


Información del proyecto IDE4PLC

   Sitio web: http://ide4plc.wordpress.com
   E-mail del proyecto IDE4PLC: ide4plc@gmail.com

   Sitio web: http://www.proyecto-ciaa.com.ar/devwiki/doku.php
            ?id=desarrollo:software-plc
   Grupo de desarrollo del Soft-PLC del proyecto CIAA:
   https://groups.google.com/forum/#!forum/ciaa-software-plc
   
   
Acerca del autor
   
   Ing. Eric Nicolás Pernia.
   Quilmes, Buenos Aires, Argentina.
   ericpernia@gmail.com
   Docente-Investigador en la Universidad Nacional de Quilmes (UNQ).
   Responsable de Responsable de Software-PLC en el Proyecto CIAA.
   
Colaboradores en el port del Firmware de IDE4PLC a la EDU-CIAA-NXP

   Mariano Cerdeiro
   Pablo Ridolfi
   Juan Cecconi
   Leandro Kollenberger
