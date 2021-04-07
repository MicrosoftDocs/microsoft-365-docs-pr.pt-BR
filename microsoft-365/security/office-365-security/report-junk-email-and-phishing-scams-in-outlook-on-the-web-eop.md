---
title: Relatar lixo eletrônico e email de phishing no Outlook na Web
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
description: Os administradores podem aprender sobre as opções de relatório de lixo eletrônico, não lixo eletrônico e phishing no Outlook na Web (Outlook Web App) no Exchange Online e como desabilitar essas opções de relatórios para usuários.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 933387dd32a6c1ca1e27ee11e4a9384615e8fdec
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615203"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Relatar lixo eletrônico e email de phishing no Outlook na Web no Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nas organizações do Microsoft 365 com caixas de correio [](../../enterprise/hybrid-modern-auth-overview.md)no Exchange Online ou caixas de correio locais usando autenticação moderna híbrida, você pode enviar falsos positivos (emails bons marcados como spam), falsos negativos (email ruim permitido) e mensagens de phishing para a Proteção do Exchange Online (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para a melhor experiência de envio de usuário, recomendamos usar a Mensagem de Relatório e os complementos de Phishing de Relatório. Consulte [Habilitar](./enable-the-report-message-add-in.md) o complemento Mensagem de Relatório e [Habilitar o add-in de Phishing de Relatório](./enable-the-report-phish-add-in.md) para obter mais informações.

- Se você for um administrador em uma organização com caixas de correio do Exchange Online, recomendamos que você use o portal Envios no Centro de Conformidade & Segurança. Para obter mais informações, [consulte Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

- Os administradores podem desabilitar ou habilitar a capacidade de os usuários relatarem mensagens à Microsoft no Outlook na Web. Para obter detalhes, consulte [a seção Desabilitar ou](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) habilitar relatórios de lixo eletrônico no Outlook na Web posteriormente neste artigo.

- Você pode configurar mensagens relatadas a serem copiadas ou redirecionadas para uma caixa de correio especificada. Para obter mais informações, consulte [Políticas de envios de usuário](user-submission.md).

- Para obter mais informações sobre o relatório de mensagens para a Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Desabilitar ou habilitar relatórios de lixo eletrônico no Outlook na Web

Por padrão, os usuários podem relatar falsos positivos de spam, falsos negativos e mensagens de phishing para a Microsoft para análise no Outlook na Web. Os administradores podem configurar as políticas de caixa de correio do Outlook na Web no PowerShell do Exchange Online para impedir que os usuários reportem falsos positivos de spam e falsos negativos de spam para a Microsoft. Não é possível desabilitar a capacidade de os usuários relatarem mensagens de phishing à Microsoft.

### <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Você precisa ter permissões atribuídas no Exchange Online antes de poder fazer os procedimentos neste artigo. Especificamente, você precisa das **funções Políticas** de Destinatário ou  Destinatários  de Email, que são **atribuídas** aos grupos de função Gerenciamento da Organização e Gerenciamento de Destinatários por padrão. Para obter mais informações sobre grupos de função no Exchange Online, consulte [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo) e Modificar grupos de função no Exchange [Online](/Exchange/permissions-exo/role-groups#modify-role-groups).

- Cada organização tem uma política padrão chamada OwaMailboxPolicy-Default, mas você pode criar políticas personalizadas. Políticas personalizadas são aplicadas a usuários com escopo antes da política padrão. Para obter mais informações sobre as políticas de caixa de correio da Web do [Outlook,](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)consulte Outlook on the Web mailbox policies in Exchange Online .

- Desabilitar relatórios de lixo eletrônico não remove a capacidade de marcar uma mensagem como lixo eletrônico ou não lixo eletrônico no Outlook na Web. Selecionar uma mensagem na pasta Lixo Eletrônico e clicar em Não lixo **eletrônico** Não lixo eletrônico ainda move a mensagem de \>  volta para a Caixa de Entrada. Selecionar uma mensagem em qualquer outra pasta de email e clicar em **Lixo** Eletrônico ainda move a mensagem \>  para a pasta Lixo Eletrônico. O que não está mais disponível é a opção de relatar a mensagem à Microsoft.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Usar o PowerShell do Exchange Online para desabilitar ou habilitar relatórios de lixo eletrônico no Outlook na Web

1. Para encontrar seu Outlook existente nas políticas de caixa de correio da Web e o status do relatório de lixo eletrônico, execute o seguinte comando:

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Para desabilitar ou habilitar relatórios de lixo eletrônico no Outlook na Web, use a seguinte sintaxe:

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

- No PowerShell do Exchange Online, execute o seguinte comando e verifique o valor da propriedade **ReportJunkEmailEnabled:**

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Abra a caixa de correio de um usuário afetado no Outlook  na Web, selecione uma mensagem na Caixa de Entrada, clique em Lixo Eletrônico e verifique se o prompt para relatar a mensagem à Microsoft é ou não \>  exibido.<sup>\*</sup>

- Abra a caixa de correio de um usuário afetado no Outlook na  Web, selecione uma mensagem na pasta Lixo Eletrônico, clique em Lixo Eletrônico e verifique se o prompt para relatar a mensagem à Microsoft é ou não \>  exibido.<sup>\*</sup>

<sup>\*</sup> Os usuários podem ocultar o prompt para relatar a mensagem enquanto ainda relatam a mensagem. Para verificar essa configuração no Outlook na Web:

1. Clique **em Configurações** ![ Do Outlook no ícone de configurações da Web ](../../media/owa-settings-icon.png) \> **Exibir todas as configurações do Outlook** \> **Lixo eletrônico.**
2. Na seção **Relatórios,** verifique o valor: **Pergunte-me antes de enviar um relatório**.

   ![Configurações do Relatório de Lixo Eletrônico do Outlook na Web](../../media/owa-junk-email-reporting-options.png)