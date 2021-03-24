---
title: Perguntas frequentes ao ligar o Microsoft 365 Defender
description: Obter respostas para as perguntas mais frequentes sobre licenciamento, permissões, configurações iniciais e outros produtos e serviços relacionados à habilitação do Microsoft 365 Defender
keywords: perguntas frequentes, perguntas frequentes, GCC, começar, habilitar MTP, Proteção contra Ameaças da Microsoft, M365, segurança, localização de dados, permissões necessárias, qualificação de licença, página de configurações
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7482bf614e7cb3ffad6596f3c5d8bc554d46d912
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054507"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="8507b-104">Perguntas frequentes ao ligar o Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8507b-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8507b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8507b-105">**Applies to:**</span></span>
- <span data-ttu-id="8507b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8507b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8507b-107">Leia respostas às perguntas mais frequentes sobre como acionar o [Microsoft 365 Defender](microsoft-365-defender.md), incluindo licenças e permissões necessárias, implantação de serviços de suporte e configurações iniciais.</span><span class="sxs-lookup"><span data-stu-id="8507b-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-365-defender.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="8507b-108">Para obter instruções sobre como ativar o serviço, [leia Ativar o Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="8507b-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="8507b-109">Não tenho uma licença do Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="8507b-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="8507b-110">Ainda posso usar o Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="8507b-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="8507b-111">Os clientes com as seguintes licenças que não são do E5 podem usar o Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="8507b-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="8507b-112">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8507b-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="8507b-113">Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="8507b-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="8507b-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8507b-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="8507b-115">Defender para Office 365 (Plano 2)</span><span class="sxs-lookup"><span data-stu-id="8507b-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="8507b-116">Para uma lista completa de licenças com suporte, [leia os requisitos de licenciamento.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="8507b-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="8507b-117">Preciso instalar ou implantar algo para começar a usar o Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="8507b-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="8507b-118">Não, o Microsoft 365 Defender consolida dados dos serviços de segurança do Microsoft 365 que você já implantou.</span><span class="sxs-lookup"><span data-stu-id="8507b-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="8507b-119">Depois que você a ativar, as experiências de incidente, automação e busca começarão a funcionar no escopo dos produtos implantados.</span><span class="sxs-lookup"><span data-stu-id="8507b-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="8507b-120">Se nenhum desses produtos for implantado corretamente, o Microsoft 365 Defender não exibirá dados e não poderá tomar nenhuma ação.</span><span class="sxs-lookup"><span data-stu-id="8507b-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="8507b-121">Para otimizar suas experiências do Microsoft 365 Defender, recomendamos implantar todos os produtos e serviços de segurança do [Microsoft 365](deploy-supported-services.md)com suporte. </span><span class="sxs-lookup"><span data-stu-id="8507b-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="8507b-122">Onde o Microsoft 365 Defender processa e armazena meus dados?</span><span class="sxs-lookup"><span data-stu-id="8507b-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="8507b-123">O Microsoft 365 Defender seleciona automaticamente um local ideal para o data center onde os dados consolidados são processados e armazenados.</span><span class="sxs-lookup"><span data-stu-id="8507b-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="8507b-124">Se você tiver o Microsoft Defender para Ponto de Extremidade, ele selecionará o mesmo local usado pelo Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="8507b-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="8507b-125">O Microsoft Defender para Ponto de Extremidade provisiona automaticamente em data centers da União Europeia (UE) quando ativado por meio do Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="8507b-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="8507b-126">O Microsoft 365 Defender provisiona automaticamente no mesmo data center da UE para clientes que provisionam o Microsoft Defender para o Ponto de Extremidade dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="8507b-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="8507b-127">O local do data center é mostrado antes e depois que o serviço é provisionado na página de configurações do Microsoft 365 Defender (**Configurações > Microsoft 365 Defender**).</span><span class="sxs-lookup"><span data-stu-id="8507b-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="8507b-128">Se você preferir usar outro local do data center, selecione Precisa **de ajuda?** no Centro de segurança do Microsoft 365 para entrar em contato com o suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8507b-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="8507b-129">Onde posso acessar o Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="8507b-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="8507b-130">O Microsoft 365 Defender está disponível no Centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8507b-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="8507b-131">Para ir para o centro de segurança, navegue até a URL [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="8507b-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="8507b-132">Quais permissões preciso para acessar o Microsoft 365 Defender no Centro de segurança do Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="8507b-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="8507b-133">As contas atribuídas às seguintes funções do Azure Active Directory (AD) podem acessar a funcionalidade e os dados do Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="8507b-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="8507b-134">Administrador global</span><span class="sxs-lookup"><span data-stu-id="8507b-134">Global administrator</span></span>
- <span data-ttu-id="8507b-135">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="8507b-135">Security administrator</span></span>
- <span data-ttu-id="8507b-136">Operador de segurança</span><span class="sxs-lookup"><span data-stu-id="8507b-136">Security Operator</span></span>
- <span data-ttu-id="8507b-137">Leitor global</span><span class="sxs-lookup"><span data-stu-id="8507b-137">Global Reader</span></span>
- <span data-ttu-id="8507b-138">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="8507b-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="8507b-139">As configurações de controle de acesso baseado em função no Microsoft Defender para Ponto de Extremidade influenciam o acesso aos dados.</span><span class="sxs-lookup"><span data-stu-id="8507b-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="8507b-140">Para obter mais informações, leia sobre como [gerenciar o acesso ao Microsoft 365 Defender](m365d-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8507b-140">For more information, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="8507b-141">Para qual fuso horário o Microsoft 365 Defender é padrão?</span><span class="sxs-lookup"><span data-stu-id="8507b-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="8507b-142">Por padrão, o Microsoft 365 Defender exibe informações de hora no fuso horário UTC.</span><span class="sxs-lookup"><span data-stu-id="8507b-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="8507b-143">Você pode alterar essa configuração para usar o fuso horário local.</span><span class="sxs-lookup"><span data-stu-id="8507b-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="8507b-144">Saiba mais sobre como definir o fuso horário</span><span class="sxs-lookup"><span data-stu-id="8507b-144">Learn about setting the time zone</span></span>](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="8507b-145">Como saber mais sobre os novos recursos do Microsoft 365 Defender e as atualizações da interface do usuário?</span><span class="sxs-lookup"><span data-stu-id="8507b-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="8507b-146">A Microsoft fornece regularmente informações por meio dos vários canais, incluindo:</span><span class="sxs-lookup"><span data-stu-id="8507b-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="8507b-147">O [centro de mensagens](../../admin/manage/message-center.md) no Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8507b-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="8507b-148">Blogposts na comunidade técnica de segurança [do Microsoft 365 & conformidade](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="8507b-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="8507b-149">Obter as experiências mais recentes disponíveis publicamente, a partir de recursos [de visualização.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="8507b-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="8507b-150">O Microsoft 365 Defender está disponível para a GCC (Nuvem da Comunidade Governamental) dos EUA ou GCC High?</span><span class="sxs-lookup"><span data-stu-id="8507b-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="8507b-151">No momento, ela não está disponível.</span><span class="sxs-lookup"><span data-stu-id="8507b-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8507b-152">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8507b-152">Related topics</span></span>

- [<span data-ttu-id="8507b-153">Visão geral do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8507b-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- <span data-ttu-id="8507b-154">[A turn on Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="8507b-154">[Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>
- [<span data-ttu-id="8507b-155">Requisitos de licenciamento e outros pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8507b-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="8507b-156">Implantar serviços com suporte</span><span class="sxs-lookup"><span data-stu-id="8507b-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="8507b-157">Habilitar recursos de prévia</span><span class="sxs-lookup"><span data-stu-id="8507b-157">Turn on preview features</span></span>](preview.md)
