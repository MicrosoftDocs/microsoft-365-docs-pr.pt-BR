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
description: Após concluir a configuração do Office 365 Message Encryption (OME), você pode personalizar a configuração de sua implantação de várias maneiras. Por exemplo, você pode configurar se deseja habilitar códigos de passagem única, exibir o botão proteger no Outlook na Web e muito mais. As tarefas deste artigo descrevem como.
ms.openlocfilehash: 102d57681e049bf803b377fea97cc0fdb11affb2
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42562047"
---
# <a name="manage-office-365-message-encryption"></a>Gerenciar a Criptografia de Mensagens do Office 365

Após concluir a configuração do Office 365 Message Encryption (OME), você pode personalizar a configuração de sua implantação de várias maneiras. Por exemplo, você pode configurar se deseja habilitar códigos de passagem única, exibir o botão **criptografar** no Outlook na Web e muito mais. As tarefas deste artigo descrevem como.

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Gerenciar se o Google, Yahoo e destinatários de contas da Microsoft podem usar essas contas para entrar no portal de criptografia de mensagens do Office 365

Ao configurar os novos recursos de criptografia de mensagens do Office 365, os usuários em sua organização podem enviar mensagens para destinatários fora da sua organização do Office 365. Se o destinatário usar uma *ID social* , como uma conta do Google, uma conta do Yahoo ou uma conta da Microsoft, o destinatário poderá entrar no portal do ome com uma ID social. Se quiser, você pode optar por não permitir que os destinatários usem IDs sociais para entrar no portal do OME.
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>Para gerenciar se os destinatários podem usar IDs sociais para entrar no portal do OME
  
1. [Conecte-se ao Exchange Online usando o PowerShell remoto](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).

2. Execute o cmdlet Set-OMEConfiguration com o parâmetro SocialIdSignIn da seguinte maneira:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   Por exemplo, para desabilitar as IDs sociais:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   Para habilitar as IDs sociais:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>Gerenciar o uso de códigos de passagem única para o portal de criptografia de mensagem do Office 365

Se o destinatário de uma mensagem criptografada pelo OME não usar o Outlook, independentemente da conta usada pelo destinatário, o destinatário receberá um link de exibição da Web de tempo limitado que permite que ele leia a mensagem. Este link inclui um código de passagem única. Como administrador, você pode decidir se os destinatários podem usar códigos de passagem única para entrar no portal do OME.
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>Para gerenciar se o OME gera códigos de passagem única
  
1. Use uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização do Office 365 e inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).

2. Execute o cmdlet Set-OMEConfiguration com o parâmetro OTPEnabled:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   Por exemplo, para desabilitar códigos de passagem única:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   Para habilitar códigos de passagem única:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>Gerenciar a exibição do botão criptografar no Outlook na Web

Como administrador, você pode gerenciar se deseja exibir este botão para os usuários finais.
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>Para gerenciar se o botão criptografar aparece no Outlook na Web
  
1. Use uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização do Office 365 e inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).

2. Execute o cmdlet Set-IRMConfiguration com o parâmetro-SimplifiedClientAccessEnabled:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   Por exemplo, para desabilitar o botão **criptografar** :

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   Para habilitar o botão **criptografar** :

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>Habilitar a descriptografia do lado do serviço de mensagens de email para usuários do aplicativo iOS mail

O aplicativo de email iOS não pode descriptografar mensagens protegidas com a criptografia de mensagem do Office 365. Como administrador do Office 365, você pode aplicar a descriptografia do lado do serviço para mensagens entregues ao aplicativo de email iOS. Quando você opta por usar a descriptografia do lado do serviço, o serviço envia uma cópia descriptografada da mensagem para o dispositivo iOS. O dispositivo cliente armazena uma cópia descriptografada da mensagem. A mensagem também mantém informações sobre direitos de uso, mesmo que o aplicativo de email iOS não aplique direitos de uso do lado do cliente ao usuário. O usuário pode copiar ou imprimir a mensagem, mesmo que não tenha originalmente os direitos para fazer isso. No entanto, se o usuário tentar concluir uma ação que requer o servidor de email do Office 365, como encaminhar a mensagem, o servidor não permitirá a ação se o usuário não tiver originalmente o uso do direito de fazer isso. No entanto, os usuários finais podem contornar a restrição de uso "não encaminhar" encaminhando a mensagem de uma conta diferente no aplicativo de email do iOS. Independentemente de você configurar a descriptografia do lado do serviço de email, os anexos a mensagens criptografadas e protegidas por direitos não podem ser exibidos no aplicativo de email do iOS.
  
Se você optar por não permitir que as mensagens descriptografadas sejam enviadas aos usuários do aplicativo de email iOS, os usuários receberão uma mensagem afirmando que eles não têm direitos para exibir a mensagem. Por padrão, a descriptografia do lado do serviço de mensagens de email não está habilitada.
  
Para obter mais informações e para uma visão da experiência do cliente, consulte [Exibir mensagens criptografadas no seu iPhone ou iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>Para gerenciar se os usuários do aplicativo iOS podem exibir mensagens protegidas pela criptografia de mensagens do Office 365
  
1. Use uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização do Office 365 e inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).

2. Execute o cmdlet Set-ActiveSyncOrganizations com o parâmetro AllowRMSSupportForUnenlightenedApps:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   Por exemplo, para configurar o serviço para descriptografar mensagens antes que elas sejam enviadas para aplicativos não habilitados, como o aplicativo de email iOS:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   Ou, para configurar o serviço para não enviar mensagens descriptografadas a aplicativos não habilitados:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> As políticas de caixa de correio individuais (OWA/ActiveSync) substituem essas configurações (ou seja, se-IRMEnabled estiver definida como false dentro da respectiva diretiva de caixa de correio do OWA ou da diretiva de caixa de correio do ActiveSync, essas configurações não serão aplicadas).

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Habilitar a descriptografia do lado do serviço de anexos de email para clientes de email de navegador da Web

Normalmente, quando você usa a criptografia de mensagem do Office 365, os anexos são criptografados automaticamente. Como administrador do Office 365, você pode aplicar a descriptografia do lado do serviço para os anexos de email que os usuários baixem de um navegador da Web.
  
Quando você usa a descriptografia do lado do serviço, o serviço envia uma cópia descriptografada do arquivo ao dispositivo. A mensagem ainda está criptografada. O anexo de email também mantém informações sobre direitos de uso, embora o navegador não aplique direitos de uso do lado do cliente ao usuário. O usuário pode copiar ou imprimir o anexo de email, mesmo que não tenha originalmente os direitos para fazer isso. No entanto, se o usuário tentar concluir uma ação que requer o servidor de email do Office 365, como encaminhar o anexo, o servidor não permitirá a ação se o usuário não tiver originalmente o uso do direito de fazer isso.
  
Independentemente de você configurar a descriptografia do lado do serviço de anexos, os usuários não podem exibir nenhum anexo a emails protegidos e criptografados no aplicativo de email do iOS.
  
Se você optar por não permitir anexos de email descriptografados, que é o padrão, os usuários receberão uma mensagem afirmando que eles não têm direitos para exibir o anexo.
  
Para obter mais informações sobre como o Office 365 implementa a criptografia de emails e anexos de email com a opção somente criptografia, consulte [opção somente criptografia para emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>Para gerenciar se os anexos de email são descriptografados no download a partir de um navegador da Web
  
1. Use uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização do Office 365 e inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).

2. Execute o cmdlet Set-IRMConfiguration com o parâmetro DecryptAttachmentForEncryptOnly:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   Por exemplo, para configurar o serviço para descriptografar anexos de email quando um usuário o baixa de um navegador da Web:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   Para configurar o serviço para deixar anexos de email criptografados como estão no download:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a>Garantir que todos os destinatários externos usem o portal do OME para ler emails criptografados

Você pode usar modelos de identidade visual personalizados para forçar os destinatários a receber emails de conteúdo adicional que os direcionam a ler emails criptografados no portal do OME, em vez de usar o Outlook ou o Outlook na Web. Você pode querer fazer isso se você usar deseja ter maior controle sobre como os destinatários usam o email que eles recebem. Por exemplo, se os destinatários externos exibem email no portal da Web, você pode definir uma data de expiração para o email e pode revogar o email. Esses recursos só são compatíveis com o portal do OME. Você pode usar a opção criptografar e a opção não encaminhar ao criar regras de fluxo de emails.

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a>Usar um modelo personalizado para forçar todos os destinatários externos a usar o portal do OME e emails criptografados

1. Use uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização do Office 365 e inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).

2. Execute o cmdlet New-TransportRule:

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    em que:

   - `mail flow rule name`é o nome que você deseja usar para a nova regra de fluxo de emails.

   - `option name`é `Encrypt` ou `Do Not Forward`.

   - `template name`é o nome que você deu ao modelo de identidade visual personalizado, `OME Configuration`por exemplo.

   Para criptografar todos os emails externos com o modelo "venda de uma semana" e aplicar a opção somente criptografia:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "<OME Configuration>"
   ```

   Para criptografar todos os emails externos com o modelo "configuração do OME" e aplicar a opção não encaminhar:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "<OME Configuration>"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>Personalizar a aparência de mensagens de email e o portal do OME

Para obter informações detalhadas sobre como você pode personalizar o OME para sua organização, confira [Adicionar a marca da sua organização às mensagens criptografadas](add-your-organization-brand-to-encrypted-messages.md).
  
## <a name="disable-the-new-capabilities-for-ome"></a>Desabilitar os novos recursos do OME

Esperamos que ele não venha, mas se você precisar, desabilitar os novos recursos do OME é muito simples. Primeiro, você precisará remover as regras de fluxo de emails que criou que usam os novos recursos do OME. Para obter informações sobre como remover regras de fluxo de email, consulte [Manage Mail Flow Rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx). Em seguida, conclua estas etapas no PowerShell do Exchange Online.
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>Para desabilitar os novos recursos do OME
  
1. Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização do Office 365, inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).

2. Se você habilitou o botão **criptografar** no Outlook na Web, desabilite-o executando o cmdlet Set-IRMConfiguration com o parâmetro SimplifiedClientAccessEnabled. Caso contrário, pule esta etapa.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. Desabilite os novos recursos do OME executando o cmdlet Set-IRMConfiguration com o parâmetro AzureRMSLicensingEnabled definido como false:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
