---
title: Gerenciamento de dispositivo móvel para a Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda como a Contoso usa Intune no Microsoft 365 Enterprise para gerenciar seus dispositivos e aplicativos com base nessa plataforma.
ms.openlocfilehash: c486c9ef338ab1bd8959266183da6b79d62b3311
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673177"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="9268e-103">Gerenciamento de dispositivo móvel para a Contoso</span><span class="sxs-lookup"><span data-stu-id="9268e-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="9268e-104">O Microsoft 365 Enterprise inclui o Microsoft Intune e um conjunto de serviços do Azure que dão suporte a segurança, ao gerenciamento de aplicativos e dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="9268e-104">Microsoft 365 Enterprise includes Intune and a set of Azure services to support mobile device and application management and security.</span></span>

<span data-ttu-id="9268e-p101">A Contoso tem vários funcionários com dispositivos móveis, alguns em escritórios da Contoso e alguns dos quais não têm escritórios. A Contoso precisa de uma maneira de habilitar a produtividade mas manter a proteção nos dispositivos, nos dados da Contoso armazenados nesses dispositivos e no comportamento dos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="9268e-p101">Contoso has many mobile-enabled employees, some of which have offices in Contoso locations and some of which have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="9268e-107">Planejar</span><span class="sxs-lookup"><span data-stu-id="9268e-107">Plan</span></span>

<span data-ttu-id="9268e-108">No início da análise de gerenciamento de dispositivo móvel para o Microsoft 365 Enterprise, a Contoso identificou os seguintes casos de uso do Intune:</span><span class="sxs-lookup"><span data-stu-id="9268e-108">Early in the analysis of mobile device management for Microsoft 365 Enterprise, Contoso identified the following Intune use cases:</span></span>

- <span data-ttu-id="9268e-109">Proteger os dados e emails do Exchange Online para que possam ser acessados com segurança em dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="9268e-109">Protect Exchange Online email and data so it can be safely accessed by mobile devices</span></span>
- <span data-ttu-id="9268e-110">Implementar um programa "traga seu próprio dispositivo" (BYOD) para funcionários da Contoso</span><span class="sxs-lookup"><span data-stu-id="9268e-110">Implement a bring your own device (BYOD) program for Contoso employees</span></span>
- <span data-ttu-id="9268e-111">Emitir telefones e tablets pertencentes à organização e tablets compartilhados de uso limitado para funcionários da Contoso</span><span class="sxs-lookup"><span data-stu-id="9268e-111">Issue organization-owned phones and limited-use shared tablets to Contoso employees</span></span>

<span data-ttu-id="9268e-112">A Contoso não está usando o Intune para:</span><span class="sxs-lookup"><span data-stu-id="9268e-112">Contoso is not using Intune to:</span></span>

- <span data-ttu-id="9268e-113">Permitir aos funcionários acessar com segurança o Office 365 de um kiosk público não gerenciado</span><span class="sxs-lookup"><span data-stu-id="9268e-113">Allow employees to securely access Office 365 from an unmanaged public kiosk</span></span>
- <span data-ttu-id="9268e-114">Proteger dados e emails locais para que possam ser acessados com segurança em dispositivos móveis, já que não há mais servidores locais do Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="9268e-114">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no longer on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="9268e-115">Implantar</span><span class="sxs-lookup"><span data-stu-id="9268e-115">Deploy</span></span>

<span data-ttu-id="9268e-116">A Contoso configurou sua infraestrutura de gerenciamento de dispositivo móvel da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="9268e-116">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="9268e-117">Configurou o Intune como a autoridade de Gerenciamento de Dispositivo Móvel (MDM) e está usando o Intune no Azure para administrar o conteúdo e gerenciar os dispositivos</span><span class="sxs-lookup"><span data-stu-id="9268e-117">Set Intune as the Mobile Device Management (MDM) authority and are using Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="9268e-118">Criou grupos do Azure AD para dispositivos para registro e configurações do Intune, além de políticas de acesso condicional baseadas no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9268e-118">Created Azure AD groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="9268e-119">Confira [políticas de acesso condicional da Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="9268e-119">See [Contoso's Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) for more information.</span></span>

- <span data-ttu-id="9268e-120">Habilitou a plataforma de dispositivos Apple para dar suporte a funcionários com iPads, iPhones e iMacs e celulares de propriedade corporativa com base no iPhone</span><span class="sxs-lookup"><span data-stu-id="9268e-120">Enabled the Apple device platform to support employees with iPads, iMacs, iPhones, and for iPhone-based corporate-owned phones</span></span>
- <span data-ttu-id="9268e-121">Criou políticas de termos e condições específicas da Contoso, que são apresentadas durante a instalação do Portal da Empresa da Contoso em dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="9268e-121">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="9268e-122">Para dispositivos que não estão registrados, um conjunto de políticas de Gerenciamento de Aplicativo Móvel (MAM) para exigir autenticação para acesso aos serviços do Office 365</span><span class="sxs-lookup"><span data-stu-id="9268e-122">For devices that are not enrolled, a set of Mobile Application Management (MAM) policies to require authentication for access to Office 365 services</span></span>
- <span data-ttu-id="9268e-123">Políticas criadas do Intune que imponham:</span><span class="sxs-lookup"><span data-stu-id="9268e-123">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="9268e-124">Aplicativos permitidos</span><span class="sxs-lookup"><span data-stu-id="9268e-124">Allowed apps</span></span>
  - <span data-ttu-id="9268e-125">Criptografia de dispositivos para ajudar a impedir o acesso não autorizado</span><span class="sxs-lookup"><span data-stu-id="9268e-125">Device encryption to help prevent unauthorized access</span></span>
  - <span data-ttu-id="9268e-126">Um PIN de seis dígitos ou senha</span><span class="sxs-lookup"><span data-stu-id="9268e-126">A six-digit PIN or password</span></span>
  - <span data-ttu-id="9268e-127">Um tempo limite de inatividade</span><span class="sxs-lookup"><span data-stu-id="9268e-127">An inactivity timeout period</span></span>
  - <span data-ttu-id="9268e-128">Proteção antivírus e contra malware, e atualizações de assinaturas com o Windows Defender em dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="9268e-128">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices</span></span>
  - <span data-ttu-id="9268e-129">Atualizações automáticas em dispositivos Windows 10 que incluem as atualizações de segurança mais recentes</span><span class="sxs-lookup"><span data-stu-id="9268e-129">Automatic updates on Windows 10 devices that include the latest security updates</span></span>
  - <span data-ttu-id="9268e-130">Enviar certificados para dispositivos gerenciados</span><span class="sxs-lookup"><span data-stu-id="9268e-130">Pushing certificates to managed devices</span></span>
  - <span data-ttu-id="9268e-p102">Clara separação de dados pessoais e comerciais. Os administradores ou usuários podem apagar seletivamente dados corporativos do dispositivo, mantendo inalterados dados pessoais, como imagens, contas de email e arquivos pessoais.</span><span class="sxs-lookup"><span data-stu-id="9268e-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="9268e-p103">Depois de implantar, a Contoso registrou os PCs, smartphones e tablets de propriedade da empresa adicionando-os aos grupos de dispositivos apropriados do Intune, e gradualmente implementou um programa BYOD para os funcionários poderem registrar seus dispositivos pessoais. Os dispositivos registrados receberam políticas do Intune, resultando em dispositivos e aplicativos gerenciados e seguros. Dispositivos não registrados têm políticas de gerenciamento de aplicativo móvel (MAM) que especificam aplicativos permitidos.</span><span class="sxs-lookup"><span data-stu-id="9268e-p103">Once deployed, Contoso enrolled PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups and rolled out a BYOD program for employees to enroll their personal devices. Enrolled devices received Intune policies, resulting in managed and secured devices and their applications. Devices that are not enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="9268e-136">Esta é a arquitetura de implantação de gerenciamento de dispositivo móvel da Contoso.</span><span class="sxs-lookup"><span data-stu-id="9268e-136">Here is Contoso's mobile device management deployment architecture.</span></span>

![Infraestrutura de implantação de gerenciamento de dispositivo móvel da Contoso.](./media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="9268e-138">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="9268e-138">Next step</span></span>

<span data-ttu-id="9268e-139">[Saiba](contoso-info-protect.md) como a Contoso usa os recursos de proteção de informações do Microsoft 365 Enterprise para classificar, identificar e proteger ativos digitais fundamentais em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9268e-139">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 Enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="9268e-140">Confira também</span><span class="sxs-lookup"><span data-stu-id="9268e-140">See also</span></span>

[<span data-ttu-id="9268e-141">Gerenciamento de dispositivo móvel para o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9268e-141">Mobile device management for Microsoft 365 Enterprise</span></span>](mobility-infrastructure.md)

[<span data-ttu-id="9268e-142">Guia de implantação</span><span class="sxs-lookup"><span data-stu-id="9268e-142">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="9268e-143">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="9268e-143">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

