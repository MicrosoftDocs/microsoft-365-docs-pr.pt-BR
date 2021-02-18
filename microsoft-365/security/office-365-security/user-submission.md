---
title: Política de envios de usuário
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
ms.openlocfilehash: 6022d2ca0e4357b422a20490fee7486affefa09c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287264"
---
# <a name="user-submissions-policy"></a>Política de envios de usuário

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nas organizações do Microsoft 365 com caixas de correio do Exchange Online, você pode especificar uma caixa de correio para receber mensagens que os usuários relatam como mal-intencionadas ou não mal-intencionadas. Quando os usuários enviam mensagens usando as várias opções de relatório, você pode usar essa caixa de correio para interceptar mensagens (enviar somente para a caixa de correio personalizada) ou receber cópias de mensagens (enviar para a caixa de correio personalizada e a Microsoft). Esse recurso funciona com as seguintes opções de relatório de mensagens:

- [O complemento Mensagem de Relatório](enable-the-report-message-add-in.md)

- [O add-in De phishing de relatório](enable-the-report-phish-add-in.md)

- [Relatórios integrados no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (anteriormente conhecido como Outlook Web App)

- [Relatórios integrados no Outlook para iOS e Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Se os relatórios foram desabilitados no Outlook na [Web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)habilitar envios de usuário aqui substituirá essa configuração e permitirá que os usuários re reportem mensagens no Outlook na Web.

Você também pode configurar ferramentas de relatório de mensagens de terceiros para encaminhar mensagens para a caixa de correio especificada.

Entregar mensagens relatadas pelo usuário para uma caixa de correio personalizada em vez de diretamente para a Microsoft permite que seus administradores reportem mensagens seletiva e manualmente à Microsoft usando o envio [de Administrador.](admin-submission.md)

## <a name="custom-mailbox-prerequisites"></a>Pré-requisitos de caixa de correio personalizados

Use os artigos a seguir para configurar os pré-requisitos necessários para que as mensagens relatadas pelo usuário acessem sua caixa de correio personalizada:

- Ignore a filtragem de spam na caixa de correio personalizada criando uma regra de fluxo de emails do Exchange para definir o nível de confiança de spam. Consulte [Usar o EAC para criar uma regra](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) de fluxo de emails que define o SCL de uma mensagem para definir o SCL como **-1**.

- Desativar a verificação de anexos de malware na caixa de correio personalizada. Use políticas de Configuração de Anexos Seguros no [Defender para Office 365](set-up-atp-safe-attachments-policies.md) para criar uma política de Anexos Seguros com a configuração Off para a resposta de malware desconhecida de **Anexos Seguros.** 

- Desativar a verificação de URL em mensagens na caixa de correio personalizada. Use as políticas Configurar Links Seguros no [Defender para Office 365](set-up-atp-safe-links-policies.md) para criar uma política de Links Seguros com a configuração Para Selecionar a ação para URLs potencialmente mal-intencionadas **desconhecidas nas mensagens.** 

- Crie uma política anti-malware para desativar a Limpeza Automática Zero Hora do Malware. Consulte Usar o Centro de Conformidade & segurança para criar políticas [anti-malware](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) para definir a Limpeza **Automática Zero Hora** do Malware como **Desligada.**

- Crie uma política de filtro de spam para desabilitar a ZAP (Limpeza Automática Zero Hora) para spam e phishing na caixa de correio personalizada. Consulte Usar o Centro de Conformidade e Segurança & para criar políticas [anti-spam](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) e des clear the **On** checkboxes for **Spam ZAP** and Phish **ZAP**.

- Desabilite a regra de lixo eletrônico na caixa de correio personalizada. Use [Definir configurações de lixo eletrônico em caixas de correio do Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md) para desabilitar a regra de lixo eletrônico. Depois de desabilitada, o EOP não pode mover mensagens para  a pasta Lixo Eletrônico com base na ação de veredito de filtragem de spam Mover mensagem para a pasta Lixo Eletrônico ou o conjunto de listas seguras na caixa de correio.

Depois de verificar se sua caixa de correio atende a todos os pré-requisitos aplicáveis, & use o Centro de Conformidade e Segurança para configurar a caixa de correio de [envios](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) do usuário (neste artigo).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a **página envios de** usuário, use <https://protection.office.com/userSubmissionsReportMessage> .

- Para modificar a configuração para envios de usuário, você precisa ser membro de um dos seguintes grupos de função:

  - **Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).
  - **Gerenciamento da organização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Você precisa acessar o PowerShell do Exchange Online. Se a conta que você está tentando usar não tiver acesso ao PowerShell do Exchange Online, você receberá um erro parecido com este ao especificar a caixa de correio de envios:

  > Especificar um endereço de email em seu domínio

  Para obter mais informações sobre a habilitação ou desabilitação do acesso ao PowerShell do Exchange Online, consulte os seguintes tópicos:

  - [Habilitar ou desabilitar o acesso ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Regras de Acesso para Cliente no Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Usar o Centro de Conformidade & segurança para configurar a caixa de correio de envios do usuário

1. No Centro de Conformidade & segurança,  vá para envios de usuário da Política de Gerenciamento \>  \> **de Ameaças.**

2. Na página **Envios de usuário** exibida, selecione uma das seguintes opções:

   1. Habilitar o recurso Mensagem de Relatório do **Outlook (Recomendado)**: selecione essa opção se você usar o complemento Mensagem de Relatório, o relatório de phishing ou os relatórios integrados no Outlook na Web e, em seguida, definir as seguintes configurações:

      - **Personalize a mensagem de confirmação do usuário final:** clique neste link. No menu **de confirmação Personalizar mensagem** exibida, de configure as seguintes configurações:

      - **Antes do** envio:  nas caixas de mensagem Título e Confirmação, insira o texto descritivo que os usuários veem antes de relatar uma mensagem usando o complemento Mensagem de Relatório ou o complemento Phishing de Relatório.  Você pode usar a variável %type% para incluir o tipo de envio (lixo eletrônico, não lixo eletrônico, phishing etc.).

        Conforme registrado, se você selecionar uma opção que envia as mensagens relatadas à Microsoft, o texto a seguir também será adicionado à notificação:

        > Seu email será enviado como está à Microsoft para análise. Alguns emails podem conter informações pessoais ou confidenciais.

      - **Após o envio:** clique ![ no ícone ](../../media/scc-expand-icon.png) Expandir. Nas caixas  **de** mensagem Título e Confirmação, insira o texto descritivo que os usuários veem depois de relatar uma mensagem usando o complemento Mensagem de Relatório ou o complemento Phishing de Relatório. Você pode usar a variável %type% para incluir o tipo de envio.

      Quando concluir, clique em **Salvar**. Para limpar esses valores, clique **em Restaurar** novamente na **página Envios de** usuário.

      - **Envie as mensagens relatadas para:** Faça uma das seguintes seleções:

        - **Microsoft (Recomendado)**: a caixa de correio de envios do usuário não é usada (todas as mensagens relatadas vão para a Microsoft).

        - **Microsoft e uma caixa de correio personalizada:** na caixa exibida, insira o endereço de email de uma caixa de correio existente do Exchange Online. Grupos de distribuição não são permitidos. Os envios de usuário serão para a Microsoft para análise e para a caixa de correio personalizada para que sua equipe de operações de segurança ou administrador analise.

        - **Caixa de** correio personalizada: na caixa exibida, insira o endereço de email de uma caixa de correio existente do Exchange Online. Grupos de distribuição não são permitidos. Use essa opção se quiser que a mensagem vá apenas para um administrador ou para a equipe de operações de segurança para análise primeiro. As mensagens não serão enviadas para a Microsoft, a menos que o administrador as encaminhe por conta própria.

        > [!NOTE]
        > As organizações governamentais dos EUA (GCC, GCC-H e DoD) só podem configurar a caixa **de correio Personalizada.** As outras duas opções estão desabilitadas.

      Quando terminar, clique em **Confirmar.**

      > [!CAUTION]
      > Se você desabilitou o relatório de lixo eletrônico no Outlook na [Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) usando as políticas de caixa de correio do Outlook na Web, mas definiu uma das configurações anteriores para relatar mensagens à Microsoft, os usuários poderão relatar mensagens à Microsoft no Outlook na Web usando o complemento Mensagem de Relatório ou o complemento Phishing de Relatório.

   - Desabilite o recurso Mensagem de Relatório do **Outlook:** selecione essa opção se você usar ferramentas de relatório de terceiros em vez do complemento Mensagem de Relatório, o complemento Relatar Phishing ou os relatórios integrados no Outlook na Web e, em seguida, definir as seguintes configurações:

      Selecione **Usar essa caixa de correio personalizada para receber envios relatados pelo usuário.** Na caixa exibida, insira o endereço de email de uma caixa de correio existente que já está no Office 365. Deve ser uma caixa de correio existente no Exchange Online que pode receber emails.

      Quando terminar, clique em **Confirmar.**

## <a name="message-submission-format"></a>Formato de envio de mensagem

As mensagens enviadas para caixas de correio personalizadas precisam seguir um formato de email de envio específico. O Assunto (Título do Envelope) do envio deve estar neste formato:

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

em que SafetyAPIAction é um dos seguintes valores inteiros:

- 1: Lixo eletrônico
- 2: Não é lixo eletrônico
- 3: Phishing

No exemplo a seguir:

- A mensagem está sendo relatada como phishing.
- A ID de Mensagem de Rede é 49871234-6dc6-43e8-abcd-08d797f20abe.
- O IP do Remetente é 167.220.232.101.
- O endereço De é test@contoso.com.
- A linha de assunto da mensagem é "testar o envio de phishing"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

Mensagens que não seguem esse formato não serão exibidas corretamente no portal envios.
