
# socket file sender

Uma aplicação leve e eficiente em Java puro (Core Java) para transferência de arquivos via rede local (LAN), utilizando a arquitetura Cliente-Servidor com Sockets.

O projeto é ideal para enviar rapidamente documentos do dia a dia (como NF-e) ou arquivos grandes entre máquinas na mesma rede. É perfeito para transferências entre computadores com diferentes versões do sistema operacional, como Windows 7 e Windows 11, sem depender de pendrives.

## 🚀 Funcionalidades

-   **Transferência rápida e contínua:** utiliza leitura e escrita através de um buffer de 64 KB.
    
-   **Interface de progresso:** o servidor exibe uma barra de progresso no terminal em tempo real, informando a porcentagem, a quantidade transferida e a velocidade estimada em MB/s.
    
-   **Flexibilidade no envio:** o cliente permite digitar o caminho do arquivo no terminal ou recebê-lo automaticamente por argumentos, facilitando o uso de _drag-and-drop_ no executável.
    
-   **Gestão de diretórios:** o servidor cria automaticamente uma pasta `recebidos` para salvar os arquivos e alerta caso um arquivo com o mesmo nome já exista, evitando perdas não intencionais.
    

## 🛠️ Tecnologias Utilizadas

-   **Java (Core Java)**
    
-   **Sockets:**  `java.net`
    
-   **Streams de entrada e saída:**  `java.io`
    

## ⚙️ Pré-requisitos e Configuração

Certifique-se de ter o [Java JDK](https://www.oracle.com/java/technologies/downloads/) instalado em ambas as máquinas.

Antes de compilar, abra o arquivo `Client.java` e altere a variável `hostName` para o nome ou o endereço IP da máquina que receberá os arquivos:

```
// Altere para o IP local (ex.: 192.168.1.15) ou o nome exato do PC servidor
String hostName = "DESKTOP-S5UB9PS";
```

## 🖥️ Como Executar

### 1. Iniciar o Servidor (Máquina de Destino)

No computador que receberá os arquivos, compile e execute o servidor:

```
javac Server.java
java Server
```

O console indicará que o servidor está aguardando conexões na porta `5000`.

### 2. Iniciar o Cliente (Máquina de Origem)

No computador que enviará o arquivo, compile e execute o cliente:

```
javac Client.java
java Client
```

O cliente solicitará o caminho do arquivo que deverá ser enviado.

Para pular a etapa de digitar o caminho no terminal, você pode passar o arquivo diretamente como argumento na execução:

```
java Client "C:\caminho\para\seu\arquivo.pdf"
```

## 📄 Licença

Este projeto está sob a licença MIT.
