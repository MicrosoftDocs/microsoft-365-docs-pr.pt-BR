---
title: Adicionar a marca da sua organização às mensagens criptografadas
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Como administrador global do Office 365, você pode aplicar a identidade visual da sua organização às mensagens de email criptografadas da sua organização e ao conteúdo do portal de criptografia.
ms.openlocfilehash: dd08ffad4a50cafd90f2306645e93e623b8076cd
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072358"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>Adicionar a marca da sua organização a suas mensagens criptografadas

Como administrador do Exchange Online ou do Exchange Online Protection, você pode aplicar a identidade visual da sua empresa para personalizar a aparência das mensagens de email de criptografia de mensagem do Office 365 da sua organização e o conteúdo do portal de criptografia. Usando os cmdlets Get-OMEConfiguration e Set-OMEConfiguration do Windows PowerShell, você pode personalizar os seguintes aspectos da experiência de visualização para destinatários de mensagens de email criptografadas:
  
- Texto introdutório do email que contém a mensagem criptografada

- Texto do aviso de isenção de responsabilidade do email que contém a mensagem criptografada

- Texto que aparece no portal OME

- Logotipo que aparece na mensagem de email e no portal do OME

- Cor de plano de fundo na mensagem de email e no portal OME

Você também pode reverter para a aparência padrão a qualquer momento.

 Se quiser mais controle, você pode usar a criptografia de mensagem avançada do Office 365 e criar vários modelos para emails criptografados provenientes da sua organização. Usando esses modelos, você pode controlar mais do que apenas a aparência das mensagens de email, mas também controlar partes da experiência do usuário final. Por exemplo, você pode especificar se os destinatários de emails que têm esse modelo aplicado e quem usam o Google, Yahoo e contas da Microsoft podem usar essas contas para entrar no portal de criptografia de mensagens do Office 365. Você pode usar modelos para cumprir vários casos de uso, como:

- Modelos para cada departamento, como finanças, vendas, etc.

- Modelos para produtos diferentes

- Modelos para diferentes regiões geográficas ou países

- Se você deseja ou não permitir que os emails sejam revogados

- Se você deseja ou não que os emails enviados para destinatários externos expirem após um determinado número de dias.

Depois de criar os modelos, você pode aplicá-los a emails criptografados usando regras de fluxo de email do Exchange. Se você tiver a criptografia de mensagem avançada do Office 365, poderá revogar qualquer email que tenha marcado usando esses modelos.
  
||
|:-----|
|Este artigo faz parte de uma série maior de artigos sobre a criptografia de mensagens do Office 365. Este artigo destina-se a administradores e ITPros. Se você estiver apenas procurando informações sobre como enviar ou receber uma mensagem criptografada, consulte a lista de artigos na [ome (criptografia de mensagens do Office 365)](ome.md) e localize o artigo que melhor atende às suas necessidades.|
||

## <a name="create-branding-templates"></a>Criar modelos de identidade visual

Você cria modelos de identidade visual para sua organização no Windows PowerShell com o cmdlet New-OMEConfiguration. Depois de criar o modelo, você define as partes do modelo usando o cmdlet Set-OMEConfiguration. Você pode criar vários modelos.

![Partes de email personalizáveis](media/ome-template-breakout.png)
  
1. Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização do Office 365, inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, consulte [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Use o cmdlet New-OMEConfiguration para criar um novo modelo.

   ```powershell
   New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
   ```

   For example,

   ```powershell
   New-OMEConfiguration -Identity "Branding template 1"
   ```

3. Defina as personalizações para o modelo que você acabou de definir usando o cmdlet Set-OMEConfiguration conforme descrito em [set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration) ou use a tabela a seguir para orientação.

|**Para personalizar este recurso da experiência com criptografia**|**Use estes comandos**|
|:-----|:-----|
|Cor da tela de fundo|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **Exemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"`|
|Logotipo|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **Exemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Formatos de arquivo com suporte: .png, .jpg, .bmp ou .tiff  <br/> Tamanho ideal do arquivo de logotipo: menos que 40 KB  <br/> Tamanho ideal da imagem de logotipo: 170 pixels x 70 pixels|
|Texto ao lado do nome do remetente e endereço de email|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> **Exemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Texto que aparece no botão "mensagem de leitura"|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> **Exemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Texto que aparece acima abaixo do botão "ler mensagem"|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **Exemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|Declaração de isenção de responsabilidade nos emails que contêm a mensagem criptografada|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Exemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|Texto que aparece na parte superior do portal de exibição do email criptografado|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Exemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|Para habilitar ou desabilitar a autenticação com um código de passagem única para este modelo personalizado|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> **Exemplos:** <br/>Para habilitar as senha de uso único para este modelo personalizado <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> Para desabilitar as senha de uso único para este modelo personalizado <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|Para habilitar ou desabilitar a autenticação com identidades Microsoft, Google ou Yahoo para este modelo personalizado|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> **Exemplos:** <br/>Para habilitar as IDs sociais para este modelo personalizado <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> Para desabilitar as IDs sociais para este modelo personalizado <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="to-remove-brand-customizations-from-the-ome-portal-and-email-messages-encrypted-by-ome"></a>Para remover as personalizações de marca do portal OME e mensagens de email criptografadas por OME
  
1. [Conectar-se ao Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Use o cmdlet **set-OMEConfiguration** conforme descrito em [set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration). Para remover as personalizações da marca da sua organização dos valores DisclaimerText, EmailText e PortalText, defina o valor como uma cadeia de caracteres vazia `""`,. Para todos os valores de imagem, como logotipo, defina o valor `"$null"`como.

**Opções de personalização de criptografia**

**Para reverter esse recurso da experiência de criptografia para o texto e a imagem padrões**|**Use estes comandos**|
|:-----|:-----|
|Texto padrão que acompanha as mensagens de email criptografadas  <br/> O texto padrão é exibido acima das instruções para a exibição de mensagens criptografadas|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **Exemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
|Declaração de isenção de responsabilidade nos emails que contêm a mensagem criptografada|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **Exemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
|Texto que aparece na parte superior do portal de exibição do email criptografado|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **Exemplo reverter para o padrão:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
|Logotipo|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **Exemplo reverter para o padrão:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
|Cor da tela de fundo|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **Exemplo reverter para o padrão:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="create-an-exchange-mail-flow-rule-that-applies-custom-branding-to-encrypted-emails"></a>Criar uma regra de fluxo de email do Exchange que aplica identidade visual personalizada a emails criptografados

Depois de criar um modelo de identidade visual, você pode criar regras de fluxo de email do Exchange para aplicar a identidade visual personalizada com base em determinadas condições. Tal regra aplicará a identidade visual personalizada nos seguintes cenários:

- Se o email foi criptografado manualmente pelo usuário final do Outlook ou do Outlook na Web (anteriormente conhecido como Outlook Web App) clientes

- Se o email foi criptografado automaticamente por uma regra de fluxo de email do Exchange ou pela política de prevenção de perda de dados do Office 365

Para obter informações sobre como criar uma regra de fluxo de email do Exchange que aplica criptografia, consulte [definir regras de fluxo de emails para criptografar mensagens de email no Office 365](define-mail-flow-rules-to-encrypt-email.md).

1. Em um navegador da Web, usando uma conta corporativa ou de estudante que recebeu permissões de administrador global, [entre no Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Escolha o bloco **administrador** .

3. No centro de administração do Microsoft 365, escolha central de **Administração** \> do **Exchange**.

4. No Eat, vá para **regras** de **fluxo** \> de email e selecione **novo** ![novo](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> ícone **criar uma nova regra**. Para obter mais informações sobre como usar o Eat, consulte [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. Em **nome**, digite um nome para a regra, como identidade visual do departamento de vendas.

6. Em **aplicar esta regra se** selecionar uma condição, selecione a condição em que **o remetente está localizado dentro da organização** , bem como outras condições que você deseja na lista de condições disponíveis. Por exemplo, talvez você queira aplicar um modelo de identidade visual específico a:

     - Todos os emails criptografados enviados por membros do departamento financeiro
     - Emails criptografados enviados com uma determinada palavra-chave, como "externo" ou "parceiro"
     - Emails criptografados enviados para um domínio específico

7. Em **faça o seguinte**, selecione **Modificar a segurança** > da mensagem**aplicar a identidade visual personalizada às mensagens do ome**. Em seguida, na lista suspensa, selecione um modelo de identidade visual dos que você criou.

8. Opcion Se você deseja que a regra de fluxo de emails também aplique criptografia além da identidade visual personalizada, em **faça o seguinte**, selecione **Modificar a segurança da mensagem** e, em seguida, escolha **aplicar proteção de mensagens e proteção de direitos do Office 365**. Selecione um modelo do RMS na lista, escolha **salvar**e, em seguida, escolha **OK**.
  
     A lista de modelos inclui todos os modelos e opções padrão, bem como os modelos personalizados que você criou para uso pelo Office 365. Se a lista estiver vazia, verifique se você configurou a criptografia de mensagem do Office 365 com os novos recursos, conforme descrito em [configurar novos recursos de criptografia de mensagens do office 365](set-up-new-message-encryption-capabilities.md). Para obter informações sobre os modelos padrão, consulte [Configurando e Gerenciando modelos para a proteção de informações do Azure](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Para obter informações sobre a opção não **encaminhar** , confira a [opção não encaminhar para emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obter informações sobre a opção **somente criptografia** , confira a [opção criptografar somente para emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

     Você pode escolher **Adicionar ação** se quiser especificar outra ação.
