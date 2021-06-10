---
title: Configurar o Gerenciamento de Direitos do Azure para a versão anterior da Criptografia de Mensagens
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: A versão anterior do Criptografia de Mensagens do Office 365 depende Microsoft Azure Gerenciamento de Direitos (anteriormente conhecido como gerenciamento de direitos Windows Azure Active Directory direitos).
ms.openlocfilehash: 978a8027c79de574b80aeedabcbbd51fa6f9e2a0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919487"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a><span data-ttu-id="8b18c-103">Configurar o Gerenciamento de Direitos do Azure para a versão anterior da Criptografia de Mensagens</span><span class="sxs-lookup"><span data-stu-id="8b18c-103">Set up Azure Rights Management for the previous version of Message Encryption</span></span>

<span data-ttu-id="8b18c-104">Este tópico descreve as etapas que você precisa seguir para ativar e configurar o Azure Rights Management (RMS), parte da Proteção de Informações do Azure, para uso com a versão anterior do Criptografia de Mensagens do Office 365 (OME).</span><span class="sxs-lookup"><span data-stu-id="8b18c-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with the previous version of Office 365 Message Encryption (OME).</span></span>

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a><span data-ttu-id="8b18c-105">Este artigo só se aplica à versão anterior do OME</span><span class="sxs-lookup"><span data-stu-id="8b18c-105">This article only applies to the previous version of OME</span></span>

<span data-ttu-id="8b18c-106">Se você ainda não moveu sua organização para os novos recursos OME, mas já implantou o OME, as informações neste artigo se aplicarão à sua organização.</span><span class="sxs-lookup"><span data-stu-id="8b18c-106">If you haven't yet moved your organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization.</span></span> <span data-ttu-id="8b18c-107">A Microsoft recomenda que você faça um plano para mover para os novos recursos OME assim que for razoável para sua organização.</span><span class="sxs-lookup"><span data-stu-id="8b18c-107">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="8b18c-108">Para obter instruções, [consulte Set up new Criptografia de Mensagens do Office 365 capabilities](set-up-new-message-encryption-capabilities.md).</span><span class="sxs-lookup"><span data-stu-id="8b18c-108">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="8b18c-109">Se você quiser saber mais sobre como os novos recursos funcionam primeiro, [consulte Criptografia de Mensagens do Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="8b18c-109">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span> <span data-ttu-id="8b18c-110">O restante deste artigo refere-se ao comportamento OME antes da versão dos novos recursos OME.</span><span class="sxs-lookup"><span data-stu-id="8b18c-110">The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="8b18c-111">Pré-requisitos para usar a versão anterior do Criptografia de Mensagens do Office 365</span><span class="sxs-lookup"><span data-stu-id="8b18c-111">Prerequisites for using the previous version of Office 365 Message Encryption</span></span>
<span data-ttu-id="8b18c-112"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="8b18c-112"><a name="warmprereqs"> </a></span></span>

<span data-ttu-id="8b18c-113">Criptografia de Mensagens do Office 365 (OME), incluindo IRM, depende do Azure Rights Management (Azure RMS).</span><span class="sxs-lookup"><span data-stu-id="8b18c-113">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS).</span></span> <span data-ttu-id="8b18c-114">O Azure RMS é a tecnologia de proteção usada pela Proteção de Informações do Azure.</span><span class="sxs-lookup"><span data-stu-id="8b18c-114">Azure RMS is the protection technology used by Azure Information Protection.</span></span> <span data-ttu-id="8b18c-115">Para usar o OME, sua organização deve incluir uma assinatura Exchange Online ou Proteção do Exchange Online que, por sua vez, inclui uma assinatura de Gerenciamento de Direitos do Azure.</span><span class="sxs-lookup"><span data-stu-id="8b18c-115">To use OME, your organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="8b18c-116">Se você não tiver certeza do que sua assinatura inclui, consulte as descrições Exchange Online de serviço para Política de Mensagem, Recuperação [e Conformidade.](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)</span><span class="sxs-lookup"><span data-stu-id="8b18c-116">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

- <span data-ttu-id="8b18c-117">Se você tiver o Azure Rights Management, mas ele não estiver definido para o Exchange Online ou Proteção do Exchange Online, este artigo explica como ativar o Gerenciamento de Direitos do Azure e, em seguida, descreve a melhor maneira de configurar o OME para trabalhar com o Gerenciamento de Direitos do Azure.</span><span class="sxs-lookup"><span data-stu-id="8b18c-117">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>

- <span data-ttu-id="8b18c-118">Se você já definiu o OME para trabalhar com o Gerenciamento de Direitos do Azure para Exchange Online ou Proteção do Exchange Online, dependendo de como você a configurar, talvez esteja pronto para começar a usar o OME e seus novos recursos imediatamente.</span><span class="sxs-lookup"><span data-stu-id="8b18c-118">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away.</span></span> <span data-ttu-id="8b18c-119">Este artigo explica como determinar se você definiu o OME corretamente, o que fazer se precisar alterar sua configuração e o que acontece se você optar por não alterar sua configuração.</span><span class="sxs-lookup"><span data-stu-id="8b18c-119">This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup.</span></span> <span data-ttu-id="8b18c-120">Por exemplo, para usar os novos recursos, você deve usar o Azure RMS com o OME.</span><span class="sxs-lookup"><span data-stu-id="8b18c-120">For example, in order to use the new capabilities, you must use Azure RMS with OME.</span></span> <span data-ttu-id="8b18c-121">Não é possível usar os novos recursos com um RMS do Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="8b18c-121">You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a><span data-ttu-id="8b18c-122">Ativar o Gerenciamento de Direitos do Azure para a versão anterior do OME no Office 365</span><span class="sxs-lookup"><span data-stu-id="8b18c-122">Activate Azure Rights Management for  the previous version of OME in Office 365</span></span>

<span data-ttu-id="8b18c-123">Você precisa ativar o Gerenciamento de Direitos do Azure para que os usuários em sua organização possam aplicar proteção de informações às mensagens enviadas e abrir mensagens e arquivos protegidos pelo serviço de Gerenciamento de Direitos do Azure.</span><span class="sxs-lookup"><span data-stu-id="8b18c-123">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service.</span></span> <span data-ttu-id="8b18c-124">Para obter instruções, [consulte Ativando o Gerenciamento de Direitos do Azure](/azure/information-protection/activate-service).</span><span class="sxs-lookup"><span data-stu-id="8b18c-124">For instructions, see [Activating Azure Rights Management](/azure/information-protection/activate-service).</span></span> <span data-ttu-id="8b18c-125">Depois de concluir a ativação, retorne aqui e continue com as tarefas deste artigo.</span><span class="sxs-lookup"><span data-stu-id="8b18c-125">Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="8b18c-126">Configurar a versão anterior do OME para usar o Azure RMS importando domínios de publicação confiáveis (TPDs)</span><span class="sxs-lookup"><span data-stu-id="8b18c-126">Set up the previous version of OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>

<span data-ttu-id="8b18c-127">Um TPD é um arquivo XML que contém informações sobre as configurações de gerenciamento de direitos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="8b18c-127">A TPD is an XML file that contains information about your organization's rights management settings.</span></span> <span data-ttu-id="8b18c-128">Por exemplo, o TPD contém informações sobre o certificado licenciador do servidor (SLC) usado para assinar e criptografar certificados e licenças, as URLs usadas para licenciamento e publicação, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="8b18c-128">For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on.</span></span> <span data-ttu-id="8b18c-129">Você importa o TPD para sua organização usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b18c-129">You import the TPD into your organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8b18c-130">Anteriormente, você poderia optar por importar TPDs do serviço de Gerenciamento de Direitos do Active Directory (AD RMS) para sua organização.</span><span class="sxs-lookup"><span data-stu-id="8b18c-130">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your organization.</span></span> <span data-ttu-id="8b18c-131">No entanto, isso impedirá que você use os novos recursos OME e não é recomendado.</span><span class="sxs-lookup"><span data-stu-id="8b18c-131">However, doing so will prevent you from using the new OME capabilities and is not recommended.</span></span> <span data-ttu-id="8b18c-132">Se sua organização estiver configurada no momento dessa forma, a Microsoft recomenda que você crie um plano para migrar do RMS do Active Directory local para a Proteção de Informações do Azure baseada na nuvem.</span><span class="sxs-lookup"><span data-stu-id="8b18c-132">If your organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection.</span></span> <span data-ttu-id="8b18c-133">Para obter mais informações, [consulte Migrating from AD RMS to Azure Information Protection](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span><span class="sxs-lookup"><span data-stu-id="8b18c-133">For more information, see [Migrating from AD RMS to Azure Information Protection](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span></span> <span data-ttu-id="8b18c-134">Você não poderá usar os novos recursos OME até concluir a migração para a Proteção de Informações do Azure.</span><span class="sxs-lookup"><span data-stu-id="8b18c-134">You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span>
  
 <span data-ttu-id="8b18c-135">**Para importar TPDs do Azure RMS**</span><span class="sxs-lookup"><span data-stu-id="8b18c-135">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="8b18c-136">[Conexão usar Exchange Online PowerShell Remoto.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="8b18c-136">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="8b18c-137">Escolha a URL de compartilhamento de chaves que corresponde à localização geográfica da sua organização:</span><span class="sxs-lookup"><span data-stu-id="8b18c-137">Choose the key-sharing URL that corresponds to your organization's geographic location:</span></span>

|<span data-ttu-id="8b18c-138">**Location**</span><span class="sxs-lookup"><span data-stu-id="8b18c-138">**Location**</span></span>|<span data-ttu-id="8b18c-139">**URL de local de compartilhamento de chaves**</span><span class="sxs-lookup"><span data-stu-id="8b18c-139">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8b18c-140">América do Norte</span><span class="sxs-lookup"><span data-stu-id="8b18c-140">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="8b18c-141">União Europeia</span><span class="sxs-lookup"><span data-stu-id="8b18c-141">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="8b18c-142">Ásia</span><span class="sxs-lookup"><span data-stu-id="8b18c-142">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="8b18c-143">América do Sul</span><span class="sxs-lookup"><span data-stu-id="8b18c-143">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="8b18c-144">Office 365 para agências governamentais (Nuvem de Comunidade Governamental)</span><span class="sxs-lookup"><span data-stu-id="8b18c-144">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="8b18c-145">Esse local de compartilhamento de chaves RMS é reservado para clientes que compraram Office 365 SKUs do Governo.</span><span class="sxs-lookup"><span data-stu-id="8b18c-145">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. <span data-ttu-id="8b18c-146">Configure o local de compartilhamento de chaves executando o cmdlet [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="8b18c-146">Configure the key-sharing location by running the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows:</span></span> 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   <span data-ttu-id="8b18c-147">Por exemplo, para configurar o local de compartilhamento de chaves se sua organização estiver localizada na América do Norte:</span><span class="sxs-lookup"><span data-stu-id="8b18c-147">For example, to configure the key sharing location if your organization is located in North America:</span></span>

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. <span data-ttu-id="8b18c-148">Execute o cmdlet [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) com a opção -RMSOnline para importar o TPD do Azure Rights Management:</span><span class="sxs-lookup"><span data-stu-id="8b18c-148">Run the [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   <span data-ttu-id="8b18c-149">Onde  *TPDName*  é o nome que você deseja usar para o TPD.</span><span class="sxs-lookup"><span data-stu-id="8b18c-149">Where  *TPDName*  is the name you want to use for the TPD.</span></span> <span data-ttu-id="8b18c-150">Por exemplo, "Contoso TPD norte-americano".</span><span class="sxs-lookup"><span data-stu-id="8b18c-150">For example, "Contoso North American TPD".</span></span> 

5. <span data-ttu-id="8b18c-151">Para verificar se você configurou com êxito sua organização para usar o serviço de Gerenciamento de Direitos do Azure, execute o cmdlet [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) com a opção -RMSOnline da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="8b18c-151">To verify that you successfully configured your organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) cmdlet with the -RMSOnline switch as follows:</span></span>

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   <span data-ttu-id="8b18c-152">Entre outras coisas, este cmdlet verifica a conectividade com o serviço de Gerenciamento de Direitos do Azure, baixa o TPD e verifica sua validade.</span><span class="sxs-lookup"><span data-stu-id="8b18c-152">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>

6. <span data-ttu-id="8b18c-153">Execute o cmdlet [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) da seguinte forma para desabilitar os modelos de Gerenciamento de Direitos do Azure de estarem disponíveis no Outlook na Web e Outlook:</span><span class="sxs-lookup"><span data-stu-id="8b18c-153">Run the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. <span data-ttu-id="8b18c-154">Execute o cmdlet [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) da seguinte forma para habilitar o Gerenciamento de Direitos do Azure para sua organização de email baseada em nuvem e configurá-lo para usar o Gerenciamento de Direitos do Azure para Criptografia de Mensagens do Office 365:</span><span class="sxs-lookup"><span data-stu-id="8b18c-154">Run the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span>

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. <span data-ttu-id="8b18c-155">Para verificar se você importou com êxito o TPD e habilitar o Gerenciamento de Direitos do Azure, use o cmdlet Test-IRMConfiguration para testar a funcionalidade de Gerenciamento de Direitos do Azure.</span><span class="sxs-lookup"><span data-stu-id="8b18c-155">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality.</span></span> <span data-ttu-id="8b18c-156">Para obter detalhes, confira "Exemplo 1" em [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).</span><span class="sxs-lookup"><span data-stu-id="8b18c-156">For details, see "Example 1" in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).</span></span>

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="8b18c-157">Tenho a versão anterior do OME configurada com o Gerenciamento de Direitos do Active Directory e não a Proteção de Informações do Azure, o que faço?</span><span class="sxs-lookup"><span data-stu-id="8b18c-157">I have the previous version of OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="8b18c-158"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="8b18c-158"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="8b18c-159">Você pode continuar a usar suas regras de fluxo de email Criptografia de Mensagens do Office 365 existentes com o Gerenciamento de Direitos do Active Directory, mas não pode configurar ou usar os novos recursos OME.</span><span class="sxs-lookup"><span data-stu-id="8b18c-159">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities.</span></span> <span data-ttu-id="8b18c-160">Em vez disso, você precisa migrar para a Proteção de Informações do Azure.</span><span class="sxs-lookup"><span data-stu-id="8b18c-160">Instead, you need to migrate to Azure Information Protection.</span></span> <span data-ttu-id="8b18c-161">Para obter informações sobre migração e o que isso significa para sua organização, consulte [Migrating from AD RMS to Azure Information Protection](/information-protection/deploy-use/prepare-environment-adrms).</span><span class="sxs-lookup"><span data-stu-id="8b18c-161">For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="8b18c-162">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="8b18c-162">Next steps</span></span>
<span data-ttu-id="8b18c-163"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="8b18c-163"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="8b18c-164">Depois de concluir a instalação do Gerenciamento de Direitos do Azure, se quiser habilitar os novos recursos OME, consulte Configurar novos recursos Criptografia de Mensagens do Office 365 do Azure com base na Proteção de Informações do [Azure.](./set-up-new-message-encryption-capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="8b18c-164">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](./set-up-new-message-encryption-capabilities.md)</span></span>
  
<span data-ttu-id="8b18c-165">Depois de configurar sua organização para usar os novos recursos OME, você estará pronto para Definir regras de fluxo de emails para proteger mensagens de email com novos recursos [OME.](define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="8b18c-165">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8b18c-166">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8b18c-166">Related topics</span></span>
<span data-ttu-id="8b18c-167"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="8b18c-167"><a name="importTPDs"> </a></span></span>

[<span data-ttu-id="8b18c-168">Criptografia no Office 365</span><span class="sxs-lookup"><span data-stu-id="8b18c-168">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="8b18c-169">Detalhes de referências técnicas sobre a criptografia no Office 365</span><span class="sxs-lookup"><span data-stu-id="8b18c-169">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="8b18c-170"> O que é o Azure Rights Management? </span><span class="sxs-lookup"><span data-stu-id="8b18c-170">What is Azure Rights Management?</span></span>](/information-protection/understand-explore/what-is-azure-rms)