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

## 🛠️ Tecnologias Utilizadas

- C++ (Arduino Framework)
- ESP32
- Node-RED
- SQLite
- HiveMQ Cloud
- MQTT
- Wokwi

---

## ▶️ Como Rodar o Projeto

### Pré-requisitos

- Node.js instalado
- Node-RED instalado
- Conta no HiveMQ Cloud
- Projeto aberto no Wokwi

---

### Instalar dependências do Node-RED

Instale os seguintes módulos:

```bash
npm install node-red-dashboard
npm install node-red-node-sqlite
