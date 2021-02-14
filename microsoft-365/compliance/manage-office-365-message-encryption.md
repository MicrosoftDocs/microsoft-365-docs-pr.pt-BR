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
description: Depois de terminar de configurar a Criptografia de Mensagens do Office 365 (OME), saiba como personalizar sua implantação de várias maneiras.
ms.openlocfilehash: 83fa620852ea9b2e0cd50d50b6715742658b7239
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815428"
---
# <a name="manage-office-365-message-encryption"></a>Gerenciar a Criptografia de Mensagens do Office 365

Depois de terminar de configurar a Criptografia de Mensagens do Office 365 (OME), você pode personalizar a configuração da sua implantação de várias maneiras. Por exemplo, você pode configurar se deve habilitar códigos de acesso único, exibir o botão Criptografar no Outlook na Web e muito mais.  As tarefas neste artigo descrevem como.

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Gerenciar se os destinatários da Conta do Google, do Yahoo e da Microsoft podem usar essas contas para entrar no portal de Criptografia de Mensagens do Office 365

Quando você configura os novos recursos de Criptografia de Mensagens do Office 365, os usuários em sua organização podem enviar mensagens para destinatários que estão fora da sua organização. Se o destinatário usar uma *ID social,* como uma conta do Google, do Yahoo ou da Microsoft, o destinatário poderá entrar no portal do OME com uma ID social. Se quiser, você pode optar por não permitir que os destinatários usem IDs sociais para entrar no portal do OME.
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>Para gerenciar se os destinatários podem usar IDs sociais para entrar no portal do OME
  
1. [Conecte-se ao Exchange Online usando o PowerShell Remoto.](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)

2. Execute o Set-OMEConfiguration cmdlet com o parâmetro SocialIdSignIn da seguinte forma:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   Por exemplo, para desabilitar as IDs sociais:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   Para habilitar IDs sociais:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>Gerenciar o uso de códigos de acesso único para o portal de Criptografia de Mensagens do Office 365

Se o destinatário de uma mensagem criptografada pelo OME não usar o Outlook, independentemente da conta usada pelo destinatário, o destinatário receberá um link de exibição da Web de tempo limitado que permite que ele leia a mensagem. Esse link inclui um código de acesso único. Como administrador, você pode decidir se os destinatários podem usar códigos de acesso único para entrar no portal do OME.
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>Para gerenciar se o OME gera códigos de acesso único
  
1. Use uma conta comercial ou de estudante que tenha permissões de administrador global em sua organização, inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).

2. Execute o Set-OMEConfiguration cmdlet com o parâmetro OTPEnabled:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   Por exemplo, para desabilitar códigos de acesso único:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   Para habilitar códigos de acesso único:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>Gerenciar a exibição do botão Criptografar no Outlook na Web

Como administrador, você pode gerenciar se deve exibir esse botão para os usuários finais.
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>Para gerenciar se o botão Criptografar aparece no Outlook na Web
  
1. Use uma conta comercial ou de estudante que tenha permissões de administrador global em sua organização, inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).

2. Execute o Set-IRMConfiguration cmdlet com o parâmetro -SimplifiedClientAccessEnabled:

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

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>Habilitar a descriptografia do lado do serviço de mensagens de email para usuários do aplicativo de email iOS

O aplicativo de email do iOS não pode descriptografar mensagens protegidas com a Criptografia de Mensagem do Office 365. Como administrador do Microsoft 365, você pode aplicar a descriptografia do lado do serviço para mensagens entregues ao aplicativo de email do iOS. Quando você opta por usar a descriptografia do lado do serviço, o serviço envia uma cópia descriptografada da mensagem para o dispositivo iOS. O dispositivo cliente armazena uma cópia descriptografada da mensagem. A mensagem também mantém informações sobre direitos de uso, mesmo que o aplicativo de email iOS não aplique direitos de uso do lado do cliente ao usuário. O usuário pode copiar ou imprimir a mensagem, mesmo que originalmente não tenha os direitos de fazê-lo. No entanto, se o usuário tentar concluir uma ação que exija o servidor de email do Microsoft 365, como encaminhar a mensagem, o servidor não permitirá a ação se o usuário originalmente não tiver o direito de uso para fazer isso. No entanto, os usuários finais podem trabalhar em torno da restrição de uso "Não Encaminhar" encaminhando a mensagem de uma conta diferente dentro do aplicativo de email do iOS. Independentemente de você configurar ou não a descriptografia de email no lado do serviço, os anexos a emails criptografados e direitos protegidos não podem ser exibidos no aplicativo de email do iOS.
  
Se você optar por não permitir que mensagens descriptografadas sejam enviadas a usuários de aplicativos de email do iOS, os usuários receberão uma mensagem informando que eles não têm direitos para exibir a mensagem. Por padrão, a descriptografia do lado do serviço de mensagens de email não está habilitada.
  
Para obter mais informações e obter uma visão da experiência do cliente, consulte Exibir mensagens criptografadas em [seu iPhone ou iPad.](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>Para gerenciar se os usuários do aplicativo de email iOS podem exibir mensagens protegidas pela Criptografia de Mensagem do Office 365
  
1. Use uma conta comercial ou de estudante que tenha permissões de administrador global em sua organização, inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).

2. Execute o Set-ActiveSyncOrganizations cmdlet com o parâmetro AllowRMSSupportForUnenlightenedApps:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   Por exemplo, para configurar o serviço para descriptografar mensagens antes que elas são enviadas para aplicativos não-lighted, como o aplicativo de email do iOS:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   Ou, para configurar o serviço para não enviar mensagens descriptografadas para aplicativos não-lighted:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> As políticas de caixa de correio individuais (OWA/ActiveSync) substituem essas configurações (ou seja, se -IRMEnabled for definido como False na respectiva política de Caixa de Correio do OWA ou na política de Caixa de Correio do ActiveSync, essas configurações não se aplicarão).

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Habilitar a descriptografia do lado do serviço de anexos de email para clientes de email do navegador da Web

Normalmente, quando você usa a criptografia de mensagem do Office 365, os anexos são criptografados automaticamente. Como administrador, você pode aplicar a descriptografia do lado do serviço para anexos de email que os usuários baixam de um navegador da Web.
  
Quando você usa a descriptografia do lado do serviço, o serviço envia uma cópia descriptografada do arquivo para o dispositivo. A mensagem ainda está criptografada. O anexo de email também mantém informações sobre direitos de uso, mesmo que o navegador não aplique direitos de uso do lado do cliente ao usuário. O usuário pode copiar ou imprimir o anexo de email, mesmo que ele originalmente não tenha os direitos de fazê-lo. No entanto, se o usuário tentar concluir uma ação que exija o servidor de email do Microsoft 365, como encaminhar o anexo, o servidor não permitirá a ação se o usuário originalmente não tiver o direito de uso para fazer isso.
  
Independentemente de você configurar ou não a descriptografia do lado do serviço de anexos, os usuários não poderão exibir anexos para email criptografado e protegido por direitos no aplicativo de email do iOS.
  
Se você optar por não permitir anexos de email descriptografados, que é o padrão, os usuários receberão uma mensagem informando que eles não têm direitos para exibir o anexo.
  
Para obter mais informações sobre como o Microsoft 365 implementa a criptografia para emails e anexos de email com a Encrypt-Only de email, consulte a opção Somente Criptografia [para emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>Para gerenciar se anexos de email são descriptografados ao baixar de um navegador da Web
  
1. Use uma conta comercial ou de estudante que tenha permissões de administrador global em sua organização, inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).

2. Execute o Set-IRMConfiguration cmdlet com o parâmetro DecryptAttachmentForEncryptOnly:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   Por exemplo, para configurar o serviço para descriptografar anexos de email quando um usuário os baixa de um navegador da Web:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   Para configurar o serviço para deixar anexos de email criptografados como estão no download:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a>Certifique-se de que todos os destinatários externos usem o Portal OME para ler emails criptografados

Você pode usar modelos de identidade visual personalizados para forçar os destinatários a receberem um email de wrapper que os direciona a ler emails criptografados no Portal OME em vez de usar o Outlook ou o Outlook na Web. Talvez você queira fazer isso se quiser ter mais controle sobre como os destinatários usam o email recebido. Por exemplo, se destinatários externos exibirem emails no portal da Web, você poderá definir uma data de expiração para o email e revogar o email. Esses recursos só são suportados por meio do Portal OME. Você pode usar as opções Criptografar e Não Encaminhar ao criar as regras de fluxo de emails.

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a>Usar um modelo personalizado para forçar todos os destinatários externos a usar o Portal OME e emails criptografados

1. Use uma conta comercial ou de estudante que tenha permissões de administrador global em sua organização, inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).

2. Execute o New-TransportRule cmdlet:

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    em que:

   - `mail flow rule name` é o nome que você deseja usar para a nova regra de fluxo de emails.

   - `option name` é um `Encrypt` ou `Do Not Forward` .

   - `template name` é o nome que você deu ao modelo de identidade visual personalizado, por `OME Configuration` exemplo.

   Para criptografar todos os emails externos com o modelo "Configuração do OME" e aplicar a Encrypt-Only opção:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   Para criptografar todos os emails externos com o modelo "Configuração do OME" e aplicar a opção Não Encaminhar:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>Personalizar a aparência das mensagens de email e o portal OME

Para obter informações detalhadas sobre como personalizar o OME para sua organização, consulte Adicionar a marca da sua organização [às suas mensagens criptografadas.](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="disable-the-new-capabilities-for-ome"></a>Desabilitar os novos recursos para OME

Esperamos que isso não seja o caso, mas, se você precisar, desabilitar os novos recursos para OME é muito simples. Primeiro, você precisará remover quaisquer regras de fluxo de emails que você criou que usem os novos recursos do OME. Para obter informações sobre como remover regras de fluxo de emails, consulte [Gerenciar regras de fluxo de emails.](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx) Em seguida, conclua estas etapas no PowerShell do Exchange Online.
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>Para desabilitar os novos recursos do OME
  
1. Usando uma conta de trabalho ou de estudante que tenha permissões de administrador global em sua organização, inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).

2. Se você tiver  habilitado o botão Criptografar no Outlook na Web, desabilite-o executando o cmdlet Set-IRMConfiguration com o parâmetro SimplifiedClientAccessEnabled. Caso contrário, ignore esta etapa.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. Desabilite os novos recursos para OME executando o cmdlet Set-IRMConfiguration com o parâmetro AzureRMSLicensingEnabled definido como falso:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
