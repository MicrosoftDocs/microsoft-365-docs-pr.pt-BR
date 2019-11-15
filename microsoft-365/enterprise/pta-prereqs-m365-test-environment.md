---
title: Pré-requisitos de acesso a identidades e dispositivos para autenticação de passagem no seu ambiente de teste do Microsoft 365
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Crie um ambiente do Microsoft 365 para testar a identidade e o acesso a dispositivos com os pré-requisitos para a autenticação de passagem.
ms.openlocfilehash: 348885b2cc7a0d6134dce49cd0a2a39706c5e71d
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627485"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a><span data-ttu-id="e2155-103">Pré-requisitos de acesso a identidades e dispositivos para autenticação de passagem no seu ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e2155-103">Identity and device access prerequisites for pass-through authentication in your Microsoft 365 test environment</span></span>

<span data-ttu-id="e2155-104">As [configurações de acesso a identidades e dispositivos](microsoft-365-policies-configurations.md) são um conjunto de configurações e políticas de acesso condicional para proteger o acesso a todos os serviços integrados ao Azure Active Directory (Azure AD), incluindo o Office 365 e o Enterprise Mobility + Security (EMS) no Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e2155-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="e2155-105">Este artigo descreve como você pode configurar um ambiente de teste do Microsoft 365 que atenda aos requisitos da [Configuração de pré-requisitos de autenticação de passagem](identity-access-prerequisites.md#prerequisites) para acesso a identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e2155-105">This article describes how you can configure a Microsoft 365 test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="e2155-106">Existem oito fases para configurar este ambiente de teste:</span><span class="sxs-lookup"><span data-stu-id="e2155-106">There are eight phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="e2155-107">Crie sua empresa simulada com autenticação de passagem no ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e2155-107">Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>
2.  <span data-ttu-id="e2155-108">Configurar logon único contínuo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="e2155-108">Configure Azure AD seamless single sign-on</span></span>
3.  <span data-ttu-id="e2155-109">Configurar localizações nomeadas</span><span class="sxs-lookup"><span data-stu-id="e2155-109">Configure named locations</span></span>
4.  <span data-ttu-id="e2155-110">Configurar o write-back de senha</span><span class="sxs-lookup"><span data-stu-id="e2155-110">Configure password writeback</span></span>
5.  <span data-ttu-id="e2155-111">Configurar a redefinição de senha de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="e2155-111">Configure self-service password reset</span></span>
6.  <span data-ttu-id="e2155-112">Configurar autenticação multifatorial</span><span class="sxs-lookup"><span data-stu-id="e2155-112">Configure multifactor authentication</span></span>
7.  <span data-ttu-id="e2155-113">Habilitar o Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="e2155-113">Enable Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="e2155-114">Habilite a autenticação moderna para o Exchange Online e o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e2155-114">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a><span data-ttu-id="e2155-115">Fase 1: crie sua empresa simulada com autenticação de passagem no ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e2155-115">Phase 1: Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>

<span data-ttu-id="e2155-116">Siga as instruções em [Autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e2155-116">Follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

<span data-ttu-id="e2155-117">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="e2155-117">Here is the resulting configuration.</span></span>

![A empresa simulada com ambiente de teste de autenticação de passagem](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="e2155-119">Fase 2: configurar o logon único contínuo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="e2155-119">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="e2155-120">Siga as instruções na [Fase 2 do Guia do Laboratório de Testes de Logon Único Contínuo do Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="e2155-120">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="e2155-121">Fase 3: Configurar locais nomeados</span><span class="sxs-lookup"><span data-stu-id="e2155-121">Phase 3: Configure named locations</span></span>

<span data-ttu-id="e2155-122">Primeiro, determine os endereços IP públicos ou os intervalos de endereços usados por sua organização.</span><span class="sxs-lookup"><span data-stu-id="e2155-122">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="e2155-123">Em seguida, siga as instruções em [Configurar locais nomeados no Active Directory do Azure](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) para adicionar os endereços ou intervalos de endereços como locais nomeados.</span><span class="sxs-lookup"><span data-stu-id="e2155-123">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="e2155-124">Fase 4: Configurar write-back de senha</span><span class="sxs-lookup"><span data-stu-id="e2155-124">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="e2155-125">Siga as instruções da [Fase 2 do Guia do Laboratório de Teste de write-back de senha](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="e2155-125">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="e2155-126">Fase 5: Configurar a redefinição da senha de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="e2155-126">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="e2155-127">Siga as instruções na [Fase 3 do Guia do Laboratório de Teste de redefinição de senha](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="e2155-127">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="e2155-128">Ao habilitar a redefinição de senha para as contas em um grupo específico do Azure AD, adicione essas contas ao grupo **Redefinição de senha**:</span><span class="sxs-lookup"><span data-stu-id="e2155-128">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="e2155-129">Usuário 2</span><span class="sxs-lookup"><span data-stu-id="e2155-129">User 2</span></span>
- <span data-ttu-id="e2155-130">Usuário 3</span><span class="sxs-lookup"><span data-stu-id="e2155-130">User 3</span></span>
- <span data-ttu-id="e2155-131">Usuário 4</span><span class="sxs-lookup"><span data-stu-id="e2155-131">User 4</span></span>
- <span data-ttu-id="e2155-132">Usuário 5</span><span class="sxs-lookup"><span data-stu-id="e2155-132">User 5</span></span>

<span data-ttu-id="e2155-133">Teste a redefinição de senha somente para a conta do Usuário 2.</span><span class="sxs-lookup"><span data-stu-id="e2155-133">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="e2155-134">Fase 6: Configurar a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="e2155-134">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="e2155-135">Siga as instruções na [Fase 2 do Guia do Laboratório de Teste de autenticação multifator](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) para as seguintes contas de usuário:</span><span class="sxs-lookup"><span data-stu-id="e2155-135">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="e2155-136">Usuário 2</span><span class="sxs-lookup"><span data-stu-id="e2155-136">User 2</span></span>
- <span data-ttu-id="e2155-137">Usuário 3</span><span class="sxs-lookup"><span data-stu-id="e2155-137">User 3</span></span>
- <span data-ttu-id="e2155-138">Usuário 4</span><span class="sxs-lookup"><span data-stu-id="e2155-138">User 4</span></span>
- <span data-ttu-id="e2155-139">Usuário 5</span><span class="sxs-lookup"><span data-stu-id="e2155-139">User 5</span></span>

<span data-ttu-id="e2155-140">Teste a autenticação de vários fatores somente para a conta do Usuário 2.</span><span class="sxs-lookup"><span data-stu-id="e2155-140">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="e2155-141">Fase 7: ativar a proteção de identidade do Azure AD</span><span class="sxs-lookup"><span data-stu-id="e2155-141">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="e2155-142">Siga as instruções na [Fase 2 do Guia do Laboratório de Teste do Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="e2155-142">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="e2155-143">Fase 8: habilite a autenticação moderna para o Exchange Online e o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e2155-143">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="e2155-144">Para o Exchange Online, siga [estas instruções](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="e2155-144">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="e2155-145">Para o Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="e2155-145">For Skype for Business Online:</span></span>

1. <span data-ttu-id="e2155-146">Conecte-se ao [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="e2155-146">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="e2155-147">Execute este comando.</span><span class="sxs-lookup"><span data-stu-id="e2155-147">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="e2155-148">Verifique se a mudança foi bem sucedida com este comando.</span><span class="sxs-lookup"><span data-stu-id="e2155-148">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="e2155-149">O resultado é um ambiente de teste que atende aos requisitos da [configuração de pré-requisito de autenticação de passagem](identity-access-prerequisites.md#prerequisites) para acesso a identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e2155-149">The result is a test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="e2155-150">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="e2155-150">Next step</span></span>

<span data-ttu-id="e2155-151">Use [Políticas comuns de acesso a identidades e dispositivos](identity-access-policies.md) para configurar as políticas criadas com base nos pré-requisitos e proteger identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e2155-151">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2155-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="e2155-152">See also</span></span>

[<span data-ttu-id="e2155-153">Guias adicionais de laboratório de teste de identidade</span><span class="sxs-lookup"><span data-stu-id="e2155-153">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="e2155-154">Fase 2: Identidade</span><span class="sxs-lookup"><span data-stu-id="e2155-154">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="e2155-155">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e2155-155">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e2155-156">Implantação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e2155-156">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="e2155-157">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e2155-157">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

