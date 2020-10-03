---
title: Políticas de envios de usuários
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a configurar uma caixa de correio para coletar spam e emails de phishing relatados pelos usuários.
ms.openlocfilehash: bffa70184a9307869ce6170ba1ea05ae3f084ccf
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350266"
---
# <a name="user-submissions-policies"></a>Políticas de envios de usuários

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Nas organizações do Microsoft 365 com caixas de correio do Exchange Online, você pode especificar uma caixa de correio para receber mensagens que os usuários relatam como mal-intencionadas ou não mal intencionadas. Quando os usuários enviam mensagens usando as várias opções de relatórios, você pode usar essa caixa de correio para interceptar mensagens (enviar somente para a caixa de correio personalizada) ou receber cópias de mensagens (enviar para a caixa de correio personalizada e Microsoft). Este recurso funciona com as seguintes opções de relatório de mensagens:

- [O suplemento de mensagem de relatório](enable-the-report-message-add-in.md)

- [Relatórios internos no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (anteriormente conhecido como Outlook Web App)

- [Relatórios internos no Outlook para iOS e Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Se o relatório tiver sido [desabilitado no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), habilitar os envios de usuários aqui substituirá essa configuração e permitirá que os usuários reportem mensagens no Outlook na Web novamente.

Você também pode configurar ferramentas de relatório de mensagens de terceiros para encaminhar mensagens para a caixa de correio que você especificar.

O fornecimento de mensagens relatadas pelo usuário para uma caixa de correio personalizada em vez de diretamente para a Microsoft permite que os administradores reportem mensagens de forma seletiva e manual para a Microsoft usando o [envio do administrador](admin-submission.md)

## <a name="custom-mailbox-prerequisites"></a>Pré-requisitos de caixa de correio personalizada

Use os artigos a seguir para configurar os pré-requisitos necessários para que o usuário reportado mensagens vá para sua caixa de correio personalizada:

- Ignorar filtragem de spam criando uma regra de fluxo de email do Exchange para definir o nível de confiança de spam. Consulte [usar o Eat para criar uma regra de fluxo de emails que define o SCL de uma mensagem](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages?view=o365-worldwide#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) para definir o SCL como **-1**.

- Desativar a verificação de anexos de malware. Use [Configurar (ou editar) uma política de anexos seguros de ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide#step-2-set-up-or-edit-an-atp-safe-attachments-policy) para criar uma política de anexos seguros com a configuração **off-Attachment não será verificada para malware** habilitado.

- Desative a verificação de URL em mensagens. Use [Adicionar (ou editar) políticas de links seguros de ATP que se aplicam a todos os destinatários de email específicos](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-links-policies?view=o365-worldwide#step-3-add-or-edit-atp-safe-links-policies-that-apply-to-all-or-specific-email-recipients) para criar uma política de links seguros com a **opção Selecionar a ação para URLs possivelmente mal-intencionadas desconhecidas em mensagens** definidas como **desativadas**.

- Criar uma política antimalware para desativar a limpeza automática de malware zero-hora. Consulte [usar o centro de conformidade de & de segurança para criar políticas Antimalware](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide#use-the-security--compliance-center-to-create-anti-spam-policies) para definir a **limpeza automática de zero-hora de malware** como **desativada**.

- Criar uma política de filtro de spam para desabilitar a limpeza automática de zero hora (ZAP) para spam ZAP e Phish de phishing. Consulte [usar o centro de conformidade de & de segurança para criar políticas antispam](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide#use-the-security--compliance-center-to-create-anti-spam-policies) e desmarcar as caixas de seleção **em** spam zap e phishing zap.

- Desabilitar a regra de lixo eletrônico. Use [definir configurações de lixo eletrônico em caixas de correio do Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes?view=o365-worldwide) para desabilitar a regra de lixo eletrônico. Depois de desabilitado, o EOP não pode mover mensagens para a pasta lixo eletrônico com base na ação de filtro de spam veredicto **mover mensagem para a pasta lixo eletrônico** ou para a coleção SafeList na caixa de correio.

Depois de verificar se a caixa de correio atende a todos os pré-requisitos aplicáveis, [use o centro de conformidade de & de segurança para configurar a caixa de correio de envios de usuários](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (neste artigo).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página **envios de usuários** , use <https://protection.office.com/userSubmissionsReportMessage> .

- Para modificar a configuração dos envios de usuários, você precisa ser membro de um dos grupos de função a seguir:

  - **Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).
  - **Gerenciamento de organização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

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

        - Caixa de **correio personalizada**: na caixa exibida, insira o endereço de email de uma caixa de correio do Exchange Online existente. Os grupos de distribuição não são permitidos. Use essa opção se quiser que a mensagem apenas vá para a equipe de operações de segurança ou de administração para análise primeiro. As mensagens não irão para a Microsoft, a menos que o administrador a encaminhe.

        > [!NOTE]
        > As organizações governamentais dos EUA (GCC, GCC-H e DoD) só podem configurar a **caixa de correio personalizada**. As outras duas opções estão desativadas. 

      Quando tiver concluído, clique em **confirmar**.

      > [!CAUTION]
      > Se você [desabilitou o envio de relatórios de lixo eletrônico no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) usando o Outlook nas políticas de caixa de correio da Web, mas configurar qualquer uma das configurações anteriores para relatar mensagens à Microsoft, os usuários poderão relatar mensagens para a Microsoft no Outlook na Web usando o suplemento de mensagem de relatório.

   - **Desabilitar o recurso de mensagem de relatório para Outlook**: Selecione essa opção se você usar ferramentas de relatório de terceiros em vez do suplemento de mensagem de relatório ou os relatórios internos no Outlook na Web e, em seguida, defina as seguintes configurações:

      Selecione **usar esta caixa de correio personalizada para receber os envios relatados pelo usuário**. Na caixa exibida, insira o endereço de email de uma caixa de correio existente que já está no Office 365. Deve ser uma caixa de correio existente no Exchange Online que possa receber emails.

      Quando tiver concluído, clique em **confirmar**.

## <a name="message-submission-format"></a>Formato de envio de mensagens

As mensagens enviadas para caixas de correio personalizadas precisam seguir um formato de email de envio específico. O assunto (título do envelope) do envio deve estar neste formato:

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

SafetyAPIAction é um dos seguintes valores inteiros:

- 1: lixo eletrônico
- 2: não é lixo eletrônico
- 3: Phish

No exemplo a seguir:

- A mensagem está sendo relatada como phishing.
- A ID da mensagem de rede é 49871234-6dc6-43e8-ABCD-08d797f20abe.
- O IP do remetente é 167.220.232.101.
- O endereço de é test@contoso.com.
- A linha de assunto da mensagem é "testar envio de phishing"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

As mensagens que não seguem esse formato não serão exibidas corretamente no portal de envios.
