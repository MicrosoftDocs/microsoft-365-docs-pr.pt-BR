---
title: Microsoft Defender para Ponto de Extremidade para iOS
ms.reviewer: ''
description: Descreve como instalar e usar o Microsoft Defender para Ponto de Extremidade no iOS
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, overview, installation, deploy, uninstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b4c2d586cd23a346db1bcebf891689ff648b639b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844701"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="6ebf0-104">Microsoft Defender para Ponto de Extremidade para iOS</span><span class="sxs-lookup"><span data-stu-id="6ebf0-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6ebf0-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6ebf0-105">**Applies to:**</span></span>
- [<span data-ttu-id="6ebf0-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6ebf0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6ebf0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6ebf0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6ebf0-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="6ebf0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6ebf0-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="6ebf0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="6ebf0-110">**O Microsoft Defender para Ponto de Extremidade** no iOS oferecerá proteção contra phishing e conexões de rede não seguras de sites, emails e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6ebf0-110">**Microsoft Defender for Endpoint on iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="6ebf0-111">Todos os alertas estarão disponíveis por meio de um único painel de vidro no Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="6ebf0-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="6ebf0-112">O portal fornece às equipes de segurança uma exibição centralizada de ameaças em dispositivos iOS juntamente com outras plataformas.</span><span class="sxs-lookup"><span data-stu-id="6ebf0-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="6ebf0-113">A execução de outros produtos de proteção de ponto de extremidade de terceiros juntamente com o Defender for Endpoint no iOS provavelmente causará problemas de desempenho e erros imprevisíveis do sistema.</span><span class="sxs-lookup"><span data-stu-id="6ebf0-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="6ebf0-114">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6ebf0-114">Pre-requisites</span></span>

<span data-ttu-id="6ebf0-115">**Para usuários finais**</span><span class="sxs-lookup"><span data-stu-id="6ebf0-115">**For End Users**</span></span>

- <span data-ttu-id="6ebf0-116">Licença do Microsoft Defender para Ponto de Extremidade atribuída ao(s) usuário(s) final do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6ebf0-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="6ebf0-117">Consulte [Requisitos de licenciamento do Microsoft Defender para Ponto de Extremidade.](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="6ebf0-117">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="6ebf0-118">Os dispositivos são [inscritos por](/mem/intune/user-help/enroll-your-device-in-intune-ios) meio do aplicativo Portal da Empresa do Intune para impor políticas de conformidade de dispositivos do Intune.</span><span class="sxs-lookup"><span data-stu-id="6ebf0-118">Device(s) are [enrolled](/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="6ebf0-119">Isso exige que o usuário final seja atribuído a uma Microsoft Intune de usuário.</span><span class="sxs-lookup"><span data-stu-id="6ebf0-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="6ebf0-120">Portal da Empresa do Intune aplicativo pode ser baixado na [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span><span class="sxs-lookup"><span data-stu-id="6ebf0-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="6ebf0-121">Observe que a Apple não permite que os usuários de redirecionamento baixem outros aplicativos da loja de aplicativos e, portanto, essa etapa precisa ser feita pelo usuário antes de entrar no aplicativo Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="6ebf0-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="6ebf0-122">Para obter mais informações sobre como atribuir licenças, consulte [Atribuir licenças aos usuários](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="6ebf0-122">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="6ebf0-123">**Para administradores**</span><span class="sxs-lookup"><span data-stu-id="6ebf0-123">**For Administrators**</span></span>

- <span data-ttu-id="6ebf0-124">Acesso ao portal Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="6ebf0-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6ebf0-125">Microsoft Intune é a única solução UEM (Gerenciamento Unificado de Pontos de Extremidade) com suporte para implantar o Microsoft Defender para Ponto de Extremidade e aplicar políticas de conformidade de dispositivo relacionadas ao Defender para Ponto de Extremidade no Intune.</span><span class="sxs-lookup"><span data-stu-id="6ebf0-125">Microsoft Intune is the only supported Unified Endpoint Management (UEM) solution for deploying Microsoft Defender for Endpoint and enforcing Defender for Endpoint related device compliance policies in Intune.</span></span>

- <span data-ttu-id="6ebf0-126">Acesso ao [Microsoft Endpoint Manager de](https://go.microsoft.com/fwlink/?linkid=2109431)administração , para implantar o aplicativo em grupos de usuários inscritos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6ebf0-126">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="6ebf0-127">**Requisitos do sistema**</span><span class="sxs-lookup"><span data-stu-id="6ebf0-127">**System Requirements**</span></span>

- <span data-ttu-id="6ebf0-128">Dispositivos iOS que executam o iOS 11.0 ou superior.</span><span class="sxs-lookup"><span data-stu-id="6ebf0-128">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="6ebf0-129">iPad dispositivos são oficialmente compatíveis com a versão 1.1.15010101 em diante.</span><span class="sxs-lookup"><span data-stu-id="6ebf0-129">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="6ebf0-130">O dispositivo está inscrito no aplicativo [Portal da Empresa do Intune .](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="6ebf0-130">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="6ebf0-131">Instruções de instalação</span><span class="sxs-lookup"><span data-stu-id="6ebf0-131">Installation instructions</span></span>

<span data-ttu-id="6ebf0-132">A implantação do Microsoft Defender para Ponto de Extremidade no iOS é via Microsoft Intune (MDM) e há suporte para dispositivos supervisionados e não supervisionados.</span><span class="sxs-lookup"><span data-stu-id="6ebf0-132">Deployment of Microsoft Defender for Endpoint on iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span> <span data-ttu-id="6ebf0-133">Os usuários finais também podem instalar diretamente o aplicativo na [Loja de Aplicativos da Apple.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="6ebf0-133">End-users can also directly install the app from the [Apple app store](https://aka.ms/mdatpiosappstore).</span></span>
<span data-ttu-id="6ebf0-134">Para obter mais informações, [consulte Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span><span class="sxs-lookup"><span data-stu-id="6ebf0-134">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="6ebf0-135">Recursos</span><span class="sxs-lookup"><span data-stu-id="6ebf0-135">Resources</span></span>

- <span data-ttu-id="6ebf0-136">Mantenha-se informado sobre as próximas versões visitando Novidades do Microsoft Defender para Ponto de Extremidade [no iOS](ios-whatsnew.md) ou em nosso [blog.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)</span><span class="sxs-lookup"><span data-stu-id="6ebf0-136">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="6ebf0-137">Fornecer comentários por meio do sistema de comentários no aplicativo ou por meio do [portal SecOps](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="6ebf0-137">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="6ebf0-138">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="6ebf0-138">Next steps</span></span>

- [<span data-ttu-id="6ebf0-139">Implantar o Microsoft Defender para Ponto de Extremidade no iOS</span><span class="sxs-lookup"><span data-stu-id="6ebf0-139">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="6ebf0-140">Configurar o Microsoft Defender para Ponto de Extremidade em recursos do iOS</span><span class="sxs-lookup"><span data-stu-id="6ebf0-140">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
