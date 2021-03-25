---
title: Configurar recursos automatizados de investigação e correção
description: Configurar seus recursos automatizados de investigação e correção no Microsoft Defender para Ponto de Extremidade.
keywords: configurar, configurar, automatizar, investigação, detecção, alertas, correção, resposta
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: 31a1c79440a8c1edc2bc8e2f2a163ded2a92fd64
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165760"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="dbf8a-104">Configurar recursos automatizados de investigação e correção no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="dbf8a-104">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dbf8a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="dbf8a-105">**Applies to:**</span></span>
- [<span data-ttu-id="dbf8a-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="dbf8a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="dbf8a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dbf8a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="dbf8a-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="dbf8a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="dbf8a-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="dbf8a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="dbf8a-110">Se sua organização estiver usando o [Microsoft Defender para Ponto](https://docs.microsoft.com/windows/security/threat-protection/) de Extremidade (Defender para Ponto de Extremidade), os recursos automatizados de investigação e correção podem economizar tempo e esforço da equipe de operações de segurança. [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations)</span><span class="sxs-lookup"><span data-stu-id="dbf8a-110">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/) (Defender for Endpoint), [automated investigation and remediation capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) can save your security operations team time and effort.</span></span> <span data-ttu-id="dbf8a-111">Conforme descrito nesta [postagem de blog,](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)esses recursos imitam as etapas ideais que um analista de segurança toma para investigar e remediar ameaças.</span><span class="sxs-lookup"><span data-stu-id="dbf8a-111">As outlined in [this blog post](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946), these capabilities mimic the ideal steps that a security analyst takes to investigate and remediate threats.</span></span> <span data-ttu-id="dbf8a-112">[Saiba mais sobre investigação e correção automatizadas.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations)</span><span class="sxs-lookup"><span data-stu-id="dbf8a-112">[Learn more about automated investigation and remediation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations).</span></span> 

<span data-ttu-id="dbf8a-113">Para configurar a investigação e a correção automatizadas,</span><span class="sxs-lookup"><span data-stu-id="dbf8a-113">To configure automated investigation and remediation,</span></span>
1. <span data-ttu-id="dbf8a-114">[Ativar os recursos;](#turn-on-automated-investigation-and-remediation) e</span><span class="sxs-lookup"><span data-stu-id="dbf8a-114">[Turn on the features](#turn-on-automated-investigation-and-remediation); and</span></span> 
2. <span data-ttu-id="dbf8a-115">[Configurar grupos de dispositivos](#set-up-device-groups).</span><span class="sxs-lookup"><span data-stu-id="dbf8a-115">[Set up device groups](#set-up-device-groups).</span></span>

## <a name="turn-on-automated-investigation-and-remediation"></a><span data-ttu-id="dbf8a-116">Ativar investigação e correção automatizadas</span><span class="sxs-lookup"><span data-stu-id="dbf8a-116">Turn on automated investigation and remediation</span></span>

1. <span data-ttu-id="dbf8a-117">Como administrador global ou administrador de segurança, acesse o Centro de Segurança do Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="dbf8a-117">As a global administrator or security administrator, go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>
2. <span data-ttu-id="dbf8a-118">No painel de navegação, escolha **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="dbf8a-118">In the navigation pane, choose **Settings**.</span></span>
3. <span data-ttu-id="dbf8a-119">Na seção **Geral,** selecione **Recursos avançados**.</span><span class="sxs-lookup"><span data-stu-id="dbf8a-119">In the **General** section, select **Advanced features**.</span></span>
4. <span data-ttu-id="dbf8a-120">Acione a **Investigação Automatizada e** resolva **automaticamente os alertas**.</span><span class="sxs-lookup"><span data-stu-id="dbf8a-120">Turn on both **Automated Investigation** and **Automatically resolve alerts**.</span></span>

## <a name="set-up-device-groups"></a><span data-ttu-id="dbf8a-121">Configurar grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="dbf8a-121">Set up device groups</span></span>

1. <span data-ttu-id="dbf8a-122">No Centro de Segurança do Microsoft Defender ( ), na página [https://securitycenter.windows.com](https://securitycenter.windows.com) **Configurações,** em **Permissões,** selecione **Grupos de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="dbf8a-122">In the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)), on the **Settings** page, under **Permissions**, select **Device groups**.</span></span>
2. <span data-ttu-id="dbf8a-123">Selecione **+ Adicionar grupo de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="dbf8a-123">Select **+ Add device group**.</span></span>
3. <span data-ttu-id="dbf8a-124">Crie pelo menos um grupo de dispositivos, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="dbf8a-124">Create at least one device group, as follows:</span></span>
   - <span data-ttu-id="dbf8a-125">Especifique um nome e uma descrição para o grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dbf8a-125">Specify a name and description for the device group.</span></span>
   - <span data-ttu-id="dbf8a-126">Na lista **Nível de automação,** selecione um nível, como **Full – correção de ameaças automaticamente**.</span><span class="sxs-lookup"><span data-stu-id="dbf8a-126">In the **Automation level list**, select a level, such as **Full – remediate threats automatically**.</span></span> <span data-ttu-id="dbf8a-127">O nível de automação determina se as ações de correção são realizadas automaticamente ou somente após a aprovação.</span><span class="sxs-lookup"><span data-stu-id="dbf8a-127">The automation level determines whether remediation actions are taken automatically, or only upon approval.</span></span> <span data-ttu-id="dbf8a-128">Para saber mais, confira [Níveis de automação em investigação e correção automatizadas.](automation-levels.md)</span><span class="sxs-lookup"><span data-stu-id="dbf8a-128">To learn more, see [Automation levels in automated investigation and remediation](automation-levels.md).</span></span>
   - <span data-ttu-id="dbf8a-129">Na seção **Membros,** use uma ou mais condições para identificar e incluir dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dbf8a-129">In the **Members** section, use one or more conditions to identify and include devices.</span></span>
   - <span data-ttu-id="dbf8a-130">Na guia **Acesso ao** usuário, selecione os grupos do [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) que devem ter acesso ao grupo de dispositivos que você está criando.</span><span class="sxs-lookup"><span data-stu-id="dbf8a-130">On the **User access** tab, select the [Azure Active Directory groups](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) who should have access to the device group you're creating.</span></span>
4. <span data-ttu-id="dbf8a-131">Selecione **Concluído** quando terminar de configurar o grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dbf8a-131">Select **Done** when you're finished setting up your device group.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dbf8a-132">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="dbf8a-132">Next steps</span></span>

- [<span data-ttu-id="dbf8a-133">Visite o Centro de Ações para exibir ações pendentes e concluídas de correção</span><span class="sxs-lookup"><span data-stu-id="dbf8a-133">Visit the Action Center to view pending and completed remediation actions</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [<span data-ttu-id="dbf8a-134">Revisar e aprovar ações pendentes</span><span class="sxs-lookup"><span data-stu-id="dbf8a-134">Review and approve pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a><span data-ttu-id="dbf8a-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="dbf8a-135">See also</span></span>

- [<span data-ttu-id="dbf8a-136">Resolver falsos positivos/negativos no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="dbf8a-136">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
