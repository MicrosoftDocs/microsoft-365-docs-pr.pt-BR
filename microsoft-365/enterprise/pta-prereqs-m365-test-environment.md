---
title: Pré-requisitos de acesso a identidades e dispositivos para autenticação de passagem no seu ambiente de teste do Microsoft 365
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
description: Crie um ambiente do Microsoft 365 para testar a identidade e o acesso a dispositivos com os pré-requisitos para a autenticação de passagem.
ms.openlocfilehash: 043a8999feb3941569119b5e52d94b0f6dd3533f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051229"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a><span data-ttu-id="1a70b-103">Pré-requisitos de acesso a identidades e dispositivos para autenticação de passagem no seu ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1a70b-103">Identity and device access prerequisites for pass-through authentication in your Microsoft 365 test environment</span></span>

<span data-ttu-id="1a70b-104">*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="1a70b-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="1a70b-105">Configurações de identidade e acesso a dispositivos são um conjunto de configurações e políticas de acesso condicional para proteger o acesso a todos os serviços no Microsoft 365 para empresas [integrados](../security/defender-365-security/microsoft-365-policies-configurations.md) ao Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="1a70b-105">[Identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services in Microsoft 365 for enterprise that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="1a70b-106">Este artigo descreve como você pode configurar um ambiente de teste do Microsoft 365 que atenda aos requisitos da [Configuração de pré-requisitos de autenticação de passagem](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) para acesso a identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1a70b-106">This article describes how you can configure a Microsoft 365 test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="1a70b-107">Há dez fases para configurar esse ambiente de teste:</span><span class="sxs-lookup"><span data-stu-id="1a70b-107">There are ten phases to setting up this test environment:</span></span>

1. <span data-ttu-id="1a70b-108">Crie sua empresa simulada com autenticação de passagem no ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1a70b-108">Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>
2. <span data-ttu-id="1a70b-109">Configurar logon único contínuo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="1a70b-109">Configure Azure AD seamless single sign-on</span></span>
3. <span data-ttu-id="1a70b-110">Configurar localizações nomeadas</span><span class="sxs-lookup"><span data-stu-id="1a70b-110">Configure named locations</span></span>
4. <span data-ttu-id="1a70b-111">Configurar o write-back de senha</span><span class="sxs-lookup"><span data-stu-id="1a70b-111">Configure password writeback</span></span>
5. <span data-ttu-id="1a70b-112">Configurar a redefinição de senha de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="1a70b-112">Configure self-service password reset</span></span>
6. <span data-ttu-id="1a70b-113">Configurar autenticação multifatorial</span><span class="sxs-lookup"><span data-stu-id="1a70b-113">Configure multifactor authentication</span></span>
7. <span data-ttu-id="1a70b-114">Habilitar o registro automático de dispositivo de computadores Windows ingressados no domínio</span><span class="sxs-lookup"><span data-stu-id="1a70b-114">Enable automatic device registration of domain-joined Windows computers</span></span>
8. <span data-ttu-id="1a70b-115">Configurar a proteção de senha do Azure AD</span><span class="sxs-lookup"><span data-stu-id="1a70b-115">Configure Azure AD password protection</span></span> 
9. <span data-ttu-id="1a70b-116">Habilitar o Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="1a70b-116">Enable Azure AD Identity Protection</span></span>
10. <span data-ttu-id="1a70b-117">Habilite a autenticação moderna para o Exchange Online e o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1a70b-117">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a><span data-ttu-id="1a70b-118">Fase 1: crie sua empresa simulada com autenticação de passagem no ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1a70b-118">Phase 1: Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>

<span data-ttu-id="1a70b-119">Siga as instruções em [Autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1a70b-119">Follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

<span data-ttu-id="1a70b-120">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="1a70b-120">Here is the resulting configuration.</span></span>

![A empresa simulada com ambiente de teste de autenticação de passagem](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="1a70b-122">Fase 2: configurar o logon único contínuo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="1a70b-122">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="1a70b-123">Siga as instruções na [Fase 2 do Guia do Laboratório de Testes de Logon Único Contínuo do Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="1a70b-123">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="1a70b-124">Fase 3: Configurar locais nomeados</span><span class="sxs-lookup"><span data-stu-id="1a70b-124">Phase 3: Configure named locations</span></span>

<span data-ttu-id="1a70b-125">Primeiro, determine os endereços IP públicos ou os intervalos de endereços usados por sua organização.</span><span class="sxs-lookup"><span data-stu-id="1a70b-125">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="1a70b-126">Em seguida, siga as instruções em [Configurar locais nomeados no Active Directory do Azure](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) para adicionar os endereços ou intervalos de endereços como locais nomeados.</span><span class="sxs-lookup"><span data-stu-id="1a70b-126">Next, follow the instructions in [Configure named locations in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="1a70b-127">Fase 4: Configurar write-back de senha</span><span class="sxs-lookup"><span data-stu-id="1a70b-127">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="1a70b-128">Siga as instruções da [Fase 2 do Guia do Laboratório de Teste de write-back de senha](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="1a70b-128">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="1a70b-129">Fase 5: Configurar a redefinição da senha de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="1a70b-129">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="1a70b-130">Siga as instruções na [Fase 3 do Guia do Laboratório de Teste de redefinição de senha](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="1a70b-130">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="1a70b-131">Ao habilitar a redefinição de senha para as contas em um grupo específico do Azure AD, adicione essas contas ao grupo **Redefinição de senha**:</span><span class="sxs-lookup"><span data-stu-id="1a70b-131">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="1a70b-132">Usuário 2</span><span class="sxs-lookup"><span data-stu-id="1a70b-132">User 2</span></span>
- <span data-ttu-id="1a70b-133">Usuário 3</span><span class="sxs-lookup"><span data-stu-id="1a70b-133">User 3</span></span>
- <span data-ttu-id="1a70b-134">Usuário 4</span><span class="sxs-lookup"><span data-stu-id="1a70b-134">User 4</span></span>
- <span data-ttu-id="1a70b-135">Usuário 5</span><span class="sxs-lookup"><span data-stu-id="1a70b-135">User 5</span></span>

<span data-ttu-id="1a70b-136">Teste a redefinição de senha somente para a conta do Usuário 2.</span><span class="sxs-lookup"><span data-stu-id="1a70b-136">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="1a70b-137">Fase 6: Configurar a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="1a70b-137">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="1a70b-138">Siga as instruções na [Fase 2 do Guia do Laboratório de Teste de autenticação multifator](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) para as seguintes contas de usuário:</span><span class="sxs-lookup"><span data-stu-id="1a70b-138">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="1a70b-139">Usuário 2</span><span class="sxs-lookup"><span data-stu-id="1a70b-139">User 2</span></span>
- <span data-ttu-id="1a70b-140">Usuário 3</span><span class="sxs-lookup"><span data-stu-id="1a70b-140">User 3</span></span>
- <span data-ttu-id="1a70b-141">Usuário 4</span><span class="sxs-lookup"><span data-stu-id="1a70b-141">User 4</span></span>
- <span data-ttu-id="1a70b-142">Usuário 5</span><span class="sxs-lookup"><span data-stu-id="1a70b-142">User 5</span></span>

<span data-ttu-id="1a70b-143">Teste a autenticação multifator apenas para a conta de Usuário 2.</span><span class="sxs-lookup"><span data-stu-id="1a70b-143">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="1a70b-144">Fase 7: Habilitar o registro automático de dispositivos de computadores Windows ingressados no domínio</span><span class="sxs-lookup"><span data-stu-id="1a70b-144">Phase 7: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="1a70b-145">Siga [estas instruções para](/azure/active-directory/devices/hybrid-azuread-join-plan) habilitar o registro automático de dispositivos de computadores Windows ingressados no domínio.</span><span class="sxs-lookup"><span data-stu-id="1a70b-145">Follow [these instructions](/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-8-configure-azure-ad-password-protection"></a><span data-ttu-id="1a70b-146">Fase 8: Configurar a proteção de senha do Azure AD</span><span class="sxs-lookup"><span data-stu-id="1a70b-146">Phase 8: Configure Azure AD password protection</span></span> 

<span data-ttu-id="1a70b-147">Siga [estas instruções para](/azure/active-directory/authentication/concept-password-ban-bad) bloquear senhas fracas conhecidas e suas variantes.</span><span class="sxs-lookup"><span data-stu-id="1a70b-147">Follow [these instructions](/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-9-enable-azure-ad-identity-protection"></a><span data-ttu-id="1a70b-148">Fase 9: Habilitar a Proteção de Identidade do Azure AD</span><span class="sxs-lookup"><span data-stu-id="1a70b-148">Phase 9: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="1a70b-149">Siga as instruções em [Fase 2 Azure AD Identity Protection do Guia do Laboratório de Teste](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="1a70b-149">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-10-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="1a70b-150">Fase 10: Habilitar a autenticação moderna para o Exchange Online e o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1a70b-150">Phase 10: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="1a70b-151">Para o Exchange Online, siga [estas instruções](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="1a70b-151">For Exchange Online, follow [these instructions](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="1a70b-152">Para o Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="1a70b-152">For Skype for Business Online:</span></span>

1. <span data-ttu-id="1a70b-153">Conecte-se ao [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="1a70b-153">Connect to [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="1a70b-154">Execute este comando.</span><span class="sxs-lookup"><span data-stu-id="1a70b-154">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="1a70b-155">Verifique se a mudança foi bem sucedida com este comando.</span><span class="sxs-lookup"><span data-stu-id="1a70b-155">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="1a70b-156">O resultado é um ambiente de teste que atende aos requisitos da [configuração de pré-requisito de autenticação de passagem](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) para acesso a identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1a70b-156">The result is a test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/defender-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="1a70b-157">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="1a70b-157">Next step</span></span>

<span data-ttu-id="1a70b-158">Use [Políticas comuns de acesso a identidades e dispositivos](../security/defender-365-security/identity-access-policies.md) para configurar as políticas criadas com base nos pré-requisitos e proteger identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1a70b-158">Use [Common identity and device access policies](../security/defender-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a70b-159">Confira também</span><span class="sxs-lookup"><span data-stu-id="1a70b-159">See also</span></span>

[<span data-ttu-id="1a70b-160">Guias adicionais de laboratório de teste de identidade</span><span class="sxs-lookup"><span data-stu-id="1a70b-160">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="1a70b-161">Roteiro de identidade</span><span class="sxs-lookup"><span data-stu-id="1a70b-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="1a70b-162">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="1a70b-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="1a70b-163">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="1a70b-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="1a70b-164">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="1a70b-164">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
