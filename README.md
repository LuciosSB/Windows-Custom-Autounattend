# 💿 Windows Customizados para TI (Light & Winhance)

Este repositório contém a documentação e os links de download para versões customizadas e otimizadas do Windows 10 e Windows 11. Estas imagens (`.iso`) foram projetadas especificamente para ambientes de Suporte de TI, focando em desempenho e remoção de bloatwares (aplicativos desnecessários).

## 📦 Versões Disponíveis

### 1. Windows 10 Light
Versão extremamente leve do Windows 10, ideal para computadores corporativos mais antigos ou máquinas com hardware limitado. Processos em segundo plano reduzidos e telemetria desativada.
* **Download ISO:** `[Insira seu link do Google Drive/OneDrive aqui]`

### 2. Windows 11 Winhance
Versão "Enhanced" (Aprimorada) do Windows 11, otimizada para produtividade de TI. Mantém a estética e os recursos mais modernos, mas remove as distrações e bloatwares que vêm de fábrica.
* **Download ISO:** `[Insira seu link do Google Drive/OneDrive aqui]`

---

## ⚠️ AVISOS IMPORTANTES (Leia antes de instalar)

Como estas ISOs foram profundamente enxugadas para obter o máximo de desempenho, alguns pacotes genéricos de drivers foram removidos. Esteja preparado para as seguintes situações durante a formatação:

> [!WARNING]
> **1. Ausência de Drivers de Rede (Ethernet / Wi-Fi)**
> Logo após a instalação, é altamente provável que o computador não tenha acesso à internet, pois os drivers básicos de placa de rede podem não estar embutidos. 
> **Solução:** Antes de formatar, baixe o driver de rede (Wi-Fi ou LAN) específico da sua placa-mãe/notebook e deixe salvo em um pen drive.

> [!CAUTION]
> **2. Discos não reconhecidos na Instalação (Falta do Intel VMD / IRST)**
> Na tela de selecionar a partição para instalar o Windows, o seu HD ou SSD (especialmente NVMe de 11ª geração Intel ou superior) pode não aparecer. Isso ocorre pela ausência do driver Intel Rapid Storage Technology (IRST / VMD).
> **Solução:** 
> * **Opção A:** Baixe o driver *Intel VMD / IRST (F6 Flpy)* no site do fabricante do seu notebook, extraia em um pen drive e clique em "Carregar Driver" na tela de instalação do Windows.
> * **Opção B:** Entre na BIOS do computador e desative a tecnologia **Intel VMD** ou mude o modo SATA de RAID para **AHCI**.

---

## 🛠️ Recomendações Pós-Instalação

Recomendamos o uso da nossa ferramenta [MARTI](https://github.com/LuciosSB/MARTI) logo após a formatação com estas ISOs. O MARTI cuidará de mapear as impressoras, instalar os softwares essenciais silenciosamente e configurar a máquina para o padrão da empresa, compensando a natureza "limpa" destas ISOs.
