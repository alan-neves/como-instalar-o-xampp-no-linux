# Como instalar o XAMPP no Linux (Ubuntu)

## 1. O XAMPP

O XAMPP é um ambiente de desenvolvimento criado para facilitar a instalação e configuração de servidores web locais. Ele foi desenvolvido pela Apache Friends e inclui o Apache HTTP Server, MariaDB (um fork do MySQL), PHP e Perl. O objetivo principal do XAMPP é fornecer uma solução pronta para desenvolvedores testarem aplicações web localmente sem necessidade de configurações complexas.  

O nome XAMPP é um acrônimo que representa os seguintes componentes:  

- **X** – Multiplataforma (Windows, Linux e macOS)
- **A** – Apache HTTP Server
- **M** – MariaDB (antigo MySQL)
- **P** – PHP
- **P** – Perl

## 2. Instalação do XAMPP no Ubuntu

### Passo 1: Verificar a versão mais recente do XAMPP

Antes de baixar o XAMPP, verifique a versão mais recente disponível no site oficial:

🔗 [Apache Friends - Download XAMPP](https://www.apachefriends.org/pt_br/download.html)

Caso prefira baixar diretamente pelo terminal, liste as versões disponíveis executando:

```sh
wget -qO- https://sourceforge.net/projects/xampp/rss?path=/ | grep -o 'https://.*xampp-linux-x64-.*-installer.run' | head -n 1
```

Isso te mostrará o link do instalador. Depois, use o `wget` para baixá-lo:

```sh
wget <URL_DO_INSTALADOR>
```

Substitua `<URL_DO_INSTALADOR>` pelo link obtido no comando anterior.

### Passo 2: Tornar o Instalador Executável

Após baixar o arquivo, dê permissão de execução:

```sh
chmod +x xampp-linux-x64-*.run
```

### Passo 3: Executar o Instalador

Agora, inicie a instalação:

```sh
sudo ./xampp-linux-x64-*.run
```

Siga as instruções na interface gráfica do instalador.

### Passo 4: Iniciar o XAMPP

Após a instalação, para iniciar o XAMPP, use o seguinte comando:

```sh
sudo /opt/lampp/lampp start
```

Se precisar parar o servidor:

```sh
sudo /opt/lampp/lampp stop
```

## 3. Criando um Atalho para Facilitar a Execução

Criamos um script para iniciar o XAMPP mais facilmente. Para isso, execute:

```sh
sudo nano /usr/local/bin/start_xampp
```

E adicione o seguinte conteúdo:

```sh
#!/bin/bash
sudo /opt/lampp/manager-linux-x64.run
```

Agora, torne o script executável:

```sh
sudo chmod +x /usr/local/bin/start_xampp
```

Agora, sempre que quiser iniciar o XAMPP, basta rodar:

```sh
start_xampp
```

## 4. Removendo o XAMPP

Se precisar desinstalar o XAMPP, basta rodar:

```sh
sudo /opt/lampp/uninstall
```

E depois remover a pasta:

```sh
sudo rm -rf /opt/lampp
```

Se criou o atalho, remova-o com:

```sh
sudo rm /usr/local/bin/start_xampp
```

Espero que o guia o ajude na sua jornada com o linux, até breve. 

