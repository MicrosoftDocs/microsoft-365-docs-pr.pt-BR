---
title: Especificar uma caixa de correio para envios de spam e mensagens de phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a configurar uma caixa de correio para coletar spam e emails de phishing relatados pelos usuários.
ms.openlocfilehash: 2a1872aff88cd1cc21c6a6e3258671c303b55e17
ms.sourcegitcommit: 4ce28ad4d17d336106c1720d65349f19f9e90e04
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44294188"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>Especificar uma caixa de correio para envios de spam e mensagens de phishing no Exchange Online

Nas organizações do Microsoft 365 com caixas de correio do Exchange Online, você pode especificar uma caixa de correio para receber mensagens que os usuários relatam como mal-intencionadas ou não mal intencionadas. Quando os usuários enviam mensagens usando as várias opções de relatórios, você pode usar essa caixa de correio para interceptar mensagens (enviar somente para a caixa de correio personalizada) ou receber cópias de mensagens (enviar para a caixa de correio personalizada e Microsoft). Este recurso funciona com as seguintes opções de relatório de mensagens:

- [O suplemento de mensagem de relatório](enable-the-report-message-add-in.md)

- [Relatórios internos no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (anteriormente conhecido como Outlook Web App)

  > [!NOTE]
  > Se o relatório tiver sido [desabilitado no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), habilitar os envios de usuários aqui substituirá essa configuração e permitirá que os usuários reportem mensagens no Outlook na Web novamente.

Você também pode configurar ferramentas de relatório de mensagens de terceiros para encaminhar mensagens para a caixa de correio que você especificar.

O fornecimento de mensagens relatadas pelo usuário para uma caixa de correio personalizada em vez de diretamente para a Microsoft permite que os administradores reportem mensagens de forma seletiva e manual para a Microsoft usando o [envio do administrador](admin-submission.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página **envios de usuários** , use <https://protection.office.com/userSubmissionsReportMessage> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Para se conectar ao PowerShell do EOP autônomo, confira [conectar-se ao PowerShell do Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Você precisa receber permissões para executar esses procedimentos. Para configurar a caixa de correio para envios de usuários, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de **administrador de segurança** . Para obter mais informações sobre grupos de funções no Centro de Conformidade e Segurança, confira [Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md).

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Usar o centro de conformidade de & de segurança para configurar a caixa de correio de envios de usuários

1. No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **envios do usuário**da política de gerenciamento de ameaças.

2. Na página **envios de usuários** que aparece, selecione uma das seguintes opções:

   a. **Habilitar o recurso de mensagem de relatório para o Outlook (recomendado)**: Selecione essa opção se você usar o suplemento de mensagem de relatório ou os relatórios internos no Outlook na Web e, em seguida, defina as seguintes configurações:

      - **Personalizar a mensagem de confirmação do usuário final**: clique neste link. No submenu **Personalizar mensagem de confirmação** que aparece, defina as seguintes configurações:

      - **Antes do envio**: nas caixas de **mensagem** **título** e confirmação, insira o texto descritivo que os usuários veem antes de reportar uma mensagem usando o suplemento de mensagem de relatório. Você pode usar a variável% Type% para incluir o tipo de envio (lixo eletrônico, não lixo eletrônico, Phish, etc.).

        Conforme observado, se você selecionar uma opção que envia as mensagens relatadas à Microsoft, o texto a seguir também será adicionado à notificação:

        > Seu email será enviado como é para a Microsoft para análise. Alguns emails podem conter informações pessoais ou confidenciais.

      - **Após o envio**: clique em ![ ícone de expansão ](../../media/scc-expand-icon.png) . Nas caixas de mensagem **título** e **confirmação** , insira o texto descritivo que os usuários veem depois de reportar uma mensagem usando o suplemento de mensagem de relatório. Você pode usar a variável% Type% para incluir o tipo de envio.

      Quando concluir, clique em **Salvar**. Para limpar esses valores, clique em **restaurar** novamente na página **envios de usuários** .

      - **Enviar as mensagens relatadas para**: faça uma das seguintes seleções:

        - **Microsoft (recomendado)**: a caixa de correio de envios do usuário não é usada (todas as mensagens relatadas vão para a Microsoft).

        - **Microsoft e uma caixa de correio personalizada**: na caixa exibida, insira o endereço de email de uma caixa de correio do Exchange Online existente. Os grupos de distribuição não são permitidos. Os envios de usuários vão para a Microsoft para análise e para a caixa de correio personalizada da equipe de administração ou de operações de segurança a serem analisadas.

        - Caixa de **correio personalizada**: na caixa exibida, insira o endereço de email de uma caixa de correio do Exchange Online existente. Os grupos de distribuição não são permitidos. Use essa opção se quiser que a mensagem apenas vá para a equipe de operações de administrador ou de segurança para análise primeiro. As mensagens não irão para a Microsoft, a menos que o administrador a encaminhe.

        Quando tiver concluído, clique em **confirmar**.

     > [!CAUTION]
     > Se você [desabilitou o envio de relatórios de lixo eletrônico no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) usando o Outlook nas políticas de caixa de correio da Web, mas configurar qualquer uma das configurações anteriores para relatar mensagens à Microsoft, os usuários poderão relatar mensagens para a Microsoft no Outlook na Web usando o suplemento de mensagem de relatório.

   - **Desabilitar o recurso de mensagem de relatório para Outlook**: Selecione essa opção se você usar ferramentas de relatório de terceiros em vez do suplemento de mensagem de relatório ou os relatórios internos no Outlook na Web e, em seguida, defina as seguintes configurações:

      Selecione **usar esta caixa de correio personalizada para receber os envios relatados pelo usuário**. Na caixa exibida, insira o endereço de email de uma caixa de correio existente que já está no Office 365. Deve ser uma caixa de correio existente no Exchange Online que possa receber emails.

      Quando tiver concluído, clique em **confirmar**.

## <a name="message-submission-format"></a>Formato de envio de mensagens

As mensagens enviadas para caixas de correio personalizadas precisam seguir um formato de email de envio específico. O assunto (título do envelope) do envio deve estar neste formato:

`{(int)safetyApiAction}|{networkId}|{senderIp}|{fromAddress}|({subject.Substring(0, Math.Min(subjectLen, subject.Length))})`

SafetyApiAction foi:

- Lixo eletrônico = 1
- Não é lixo eletrônico = 2
- Phish = 3

No exemplo a seguir:

- A mensagem está sendo relatada como phishing.
- A ID da mensagem de rede é 49871234-6dc6-43e8-ABCD-08d797f20abe.
- O IP do remetente é 167.220.232.101.
- O endereço de é test@contoso.com.
- O assunto do email da mensagem é "testar envio de phishing"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

As mensagens que não seguem esse formato não serão exibidas corretamente no portal de envios.
