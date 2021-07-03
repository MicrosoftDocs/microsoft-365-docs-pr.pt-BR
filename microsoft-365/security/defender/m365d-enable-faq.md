---
title: Perguntas frequentes ao Microsoft 365 Defender
description: Obter respostas para as perguntas mais frequentes sobre licenciamento, permissões, configurações iniciais e outros produtos e serviços relacionados à habilitação de Microsoft 365 Defender
keywords: perguntas frequentes, perguntas frequentes, GCC, começar, habilitar Microsoft 365 Defender, Microsoft 365 Defender, M365, segurança, localização de dados, permissões necessárias, qualificação de licença, página de configurações
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
ms.openlocfilehash: 1ba049e9fe608ba8bd559180c5a30060b10ee9e0
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53285980"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="66955-104">Perguntas frequentes ao Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66955-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="66955-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="66955-105">**Applies to:**</span></span>
- <span data-ttu-id="66955-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66955-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="66955-107">Leia respostas às perguntas mais frequentes sobre como Microsoft 365 Defender [,](microsoft-365-defender.md)incluindo licenças e permissões necessárias, implantação de serviços de suporte e configurações iniciais.</span><span class="sxs-lookup"><span data-stu-id="66955-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-365-defender.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="66955-108">Para obter instruções sobre como ativar o serviço, [leia Ativar Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="66955-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="66955-109">Não tenho uma licença de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="66955-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="66955-110">Ainda posso usar Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="66955-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="66955-111">Os clientes com as seguintes licenças que não são do E5 podem usar Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="66955-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="66955-112">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="66955-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="66955-113">Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="66955-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="66955-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="66955-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="66955-115">Microsoft Defender para Office 365 (Plano 2)</span><span class="sxs-lookup"><span data-stu-id="66955-115">Defender for Office 365 (Plan 2)</span></span>

<span data-ttu-id="66955-116">Para uma lista completa de licenças com suporte, [leia os requisitos de licenciamento.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="66955-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="66955-117">Preciso instalar ou implantar algo para começar a usar Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="66955-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="66955-118">Não, Microsoft 365 Defender consolida dados Microsoft 365 serviços de segurança que você já implantou.</span><span class="sxs-lookup"><span data-stu-id="66955-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="66955-119">Depois que você a ativar, as experiências de incidente, automação e busca começarão a funcionar no escopo dos produtos implantados.</span><span class="sxs-lookup"><span data-stu-id="66955-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="66955-120">Se nenhum desses produtos for implantado corretamente, Microsoft 365 Defender não exibirá dados e não poderá tomar nenhuma ação.</span><span class="sxs-lookup"><span data-stu-id="66955-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="66955-121">Para otimizar suas experiências Microsoft 365 Defender, recomendamos  a implantação de todos os produtos e serviços Microsoft 365 segurança com [suporte.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="66955-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="66955-122">Onde o Microsoft 365 Defender processa e armazena meus dados?</span><span class="sxs-lookup"><span data-stu-id="66955-122">Where does Microsoft 365 Defender process and store my data?</span></span>

<span data-ttu-id="66955-123">Microsoft 365 Defender seleciona automaticamente um local ideal para o data center onde os dados consolidados são processados e armazenados.</span><span class="sxs-lookup"><span data-stu-id="66955-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="66955-124">Se você tiver o Microsoft Defender para Ponto de Extremidade, ele selecionará o mesmo local usado pelo Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="66955-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="66955-125">O Microsoft Defender para Ponto de Extremidade provisiona automaticamente em data centers da União Europeia (UE) quando ativado por meio do Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="66955-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="66955-126">Microsoft 365 Defender provisionamento automático no mesmo data center da UE para clientes que provisionou o Microsoft Defender para o Ponto de Extremidade dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="66955-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span>

<span data-ttu-id="66955-127">O local do data center é mostrado antes e depois que o serviço é provisionado na página de configurações para Microsoft 365 Defender (**Configurações > Microsoft 365 Defender**).</span><span class="sxs-lookup"><span data-stu-id="66955-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="66955-128">Se você preferir usar outro local do data center, selecione Precisa de **ajuda?** no centro de segurança Microsoft 365 para entrar em contato com o suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="66955-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="66955-129">Onde posso acessar Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="66955-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="66955-130">Microsoft 365 Defender está disponível no Microsoft 365 de segurança.</span><span class="sxs-lookup"><span data-stu-id="66955-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="66955-131">Para ir para o centro de segurança, navegue até a URL <https://security.microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="66955-131">To go to the security center, browse to the URL <https://security.microsoft.com>.</span></span>

## <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="66955-132">Quais permissões preciso para acessar Microsoft 365 Defender no Microsoft 365 de segurança?</span><span class="sxs-lookup"><span data-stu-id="66955-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="66955-133">As contas atribuídas às seguintes funções Azure Active Directory (Azure AD) podem acessar Microsoft 365 Defender funcionalidade e dados:</span><span class="sxs-lookup"><span data-stu-id="66955-133">Accounts assigned the following Azure Active Directory (Azure AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="66955-134">Administrador global</span><span class="sxs-lookup"><span data-stu-id="66955-134">Global administrator</span></span>
- <span data-ttu-id="66955-135">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="66955-135">Security administrator</span></span>
- <span data-ttu-id="66955-136">Operador de segurança</span><span class="sxs-lookup"><span data-stu-id="66955-136">Security Operator</span></span>
- <span data-ttu-id="66955-137">Leitor global</span><span class="sxs-lookup"><span data-stu-id="66955-137">Global Reader</span></span>
- <span data-ttu-id="66955-138">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="66955-138">Security Reader</span></span>

> [!NOTE]
> <span data-ttu-id="66955-139">As configurações de controle de acesso baseado em função no Microsoft Defender para Ponto de Extremidade influenciam o acesso aos dados.</span><span class="sxs-lookup"><span data-stu-id="66955-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="66955-140">Para obter mais informações, leia sobre como [gerenciar o acesso Microsoft 365 Defender](m365d-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="66955-140">For more information, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="66955-141">Qual fuso horário Microsoft 365 Defender padrão?</span><span class="sxs-lookup"><span data-stu-id="66955-141">What time zone does Microsoft 365 Defender default to?</span></span>

<span data-ttu-id="66955-142">Por padrão, Microsoft 365 Defender exibe informações de hora no fuso horário UTC.</span><span class="sxs-lookup"><span data-stu-id="66955-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="66955-143">Você pode alterar essa configuração para usar o fuso horário local.</span><span class="sxs-lookup"><span data-stu-id="66955-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="66955-144">Saiba mais sobre como definir o fuso horário</span><span class="sxs-lookup"><span data-stu-id="66955-144">Learn about setting the time zone</span></span>](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="66955-145">Como posso saber mais sobre novos recursos Microsoft 365 Defender e atualizações da interface do usuário?</span><span class="sxs-lookup"><span data-stu-id="66955-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="66955-146">A Microsoft fornece regularmente informações por meio dos vários canais, incluindo:</span><span class="sxs-lookup"><span data-stu-id="66955-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="66955-147">O [centro de mensagens](../../admin/manage/message-center.md) no Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="66955-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="66955-148">Blogposts na Microsoft 365 [de segurança & de conformidade](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="66955-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="66955-149">Obter as experiências mais recentes disponíveis publicamente, a partir de recursos [de visualização.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="66955-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="66955-150">O Microsoft 365 Defender está disponível para us Nuvem da Comunidade Governamental (GCC) ou GCC Alta?</span><span class="sxs-lookup"><span data-stu-id="66955-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>

<span data-ttu-id="66955-151">No momento, ela não está disponível.</span><span class="sxs-lookup"><span data-stu-id="66955-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="66955-152">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="66955-152">Related topics</span></span>

- [<span data-ttu-id="66955-153">Microsoft 365 Defender visão geral</span><span class="sxs-lookup"><span data-stu-id="66955-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- <span data-ttu-id="66955-154">[A Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="66955-154">[Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>
- [<span data-ttu-id="66955-155">Requisitos de licenciamento e outros pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="66955-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="66955-156">Implantar serviços com suporte</span><span class="sxs-lookup"><span data-stu-id="66955-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="66955-157">Habilitar recursos de prévia</span><span class="sxs-lookup"><span data-stu-id="66955-157">Turn on preview features</span></span>](preview.md)
