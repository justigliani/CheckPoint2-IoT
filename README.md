# 🌐 Monitoramento de Sensores IoT — CP2

## 👥 Integrantes do Grupo

| Nome | RM | Sala |
|------|----|------|
| Juliana da Silva Stigliani | 561171 | 2TDSPJ |
| Erik Naoki Miyasato | 565771 | 2TDSPJ |

---

## 📝 Descrição do Projeto

Este projeto consiste em um sistema de monitoramento remoto utilizando sensores de temperatura, umidade e distância.  

Os dados são capturados por um ESP32, enviados via protocolo MQTT para um broker na nuvem (HiveMQ) e processados pelo Node-RED, onde são exibidos em um dashboard em tempo real e armazenados em um banco de dados SQLite.

---

## 🏗️ Arquitetura da Solução

- **ESP32** — microcontrolador responsável pela leitura dos sensores.
- **DHT22** — sensor de temperatura e umidade.
- **HC-SR04** — sensor ultrassônico de distância.
- **MQTT** — protocolo utilizado para comunicação IoT.
- **HiveMQ Cloud** — broker MQTT utilizado para troca de mensagens.
- **Node-RED** — plataforma utilizada para processamento dos dados e criação do dashboard.
- **SQLite** — banco de dados local para persistência dos dados.
- **Wokwi** — simulador utilizado para execução do projeto.

  ---

## 📝 Funcionamento: Sistema de Monitoramento IoT
O projeto consiste em uma solução de telemetria ponta a ponta, dividida em três camadas principais: Hardware, Comunicação e Interface.

1. Camada de Hardware (Wokwi)
No simulador Wokwi, utilizamos um microcontrolador ESP32 para gerenciar a leitura de três sensores: o DHT22, que captura temperatura e umidade, e o HC-SR04, que monitora a distância via ondas ultrassônicas. O código processa esses sinais e os prepara para a transmissão, garantindo que as leituras sejam atualizadas em intervalos regulares para evitar sobrecarga na rede.

2. Processamento e Lógica (Node-RED)
O Node-RED atua como o cérebro da nossa aplicação. Ele recebe as mensagens publicadas pelo ESP32 através de tópicos específicos via protocolo MQTT. Dentro do fluxo, implementamos funções em JavaScript que realizam o parsing (tratamento) desses dados, convertendo-os de texto para valores numéricos. Além disso, o Node-RED integra uma API de clima externa, permitindo comparar os dados internos do sensor com as condições climáticas reais de São Paulo em tempo real.

3. Visualização e Persistência (Dashboard e Banco de Dados)
A interface de usuário é apresentada através de um Dashboard interativo, composto por Gauges e gráficos que permitem uma leitura visual rápida e intuitiva dos níveis de segurança e conforto. Paralelo à visualização, o sistema executa comandos SQL para registrar cada evento em um banco de dados SQLite. Essa persistência é fundamental para auditorias e análises históricas, permitindo identificar padrões de comportamento dos sensores ao longo do tempo.

---

## 🎥 Demonstração do Projeto
Link: 

---

## ▶️ Como Rodar o Projeto

### Pré-requisitos

- Node.js instalado
- Node-RED instalado
- Conta no HiveMQ Cloud
- Projeto aberto no Wokwi

---
### 🗄️ Estrutura do Banco de Dados (SQLite)

```sql
CREATE TABLE monitoramento (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    sensor TEXT,
    valor REAL,
    data_hora DATETIME DEFAULT CURRENT_TIMESTAMP
);
```
---

### Instalar dependências do Node-RED

⚙️ Instale os seguintes módulos:

```bash
npm install node-red-dashboard
npm install node-red-node-sqlite



---

### Instalar dependências do Node-RED

Instale os seguintes módulos:

```bash
npm install node-red-dashboard
npm install node-red-node-sqlite

