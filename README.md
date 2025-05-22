# 🛰️ Projeto Ping Cliente-Servidor em Python
Este repositório contém a implementação de uma aplicação de rede cliente-servidor utilizando sockets em Python, com comunicação baseada inicialmente em UDP e, posteriormente, em TCP. O objetivo principal é simular um programa ping personalizado, que envia mensagens do tipo "ping" do cliente ao servidor e recebe "pong" como resposta, medindo o tempo de ida e volta (RTT).

## 👨‍💻 Desenvolvedores
Lucas Saft Schemes - 23102568

Fabio Marcon Siqueira - 23101751

## 📚 Conteúdo
- Implementação do cliente e servidor utilizando UDP

- Cálculo do RTT para cada ping

- Detecção de perda de pacotes (timeout de 1 segundo)

- Adaptação da solução para o protocolo TCP

- Testes realizados entre duas máquinas distintas

## 📌 Objetivo da Atividade
Desenvolver um sistema simples de cliente-servidor com sockets em Python, simulando o comportamento do comando ping, mas utilizando UDP como protocolo de transporte. Posteriormente, adaptar para TCP e executar em duas máquinas distintas.

## 💻 Execução da Aplicação TCP
- Servidor (TCP):

- Cliente (TCP):

## 🔧 Modificações para adaptar de UDP para TCP
Troca do tipo de socket:
- UDP: socket.SOCK_DGRAM -> TCP: socket.SOCK_STREAM

- Modelo de comunicação:
UDP é sem conexão (sendto / recvfrom) -> TCP exige conexão (connect / accept / send / recv)

- Controle de fluxo:
UDP não garante entrega, nem ordem. -> TCP garante entrega, ordem e confiabilidade — ideal para aplicações onde a perda de pacotes é inaceitável.

- Timeouts:
Ambos podem usar socket.settimeout(), mas o controle de falhas no TCP é gerenciado automaticamente.

## 📡 Testes entre duas máquinas
Para testar a versão TCP entre duas máquinas:

- Servidor: execute em uma máquina (use IP local ou da rede)

- Cliente: execute na outra, utilizando o IP do servidor como destino

- Verifique se ambas estão na mesma rede e não há bloqueios de firewall na porta escolhida.

## ✅ Requisitos
- Python 3.x

- Acesso a terminal/console

- Conexão de rede entre as máquinas (no caso do teste TCP)

## 🛠️ Porta Utilizada
- A porta definida para a aplicação foi: 6969
