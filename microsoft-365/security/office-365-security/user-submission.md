---
title: Configurações de mensagem relatadas pelo usuário
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Os administradores podem aprender a configurar uma caixa de correio para coletar emails de spam e phishing relatados pelos usuários.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f59548a1f36e067d8b649f7fe22149362d6fe9c6
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083531"
---
# <a name="user-reported-message-settings"></a>Configurações de mensagem relatadas pelo usuário

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Em Microsoft 365 com caixas de correio Exchange Online, você pode especificar uma caixa de correio para receber mensagens que os usuários relatam como mal-intencionadas ou não mal-intencionadas. Quando os usuários relatam mensagens usando as várias opções de relatório, você pode usar essa caixa de correio para interceptar mensagens (enviar somente para a caixa de correio personalizada) ou receber cópias de mensagens (enviar para a caixa de correio personalizada e a Microsoft). Esse recurso funciona com as seguintes opções de relatório de mensagens:

- [O complemento Mensagem de Relatório](enable-the-report-message-add-in.md)
- [O add-in De relatório phishing](enable-the-report-phish-add-in.md)
- [Ferramentas de relatórios de terceiros](#third-party-reporting-tools)

A entrega de mensagens relatadas pelo usuário a uma caixa de correio personalizada, em vez de diretamente à Microsoft, permite que os administradores reportem mensagens de forma seletiva e manual à Microsoft usando [o envio de Administrador.](admin-submission.md) Essas configurações eram anteriormente conhecidas como a política de envios do usuário.

  > [!NOTE]
  > Se o relatório tiver sido desabilitado [Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), habilitar mensagens relatadas pelo usuário aqui substituirá essa configuração e permitirá que os usuários reportem mensagens Outlook na Web novamente.

## <a name="custom-mailbox-prerequisites"></a>Pré-requisitos de caixa de correio personalizados

Use os seguintes artigos para configurar os pré-requisitos necessários para que as mensagens relatadas pelo usuário acessem sua caixa de correio personalizada:

- Ignore a filtragem de spam na caixa de correio personalizada criando uma regra de fluxo de emails do exchange para definir o nível de confiança de spam. Consulte [Usar o EAC para criar uma regra](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) de fluxo de emails que define o SCL de uma mensagem para definir o SCL como Ignorar a **filtragem de spam**.

- [Crie uma Cofre de anexos](set-up-safe-attachments-policies.md) que inclua a caixa de correio personalizada onde a verificação de anexos Cofre está desligada ( Cofre Seção De resposta a malware desconhecido **anexos** \> **está desligada).**

- [Crie uma política Cofre Links](set-up-safe-links-policies.md) que inclua a caixa de correio personalizada onde a verificação de links Cofre está desligada ( Selecione a ação para **URLs desconhecidas** potencialmente mal-intencionadas na seção Mensagens \> **Desligadas).**

- [Crie uma política anti-malware](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) que inclua a caixa de correio personalizada onde o ZAP (limpeza automática de hora zero) para malware está desligado **(** Seção Configurações de proteção Habilitar limpeza automática de hora zero para malware não está \>  selecionada).

- Crie uma [política anti-spam](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) que inclua a caixa de correio personalizada em que o ZAP para spam e o ZAP para phishing estão desligados **(** a seção Limpeza automática de hora zero não está \>  selecionada).

- Desabilite a regra de lixo eletrônico na caixa de correio personalizada. Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule. Depois de desabilitado, o EOP não pode mover mensagens para a pasta Lixo Eletrônico com base na ação de veredito de filtragem de spam **Mover** mensagem para a pasta Lixo Eletrônico ou o conjunto de listas seguras na caixa de correio.

Depois de verificar se sua caixa de correio atende a todos os pré-requisitos aplicáveis, você pode usar os procedimentos neste artigo para configurar a caixa de correio de envios do usuário.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com/>. Para ir diretamente para a página **Envios,** use <https://security.microsoft.com/reportsubmission> .

- Para modificar a configuração para envios do usuário, você precisa ser membro de um dos seguintes grupos de função:

  - **Gerenciamento da** organização **ou Administrador de** Segurança nas Permissões no portal Microsoft 365 Defender [.](permissions-microsoft-365-security-center.md)
  - **Gerenciamento de organização** em [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

- Você precisa acessar o Exchange Online PowerShell. Se a conta que você está tentando usar não tiver acesso ao Exchange Online PowerShell, você receberá um erro com esta aparência ao especificar a caixa de correio de envios:

  > Especificar um endereço de email em seu domínio

  Para obter mais informações sobre a habilitação ou desabilitação do acesso ao Exchange Online PowerShell, consulte os seguintes tópicos:

  - [Habilitar ou desabilitar o acesso Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Regras de Acesso para Cliente no Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a>Usar o portal Microsoft 365 Defender para configurar a caixa de correio de envios do usuário

1. No portal Microsoft 365 Defender, vá para **Políticas** & políticas de ameaça Outras seção Configurações de mensagem relatadas pelo usuário \>  \>  \>  \> **Envios de usuário**.

2. Na página **Envios do** usuário, o que você vê é determinado se a configuração do botão Mensagem de Relatório da **Microsoft** Outlook está **Off** ou **On**:

   - **Botão Outlook Mensagem de Relatório** \> da Microsoft **On** ![ Alternar em : selecione essa opção se você usar o add-in Mensagem de Relatório, o complemento De relatório phishing ou o relatório integrado no Outlook na Web e, em seguida, configurar as seguintes ](../../media/scc-toggle-on.png) configurações:
     - **Envie as mensagens relatadas para**: Selecione uma das seguintes opções:
       - **Microsoft**: A caixa de correio de envios do usuário não é usada (todas as mensagens relatadas vão para a Microsoft).
       - **Caixa** de correio da Microsoft e da minha organização: na caixa exibida, insira o endereço de email de uma caixa de correio Exchange Online existente. Grupos de distribuição não são permitidos. Os envios do usuário irão para a Microsoft para análise e para a caixa de correio personalizada para sua equipe de operações de segurança ou administrador analisar.
       - **Caixa de correio da minha organização:** na caixa exibida, insira o endereço de email de uma caixa de correio Exchange Online existente. Grupos de distribuição não são permitidos. Use essa opção se quiser que a mensagem vá apenas para um administrador ou a equipe de operações de segurança para análise primeiro. As mensagens não serão enviadas para a Microsoft, a menos que o administrador as encaminhe por conta própria.

          > [!IMPORTANT]
          >
          > As organizações governamentais dos EUA (GCC, GCC Alta e DoD) só podem configurar a caixa de correio **da minha organização.** As outras duas opções estão desabilitadas.
          >
          > Se as organizações estão configuradas para enviar somente para a caixa de correio personalizada, as mensagens relatadas não serão enviadas para análise novamente e os resultados no portal de mensagens relatadas pelo usuário sempre estarão vazios.

       Independentemente do valor selecionado para **Enviar as mensagens relatadas para**, as seguintes configurações estão disponíveis:

       - **Permitir que os usuários escolham se querem relatar suas mensagens à Microsoft**
       - **Selecione opções de relatório que estão disponíveis para os** usuários seção: Selecione pelo menos uma entre as seguintes opções:
         - **Pergunte-me antes de enviar a mensagem**
         - **Sempre relatar a mensagem**
         - **Nunca relatar a mensagem**

          > [!CAUTION]
          > Se você desabilitou o relatório de lixo eletrônico no [Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) usando políticas de caixa de correio do Outlook na Web, mas configurou qualquer uma das configurações anteriores para relatar mensagens à Microsoft, os usuários poderão relatar mensagens à Microsoft no Outlook na Web usando o complemento Mensagem de Relatório ou o complemento Relatar Phishing.

     - **Seção Experiência de relatório do usuário**
       - **Antes de relatar**  a  guia: nas caixas de corpo Título e Mensagem, insira o texto descritivo que os usuários veem antes de relatar uma mensagem usando o complemento Mensagem de Relatório ou o complemento Relatar Phishing. Você pode usar a variável %type% para incluir o tipo de envio (lixo eletrônico, não lixo eletrônico, phishing etc.).
       - **Após o** relatório  guia:  nas caixas de mensagem Título e Confirmação, insira o texto descritivo que os usuários veem depois de relatar uma mensagem usando o complemento Mensagem de Relatório ou o complemento Relatar Phishing. Você pode usar a variável %type% para incluir o tipo de envio.

       Conforme mostrado na página, se você selecionar uma opção que envie as mensagens relatadas para a Microsoft, o texto a seguir também será adicionado à notificação:

          > Seu email será enviado como está para a Microsoft para análise. Alguns emails podem conter informações pessoais ou confidenciais.

   - **Botão Outlook Mensagem de Relatório** \> da Microsoft **Off** ![ Alternar fora : selecione essa opção se você usar ferramentas de relatório de terceiros em vez do add-in Mensagem de Relatório, o add-in De relatório phishing ou o relatório integrado no Outlook na Web e, em seguida, configurar as seguintes ](../../media/scc-toggle-off.png) configurações:
     - Selecione **Usar essa caixa de correio personalizada para receber envios relatados pelo usuário.** Na caixa exibida, insira o endereço de email de uma caixa de correio Exchange Online existente que possa receber emails.

   Quando terminar, clique em **Confirmar**. Para limpar esses valores, clique em **Restaurar**

## <a name="third-party-reporting-tools"></a>Ferramentas de relatórios de terceiros

Você pode configurar ferramentas de relatório de mensagens de terceiros para enviar mensagens relatadas para a caixa de correio personalizada. Você faria isso definindo a configuração do botão Mensagem de  Relatório do **Microsoft Outlook** como **Desligado** e definindo a caixa de correio minha organização como uma caixa de correio Office 365 de sua escolha.

O único requisito é que a mensagem original seja incluída como . EML ou . Anexo MSG (não compactado) na mensagem que é enviada para a caixa de correio personalizada (não apenas encaminhe a mensagem original para a caixa de correio personalizada).

Os requisitos de formatação de mensagens são descritos na próxima seção. A formatação é opcional, mas se ela não seguir o formato prescrito, os relatórios sempre serão enviados como phishing.

## <a name="message-submission-format"></a>Formato de envio de mensagem

Para identificar corretamente as mensagens anexadas originais, as mensagens enviadas para a caixa de correio personalizada exigem formatação específica. Se as mensagens não usarem esse formato, as mensagens anexadas originais sempre serão identificadas como envios de phishing.

Para a identificação correta das mensagens anexadas originais, as mensagens enviadas para a caixa de correio personalizada precisam usar a sintaxe a seguir para o Assunto (Título do Envelope):

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

em que SafetyAPIAction é um dos seguintes valores inteiros:

- 1: Lixo eletrônico
- 2: Não lixo eletrônico
- 3: Phishing

Este exemplo usa os seguintes valores:

- A mensagem está sendo relatada como phishing.
- A ID da Mensagem de Rede é 49871234-6dc6-43e8-abcd-08d797f20abe.
- O IP do Remetente é 167.220.232.101.
- O endereço From é test@contoso.com.
- A linha de assunto da mensagem é "testar o envio de phishing"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

As mensagens que não seguem esse formato não serão exibidas corretamente no portal Envios.
