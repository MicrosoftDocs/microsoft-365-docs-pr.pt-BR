---
title: Usar políticas de prevenção contra perda de dados para aplicativos de nuvem que não são da Microsoft (visualização)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Saiba como usar políticas dlp para aplicativos de nuvem que não são da Microsoft.
ms.openlocfilehash: 0b588bf27738a0f9a8078999311294f74e5193c0
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649652"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="91e8b-103">Usar políticas de prevenção contra perda de dados para aplicativos de nuvem que não são da Microsoft (visualização)</span><span class="sxs-lookup"><span data-stu-id="91e8b-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="91e8b-104">As políticas de prevenção contra perda de dados (DLP) para aplicativos de nuvem que não são da Microsoft fazem parte do pacote de recursos DLP do Microsoft 365; Usando esses recursos, você pode descobrir e proteger itens confidenciais nos serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="91e8b-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="91e8b-105">Para obter mais informações sobre todas as ofertas de DLP da Microsoft, consulte [Visão geral da prevenção contra perda de dados.](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="91e8b-105">For more information about all Microsoft DLP offerings, see [Overview of data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide).</span></span>

<span data-ttu-id="91e8b-106">Você pode usar políticas DLP para aplicativos de nuvem que não são da Microsoft para monitorar e detectar quando itens confidenciais são usados e compartilhados por meio de aplicativos em nuvem que não são da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="91e8b-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="91e8b-107">O uso dessas políticas oferece a visibilidade e o controle necessários para garantir que elas são usadas e protegidas corretamente, e isso ajuda a evitar comportamentos arriscados que possam comprometer essas políticas.</span><span class="sxs-lookup"><span data-stu-id="91e8b-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="91e8b-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="91e8b-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="91e8b-109">Licenciamento SKU/assinaturas</span><span class="sxs-lookup"><span data-stu-id="91e8b-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="91e8b-110">Antes de começar a usar políticas DLP para aplicativos de nuvem que não são da Microsoft, confirme sua assinatura do [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e quaisquer complementos.</span><span class="sxs-lookup"><span data-stu-id="91e8b-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="91e8b-111">Para acessar e usar essa funcionalidade, você deve ter uma destas assinaturas ou complementos:</span><span class="sxs-lookup"><span data-stu-id="91e8b-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="91e8b-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="91e8b-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="91e8b-113">Conformidade do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="91e8b-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="91e8b-114">Segurança do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="91e8b-114">Microsoft 365 E5 Security</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="91e8b-115">Preparar seu ambiente do Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="91e8b-115">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="91e8b-116">As políticas DLP para aplicativos de nuvem que não são da Microsoft usam recursos de DLP do Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="91e8b-116">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="91e8b-117">Para usá-lo, você deve preparar seu ambiente do Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="91e8b-117">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="91e8b-118">Para obter instruções, consulte [Definir ações de visibilidade instantânea, proteção e governança para seus aplicativos.](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)</span><span class="sxs-lookup"><span data-stu-id="91e8b-118">For instructions, see [Set instant visibility, protection, and governance actions for your apps](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="91e8b-119">Conectar um aplicativo de nuvem que não seja da Microsoft</span><span class="sxs-lookup"><span data-stu-id="91e8b-119">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="91e8b-120">Para usar a política de DLP para um aplicativo de nuvem específico que não seja da Microsoft, o aplicativo deve estar conectado ao Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="91e8b-120">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="91e8b-121">Para obter informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="91e8b-121">For information, see:</span></span>

- [<span data-ttu-id="91e8b-122">Caixa Conectar</span><span class="sxs-lookup"><span data-stu-id="91e8b-122">Connect Box</span></span>](https://docs.microsoft.com/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="91e8b-123">Conectar o Dropbox</span><span class="sxs-lookup"><span data-stu-id="91e8b-123">Connect Dropbox</span></span>](https://docs.microsoft.com/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="91e8b-124">Conectar-se ao G-Suite</span><span class="sxs-lookup"><span data-stu-id="91e8b-124">Connect G-Suite</span></span>](https://docs.microsoft.com/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="91e8b-125">Connect Salesforce</span><span class="sxs-lookup"><span data-stu-id="91e8b-125">Connect Salesforce</span></span>](https://docs.microsoft.com/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="91e8b-126">Conectar a Cisco Webex</span><span class="sxs-lookup"><span data-stu-id="91e8b-126">Connect Cisco Webex</span></span>](https://docs.microsoft.com/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="91e8b-127">Depois de conectar seus aplicativos de nuvem ao Cloud App Security, você pode criar políticas DLP do Microsoft 365 para eles.</span><span class="sxs-lookup"><span data-stu-id="91e8b-127">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

>[!NOTE]
><span data-ttu-id="91e8b-128">Também é possível usar o Microsoft Cloud App Security para criar políticas DLP para aplicativos em nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="91e8b-128">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="91e8b-129">No entanto, é recomendável usar o Microsoft 365 para criar e gerenciar políticas DLP para aplicativos em nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="91e8b-129">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="91e8b-130">Criar uma política DLP para um aplicativo de nuvem que não seja da Microsoft</span><span class="sxs-lookup"><span data-stu-id="91e8b-130">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="91e8b-131">Quando você selecionar um local para a política de DLP, a ligue o local **do Microsoft Cloud App Security.**</span><span class="sxs-lookup"><span data-stu-id="91e8b-131">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="91e8b-132">Para selecionar um aplicativo ou uma instância específica, selecione **Escolher instância.**</span><span class="sxs-lookup"><span data-stu-id="91e8b-132">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="91e8b-133">Se você não selecionar uma instância, a política usará todos os aplicativos conectados em seu locatário do Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="91e8b-133">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![Locais para aplicar a política](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US e Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="91e8b-136">Você pode escolher várias ações para cada aplicativo de nuvem não Microsoft com suporte.</span><span class="sxs-lookup"><span data-stu-id="91e8b-136">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="91e8b-137">Para cada aplicativo, há diferentes ações possíveis (depende da API do aplicativo na nuvem).</span><span class="sxs-lookup"><span data-stu-id="91e8b-137">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![Criar regra](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="91e8b-139">Ao criar uma regra na política de DLP, você pode selecionar uma ação para aplicativos de nuvem que não são da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="91e8b-139">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="91e8b-140">Para restringir aplicativos de terceiros, selecione **Restringir Aplicativos de Terceiros.**</span><span class="sxs-lookup"><span data-stu-id="91e8b-140">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![Restringir aplicativos de terceiros](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

<span data-ttu-id="91e8b-142">Para obter informações sobre como criar e configurar políticas DLP, consulte [Criar teste e ajustar uma política de DLP.](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="91e8b-142">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide).</span></span>

## <a name="see-also"></a><span data-ttu-id="91e8b-143">Confira também</span><span class="sxs-lookup"><span data-stu-id="91e8b-143">See Also</span></span>

- [<span data-ttu-id="91e8b-144">Criar teste e ajustar uma política de DLP</span><span class="sxs-lookup"><span data-stu-id="91e8b-144">Create test and tune a DLP policy</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)
- [<span data-ttu-id="91e8b-145">Introdução à política DLP padrão</span><span class="sxs-lookup"><span data-stu-id="91e8b-145">Get started with the default DLP policy</span></span>](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-the-default-dlp-policy?view=o365-worldwide)
- [<span data-ttu-id="91e8b-146">Criar uma política DLP a partir de um modelo</span><span class="sxs-lookup"><span data-stu-id="91e8b-146">Create a DLP policy from a template</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template?view=o365-worldwide)
