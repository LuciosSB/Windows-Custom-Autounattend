# 💿 Windows 10 Light (Automated Deployment & Debloat)

Este repositório contém as "receitas" (arquivos de resposta `autounattend.xml`) projetadas para automatizar a instalação, limpar bloatwares e otimizar a performance do Windows 10 (22H2) direto na formatação (Zero-Touch Deployment). 

O projeto foi dividido em duas variantes principais para atender tanto a infraestruturas corporativas quanto a usuários domésticos e gaymers.

---

## 📦 Variantes Disponíveis

### 1. Corporativa (TI)
**Arquivo:** `autounattend_win10_ti.xml`
Projetado para reviver máquinas antigas e focar estritamente em produtividade.
* **Perfil:** Cria a conta local de suporte (senha customizável no XML).
* **Limpeza Extrema:** Remoção total da Microsoft Store, Xbox App, OneDrive e apps nativos.
* **Otimizações:** Edge bloqueado em segundo plano, Widgets/Feeds desativados na raiz, telemetria cortada.
* **Ambiente:** Serviços de rede voltados para domínio, spooler de impressão em automático.

### 2. Pessoal e Games
**Arquivo:** `autounattend_win10_personal.xml`
Projetado para extrair o máximo de FPS e fluidez em casa, sem quebrar o ecossistema da Microsoft.
* **Perfil:** Cria a conta local padrão `USER` (sem senha) pulando a exigência de conta Microsoft.
* **Ecossistema Mantido:** Mantém a Microsoft Store e as dependências do Xbox (Game Bar funciona nativamente, sem o erro `0x80073cf3`).
* **Performance:** Plano de energia setado para *Alto Desempenho*, GameDVR otimizado.
* **Limpeza:** Remove bloatwares genéricos (Bing, Solitaire, etc.), mas mantém o essencial.

---

## ✨ Novidades da v2.0
* **Instalação Ultra-Rápida:** Correção do gargalo do `.NET Framework 3.5`. O script agora busca a dependência localmente na mídia de instalação antes de tentar baixar da internet, reduzindo o tempo de formatação de horas para minutos.
* **SvcHost Inteligente:** Divisão de processos do Windows (SvcHostSplitThreshold) agora é calculada dinamicamente com base na memória RAM real da máquina.
* **Bloqueio de Concorrência I/O:** O Windows Update é temporariamente suspenso durante a fase `specialize` para evitar que downloads simultâneos causem lentidão extrema em HDDs e SSDs mais lentos.

---

## 🚀 Como Utilizar (Recomendado: Ventoy)

Não distribuímos arquivos `.iso` modificados. Você deve aplicar estas configurações em uma ISO oficial usando o **Ventoy Auto Installation Plugin**:

1. Crie um pen drive bootável utilizando o [Ventoy](https://www.ventoy.net/).
2. Copie a ISO oficial do Windows 10 para a partição principal do pen drive.
3. Crie a estrutura de pastas `ventoy/script/` na raiz do pen drive.
4. Coloque os arquivos `.xml` deste repositório na pasta `script`.
5. Crie um arquivo `ventoy.json` na pasta `ventoy` apontando para os XMLs.
6. Dê boot pelo pen drive. Um menu azul permitirá escolher qual das duas versões você deseja instalar.

---

## 🛠️ Ferramentas Pós-Formatação (Troubleshooting)

O pacote inclui scripts auxiliares para cenários específicos após a instalação:

* **Gerenciamento do Windows Defender:** Script interativo para desativar o Defender. O script detecta automaticamente se o *Tamper Protection* (Proteção contra Violações) está ativo e orienta o usuário sobre como desativá-lo antes de aplicar as políticas de registro.
* **Diagnóstico de Rede/Drivers:** Script que lê o gerenciador de dispositivos e lista exatamente quais hardwares não foram reconhecidos. Útil para identificar drivers Wi-Fi/Ethernet faltantes (comportamento comum em instalações limpas).

> **Aviso de Segurança:** Verifique os arquivos `.xml` antes de compilar sua ISO. Altere variáveis de ambiente, nomes de contas padrão e remova comentários antes de implementar em produção corporativa. Nenhuma senha real ou dado sensível é mantido neste repositório.
