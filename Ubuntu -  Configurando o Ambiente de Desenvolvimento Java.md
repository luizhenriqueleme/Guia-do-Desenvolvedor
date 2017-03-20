# Ubuntu -  Configurando o Ambiente de Desenvolvimento Java

## Instalando o Java

<p> Para instalar o Java no Ubuntu, execute os seguintes comandos.</p>

```
sudo add-apt-repository ppa:webupd8team/java 

sudo apt-get update

sudo apt-get install oracle-java8-installer
```

## Instalando o Eclipse

Faça o download do [Eclipse](https://www.eclipse.org), pode ser a versão atual ou a que desejar. Neste exemplo, uso a versão <strong> Neon </strong>.

Após fazer o download do Eclipse Neon, pelo <strong>Terminal</strong> acesse o diretório onde ele foi baixado, geralmente é a pasta 'Downloads'.

1. Extraia o arquivo

```shell
$ tar -zxvf eclipse-jee-neon-2-linux-gtk-x86_64.tar.gz
```

2. Mova o conteúdo da pasta "eclipse" para <i>/usr/lib</i>

```shell
$ sudo mv eclipse /usr/lib
```
3. Crie o executável

```shell
$ sudo touch /usr/bin/eclipse
```
4. De permissão de execução

```shell
$ sudo chmod 755 /usr/bin/eclipse
```

5. Edite o executável

```shell
$ gksu gedit /usr/bin/eclipse
```

Na tela que abrir, cole o seguinte texto e salve o arquivo

```shell
#!/bin/sh
export ECLIPSE_HOME="/usr/lib/eclipse/eclipse"
```

Criando o lançadordo <strong>Eclipse</strong>

```shell
$ gksu gedit /usr/share/applications/eclipse.desktop 
```

Copie e cole o seguinte código na tela que se abrir, e depois salve.

```shell
[Desktop Entry]
Type=Application
Encoding=UTF-8
Name=Eclipse
Comment=Eclipse  IDE
Exec=/usr/lib/eclipse/eclipse
Icon=/usr/lib/eclipse/icon.xpm
Terminal=false
Type=Application
Categories=GNOME;Application;Development;
StartupNotify=true
```

Eclipse pronto para uso.


## Instalando o Maven

Faça o download do [Maven](https://maven.apache.org/download.cgi), aqui usarei a versão <strong>apache-maven-3.3.9</strong>.

Após fazer o download do Maven, pelo <strong>Terminal</strong> acesse o diretório onde ele foi baixado, geralmente é a pasta 'Downloads'.

1. Extraia o  arquivo

```shell
$ tar -zxvf apache-maven-3.3.9-bin.tar.gz
```

2. Mover o Maven de diretório 

Depois de extraído o maven, ele deve ser movido de diretório para um diretório mais apropriado, do que o diretório de Download. Para isso, escolha odiretório destino e mova o diretório do Maven com o comando.

```shell
$ mv apache-maven -3.3.9/ /opt/maven/
```

3. Configurar a variável de ambiente <strong>PATH</strong>.

Depois de movido de diretório, teremos que configurar a variaável de ambiente  PATH do sistema para que, ao digitar o comando Maven, o sistema saiba onde procurar o arquivo de execução.

Para isso, criar a variávei de ambiente <strong> M3_HOME </strong>.
