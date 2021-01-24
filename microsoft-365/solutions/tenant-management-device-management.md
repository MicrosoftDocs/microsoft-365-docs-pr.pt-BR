---
title: Etapa 5. Gerenciamento de dispositivos e aplicativos para locatários do Microsoft 365 para empresas
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Implante a opção correta para gerenciamento de dispositivos e aplicativos para seus locatários do Microsoft 365.
ms.openlocfilehash: a581af3ec2ec192112656f1919e27f5b05a41cb1
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908438"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="96e8e-104">Etapa 5.</span><span class="sxs-lookup"><span data-stu-id="96e8e-104">Step 5.</span></span> <span data-ttu-id="96e8e-105">Gerenciamento de dispositivos e aplicativos para locatários do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="96e8e-105">Device and app management for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="96e8e-106">O Microsoft 365 para empresas inclui recursos para ajudar a gerenciar dispositivos e o uso de aplicativos nesses dispositivos em sua organização com gerenciamento de dispositivo móvel (MDM) e gerenciamento de aplicativo móvel (MAM).</span><span class="sxs-lookup"><span data-stu-id="96e8e-106">Microsoft 365 for enterprise includes features to help manage devices and the use of apps on those devices within your organization with mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="96e8e-107">Você pode gerenciar dispositivos iOS, Android, macOS e Windows para proteger o acesso aos recursos da sua organização, incluindo seus dados.</span><span class="sxs-lookup"><span data-stu-id="96e8e-107">You can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="96e8e-108">Por exemplo, você pode impedir que emails são enviados para pessoas de fora da sua organização ou isolar dados da organização de dados pessoais nos dispositivos pessoais do seu funcionário.</span><span class="sxs-lookup"><span data-stu-id="96e8e-108">For example, you can prevent emails from being sent to people outside your organization or isolate organization data from personal data on your worker's personal devices.</span></span>

<span data-ttu-id="96e8e-109">Aqui está um exemplo de validação e gerenciamento de usuários, seus dispositivos e seu uso de aplicativos de produtividade local e na nuvem, como o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="96e8e-109">Here is an example of the validation and management of users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Validação e gerenciamento de usuários, dispositivos e aplicativos](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

<span data-ttu-id="96e8e-111">Para ajudar você a proteger os recursos da sua organização, o Microsoft 365 para empresas inclui recursos para ajudar a gerenciar dispositivos e seu acesso a aplicativos.</span><span class="sxs-lookup"><span data-stu-id="96e8e-111">To help you secure and protect your organization's resources, Microsoft 365 for enterprise includes features to help manage devices and their access to apps.</span></span> <span data-ttu-id="96e8e-112">Há duas opções de gerenciamento de dispositivos:</span><span class="sxs-lookup"><span data-stu-id="96e8e-112">There are two options for device management:</span></span>

- <span data-ttu-id="96e8e-113">Microsoft Intune, que é uma solução abrangente de gerenciamento de dispositivos e aplicativos para empresas.</span><span class="sxs-lookup"><span data-stu-id="96e8e-113">Microsoft Intune, which is a comprehensive device and app management solution for enterprises.</span></span>
- <span data-ttu-id="96e8e-114">Mobilidade básica e segurança, que é um subconjunto de serviços do Intune incluídos em todos os produtos do Microsoft 365 para gerenciar dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="96e8e-114">Basic Mobility and Security, which is a subset of Intune services included with all Microsoft 365 products for managing devices in your organization.</span></span> <span data-ttu-id="96e8e-115">Para obter mais informações, [consulte Recursos de Mobilidade Básica e Segurança.](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities)</span><span class="sxs-lookup"><span data-stu-id="96e8e-115">For more information, see [Capabilities of Basic Mobility and Security](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities).</span></span>

<span data-ttu-id="96e8e-116">Se você tiver o Microsoft 365 E3 ou E5, deverá usar o Intune.</span><span class="sxs-lookup"><span data-stu-id="96e8e-116">If you have Microsoft 365 E3 or E5, you should use Intune.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="96e8e-117">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="96e8e-117">Microsoft Intune</span></span>

<span data-ttu-id="96e8e-118">Você usa [o Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) para gerenciar o acesso à sua organização usando MDM ou MAM.</span><span class="sxs-lookup"><span data-stu-id="96e8e-118">You use [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) to manage access to your organization using MDM or MAM.</span></span> <span data-ttu-id="96e8e-119">O MDM é quando os usuários "registram" seus dispositivos no Intune.</span><span class="sxs-lookup"><span data-stu-id="96e8e-119">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="96e8e-120">Depois que um dispositivo é inscrito, ele é um dispositivo gerenciado e pode receber as políticas, regras e configurações da sua organização.</span><span class="sxs-lookup"><span data-stu-id="96e8e-120">After a device is enrolled, it is a managed device and can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="96e8e-121">Por exemplo, você pode instalar aplicativos específicos, criar uma política de senha, instalar uma conexão VPN e muito mais.</span><span class="sxs-lookup"><span data-stu-id="96e8e-121">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="96e8e-122">Os usuários com seus próprios dispositivos pessoais podem não querer registrar seus dispositivos ou ser gerenciados pelo Intune e pelas políticas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="96e8e-122">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="96e8e-123">Mas você ainda precisa proteger os recursos e dados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="96e8e-123">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="96e8e-124">Nesse cenário, você pode proteger seus aplicativos usando o MAM.</span><span class="sxs-lookup"><span data-stu-id="96e8e-124">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="96e8e-125">Por exemplo, você pode usar uma política de MAM que exija que um usuário insira um PIN ao acessar o SharePoint no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="96e8e-125">For example, you can use an MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="96e8e-126">Você também determinará como gerenciará dispositivos pessoais e dispositivos de propriedade da organização.</span><span class="sxs-lookup"><span data-stu-id="96e8e-126">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="96e8e-127">Talvez você queira tratar os dispositivos de maneira diferente, dependendo de seus usos.</span><span class="sxs-lookup"><span data-stu-id="96e8e-127">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="identity-and-device-access-configurations"></a><span data-ttu-id="96e8e-128">Identidade e configurações de acesso ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="96e8e-128">Identity and device access configurations</span></span>

<span data-ttu-id="96e8e-129">A Microsoft fornece um conjunto de configurações de acesso a identidades e [dispositivos](../security/office-365-security/microsoft-365-policies-configurations.md) para garantir uma força de trabalho segura e produtiva.</span><span class="sxs-lookup"><span data-stu-id="96e8e-129">Microsoft provides a set of configurations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="96e8e-130">Essas configurações incluem o uso de:</span><span class="sxs-lookup"><span data-stu-id="96e8e-130">These configurations include the use of:</span></span>

- <span data-ttu-id="96e8e-131">Políticas de Acesso Condicional do Azure AD</span><span class="sxs-lookup"><span data-stu-id="96e8e-131">Azure AD Conditional Access policies</span></span>
- <span data-ttu-id="96e8e-132">Conformidade de dispositivos e políticas de proteção de aplicativos do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="96e8e-132">Microsoft Intune device compliance and app protection policies</span></span>
- <span data-ttu-id="96e8e-133">Políticas de risco de usuário do Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="96e8e-133">Azure AD Identity Protection user risk policies</span></span>
- <span data-ttu-id="96e8e-134">Políticas adicionais de aplicativos de nuvem</span><span class="sxs-lookup"><span data-stu-id="96e8e-134">Additional policies of cloud apps</span></span>

<span data-ttu-id="96e8e-135">Aqui está um exemplo da aplicação dessas configurações e políticas para validar e restringir usuários, seus dispositivos e seu uso de aplicativos de produtividade local e na nuvem, como o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="96e8e-135">Here is an example of the application of these settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Configurações de acesso a identidades e dispositivos para requisitos e restrições de usuários, dispositivos e uso de aplicativos](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

<span data-ttu-id="96e8e-137">Para acesso de dispositivos e gerenciamento de aplicativos, use as configurações destes artigos:</span><span class="sxs-lookup"><span data-stu-id="96e8e-137">For device access and app management, use the configurations in these articles:</span></span>

- [<span data-ttu-id="96e8e-138">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="96e8e-138">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="96e8e-139">Identidade comum e políticas de acesso ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="96e8e-139">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a><span data-ttu-id="96e8e-140">Resultados da Etapa 5</span><span class="sxs-lookup"><span data-stu-id="96e8e-140">Results of Step 5</span></span>

<span data-ttu-id="96e8e-141">Para o gerenciamento de dispositivos e aplicativos para seu locatário do Microsoft 365, você determinou as configurações e políticas do Intune para validar e restringir os usuários, seus dispositivos e o uso de aplicativos de produtividade local e na nuvem.</span><span class="sxs-lookup"><span data-stu-id="96e8e-141">For device and app management for your Microsoft 365 tenant, you have determined the Intune settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps.</span></span>

<span data-ttu-id="96e8e-142">Aqui está um exemplo de locatário com gerenciamento de dispositivos e aplicativos do Intune com os novos elementos destacados.</span><span class="sxs-lookup"><span data-stu-id="96e8e-142">Here is an example of a tenant with Intune device and app management with the new elements highlighted.</span></span>

![Exemplo de um locatário com gerenciamento de dispositivos e aplicativos do Intune](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

<span data-ttu-id="96e8e-144">Nesta ilustração, o locatário tem:</span><span class="sxs-lookup"><span data-stu-id="96e8e-144">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="96e8e-145">Dispositivos de propriedade da organização inscritos no Intune.</span><span class="sxs-lookup"><span data-stu-id="96e8e-145">Organization-owned devices enrolled in Intune.</span></span>
- <span data-ttu-id="96e8e-146">Políticas de dispositivos e aplicativos do Intune para dispositivos inscritos e pessoais.</span><span class="sxs-lookup"><span data-stu-id="96e8e-146">Intune device and app policies for enrolled and personal devices.</span></span>

## <a name="ongoing-maintenance-for-device-and-app-management"></a><span data-ttu-id="96e8e-147">Manutenção contínua para gerenciamento de dispositivos e aplicativos</span><span class="sxs-lookup"><span data-stu-id="96e8e-147">Ongoing maintenance for device and app management</span></span>

<span data-ttu-id="96e8e-148">Em uma base contínua, talvez seja necessário:</span><span class="sxs-lookup"><span data-stu-id="96e8e-148">On an ongoing basis, you might need to:</span></span> 

- <span data-ttu-id="96e8e-149">Gerencie o registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="96e8e-149">Manage device enrollment.</span></span>
- <span data-ttu-id="96e8e-150">Revise suas configurações e políticas para aplicativos, dispositivos e requisitos de segurança adicionais.</span><span class="sxs-lookup"><span data-stu-id="96e8e-150">Revise your settings and policies for additional apps, devices, and security requirements.</span></span>