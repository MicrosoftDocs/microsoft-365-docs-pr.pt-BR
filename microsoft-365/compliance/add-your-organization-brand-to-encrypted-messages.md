---
title: Adicionar sua marca de organização às suas mensagens criptografadas
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Saiba como os administradores globais do Office 365 podem aplicar a identidade visual da sua organização a mensagens de email criptografadas & conteúdo do portal de criptografia.
ms.openlocfilehash: 2898e12ad00d11cd9eb2f3be5d817ef113607e79
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394709"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a>Adicionar a marca da sua organização ao Microsoft 365 para empresas mensagens criptografadas de Criptografia de Mensagens

Você pode aplicar a identidade visual da sua empresa para personalizar a aparência das mensagens de email da sua organização e o portal de criptografia. Você precisará aplicar permissões de administrador global à sua conta de estudante ou trabalho antes de começar. Depois de ter essas permissões, use os cmdlets Get-OMEConfiguration e Set-OMEConfiguration Windows PowerShell para personalizar essas partes de mensagens de email criptografadas:
  
- Texto introdutório

- Disclaimer text

- URL para a declaração de privacidade da sua organização

- Texto no portal OME

- Logotipo que aparece na mensagem de email e no portal OME ou se deve usar um logotipo

- Cor do plano de fundo na mensagem de email e no portal OME

Você também pode reverter para a aparência padrão a qualquer momento.

Se quiser mais controle, use a Criptografia Avançada de Mensagens do Office 365 para criar vários modelos para emails criptografados provenientes da sua organização. Use esses modelos para controlar partes da experiência do usuário final. Por exemplo, especifique se os destinatários podem usar o Google, o Yahoo e as Contas da Microsoft para entrar no portal de criptografia. Use modelos para atender a vários casos de uso, como:

- Departamentos individuais, como Finanças, Vendas e assim por diante.

- Produtos diferentes

- Diferentes regiões geográficas ou países

- Se você deseja permitir que os emails sejam revogados

- Se você deseja que emails enviados para destinatários externos expirem após um número especificado de dias.

Depois de criar os modelos, você pode aplicá-los a emails criptografados usando regras de fluxo de emails do Exchange. Se você tiver a Criptografia de Mensagem Avançada do Office 365, poderá revogar qualquer email que tenha sido marcado usando esses modelos.

## <a name="work-with-ome-branding-templates"></a>Trabalhar com modelos de identidade visual OME

Você pode modificar vários recursos em um modelo de identidade visual. Você pode modificar, mas não remover, o modelo padrão. Se você tiver Criptografia avançada de Mensagem, também poderá criar, modificar e remover modelos personalizados. Use Windows PowerShell para trabalhar com um modelo de identidade visual por vez.

- [Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) - Modificar o modelo de identidade visual padrão ou um modelo de identidade visual personalizado que você criou.
- [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - Crie um novo modelo de identidade visual, somente Criptografia de Mensagem Avançada.
- [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - Remover um modelo de identidade visual personalizado, somente Criptografia de Mensagem Avançada. Não é possível excluir o modelo de identidade visual padrão.
  
## <a name="modify-an-ome-branding-template"></a>Modificar um modelo de identidade visual OME

Use Windows PowerShell para modificar um modelo de identidade visual por vez. Se você tiver Criptografia avançada de Mensagem, também poderá criar, modificar e remover modelos personalizados.

1. Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, inicie uma sessão Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Use o cmdlet Set-OMEConfiguration como descrito em [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) ou use o gráfico e a tabela a seguir para obter orientações.

![Partes de email personalizáveis](../media/ome-template-breakout.png)

|**Para personalizar este recurso da experiência com criptografia**|**Use esses comandos**|
|:-----|:-----|
|Cor da tela de fundo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> **Exemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> Para obter mais informações sobre cores de plano de fundo, consulte a seção [Cores de](#background-color-reference) plano de fundo mais adiante neste artigo.|
|Logotipo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> **Exemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Formatos de arquivo com suporte: .png, .jpg, .bmp ou .tiff  <br/> Tamanho ideal do arquivo de logotipo: menos que 40 KB  <br/> Tamanho ideal da imagem de logotipo: 170 x 70 pixels. Se sua imagem exceder essas dimensões, o serviço resize seu logotipo para exibição no portal. O serviço não modifica o próprio arquivo gráfico. Para obter melhores resultados, use o tamanho ideal.|
|Texto ao lado do nome e endereço de email do remetente|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> **Exemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Texto que aparece no botão "Ler Mensagem"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> **Exemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Texto que aparece abaixo do botão "Ler Mensagem"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> **Exemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|URL do link Política de Privacidade|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> **Exemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|Declaração de isenção de responsabilidade nos emails que contêm a mensagem criptografada|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Exemplo:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|Texto que aparece na parte superior do portal de exibição do email criptografado|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Exemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|Para habilitar ou desabilitar a autenticação com um código de passagem única para este modelo personalizado|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> **Exemplos:** <br/>Para habilitar senhas única para este modelo personalizado <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> Para desabilitar senhas única para este modelo personalizado <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|Para habilitar ou desabilitar a autenticação com as identidades Microsoft, Google ou Yahoo para este modelo personalizado|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> **Exemplos:** <br/>Para habilitar IDs sociais para este modelo personalizado <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> Para desabilitar IDs sociais para este modelo personalizado <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>Criar um modelo de identidade visual OME (Criptografia Avançada de Mensagens)

Se você tiver a Criptografia avançada de Mensagens do Office 365, poderá criar modelos de identidade visual personalizados para sua organização usando o cmdlet [New-OMEConfiguration.](/powershell/module/exchange/new-omeconfiguration) Depois de criar o modelo, modifique o modelo usando o cmdlet Set-OMEConfiguration conforme descrito em [Modify an OME branding template](#modify-an-ome-branding-template). Você pode criar vários modelos.

Para criar um novo modelo de identidade visual personalizado:

1. Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, inicie uma sessão Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Use o cmdlet [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) para criar um novo modelo.

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   Por exemplo,

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>Retornar o modelo de identidade visual padrão para seus valores originais

Para remover todas as modificações do modelo padrão, incluindo personalizações de marca e assim por diante, conclua estas etapas:
  
1. Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, inicie uma sessão Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Use o cmdlet **Set-OMEConfiguration** conforme descrito em [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration). Para remover as personalizações de marca da sua organização dos valores DisclaimerText, EmailText e PortalText, de definir o valor como uma cadeia de caracteres vazia, `""` . Para todos os valores de imagem, como Logo, de definir o valor como  `"$null"` .

   A tabela a seguir descreve os padrões da opção de personalização de criptografia.

   |Para reverter esse recurso da experiência de criptografia para o texto e a imagem padrões|Use esses comandos|
   |:-----|:-----|
   |Texto padrão que vem com mensagens de email criptografadas.  O texto padrão é exibido acima das instruções para a exibição de mensagens criptografadas|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> **Exemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |Declaração de isenção de responsabilidade nos emails que contêm a mensagem criptografada|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> **Exemplo:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |Texto que aparece na parte superior do portal de exibição do email criptografado|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> **Exemplo revertendo de volta para o padrão:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |Logotipo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> **Exemplo revertendo de volta para o padrão:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |Cor da tela de fundo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> **Exemplo revertendo de volta para o padrão:** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>Remover um modelo de identidade visual personalizado (Criptografia Avançada de Mensagens)

Você só pode remover ou excluir modelos de identidade visual que você fez. Não é possível remover o modelo de identidade visual padrão.

Para remover um modelo de identidade visual personalizado:
  
1. Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, inicie uma sessão Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Use o cmdlet **Remove-OMEConfiguration** da seguinte forma:

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   Por exemplo,

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   Para obter mais informações, [consulte Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration).

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>Criar uma regra de fluxo de emails do Exchange que aplique sua identidade visual personalizada a emails criptografados

Depois de modificar o modelo padrão ou criar novos modelos de identidade visual, você pode criar regras de fluxo de emails do Exchange para aplicar sua identidade visual personalizada com base em determinadas condições. Essa regra aplicará a identidade visual personalizada nos seguintes cenários:

- Se o email foi criptografado manualmente pelo usuário final usando o Outlook ou o Outlook na Web, anteriormente o Outlook Web App

- Se o email foi criptografado automaticamente por uma regra de fluxo de emails do Exchange ou política de Prevenção contra Perda de Dados

Para obter informações sobre como criar uma regra de fluxo de emails do Exchange que aplique criptografia, consulte Definir regras de fluxo de emails para criptografar mensagens de [email no Office 365](define-mail-flow-rules-to-encrypt-email.md).

1. Em um navegador da Web, usando uma conta de trabalho ou de estudante que recebeu permissões globais de administrador, entre [no Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Escolha o **painel** Administrador.

3. No Centro de administração do Microsoft 365, escolha **Centros de administração** \> **Exchange**.

4. No EAC, vá para **Regras de fluxo de email** e selecione \>  **Novo** ícone Criar ![ uma nova ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **regra.** Para obter mais informações sobre como usar o EAC, consulte Centro de [administração do Exchange no Exchange Online](/exchange/exchange-admin-center).

5. Em **Nome**, digite um nome para a regra, como Branding for sales department.

6. Em **Aplicar essa regra se**, selecione a condição O **remetente** está localizado dentro da organização e outras condições que você deseja na lista de condições disponíveis. Por exemplo, talvez você queira aplicar um modelo de identidade visual específico a:

   - Todos os emails criptografados enviados de membros do departamento financeiro
   - Emails criptografados enviados com uma determinada palavra-chave, como "External" ou "Partner"
   - Emails criptografados enviados para um domínio específico

7. Em **Fazer o seguinte,** selecione **Modificar a segurança da mensagem** Aplicar identidade visual personalizada a \> **mensagens OME**. Em seguida, no drop-down, selecione um modelo de identidade visual.

8. (Opcional) Você pode configurar a regra de fluxo de emails para aplicar criptografia e identidade visual personalizada. Em **Fazer o seguinte,** selecione **Modificar a** segurança da mensagem e, em seguida, escolha Aplicar a Criptografia de Mensagens do **Office 365 e proteção de direitos.** Selecione um modelo RMS na lista, escolha **Salvar** e, em seguida, escolha **OK**.
  
   A lista de modelos inclui modelos e opções padrão e todos os modelos personalizados que você criar. Se a lista estiver vazia, verifique se você definiu a Criptografia de Mensagens do Office 365 com os novos recursos. Para obter instruções, consulte Configurar novos recursos de Criptografia de Mensagens do [Office 365.](set-up-new-message-encryption-capabilities.md) Para obter informações sobre os modelos padrão, consulte [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates). Para obter informações sobre a **opção Não Encaminhar,** consulte [a opção Não Encaminhar para emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obter informações sobre a **opção criptografar somente,** consulte [Encrypt Only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

   Escolha **adicionar ação** se quiser especificar outra ação.

## <a name="background-color-reference"></a>Referência de cor de plano de fundo

Os nomes de cores que você pode usar para a cor de plano de fundo são limitados. Em vez de um nome de cor, você pode usar um valor de código hexaxa (#RRGGBB). Você pode usar um valor de código hexaxa que corresponda a um nome de cor ou pode usar um valor de código hexaxa personalizado. Certifique-se de colocar o valor do código hexaxa entre aspas (por exemplo, `"#f0f8ff"` ).

Os nomes de cores de plano de fundo disponíveis e seus valores de código hexaxa correspondentes são descritos na tabela a seguir.

|**Nome da cor**|**Código de cor**|
|---|---|
|`aliceblue`|#f0f8ff|
|`antiquewhite`|#faebd7|
|`aqua`|#00ffff|
|`aquamarine`|#7fffd4|
|`azure`|#f0ffff|
|`beige`|#f5f5dc|
|`bisque`|#ffe4c4|
|`black`|#000000|
|`blanchedalmond`|#ffebcd|
|`blue`|#0000ff|
|`blueviolet`|#8a2be2|
|`brown`|#a52a2a|
|`burlywood`|#deb887|
|`cadetblue`|#5f9ea0|
|`chartreuse`|#7fff00|
|`chocolate`|#d2691e|
|`coral`|#ff7f50|
|`cornflowerblue`|#6495ed|
|`cornsilk`|#fff8dc|
|`crimson`|#dc143c|
|`cyan`|#00ffff|
|`darkblue`|#00008b|
|`darkcyan`|#008b8b|
|`darkgoldenrod`|#b8860b|
|`darkgray`|#a9a9a9|
|`darkgreen`|#006400|
|`darkkhaki`|#bdb76b|
|`darkmagenta`|#8b008b|
|`darkolivegreen`|#556b2f|
|`darkorange`|#ff8c00|
|`darkorchid`|#9932cc|
|`darkred`|#8b0000|
|`darksalmon`|#e9967a|
|`darkseagreen`|#8fbc8f|
|`darkslateblue`|#483d8b|
|`darkslategray`|#2f4f4f|
|`darkturquoise`|#00ced1|
|`darkviolet`|#9400d3|
|`deeppink`|#ff1493|
|`deepskyblue`|#00bfff|
|`dimgray`|#696969|
|`dodgerblue`|#1e90ff|
|`firebrick`|#b22222|
|`floralwhite`|#fffaf0|
|`forestgreen`|#228b22|
|`fuchsia`|#ff00ff|
|`gainsboro`|#dcdcdc|
|`ghostwhite`|#f8f8ff|
|`gold`|#ffd700|
|`goldenrod`|#daa520|
|`gray`|#808080|
|`green`|#008000|
|`greenyellow`|#adff2f|
|`honeydew`|#f0fff0|
|`hotpink`|#ff69b4|
|`indianred`|#cd5c5c|
|`indigo`|#4b0082|
|`ivory`|#fffff0|
|`khaki`|#f0e68c|
|`lavender`|#e6e6fa|
|`lavenderblush`|#fff0f5|
|`lawngreen`|#7cfc00|
|`lemonchiffon`|#fffacd|
|`lightblue`|#add8e6|
|`lightcoral`|#f08080|
|`lightcyan`|#e0ffff|
|`lightgoldenrodyellow`|#fafad2|
|`lightgray`|#d3d3d3|
|`lightgrey`|#d3d3d3|
|`lightgreen`|#90ee90|
|`lightpink`|#ffb6c1|
|`lightsalmon`|#ffa07a|
|`lightseagreen`|#20b2aa|
|`lightskyblue`|#87cefa|
|`lightslategray`|#778899|
|`lightsteelblue`|#b0c4de|
|`lightyellow`|#ffffe0|
|`lime`|#00ff00|
|`limegreen`|#32cd32|
|`linen`|#faf0e6|
|`magenta`|#ff00ff|
|`maroon`|#800000|
|`mediumaquamarine`|#66cdaa|
|`mediumblue`|#0000cd|
|`mediumorchid`|#ba55d3|
|`mediumpurple`|#9370db|
|`mediumseagreen`|#3cb371|
|`mediumslateblue`|#7b68ee|
|`mediumspringgreen`|#00fa9a|
|`mediumturquoise`|#48d1cc|
|`mediumvioletred`|#c71585|
|`midnightblue`|#191970|
|`mintcream`|#f5fffa|
|`mistyrose`|#ffe4e1|
|`moccasin`|#ffe4b5|
|`navajowhite`|#ffdead|
|`navy`|#000080|
|`oldlace`|#fdf5e6|
|`olive`|#808000|
|`olivedrab`|#6b8e23|
|`orange`|#ffa500|
|`orangered`|#ff4500|
|`orchid`|#da70d6|
|`palegoldenrod`|#eee8aa|
|`palegreen`|#98fb98|
|`paleturquoise`|#afeeee|
|`palevioletred`|#db7093|
|`papayawhip`|#ffefd5|
|`peachpuff`|#ffdab9|
|`peru`|#cd853f|
|`pink`|#ffc0cb|
|`plum`|#dda0dd|
|`powderblue`|#b0e0e6|
|`purple`|#800080|
|`red`|#ff0000|
|`rosybrown`|#bc8f8f|
|`royalblue`|#4169e1|
|`saddlebrown`|#8b4513|
|`salmon`|#fa8072|
|`sandybrown`|#f4a460|
|`seagreen`|#00ff00|
|`seashell`|#fff5ee|
|`sienna`|#a0522d|
|`silver`|#c0c0c0|
|`skyblue`|#87ceeb|
|`slateblue`|#6a5acd|
|`slategray`|#708090|
|`snow`|#fffafa|
|`springgreen`|#00ff7f|
|`steelblue`|#4682b4|
|`tan`|#d2b48c|
|`teal`|#008080|
|`thistle`|#d8bfd8|
|`tomato`|#ff6347|
|`turquoise`|#40e0d0|
|`violet`|#ee82ee|
|`wheat`|#f5deb3|
|`white`|#ffffff|
|`whitesmoke`|#f5f5f5|
|`yellow`|#ffff00|
|`yellowgreen`|#9acd32|