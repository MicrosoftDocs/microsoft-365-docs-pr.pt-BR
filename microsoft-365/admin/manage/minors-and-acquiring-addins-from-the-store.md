---
title: Secundárias e aquisição de complementos da Loja
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Saiba mais sobre os regulamentos do RGPD (Regulamento Geral de Proteção de Dados) que regem os dados pessoais de menores.
ms.openlocfilehash: e7f53a5a6b64f29f5029f0080fef44439c926edb
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580913"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="9540d-103">Secundárias e aquisição de complementos da Loja</span><span class="sxs-lookup"><span data-stu-id="9540d-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="9540d-104">O RGPD (Regulamento Geral de Proteção de Dados) é uma regulamentação da União Europeia que entra em vigor em 25 de maio de 2018.</span><span class="sxs-lookup"><span data-stu-id="9540d-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="9540d-105">Ele dá aos usuários direitos e proteção de seus dados.</span><span class="sxs-lookup"><span data-stu-id="9540d-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="9540d-106">Um dos aspectos do RGPD é que os menores não podem ter seus dados pessoais enviados às partes que seu pai ou responsável não aprovou.</span><span class="sxs-lookup"><span data-stu-id="9540d-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="9540d-107">A idade específica definida como secundária depende da região onde o indivíduo está localizado.</span><span class="sxs-lookup"><span data-stu-id="9540d-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="9540d-108">As regiões que têm regulamentos estatutários sobre o consentimento dos pais incluem os Estados Unidos, a Coreia do Sul, o Reino Unido e a União Europeia.</span><span class="sxs-lookup"><span data-stu-id="9540d-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="9540d-109">Para essas regiões, um secundário será bloqueado (por Azure Active Directory) de obter novos Office novos Office da Loja e executar os complementos que foram adquiridos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9540d-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="9540d-110">Para países sem regulamentos estatutários, não haverá restrições de download.</span><span class="sxs-lookup"><span data-stu-id="9540d-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="9540d-111">Um usuário é determinado como um secundário com base nos dados especificados em Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9540d-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="9540d-112">O administrador da organização é responsável por declarar a faixa etária legal e o consentimento dos pais para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="9540d-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="9540d-113">Se o pai/responsável consentir com um menor usando um complemento específico, o administrador da organização poderá usar a implantação centralizada para implantar esse complemento em todos os menores que tenham consentimento.</span><span class="sxs-lookup"><span data-stu-id="9540d-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="9540d-114">Para ser compatível com o RGPD para menores, você precisa garantir que uma das seguintes builds de Office seja implantada em sua escola/organização.</span><span class="sxs-lookup"><span data-stu-id="9540d-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="9540d-115">**Para Word, Excel, PowerPoint e Project**:</span><span class="sxs-lookup"><span data-stu-id="9540d-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="9540d-116">**Plataforma**</span><span class="sxs-lookup"><span data-stu-id="9540d-116">**Platform**</span></span> <br/> |<span data-ttu-id="9540d-117">**Número de compilação**</span><span class="sxs-lookup"><span data-stu-id="9540d-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="9540d-118">Microsoft 365 Apps para Grandes Empresas (Canal Atual)</span><span class="sxs-lookup"><span data-stu-id="9540d-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="9540d-119">9001.2138</span><span class="sxs-lookup"><span data-stu-id="9540d-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="9540d-120">Microsoft 365 Apps para Grandes Empresas (Canal de Enterprise Semes Enterprise)</span><span class="sxs-lookup"><span data-stu-id="9540d-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="9540d-121">8431.2159</span><span class="sxs-lookup"><span data-stu-id="9540d-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="9540d-122">Office 2016 para Windows</span><span class="sxs-lookup"><span data-stu-id="9540d-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="9540d-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="9540d-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="9540d-124">Office 2013 para Windows</span><span class="sxs-lookup"><span data-stu-id="9540d-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="9540d-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="9540d-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="9540d-126">Office 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="9540d-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="9540d-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="9540d-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="9540d-128">Office na Web</span><span class="sxs-lookup"><span data-stu-id="9540d-128">Office for the web</span></span>  <br/> |<span data-ttu-id="9540d-129">N/A</span><span class="sxs-lookup"><span data-stu-id="9540d-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="9540d-130">**Para Outlook**:</span><span class="sxs-lookup"><span data-stu-id="9540d-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="9540d-131">**Plataforma**</span><span class="sxs-lookup"><span data-stu-id="9540d-131">**Platform**</span></span> <br/> |<span data-ttu-id="9540d-132">**Número de compilação**</span><span class="sxs-lookup"><span data-stu-id="9540d-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="9540d-133">Outlook 2016 para Windows (MSI)</span><span class="sxs-lookup"><span data-stu-id="9540d-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="9540d-134">Build No TBD</span><span class="sxs-lookup"><span data-stu-id="9540d-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="9540d-135">Outlook 2016 para Windows (C2R)</span><span class="sxs-lookup"><span data-stu-id="9540d-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="9540d-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="9540d-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="9540d-137">Office 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="9540d-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="9540d-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="9540d-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="9540d-139">Outlook celular para iOS</span><span class="sxs-lookup"><span data-stu-id="9540d-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="9540d-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="9540d-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="9540d-141">Outlook celular para Android</span><span class="sxs-lookup"><span data-stu-id="9540d-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="9540d-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="9540d-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="9540d-143">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="9540d-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="9540d-144">N/A</span><span class="sxs-lookup"><span data-stu-id="9540d-144">N/A</span></span>  <br/> |

 <span data-ttu-id="9540d-145">**Office requisitos de 2013**</span><span class="sxs-lookup"><span data-stu-id="9540d-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="9540d-146">Word, Excel e PowerPoint 2013 para Windows darão suporte às mesmas verificações secundárias se a Biblioteca de Autenticação do Active Directory (ADAL) estiver habilitada.</span><span class="sxs-lookup"><span data-stu-id="9540d-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="9540d-147">Há duas opções de conformidade, conforme explicado em seguida.</span><span class="sxs-lookup"><span data-stu-id="9540d-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="9540d-148">**Habilitar a ADAL**.</span><span class="sxs-lookup"><span data-stu-id="9540d-148">**Enable ADAL**.</span></span> <span data-ttu-id="9540d-149">Este artigo explica como habilitar o ADAL para Office 2013: usando Microsoft 365 [autenticação](../../enterprise/modern-auth-for-office-2013-and-2016.md)moderna com Office clientes .</span><span class="sxs-lookup"><span data-stu-id="9540d-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](../../enterprise/modern-auth-for-office-2013-and-2016.md).</span></span><br/><span data-ttu-id="9540d-150">Você também precisa definir as chaves do Registro para habilitar o ADAL, conforme explicado em [Enable Modern Authentication for Office 2013 em Windows dispositivos](../security-and-compliance/enable-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="9540d-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="9540d-151">Além disso, você precisa instalar as seguintes atualizações de abril para Office 2013:</span><span class="sxs-lookup"><span data-stu-id="9540d-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="9540d-152">Descrição da atualização de segurança Office 2013: 10 de abril de 2018</span><span class="sxs-lookup"><span data-stu-id="9540d-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="9540d-153">3 de abril de 2018, atualização para Office 2013 (KB4018333)</span><span class="sxs-lookup"><span data-stu-id="9540d-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="9540d-154">**Não habilita o ADAL**.</span><span class="sxs-lookup"><span data-stu-id="9540d-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="9540d-155">Se você não conseguir habilitar o ADAL no Office 2013, nossa recomendação é usar a Política de Grupo para desativar a Loja para os clientes Office.</span><span class="sxs-lookup"><span data-stu-id="9540d-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="9540d-156">Informações sobre como desativar o aplicativo para Office configurações estão localizadas [aqui](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15)).</span><span class="sxs-lookup"><span data-stu-id="9540d-156">Information on how to turn off the app for Office settings is located [here](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15)).</span></span>

## <a name="related-articles"></a><span data-ttu-id="9540d-157">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="9540d-157">Related articles</span></span>

[<span data-ttu-id="9540d-158">Implantar suplementos no centro de administração</span><span class="sxs-lookup"><span data-stu-id="9540d-158">Deploy add-ins in the admin center</span></span>](./manage-deployment-of-add-ins.md)

[<span data-ttu-id="9540d-159">Gerenciar suplementos no centro de administração</span><span class="sxs-lookup"><span data-stu-id="9540d-159">Manage add-ins in the admin center</span></span>](./manage-addins-in-the-admin-center.md)
