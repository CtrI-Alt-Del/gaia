# Arquitetura do Sistema

## Introdução

O sistema é uma solução IoT (Internet das Coisas) ou de monitoramento, onde dados são coletados de estações remotas, transmitidos via protocolo MQTT, persistidos em bancos de dados e acessados por uma aplicação web. Os componentes principais incluem um broker de mensagens, receptores de dados, bancos de dados (Mongo e PostgreSQL) e um servidor principal que intermedia o acesso à web.

O fluxo geral é o seguinte:
- Dados são publicados por estações via MQTT.
- Um broker gerencia a distribuição.
- Dados são recebidos e persistidos em bancos.
- Processamento periódico trata dados brutos.
- Um servidor principal recupera e fornece dados para a interface web via HTTP.

Todos os componentes utilizam protocolos como MQTT para publicação/subscrição, TCP/IP para persistência e recuperação de dados, e HTTP para acesso web.

<img src="../media/archtecture.png"  />

## Componentes Principais

### Estação
- **Descrição**: Representa o ponto de origem dos dados por um sensor.
- **Função**: Publica dados via protocolo MQTT para o broker.
- **Tecnologia**: Não especificada no diagrama, mas integrada com MQTT.

### Broker - HiveMQ
- **Descrição**: Servidor de mensagens que atua como intermediário para a comunicação assíncrona.
- **Função**: Recebe publicações de dados via MQTT das estações e permite subscrições para distribuição. HiveMQ é um broker MQTT open-source escalável.
- **Conexões**:
  - Entrada: Publicações MQTT da Estação.
  - Saída: Subscrições MQTT para o Receptor de Dados implementado em Node.js.

### Receptor de Dados - Node.js
- **Descrição**: Aplicação Node.js responsável por receber e processar dados iniciais.
- **Função**: Inscreve-se no broker para receber dados via MQTT e persiste os dados via TCP/IP em um banco de dados Mongo.
- **Tecnologia**: Node.js, com suporte a MQTT e conexões TCP/IP.

### Mongo
- **Descrição**: Banco de dados MongoDB.
- **Função**: Armazena dados brutos recebidos do Receptor. Serve como repositório temporário ou para dados não estruturados.
- **Conexões**:
  - Entrada: Persistência via TCP/IP do Receptor de Dados.
  - Saída: Recuperação via TCP/IP para o Servidor Principal.

### PostgreSQL
- **Descrição**: Banco de dados relacional SQL.
- **Função**: Armazena dados processados e tratados, utilizados para consultas estruturadas e persistência final.
- **Conexões**:
  - Entrada/Saída: Persistência e recuperação via TCP/IP com o Servidor Principal.
- **Nota**: Dados são tratados antes de serem persistidos aqui, vindo de um processo periódico.

### Servidor Principal - Node.js (Nest)
- **Descrição**: Servidor backend principal, construído com Node.js e framework NestJS.
- **Função**: Gerencia a lógica de negócios, recupera dados de bancos (Mongo e PostgreSQL), processa requisições e expõe APIs.
- **Conexões**:
  - Com Mongo: Recupera dados via TCP/IP.
  - Com PostgreSQL: Persiste e recupera dados via TCP/IP.
  - Com Web: Fornece dados via HTTP.

### Web - Remix
- **Descrição**: Interface frontend web.
- **Função**: Permite aos usuários visualizar e buscar dados processados.
- **Tecnologia**: Remix (framework React para aplicações web server-side rendered).
- **Conexões**: Busca dados via HTTP do Servidor Principal.

## Fluxo de Dados

1. **Coleta e Publicação**:
   - A Estação coleta dados e os publica via MQTT para o Broker (HiveMQ).

2. **Distribuição via Broker**:
   - O Broker recebe os dados e notifica os assinantes, como o Receptor de Dados (Node.js), via MQTT.

3. **Recepção e Persistência Inicial**:
   - O Receptor de Dados inscreve-se no Broker, recebe os dados e os persiste via TCP/IP em Mongo (para armazenamento de dados brutos).

4. **Processamento Periódico**:
   - Um job busca dados brutos do Mongo a cada 10 minutos.
   - Os dados são tratados (processados, limpados ou agregados) antes de serem persistidos no PostgreSQL.
   - Isso garante que o PostgreSQL contenha dados refinados e prontos para uso.

5. **Recuperação e Servidor Principal**:
   - O Servidor Principal (Node.js com Nest) recupera dados brutos de Mongo via TCP/IP quando necessário.
   - Persiste e recupera dados processados de PostgreSQL via TCP/IP, atuando como camada de abstração.

6. **Acesso Web**:
   - A aplicação Web (Remix) busca dados via HTTP do Servidor Principal, permitindo visualização e interação com os dados.
