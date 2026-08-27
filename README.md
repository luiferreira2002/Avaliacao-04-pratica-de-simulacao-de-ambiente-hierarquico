# Avaliação 04 — Prática de Simulação de Ambiente Hierárquico

Projeto de simulação de rede desenvolvido no **Cisco Packet Tracer**, implementando o **modelo hierárquico de 3 camadas + borda** (Edge, Core, Distribuição e Acesso), amplamente utilizado em projetos de redes corporativas.

## 

## Sobre o Projeto

Este projeto foi desenvolvido como parte da disciplina **Comutação de Redes Locais**, com o objetivo de simular um ambiente de rede corporativo utilizando o modelo hierárquico de camadas da Cisco, aplicando conceitos de:

* Redundância de enlaces
* Agregação de links (EtherChannel)
* Spanning Tree Protocol (STP)
* Segmentação por função (Borda, Core, Distribuição, Acesso)



## Arquitetura da Rede

A topologia está organizada em **4 camadas hierárquicas**:



### Camada de Borda (Edge)

Ponto de entrada/saída da rede interna, responsável pela conexão com redes externas (WAN/Internet) e por funções como roteamento, NAT e políticas de borda.

* `Router0` — Cisco 2811



### Camada de Core (Núcleo)

Responsável por comutar tráfego em alta velocidade entre a borda e a distribuição, sem aplicar políticas complexas. Os switches do core estão interligados por um **link agregado**, garantindo maior banda e redundância.

* `Switch0`
* `Switch0(2)



### Camada de Distribuição

Agrega o tráfego vindo da camada de acesso e se conecta redundantemente a **ambos** os switches de core, formando um anel lógico protegido por STP contra loops.

* `Switch0(1)`
* `Switch0(3)`



### Camada de Acesso

Ponto de conexão direta dos dispositivos finais (PCs, notebooks e servidor) à rede.

* `Switch4`, `Switch5` → conectados a `Switch0(1)`
* `Switch6`, `Switch7` → conectados a `Switch0(3)`



## Inventário de Equipamentos

|Camada|Equipamento|Modelo|Quantidade|
|-|-|-|-|
|Borda|Roteador|Cisco 2811|1|
|Core|Switch|Switch-PT-Empty|2|
|Distribuição|Switch|Switch-PT-Empty|2|
|Acesso|Switch|Cisco 2950-24|4|
|Host|Desktop|PC-PT|4|
|Host|Notebook|Laptop-PT|4|
|Servidor|Servidor|Server-PT|1|

**Total: 18 dispositivos**



## Topologia

<img width="1919" height="1079" alt="Captura de tela 2026-08-27 020238" src="https://github.com/user-attachments/assets/d41881c5-95a9-4796-a134-9e01f5523a43" />



## Pings

<img width="743" height="1034" alt="Captura de tela 2026-08-27 172043" src="https://github.com/user-attachments/assets/88204cb3-8130-4b9d-9aaf-13f2529c71e5" />

<img width="746" height="1036" alt="Captura de tela 2026-08-27 172117" src="https://github.com/user-attachments/assets/3652d0aa-dc36-480d-ba65-7191c658a9ad" />
