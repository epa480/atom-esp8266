# Micropyhon com IoT

Podemos utilizar microcontroladores com micropython de utilizando vários programas, entre eles: 
  - terminal tool (screen no Linux/MacOS), PuTTY (no Windows); 
  - rshell; 
  - ampy;
  - Atom editor com o plugin PyMakr; e 
  - Visual Studio Code com o plugin PyMakr.
  
## 1. Pré-Requisitos

Para a utilização dos microcontroladores com micropython, é necessário a instalação de um dos seguintes programas:
  - terminal tool (screen no Lunix/MacOS), PuTTy (no Windows);
  - rshell;
  - ampy
  - Atom editor com o plugun Pymakr; e/ou
  - Visual Studio Code com o plugin Pymakr.

Em alguns sistemas operacionais (geralmente no Linux e MacOS), são necessários a instalação de alguns pacotes/configurações para que os dispositivos ESP8266, LoPy4, FiPy, etc. possam funcionar corretamente.

Quando o sistema operacional (Linux e MacOS) reconhece o dispositivo e a porta porém ocorre erro de Permissão da Porta Serial

Digite o seguinte comando:
```
ls -l /dev/ttyACM*
```
ou 

ls -l /dev/ttyUSB*

Ao utilizar LoPy4 e FiPy com as extension board v3, irá reconhecer como ACM*. Caso utilize a extension board v2 ou ESP8266 será reconhecido como USB*.

Será retornado uma resposta semelhante ao trecho de código abaixo.
crw-rw---- 1 root dialout 188, 0 5 apr 23.01 ttyACM0


Now we just need to add our user to the group:

sudo usermod -a -G dialout <username> 


## 2. Primeiros Passos com Micropython


## 3.  


