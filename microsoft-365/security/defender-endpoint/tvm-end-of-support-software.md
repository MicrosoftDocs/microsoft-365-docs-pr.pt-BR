---
title: Planejar versões de software e software de fim de suporte
description: Descubra e planeje versões de software e software que não são mais suportadas e não receberão atualizações de segurança.
keywords: Gerenciamento de Ameaças e Vulnerabilidades, recomendação de segurança de TV do Microsoft Defender para Endpoint, recomendação de segurança cibernética, recomendação de segurança a ação
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1800cfdabd402321c49b737eff7f9d67639eb300
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52688996"
---
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a><span data-ttu-id="cf97d-104">Planejar versões de software e software de fim de suporte com Gerenciamento de Ameaças e Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="cf97d-104">Plan for end-of-support software and software versions with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cf97d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="cf97d-105">**Applies to:**</span></span>

- [<span data-ttu-id="cf97d-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="cf97d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="cf97d-107">Ameaça e Gerenciamento de Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="cf97d-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="cf97d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf97d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="cf97d-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="cf97d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cf97d-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="cf97d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="cf97d-111">O fim do suporte (EOS), também conhecido como EOL (fim da vida útil), para versões de software ou software significa que eles não serão mais suportados ou atendidos e não receberão atualizações de segurança.</span><span class="sxs-lookup"><span data-stu-id="cf97d-111">End-of-support (EOS), otherwise known as end-of-life (EOL), for software or software versions means that they will no longer be supported or serviced, and will not receive security updates.</span></span> <span data-ttu-id="cf97d-112">Quando você usa versões de software ou software com suporte final, você está expondo sua organização a vulnerabilidades de segurança, riscos legais e financeiros.</span><span class="sxs-lookup"><span data-stu-id="cf97d-112">When you use software or software versions with ended support, you're exposing your organization to security vulnerabilities, legal, and financial risks.</span></span>

<span data-ttu-id="cf97d-113">É fundamental que os administradores de segurança e DES trabalhem juntos e garantam que o inventário de software da organização seja configurado para obter resultados ideais, conformidade e um ecossistema de rede saudável.</span><span class="sxs-lookup"><span data-stu-id="cf97d-113">It's crucial for Security and IT Administrators to work together and ensure that the organization's software inventory is configured for optimal results, compliance, and a healthy network ecosystem.</span></span> <span data-ttu-id="cf97d-114">Eles devem examinar as opções para remover ou substituir aplicativos que chegaram às versões de fim de suporte e atualização que não são mais suportadas.</span><span class="sxs-lookup"><span data-stu-id="cf97d-114">They should examine the options to remove or replace apps that have reached end-of-support and update versions that are no longer supported.</span></span> <span data-ttu-id="cf97d-115">É melhor criar e implementar um plano **antes do** final das datas de suporte.</span><span class="sxs-lookup"><span data-stu-id="cf97d-115">It's best to create and implement a plan **before** the end of support dates.</span></span>

>[!NOTE]
> <span data-ttu-id="cf97d-116">A funcionalidade de fim de suporte está disponível apenas para produtos Windows.</span><span class="sxs-lookup"><span data-stu-id="cf97d-116">End-of-support capability is currently available only for Windows products.</span></span>

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a><span data-ttu-id="cf97d-117">Encontre versões de software ou software que não são mais suportadas</span><span class="sxs-lookup"><span data-stu-id="cf97d-117">Find software or software versions that are no longer supported</span></span>

1. <span data-ttu-id="cf97d-118">No menu Gerenciamento de Ameaças e Vulnerabilidades, navegue até [**Recomendações de segurança**](tvm-security-recommendation.md).</span><span class="sxs-lookup"><span data-stu-id="cf97d-118">From the threat and vulnerability management menu, navigate to [**Security recommendations**](tvm-security-recommendation.md).</span></span>
2. <span data-ttu-id="cf97d-119">Vá para o **painel Filtros** e procure a seção marcas.</span><span class="sxs-lookup"><span data-stu-id="cf97d-119">Go to the **Filters** panel and look for the tags section.</span></span> <span data-ttu-id="cf97d-120">Selecione uma ou mais opções de marca EOS.</span><span class="sxs-lookup"><span data-stu-id="cf97d-120">Select one or more of the EOS tag options.</span></span> <span data-ttu-id="cf97d-121">Em **seguida, aplique**.</span><span class="sxs-lookup"><span data-stu-id="cf97d-121">Then **Apply**.</span></span>

    ![Marcas de captura de tela que dizem software EOS, versões do EOS e versões futuras do EOS.](images/tvm-eos-tag.png)

3. <span data-ttu-id="cf97d-123">Você verá uma lista de recomendações relacionadas ao software com suporte final, versões de software que são o fim do suporte ou versões com o próximo fim do suporte.</span><span class="sxs-lookup"><span data-stu-id="cf97d-123">You'll see a list of recommendations related to software with ended support, software versions that are end of support, or versions with upcoming end of support.</span></span> <span data-ttu-id="cf97d-124">Essas marcas também estão visíveis na [página de inventário de software.](tvm-software-inventory.md)</span><span class="sxs-lookup"><span data-stu-id="cf97d-124">These tags are also visible in the [software inventory](tvm-software-inventory.md) page.</span></span>

    ![Recomendações com a marca EOS.](images/tvm-eos-tags-column.png)

## <a name="list-of-versions-and-dates"></a><span data-ttu-id="cf97d-126">Lista de versões e datas</span><span class="sxs-lookup"><span data-stu-id="cf97d-126">List of versions and dates</span></span>

<span data-ttu-id="cf97d-127">Para exibir uma lista de versões que chegaram ao fim do suporte, fim ou suporte em breve, e essas datas, siga as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="cf97d-127">To view a list of versions that have reached end of support, or end or support soon, and those dates, follow the below steps:</span></span>

1. <span data-ttu-id="cf97d-128">Uma mensagem aparecerá no sobrevoo de recomendação de segurança para software com versões que chegaram ao fim do suporte ou chegarão ao fim do suporte em breve.</span><span class="sxs-lookup"><span data-stu-id="cf97d-128">A message will appear in the security recommendation flyout for software with versions that have reached end of support, or will reach end of support soon.</span></span>

    ![Captura de tela do link de distribuição de versão.](images/eos-upcoming-eos.png)

2. <span data-ttu-id="cf97d-130">Selecione o link **de distribuição** de versão para ir para a página de análise de software.</span><span class="sxs-lookup"><span data-stu-id="cf97d-130">Select the **version distribution** link to go to the software drill-down page.</span></span> <span data-ttu-id="cf97d-131">Lá, você pode ver uma lista filtrada de versões com marcas que as identificam como fim do suporte ou o próximo fim do suporte.</span><span class="sxs-lookup"><span data-stu-id="cf97d-131">There, you can see a filtered list of versions with tags identifying them as end of support, or upcoming end of support.</span></span>

    ![Captura de tela da página de detalhamento de software com o fim do software de suporte.](images/software-drilldown-eos.png)

3. <span data-ttu-id="cf97d-133">Selecione uma das versões na tabela a ser aberta.</span><span class="sxs-lookup"><span data-stu-id="cf97d-133">Select one of the versions in the table to open.</span></span> <span data-ttu-id="cf97d-134">Por exemplo, versão 10.0.18362.1.</span><span class="sxs-lookup"><span data-stu-id="cf97d-134">For example, version 10.0.18362.1.</span></span> <span data-ttu-id="cf97d-135">Um flyout aparecerá com a data de término do suporte.</span><span class="sxs-lookup"><span data-stu-id="cf97d-135">A flyout will appear with the end of support date.</span></span>

    ![Captura de tela da data de término do suporte.](images/version-eos-date.png)

<span data-ttu-id="cf97d-137">Depois de identificar quais versões de software e software são vulneráveis devido ao status de fim de suporte, você deve decidir se as atualizará ou removerá da sua organização.</span><span class="sxs-lookup"><span data-stu-id="cf97d-137">Once you identify which software and software versions are vulnerable due to their end-of-support status, you must decide whether to update or remove them from your organization.</span></span> <span data-ttu-id="cf97d-138">Isso reduzirá a exposição de suas organizações a vulnerabilidades e ameaças persistentes avançadas.</span><span class="sxs-lookup"><span data-stu-id="cf97d-138">Doing so will lower your organizations exposure to vulnerabilities and advanced persistent threats.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cf97d-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cf97d-139">Related topics</span></span>

- [<span data-ttu-id="cf97d-140">Visão geral Gerenciamento de Vulnerabilidades ameaça</span><span class="sxs-lookup"><span data-stu-id="cf97d-140">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="cf97d-141">Recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="cf97d-141">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="cf97d-142">Inventário de software</span><span class="sxs-lookup"><span data-stu-id="cf97d-142">Software inventory</span></span>](tvm-software-inventory.md)
