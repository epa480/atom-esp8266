# Micropython com IoT

  
## 1. Pré-Requisitos

Para a utilização dos microcontroladores com micropython, é necessário a instalação de um dos seguintes programas:
  - terminal tool (screen no Lunix/MacOS), PuTTy (no Windows);
  - rshell;
  - ampy
  - Atom editor com o plugun Pymakr; e/ou
  - Visual Studio Code com o plugin Pymakr.

Em alguns sistemas operacionais (geralmente no Linux e MacOS), são necessários a instalação de alguns pacotes/configurações para que os dispositivos ESP8266, LoPy4, FiPy, etc. possam funcionar corretamente. Solução encontrada em [Arduino](https://www.arduino.cc/en/guide/linux).

Quando o sistema operacional (Linux e MacOS) reconhece o dispositivo e a porta porém ocorre erro de Permissão da Porta Serial

Digite o seguinte comando:
```
ls -l /dev/ttyACM*
```
ou 
```
ls -l /dev/ttyUSB*
```

Ao utilizar LoPy4 e FiPy com as extension board v3, irá reconhecer como ACM*. Caso utilize a extension board v2 ou ESP8266 será reconhecido como USB*.

Será retornado uma resposta semelhante ao seguinte trecho de código abaixo.
```
crw-rw---- 1 root dialout 188, 0 5 apr 23.01 ttyACM0
```
Precisamos adicionar seu usuário ao grupo:
```
sudo usermod -a -G dialout <username> 
```
Por fim, basta fazer o logoff e acessar novamente.

Outro problema que pode ser encontrado (geralmente com o ESP8266) nos sistemas operacionais que não reconhecem o(s) dispositivo(s). Para isso, basta instalar o driver [CH340](https://sparks.gogo.co.nz/ch340.html).

## 2. Primeiros Passos com Micropython

A maneira mais fácil de interagir com o hardware Micropython é conectar um cabo USB e usar o prompt interativo (REPL). Algumas ferramentas de softwares compatíveis com USB REPL com hardware Micropython:
  - screen (Linux/MacOS);
  - PuTTY (ou similar) no Windows;
  - rshell e ferramenta de gerenciamento de arquivos (Linux/MacOS/Windows);
  - Atom com plugin PyMakr (Linux/MacOS/Windows);
  - Visual Studio Code com plugin PyMakr (Linux/MacOS/Windows).

Para verificar qual o nome da porta que o hardware Micropython estará usando, basta conectá-lo e digitar o seguinte comando.
```
ls /dev/tty*
```
Será listado um conjunto de portas, geralmente são usadas as portas ACM* e USB*. Para verificar se o dispositivo esta comunicando corretamente com o sistema operacional, basta utilizar o comando acima e substituir * pelo nome da porta. 
```
ls /dev/ttyACM0
```
ou 
```
ls /dev/ttyUSB0
```

## 3. Conectando o disposito no PC

### 3.1. Via Terminal

Apos seguir o passos anteriores e conectando o dispotivo no computador. Podemos executar o seguinte comando (utilizado no Linux).
```
rshell -p /dev/ttyUSB0 -b 115200
```
ou
```
rshell -p /dev/ttyUSB0 -b 115200 --buffer-size=30
```
Conseguimos conectar acessar o dispostivo. Para listar os arquivos que estao contidos no dispositivo, podemos utilizar seguinte comando.
```
ls -a  /pyboard/
```
Para copiar algum arquivo para o dispositivo, utilizamos o seguinte comando.
```
cp <diretorio do arquivo>/arquivo /pyboard/
```
Para deletar algum arquivo do dispositivo.
```
rm /pyboard/<diretorio do arquivo dentro do dispositivo>/arquivo_para deletar
```

Os passos acima sao utilizados quando se deseja escrever algum script e executa-lo. Podemos tambem utilizar o micropython sem a necessidade de copiar arquivos, bastando utilizar o micropython. Para isso basta digitar o seguinte comando no terminal.
```
repl
```

Agora estamos dentro do Micropython, e podemos utilizar o interpretador do python. Como primeiro exemplo, podemos executar o seguinte comando.
```
>>> 1 + 1
```
Sera retornado o valor da soma.
```
>>> 1 + 1
>>> 2
```


