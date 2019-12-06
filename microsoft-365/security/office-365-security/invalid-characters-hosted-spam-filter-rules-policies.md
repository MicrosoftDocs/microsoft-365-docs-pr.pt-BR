---
title: Evitar caracteres inválidos nas regras e política de filtro de spam
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/24/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Fornece ajuda para os administradores que têm caracteres inválidos na configuração antispam e estão em problemas ao tentar usar o centro de conformidade &amp; de segurança.
ms.openlocfilehash: 5e6fa97a3f325b6fc6fdc449ba4a61282f67b644
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39866713"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a><span data-ttu-id="f5109-103">Evitar caracteres inválidos em suas regras de filtro de spam e política de filtro de spam</span><span class="sxs-lookup"><span data-stu-id="f5109-103">Avoid invalid characters in your spam filter rules and spam filter policy</span></span> 

<span data-ttu-id="f5109-104">Anteriormente, os administradores do Office 365 configuram e configuraram regras de filtro de spam e a política de filtro de spam usando o centro de administração do Exchange (Eat).</span><span class="sxs-lookup"><span data-stu-id="f5109-104">Previously, Office 365 administrators set up and configured spam filter rules and the spam filter policy by using the Exchange admin center (EAC).</span></span> <span data-ttu-id="f5109-105">Agora, use o centro de &amp; conformidade de segurança para gerenciar a configuração antispam.</span><span class="sxs-lookup"><span data-stu-id="f5109-105">Now, you use the Security &amp; Compliance Center to manage the your anti-spam configuration.</span></span> <span data-ttu-id="f5109-106">Os seguintes caracteres foram suportados no Eat, mas não têm suporte para uso no centro de &amp; conformidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="f5109-106">The following characters were supported in the EAC but are not supported for use in the Security &amp; Compliance Center.</span></span>  

<span data-ttu-id="f5109-107">**Caracteres inválidos:**</span><span class="sxs-lookup"><span data-stu-id="f5109-107">**Invalid characters:**</span></span>
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

<span data-ttu-id="f5109-108">Se suas regras de filtro de spam ou sua política de filtro de spam contiver qualquer um dos caracteres inválidos, você poderá encontrar qualquer um ou todos esses problemas:</span><span class="sxs-lookup"><span data-stu-id="f5109-108">If your spam filter rules or your spam filter policy contains any of the invalid characters, you might encounter any or all of these issues:</span></span>
- <span data-ttu-id="f5109-109">Você pode não conseguir encontrar a política ou as regras no centro de &amp; conformidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="f5109-109">You might be unable to find the policy or rules in the Security &amp; Compliance Center.</span></span>
- <span data-ttu-id="f5109-110">Você pode receber erros ao tentar obter as regras ou política usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5109-110">You might receive errors when trying to get the rules or policy by using Windows PowerShell.</span></span>
- <span data-ttu-id="f5109-111">Você pode achar que a política ou as configurações não são executadas ou executadas conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="f5109-111">You might find that the policy or settings do not run or perform as expected.</span></span>

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a><span data-ttu-id="f5109-112">Remover os caracteres inválidos da política e regras de filtro de spam</span><span class="sxs-lookup"><span data-stu-id="f5109-112">Remove the invalid characters from the spam filter policy and rules</span></span>

<span data-ttu-id="f5109-113">Depois de identificar a política e as regras que contêm caracteres inválidos, você pode alterar os nomes usando os cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5109-113">Once you have identified the policy and rules that contain invalid characters, you can change the names by using the Windows PowerShell cmdlets.</span></span> 

1. <span data-ttu-id="f5109-114">[Conecte-se ao Exchange Online usando o PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f5109-114">[Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="f5109-115">Para alterar o nome da política de filtro de spam, execute o cmdlet Set-HostedContentFilterPolicy da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f5109-115">To change the name of the spam filter policy, run the Set-HostedContentFilterPolicy cmdlet as follows:</span></span>
    
    ```powershell
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. <span data-ttu-id="f5109-116">Para alterar o nome de uma regra de filtro de spam, execute o cmdlet Set-HostedContentFilterRule da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f5109-116">To change the name of a spam filter rule, run the Set-HostedContentFilterRule cmdlet as follows:</span></span>
    
    ```powershell
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a><span data-ttu-id="f5109-117">Para saber mais</span><span class="sxs-lookup"><span data-stu-id="f5109-117">For more information</span></span>

[<span data-ttu-id="f5109-118">Gerenciamento de ameaças no centro &amp; de conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="f5109-118">Threat management in the Security &amp; Compliance Center</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="f5109-119">Set-HostedContentFilterPolicy</span><span class="sxs-lookup"><span data-stu-id="f5109-119">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)

[<span data-ttu-id="f5109-120">Set-HostedContentFilterRule</span><span class="sxs-lookup"><span data-stu-id="f5109-120">Set-HostedContentFilterRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule)
