---
title: Pré-requisitos de acesso ao dispositivo e identidade somente nuvem no seu ambiente de teste do Microsoft 365.
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
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Crie um ambiente do Microsoft 365 para testar o acesso de dispositivo e identidade com os pré-requisitos para autenticação somente nuvem.
ms.openlocfilehash: 927aa032e4181206b3a744da7076b696ac5cf4d4
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199544"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="79e4b-103">Pré-requisitos de acesso ao dispositivo e identidade somente nuvem no seu ambiente de teste do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="79e4b-103">Identity and device access prerequisites for cloud only in your Microsoft 365 test environment</span></span>

<span data-ttu-id="79e4b-104">*Este Guia de Laboratório de Teste só pode ser usado para Microsoft 365 ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="79e4b-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="79e4b-105">[Configurações de identidade](../security/office-365-security/microsoft-365-policies-configurations.md) e acesso a dispositivos são um conjunto de configurações recomendadas e políticas de acesso condicional para proteger o acesso a todos os serviços integrados ao Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="79e4b-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="79e4b-106">Este artigo descreve como configurar um ambiente de teste do Microsoft 365 que atenda aos requisitos das [ configurações com pré-requisitos somente nuvem ](../security/office-365-security/identity-access-prerequisites.md#prerequisites) para acesso ao dispositivo e identidade.</span><span class="sxs-lookup"><span data-stu-id="79e4b-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="79e4b-107">Existem oito fases para configurar este ambiente de teste:</span><span class="sxs-lookup"><span data-stu-id="79e4b-107">There are eight phases to setting up this test environment:</span></span>

1. <span data-ttu-id="79e4b-108">Criar seu ambiente de teste simples</span><span class="sxs-lookup"><span data-stu-id="79e4b-108">Build out your lightweight test environment</span></span>
2. <span data-ttu-id="79e4b-109">Configurar localizações nomeadas</span><span class="sxs-lookup"><span data-stu-id="79e4b-109">Configure named locations</span></span>
3. <span data-ttu-id="79e4b-110">Configurar a redefinição de senha de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="79e4b-110">Configure self-service password reset</span></span>
4. <span data-ttu-id="79e4b-111">Configurar autenticação multifatorial</span><span class="sxs-lookup"><span data-stu-id="79e4b-111">Configure multifactor authentication</span></span>
5. <span data-ttu-id="79e4b-112">Habilitar o registro automático de dispositivos de computadores Windows ingressados no domínio</span><span class="sxs-lookup"><span data-stu-id="79e4b-112">Enable automatic device registration of domain-joined Windows computers</span></span>
6. <span data-ttu-id="79e4b-113">Configurar a proteção de senha do Azure AD</span><span class="sxs-lookup"><span data-stu-id="79e4b-113">Configure Azure AD password protection</span></span> 
7. <span data-ttu-id="79e4b-114">Habilitar o Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="79e4b-114">Enable Azure AD Identity Protection</span></span>
8. <span data-ttu-id="79e4b-115">Habilitar a autenticação moderna do Exchange Online e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="79e4b-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="79e4b-116">Fase 1: Criar seu ambiente de teste simples do Microsoft 365 </span><span class="sxs-lookup"><span data-stu-id="79e4b-116">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="79e4b-117">Siga as instruções em [Configuração de base leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="79e4b-117">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="79e4b-118">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="79e4b-118">Here is the resulting configuration.</span></span>

![O ambiente de teste leve do Microsoft 3656 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 
## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="79e4b-120">Fase 2: Configurar localizações nomeadas</span><span class="sxs-lookup"><span data-stu-id="79e4b-120">Phase 2: Configure named locations</span></span>

<span data-ttu-id="79e4b-121">Primeiro, determine os endereços IP públicos ou intervalos de endereços usados pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="79e4b-121">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="79e4b-122">Em seguida, siga as instruções em [Configurar locais nomeados no Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) para adicionar os endereços ou intervalos de endereços como locais nomeados.</span><span class="sxs-lookup"><span data-stu-id="79e4b-122">Next, follow the instructions in [Configure named locations in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-self-service-password-reset"></a><span data-ttu-id="79e4b-123">Fase 3: Configurar redefinição de senha de autoatendados</span><span class="sxs-lookup"><span data-stu-id="79e4b-123">Phase 3: Configure self-service password reset</span></span>

<span data-ttu-id="79e4b-124">Siga as instruções em [Fase 3 da redefinição de senha do Guia do Laboratório de Teste](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="79e4b-124">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="79e4b-125">Ao habilitar a redefinição de senha para as contas em um grupo específico do Azure AD, adicione essas contas ao grupo **Redefinição de senha**:</span><span class="sxs-lookup"><span data-stu-id="79e4b-125">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="79e4b-126">Usuário 2</span><span class="sxs-lookup"><span data-stu-id="79e4b-126">User 2</span></span>
- <span data-ttu-id="79e4b-127">Usuário 3</span><span class="sxs-lookup"><span data-stu-id="79e4b-127">User 3</span></span>
- <span data-ttu-id="79e4b-128">Usuário 4</span><span class="sxs-lookup"><span data-stu-id="79e4b-128">User 4</span></span>
- <span data-ttu-id="79e4b-129">Usuário 5</span><span class="sxs-lookup"><span data-stu-id="79e4b-129">User 5</span></span>

<span data-ttu-id="79e4b-130">Teste a redefinição de senha apenas na conta do Usuário 2.</span><span class="sxs-lookup"><span data-stu-id="79e4b-130">Test password reset only for the User 2 account.</span></span>

## <a name="phase-4-configure-multi-factor-authentication"></a><span data-ttu-id="79e4b-131">Fase 4: Configurar a autenticação multifatória</span><span class="sxs-lookup"><span data-stu-id="79e4b-131">Phase 4: Configure multi-factor authentication</span></span>

<span data-ttu-id="79e4b-132">Siga as instruções na [Fase 2 de autenticação multifator do Guia de Laboratório de Teste](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) para as seguintes contas de usuário:</span><span class="sxs-lookup"><span data-stu-id="79e4b-132">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="79e4b-133">Usuário 2</span><span class="sxs-lookup"><span data-stu-id="79e4b-133">User 2</span></span>
- <span data-ttu-id="79e4b-134">Usuário 3</span><span class="sxs-lookup"><span data-stu-id="79e4b-134">User 3</span></span>
- <span data-ttu-id="79e4b-135">Usuário 4</span><span class="sxs-lookup"><span data-stu-id="79e4b-135">User 4</span></span>
- <span data-ttu-id="79e4b-136">Usuário 5</span><span class="sxs-lookup"><span data-stu-id="79e4b-136">User 5</span></span>

<span data-ttu-id="79e4b-137">Teste a autenticação multifator apenas para a conta de Usuário 2.</span><span class="sxs-lookup"><span data-stu-id="79e4b-137">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-5-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="79e4b-138">Fase 5: Habilitar o registro automático de dispositivos de computadores Windows ingressados no domínio</span><span class="sxs-lookup"><span data-stu-id="79e4b-138">Phase 5: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="79e4b-139">Siga [estas instruções para](/azure/active-directory/devices/hybrid-azuread-join-plan) habilitar o registro automático de dispositivos de computadores Windows de domínio.</span><span class="sxs-lookup"><span data-stu-id="79e4b-139">Follow [these instructions](/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-6-configure-azure-ad-password-protection"></a><span data-ttu-id="79e4b-140">Fase 6: Configurar a proteção de senha do Azure AD</span><span class="sxs-lookup"><span data-stu-id="79e4b-140">Phase 6: Configure Azure AD password protection</span></span> 

<span data-ttu-id="79e4b-141">Siga [estas instruções para](/azure/active-directory/authentication/concept-password-ban-bad) bloquear senhas fracas conhecidas e suas variantes.</span><span class="sxs-lookup"><span data-stu-id="79e4b-141">Follow [these instructions](/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="79e4b-142">Fase 7: ativar a proteção de identidade do Azure AD</span><span class="sxs-lookup"><span data-stu-id="79e4b-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="79e4b-143">Siga as instruções na [Fase 2 do Guia do Laboratório de Teste do Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="79e4b-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="79e4b-144">Fase 8: habilite a autenticação moderna para o Exchange Online e o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="79e4b-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="79e4b-145">Para o Exchange Online, siga [estas instruções](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="79e4b-145">For Exchange Online, follow [these instructions](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="79e4b-146">Para o Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="79e4b-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="79e4b-147">Conecte-se ao [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="79e4b-147">Connect to [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="79e4b-148">Execute este comando.</span><span class="sxs-lookup"><span data-stu-id="79e4b-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="79e4b-149">Verifique se a alteração foi bem-sucedida com esse comando.</span><span class="sxs-lookup"><span data-stu-id="79e4b-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="79e4b-150">O resultado é um ambiente de teste que atende aos requisitos da configuração de [pré-requisito](../security/office-365-security/identity-access-prerequisites.md#prerequisites) somente na nuvem para acesso à identidade e ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="79e4b-150">The result is a test environment that meets the requirements of the [cloud-only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="79e4b-151">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="79e4b-151">Next step</span></span>

<span data-ttu-id="79e4b-152">Use [Políticas comuns de acesso a identidades e dispositivos](../security/office-365-security/identity-access-policies.md) para configurar as políticas criadas com base nos pré-requisitos e proteger identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="79e4b-152">Use [Common identity and device access policies](../security/office-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="79e4b-153">Confira também</span><span class="sxs-lookup"><span data-stu-id="79e4b-153">See also</span></span>

[<span data-ttu-id="79e4b-154">Guias adicionais de laboratório de teste de identidade</span><span class="sxs-lookup"><span data-stu-id="79e4b-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="79e4b-155">Roteiro de identidade</span><span class="sxs-lookup"><span data-stu-id="79e4b-155">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="79e4b-156">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="79e4b-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="79e4b-157">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="79e4b-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="79e4b-158">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="79e4b-158">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
