---
title: Menores e aquisição de suplementos da loja
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
description: Saiba mais sobre as normas gerais de RGPD (regulamentação de proteção de dados) que governam os dados pessoais dos menores.
ms.openlocfilehash: dcf2c98906830e0007747e2dd90e67b9dc85a5bb
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103085"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="f304c-103">Menores e aquisição de suplementos da loja</span><span class="sxs-lookup"><span data-stu-id="f304c-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="f304c-104">A regulamentação geral de proteção de dados (RGPD) é uma regulamentação de União Européia que se torna efetiva 25 de maio de 2018.</span><span class="sxs-lookup"><span data-stu-id="f304c-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="f304c-105">Ele fornece direitos e proteção de seus dados aos usuários.</span><span class="sxs-lookup"><span data-stu-id="f304c-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="f304c-106">Um dos aspectos do RGPD é que os menores não podem ter seus dados pessoais enviados a partes que seu pai ou guardião não aprovou.</span><span class="sxs-lookup"><span data-stu-id="f304c-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="f304c-107">A idade específica definida como um secundário depende da região onde o indivíduo está localizado.</span><span class="sxs-lookup"><span data-stu-id="f304c-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="f304c-108">Regiões que têm regulamentações estatutárias sobre o consentimento dos pais incluem Estados Unidos, Coréia do Sul, Reino Unido e União Européia.</span><span class="sxs-lookup"><span data-stu-id="f304c-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="f304c-109">Para essas regiões, um pequeno será bloqueado (por meio do Azure Active Directory) para obter qualquer suplemento novo do Office a partir da loja e executar suplementos que foram adquiridos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f304c-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="f304c-110">Para países sem regulamentações legais, não haverá restrições de download.</span><span class="sxs-lookup"><span data-stu-id="f304c-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="f304c-111">Um usuário é determinado como um secundário com base nos dados especificados no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f304c-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="f304c-112">O administrador da organização é responsável por declarar o grupo de idades legais e o consentimento do responsável para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="f304c-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="f304c-113">Se o pai/guardião for enviado a um secundário usando um suplemento específico, o administrador da organização poderá usar a implantação centralizada para implantar esse suplemento em todos os menores que tiverem consentimento.</span><span class="sxs-lookup"><span data-stu-id="f304c-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="f304c-114">Ser compatível com o RGPD para menores que você precisa para garantir que uma das seguintes versões do Office seja implantada em sua escola/organização.</span><span class="sxs-lookup"><span data-stu-id="f304c-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="f304c-115">**Para Word, Excel, PowerPoint e Project**:</span><span class="sxs-lookup"><span data-stu-id="f304c-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="f304c-116">**Plataforma**</span><span class="sxs-lookup"><span data-stu-id="f304c-116">**Platform**</span></span> <br/> |<span data-ttu-id="f304c-117">**Número de compilação**</span><span class="sxs-lookup"><span data-stu-id="f304c-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="f304c-118">Microsoft 365 aplicativos para empresas (canal atual)</span><span class="sxs-lookup"><span data-stu-id="f304c-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="f304c-119">9001,2138</span><span class="sxs-lookup"><span data-stu-id="f304c-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="f304c-120">Microsoft 365 aplicativos para empresas (canal empresarial semestral)</span><span class="sxs-lookup"><span data-stu-id="f304c-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="f304c-121">8431,2159</span><span class="sxs-lookup"><span data-stu-id="f304c-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="f304c-122">Office 2016 para Windows</span><span class="sxs-lookup"><span data-stu-id="f304c-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="f304c-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="f304c-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="f304c-124">Office 2013 para Windows</span><span class="sxs-lookup"><span data-stu-id="f304c-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="f304c-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="f304c-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="f304c-126">Office 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="f304c-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="f304c-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="f304c-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="f304c-128">Office para a Web</span><span class="sxs-lookup"><span data-stu-id="f304c-128">Office for the web</span></span>  <br/> |<span data-ttu-id="f304c-129">N/D</span><span class="sxs-lookup"><span data-stu-id="f304c-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="f304c-130">**Para o Outlook**:</span><span class="sxs-lookup"><span data-stu-id="f304c-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="f304c-131">**Plataforma**</span><span class="sxs-lookup"><span data-stu-id="f304c-131">**Platform**</span></span> <br/> |<span data-ttu-id="f304c-132">**Número de compilação**</span><span class="sxs-lookup"><span data-stu-id="f304c-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="f304c-133">Outlook 2016 para Windows (MSI)</span><span class="sxs-lookup"><span data-stu-id="f304c-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="f304c-134">Compilação não TBD</span><span class="sxs-lookup"><span data-stu-id="f304c-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="f304c-135">Outlook 2016 para Windows (C2R)</span><span class="sxs-lookup"><span data-stu-id="f304c-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="f304c-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="f304c-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="f304c-137">Office 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="f304c-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="f304c-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="f304c-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="f304c-139">Outlook Mobile para iOS</span><span class="sxs-lookup"><span data-stu-id="f304c-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="f304c-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="f304c-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="f304c-141">Outlook Mobile para Android</span><span class="sxs-lookup"><span data-stu-id="f304c-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="f304c-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="f304c-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="f304c-143">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="f304c-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="f304c-144">N/D</span><span class="sxs-lookup"><span data-stu-id="f304c-144">N/A</span></span>  <br/> |

 <span data-ttu-id="f304c-145">**Requisitos do Office 2013**</span><span class="sxs-lookup"><span data-stu-id="f304c-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="f304c-146">O Word, o Excel e o PowerPoint 2013 para Windows oferecerão suporte às mesmas verificações secundárias se a biblioteca de autenticação do Active Directory (ADAL) estiver habilitada.</span><span class="sxs-lookup"><span data-stu-id="f304c-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="f304c-147">Há duas opções de conformidade, conforme explicado a seguir.</span><span class="sxs-lookup"><span data-stu-id="f304c-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="f304c-148">**Habilitar Adal**.</span><span class="sxs-lookup"><span data-stu-id="f304c-148">**Enable ADAL**.</span></span> <span data-ttu-id="f304c-149">Este artigo explica como habilitar a ADAL para o Office 2013: [usando a autenticação moderna da Microsoft 365 com clientes do Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).</span><span class="sxs-lookup"><span data-stu-id="f304c-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).</span></span><br/><span data-ttu-id="f304c-150">Você também precisa definir as chaves do registro para habilitar a ADAL, conforme explicado em [habilitar a autenticação moderna para o Office 2013 em dispositivos Windows](../security-and-compliance/enable-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="f304c-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="f304c-151">Além disso, você precisa instalar as seguintes atualizações de abril para o Office 2013:</span><span class="sxs-lookup"><span data-stu-id="f304c-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="f304c-152">Descrição da atualização de segurança para o Office 2013:10 de abril de 2018</span><span class="sxs-lookup"><span data-stu-id="f304c-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="f304c-153">3 de abril de 2018, atualização para o Office 2013 (KB4018333)</span><span class="sxs-lookup"><span data-stu-id="f304c-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="f304c-154">**Não habilite a Adal**.</span><span class="sxs-lookup"><span data-stu-id="f304c-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="f304c-155">Se você não conseguir habilitar a ADAL no Office 2013, nossa recomendação é usar a política de grupo para desativar o repositório para os clientes do Office.</span><span class="sxs-lookup"><span data-stu-id="f304c-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="f304c-156">As informações sobre como desativar as configurações de aplicativo para Office estão localizadas [aqui](https://technet.microsoft.com/library/cc178992.aspx).</span><span class="sxs-lookup"><span data-stu-id="f304c-156">Information on how to turn off the app for Office settings is located [here](https://technet.microsoft.com/library/cc178992.aspx).</span></span>

## <a name="related-articles"></a><span data-ttu-id="f304c-157">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="f304c-157">Related articles</span></span>

[<span data-ttu-id="f304c-158">Implantar suplementos no centro de administração</span><span class="sxs-lookup"><span data-stu-id="f304c-158">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[<span data-ttu-id="f304c-159">Gerenciar suplementos no centro de administração</span><span class="sxs-lookup"><span data-stu-id="f304c-159">Manage add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
