---
title: Perguntas frequentes ao ativar a proteção contra ameaças da Microsoft
description: Obtenha respostas para as perguntas mais frequentes sobre licenciamento, permissões, configurações iniciais e outros produtos e serviços relacionados à habilitação da proteção contra ameaças da Microsoft
keywords: perguntas frequentes, perguntas frequentes, GCC, introdução, habilitar MTP, proteção contra ameaças da Microsoft, M365, segurança, local dos dados, permissões necessárias, qualificação para licenças, página Configurações
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 6b0d8d9be0cc84e61a3228f79fc14f1bfc9f8a83
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198834"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a><span data-ttu-id="173ad-104">Perguntas frequentes ao ativar a proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="173ad-104">Frequently asked questions when turning on Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="173ad-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="173ad-105">**Applies to:**</span></span>
- <span data-ttu-id="173ad-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="173ad-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="173ad-107">Leia as respostas para as perguntas mais frequentes sobre como ativar a [proteção contra ameaças da Microsoft](microsoft-threat-protection.md), incluindo licenças e permissões necessárias, implantação de serviços de suporte e configurações iniciais.</span><span class="sxs-lookup"><span data-stu-id="173ad-107">Read responses to the most commonly asked questions about turning on [Microsoft Threat Protection](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="173ad-108">Para obter instruções sobre como ativar o serviço, [Leia ativar a proteção contra ameaças da Microsoft](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="173ad-108">For instructions on how to turn on the service, [read Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a><span data-ttu-id="173ad-109">Não tenho uma licença do Microsoft 365 e5.</span><span class="sxs-lookup"><span data-stu-id="173ad-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="173ad-110">Ainda posso usar a proteção contra ameaças da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="173ad-110">Can I still use Microsoft Threat Protection?</span></span>

<span data-ttu-id="173ad-111">Os clientes com as seguintes licenças não E5 podem usar a proteção contra ameaças da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="173ad-111">Customers with the following non-E5 licenses can use Microsoft Threat Protection:</span></span>

- <span data-ttu-id="173ad-112">Proteção Avançada contra Ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="173ad-112">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="173ad-113">Proteção Avançada contra Ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="173ad-113">Azure Advanced Threat Protection</span></span>
- <span data-ttu-id="173ad-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="173ad-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="173ad-115">Proteção contra Ameaças do Office 365 Advanced (Plano 2)</span><span class="sxs-lookup"><span data-stu-id="173ad-115">Office 365 Advanced Threat Protection (Plan 2)</span></span>
 
<span data-ttu-id="173ad-116">Para obter uma lista completa de licenças compatíveis, [Leia os requisitos de licenciamento](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="173ad-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a><span data-ttu-id="173ad-117">Preciso instalar ou implantar nada para começar a usar a proteção contra ameaças da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="173ad-117">Do I need to install or deploy anything to start using Microsoft Threat Protection?</span></span>

<span data-ttu-id="173ad-118">Não, a proteção contra ameaças da Microsoft consolida os dados dos serviços de segurança da Microsoft 365 que você já implantou.</span><span class="sxs-lookup"><span data-stu-id="173ad-118">No, Microsoft Threat Protection consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="173ad-119">Depois que você ativá-la, as experiências de incidentes, de automação e de caça começarão a funcionar dentro do escopo dos produtos implantados.</span><span class="sxs-lookup"><span data-stu-id="173ad-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="173ad-120">Se nenhum desses produtos estiver implantado corretamente, a proteção contra ameaças da Microsoft não exibirá nenhum dado e não poderá realizar qualquer ação.</span><span class="sxs-lookup"><span data-stu-id="173ad-120">If none of these products are properly deployed, Microsoft Threat Protection will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="173ad-121">Para otimizar suas experiências de proteção contra ameaças da Microsoft, recomendamos implantar *todos os* [produtos e serviços de segurança compatíveis com o Microsoft 365](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="173ad-121">To optimize your Microsoft Threat Protection experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a><span data-ttu-id="173ad-122">Onde funciona o processo de proteção contra ameaças da Microsoft e armazenar meus dados?</span><span class="sxs-lookup"><span data-stu-id="173ad-122">Where does Microsoft Threat Protection process and store my data?</span></span>
<span data-ttu-id="173ad-123">A proteção contra ameaças da Microsoft seleciona automaticamente um local ideal para o Data Center em que os dados consolidados são processados e armazenados.</span><span class="sxs-lookup"><span data-stu-id="173ad-123">Microsoft Threat Protection automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="173ad-124">Se você tiver o Microsoft defender ATP, ele selecionará o mesmo local usado pelo Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="173ad-124">If you have Microsoft Defender ATP, it selects the same location used by Microsoft Defender ATP.</span></span>

>[!NOTE]
><span data-ttu-id="173ad-125">O Microsoft defender ATP provisiona automaticamente nos data centers da União Européia (UE) quando ativado pela central de segurança do Azure.</span><span class="sxs-lookup"><span data-stu-id="173ad-125">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="173ad-126">A proteção contra ameaças da Microsoft será provisionada automaticamente no mesmo Data Center da UE para clientes que tenham provisionado o Microsoft defender ATP dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="173ad-126">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

<span data-ttu-id="173ad-127">O local do Data Center é mostrado antes e depois que o serviço é provisionado na página de configurações para proteção contra ameaças da Microsoft (**configurações > proteção contra ameaças da Microsoft**).</span><span class="sxs-lookup"><span data-stu-id="173ad-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft Threat Protection (**Settings > Microsoft Threat Protection**).</span></span> <span data-ttu-id="173ad-128">Se você preferir usar outro local de data center, selecione **precisa de ajuda?** no centro de segurança do Microsoft 365 para entrar em contato com o suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="173ad-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-threat-protection"></a><span data-ttu-id="173ad-129">Onde posso acessar a proteção contra ameaças da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="173ad-129">Where can I access Microsoft Threat Protection?</span></span>

<span data-ttu-id="173ad-130">A proteção contra ameaças da Microsoft está disponível no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="173ad-130">Microsoft Threat Protection is available in Microsoft 365 security center.</span></span> <span data-ttu-id="173ad-131">Para ir para a central de segurança, navegue até a URL [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="173ad-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a><span data-ttu-id="173ad-132">Que permissões preciso para acessar a proteção contra ameaças da Microsoft no centro de segurança do Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="173ad-132">What permissions do I need to access Microsoft Threat Protection in Microsoft 365 security center?</span></span>

<span data-ttu-id="173ad-133">Contas atribuídas às seguintes funções do Azure Active Directory (AD) podem acessar a funcionalidade e os dados da Proteção contra Ameaças da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="173ad-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>

- <span data-ttu-id="173ad-134">Administrador global</span><span class="sxs-lookup"><span data-stu-id="173ad-134">Global administrator</span></span>
- <span data-ttu-id="173ad-135">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="173ad-135">Security administrator</span></span>
- <span data-ttu-id="173ad-136">Operador de segurança</span><span class="sxs-lookup"><span data-stu-id="173ad-136">Security Operator</span></span>
- <span data-ttu-id="173ad-137">Leitor global</span><span class="sxs-lookup"><span data-stu-id="173ad-137">Global Reader</span></span>
- <span data-ttu-id="173ad-138">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="173ad-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="173ad-139">As configurações de controle de acesso baseado em função no Microsoft defender ATP influenciam o acesso aos dados.</span><span class="sxs-lookup"><span data-stu-id="173ad-139">Role-based access control settings in Microsoft Defender ATP influence access to data.</span></span> <span data-ttu-id="173ad-140">Para obter mais informações, leia sobre [o gerenciamento de acesso à proteção contra ameaças da Microsoft](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="173ad-140">For more information, read about [managing access to Microsoft Threat Protection](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a><span data-ttu-id="173ad-141">A que fuso horário a proteção de ameaças da Microsoft é padrão?</span><span class="sxs-lookup"><span data-stu-id="173ad-141">What time zone does Microsoft Threat Protection default to?</span></span>
<span data-ttu-id="173ad-142">Por padrão, a proteção contra ameaças da Microsoft exibe informações de hora no fuso horário UTC.</span><span class="sxs-lookup"><span data-stu-id="173ad-142">By default, Microsoft Threat Protection displays time information in the UTC time zone.</span></span> <span data-ttu-id="173ad-143">Você pode alterar essa configuração para usar seu fuso horário local.</span><span class="sxs-lookup"><span data-stu-id="173ad-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="173ad-144">Saiba como configurar o fuso horário</span><span class="sxs-lookup"><span data-stu-id="173ad-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a><span data-ttu-id="173ad-145">Como posso saber mais sobre o novo recurso de proteção contra ameaças da Microsoft e as atualizações da interface do usuário?</span><span class="sxs-lookup"><span data-stu-id="173ad-145">How can I learn about new Microsoft Threat Protection feature and UI updates?</span></span>

<span data-ttu-id="173ad-146">A Microsoft regularmente fornece informações através de vários canais, incluindo:</span><span class="sxs-lookup"><span data-stu-id="173ad-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="173ad-147">O [centro de mensagens](../../admin/manage/message-center.md) no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="173ad-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="173ad-148">Blogposts na [comunidade técnica de conformidade do Microsoft 365 security &](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="173ad-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="173ad-149">Obtenha as experiências disponíveis publicamente mais recentes, ativando os [recursos de visualização](preview.md).</span><span class="sxs-lookup"><span data-stu-id="173ad-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="173ad-150">A Proteção contra Ameaças da Microsoft está disponível para a nuvem governamental de comunidade dos EUA (GCC) ou para a GCC High (de alta confidencialidade)?</span><span class="sxs-lookup"><span data-stu-id="173ad-150">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="173ad-151">No momento, ela não está disponível.</span><span class="sxs-lookup"><span data-stu-id="173ad-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="173ad-152">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="173ad-152">Related topics</span></span>

- [<span data-ttu-id="173ad-153">Visão geral da Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="173ad-153">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="173ad-154">[Ative a proteção contra ameaças da Microsoft](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="173ad-154">[Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>
- [<span data-ttu-id="173ad-155">Requisitos de licenciamento e outros pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="173ad-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="173ad-156">Implantar serviços com suporte</span><span class="sxs-lookup"><span data-stu-id="173ad-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="173ad-157">Ativar recursos de visualização</span><span class="sxs-lookup"><span data-stu-id="173ad-157">Turn on preview features</span></span>](preview.md)
