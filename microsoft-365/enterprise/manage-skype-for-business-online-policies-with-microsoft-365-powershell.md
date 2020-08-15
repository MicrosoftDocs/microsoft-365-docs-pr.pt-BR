---
title: Gerenciar as políticas do Skype for Business Online com o Windows PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: ff93a341-6f0f-4f06-9690-726052e1be64
description: 'Resumo: Use o PowerShell para gerenciar as propriedades da conta de usuário do Skype for Business online com políticas.'
ms.openlocfilehash: 7657dae6fa1b27299e4cbc0cf6a311380cb90e9e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687374"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a><span data-ttu-id="4c490-103">Gerenciar as políticas do Skype for Business Online com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c490-103">Manage Skype for Business Online policies with PowerShell</span></span>

<span data-ttu-id="4c490-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4c490-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4c490-105">Para gerenciar muitas propriedades da conta de usuário do Skype for Business Online, você deve especificá-las como propriedades de políticas com o PowerShell para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c490-105">To manage many properties of user account for Skype for Business Online, you must specify them as properties of policies with PowerShell for Microsoft 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="4c490-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4c490-106">Before you begin</span></span>

<span data-ttu-id="4c490-107">Use estas instruções para configurar a execução dos comandos (pule as etapas que você já concluiu):</span><span class="sxs-lookup"><span data-stu-id="4c490-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>
  
1. <span data-ttu-id="4c490-108">Baixe e instale o [módulo do conector do Skype for Business online](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="4c490-108">Download and install the [Skype for Business Online Connector module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
    
2. <span data-ttu-id="4c490-109">Abra um prompt de comando do Windows PowerShell e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="4c490-109">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
  ```

<span data-ttu-id="4c490-110">Quando solicitado, insira o nome da conta e a senha do administrador do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="4c490-110">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="manage-user-account-policies"></a><span data-ttu-id="4c490-111">Gerenciar políticas de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="4c490-111">Manage user account policies</span></span>

<span data-ttu-id="4c490-112">Muitas propriedades da conta de usuário do Skype for Business online são configuradas usando políticas.</span><span class="sxs-lookup"><span data-stu-id="4c490-112">Many Skype for Business Online user account properties are configured by using policies.</span></span> <span data-ttu-id="4c490-113">As políticas são apenas coleções de configurações que podem ser aplicadas a um ou mais usuários.</span><span class="sxs-lookup"><span data-stu-id="4c490-113">Policies are simply collections of settings that can be applied to one or more users.</span></span> <span data-ttu-id="4c490-114">Para ver como a política foi configurada, você pode executar este comando de exemplo para a política FederationAndPICDefault:</span><span class="sxs-lookup"><span data-stu-id="4c490-114">To take a look at how the a policy has been configured, you can run this example command for the FederationAndPICDefault policy:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

<span data-ttu-id="4c490-115">Por sua vez, você deve obter algo semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="4c490-115">In turn, you should get back something similar to this:</span></span>
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

<span data-ttu-id="4c490-116">Neste exemplo, os valores nesta política determinam o que um uso pode ou não fazer quando se trata de comunicação com usuários federados.</span><span class="sxs-lookup"><span data-stu-id="4c490-116">In this example, the values within this policy determine what a use can or cannot do when it comes to communicating with federated users.</span></span> <span data-ttu-id="4c490-117">Por exemplo, a propriedade EnableOutsideAccess deve ser definida como true para que um usuário seja capaz de se comunicar com pessoas de fora da organização.</span><span class="sxs-lookup"><span data-stu-id="4c490-117">For example, the EnableOutsideAccess property must be set to True for a user to be able to communicate with people outside the organization.</span></span> <span data-ttu-id="4c490-118">Observe que essa propriedade não aparece no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c490-118">Note that this property does not appear in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4c490-119">Em vez disso, a propriedade é automaticamente definida como true ou false com base nas outras seleções que você faz.</span><span class="sxs-lookup"><span data-stu-id="4c490-119">Instead, the property is automatically set to True or False based on the other selections that you make.</span></span> <span data-ttu-id="4c490-120">As outras duas propriedades de interesse são:</span><span class="sxs-lookup"><span data-stu-id="4c490-120">The other two properties of interest are:</span></span>
  
- <span data-ttu-id="4c490-121">**EnableFederationAccess** indica se o usuário pode se comunicar com pessoas de domínios federados.</span><span class="sxs-lookup"><span data-stu-id="4c490-121">**EnableFederationAccess** indicates whether the user can communicate with people from federated domains.</span></span>
    
- <span data-ttu-id="4c490-122">**EnablePublicCloudAccess** indica se o usuário pode se comunicar com usuários do Windows Live.</span><span class="sxs-lookup"><span data-stu-id="4c490-122">**EnablePublicCloudAccess** indicates whether the user can communicate with Windows Live users.</span></span>
    
<span data-ttu-id="4c490-123">Portanto, você não altera diretamente as propriedades relacionadas à Federação nas contas de usuário (por exemplo, **set-CsUser-EnableFederationAccess $true**).</span><span class="sxs-lookup"><span data-stu-id="4c490-123">Therefore, you don't directly change federation-related properties on user accounts (for example, **Set-CsUser -EnableFederationAccess $True**).</span></span> <span data-ttu-id="4c490-124">Em vez disso, atribua uma conta uma política de acesso externo que tenha os valores de propriedade desejados pré-configurados.</span><span class="sxs-lookup"><span data-stu-id="4c490-124">Instead, you assign an account an external access policy that has the desired property values preconfigured.</span></span> <span data-ttu-id="4c490-125">Se quisermos que um usuário seja capaz de se comunicar com usuários federados e com usuários do Windows Live, essa conta de usuário deve ser atribuída a uma política que permita esses tipos de comunicação.</span><span class="sxs-lookup"><span data-stu-id="4c490-125">If we want a user to be able to communicate with federated users and with Windows Live users, that user account must be assigned a policy that allows those types of communication.</span></span>
  
<span data-ttu-id="4c490-126">Se você quiser saber se alguém pode se comunicar com os usuários de fora da organização, é necessário:</span><span class="sxs-lookup"><span data-stu-id="4c490-126">If you want to know whether or not someone can communicate with users from outside the organization, you have to:</span></span>
  
- <span data-ttu-id="4c490-127">Determinar qual política de acesso externo foi atribuída a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="4c490-127">Determine which external access policy has been assigned to that user.</span></span>
    
- <span data-ttu-id="4c490-128">Determinar quais recursos são ou não permitidos por essa política.</span><span class="sxs-lookup"><span data-stu-id="4c490-128">Determine which capabilities are or are not allowed by that policy.</span></span>
    
<span data-ttu-id="4c490-129">Por exemplo, você pode fazer isso usando este comando:</span><span class="sxs-lookup"><span data-stu-id="4c490-129">For example, you can do that by using this command:</span></span>
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

<span data-ttu-id="4c490-130">Este comando localiza a política atribuída ao usuário e, em seguida, localiza os recursos habilitados ou desabilitados nessa política.</span><span class="sxs-lookup"><span data-stu-id="4c490-130">This command finds the policy assigned to the user, then finds the capabilities enabled or disabled within that policy.</span></span>
  
<span data-ttu-id="4c490-131">Para gerenciar as políticas do Skype for Business online com o PowerShell, confira os cmdlets para:</span><span class="sxs-lookup"><span data-stu-id="4c490-131">To manage Skype for Business Online policies with PowerShell, see the cmdlets for:</span></span>

- <span data-ttu-id="4c490-132">[Política de cliente](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="4c490-132">[Client policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span></span>
- <span data-ttu-id="4c490-133">[Política de conferência](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="4c490-133">[Conferencing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span></span>
- <span data-ttu-id="4c490-134">[Política móvel](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="4c490-134">[Mobile policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span></span>
- <span data-ttu-id="4c490-135">[Política de caixa postal online](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="4c490-135">[Online Voicemail policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span></span>
- <span data-ttu-id="4c490-136">[Política de roteamento de voz](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="4c490-136">[Voice Routing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span></span>


> [!NOTE]
> <span data-ttu-id="4c490-137">Um plano de discagem do Skype for Business Online é uma política em cada relação, exceto o nome.</span><span class="sxs-lookup"><span data-stu-id="4c490-137">A Skype for Business Online dial plan is a policy in every respect except the name.</span></span> <span data-ttu-id="4c490-138">O nome "plano de discagem" foi escolhido em vez de, digamos, "política de discagem" para fornecer compatibilidade com versões anteriores do Office Communications Server e com o Exchange.</span><span class="sxs-lookup"><span data-stu-id="4c490-138">The name "dial plan" was chosen instead of, say, "dialing policy" in order to provide backward compatibility with Office Communications Server and with Exchange.</span></span> 
  
<span data-ttu-id="4c490-139">Por exemplo, para examinar todas as políticas de voz disponíveis para uso, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="4c490-139">For example, to look at all the voice policies available for your use, run this command:</span></span>
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> <span data-ttu-id="4c490-140">Isso retorna uma lista de todas as políticas de voz disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="4c490-140">That returns a list of all the voice policies available to you.</span></span> <span data-ttu-id="4c490-141">No entanto, tenha em mente que nem todas as políticas podem ser atribuídas a todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="4c490-141">Keep in mind, however, that not all policies can be assigned to all users.</span></span> <span data-ttu-id="4c490-142">Isso se deve a várias restrições envolvendo o licenciamento e localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="4c490-142">This is due to various restrictions involving licensing and geographic location.</span></span> <span data-ttu-id="4c490-143">(O que é chamado de "[local de uso](https://msdn.microsoft.com/library/azure/dn194136.aspx).") Se você quiser saber as políticas de acesso externo e as políticas de conferência que podem ser atribuídas a um usuário específico, use comandos semelhantes a estes:</span><span class="sxs-lookup"><span data-stu-id="4c490-143">(The so-called "[usage location](https://msdn.microsoft.com/library/azure/dn194136.aspx).") If you want to know the external access policies and the conferencing policies that can be assigned to a particular user, use commands similar to these:</span></span> 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

<span data-ttu-id="4c490-p106">O parâmetro ApplicableTo limita os dados retornados para políticas que podem ser atribuídas ao usuário especificado (por exemplo, Antônio Teixeira). Dependendo das restrições de licenciamento e local de uso, isso pode representar um subconjunto de todas as políticas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="4c490-p106">The ApplicableTo parameter limits the returned data to policies that can be assigned to the specified user (for example, Alex Darrow). Depending on licensing and usage location restrictions, that might represent a subset of all the available policies.</span></span> 
  
<span data-ttu-id="4c490-146">Em alguns casos, as propriedades das políticas não são usadas com o Microsoft 365, enquanto outras podem ser gerenciadas pela equipe de suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4c490-146">In some cases, properties of policies are not used with Microsoft 365, while others can only be managed by Microsoft support personnel.</span></span> 
  
<span data-ttu-id="4c490-147">Com o Skype for Business Online, os usuários devem ser gerenciados por uma política de algum tipo.</span><span class="sxs-lookup"><span data-stu-id="4c490-147">With Skype for Business Online, users must be managed by a policy of some kind.</span></span> <span data-ttu-id="4c490-148">Se uma propriedade válida relacionada à política estiver em branco, isso significa que o usuário em questão está sendo gerenciado por uma política global, que é uma política aplicada automaticamente a um usuário, a menos que seja especificamente atribuída uma política por usuário.</span><span class="sxs-lookup"><span data-stu-id="4c490-148">If a valid policy-related property is blank, that means that the user in question is being managed by a global policy, which is a policy that is automatically applied to a user unless he or she is specifically assigned a per-user policy.</span></span> <span data-ttu-id="4c490-149">Como não vemos uma política de cliente listada para uma conta de usuário, ela é gerenciada pela política global.</span><span class="sxs-lookup"><span data-stu-id="4c490-149">Because we don't see a client policy listed for a user account, it is managed by the global policy.</span></span> <span data-ttu-id="4c490-150">Você pode determinar a política de cliente global com este comando:</span><span class="sxs-lookup"><span data-stu-id="4c490-150">You can determine the global client policy with this command:</span></span>
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a><span data-ttu-id="4c490-151">Confira também</span><span class="sxs-lookup"><span data-stu-id="4c490-151">See also</span></span>

[<span data-ttu-id="4c490-152">Gerenciar o Skype for Business Online com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c490-152">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4c490-153">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c490-153">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4c490-154">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c490-154">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

