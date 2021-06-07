---
title: Relatar lixo eletrônico e email de phishing Outlook na Web
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender sobre as opções internas de relatório de lixo eletrônico, não lixo eletrônico e phishing no Outlook na Web (Outlook Web App) no Exchange Online e como desabilitar essas opções de relatórios para usuários.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1139871f5929ff9fef29e980b7614e5bc7b92570
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788302"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Relatar lixo eletrônico e phishing em Outlook na Web em Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Em organizações com caixas de correio em Exchange Online ou caixas [](../../enterprise/hybrid-modern-auth-overview.md)de correio locais usando autenticação moderna híbrida, você pode enviar falsos positivos (emails bons marcados como spam), falsos negativos (email ruim permitido) e mensagens de phishing para Proteção do Exchange Online (EOP). Microsoft 365

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

> [!IMPORTANT]
> Recomendamos o complemento Mensagem de Relatório ou o complemento Relatar Phishing para envios de usuários. Para obter mais informações, [consulte Enable the Report Message or the Report Phishing add-ins](./enable-the-report-message-add-in.md). Não recomendamos a experiência interna de relatório no Outlook porque ela não pode usar a [política de envio do usuário.](./user-submission.md)

- Se você for um administrador em uma organização com Exchange Online caixas de correio, recomendamos que você use o portal Envios no Centro de Conformidade & Segurança. Para obter mais informações, [consulte Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

- Os administradores podem desabilitar ou habilitar a capacidade de os usuários relatarem mensagens à Microsoft Outlook na Web. Para obter detalhes, consulte [a seção Desabilitar ou](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) habilitar relatórios de lixo eletrônico Outlook na Web posteriormente neste artigo.

- Você pode configurar mensagens relatadas a serem copiadas ou redirecionadas para uma caixa de correio especificada. Para obter mais informações, consulte [Políticas de envios de usuário](user-submission.md).

- Para obter mais informações sobre o relatório de mensagens para a Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Desabilitar ou habilitar relatórios de lixo eletrônico Outlook na Web

Por padrão, os usuários podem relatar falsos positivos de spam, falsos negativos e mensagens de phishing para a Microsoft para análise Outlook na Web. Os administradores podem configurar Outlook nas políticas de caixa de correio da Web no Exchange Online PowerShell para impedir que os usuários reportem falsos positivos de spam e falsos negativos de spam para a Microsoft. Não é possível desabilitar a capacidade de os usuários relatarem mensagens de phishing à Microsoft.

### <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Você precisa ter permissões atribuídas Exchange Online antes de poder fazer os procedimentos neste artigo. Especificamente, você precisa das **funções Políticas** de Destinatário ou  Destinatários  de Email, que são **atribuídas** aos grupos de função Gerenciamento da Organização e Gerenciamento de Destinatários por padrão. Para obter mais informações sobre grupos de função Exchange Online, consulte Permissões no [Exchange Online](/exchange/permissions-exo/permissions-exo) e Modificar grupos de [função em Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).

- Cada organização tem uma política padrão chamada OwaMailboxPolicy-Default, mas você pode criar políticas personalizadas. Políticas personalizadas são aplicadas a usuários com escopo antes da política padrão. Para obter mais informações sobre Outlook nas políticas de caixa de correio da Web, consulte Outlook nas políticas de caixa de correio da [Web em Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).

- Desabilitar relatórios de lixo eletrônico não remove a capacidade de marcar uma mensagem como lixo eletrônico ou não lixo eletrônico Outlook na Web. Selecionar uma mensagem na pasta Lixo Eletrônico e clicar em Não lixo **eletrônico** Não lixo eletrônico ainda move a mensagem de \>  volta para a Caixa de Entrada. Selecionar uma mensagem em qualquer outra pasta de email e clicar em **Lixo** Eletrônico ainda move a mensagem \>  para a pasta Lixo Eletrônico. O que não está mais disponível é a opção de relatar a mensagem à Microsoft.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Use Exchange Online PowerShell para desabilitar ou habilitar relatórios de lixo eletrônico Outlook na Web

1. Para encontrar suas informações Outlook nas políticas de caixa de correio da Web e o status do relatório de lixo eletrônico, execute o seguinte comando:

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Para desabilitar ou habilitar relatórios de lixo eletrônico Outlook na Web, use a seguinte sintaxe:

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   Este exemplo desabilita o relatório de lixo eletrônico na política padrão.

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   Este exemplo habilita o relatório de lixo eletrônico na política personalizada denominada Gerentes da Contoso.

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) e [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).

### <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você habilitar ou desabilitar com êxito o relatório de lixo eletrônico no Outlook na Web, use qualquer uma das seguintes etapas:

- No Exchange Online PowerShell, execute o seguinte comando e verifique o valor da propriedade **ReportJunkEmailEnabled:**

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Abra a caixa de correio de um usuário afetado Outlook na Web,  selecione uma mensagem na Caixa de Entrada, clique em Lixo Eletrônico e verifique se o prompt para relatar a mensagem à Microsoft é ou não \>  exibido.<sup>\*</sup>

- Abra a caixa de correio de um usuário afetado Outlook na Web, selecione  uma mensagem na pasta Lixo Eletrônico, clique em Lixo Eletrônico e verifique se o prompt para relatar a mensagem à Microsoft é ou não \>  exibido.<sup>\*</sup>

<sup>\*</sup> Os usuários podem ocultar o prompt para relatar a mensagem enquanto ainda relatam a mensagem. Para verificar essa configuração Outlook na Web:

1. Clique **Configurações** ![ Outlook no ícone configurações da Web ](../../media/owa-settings-icon.png) \> **Exibir todas as Outlook configurações** \> **Lixo eletrônico.**
2. Na seção **Relatórios,** verifique o valor: **Pergunte-me antes de enviar um relatório**.

   ![Outlook configurações do Relatório de Lixo Eletrônico na Web](../../media/owa-junk-email-reporting-options.png)
