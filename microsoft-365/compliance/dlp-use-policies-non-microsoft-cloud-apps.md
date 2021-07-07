---
title: Usar políticas de prevenção contra perda de dados para aplicativos de nuvem que não são da Microsoft
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
ms.openlocfilehash: 4bda45a6da6b9626391da37eb9a806b3308c5e7f
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322312"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps"></a><span data-ttu-id="fa528-103">Usar políticas de prevenção contra perda de dados para aplicativos de nuvem que não são da Microsoft</span><span class="sxs-lookup"><span data-stu-id="fa528-103">Use data loss prevention policies for non-Microsoft cloud apps</span></span>

<span data-ttu-id="fa528-104">As políticas de prevenção contra perda de dados (DLP) para aplicativos de nuvem que não são da Microsoft fazem parte do Microsoft 365 DLP de recursos; usando esses recursos, você pode descobrir e proteger itens confidenciais em Microsoft 365 serviços.</span><span class="sxs-lookup"><span data-stu-id="fa528-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="fa528-105">Para obter mais informações sobre todas as ofertas de DLP da Microsoft, [consulte Learn about data loss prevention](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="fa528-105">For more information about all Microsoft DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="fa528-106">Você pode usar políticas de DLP para aplicativos de nuvem que não sejam da Microsoft para monitorar e detectar quando itens confidenciais são usados e compartilhados por meio de aplicativos de nuvem que não são da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fa528-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="fa528-107">O uso dessas políticas oferece a visibilidade e o controle necessários para garantir que elas são usadas e protegidas corretamente, e isso ajuda a evitar comportamentos de risco que podem comprometer eles.</span><span class="sxs-lookup"><span data-stu-id="fa528-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fa528-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="fa528-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="fa528-109">Licenciamento SKU/assinaturas</span><span class="sxs-lookup"><span data-stu-id="fa528-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="fa528-110">Antes de começar a usar políticas DLP para aplicativos de nuvem que não são da Microsoft, confirme sua assinatura [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e quaisquer complementos.</span><span class="sxs-lookup"><span data-stu-id="fa528-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="fa528-111">Para acessar e usar essa funcionalidade, você deve ter uma dessas assinaturas ou complementos:</span><span class="sxs-lookup"><span data-stu-id="fa528-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="fa528-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="fa528-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="fa528-113">Conformidade do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="fa528-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="fa528-114">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="fa528-114">Microsoft 365 E5 Security</span></span>

### <a name="permissions"></a><span data-ttu-id="fa528-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="fa528-115">Permissions</span></span>
<span data-ttu-id="fa528-116">O usuário que cria a política DLP deve ser:</span><span class="sxs-lookup"><span data-stu-id="fa528-116">The user who creates the DLP policy should be a:</span></span>
- <span data-ttu-id="fa528-117">Administrador global</span><span class="sxs-lookup"><span data-stu-id="fa528-117">Global administrator</span></span>
- <span data-ttu-id="fa528-118">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="fa528-118">Compliance administrator</span></span>
- <span data-ttu-id="fa528-119">Administrador de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="fa528-119">Compliance data administrator</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="fa528-120">Preparar seu ambiente Cloud App Security ambiente</span><span class="sxs-lookup"><span data-stu-id="fa528-120">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="fa528-121">As políticas de DLP para aplicativos de nuvem que não são da Microsoft usam Cloud App Security DLP.</span><span class="sxs-lookup"><span data-stu-id="fa528-121">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="fa528-122">Para usá-lo, você deve preparar seu ambiente Cloud App Security ambiente.</span><span class="sxs-lookup"><span data-stu-id="fa528-122">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="fa528-123">Para obter instruções, consulte [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span><span class="sxs-lookup"><span data-stu-id="fa528-123">For instructions, see [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="fa528-124">Conexão um aplicativo de nuvem que não seja da Microsoft</span><span class="sxs-lookup"><span data-stu-id="fa528-124">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="fa528-125">Para usar a política de DLP a um aplicativo de nuvem não Microsoft específico, o aplicativo deve estar conectado a Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="fa528-125">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="fa528-126">Para obter informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="fa528-126">For information, see:</span></span>

- [<span data-ttu-id="fa528-127">Conexão Box</span><span class="sxs-lookup"><span data-stu-id="fa528-127">Connect Box</span></span>](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="fa528-128">Conexão Dropbox</span><span class="sxs-lookup"><span data-stu-id="fa528-128">Connect Dropbox</span></span>](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="fa528-129">Conexão G-Suite</span><span class="sxs-lookup"><span data-stu-id="fa528-129">Connect G-Suite</span></span>](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="fa528-130">Conexão Salesforce</span><span class="sxs-lookup"><span data-stu-id="fa528-130">Connect Salesforce</span></span>](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="fa528-131">Conexão Cisco Webex</span><span class="sxs-lookup"><span data-stu-id="fa528-131">Connect Cisco Webex</span></span>](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="fa528-132">Depois de conectar seus aplicativos de nuvem Cloud App Security, você pode criar Microsoft 365 DLP para eles.</span><span class="sxs-lookup"><span data-stu-id="fa528-132">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

> [!NOTE]
> <span data-ttu-id="fa528-133">Também é possível usar o Microsoft Cloud App Security para criar políticas de DLP para aplicativos de nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fa528-133">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="fa528-134">No entanto, é recomendável usar o Microsoft 365 para criar e gerenciar políticas de DLP para aplicativos de nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fa528-134">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="fa528-135">Criar uma política de DLP para um aplicativo de nuvem que não seja da Microsoft</span><span class="sxs-lookup"><span data-stu-id="fa528-135">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="fa528-136">Quando você selecionar um local para a política DLP, a Microsoft Cloud App Security **local.**</span><span class="sxs-lookup"><span data-stu-id="fa528-136">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="fa528-137">Para selecionar um aplicativo ou instância específico, selecione **Escolher instância**.</span><span class="sxs-lookup"><span data-stu-id="fa528-137">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="fa528-138">Se você não selecionar uma instância, a política usará todos os aplicativos conectados em seu Microsoft Cloud App Security locatário.</span><span class="sxs-lookup"><span data-stu-id="fa528-138">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![Locais para aplicar a política](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US e Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="fa528-141">Você pode escolher várias ações para cada aplicativo de nuvem que não seja da Microsoft com suporte.</span><span class="sxs-lookup"><span data-stu-id="fa528-141">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="fa528-142">Para cada aplicativo, há diferentes ações possíveis (depende da API do aplicativo na nuvem).</span><span class="sxs-lookup"><span data-stu-id="fa528-142">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![Criar regra](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="fa528-144">Ao criar uma regra na política DLP, você pode selecionar uma ação para aplicativos de nuvem que não são da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fa528-144">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="fa528-145">Para restringir aplicativos de terceiros, selecione **Restringir Aplicativos de Terceiros.**</span><span class="sxs-lookup"><span data-stu-id="fa528-145">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![Restringir aplicativos de terceiros](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

> [!NOTE]
> <span data-ttu-id="fa528-147">As políticas de DLP aplicadas a aplicativos que não são da Microsoft usam Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="fa528-147">DLP policies applied to non-Microsoft apps use Microsoft Cloud App Security.</span></span> <span data-ttu-id="fa528-148">Quando a política de DLP para um aplicativo não Microsoft é criada, a mesma política será criada automaticamente no Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="fa528-148">When the DLP policy for a non-Microsoft app is created, the same policy will be automatically created in Microsoft Cloud App Security.</span></span>

<span data-ttu-id="fa528-149">Para obter informações sobre como criar e configurar políticas DLP, consulte [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="fa528-149">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fa528-150">Confira também</span><span class="sxs-lookup"><span data-stu-id="fa528-150">See Also</span></span>

- [<span data-ttu-id="fa528-151">Criar teste e ajustar uma política de DLP</span><span class="sxs-lookup"><span data-stu-id="fa528-151">Create test and tune a DLP policy</span></span>](./create-test-tune-dlp-policy.md)
- [<span data-ttu-id="fa528-152">Introdução à política DLP padrão</span><span class="sxs-lookup"><span data-stu-id="fa528-152">Get started with the default DLP policy</span></span>](./get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="fa528-153">Criar uma política DLP a partir de um modelo</span><span class="sxs-lookup"><span data-stu-id="fa528-153">Create a DLP policy from a template</span></span>](./create-a-dlp-policy-from-a-template.md)
