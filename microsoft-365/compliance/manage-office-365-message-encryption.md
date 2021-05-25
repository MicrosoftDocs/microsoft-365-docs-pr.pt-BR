---
title: Gerenciar a Criptografia de Mensagens do Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Depois de terminar de configurar o Criptografia de Mensagens do Office 365 (OME), saiba como personalizar sua implantação de várias maneiras.
ms.openlocfilehash: a2b3dde44ea541deb41eeb9d55d5ed745fa6c719
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52650979"
---
# <a name="manage-office-365-message-encryption"></a>Gerenciar a Criptografia de Mensagens do Office 365

Depois de terminar de configurar o Criptografia de Mensagens do Office 365 (OME), você pode personalizar a configuração da sua implantação de várias maneiras. Por exemplo, você pode configurar se deve habilitar códigos de passagem única, exibir o botão **Criptografar** Outlook na Web e muito mais. As tarefas deste artigo descrevem como.

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Gerenciar se os destinatários da Conta do Google, do Yahoo e da Microsoft podem usar essas contas para entrar no Criptografia de Mensagens do Office 365 portal

Quando você configura os novos recursos de Criptografia de Mensagens do Office 365, os usuários em sua organização podem enviar mensagens para destinatários que estão fora da sua organização. Se o destinatário usar uma *ID social,* como uma conta do Google, uma conta do Yahoo ou uma conta da Microsoft, o destinatário poderá entrar no portal OME com uma ID social. Se quiser, você pode optar por não permitir que os destinatários usem IDs sociais para entrar no portal OME.
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>Para gerenciar se os destinatários podem usar IDs sociais para entrar no portal OME
  
1. [Conexão usar Exchange Online PowerShell Remoto.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Execute o cmdlet Set-OMEConfiguration com o parâmetro SocialIdSignIn da seguinte forma:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   Por exemplo, para desabilitar IDs sociais:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   Para habilitar IDs sociais:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>Gerenciar o uso de códigos de passagem única para o Criptografia de Mensagens do Office 365 portal

Se o destinatário de uma mensagem criptografada pelo OME não usar Outlook, independentemente da conta usada pelo destinatário, o destinatário receberá um link de exibição da Web de tempo limitado que permite que ele leia a mensagem. Este link inclui um código de passagem única. Como administrador, você pode decidir se os destinatários podem usar códigos de passagem única para entrar no portal OME.
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>Para gerenciar se o OME gera códigos de passagem única
  
1. Use uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização e inicie uma sessão de Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Execute o cmdlet Set-OMEConfiguration com o parâmetro OTPEnabled:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -OTPEnabled <$true|$false>
   ```

   Por exemplo, para desabilitar códigos de passagem única:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   Para habilitar códigos de passagem única:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>Gerenciar a exibição do botão Criptografar Outlook na Web

Como administrador, você pode gerenciar se deve exibir esse botão para usuários finais.
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>Para gerenciar se o botão Criptografar aparece Outlook na Web
  
1. Use uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização e inicie uma sessão de Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Execute o cmdlet Set-IRMConfiguration com o parâmetro -SimplifiedClientAccessEnabled:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   Por exemplo, para desabilitar o **botão Criptografar:**

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   Para habilitar **o botão Criptografar:**

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>Habilitar a descriptografia do lado do serviço de mensagens de email para usuários de aplicativos de email iOS

O aplicativo de email do iOS não pode descriptografar mensagens protegidas com Criptografia de Mensagens do Office 365. Como administrador Microsoft 365, você pode aplicar a descriptografia do lado do serviço para mensagens entregues ao aplicativo de email do iOS. Quando você optar por usar a descriptografia do lado do serviço, o serviço envia uma cópia descriptografada da mensagem para o dispositivo iOS. O dispositivo cliente armazena uma cópia descriptografada da mensagem. A mensagem também mantém informações sobre direitos de uso, mesmo que o aplicativo de email do iOS não aplique direitos de uso do lado do cliente ao usuário. O usuário pode copiar ou imprimir a mensagem mesmo que ele não tenha originalmente os direitos de fazê-lo. No entanto, se o usuário tentar concluir uma ação que exija o servidor de email Microsoft 365, como encaminhar a mensagem, o servidor não permitirá a ação se o usuário originalmente não tiver o direito de uso para fazer isso. No entanto, os usuários finais podem trabalhar em torno da restrição de uso "Não Encaminhar" encaminhando a mensagem de uma conta diferente dentro do aplicativo de email do iOS. Independentemente de você configurar a descriptografia do lado do serviço de email, os anexos aos emails criptografados e protegidos por direitos não podem ser exibidos no aplicativo de email do iOS.
  
Se você optar por não permitir que mensagens descriptografadas sejam enviadas para usuários de aplicativos de email do iOS, os usuários receberão uma mensagem informando que não têm os direitos de exibição da mensagem. Por padrão, a descriptografia do lado do serviço de mensagens de email não está habilitada.
  
Para obter mais informações e para obter uma visão da experiência do cliente, consulte Exibir mensagens criptografadas em seu iPhone [ou iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>Para gerenciar se os usuários de aplicativos de email do iOS podem exibir mensagens protegidas por Criptografia de Mensagens do Office 365
  
1. Use uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização e inicie uma sessão de Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Execute o cmdlet Set-ActiveSyncOrganizations com o parâmetro AllowRMSSupportForUnenlightenedApps:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   Por exemplo, para configurar o serviço para descriptografar mensagens antes que elas são enviadas para aplicativos sem iluminação, como o aplicativo de email do iOS:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   Ou, para configurar o serviço para não enviar mensagens descriptografadas para aplicativos não criptografados:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> As políticas de caixa de correio individuais (OWA/ActiveSync) substituem essas configurações (ou seja, se -IRMEnabled estiver definido como False na respectiva política de Caixa de Correio do OWA ou na política de Caixa de Correio ActiveSync, essas configurações não serão aplicadas).

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Habilitar a descriptografia do lado do serviço de anexos de email para clientes de email do navegador da Web

Normalmente, quando você usa Office 365 de mensagens, os anexos são criptografados automaticamente. Como administrador, você pode aplicar a descriptografia do lado do serviço para anexos de email que os usuários baixam de um navegador da Web.
  
Quando você usa a descriptografia do lado do serviço, o serviço envia uma cópia descriptografada do arquivo para o dispositivo. A mensagem ainda está criptografada. O anexo de email também mantém informações sobre direitos de uso, mesmo que o navegador não aplique direitos de uso do lado do cliente ao usuário. O usuário pode copiar ou imprimir o anexo de email mesmo que ele não tenha originalmente os direitos de fazê-lo. No entanto, se o usuário tentar concluir uma ação que exija o servidor de email Microsoft 365, como encaminhar o anexo, o servidor não permitirá a ação se o usuário originalmente não tiver o direito de uso para fazer isso.
  
Independentemente de você configurar a descriptografia do lado do serviço de anexos, os usuários não podem exibir anexos para email criptografado e protegido por direitos no aplicativo de email do iOS.
  
Se você optar por não permitir anexos de email descriptografados, que é o padrão, os usuários receberão uma mensagem informando que eles não têm direitos para exibir o anexo.
  
Para obter mais informações sobre como Microsoft 365 a criptografia para emails e anexos de email com a opção Encrypt-Only, consulte [Encrypt-Only option for emails.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>Para gerenciar se os anexos de email são descriptografados no download de um navegador da Web
  
1. Use uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização e inicie uma sessão de Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Execute o cmdlet Set-IRMConfiguration com o parâmetro DecryptAttachmentForEncryptOnly:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   Por exemplo, para configurar o serviço para descriptografar anexos de email quando um usuário os baixa de um navegador da Web:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   Para configurar o serviço para deixar anexos de email criptografados como estão ao baixar:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a>Certifique-se de que todos os destinatários externos usem o Portal OME para ler emails criptografados

Você pode usar modelos de identidade visual personalizados para forçar os destinatários a receberem um email de wrapper que os direciona para ler emails criptografados no Portal OME em vez de usar Outlook ou Outlook na Web. Talvez você queira fazer isso se quiser ter um controle maior sobre como os destinatários usam o email recebido. Por exemplo, se destinatários externos exibirem emails no portal da Web, você poderá definir uma data de expiração para o email e revogar o email. Esses recursos só são suportados por meio do Portal OME. Você pode usar a opção Criptografar e a opção Não Encaminhar ao criar as regras de fluxo de emails.

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a>Use um modelo personalizado para forçar todos os destinatários externos a usar o Portal OME e para emails criptografados

1. Use uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização e inicie uma sessão de Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Execute o cmdlet New-TransportRule:

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    em que:

   - `mail flow rule name` é o nome que você deseja usar para a nova regra de fluxo de emails.

   - `option name` é ou `Encrypt` `Do Not Forward` .

   - `template name` é o nome que você deu ao modelo de identidade visual personalizado, por exemplo `OME Configuration` .

   Para criptografar todos os emails externos com o modelo "Configuração OME" e aplicar a Encrypt-Only opção:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   Para criptografar todos os emails externos com o modelo "Configuração OME" e aplicar a opção Não Encaminhar:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>Personalizar a aparência de mensagens de email e o portal OME

Para obter informações detalhadas sobre como personalizar o OME para sua organização, consulte Add your [organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).
  
## <a name="disable-the-new-capabilities-for-ome"></a>Desabilitar os novos recursos para OME

Esperamos que isso não seja possível, mas, se você precisar, desabilitar os novos recursos para OME é muito simples. Primeiro, você precisará remover todas as regras de fluxo de emails criadas que usem os novos recursos OME. Para obter informações sobre como remover regras de fluxo de emails, consulte [Manage mail flow rules](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules). Em seguida, conclua estas etapas Exchange Online PowerShell.
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>Para desabilitar os novos recursos do OME
  
1. Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, inicie uma sessão de Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Se você habilitar o botão **Criptografar** Outlook na Web, desabilite-o executando o cmdlet Set-IRMConfiguration com o parâmetro SimplifiedClientAccessEnabled. Caso contrário, ignore esta etapa.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. Desabilite os novos recursos para OME executando o cmdlet Set-IRMConfiguration com o parâmetro AzureRMSLicensingEnabled definido como false:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
