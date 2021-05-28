---
title: Política de envios de usuários
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
ms.openlocfilehash: 719bd2b86cae1c6a951cb34408ecb9d2b8da699a
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2021
ms.locfileid: "52696581"
---
# <a name="user-submissions-policy"></a>Política de envios de usuários

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Em Microsoft 365 com caixas de correio Exchange Online, você pode especificar uma caixa de correio para receber mensagens que os usuários relatam como mal-intencionadas ou não mal-intencionadas. Quando os usuários enviam mensagens usando as várias opções de relatório, você pode usar essa caixa de correio para interceptar mensagens (enviar somente para a caixa de correio personalizada) ou receber cópias de mensagens (enviar para a caixa de correio personalizada e a Microsoft). Esse recurso funciona com as seguintes opções de relatório de mensagens:

- [O complemento Mensagem de Relatório](enable-the-report-message-add-in.md)

- [O add-in De relatório phishing](enable-the-report-phish-add-in.md)

- [Ferramentas de relatórios de terceiros](#third-party-reporting-tools)

A entrega de mensagens relatadas pelo usuário a uma caixa de correio personalizada, em vez de diretamente à Microsoft, permite que os administradores reportem mensagens de forma seletiva e manual à Microsoft usando [o envio de Administrador.](admin-submission.md)

  > [!NOTE]
  > Se o relatório tiver sido desabilitado Outlook na [Web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)habilitar envios de usuários aqui substituirá essa configuração e permitirá que os usuários reportem mensagens Outlook na Web novamente.

## <a name="custom-mailbox-prerequisites"></a>Pré-requisitos de caixa de correio personalizados

Use os seguintes artigos para configurar os pré-requisitos necessários para que as mensagens relatadas pelo usuário acessem sua caixa de correio personalizada:

- Ignore a filtragem de spam na caixa de correio personalizada criando uma regra de fluxo de emails do exchange para definir o nível de confiança de spam. Consulte [Usar o EAC para criar uma regra](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) de fluxo de emails que define o SCL de uma mensagem para definir o SCL como Ignorar a **filtragem de spam**.

- Desativar anexos de verificação de malware na caixa de correio personalizada. Use [Configurar políticas de Cofre Anexos](set-up-safe-attachments-policies.md) no Defender para Office 365 para criar uma política  de anexos Cofre com a configuração Off para Cofre **Anexos resposta** de malware desconhecida .

- Desativar a verificação de URL em mensagens na caixa de correio personalizada. Use [Configurar políticas Cofre links](set-up-safe-links-policies.md) no Defender para Office 365 para criar uma política  de links Cofre com a configuração Off para Selecionar a ação para **URLs** potencialmente mal-intencionadas desconhecidas em mensagens .

- Crie uma política anti-malware para desativar o Malware Zero-hour Auto Purge. Consulte Usar o Centro de Conformidade & segurança para criar políticas [anti-malware](configure-your-spam-filter-policies.md#use-the-security-center-to-create-anti-spam-policies) para definir a Limpeza **Automática de Hora Zero** de Malware como **Desligada.**

- Crie uma política de filtro de spam para desabilitar a limpeza automática de hora zero (ZAP) para spam e phishing na caixa de correio personalizada. Consulte Usar o Centro de Conformidade & segurança para  criar políticas [anti-spam](configure-your-spam-filter-policies.md#use-the-security-center-to-create-anti-spam-policies) e limpar as caixas de seleção On para **SPAM ZAP** e **Phish ZAP**.

- Desabilite a regra de lixo eletrônico na caixa de correio personalizada. Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule. Depois de desabilitado, o EOP não pode mover mensagens para a pasta Lixo Eletrônico com base na ação de veredito de filtragem de spam **Mover** mensagem para a pasta Lixo Eletrônico ou o conjunto de listas seguras na caixa de correio.

Depois de verificar se sua caixa de correio atende a todos os pré-requisitos aplicáveis, & use o Centro de Conformidade e Segurança para configurar a caixa de correio de [envios](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) do usuário (neste artigo).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a **página Envios de** usuário, use <https://protection.office.com/userSubmissionsReportMessage> .

- Para modificar a configuração para envios do usuário, você precisa ser membro de um dos seguintes grupos de função:

  - **Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).
  - **Gerenciamento de organização** em [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

- Você precisa acessar o Exchange Online PowerShell. Se a conta que você está tentando usar não tiver acesso ao Exchange Online PowerShell, você receberá um erro com esta aparência ao especificar a caixa de correio de envios:

  > Especificar um endereço de email em seu domínio

  Para obter mais informações sobre a habilitação ou desabilitação do acesso ao Exchange Online PowerShell, consulte os seguintes tópicos:

  - [Habilitar ou desabilitar o acesso Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Regras de Acesso para Cliente no Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Use o Centro de Conformidade & segurança para configurar a caixa de correio de envios do usuário

1. No Centro de Conformidade & segurança, acesse **Envios** de usuário da Política de Gerenciamento \>  \> **de Ameaças.**

2. Na página **Envios de** usuário exibida, selecione uma das seguintes opções:

      1. Habilitar o recurso Mensagem de Relatório para **Outlook (Recomendado)**: Selecione essa opção se você usar o complemento De Mensagem de Relatório, o add-in Relatório phishing ou o relatório integrado no Outlook na Web e, em seguida, configure as seguintes configurações:

    - **Personalizar a mensagem de confirmação do usuário final**: clique neste link. No flyout **Personalizar mensagem de** confirmação exibida, configure as seguintes configurações:

        - **Antes do envio**:  nas caixas de mensagem Título e Confirmação, insira o texto descritivo que os usuários veem antes de relatar uma mensagem usando o complemento Mensagem de Relatório ou o complemento Relatar Phishing.  Você pode usar a variável %type% para incluir o tipo de envio (lixo eletrônico, não lixo eletrônico, phishing etc.).

          Conforme registrado, se você selecionar uma opção que envia as mensagens relatadas para a Microsoft, o texto a seguir também será adicionado à notificação:

          > Seu email será enviado como está para a Microsoft para análise. Alguns emails podem conter informações pessoais ou confidenciais.

        - **Após o envio**: clique ![ em Expandir ícone ](../../media/scc-expand-icon.png) . Nas caixas **de** **mensagem** Título e Confirmação, insira o texto descritivo que os usuários veem depois de relatar uma mensagem usando o complemento Mensagem de Relatório ou o complemento Relatar Phishing. Você pode usar a variável %type% para incluir o tipo de envio.

      Quando concluir, clique em **Salvar**. Para limpar esses valores, clique em **Restaurar** novamente na **página Envios do** usuário.
    
    - **Personalizar as opções de relatório do usuário final**: clique neste link. No **sub-lançamento Personalizar opções** de relatório do usuário final exibidas, insira o texto descritivo para opções de relatório de lixo eletrônico. 
    
      Em **Opções para mostrar quando as mensagens são relatadas,** selecione pelo menos uma entre as seguintes opções:
        - **Pergunte-me antes de enviar um relatório**
        - **Enviar relatórios automaticamente**
        - **Nunca enviar relatórios**
       
      Quando concluir, clique em **Salvar**.

        - **Envie as mensagens relatadas para**: Faça uma das seguintes seleções:

        - **Microsoft (Recomendado)**: A caixa de correio de envios do usuário não é usada (todas as mensagens relatadas vão para a Microsoft).

        - **Microsoft e uma caixa de correio personalizada:** na caixa exibida, insira o endereço de email de uma caixa de correio Exchange Online existente. Grupos de distribuição não são permitidos. Os envios do usuário irão para a Microsoft para análise e para a caixa de correio personalizada para sua equipe de operações de segurança ou administrador analisar.

        - **Caixa de correio personalizada somente**: na caixa exibida, insira o endereço de email de uma caixa de correio Exchange Online existente. Grupos de distribuição não são permitidos. Use essa opção se quiser que a mensagem vá apenas para um administrador ou a equipe de operações de segurança para análise primeiro. As mensagens não serão enviadas para a Microsoft, a menos que o administrador as encaminhe por conta própria.

          > [!NOTE]
          > As organizações governamentais dos EUA (GCC, GCC-H e DoD) só podem configurar **a caixa de correio personalizada**. As outras duas opções estão desabilitadas.

          > [!NOTE]
          > Se as organizações estão configuradas para enviar somente para a caixa de correio personalizada, as mensagens relatadas não serão enviadas para análise novamente e os resultados no portal de mensagens relatadas pelo usuário sempre estarão vazios.

      Quando terminar, clique em **Confirmar**.

      > [!CAUTION]
      > Se você desabilitou o relatório de lixo eletrônico no Outlook na [Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) usando o Outlook nas políticas de caixa de correio da Web, mas configurou uma das configurações anteriores para relatar mensagens à Microsoft, os usuários poderão relatar mensagens à Microsoft no Outlook na Web usando o complemento Mensagem de Relatório ou o complemento Relatar Phishing.


    2. Desabilitar o recurso Mensagem de Relatório para **Outlook:** selecione essa opção se você usar ferramentas de relatório de terceiros em vez do complemento De mensagem de relatório, do complemento Relatar Phishing ou do relatório integrado no Outlook na Web e, em seguida, configurar as seguintes configurações:

       Selecione **Usar essa caixa de correio personalizada para receber envios relatados pelo usuário.** Na caixa exibida, insira o endereço de email de uma caixa de correio existente que já está Office 365. Deve ser uma caixa de correio existente no Exchange Online que possa receber emails.

       Quando terminar, clique em **Confirmar**.

## <a name="third-party-reporting-tools"></a>Ferramentas de relatórios de terceiros

Você pode configurar ferramentas de relatório de mensagens de terceiros para enviar mensagens relatadas para a caixa de correio personalizada. O único requisito é que a mensagem original seja incluída como um anexo na mensagem enviada à caixa de correio personalizada (não apenas encaminhe a mensagem original para a caixa de correio personalizada).

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
