---
title: Gerenciamento de dispositivo móvel para a Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda como a contoso usa o Microsoft Intune no Microsoft 365 for Enterprise para gerenciar seus dispositivos e os aplicativos que são executados neles.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753985"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="5b4b0-103">Gerenciamento de dispositivo móvel para a Contoso</span><span class="sxs-lookup"><span data-stu-id="5b4b0-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="5b4b0-104">O Microsoft 365 for Enterprise inclui o Intune e um conjunto de serviços do Azure que oferecem suporte a gerenciamento e segurança de dispositivos móveis e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-104">Microsoft 365 for enterprise includes Intune and a set of Azure services that support mobile device and application management and security.</span></span>

<span data-ttu-id="5b4b0-p101">A contoso tem vários funcionários habilitados para dispositivos móveis. Alguns têm escritórios nos locais da Contoso e alguns não têm escritórios. A contoso precisava de uma maneira de habilitar a produtividade dos funcionários, mas manter os dispositivos, os dados da Contoso armazenados nesses dispositivos e o comportamento do aplicativo seguro.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-p101">Contoso has many mobile-enabled employees. Some have offices in Contoso locations, and some have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="5b4b0-108">Plano</span><span class="sxs-lookup"><span data-stu-id="5b4b0-108">Plan</span></span>

<span data-ttu-id="5b4b0-109">A contoso identificou os seguintes casos de uso do Intune de gerenciamento de dispositivos móveis para o Microsoft 365 para empresas:</span><span class="sxs-lookup"><span data-stu-id="5b4b0-109">Contoso identified the following Intune use cases of mobile device management for Microsoft 365 for enterprise:</span></span>

- <span data-ttu-id="5b4b0-110">Proteger os dados e emails do Exchange Online para que eles possam ser acessados com segurança por dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices.</span></span>
- <span data-ttu-id="5b4b0-111">Implementar um programa do BYOD (Traga seu próprio dispositivo) para funcionários da contoso.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-111">Implement a bring-your-own-device (BYOD) program for Contoso employees.</span></span>
- <span data-ttu-id="5b4b0-112">Emitir telefones de propriedade da organização e usar tablets compartilhados para funcionários da contoso.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span></span>

<span data-ttu-id="5b4b0-113">A contoso não usa o Intune para:</span><span class="sxs-lookup"><span data-stu-id="5b4b0-113">Contoso doesn't use Intune to:</span></span>

- <span data-ttu-id="5b4b0-114">Permitir que os funcionários acessem com segurança o Microsoft 365 de um quiosque público não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-114">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk.</span></span>
- <span data-ttu-id="5b4b0-115">Proteger os dados e emails locais para que eles possam ser acessados com segurança por dispositivos móveis, porque não há servidores do Microsoft Exchange locais.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="5b4b0-116">Implantar</span><span class="sxs-lookup"><span data-stu-id="5b4b0-116">Deploy</span></span>

<span data-ttu-id="5b4b0-117">A Contoso configurou sua infraestrutura de gerenciamento de dispositivo móvel da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="5b4b0-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="5b4b0-118">Definir o Intune como a autoridade de gerenciamento de dispositivo móvel (MDM) e usar o Intune no Azure para administrar o conteúdo e gerenciar os dispositivos</span><span class="sxs-lookup"><span data-stu-id="5b4b0-118">Set Intune as the Mobile Device Management (MDM) authority, and use Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="5b4b0-119">Criou grupos do Azure Active Directory (Azure AD) para dispositivos para registro e configurações do Intune e políticas de acesso condicional baseadas em dispositivos</span><span class="sxs-lookup"><span data-stu-id="5b4b0-119">Created Azure Active Directory (Azure AD) groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="5b4b0-120">Para obter mais informações, consulte [contoso Conditional Access Policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span><span class="sxs-lookup"><span data-stu-id="5b4b0-120">For more information, see [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>

- <span data-ttu-id="5b4b0-121">Habilitada a plataforma de dispositivo Apple para dar suporte a funcionários com o iPads, iMacs e iPhones, e iPhones corporativos</span><span class="sxs-lookup"><span data-stu-id="5b4b0-121">Enabled the Apple device platform to support employees with iPads, iMacs, and iPhones, and corporate-owned iPhones</span></span>
- <span data-ttu-id="5b4b0-122">Criou políticas de termos e condições específicas da Contoso, que são apresentadas durante a instalação do Portal da Empresa da Contoso em dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="5b4b0-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="5b4b0-123">Para dispositivos que não estão registrados, implementou um conjunto de políticas de gerenciamento de aplicativo móvel (MAM) para exigir autenticação para acesso aos serviços do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5b4b0-123">For devices that aren't enrolled, implemented a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="5b4b0-124">Políticas criadas do Intune que imponham:</span><span class="sxs-lookup"><span data-stu-id="5b4b0-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="5b4b0-125">Aplicativos permitidos.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-125">Allowed apps.</span></span>
  - <span data-ttu-id="5b4b0-126">Criptografia de dispositivo para ajudar a impedir o acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-126">Device encryption to help prevent unauthorized access.</span></span>
  - <span data-ttu-id="5b4b0-127">Um PIN de seis dígitos ou senha.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-127">A six-digit PIN or password.</span></span>
  - <span data-ttu-id="5b4b0-128">Um período de tempo limite de inatividade.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-128">An inactivity-timeout period.</span></span>
  - <span data-ttu-id="5b4b0-129">Proteção antivírus e de malware e atualizações de assinatura com o Windows Defender em dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices.</span></span>
  - <span data-ttu-id="5b4b0-130">Atualizações automáticas em dispositivos Windows 10 que incluem as atualizações de segurança mais recentes.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-130">Automatic updates on Windows 10 devices that include the latest security updates.</span></span>
  - <span data-ttu-id="5b4b0-131">Envio de certificados para dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-131">Pushing certificates to managed devices.</span></span>
  - <span data-ttu-id="5b4b0-p102">Clara separação de dados pessoais e comerciais. Os administradores ou usuários podem apagar seletivamente dados corporativos do dispositivo, mantendo inalterados dados pessoais, como imagens, contas de email e arquivos pessoais.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="5b4b0-134">A contoso registrou computadores implantados e smartphones e tablets de propriedade da empresa adicionando-os aos grupos de dispositivos do Intune apropriados.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-134">Contoso enrolled deployed PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups.</span></span> <span data-ttu-id="5b4b0-135">Eles também estabeleceram um programa do BYOD para que os funcionários registrem seus dispositivos pessoais.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-135">They also established a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="5b4b0-136">Os dispositivos registrados recebem políticas do Intune, o que resulta em dispositivos gerenciados e protegidos e seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-136">Enrolled devices receive Intune policies, which results in managed and secured devices and their applications.</span></span> <span data-ttu-id="5b4b0-137">Os dispositivos que não estão registrados têm políticas de MAM (gerenciamento de aplicativo móvel) que especificam aplicativos permitidos.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-137">Devices that aren't enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="5b4b0-138">Veja a arquitetura de implantação de gerenciamento de dispositivo móvel da contoso.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-138">Here is the Contoso mobile device management deployment architecture.</span></span>

![Infraestrutura de implantação de gerenciamento de dispositivo móvel da contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="5b4b0-140">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="5b4b0-140">Next step</span></span>

<span data-ttu-id="5b4b0-141">Saiba como a contoso usa os [recursos de proteção de informações](contoso-info-protect.md) do Microsoft 365 para empresas para classificar, identificar e proteger ativos digitais essenciais em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="5b4b0-141">Learn how Contoso uses the [information protection capabilities](contoso-info-protect.md) of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b4b0-142">Confira também</span><span class="sxs-lookup"><span data-stu-id="5b4b0-142">See also</span></span>

[<span data-ttu-id="5b4b0-143">Gerenciamento de dispositivos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5b4b0-143">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="5b4b0-144">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5b4b0-144">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5b4b0-145">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="5b4b0-145">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

