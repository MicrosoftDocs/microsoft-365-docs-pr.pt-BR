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
ms.openlocfilehash: cbe2fb39221bd9907a3d690503a392edb019d61b
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194848"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="84702-104">Microsoft Defender para Ponto de Extremidade para iOS</span><span class="sxs-lookup"><span data-stu-id="84702-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="84702-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="84702-105">**Applies to:**</span></span>
- [<span data-ttu-id="84702-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="84702-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="84702-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84702-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="84702-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="84702-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="84702-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="84702-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="84702-110">**O Microsoft Defender para Ponto de Extremidade** no iOS oferece proteção contra phishing e conexões de rede não seguras de sites, emails e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="84702-110">**Microsoft Defender for Endpoint on iOS** offers protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="84702-111">Todos os alertas estarão disponíveis por meio de um único painel de vidro no Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="84702-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="84702-112">O portal fornece às equipes de segurança uma exibição centralizada de ameaças em dispositivos iOS juntamente com outras plataformas.</span><span class="sxs-lookup"><span data-stu-id="84702-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="84702-113">A execução de outros produtos de proteção de ponto de extremidade de terceiros juntamente com o Defender for Endpoint no iOS provavelmente causará problemas de desempenho e erros imprevisíveis do sistema.</span><span class="sxs-lookup"><span data-stu-id="84702-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="84702-114">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="84702-114">Pre-requisites</span></span>

<span data-ttu-id="84702-115">**Para usuários finais**</span><span class="sxs-lookup"><span data-stu-id="84702-115">**For End Users**</span></span>

- <span data-ttu-id="84702-116">Licença do Microsoft Defender para Ponto de Extremidade atribuída ao(s) usuário(s) final do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="84702-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="84702-117">Consulte [Requisitos de licenciamento do Microsoft Defender para Ponto de Extremidade.](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="84702-117">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="84702-118">**Para dispositivos inscritos:** Os [](/mem/intune/user-help/enroll-your-device-in-intune-ios) dispositivos são inscritos por meio do aplicativo Portal da Empresa do Intune para impor políticas de conformidade de dispositivos do Intune.</span><span class="sxs-lookup"><span data-stu-id="84702-118">**For enrolled devices**: Device(s) are [enrolled](/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="84702-119">Isso exige que o usuário final seja atribuído a uma Microsoft Intune de usuário.</span><span class="sxs-lookup"><span data-stu-id="84702-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="84702-120">Portal da Empresa do Intune aplicativo pode ser baixado na [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span><span class="sxs-lookup"><span data-stu-id="84702-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="84702-121">Observe que a Apple não permite que os usuários de redirecionamento baixem outros aplicativos da loja de aplicativos e, portanto, essa etapa precisa ser feita pelo usuário antes de entrar no aplicativo Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="84702-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="84702-122">**Para dispositivos não registrados:** Os dispositivos são registrados com Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="84702-122">**For unenrolled devices**: Device(s) are registered with Azure Active Directory.</span></span> <span data-ttu-id="84702-123">Isso exige que o usuário final seja assinado por meio [Microsoft Authenticator app](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span><span class="sxs-lookup"><span data-stu-id="84702-123">This requires end user to be signed in through [Microsoft Authenticator app](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span></span>

- <span data-ttu-id="84702-124">Para obter mais informações sobre como atribuir licenças, consulte [Atribuir licenças aos usuários](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="84702-124">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="84702-125">**Para administradores**</span><span class="sxs-lookup"><span data-stu-id="84702-125">**For Administrators**</span></span>

- <span data-ttu-id="84702-126">Acesso ao portal Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="84702-126">Access to the Microsoft Defender Security Center portal.</span></span>

- <span data-ttu-id="84702-127">Acesso ao [Microsoft Endpoint Manager de](https://go.microsoft.com/fwlink/?linkid=2109431)administração , para implantar o aplicativo em grupos de usuários inscritos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="84702-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

    > [!NOTE]
    > <span data-ttu-id="84702-128">Microsoft Intune é a única solução UEM (Gerenciamento Unificado de Pontos de Extremidade) com suporte para implantar o Microsoft Defender para Ponto de Extremidade e aplicar políticas de conformidade de dispositivo relacionadas ao Defender para Ponto de Extremidade no Intune.</span><span class="sxs-lookup"><span data-stu-id="84702-128">Microsoft Intune is the only supported Unified Endpoint Management (UEM) solution for deploying Microsoft Defender for Endpoint and enforcing Defender for Endpoint related device compliance policies in Intune.</span></span>

<span data-ttu-id="84702-129">**Requisitos do sistema**</span><span class="sxs-lookup"><span data-stu-id="84702-129">**System Requirements**</span></span>

- <span data-ttu-id="84702-130">Dispositivo iOS executando o iOS 11.0 ou superior.</span><span class="sxs-lookup"><span data-stu-id="84702-130">iOS device running iOS 11.0 and above.</span></span> <span data-ttu-id="84702-131">iPad dispositivos são oficialmente compatíveis com a versão 1.1.15010101 em diante.</span><span class="sxs-lookup"><span data-stu-id="84702-131">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="84702-132">O dispositivo está registrado com o aplicativo [Portal da Empresa do Intune ou](https://apps.apple.com/us/app/intune-company-portal/id719171358) registrado com Azure Active Directory por [meio Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span><span class="sxs-lookup"><span data-stu-id="84702-132">Device is either enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358) or registered with Azure Active Directory through [Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="84702-133">Instruções de instalação</span><span class="sxs-lookup"><span data-stu-id="84702-133">Installation instructions</span></span>

<span data-ttu-id="84702-134">A implantação do Microsoft Defender para Ponto de Extremidade no iOS pode ser feita por meio Microsoft Endpoint Manager (MEM) e há suporte para dispositivos supervisionados e não supervisionados.</span><span class="sxs-lookup"><span data-stu-id="84702-134">Deployment of Microsoft Defender for Endpoint on iOS can be done via Microsoft Endpoint Manager (MEM) and both supervised and unsupervised devices are supported.</span></span> <span data-ttu-id="84702-135">Os usuários finais também podem instalar diretamente o aplicativo na [Loja de Aplicativos da Apple.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="84702-135">End-users can also directly install the app from the [Apple app store](https://aka.ms/mdatpiosappstore).</span></span>
<span data-ttu-id="84702-136">Para obter mais informações, [consulte Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span><span class="sxs-lookup"><span data-stu-id="84702-136">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="84702-137">Recursos</span><span class="sxs-lookup"><span data-stu-id="84702-137">Resources</span></span>

- <span data-ttu-id="84702-138">Mantenha-se informado sobre as próximas versões visitando Novidades do Microsoft Defender para Ponto de Extremidade [no iOS](ios-whatsnew.md) ou em nosso [blog.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)</span><span class="sxs-lookup"><span data-stu-id="84702-138">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="84702-139">Fornecer comentários por meio do sistema de comentários no aplicativo ou por meio do [portal SecOps](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="84702-139">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="84702-140">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="84702-140">Next steps</span></span>

- [<span data-ttu-id="84702-141">Implantar o Microsoft Defender para Ponto de Extremidade no iOS</span><span class="sxs-lookup"><span data-stu-id="84702-141">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="84702-142">Configurar o Microsoft Defender para Ponto de Extremidade em recursos do iOS</span><span class="sxs-lookup"><span data-stu-id="84702-142">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
