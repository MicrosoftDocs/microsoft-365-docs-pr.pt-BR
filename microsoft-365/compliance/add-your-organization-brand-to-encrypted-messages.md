---
title: Adicionar a marca da sua organização às mensagens criptografadas
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
ms.openlocfilehash: 56b948fc941da4fb221d929ecd59c5300b135e39
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709493"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a><span data-ttu-id="344e7-103">Adicionar a marca da sua organização às mensagens criptografadas de criptografia de mensagem do Microsoft 365 for Business</span><span class="sxs-lookup"><span data-stu-id="344e7-103">Add your organization's brand to your Microsoft 365 for business Message Encryption encrypted messages</span></span>

<span data-ttu-id="344e7-104">Você pode aplicar a identidade visual da empresa para personalizar a aparência das mensagens de email e do portal de criptografia da sua organização.</span><span class="sxs-lookup"><span data-stu-id="344e7-104">You can apply your company branding to customize the look of your organization's email messages and the encryption portal.</span></span> <span data-ttu-id="344e7-105">Você precisará aplicar permissões de administrador global à sua conta corporativa ou de estudante antes de começar.</span><span class="sxs-lookup"><span data-stu-id="344e7-105">You'll need to apply global administrator permissions to your work or school account before you can get started.</span></span> <span data-ttu-id="344e7-106">Depois de ter essas permissões, use o Get-OMEConfiguration e Set-OMEConfiguration cmdlets do Windows PowerShell para personalizar essas partes de mensagens de email criptografadas:</span><span class="sxs-lookup"><span data-stu-id="344e7-106">Once you have these permissions, use the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets to customize these parts of encrypted email messages:</span></span>
  
- <span data-ttu-id="344e7-107">Texto introdutório</span><span class="sxs-lookup"><span data-stu-id="344e7-107">Introductory text</span></span>

- <span data-ttu-id="344e7-108">Disclaimer text</span><span class="sxs-lookup"><span data-stu-id="344e7-108">Disclaimer text</span></span>

- <span data-ttu-id="344e7-109">URL da declaração de privacidade da sua organização</span><span class="sxs-lookup"><span data-stu-id="344e7-109">URL for Your organization's privacy statement</span></span>

- <span data-ttu-id="344e7-110">Texto no portal OME</span><span class="sxs-lookup"><span data-stu-id="344e7-110">Text in the OME portal</span></span>

- <span data-ttu-id="344e7-111">Logotipo que aparece na mensagem de email e no portal do OME, ou se um logotipo deve ser usado</span><span class="sxs-lookup"><span data-stu-id="344e7-111">Logo that appears in the email message and OME portal, or whether to use a logo at all</span></span>

- <span data-ttu-id="344e7-112">Cor de plano de fundo na mensagem de email e no portal OME</span><span class="sxs-lookup"><span data-stu-id="344e7-112">Background color in the email message and OME portal</span></span>

<span data-ttu-id="344e7-113">Você também pode reverter para a aparência padrão a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="344e7-113">You can also revert back to the default look and feel at any time.</span></span>

<span data-ttu-id="344e7-114">Se você quiser mais controle, use a criptografia de mensagem avançada do Office 365 para criar vários modelos para emails criptografados provenientes da sua organização.</span><span class="sxs-lookup"><span data-stu-id="344e7-114">If you'd like more control, use Office 365 Advanced Message Encryption to create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="344e7-115">Use esses modelos para controlar partes da experiência do usuário final.</span><span class="sxs-lookup"><span data-stu-id="344e7-115">Use these templates to control parts of the end-user experience.</span></span> <span data-ttu-id="344e7-116">Por exemplo, especifique se os destinatários podem usar o Google, o Yahoo e contas da Microsoft para entrar no portal de criptografia.</span><span class="sxs-lookup"><span data-stu-id="344e7-116">For example, specify whether recipients can use Google, Yahoo, and Microsoft Accounts to sign in to the encryption portal.</span></span> <span data-ttu-id="344e7-117">Use modelos para realizar vários casos de uso, como:</span><span class="sxs-lookup"><span data-stu-id="344e7-117">Use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="344e7-118">Departamentos individuais, como finanças, vendas e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="344e7-118">Individual departments, such as Finance, Sales, and so on.</span></span>

- <span data-ttu-id="344e7-119">Produtos diferentes</span><span class="sxs-lookup"><span data-stu-id="344e7-119">Different products</span></span>

- <span data-ttu-id="344e7-120">Diferentes regiões geográficas ou países</span><span class="sxs-lookup"><span data-stu-id="344e7-120">Different geographical regions or countries</span></span>

- <span data-ttu-id="344e7-121">Se você deseja permitir que os emails sejam revogados</span><span class="sxs-lookup"><span data-stu-id="344e7-121">Whether you want to allow emails to be revoked</span></span>

- <span data-ttu-id="344e7-122">Se você deseja que os emails enviados para destinatários externos expirem após um determinado número de dias.</span><span class="sxs-lookup"><span data-stu-id="344e7-122">Whether you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="344e7-123">Depois de criar os modelos, você pode aplicá-los a emails criptografados usando regras de fluxo de email do Exchange.</span><span class="sxs-lookup"><span data-stu-id="344e7-123">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="344e7-124">Se você tiver a criptografia de mensagem avançada do Office 365, poderá revogar qualquer email que tenha marcado usando esses modelos.</span><span class="sxs-lookup"><span data-stu-id="344e7-124">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>

## <a name="work-with-ome-branding-templates"></a><span data-ttu-id="344e7-125">Trabalhar com modelos de identidade visual do OME</span><span class="sxs-lookup"><span data-stu-id="344e7-125">Work with OME branding templates</span></span>

<span data-ttu-id="344e7-126">Você pode modificar vários recursos dentro de um modelo de identidade visual.</span><span class="sxs-lookup"><span data-stu-id="344e7-126">You can modify several features within a branding template.</span></span> <span data-ttu-id="344e7-127">Você pode modificar, mas não remover, o modelo padrão.</span><span class="sxs-lookup"><span data-stu-id="344e7-127">You can modify, but not remove, the default template.</span></span> <span data-ttu-id="344e7-128">Se você tiver criptografia de mensagem avançada, também poderá criar, modificar e remover modelos personalizados.</span><span class="sxs-lookup"><span data-stu-id="344e7-128">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span> <span data-ttu-id="344e7-129">Use o Windows PowerShell para trabalhar com um modelo de identidade visual por vez.</span><span class="sxs-lookup"><span data-stu-id="344e7-129">Use Windows PowerShell to work with one branding template at a time.</span></span>

- <span data-ttu-id="344e7-130">[Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) -modifica o modelo de identidade visual padrão ou um modelo de identidade visual personalizado que você criou.</span><span class="sxs-lookup"><span data-stu-id="344e7-130">[Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) - Modify the default branding template or a custom branding template that you created.</span></span>
- <span data-ttu-id="344e7-131">[New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) -criar um novo modelo de identidade visual, somente criptografia de mensagem avançada.</span><span class="sxs-lookup"><span data-stu-id="344e7-131">[New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) - Create a new branding template, Advanced Message Encryption only.</span></span>
- <span data-ttu-id="344e7-132">[Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) -remove um modelo de identidade visual personalizado, somente criptografia de mensagem avançada.</span><span class="sxs-lookup"><span data-stu-id="344e7-132">[Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) - Remove a custom branding template, Advanced Message Encryption only.</span></span> <span data-ttu-id="344e7-133">Não é possível excluir o modelo de identidade visual padrão.</span><span class="sxs-lookup"><span data-stu-id="344e7-133">You can't delete the default branding template.</span></span>
  
## <a name="modify-an-ome-branding-template"></a><span data-ttu-id="344e7-134">Modificar um modelo de identidade visual do OME</span><span class="sxs-lookup"><span data-stu-id="344e7-134">Modify an OME branding template</span></span>

<span data-ttu-id="344e7-135">Use o Windows PowerShell para modificar um modelo de identidade visual por vez.</span><span class="sxs-lookup"><span data-stu-id="344e7-135">Use Windows PowerShell to modify one branding template at a time.</span></span> <span data-ttu-id="344e7-136">Se você tiver criptografia de mensagem avançada, também poderá criar, modificar e remover modelos personalizados.</span><span class="sxs-lookup"><span data-stu-id="344e7-136">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span>

1. <span data-ttu-id="344e7-137">Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="344e7-137">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="344e7-138">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="344e7-138">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="344e7-139">Use o cmdlet Set-OMEConfiguration conforme descrito em [set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) ou use o gráfico e tabela a seguir para orientação.</span><span class="sxs-lookup"><span data-stu-id="344e7-139">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) or use the following graphic and table for guidance.</span></span>

![Partes de email personalizáveis](../media/ome-template-breakout.png)

|<span data-ttu-id="344e7-141">**Para personalizar este recurso da experiência com criptografia**</span><span class="sxs-lookup"><span data-stu-id="344e7-141">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="344e7-142">**Use estes comandos**</span><span class="sxs-lookup"><span data-stu-id="344e7-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="344e7-143">Cor da tela de fundo</span><span class="sxs-lookup"><span data-stu-id="344e7-143">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> <span data-ttu-id="344e7-144">**Exemplo:**</span><span class="sxs-lookup"><span data-stu-id="344e7-144">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> <span data-ttu-id="344e7-145">Para obter mais informações sobre cores de plano de fundo, consulte a seção [cores de plano de fundo](#background-color-reference) mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="344e7-145">For more information about background colors, see the [Background colors](#background-color-reference) section later in this article.</span></span>|
|<span data-ttu-id="344e7-146">Logotipo</span><span class="sxs-lookup"><span data-stu-id="344e7-146">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> <span data-ttu-id="344e7-147">**Exemplo:**</span><span class="sxs-lookup"><span data-stu-id="344e7-147">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="344e7-148">Formatos de arquivo com suporte: .png, .jpg, .bmp ou .tiff</span><span class="sxs-lookup"><span data-stu-id="344e7-148">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="344e7-149">Tamanho ideal do arquivo de logotipo: menos que 40 KB</span><span class="sxs-lookup"><span data-stu-id="344e7-149">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="344e7-150">Tamanho ideal da imagem do logotipo: 170x70 pixels.</span><span class="sxs-lookup"><span data-stu-id="344e7-150">Optimal size of logo image: 170x70 pixels.</span></span> <span data-ttu-id="344e7-151">Se a imagem exceder essas dimensões, o serviço redimensiona o logotipo para exibição no Portal.</span><span class="sxs-lookup"><span data-stu-id="344e7-151">If your image exceeds these dimensions, the service resizes your logo for display in the portal.</span></span> <span data-ttu-id="344e7-152">O serviço não modifica o próprio arquivo gráfico.</span><span class="sxs-lookup"><span data-stu-id="344e7-152">The service doesn't modify the graphic file itself.</span></span> <span data-ttu-id="344e7-153">Para obter melhores resultados, use o tamanho ideal.</span><span class="sxs-lookup"><span data-stu-id="344e7-153">For best results, use the optimal size.</span></span>|
|<span data-ttu-id="344e7-154">Texto ao lado do nome do remetente e endereço de email</span><span class="sxs-lookup"><span data-stu-id="344e7-154">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="344e7-155">**Exemplo:**</span><span class="sxs-lookup"><span data-stu-id="344e7-155">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="344e7-156">Texto que aparece no botão "mensagem de leitura"</span><span class="sxs-lookup"><span data-stu-id="344e7-156">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="344e7-157">**Exemplo:**</span><span class="sxs-lookup"><span data-stu-id="344e7-157">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="344e7-158">Texto que aparece abaixo do botão "ler mensagem"</span><span class="sxs-lookup"><span data-stu-id="344e7-158">Text that appears below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="344e7-159">**Exemplo:**</span><span class="sxs-lookup"><span data-stu-id="344e7-159">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="344e7-160">URL do link da política de privacidade</span><span class="sxs-lookup"><span data-stu-id="344e7-160">URL for the Privacy Statement link</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> <span data-ttu-id="344e7-161">**Exemplo:**</span><span class="sxs-lookup"><span data-stu-id="344e7-161">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|<span data-ttu-id="344e7-162">Declaração de isenção de responsabilidade nos emails que contêm a mensagem criptografada</span><span class="sxs-lookup"><span data-stu-id="344e7-162">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="344e7-163">**Exemplo:**</span><span class="sxs-lookup"><span data-stu-id="344e7-163">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="344e7-164">Texto que aparece na parte superior do portal de exibição do email criptografado</span><span class="sxs-lookup"><span data-stu-id="344e7-164">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="344e7-165">**Exemplo:**</span><span class="sxs-lookup"><span data-stu-id="344e7-165">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="344e7-166">Para habilitar ou desabilitar a autenticação com um código de passagem única para este modelo personalizado</span><span class="sxs-lookup"><span data-stu-id="344e7-166">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="344e7-167">**Exemplos:**</span><span class="sxs-lookup"><span data-stu-id="344e7-167">**Examples:**</span></span> <br/><span data-ttu-id="344e7-168">Para habilitar as senha de uso único para este modelo personalizado</span><span class="sxs-lookup"><span data-stu-id="344e7-168">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="344e7-169">Para desabilitar as senha de uso único para este modelo personalizado</span><span class="sxs-lookup"><span data-stu-id="344e7-169">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="344e7-170">Para habilitar ou desabilitar a autenticação com identidades Microsoft, Google ou Yahoo para este modelo personalizado</span><span class="sxs-lookup"><span data-stu-id="344e7-170">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="344e7-171">**Exemplos:**</span><span class="sxs-lookup"><span data-stu-id="344e7-171">**Examples:**</span></span> <br/><span data-ttu-id="344e7-172">Para habilitar as IDs sociais para este modelo personalizado</span><span class="sxs-lookup"><span data-stu-id="344e7-172">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="344e7-173">Para desabilitar as IDs sociais para este modelo personalizado</span><span class="sxs-lookup"><span data-stu-id="344e7-173">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a><span data-ttu-id="344e7-174">Criar um modelo de identidade visual do OME (criptografia de mensagem avançada)</span><span class="sxs-lookup"><span data-stu-id="344e7-174">Create an OME branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="344e7-175">Se você tiver a criptografia de mensagem avançada do Office 365, poderá criar modelos de identidade visual personalizados para sua organização usando o cmdlet [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) .</span><span class="sxs-lookup"><span data-stu-id="344e7-175">If you have Office 365 Advanced Message Encryption, you can create custom branding templates for your organization by using the [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) cmdlet.</span></span> <span data-ttu-id="344e7-176">Depois de criar o modelo, modifique o modelo usando o cmdlet Set-OMEConfiguration conforme descrito em [Modify an ome branding template](#modify-an-ome-branding-template).</span><span class="sxs-lookup"><span data-stu-id="344e7-176">Once you've created the template, you modify the template by using the Set-OMEConfiguration cmdlet as described in [Modify an OME branding template](#modify-an-ome-branding-template).</span></span> <span data-ttu-id="344e7-177">Você pode criar vários modelos.</span><span class="sxs-lookup"><span data-stu-id="344e7-177">You can create multiple templates.</span></span>

<span data-ttu-id="344e7-178">Para criar um novo modelo de identidade visual personalizado:</span><span class="sxs-lookup"><span data-stu-id="344e7-178">To create a new custom branding template:</span></span>

1. <span data-ttu-id="344e7-179">Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="344e7-179">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="344e7-180">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="344e7-180">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="344e7-181">Use o cmdlet [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) para criar um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="344e7-181">Use the [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   <span data-ttu-id="344e7-182">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="344e7-182">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a><span data-ttu-id="344e7-183">Retornar o modelo de identidade visual padrão para seus valores originais</span><span class="sxs-lookup"><span data-stu-id="344e7-183">Return the default branding template to its original values</span></span>

<span data-ttu-id="344e7-184">Para remover todas as modificações do modelo padrão, incluindo as personalizações de marca e assim por diante, conclua estas etapas:</span><span class="sxs-lookup"><span data-stu-id="344e7-184">To remove all modifications from the default template, including brand customizations, and so on, complete these steps:</span></span>
  
1. <span data-ttu-id="344e7-185">Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="344e7-185">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="344e7-186">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="344e7-186">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="344e7-187">Use o cmdlet **set-OMEConfiguration** conforme descrito em [set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration).</span><span class="sxs-lookup"><span data-stu-id="344e7-187">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration).</span></span> <span data-ttu-id="344e7-188">Para remover as personalizações da marca da sua organização dos valores DisclaimerText, EmailText e PortalText, defina o valor como uma cadeia de caracteres vazia, `""` .</span><span class="sxs-lookup"><span data-stu-id="344e7-188">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string, `""`.</span></span> <span data-ttu-id="344e7-189">Para todos os valores de imagem, como logotipo, defina o valor como  `"$null"` .</span><span class="sxs-lookup"><span data-stu-id="344e7-189">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

   <span data-ttu-id="344e7-190">A tabela a seguir descreve os padrões de opção de personalização de criptografia.</span><span class="sxs-lookup"><span data-stu-id="344e7-190">The following table describes the encryption customization option defaults.</span></span>

   <span data-ttu-id="344e7-191">**Para reverter esse recurso da experiência de criptografia para o texto e a imagem padrões**</span><span class="sxs-lookup"><span data-stu-id="344e7-191">**To revert this feature of the encryption experience back to the default text and image**</span></span>|<span data-ttu-id="344e7-192">**Use estes comandos**</span><span class="sxs-lookup"><span data-stu-id="344e7-192">**Use these commands**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="344e7-193">Texto padrão que vem com mensagens de email criptografadas</span><span class="sxs-lookup"><span data-stu-id="344e7-193">Default text that comes with encrypted email messages</span></span>  <br/> <span data-ttu-id="344e7-194">O texto padrão é exibido acima das instruções para a exibição de mensagens criptografadas</span><span class="sxs-lookup"><span data-stu-id="344e7-194">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> <span data-ttu-id="344e7-195">**Exemplo:**</span><span class="sxs-lookup"><span data-stu-id="344e7-195">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |<span data-ttu-id="344e7-196">Declaração de isenção de responsabilidade nos emails que contêm a mensagem criptografada</span><span class="sxs-lookup"><span data-stu-id="344e7-196">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> <span data-ttu-id="344e7-197">**Exemplo:**</span><span class="sxs-lookup"><span data-stu-id="344e7-197">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |<span data-ttu-id="344e7-198">Texto que aparece na parte superior do portal de exibição do email criptografado</span><span class="sxs-lookup"><span data-stu-id="344e7-198">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> <span data-ttu-id="344e7-199">**Exemplo reverter para o padrão:**</span><span class="sxs-lookup"><span data-stu-id="344e7-199">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |<span data-ttu-id="344e7-200">Logotipo</span><span class="sxs-lookup"><span data-stu-id="344e7-200">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> <span data-ttu-id="344e7-201">**Exemplo reverter para o padrão:**</span><span class="sxs-lookup"><span data-stu-id="344e7-201">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |<span data-ttu-id="344e7-202">Cor da tela de fundo</span><span class="sxs-lookup"><span data-stu-id="344e7-202">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> <span data-ttu-id="344e7-203">**Exemplo reverter para o padrão:**</span><span class="sxs-lookup"><span data-stu-id="344e7-203">**Example reverting back to default:**</span></span> <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a><span data-ttu-id="344e7-204">Remover um modelo de identidade visual personalizado (criptografia de mensagem avançada)</span><span class="sxs-lookup"><span data-stu-id="344e7-204">Remove a custom branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="344e7-205">Você só pode remover ou excluir modelos de identidade visual que você fez.</span><span class="sxs-lookup"><span data-stu-id="344e7-205">You can only remove or delete branding templates that you've made.</span></span> <span data-ttu-id="344e7-206">Não é possível remover o modelo de identidade visual padrão.</span><span class="sxs-lookup"><span data-stu-id="344e7-206">You can't remove the default branding template.</span></span>

<span data-ttu-id="344e7-207">Para remover um modelo de identidade visual personalizado:</span><span class="sxs-lookup"><span data-stu-id="344e7-207">To remove a custom branding template:</span></span>
  
1. <span data-ttu-id="344e7-208">Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="344e7-208">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="344e7-209">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="344e7-209">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="344e7-210">Use o cmdlet **Remove-OMEConfiguration** da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="344e7-210">Use the **Remove-OMEConfiguration** cmdlet as follows:</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   <span data-ttu-id="344e7-211">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="344e7-211">For example,</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   <span data-ttu-id="344e7-212">Para obter mais informações, consulte [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration).</span><span class="sxs-lookup"><span data-stu-id="344e7-212">For more information, see [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration).</span></span>

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a><span data-ttu-id="344e7-213">Criar uma regra de fluxo de email do Exchange que aplica sua identidade visual personalizada a emails criptografados</span><span class="sxs-lookup"><span data-stu-id="344e7-213">Create an Exchange mail flow rule that applies your custom branding to encrypted emails</span></span>

<span data-ttu-id="344e7-214">Depois de modificar o modelo padrão ou criar novos modelos de identidade visual, você pode criar regras de fluxo de email do Exchange para aplicar a identidade visual personalizada com base em determinadas condições.</span><span class="sxs-lookup"><span data-stu-id="344e7-214">After you've either modified the default template or created new branding templates, you can create Exchange mail flow rules to apply your custom branding based on certain conditions.</span></span> <span data-ttu-id="344e7-215">Tal regra aplicará a identidade visual personalizada nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="344e7-215">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="344e7-216">Se o email foi criptografado manualmente pelo usuário final usando o Outlook ou o Outlook na Web, anteriormente, o Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="344e7-216">If the email was manually encrypted by the end user using Outlook or Outlook on the web, formerly Outlook Web App</span></span>

- <span data-ttu-id="344e7-217">Se o email foi criptografado automaticamente por uma regra de fluxo de email do Exchange ou pela política de prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="344e7-217">If the email was automatically encrypted by an Exchange mail flow rule or Data Loss Prevention policy</span></span>

<span data-ttu-id="344e7-218">Para obter informações sobre como criar uma regra de fluxo de email do Exchange que aplica criptografia, consulte [definir regras de fluxo de emails para criptografar mensagens de email no Office 365](define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="344e7-218">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="344e7-219">Em um navegador da Web, usando uma conta corporativa ou de estudante que recebeu permissões de administrador global, [entre no Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span><span class="sxs-lookup"><span data-stu-id="344e7-219">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="344e7-220">Escolha o bloco **administrador** .</span><span class="sxs-lookup"><span data-stu-id="344e7-220">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="344e7-221">No centro de administração do Microsoft 365, escolha central de **Administração** do \> **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="344e7-221">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="344e7-222">No Eat, vá para regras de **fluxo de email** \>  e selecione **novo** ![ novo ícone ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **criar uma nova regra**.</span><span class="sxs-lookup"><span data-stu-id="344e7-222">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="344e7-223">Para obter mais informações sobre como usar o Eat, consulte [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="344e7-223">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="344e7-224">Em **nome**, digite um nome para a regra, como identidade visual do departamento de vendas.</span><span class="sxs-lookup"><span data-stu-id="344e7-224">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="344e7-225">Em **aplicar esta regra se**, selecione a condição que **o remetente está localizado dentro da organização** e outras condições que você deseja na lista de condições disponíveis.</span><span class="sxs-lookup"><span data-stu-id="344e7-225">In **Apply this rule if**, select the condition **The sender is located inside the organization** and other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="344e7-226">Por exemplo, talvez você queira aplicar um modelo de identidade visual específico a:</span><span class="sxs-lookup"><span data-stu-id="344e7-226">For example, you might want to apply a particular branding template to:</span></span>

   - <span data-ttu-id="344e7-227">Todos os emails criptografados enviados por membros do departamento financeiro</span><span class="sxs-lookup"><span data-stu-id="344e7-227">All encrypted emails sent from members of the finance department</span></span>
   - <span data-ttu-id="344e7-228">Emails criptografados enviados com uma determinada palavra-chave, como "externo" ou "parceiro"</span><span class="sxs-lookup"><span data-stu-id="344e7-228">Encrypted emails sent with a certain keyword such as "External" or "Partner"</span></span>
   - <span data-ttu-id="344e7-229">Emails criptografados enviados para um domínio específico</span><span class="sxs-lookup"><span data-stu-id="344e7-229">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="344e7-230">Em **faça o seguinte**, selecione **Modificar a segurança da mensagem** \> **aplicar a identidade visual personalizada às mensagens do ome**.</span><span class="sxs-lookup"><span data-stu-id="344e7-230">From **Do the following**, select **Modify the message security** \> **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="344e7-231">Em seguida, na lista suspensa, selecione um modelo de identidade visual.</span><span class="sxs-lookup"><span data-stu-id="344e7-231">Next, from the drop-down, select a branding template.</span></span>

8. <span data-ttu-id="344e7-232">Opcion Você pode configurar a regra de fluxo de emails para aplicar criptografia e identidade visual personalizada.</span><span class="sxs-lookup"><span data-stu-id="344e7-232">(Optional) You can configure the mail flow rule to apply encryption and custom branding.</span></span> <span data-ttu-id="344e7-233">Em **faça o seguinte**, selecione **Modificar a segurança da mensagem** e, em seguida, escolha **aplicar a criptografia de mensagem do Office 365 e proteção de direitos**.</span><span class="sxs-lookup"><span data-stu-id="344e7-233">From **Do the following**, select **Modify the message security**, and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="344e7-234">Selecione um modelo do RMS na lista, escolha **salvar** e, em seguida, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="344e7-234">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
   <span data-ttu-id="344e7-235">A lista de modelos inclui opções e modelos padrão e todos os modelos personalizados que você criar.</span><span class="sxs-lookup"><span data-stu-id="344e7-235">The list of templates includes default templates and options and any custom templates you create.</span></span> <span data-ttu-id="344e7-236">Se a lista estiver vazia, verifique se você configurou a criptografia de mensagem do Office 365 com os novos recursos.</span><span class="sxs-lookup"><span data-stu-id="344e7-236">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities.</span></span> <span data-ttu-id="344e7-237">Para obter instruções, consulte [configurar novos recursos de criptografia de mensagem do Office 365](set-up-new-message-encryption-capabilities.md).</span><span class="sxs-lookup"><span data-stu-id="344e7-237">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="344e7-238">Para obter informações sobre os modelos padrão, consulte [Configurando e Gerenciando modelos para a proteção de informações do Azure](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span><span class="sxs-lookup"><span data-stu-id="344e7-238">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="344e7-239">Para obter informações sobre a opção não **encaminhar** , confira a [opção não encaminhar para emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span><span class="sxs-lookup"><span data-stu-id="344e7-239">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="344e7-240">Para obter informações sobre a opção **somente criptografia** , confira a [opção criptografar somente para emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span><span class="sxs-lookup"><span data-stu-id="344e7-240">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="344e7-241">Escolha **Adicionar ação** se você quiser especificar outra ação.</span><span class="sxs-lookup"><span data-stu-id="344e7-241">Choose **add action** if you want to specify another action.</span></span>

## <a name="background-color-reference"></a><span data-ttu-id="344e7-242">Referência de cor de fundo</span><span class="sxs-lookup"><span data-stu-id="344e7-242">Background color reference</span></span>

<span data-ttu-id="344e7-243">Os nomes de cores que você pode usar para a cor de plano de fundo são limitados.</span><span class="sxs-lookup"><span data-stu-id="344e7-243">The color names that you can use for the background color are limited.</span></span> <span data-ttu-id="344e7-244">Em vez de um nome de cor, você pode usar um valor de código HEX (#RRGGBB).</span><span class="sxs-lookup"><span data-stu-id="344e7-244">Instead of a color name, you can use a hex code value (#RRGGBB).</span></span> <span data-ttu-id="344e7-245">Você pode usar um valor de código Hex que corresponde a um nome de cor ou pode usar um valor de código HEX personalizado.</span><span class="sxs-lookup"><span data-stu-id="344e7-245">You can use a hex code value that corresponds to a color name, or you can use a custom hex code value.</span></span> <span data-ttu-id="344e7-246">Certifique-se de colocar o valor do código hex entre aspas (por exemplo, `"#f0f8ff"` ).</span><span class="sxs-lookup"><span data-stu-id="344e7-246">Be sure to enclose the hex code value in quotation marks (for example, `"#f0f8ff"`).</span></span>

<span data-ttu-id="344e7-247">Os nomes de cor de plano de fundo disponíveis e seus valores de código hex correspondentes são descritos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="344e7-247">The available background color names and their corresponding hex code values are described in the following table.</span></span>

|<span data-ttu-id="344e7-248">**Nome da cor**</span><span class="sxs-lookup"><span data-stu-id="344e7-248">**Color name**</span></span>|<span data-ttu-id="344e7-249">**Código de cor**</span><span class="sxs-lookup"><span data-stu-id="344e7-249">**Color code**</span></span>|
|---|---|
|`aliceblue`|<span data-ttu-id="344e7-250">#f0f8ff</span><span class="sxs-lookup"><span data-stu-id="344e7-250">#f0f8ff</span></span>|
|`antiquewhite`|<span data-ttu-id="344e7-251">#faebd7</span><span class="sxs-lookup"><span data-stu-id="344e7-251">#faebd7</span></span>|
|`aqua`|<span data-ttu-id="344e7-252">#00ffff</span><span class="sxs-lookup"><span data-stu-id="344e7-252">#00ffff</span></span>|
|`aquamarine`|<span data-ttu-id="344e7-253">#7fffd4</span><span class="sxs-lookup"><span data-stu-id="344e7-253">#7fffd4</span></span>|
|`azure`|<span data-ttu-id="344e7-254">#f0ffff</span><span class="sxs-lookup"><span data-stu-id="344e7-254">#f0ffff</span></span>|
|`beige`|<span data-ttu-id="344e7-255">#f5f5dc</span><span class="sxs-lookup"><span data-stu-id="344e7-255">#f5f5dc</span></span>|
|`bisque`|<span data-ttu-id="344e7-256">#ffe4c4</span><span class="sxs-lookup"><span data-stu-id="344e7-256">#ffe4c4</span></span>|
|`black`|<span data-ttu-id="344e7-257">#000000</span><span class="sxs-lookup"><span data-stu-id="344e7-257">#000000</span></span>|
|`blanchedalmond`|<span data-ttu-id="344e7-258">#ffebcd</span><span class="sxs-lookup"><span data-stu-id="344e7-258">#ffebcd</span></span>|
|`blue`|<span data-ttu-id="344e7-259">#0000ff</span><span class="sxs-lookup"><span data-stu-id="344e7-259">#0000ff</span></span>|
|`blueviolet`|<span data-ttu-id="344e7-260">#8a2be2</span><span class="sxs-lookup"><span data-stu-id="344e7-260">#8a2be2</span></span>|
|`brown`|<span data-ttu-id="344e7-261">#a52a2a</span><span class="sxs-lookup"><span data-stu-id="344e7-261">#a52a2a</span></span>|
|`burlywood`|<span data-ttu-id="344e7-262">#deb887</span><span class="sxs-lookup"><span data-stu-id="344e7-262">#deb887</span></span>|
|`cadetblue`|<span data-ttu-id="344e7-263">#5f9ea0</span><span class="sxs-lookup"><span data-stu-id="344e7-263">#5f9ea0</span></span>|
|`chartreuse`|<span data-ttu-id="344e7-264">#7fff00</span><span class="sxs-lookup"><span data-stu-id="344e7-264">#7fff00</span></span>|
|`chocolate`|<span data-ttu-id="344e7-265">#d2691e</span><span class="sxs-lookup"><span data-stu-id="344e7-265">#d2691e</span></span>|
|`coral`|<span data-ttu-id="344e7-266">#ff7f50</span><span class="sxs-lookup"><span data-stu-id="344e7-266">#ff7f50</span></span>|
|`cornflowerblue`|<span data-ttu-id="344e7-267">#6495ed</span><span class="sxs-lookup"><span data-stu-id="344e7-267">#6495ed</span></span>|
|`cornsilk`|<span data-ttu-id="344e7-268">#fff8dc</span><span class="sxs-lookup"><span data-stu-id="344e7-268">#fff8dc</span></span>|
|`crimson`|<span data-ttu-id="344e7-269">#dc143c</span><span class="sxs-lookup"><span data-stu-id="344e7-269">#dc143c</span></span>|
|`cyan`|<span data-ttu-id="344e7-270">#00ffff</span><span class="sxs-lookup"><span data-stu-id="344e7-270">#00ffff</span></span>|
|`darkblue`|<span data-ttu-id="344e7-271">#00008b</span><span class="sxs-lookup"><span data-stu-id="344e7-271">#00008b</span></span>|
|`darkcyan`|<span data-ttu-id="344e7-272">#008b8b</span><span class="sxs-lookup"><span data-stu-id="344e7-272">#008b8b</span></span>|
|`darkgoldenrod`|<span data-ttu-id="344e7-273">#b8860b</span><span class="sxs-lookup"><span data-stu-id="344e7-273">#b8860b</span></span>|
|`darkgray`|<span data-ttu-id="344e7-274">#a9a9a9</span><span class="sxs-lookup"><span data-stu-id="344e7-274">#a9a9a9</span></span>|
|`darkgreen`|<span data-ttu-id="344e7-275">#006400</span><span class="sxs-lookup"><span data-stu-id="344e7-275">#006400</span></span>|
|`darkkhaki`|<span data-ttu-id="344e7-276">#bdb76b</span><span class="sxs-lookup"><span data-stu-id="344e7-276">#bdb76b</span></span>|
|`darkmagenta`|<span data-ttu-id="344e7-277">#8b008b</span><span class="sxs-lookup"><span data-stu-id="344e7-277">#8b008b</span></span>|
|`darkolivegreen`|<span data-ttu-id="344e7-278">#556b2f</span><span class="sxs-lookup"><span data-stu-id="344e7-278">#556b2f</span></span>|
|`darkorange`|<span data-ttu-id="344e7-279">#ff8c00</span><span class="sxs-lookup"><span data-stu-id="344e7-279">#ff8c00</span></span>|
|`darkorchid`|<span data-ttu-id="344e7-280">#9932cc</span><span class="sxs-lookup"><span data-stu-id="344e7-280">#9932cc</span></span>|
|`darkred`|<span data-ttu-id="344e7-281">#8b0000</span><span class="sxs-lookup"><span data-stu-id="344e7-281">#8b0000</span></span>|
|`darksalmon`|<span data-ttu-id="344e7-282">#e9967a</span><span class="sxs-lookup"><span data-stu-id="344e7-282">#e9967a</span></span>|
|`darkseagreen`|<span data-ttu-id="344e7-283">#8fbc8f</span><span class="sxs-lookup"><span data-stu-id="344e7-283">#8fbc8f</span></span>|
|`darkslateblue`|<span data-ttu-id="344e7-284">#483d8b</span><span class="sxs-lookup"><span data-stu-id="344e7-284">#483d8b</span></span>|
|`darkslategray`|<span data-ttu-id="344e7-285">#2f4f4f</span><span class="sxs-lookup"><span data-stu-id="344e7-285">#2f4f4f</span></span>|
|`darkturquoise`|<span data-ttu-id="344e7-286">#00ced1</span><span class="sxs-lookup"><span data-stu-id="344e7-286">#00ced1</span></span>|
|`darkviolet`|<span data-ttu-id="344e7-287">#9400d3</span><span class="sxs-lookup"><span data-stu-id="344e7-287">#9400d3</span></span>|
|`deeppink`|<span data-ttu-id="344e7-288">#ff1493</span><span class="sxs-lookup"><span data-stu-id="344e7-288">#ff1493</span></span>|
|`deepskyblue`|<span data-ttu-id="344e7-289">#00bfff</span><span class="sxs-lookup"><span data-stu-id="344e7-289">#00bfff</span></span>|
|`dimgray`|<span data-ttu-id="344e7-290">#696969</span><span class="sxs-lookup"><span data-stu-id="344e7-290">#696969</span></span>|
|`dodgerblue`|<span data-ttu-id="344e7-291">#1e90ff</span><span class="sxs-lookup"><span data-stu-id="344e7-291">#1e90ff</span></span>|
|`firebrick`|<span data-ttu-id="344e7-292">#b22222</span><span class="sxs-lookup"><span data-stu-id="344e7-292">#b22222</span></span>|
|`floralwhite`|<span data-ttu-id="344e7-293">#fffaf0</span><span class="sxs-lookup"><span data-stu-id="344e7-293">#fffaf0</span></span>|
|`forestgreen`|<span data-ttu-id="344e7-294">#228b22</span><span class="sxs-lookup"><span data-stu-id="344e7-294">#228b22</span></span>|
|`fuchsia`|<span data-ttu-id="344e7-295">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="344e7-295">#ff00ff</span></span>|
|`gainsboro`|<span data-ttu-id="344e7-296">#dcdcdc</span><span class="sxs-lookup"><span data-stu-id="344e7-296">#dcdcdc</span></span>|
|`ghostwhite`|<span data-ttu-id="344e7-297">#f8f8ff</span><span class="sxs-lookup"><span data-stu-id="344e7-297">#f8f8ff</span></span>|
|`gold`|<span data-ttu-id="344e7-298">#ffd700</span><span class="sxs-lookup"><span data-stu-id="344e7-298">#ffd700</span></span>|
|`goldenrod`|<span data-ttu-id="344e7-299">#daa520</span><span class="sxs-lookup"><span data-stu-id="344e7-299">#daa520</span></span>|
|`gray`|<span data-ttu-id="344e7-300">#808080</span><span class="sxs-lookup"><span data-stu-id="344e7-300">#808080</span></span>|
|`green`|<span data-ttu-id="344e7-301">#008000</span><span class="sxs-lookup"><span data-stu-id="344e7-301">#008000</span></span>|
|`greenyellow`|<span data-ttu-id="344e7-302">#adff2f</span><span class="sxs-lookup"><span data-stu-id="344e7-302">#adff2f</span></span>|
|`honeydew`|<span data-ttu-id="344e7-303">#f0fff0</span><span class="sxs-lookup"><span data-stu-id="344e7-303">#f0fff0</span></span>|
|`hotpink`|<span data-ttu-id="344e7-304">#ff69b4</span><span class="sxs-lookup"><span data-stu-id="344e7-304">#ff69b4</span></span>|
|`indianred`|<span data-ttu-id="344e7-305">#cd5c5c</span><span class="sxs-lookup"><span data-stu-id="344e7-305">#cd5c5c</span></span>|
|`indigo`|<span data-ttu-id="344e7-306">#4b0082</span><span class="sxs-lookup"><span data-stu-id="344e7-306">#4b0082</span></span>|
|`ivory`|<span data-ttu-id="344e7-307">#fffff0</span><span class="sxs-lookup"><span data-stu-id="344e7-307">#fffff0</span></span>|
|`khaki`|<span data-ttu-id="344e7-308">#f0e68c</span><span class="sxs-lookup"><span data-stu-id="344e7-308">#f0e68c</span></span>|
|`lavender`|<span data-ttu-id="344e7-309">#e6e6fa</span><span class="sxs-lookup"><span data-stu-id="344e7-309">#e6e6fa</span></span>|
|`lavenderblush`|<span data-ttu-id="344e7-310">#fff0f5</span><span class="sxs-lookup"><span data-stu-id="344e7-310">#fff0f5</span></span>|
|`lawngreen`|<span data-ttu-id="344e7-311">#7cfc00</span><span class="sxs-lookup"><span data-stu-id="344e7-311">#7cfc00</span></span>|
|`lemonchiffon`|<span data-ttu-id="344e7-312">#fffacd</span><span class="sxs-lookup"><span data-stu-id="344e7-312">#fffacd</span></span>|
|`lightblue`|<span data-ttu-id="344e7-313">#add8e6</span><span class="sxs-lookup"><span data-stu-id="344e7-313">#add8e6</span></span>|
|`lightcoral`|<span data-ttu-id="344e7-314">#f08080</span><span class="sxs-lookup"><span data-stu-id="344e7-314">#f08080</span></span>|
|`lightcyan`|<span data-ttu-id="344e7-315">#e0ffff</span><span class="sxs-lookup"><span data-stu-id="344e7-315">#e0ffff</span></span>|
|`lightgoldenrodyellow`|<span data-ttu-id="344e7-316">#fafad2</span><span class="sxs-lookup"><span data-stu-id="344e7-316">#fafad2</span></span>|
|`lightgray`|<span data-ttu-id="344e7-317">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="344e7-317">#d3d3d3</span></span>|
|`lightgrey`|<span data-ttu-id="344e7-318">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="344e7-318">#d3d3d3</span></span>|
|`lightgreen`|<span data-ttu-id="344e7-319">#90ee90</span><span class="sxs-lookup"><span data-stu-id="344e7-319">#90ee90</span></span>|
|`lightpink`|<span data-ttu-id="344e7-320">#ffb6c1</span><span class="sxs-lookup"><span data-stu-id="344e7-320">#ffb6c1</span></span>|
|`lightsalmon`|<span data-ttu-id="344e7-321">#ffa07a</span><span class="sxs-lookup"><span data-stu-id="344e7-321">#ffa07a</span></span>|
|`lightseagreen`|<span data-ttu-id="344e7-322">#20b2aa</span><span class="sxs-lookup"><span data-stu-id="344e7-322">#20b2aa</span></span>|
|`lightskyblue`|<span data-ttu-id="344e7-323">#87cefa</span><span class="sxs-lookup"><span data-stu-id="344e7-323">#87cefa</span></span>|
|`lightslategray`|<span data-ttu-id="344e7-324">#778899</span><span class="sxs-lookup"><span data-stu-id="344e7-324">#778899</span></span>|
|`lightsteelblue`|<span data-ttu-id="344e7-325">#b0c4de</span><span class="sxs-lookup"><span data-stu-id="344e7-325">#b0c4de</span></span>|
|`lightyellow`|<span data-ttu-id="344e7-326">#ffffe0</span><span class="sxs-lookup"><span data-stu-id="344e7-326">#ffffe0</span></span>|
|`lime`|<span data-ttu-id="344e7-327">#00ff00</span><span class="sxs-lookup"><span data-stu-id="344e7-327">#00ff00</span></span>|
|`limegreen`|<span data-ttu-id="344e7-328">#32cd32</span><span class="sxs-lookup"><span data-stu-id="344e7-328">#32cd32</span></span>|
|`linen`|<span data-ttu-id="344e7-329">#faf0e6</span><span class="sxs-lookup"><span data-stu-id="344e7-329">#faf0e6</span></span>|
|`magenta`|<span data-ttu-id="344e7-330">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="344e7-330">#ff00ff</span></span>|
|`maroon`|<span data-ttu-id="344e7-331">#800000</span><span class="sxs-lookup"><span data-stu-id="344e7-331">#800000</span></span>|
|`mediumaquamarine`|<span data-ttu-id="344e7-332">#66cdaa</span><span class="sxs-lookup"><span data-stu-id="344e7-332">#66cdaa</span></span>|
|`mediumblue`|<span data-ttu-id="344e7-333">#0000cd</span><span class="sxs-lookup"><span data-stu-id="344e7-333">#0000cd</span></span>|
|`mediumorchid`|<span data-ttu-id="344e7-334">#ba55d3</span><span class="sxs-lookup"><span data-stu-id="344e7-334">#ba55d3</span></span>|
|`mediumpurple`|<span data-ttu-id="344e7-335">#9370db</span><span class="sxs-lookup"><span data-stu-id="344e7-335">#9370db</span></span>|
|`mediumseagreen`|<span data-ttu-id="344e7-336">#3cb371</span><span class="sxs-lookup"><span data-stu-id="344e7-336">#3cb371</span></span>|
|`mediumslateblue`|<span data-ttu-id="344e7-337">#7b68ee</span><span class="sxs-lookup"><span data-stu-id="344e7-337">#7b68ee</span></span>|
|`mediumspringgreen`|<span data-ttu-id="344e7-338">#00fa9a</span><span class="sxs-lookup"><span data-stu-id="344e7-338">#00fa9a</span></span>|
|`mediumturquoise`|<span data-ttu-id="344e7-339">#48d1cc</span><span class="sxs-lookup"><span data-stu-id="344e7-339">#48d1cc</span></span>|
|`mediumvioletred`|<span data-ttu-id="344e7-340">#c71585</span><span class="sxs-lookup"><span data-stu-id="344e7-340">#c71585</span></span>|
|`midnightblue`|<span data-ttu-id="344e7-341">#191970</span><span class="sxs-lookup"><span data-stu-id="344e7-341">#191970</span></span>|
|`mintcream`|<span data-ttu-id="344e7-342">#f5fffa</span><span class="sxs-lookup"><span data-stu-id="344e7-342">#f5fffa</span></span>|
|`mistyrose`|<span data-ttu-id="344e7-343">#ffe4e1</span><span class="sxs-lookup"><span data-stu-id="344e7-343">#ffe4e1</span></span>|
|`moccasin`|<span data-ttu-id="344e7-344">#ffe4b5</span><span class="sxs-lookup"><span data-stu-id="344e7-344">#ffe4b5</span></span>|
|`navajowhite`|<span data-ttu-id="344e7-345">#ffdead</span><span class="sxs-lookup"><span data-stu-id="344e7-345">#ffdead</span></span>|
|`navy`|<span data-ttu-id="344e7-346">#000080</span><span class="sxs-lookup"><span data-stu-id="344e7-346">#000080</span></span>|
|`oldlace`|<span data-ttu-id="344e7-347">#fdf5e6</span><span class="sxs-lookup"><span data-stu-id="344e7-347">#fdf5e6</span></span>|
|`olive`|<span data-ttu-id="344e7-348">#808000</span><span class="sxs-lookup"><span data-stu-id="344e7-348">#808000</span></span>|
|`olivedrab`|<span data-ttu-id="344e7-349">#6b8e23</span><span class="sxs-lookup"><span data-stu-id="344e7-349">#6b8e23</span></span>|
|`orange`|<span data-ttu-id="344e7-350">#ffa500</span><span class="sxs-lookup"><span data-stu-id="344e7-350">#ffa500</span></span>|
|`orangered`|<span data-ttu-id="344e7-351">#ff4500</span><span class="sxs-lookup"><span data-stu-id="344e7-351">#ff4500</span></span>|
|`orchid`|<span data-ttu-id="344e7-352">#da70d6</span><span class="sxs-lookup"><span data-stu-id="344e7-352">#da70d6</span></span>|
|`palegoldenrod`|<span data-ttu-id="344e7-353">#eee8aa</span><span class="sxs-lookup"><span data-stu-id="344e7-353">#eee8aa</span></span>|
|`palegreen`|<span data-ttu-id="344e7-354">#98fb98</span><span class="sxs-lookup"><span data-stu-id="344e7-354">#98fb98</span></span>|
|`paleturquoise`|<span data-ttu-id="344e7-355">#afeeee</span><span class="sxs-lookup"><span data-stu-id="344e7-355">#afeeee</span></span>|
|`palevioletred`|<span data-ttu-id="344e7-356">#db7093</span><span class="sxs-lookup"><span data-stu-id="344e7-356">#db7093</span></span>|
|`papayawhip`|<span data-ttu-id="344e7-357">#ffefd5</span><span class="sxs-lookup"><span data-stu-id="344e7-357">#ffefd5</span></span>|
|`peachpuff`|<span data-ttu-id="344e7-358">#ffdab9</span><span class="sxs-lookup"><span data-stu-id="344e7-358">#ffdab9</span></span>|
|`peru`|<span data-ttu-id="344e7-359">#cd853f</span><span class="sxs-lookup"><span data-stu-id="344e7-359">#cd853f</span></span>|
|`pink`|<span data-ttu-id="344e7-360">#ffc0cb</span><span class="sxs-lookup"><span data-stu-id="344e7-360">#ffc0cb</span></span>|
|`plum`|<span data-ttu-id="344e7-361">#dda0dd</span><span class="sxs-lookup"><span data-stu-id="344e7-361">#dda0dd</span></span>|
|`powderblue`|<span data-ttu-id="344e7-362">#b0e0e6</span><span class="sxs-lookup"><span data-stu-id="344e7-362">#b0e0e6</span></span>|
|`purple`|<span data-ttu-id="344e7-363">#800080</span><span class="sxs-lookup"><span data-stu-id="344e7-363">#800080</span></span>|
|`red`|<span data-ttu-id="344e7-364">#ff0000</span><span class="sxs-lookup"><span data-stu-id="344e7-364">#ff0000</span></span>|
|`rosybrown`|<span data-ttu-id="344e7-365">#bc8f8f</span><span class="sxs-lookup"><span data-stu-id="344e7-365">#bc8f8f</span></span>|
|`royalblue`|<span data-ttu-id="344e7-366">#4169e1</span><span class="sxs-lookup"><span data-stu-id="344e7-366">#4169e1</span></span>|
|`saddlebrown`|<span data-ttu-id="344e7-367">#8b4513</span><span class="sxs-lookup"><span data-stu-id="344e7-367">#8b4513</span></span>|
|`salmon`|<span data-ttu-id="344e7-368">#fa8072</span><span class="sxs-lookup"><span data-stu-id="344e7-368">#fa8072</span></span>|
|`sandybrown`|<span data-ttu-id="344e7-369">#f4a460</span><span class="sxs-lookup"><span data-stu-id="344e7-369">#f4a460</span></span>|
|`seagreen`|<span data-ttu-id="344e7-370">#00ff00</span><span class="sxs-lookup"><span data-stu-id="344e7-370">#00ff00</span></span>|
|`seashell`|<span data-ttu-id="344e7-371">#fff5ee</span><span class="sxs-lookup"><span data-stu-id="344e7-371">#fff5ee</span></span>|
|`sienna`|<span data-ttu-id="344e7-372">#a0522d</span><span class="sxs-lookup"><span data-stu-id="344e7-372">#a0522d</span></span>|
|`silver`|<span data-ttu-id="344e7-373">#c0c0c0</span><span class="sxs-lookup"><span data-stu-id="344e7-373">#c0c0c0</span></span>|
|`skyblue`|<span data-ttu-id="344e7-374">#87ceeb</span><span class="sxs-lookup"><span data-stu-id="344e7-374">#87ceeb</span></span>|
|`slateblue`|<span data-ttu-id="344e7-375">#6a5acd</span><span class="sxs-lookup"><span data-stu-id="344e7-375">#6a5acd</span></span>|
|`slategray`|<span data-ttu-id="344e7-376">#708090</span><span class="sxs-lookup"><span data-stu-id="344e7-376">#708090</span></span>|
|`snow`|<span data-ttu-id="344e7-377">#fffafa</span><span class="sxs-lookup"><span data-stu-id="344e7-377">#fffafa</span></span>|
|`springgreen`|<span data-ttu-id="344e7-378">#00ff7f</span><span class="sxs-lookup"><span data-stu-id="344e7-378">#00ff7f</span></span>|
|`steelblue`|<span data-ttu-id="344e7-379">#4682b4</span><span class="sxs-lookup"><span data-stu-id="344e7-379">#4682b4</span></span>|
|`tan`|<span data-ttu-id="344e7-380">#d2b48c</span><span class="sxs-lookup"><span data-stu-id="344e7-380">#d2b48c</span></span>|
|`teal`|<span data-ttu-id="344e7-381">#008080</span><span class="sxs-lookup"><span data-stu-id="344e7-381">#008080</span></span>|
|`thistle`|<span data-ttu-id="344e7-382">#d8bfd8</span><span class="sxs-lookup"><span data-stu-id="344e7-382">#d8bfd8</span></span>|
|`tomato`|<span data-ttu-id="344e7-383">#ff6347</span><span class="sxs-lookup"><span data-stu-id="344e7-383">#ff6347</span></span>|
|`turquoise`|<span data-ttu-id="344e7-384">#40e0d0</span><span class="sxs-lookup"><span data-stu-id="344e7-384">#40e0d0</span></span>|
|`violet`|<span data-ttu-id="344e7-385">#ee82ee</span><span class="sxs-lookup"><span data-stu-id="344e7-385">#ee82ee</span></span>|
|`wheat`|<span data-ttu-id="344e7-386">#f5deb3</span><span class="sxs-lookup"><span data-stu-id="344e7-386">#f5deb3</span></span>|
|`white`|<span data-ttu-id="344e7-387">#ffffff</span><span class="sxs-lookup"><span data-stu-id="344e7-387">#ffffff</span></span>|
|`whitesmoke`|<span data-ttu-id="344e7-388">#f5f5f5</span><span class="sxs-lookup"><span data-stu-id="344e7-388">#f5f5f5</span></span>|
|`yellow`|<span data-ttu-id="344e7-389">#ffff00</span><span class="sxs-lookup"><span data-stu-id="344e7-389">#ffff00</span></span>|
|`yellowgreen`|<span data-ttu-id="344e7-390">#9acd32</span><span class="sxs-lookup"><span data-stu-id="344e7-390">#9acd32</span></span>|
