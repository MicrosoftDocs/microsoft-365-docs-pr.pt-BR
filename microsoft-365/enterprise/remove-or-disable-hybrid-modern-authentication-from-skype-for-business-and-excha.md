---
title: Como remover ou desabilitar a autenticação moderna híbrida do Skype for Business e do Exchange
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: Este artigo explica como remover ou desabilitar a Autenticação Moderna Híbrida do Skype for Business e do Exchange.
ms.openlocfilehash: 9442ef3e19d0835bfd59f27ec425e36fd7dfcf7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927283"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a><span data-ttu-id="9c81d-103">Como remover ou desabilitar a autenticação moderna híbrida do Skype for Business e do Exchange</span><span class="sxs-lookup"><span data-stu-id="9c81d-103">Removing or disabling Hybrid Modern Authentication from Skype for Business and Exchange</span></span>

<span data-ttu-id="9c81d-104">*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9c81d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9c81d-105">Se você habilitar a HMA (Autenticação Moderna Híbrida) apenas para descobrir que ela não é adequada para seu ambiente atual, você pode desabilitar o HMA.</span><span class="sxs-lookup"><span data-stu-id="9c81d-105">If you've enabled Hybrid Modern Authentication (HMA) only to find it's unsuitable for your current environment, you can disable HMA.</span></span> <span data-ttu-id="9c81d-106">Este artigo explica como.</span><span class="sxs-lookup"><span data-stu-id="9c81d-106">This article explains how.</span></span>
  
## <a name="who-is-this-article-for"></a><span data-ttu-id="9c81d-107">Para quem é esse artigo?</span><span class="sxs-lookup"><span data-stu-id="9c81d-107">Who is this article for?</span></span>

<span data-ttu-id="9c81d-108">Se você habilitar a Autenticação Moderna no Skype for Business Online ou local e/ou Exchange Online ou local e descobriu que precisa desabilitar o HMA, estas etapas são para você.</span><span class="sxs-lookup"><span data-stu-id="9c81d-108">If you've enabled Modern Authentication in Skype for Business Online or On-premises, and/or Exchange Online or On-premises and found you need to disable HMA, these steps are for you.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c81d-109">Consulte o artigo ' Topologias do[Skype for Business](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)com suporte com Autenticação Moderna ' se você estiver no Skype for Business Online ou no local, tenha um HMA de topologia mista e precise ver topologias com suporte antes de começar.</span><span class="sxs-lookup"><span data-stu-id="9c81d-109">See the '[Skype for Business topologies supported with Modern Authentication](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)' article if you're in Skype for Business Online or On-premises, have a mixed-topology HMA, and need to look at supported topologies before you begin.</span></span>
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a><span data-ttu-id="9c81d-110">Como desabilitar a Autenticação Moderna Híbrida (Exchange)</span><span class="sxs-lookup"><span data-stu-id="9c81d-110">How to disable Hybrid Modern Authentication (Exchange)</span></span>

1. <span data-ttu-id="9c81d-111">**Exchange Local :** Abra o Shell de Gerenciamento do Exchange e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="9c81d-111">**Exchange On-premises**: Open the Exchange Management Shell and run the following commands:</span></span> 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. <span data-ttu-id="9c81d-112">**Exchange Online**: [Conectar-se ao Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) com o PowerShell Remoto.</span><span class="sxs-lookup"><span data-stu-id="9c81d-112">**Exchange Online**: [Connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) with Remote PowerShell.</span></span> <span data-ttu-id="9c81d-113">Execute o seguinte comando para transformar seu sinalizador  *OAuth2ClientProfileEnabled*  como "false":</span><span class="sxs-lookup"><span data-stu-id="9c81d-113">Run the following command to turn your  *OAuth2ClientProfileEnabled*  flag to 'false':</span></span>

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a><span data-ttu-id="9c81d-114">Como desabilitar a Autenticação Moderna Híbrida (Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="9c81d-114">How to disable Hybrid Modern Authentication (Skype for Business)</span></span>

1. <span data-ttu-id="9c81d-115">**Skype for Business Local**: Execute os seguintes comandos no Shell de Gerenciamento do Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="9c81d-115">**Skype for Business On-premises**: Run the following commands in Skype for Business Management Shell:</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. <span data-ttu-id="9c81d-116">**Skype for Business Online**: [Conectar-se ao Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) com o PowerShell Remoto.</span><span class="sxs-lookup"><span data-stu-id="9c81d-116">**Skype for Business Online**: [Connect to Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) with Remote PowerShell.</span></span> <span data-ttu-id="9c81d-117">Execute o seguinte comando para desabilitar a Autenticação Moderna:</span><span class="sxs-lookup"><span data-stu-id="9c81d-117">Run the following command to disable Modern Authentication:</span></span>

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

<span data-ttu-id="9c81d-118">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="9c81d-118">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md) .</span></span> 
