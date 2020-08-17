---
title: Criar um grupo do Microsoft 365 com uma PDL específica
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: Saiba como criar um grupo do Microsoft 365 com um local de dados preferencial especificado em um ambiente multigeográfico.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0906d0b4881dd69bbf47cbb536c6c448a1a4f611
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687237"
---
# <a name="create-a-microsoft-365-group-with-a-specific-pdl"></a><span data-ttu-id="7f66e-103">Criar um grupo do Microsoft 365 com uma PDL específica</span><span class="sxs-lookup"><span data-stu-id="7f66e-103">Create a Microsoft 365 Group with a specific PDL</span></span>

<span data-ttu-id="7f66e-104">Quando os usuários em um ambiente multigeográfico criam um grupo do Microsoft 365, o local de dados preferido do grupo é automaticamente definido para o do usuário.</span><span class="sxs-lookup"><span data-stu-id="7f66e-104">When users in a multi-geo environment create a Microsoft 365 Group, the group preferred data location is automatically set to that of the user.</span></span> <span data-ttu-id="7f66e-105">Os administradores globais, do SharePoint e do Exchange podem criar grupos em qualquer região que selecionarem.</span><span class="sxs-lookup"><span data-stu-id="7f66e-105">Global, SharePoint, and Exchange Administrators can create groups in any region they select.</span></span> 

<span data-ttu-id="7f66e-106">Se precisar criar um grupo com uma PDL específica, você pode fazer isso através do centro do administração do SharePoint ou através do cmdlet do novo PowerShell do Microsoft Exchange Online UnifiedGroup.</span><span class="sxs-lookup"><span data-stu-id="7f66e-106">If you need to create a group with a specific PDL, you can do that using from the SharePoint admin center or through the Exchange Online New-UnifiedGroup Microsoft PowerShell cmdlet.</span></span> <span data-ttu-id="7f66e-107">Quando você fizer isso, a caixa de correio de grupo e o site do SharePoint associados ao grupo serão provisionados na PDL especificada.</span><span class="sxs-lookup"><span data-stu-id="7f66e-107">When you do this, both the group mailbox and SharePoint site associated with the group will be provisioned in the specified PDL.</span></span>

<span data-ttu-id="7f66e-108">Para criar um grupo do Microsoft 365 com a PDL que você especificar, vá para o centro de administração do SharePoint no local geográfico onde você deseja criar o site do grupo.</span><span class="sxs-lookup"><span data-stu-id="7f66e-108">To create a Microsoft 365 Group with the PDL that you specify, go to the SharePoint admin center in the geo location where you want to create the group site.</span></span>

<span data-ttu-id="7f66e-109">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7f66e-109">For example:</span></span>

<span data-ttu-id="7f66e-110">Se você quer criar um site de grupo no seu local na Austrália, pode ir para https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span><span class="sxs-lookup"><span data-stu-id="7f66e-110">If you want to create a group site in your Australia location, you can go to https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span></span>

1. <span data-ttu-id="7f66e-111">Selecione **+ Criar**.</span><span class="sxs-lookup"><span data-stu-id="7f66e-111">Select **+ Create**.</span></span>
2. <span data-ttu-id="7f66e-112">Siga o processo para criar um site de grupo.</span><span class="sxs-lookup"><span data-stu-id="7f66e-112">Follow the process to create a group site.</span></span>

<span data-ttu-id="7f66e-113">O seu site de grupo será provisionado na localização geográfica correspondente ao centro de administração do SharePoint no qual você iniciou a solicitação de criação de site.</span><span class="sxs-lookup"><span data-stu-id="7f66e-113">Your group site will be provisioned in the geo location corresponding to the SharePoint admin center from which you initiated the site creation request.</span></span> 

<span data-ttu-id="7f66e-114">Usando o PowerShell do Exchange</span><span class="sxs-lookup"><span data-stu-id="7f66e-114">Using Exchange PowerShell</span></span> 

<span data-ttu-id="7f66e-115">Conecte-se ao PowerShell do Exchange Online e passe o parâmetro *-MailBoxRegion* com o código de localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="7f66e-115">Connect to Exchange Online PowerShell and pass the parameter *-MailBoxRegion* with the geo location code.</span></span>

<span data-ttu-id="7f66e-116">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7f66e-116">For example:</span></span> 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![O Cmdlet do PowerShell de captura de tela do novo UnifiedGroup com sintaxe](../media/multi-geo-new-group-with-pdl-powershell.png)

<span data-ttu-id="7f66e-118">Observe que o provisionamento de sites de grupo do SharePoint é sob demanda.</span><span class="sxs-lookup"><span data-stu-id="7f66e-118">Note that SharePoint group site provisioning is on-demand.</span></span> <span data-ttu-id="7f66e-119">O site será configurado a primeira vez que um membro ou proprietário do grupo tentar acessá-lo.</span><span class="sxs-lookup"><span data-stu-id="7f66e-119">The site will be provisioned the first time a group owner or member attempts to access it.</span></span>

## <a name="geo-location-codes"></a><span data-ttu-id="7f66e-120">Códigos de localização geográfica</span><span class="sxs-lookup"><span data-stu-id="7f66e-120">Geo location codes</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a><span data-ttu-id="7f66e-121">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7f66e-121">Related topics</span></span>

[<span data-ttu-id="7f66e-122">Conectar-se ao PowerShell do Exchange Online </span><span class="sxs-lookup"><span data-stu-id="7f66e-122">Connect to Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)