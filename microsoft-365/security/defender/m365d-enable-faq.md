---
title: Frequentemente faz perguntas ao ligar Microsoft 365 Defender
description: Obtenha respostas para as perguntas mais comumente feitas sobre licenciamento, permissões, configurações iniciais e outros produtos e serviços relacionados à habilitação de Microsoft 365 Defender
keywords: perguntas frequentes, perguntas faq, GCC, começar, habilitar Microsoft 365 Defender, Microsoft 365 Defender, M365, segurança, localização de dados, permissões necessárias, elegibilidade da licença, página de configurações
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
ms.openlocfilehash: 008e3cc6ee65597a032aa932b74a64ac591927f2
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572760"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="2839c-104">Frequentemente faz perguntas ao ligar Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2839c-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2839c-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2839c-105">**Applies to:**</span></span>
- <span data-ttu-id="2839c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2839c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2839c-107">Leia respostas às perguntas mais comumente feitas sobre ligar [Microsoft 365 Defender](microsoft-365-defender.md), incluindo licenças e permissões necessárias, implantação de serviços de suporte e configurações iniciais.</span><span class="sxs-lookup"><span data-stu-id="2839c-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-365-defender.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="2839c-108">Para obter instruções sobre como ativar o serviço, [leia Ativar Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="2839c-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="2839c-109">Não tenho licença Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="2839c-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="2839c-110">Ainda posso usar Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="2839c-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="2839c-111">Os clientes com as seguintes licenças não-E5 podem usar Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="2839c-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="2839c-112">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2839c-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="2839c-113">Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="2839c-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="2839c-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2839c-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="2839c-115">Microsoft Defender para Office 365 (Plano 2)</span><span class="sxs-lookup"><span data-stu-id="2839c-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="2839c-116">Para obter uma lista completa de licenças suportadas, [leia os requisitos de licenciamento.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="2839c-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="2839c-117">Preciso instalar ou implantar alguma coisa para começar a usar Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="2839c-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="2839c-118">Não, Microsoft 365 Defender consolida dados de Microsoft 365 serviços de segurança que você já implantou.</span><span class="sxs-lookup"><span data-stu-id="2839c-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="2839c-119">Uma vez que você ligá-lo, experiências de incidente, automação e caça começarão a trabalhar dentro do escopo dos produtos implantados.</span><span class="sxs-lookup"><span data-stu-id="2839c-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="2839c-120">Se nenhum desses produtos for devidamente implantado, Microsoft 365 Defender não exibirá nenhum dado e não poderá tomar nenhuma ação.</span><span class="sxs-lookup"><span data-stu-id="2839c-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="2839c-121">Para otimizar suas experiências Microsoft 365 Defender, recomendamos a implantação de *todos os* produtos e serviços de segurança [Microsoft 365 suportados.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="2839c-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="2839c-122">Onde Microsoft 365 o processo do Defender e armazena meus dados?</span><span class="sxs-lookup"><span data-stu-id="2839c-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="2839c-123">Microsoft 365 O Defender seleciona automaticamente um local ideal para o data center onde os dados consolidados são processados e armazenados.</span><span class="sxs-lookup"><span data-stu-id="2839c-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="2839c-124">Se você tiver o Microsoft Defender para endpoint, ele selecionará o mesmo local usado pelo Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2839c-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="2839c-125">O Microsoft Defender for Endpoint fornece automaticamente nos data centers da União Europeia (UE) quando ligado através do Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="2839c-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="2839c-126">Microsoft 365 O Defender será automaticamente provisionado no mesmo data center da UE para clientes que provisionaram o Microsoft Defender para endpoint desta maneira.</span><span class="sxs-lookup"><span data-stu-id="2839c-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="2839c-127">O local do data center é mostrado antes e depois do serviço ser provisionado na página de configurações do Microsoft 365 Defender (**Configurações > Microsoft 365 Defender).**</span><span class="sxs-lookup"><span data-stu-id="2839c-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="2839c-128">Se você preferir usar outro local de data center, selecione **Precisar de ajuda?** no Microsoft 365 centro de segurança para entrar em contato com o suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2839c-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="2839c-129">Onde posso acessar Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="2839c-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="2839c-130">Microsoft 365 O Defender está disponível no centro de segurança Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2839c-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="2839c-131">Para ir ao centro de segurança, navegue até a URL [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="2839c-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="2839c-132">Que permissões preciso para acessar Microsoft 365 Defender no centro de segurança Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="2839c-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="2839c-133">As contas atribuídas às seguintes funções de Azure Active Directory (Azure AD) podem acessar Microsoft 365 funcionalidade e dados do Defender:</span><span class="sxs-lookup"><span data-stu-id="2839c-133">Accounts assigned the following Azure Active Directory (Azure AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="2839c-134">Administrador global</span><span class="sxs-lookup"><span data-stu-id="2839c-134">Global administrator</span></span>
- <span data-ttu-id="2839c-135">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="2839c-135">Security administrator</span></span>
- <span data-ttu-id="2839c-136">Operador de segurança</span><span class="sxs-lookup"><span data-stu-id="2839c-136">Security Operator</span></span>
- <span data-ttu-id="2839c-137">Leitor global</span><span class="sxs-lookup"><span data-stu-id="2839c-137">Global Reader</span></span>
- <span data-ttu-id="2839c-138">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="2839c-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="2839c-139">As configurações de controle de acesso baseadas em função no Microsoft Defender for Endpoint influenciam o acesso aos dados.</span><span class="sxs-lookup"><span data-stu-id="2839c-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="2839c-140">Para mais informações, leia sobre [como gerenciar o acesso ao Microsoft 365 Defender](m365d-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="2839c-140">For more information, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="2839c-141">Para que fuso horário Microsoft 365 o Defender é padrão?</span><span class="sxs-lookup"><span data-stu-id="2839c-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="2839c-142">Por padrão, Microsoft 365 Defender exibe informações de tempo no fuso horário UTC.</span><span class="sxs-lookup"><span data-stu-id="2839c-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="2839c-143">Você pode alterar esta configuração para usar o fuso horário local.</span><span class="sxs-lookup"><span data-stu-id="2839c-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="2839c-144">Saiba como definir o fuso horário</span><span class="sxs-lookup"><span data-stu-id="2839c-144">Learn about setting the time zone</span></span>](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="2839c-145">Como posso aprender sobre o novo recurso Microsoft 365 Defender e atualizações de interface do usuário?</span><span class="sxs-lookup"><span data-stu-id="2839c-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="2839c-146">A Microsoft fornece regularmente informações através dos vários canais, incluindo:</span><span class="sxs-lookup"><span data-stu-id="2839c-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="2839c-147">O [centro de mensagens](../../admin/manage/message-center.md) em Microsoft 365 centro administrativo</span><span class="sxs-lookup"><span data-stu-id="2839c-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="2839c-148">Blogs na [comunidade de tecnologia de segurança Microsoft 365 & conformidade](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="2839c-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="2839c-149">Obtenha as últimas experiências disponíveis ao público, ligando [os recursos de pré-visualização](preview.md).</span><span class="sxs-lookup"><span data-stu-id="2839c-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="2839c-150">O Microsoft 365 Defender está disponível para Nuvem da Comunidade Governamental dos EUA (GCC) ou GCC High?</span><span class="sxs-lookup"><span data-stu-id="2839c-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="2839c-151">No momento, ela não está disponível.</span><span class="sxs-lookup"><span data-stu-id="2839c-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2839c-152">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2839c-152">Related topics</span></span>

- [<span data-ttu-id="2839c-153">Microsoft 365 Visão geral do defensor</span><span class="sxs-lookup"><span data-stu-id="2839c-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- <span data-ttu-id="2839c-154">[Ligue Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="2839c-154">[Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>
- [<span data-ttu-id="2839c-155">Requisitos de licenciamento e outros pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2839c-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="2839c-156">Implantar serviços com suporte</span><span class="sxs-lookup"><span data-stu-id="2839c-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="2839c-157">Habilitar recursos de prévia</span><span class="sxs-lookup"><span data-stu-id="2839c-157">Turn on preview features</span></span>](preview.md)
