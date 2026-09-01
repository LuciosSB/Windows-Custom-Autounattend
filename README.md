# 💿 Windows Customizados para TI (Light & Winhance)

Este repositório contém as "receitas" (arquivos de respostas automáticas `autounattend.xml`) usadas para criar versões customizadas e otimizadas do Windows 10 e Windows 11. O foco destas configurações é o alto desempenho e a remoção de bloatwares (aplicativos desnecessários) para ambientes corporativos e de Suporte de TI.

## 📦 Arquivos Disponíveis

### 1. `autounattend_win10.xml` (Windows 10 Light)
Gera uma versão extremamente leve do Windows 10, ideal para computadores corporativos mais antigos ou máquinas com hardware limitado. Processos em segundo plano reduzidos e telemetria desativada.

### 2. `autounattend_win11.xml` (Windows 11 Winhance)
Gera uma versão "Enhanced" (Aprimorada) do Windows 11, otimizada para produtividade de TI. Mantém a estética e os recursos mais modernos, mas remove as distrações e bloatwares que vêm de fábrica.

---

## 🚀 Como Utilizar (Como criar a sua ISO)

Não distribuímos arquivos `.iso` pesados aqui. Em vez disso, você deve aplicar estas configurações em uma ISO original:

1. Baixe a ISO oficial do Windows 10 ou 11 através da ferramenta Media Creation Tool da Microsoft.
2. Utilize o software [Rufus](https://rufus.ie/) para criar um pen drive bootável com a ISO original.
3. Escolha um dos arquivos deste repositório (ex: `autounattend_win10.xml`), renomeie-o exatamente para `autounattend.xml` e cole-o **na raiz** do seu pen drive recém-criado.
4. Dê boot pelo pen drive. A formatação ocorrerá de forma totalmente automatizada e o sistema já iniciará otimizado e com os usuários criados!

---

## ⚠️ AVISOS IMPORTANTES (Leia antes de formatar)

Como estas configurações removem bloatwares e pacotes genéricos desnecessários para obter o máximo de desempenho, esteja preparado para as seguintes situações:

> [!WARNING]
> **1. Ausência de Drivers de Rede (Ethernet / Wi-Fi)**
> Logo após a instalação, é provável que o computador não tenha acesso à internet, pois drivers genéricos de placa de rede podem não ter sido instalados. 
> **Solução:** Antes de formatar, baixe o driver de rede (Wi-Fi ou LAN) específico da sua placa-mãe/notebook e deixe salvo em um segundo pen drive.

> [!CAUTION]
> **2. Discos não reconhecidos na Instalação (Falta do Intel VMD / IRST)**
> Durante a formatação de notebooks modernos (especialmente Intel de 11ª a 14ª geração), o seu HD ou SSD NVMe pode não aparecer. Isso ocorre porque o driver Intel Rapid Storage Technology (IRST / VMD) não está presente na imagem original da Microsoft.
> **Solução:** 
> * **Opção A:** Baixe o driver *Intel VMD / IRST (F6 Flpy)* no site do fabricante do seu notebook, extraia em um pen drive e clique em "Carregar Driver" na tela de instalação do Windows.
> * **Opção B:** Entre na BIOS do computador e desative a tecnologia **Intel VMD** ou mude o modo SATA de RAID para **AHCI**.

---

## 🛠️ Recomendações Pós-Instalação

Recomendamos o uso da nossa ferramenta de automação corporativa [MARTI](https://github.com/LuciosSB/MARTI) logo após a formatação com estas configurações. O MARTI cuidará de mapear as impressoras da rede, instalar os softwares essenciais silenciosamente (Chrome, WinRAR, PDF) e configurar a máquina para o padrão da empresa.
