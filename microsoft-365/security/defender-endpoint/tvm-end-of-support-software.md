---
title: Planejar versões de software e software de fim de suporte
description: Descubra e planeje versões de software e software que não são mais suportadas e não receberão atualizações de segurança.
keywords: gerenciamento de ameaças e vulnerabilidades, recomendação de segurança de tvm mdatp, recomendação de segurança cibernética, recomendação de segurança a ação
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
ms.openlocfilehash: 29adf8a542d97a981a07dac167343f3774aa5af4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500150"
---
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a><span data-ttu-id="5d06d-104">Planejar versões de software e software de fim de suporte com gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="5d06d-104">Plan for end-of-support software and software versions with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5d06d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5d06d-105">**Applies to:**</span></span>

- [<span data-ttu-id="5d06d-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5d06d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="5d06d-107">Gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="5d06d-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="5d06d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d06d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5d06d-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="5d06d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5d06d-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="5d06d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="5d06d-111">O fim do suporte (EOS), também conhecido como EOL (fim da vida útil), para versões de software ou software significa que eles não serão mais suportados ou atendidos e não receberão atualizações de segurança.</span><span class="sxs-lookup"><span data-stu-id="5d06d-111">End-of-support (EOS), otherwise known as end-of-life (EOL), for software or software versions means that they will no longer be supported or serviced, and will not receive security updates.</span></span> <span data-ttu-id="5d06d-112">Quando você usa versões de software ou software com suporte final, você está expondo sua organização a vulnerabilidades de segurança, riscos legais e financeiros.</span><span class="sxs-lookup"><span data-stu-id="5d06d-112">When you use software or software versions with ended support, you're exposing your organization to security vulnerabilities, legal, and financial risks.</span></span>

<span data-ttu-id="5d06d-113">É fundamental que os administradores de segurança e DES trabalhem juntos e garantam que o inventário de software da organização seja configurado para obter resultados ideais, conformidade e um ecossistema de rede saudável.</span><span class="sxs-lookup"><span data-stu-id="5d06d-113">It's crucial for Security and IT Administrators to work together and ensure that the organization's software inventory is configured for optimal results, compliance, and a healthy network ecosystem.</span></span> <span data-ttu-id="5d06d-114">Eles devem examinar as opções para remover ou substituir aplicativos que chegaram às versões de fim de suporte e atualização que não são mais suportadas.</span><span class="sxs-lookup"><span data-stu-id="5d06d-114">They should examine the options to remove or replace apps that have reached end-of-support and update versions that are no longer supported.</span></span> <span data-ttu-id="5d06d-115">É melhor criar e implementar um plano **antes do** final das datas de suporte.</span><span class="sxs-lookup"><span data-stu-id="5d06d-115">It's best to create and implement a plan **before** the end of support dates.</span></span>

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a><span data-ttu-id="5d06d-116">Encontre versões de software ou software que não são mais suportadas</span><span class="sxs-lookup"><span data-stu-id="5d06d-116">Find software or software versions that are no longer supported</span></span>

1. <span data-ttu-id="5d06d-117">No menu gerenciamento de ameaças e vulnerabilidades, navegue até [**Recomendações de segurança.**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="5d06d-117">From the threat and vulnerability management menu, navigate to [**Security recommendations**](tvm-security-recommendation.md).</span></span>
2. <span data-ttu-id="5d06d-118">Vá para o **painel Filtros** e procure a seção marcas.</span><span class="sxs-lookup"><span data-stu-id="5d06d-118">Go to the **Filters** panel and look for the tags section.</span></span> <span data-ttu-id="5d06d-119">Selecione uma ou mais opções de marca EOS.</span><span class="sxs-lookup"><span data-stu-id="5d06d-119">Select one or more of the EOS tag options.</span></span> <span data-ttu-id="5d06d-120">Em **seguida, aplique**.</span><span class="sxs-lookup"><span data-stu-id="5d06d-120">Then **Apply**.</span></span>

    ![Marcas de captura de tela que dizem software EOS, versões do EOS e versões futuras do EOS.](images/tvm-eos-tag.png)

3. <span data-ttu-id="5d06d-122">Você verá uma lista de recomendações relacionadas ao software com suporte final, versões de software que são o fim do suporte ou versões com o próximo fim do suporte.</span><span class="sxs-lookup"><span data-stu-id="5d06d-122">You'll see a list of recommendations related to software with ended support, software versions that are end of support, or versions with upcoming end of support.</span></span> <span data-ttu-id="5d06d-123">Essas marcas também estão visíveis na [página de inventário de software.](tvm-software-inventory.md)</span><span class="sxs-lookup"><span data-stu-id="5d06d-123">These tags are also visible in the [software inventory](tvm-software-inventory.md) page.</span></span>

    ![Recomendações com a marca EOS.](images/tvm-eos-tags-column.png)

## <a name="list-of-versions-and-dates"></a><span data-ttu-id="5d06d-125">Lista de versões e datas</span><span class="sxs-lookup"><span data-stu-id="5d06d-125">List of versions and dates</span></span>

<span data-ttu-id="5d06d-126">Para exibir uma lista de versões que chegaram ao fim do suporte, fim ou suporte em breve, e essas datas, siga as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="5d06d-126">To view a list of versions that have reached end of support, or end or support soon, and those dates, follow the below steps:</span></span>

1. <span data-ttu-id="5d06d-127">Uma mensagem aparecerá no sobrevoo de recomendação de segurança para software com versões que chegaram ao fim do suporte ou chegarão ao fim do suporte em breve.</span><span class="sxs-lookup"><span data-stu-id="5d06d-127">A message will appear in the security recommendation flyout for software with versions that have reached end of support, or will reach end of support soon.</span></span>

    ![Captura de tela do link de distribuição de versão.](images/eos-upcoming-eos.png)

2. <span data-ttu-id="5d06d-129">Selecione o link **de distribuição** de versão para ir para a página de análise de software.</span><span class="sxs-lookup"><span data-stu-id="5d06d-129">Select the **version distribution** link to go to the software drill-down page.</span></span> <span data-ttu-id="5d06d-130">Lá, você pode ver uma lista filtrada de versões com marcas que as identificam como fim do suporte ou o próximo fim do suporte.</span><span class="sxs-lookup"><span data-stu-id="5d06d-130">There, you can see a filtered list of versions with tags identifying them as end of support, or upcoming end of support.</span></span>

    ![Captura de tela da página de detalhamento de software com o fim do software de suporte.](images/software-drilldown-eos.png)

3. <span data-ttu-id="5d06d-132">Selecione uma das versões na tabela a ser aberta.</span><span class="sxs-lookup"><span data-stu-id="5d06d-132">Select one of the versions in the table to open.</span></span> <span data-ttu-id="5d06d-133">Por exemplo, versão 10.0.18362.1.</span><span class="sxs-lookup"><span data-stu-id="5d06d-133">For example, version 10.0.18362.1.</span></span> <span data-ttu-id="5d06d-134">Um flyout aparecerá com a data de término do suporte.</span><span class="sxs-lookup"><span data-stu-id="5d06d-134">A flyout will appear with the end of support date.</span></span>

    ![Captura de tela da data de término do suporte.](images/version-eos-date.png)

<span data-ttu-id="5d06d-136">Depois de identificar quais versões de software e software são vulneráveis devido ao status de fim de suporte, você deve decidir se as atualizará ou removerá da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5d06d-136">Once you identify which software and software versions are vulnerable due to their end-of-support status, you must decide whether to update or remove them from your organization.</span></span> <span data-ttu-id="5d06d-137">Isso reduzirá a exposição de suas organizações a vulnerabilidades e ameaças persistentes avançadas.</span><span class="sxs-lookup"><span data-stu-id="5d06d-137">Doing so will lower your organizations exposure to vulnerabilities and advanced persistent threats.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5d06d-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5d06d-138">Related topics</span></span>

- [<span data-ttu-id="5d06d-139">Visão geral do gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="5d06d-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="5d06d-140">Recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="5d06d-140">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="5d06d-141">Inventário de software</span><span class="sxs-lookup"><span data-stu-id="5d06d-141">Software inventory</span></span>](tvm-software-inventory.md)
