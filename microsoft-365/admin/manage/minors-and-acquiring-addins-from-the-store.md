---
title: Menores e aquisição de complementos da Loja
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Saiba mais sobre os regulamentos do RGPD (Regulamento Geral sobre a Proteção de Dados) que regem os dados pessoais de menores.
ms.openlocfilehash: a738e22a0ac0b995c8e44fcf4cc5a2eb47375be5
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306546"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="bc818-103">Menores e aquisição de complementos da Loja</span><span class="sxs-lookup"><span data-stu-id="bc818-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="bc818-104">O RGPD (Regulamento Geral sobre a Proteção de Dados) é uma regulamentação da União Europeia que entra em vigor em 25 de maio de 2018.</span><span class="sxs-lookup"><span data-stu-id="bc818-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="bc818-105">Ele concede aos usuários direitos e proteção de seus dados.</span><span class="sxs-lookup"><span data-stu-id="bc818-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="bc818-106">Um dos aspectos do RGPD é que os menores não podem ter seus dados pessoais enviados às partes que seu pai ou responsável não aprovou.</span><span class="sxs-lookup"><span data-stu-id="bc818-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="bc818-107">A idade específica definida como menor depende da região onde o indivíduo está localizado.</span><span class="sxs-lookup"><span data-stu-id="bc818-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="bc818-108">As regiões que têm regulamentações estatutuais sobre o consentimento dos pais incluem Estados Unidos, Coreia do Sul, Reino Unido e União Europeia.</span><span class="sxs-lookup"><span data-stu-id="bc818-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="bc818-109">Nessas regiões, um menor de idade será impedido (por meio do Azure Active Directory) de obter novos complementos do Office da Loja e executar os complementos adquiridos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="bc818-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="bc818-110">Para países sem regulamentações estatutárias, não haverá restrições de download.</span><span class="sxs-lookup"><span data-stu-id="bc818-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="bc818-111">Um usuário é determinado como menor com base nos dados especificados no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bc818-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="bc818-112">O administrador da organização é responsável por declarar a faixa etária legal e o consentimento dos pais desse usuário.</span><span class="sxs-lookup"><span data-stu-id="bc818-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="bc818-113">Se o pai/responsável consentir com um menor usando um determinado complemento, o administrador da organização poderá usar a implantação centralizada para implantar esse complemento em todos os menores que tenham consentimento.</span><span class="sxs-lookup"><span data-stu-id="bc818-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="bc818-114">Para ser compatível com o RGPD para menores, você precisa garantir que um dos seguintes builds do Office seja implantado em sua escola/organização.</span><span class="sxs-lookup"><span data-stu-id="bc818-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="bc818-115">**Para Word, Excel, PowerPoint e Project:**</span><span class="sxs-lookup"><span data-stu-id="bc818-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="bc818-116">**Plataforma**</span><span class="sxs-lookup"><span data-stu-id="bc818-116">**Platform**</span></span> <br/> |<span data-ttu-id="bc818-117">**Número de compilação**</span><span class="sxs-lookup"><span data-stu-id="bc818-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="bc818-118">Aplicativos do Microsoft 365 para empresas (Canal Atual)</span><span class="sxs-lookup"><span data-stu-id="bc818-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="bc818-119">9001.2138</span><span class="sxs-lookup"><span data-stu-id="bc818-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="bc818-120">Aplicativos do Microsoft 365 para empresas (Canal Empresarial Semestais)</span><span class="sxs-lookup"><span data-stu-id="bc818-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="bc818-121">8431.2159</span><span class="sxs-lookup"><span data-stu-id="bc818-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="bc818-122">Office 2016 para Windows</span><span class="sxs-lookup"><span data-stu-id="bc818-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="bc818-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="bc818-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="bc818-124">Office 2013 para Windows</span><span class="sxs-lookup"><span data-stu-id="bc818-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="bc818-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="bc818-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="bc818-126">Office 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="bc818-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="bc818-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="bc818-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="bc818-128">Office na Web</span><span class="sxs-lookup"><span data-stu-id="bc818-128">Office for the web</span></span>  <br/> |<span data-ttu-id="bc818-129">N/D</span><span class="sxs-lookup"><span data-stu-id="bc818-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="bc818-130">**Para o Outlook**:</span><span class="sxs-lookup"><span data-stu-id="bc818-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="bc818-131">**Plataforma**</span><span class="sxs-lookup"><span data-stu-id="bc818-131">**Platform**</span></span> <br/> |<span data-ttu-id="bc818-132">**Número de compilação**</span><span class="sxs-lookup"><span data-stu-id="bc818-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="bc818-133">Outlook 2016 para Windows (MSI)</span><span class="sxs-lookup"><span data-stu-id="bc818-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="bc818-134">Build No TBD</span><span class="sxs-lookup"><span data-stu-id="bc818-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="bc818-135">Outlook 2016 para Windows (C2R)</span><span class="sxs-lookup"><span data-stu-id="bc818-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="bc818-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="bc818-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="bc818-137">Office 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="bc818-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="bc818-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="bc818-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="bc818-139">Outlook Mobile para iOS</span><span class="sxs-lookup"><span data-stu-id="bc818-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="bc818-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="bc818-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="bc818-141">Outlook Mobile para Android</span><span class="sxs-lookup"><span data-stu-id="bc818-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="bc818-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="bc818-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="bc818-143">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="bc818-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="bc818-144">N/D</span><span class="sxs-lookup"><span data-stu-id="bc818-144">N/A</span></span>  <br/> |

 <span data-ttu-id="bc818-145">**Requisitos do Office 2013**</span><span class="sxs-lookup"><span data-stu-id="bc818-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="bc818-146">O Word, o Excel e o PowerPoint 2013 para Windows darão suporte às mesmas verificações secundárias se a ADAL (Biblioteca de Autenticação do Active Directory) estiver habilitada.</span><span class="sxs-lookup"><span data-stu-id="bc818-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="bc818-147">Há duas opções de conformidade, conforme explicado a seguir.</span><span class="sxs-lookup"><span data-stu-id="bc818-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="bc818-148">**Habilitar ADAL**.</span><span class="sxs-lookup"><span data-stu-id="bc818-148">**Enable ADAL**.</span></span> <span data-ttu-id="bc818-149">Este artigo explica como habilitar a ADAL para Office 2013: usando a autenticação moderna do [Microsoft 365 com clientes do Office.](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)</span><span class="sxs-lookup"><span data-stu-id="bc818-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).</span></span><br/><span data-ttu-id="bc818-150">Você também precisa definir as chaves do Registro para habilitar a ADAL, conforme explicado em Habilitar Autenticação Moderna para [Office 2013 em dispositivos Windows.](../security-and-compliance/enable-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="bc818-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="bc818-151">Além disso, você precisa instalar as seguintes atualizações de abril para o Office 2013:</span><span class="sxs-lookup"><span data-stu-id="bc818-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="bc818-152">Descrição da atualização de segurança do Office 2013: 10 de abril de 2018</span><span class="sxs-lookup"><span data-stu-id="bc818-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="bc818-153">3 de abril de 2018, atualização para o Office 2013 (KB4018333)</span><span class="sxs-lookup"><span data-stu-id="bc818-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="bc818-154">**Não habilitar a ADAL.**</span><span class="sxs-lookup"><span data-stu-id="bc818-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="bc818-155">Se você não conseguir habilitar a ADAL no Office 2013, nossa recomendação é usar a Política de Grupo para desativar a Loja para os clientes do Office.</span><span class="sxs-lookup"><span data-stu-id="bc818-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="bc818-156">As informações sobre como desativar o aplicativo para configurações do Office estão localizadas [aqui.](https://technet.microsoft.com/library/cc178992.aspx)</span><span class="sxs-lookup"><span data-stu-id="bc818-156">Information on how to turn off the app for Office settings is located [here](https://technet.microsoft.com/library/cc178992.aspx).</span></span>

## <a name="related-articles"></a><span data-ttu-id="bc818-157">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="bc818-157">Related articles</span></span>

[<span data-ttu-id="bc818-158">Implantar suplementos no centro de administração</span><span class="sxs-lookup"><span data-stu-id="bc818-158">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[<span data-ttu-id="bc818-159">Gerenciar suplementos no centro de administração</span><span class="sxs-lookup"><span data-stu-id="bc818-159">Manage add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
