---
title: Perguntas frequentes ao ativar o Microsoft 365 defender
description: Obtenha respostas para as perguntas mais frequentes sobre licenciamento, permissões, configurações iniciais e outros produtos e serviços relacionados à habilitação do Microsoft 365 defender
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
ms.openlocfilehash: 3dae9f208f5bb08d694322eb9f7cff35986930da
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920485"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="f02cf-104">Perguntas frequentes ao ativar o Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="f02cf-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f02cf-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f02cf-105">**Applies to:**</span></span>
- <span data-ttu-id="f02cf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f02cf-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f02cf-107">Leia as respostas para as perguntas mais frequentes sobre a ativação do [Microsoft 365 defender](microsoft-threat-protection.md), incluindo as licenças e permissões necessárias, a implantação de serviços de suporte e as configurações iniciais.</span><span class="sxs-lookup"><span data-stu-id="f02cf-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="f02cf-108">Para obter instruções sobre como ativar o serviço, [Leia ativar o Microsoft 365 defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="f02cf-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="f02cf-109">Não tenho uma licença do Microsoft 365 e5.</span><span class="sxs-lookup"><span data-stu-id="f02cf-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="f02cf-110">Ainda posso usar o Microsoft 365 defender?</span><span class="sxs-lookup"><span data-stu-id="f02cf-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="f02cf-111">Os clientes com as seguintes licenças não E5 podem usar o Microsoft 365 defender:</span><span class="sxs-lookup"><span data-stu-id="f02cf-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="f02cf-112">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f02cf-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="f02cf-113">Microsoft Defender para Identidade</span><span class="sxs-lookup"><span data-stu-id="f02cf-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="f02cf-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f02cf-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="f02cf-115">Defender para Office 365 (plano 2)</span><span class="sxs-lookup"><span data-stu-id="f02cf-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="f02cf-116">Para obter uma lista completa de licenças compatíveis, [Leia os requisitos de licenciamento](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="f02cf-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="f02cf-117">Preciso instalar ou implantar nada para começar a usar o Microsoft 365 defender?</span><span class="sxs-lookup"><span data-stu-id="f02cf-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="f02cf-118">Não, o Microsoft 365 defender consolida dados dos serviços de segurança da Microsoft 365 que você já implantou.</span><span class="sxs-lookup"><span data-stu-id="f02cf-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="f02cf-119">Depois que você ativá-la, as experiências de incidentes, de automação e de caça começarão a funcionar dentro do escopo dos produtos implantados.</span><span class="sxs-lookup"><span data-stu-id="f02cf-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="f02cf-120">Se nenhum desses produtos estiver implantado corretamente, o Microsoft 365 defender não exibirá nenhum dado e não poderá realizar qualquer ação.</span><span class="sxs-lookup"><span data-stu-id="f02cf-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="f02cf-121">Para otimizar as experiências do Microsoft 365 defender, recomendamos implantar *todos os* [produtos e serviços de segurança da Microsoft 365](deploy-supported-services.md)suportados.</span><span class="sxs-lookup"><span data-stu-id="f02cf-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="f02cf-122">Onde o Microsoft 365 defender processa e armazena meus dados?</span><span class="sxs-lookup"><span data-stu-id="f02cf-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="f02cf-123">O Microsoft 365 defender seleciona automaticamente um local ideal para o Data Center em que os dados consolidados são processados e armazenados.</span><span class="sxs-lookup"><span data-stu-id="f02cf-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="f02cf-124">Se você tiver o Microsoft defender para ponto de extremidade, ele selecionará o mesmo local usado pelo defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f02cf-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="f02cf-125">O Microsoft defender for Endpoint provisiona automaticamente nos data centers da União Europeia (UE) quando ativado pelo Azure defender.</span><span class="sxs-lookup"><span data-stu-id="f02cf-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="f02cf-126">O Microsoft 365 defender será automaticamente provisionado no mesmo Data Center da UE para clientes que tenham provisionado o Microsoft defender para ponto de extremidade dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="f02cf-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="f02cf-127">O local do Data Center é mostrado antes e depois que o serviço é provisionado na página de configurações do Microsoft 365 defender ( **configurações > Microsoft 365 defender** ).</span><span class="sxs-lookup"><span data-stu-id="f02cf-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender ( **Settings > Microsoft 365 Defender** ).</span></span> <span data-ttu-id="f02cf-128">Se você preferir usar outro local de data center, selecione **precisa de ajuda?** no centro de segurança do Microsoft 365 para entrar em contato com o suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f02cf-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="f02cf-129">Onde posso acessar o Microsoft 365 defender?</span><span class="sxs-lookup"><span data-stu-id="f02cf-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="f02cf-130">O Microsoft 365 defender está disponível na central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f02cf-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="f02cf-131">Para ir para a central de segurança, navegue até a URL [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="f02cf-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="f02cf-132">Quais permissões são necessárias para acessar o Microsoft 365 defender na central de segurança da Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="f02cf-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="f02cf-133">As contas atribuídas às seguintes funções do Azure Active Directory (AD) podem acessar a funcionalidade e os dados do Microsoft 365 defender:</span><span class="sxs-lookup"><span data-stu-id="f02cf-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="f02cf-134">Administrador global</span><span class="sxs-lookup"><span data-stu-id="f02cf-134">Global administrator</span></span>
- <span data-ttu-id="f02cf-135">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="f02cf-135">Security administrator</span></span>
- <span data-ttu-id="f02cf-136">Operador de segurança</span><span class="sxs-lookup"><span data-stu-id="f02cf-136">Security Operator</span></span>
- <span data-ttu-id="f02cf-137">Leitor global</span><span class="sxs-lookup"><span data-stu-id="f02cf-137">Global Reader</span></span>
- <span data-ttu-id="f02cf-138">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="f02cf-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="f02cf-139">As configurações de controle de acesso baseado em função no Microsoft defender para ponto de extremidade influenciam o acesso aos dados.</span><span class="sxs-lookup"><span data-stu-id="f02cf-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="f02cf-140">Para obter mais informações, leia sobre como [gerenciar o acesso ao Microsoft 365 defender](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f02cf-140">For more information, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="f02cf-141">A que fuso horário o Microsoft 365 defender tem como padrão?</span><span class="sxs-lookup"><span data-stu-id="f02cf-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="f02cf-142">Por padrão, o Microsoft 365 defender exibe informações de hora no fuso horário UTC.</span><span class="sxs-lookup"><span data-stu-id="f02cf-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="f02cf-143">Você pode alterar essa configuração para usar seu fuso horário local.</span><span class="sxs-lookup"><span data-stu-id="f02cf-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="f02cf-144">Saiba como configurar o fuso horário</span><span class="sxs-lookup"><span data-stu-id="f02cf-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="f02cf-145">Como posso saber mais sobre as novas atualizações do recurso Microsoft 365 defender e da interface do usuário?</span><span class="sxs-lookup"><span data-stu-id="f02cf-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="f02cf-146">A Microsoft regularmente fornece informações através de vários canais, incluindo:</span><span class="sxs-lookup"><span data-stu-id="f02cf-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="f02cf-147">O [centro de mensagens](../../admin/manage/message-center.md) no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f02cf-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="f02cf-148">Blogposts na [comunidade técnica de conformidade do Microsoft 365 security &](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="f02cf-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="f02cf-149">Obtenha as experiências disponíveis publicamente mais recentes, ativando os [recursos de visualização](preview.md).</span><span class="sxs-lookup"><span data-stu-id="f02cf-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="f02cf-150">O Microsoft 365 defender está disponível para a nuvem da Comunidade dos EUA (GCC) ou GCC High?</span><span class="sxs-lookup"><span data-stu-id="f02cf-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="f02cf-151">No momento, ela não está disponível.</span><span class="sxs-lookup"><span data-stu-id="f02cf-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f02cf-152">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f02cf-152">Related topics</span></span>

- [<span data-ttu-id="f02cf-153">Visão geral do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="f02cf-153">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="f02cf-154">[Ative o Microsoft 365 defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="f02cf-154">[Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>
- [<span data-ttu-id="f02cf-155">Requisitos de licenciamento e outros pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f02cf-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="f02cf-156">Implantar serviços com suporte</span><span class="sxs-lookup"><span data-stu-id="f02cf-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="f02cf-157">Habilitar recursos de prévia</span><span class="sxs-lookup"><span data-stu-id="f02cf-157">Turn on preview features</span></span>](preview.md)
