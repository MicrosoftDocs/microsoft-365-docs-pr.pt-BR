---
title: Relatar lixo eletrônico e phishing no Outlook na Web
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
description: Os administradores podem aprender sobre as opções internas de relatório de lixo eletrônico, não lixo eletrônico e phishing no Outlook na Web (Outlook Web App) no Exchange Online e como desabilitar essas opções de relatório para usuários.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0af57aceed608ae80e72e3ae18724925c1168e26
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029205"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Relatar lixo eletrônico e phishing no Outlook na Web no Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Nas organizações do Microsoft 365 com caixas de correio no Exchange Online, você pode usar as opções internas de relatório no Outlook na Web (anteriormente conhecido como Outlook Web App) para enviar falsos positivos (emails bons marcados como spam), falsos negativos (emails falsos permitidos) e mensagens de phishing para o Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Se você for um administrador em uma organização com caixas de correio do Exchange Online, recomendamos usar o portal de Envios no Centro de Conformidade e Segurança & Segurança. Para obter mais informações, consulte Usar o Envio de Administrador [para enviar spam, phishing, URLs e arquivos suspeitos para a Microsoft.](admin-submission.md)

- Os administradores podem desabilitar ou habilitar a capacidade dos usuários de relatar mensagens à Microsoft no Outlook na Web. Para obter detalhes, consulte [a seção Desabilitar](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) ou habilitar o relatório de lixo eletrônico no Outlook na Web posteriormente neste artigo.

- Você pode configurar mensagens relatadas para serem copiadas ou redirecionadas para uma caixa de correio que você especificar. Para obter mais informações, consulte [Políticas de envios de usuário.](user-submission.md)

- Para obter mais informações sobre como relatar mensagens à Microsoft, consulte [Mensagens e arquivos de relatório para a Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a>Relatar mensagens de spam e phishing no Outlook na Web

1. Para mensagens na Caixa de Entrada ou em qualquer outra pasta de email, exceto Lixo Eletrônico, use um dos métodos a seguir para relatar mensagens de spam e phishing:

   - Selecione a mensagem, clique **em Lixo** Eletrônico na barra de ferramentas e selecione **Lixo Eletrônico** ou **Phishing.**

     ![Relatar lixo eletrônico ou email de phishing da faixa de opções](../../media/owa-report-junk.png)

   - Selecione uma ou mais mensagens, clique com o botão direito do mouse e selecione **Marcar como lixo eletrônico.**

2. Na caixa de diálogo exibida, clique em **Relatório.** Se você mudar de ideia, clique **em Não Relatar.**

   |Lixo eletrônico|Phishing|
   |:---:|:---:|
   |![Relatar como caixa de diálogo lixo eletrônico](../../media/owa-report-as-junk-dialog.png)|![Relatar como caixa de diálogo de phishing](../../media/owa-report-as-phishing-dialog.png)|

3. As mensagens selecionadas serão enviadas à Microsoft para análise. Para confirmar se as mensagens foram enviadas, abra sua pasta **Itens Enviados** para exibir as mensagens enviadas.

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a>Relatar mensagens de não spam e phishing da pasta Lixo Eletrônico no Outlook na Web

1. Na pasta Lixo Eletrônico, use um dos métodos a seguir para relatar falsos positivos de spam ou mensagens de phishing:

   - Selecione a mensagem, clique **em Não é Lixo** Eletrônico na barra de ferramentas e selecione Não é Lixo **Eletrônico** ou **Phishing.**

     ![Relatar não lixo eletrônico ou não phishing na faixa de opções](../../media/owa-report-not-junk.png)

   - Selecione uma ou mais mensagens, clique com o botão direito do mouse e selecione **Marcar como não sendo lixo eletrônico.**

2. Na caixa de diálogo exibida, leia as informações e clique em **Relatório.** Se você mudar de ideia, clique **em Não Relatar.**

   |Não é Lixo Eletrônico|Phishing|
   |:---:|:---:|
   |![Relatar como não é uma caixa de diálogo de lixo eletrônico](../../media/owa-report-as-not-junk-dialog.png)|![Relatar como caixa de diálogo de phishing](../../media/owa-report-as-phishing-dialog.png)|

3. As mensagens selecionadas serão enviadas à Microsoft para análise. Para confirmar se as mensagens foram enviadas, abra sua pasta **Itens Enviados** para exibir as mensagens enviadas.

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Desabilitar ou habilitar relatórios de lixo eletrônico no Outlook na Web

Por padrão, os usuários podem relatar falsos positivos de spam, falsos negativos e mensagens de phishing à Microsoft para análise no Outlook na Web. Os administradores podem configurar as políticas de caixa de correio do Outlook na Web no PowerShell do Exchange Online para impedir que os usuários reportem falsos positivos e falsos negativos de spam para a Microsoft. Não é possível desabilitar a capacidade dos usuários relatarem mensagens de phishing à Microsoft.

### <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para se conectar ao Windows PowerShell do Exchange Online, confira [Conectar ao Windows PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Você precisa ter permissões no Exchange Online para poder fazer os procedimentos neste artigo. Especificamente, você precisa das **funções Políticas** de Destinatário ou  Destinatários  de Email, que são **atribuídas** aos grupos de função Gerenciamento da Organização e Gerenciamento de Destinatários por padrão. Para obter mais informações sobre grupos de função no Exchange Online, consulte Permissões no [Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) e modificar grupos de função no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).

- Cada organização tem uma política padrão chamada OwaMailboxPolicy-Default, mas você pode criar políticas personalizadas. As políticas personalizadas são aplicadas a usuários com escopo antes da política padrão. Para saber mais sobre as políticas de caixa de correio do Outlook na Web, confira as políticas de caixa de correio do Outlook na [Web no Exchange Online.](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)

- Desabilitar o relatório de lixo eletrônico não remove a capacidade de marcar uma mensagem como lixo eletrônico ou não no Outlook na Web. Selecionar uma mensagem na pasta Lixo eletrônico e clicar em **Não** é lixo eletrônico Ainda move a mensagem de volta para a \>  Caixa de Entrada. Selecionar uma mensagem em qualquer outra pasta de email e clicar em **Lixo** Eletrônico ainda move a mensagem \>  para a pasta Lixo Eletrônico. O que não está mais disponível é a opção de relatar a mensagem à Microsoft.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Usar o PowerShell do Exchange Online para desabilitar ou habilitar relatórios de lixo eletrônico no Outlook na Web

1. Para encontrar as políticas de caixa de correio existentes do Outlook na Web e o status do relatório de lixo eletrônico, execute o seguinte comando:

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Para desabilitar ou habilitar o relatório de lixo eletrônico no Outlook na Web, use a seguinte sintaxe:

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

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) e [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).

### <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você habilitar ou desabilitar com êxito os relatórios de lixo eletrônico no Outlook na Web, use uma das seguintes etapas:

- No PowerShell do Exchange Online, execute o seguinte comando e verifique o valor da propriedade **ReportJunkEmailEnabled:**

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Abra a caixa de correio de um usuário afetado no Outlook  na Web, selecione uma mensagem na Caixa de Entrada, clique em Lixo Eletrônico e verifique se o prompt para relatar a mensagem à Microsoft é ou não \>  exibido.<sup>\*</sup>

- Abra a caixa de correio de um usuário afetado no Outlook na  Web, selecione uma mensagem na pasta Lixo Eletrônico, clique em Lixo Eletrônico e verifique se o prompt para relatar a mensagem à Microsoft é ou não \>  exibido.<sup>\*</sup>

<sup>\*</sup> Os usuários podem ocultar o prompt para relatar a mensagem enquanto ainda relatam a mensagem. Para verificar essa configuração no Outlook na Web:

1. Click **Settings** ![ Outlook on the web settings icon View all Outlook ](../../media/owa-settings-icon.png) \> **settings** Junk \> **email**.
2. Na seção **Relatórios,** verifique o valor: **Pergunte-me antes de enviar um relatório.**

   ![Configurações de Relatório de Lixo Eletrônico do Outlook na Web](../../media/owa-junk-email-reporting-options.png)
