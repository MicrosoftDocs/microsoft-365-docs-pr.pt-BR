---
title: Pré-requisitos de acesso a identidades e dispositivos para sincronização de hash de senha no seu ambiente de teste do Microsoft 365
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
description: Crie um ambiente do Microsoft 365 para testar o acesso a identidades e dispositivos com os pré-requisitos para a autenticação de sincronização de hash de senha.
ms.openlocfilehash: 274f73b1cd6a925b972ab14417c9d854c48c2f00
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074151"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a><span data-ttu-id="376bd-103">Pré-requisitos de acesso a identidades e dispositivos para sincronização de hash de senha no seu ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="376bd-103">Identity and device access prerequisites for password hash synchronization in your Microsoft 365 test environment</span></span>

<span data-ttu-id="376bd-104">As [configurações de acesso a identidades e dispositivos](microsoft-365-policies-configurations.md) são um conjunto de configurações e políticas de acesso condicional para proteger o acesso a todos os serviços integrados ao Azure Active Directory (Azure AD), incluindo o Office 365 e o Enterprise Mobility + Security (EMS) no Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="376bd-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="376bd-105">Este artigo descreve como configurar um ambiente de teste do Microsoft 365 que atenda aos requisitos do [Active Directory com a configuração de pré-requisito de sincronização de hash de senha](identity-access-prerequisites.md#prerequisites) para acesso a identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="376bd-105">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="376bd-106">Existem oito fases para configurar este ambiente de teste:</span><span class="sxs-lookup"><span data-stu-id="376bd-106">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="376bd-107">Crie uma empresa simulada com o ambiente de teste de sincronização de hash de senha</span><span class="sxs-lookup"><span data-stu-id="376bd-107">Create a simulated enterprise with password hash sync test environment</span></span>
2.  <span data-ttu-id="376bd-108">Configurar logon único contínuo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="376bd-108">Configure Azure AD single sign-on</span></span>
3.  <span data-ttu-id="376bd-109">Configurar localizações nomeadas</span><span class="sxs-lookup"><span data-stu-id="376bd-109">Configure named locations</span></span>
4.  <span data-ttu-id="376bd-110">Configurar o write-back de senha</span><span class="sxs-lookup"><span data-stu-id="376bd-110">Configure password writeback</span></span>
5.  <span data-ttu-id="376bd-111">Configurar redefinição de senha de autoatendimento para todas as contas de usuário</span><span class="sxs-lookup"><span data-stu-id="376bd-111">Configure self-service password reset for all user accounts</span></span>
6.  <span data-ttu-id="376bd-112">Configurar autenticação multifator para todas as contas de usuário</span><span class="sxs-lookup"><span data-stu-id="376bd-112">Configure multifactor authentication for all user accounts</span></span>
7.  <span data-ttu-id="376bd-113">Habilitar o Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="376bd-113">Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="376bd-114">Habilite a autenticação moderna para o Exchange Online e o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="376bd-114">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a><span data-ttu-id="376bd-115">Fase 1: construa sua empresa simulada com sincronização de hash de senha no ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="376bd-115">Phase 1: Build out your simulated enterprise with password hash sync Microsoft 365 test environment</span></span>

<span data-ttu-id="376bd-116">Siga as instruções em [Sincronização de hash de senha](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="376bd-116">Follow the instructions in [Password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span>
<span data-ttu-id="376bd-117">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="376bd-117">Here is the resulting configuration.</span></span>

![Empresa simulada com ambiente de teste de sincronização de hash de senha](media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="376bd-119">Fase 2: configurar o logon único contínuo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="376bd-119">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="376bd-120">Siga as instruções na [Fase 2 do Guia do Laboratório de Testes de Logon Único Contínuo do Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="376bd-120">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="376bd-121">Fase 3: Configurar locais nomeados</span><span class="sxs-lookup"><span data-stu-id="376bd-121">Phase 3: Configure named locations</span></span>

<span data-ttu-id="376bd-122">Primeiro, determine os endereços IP públicos ou os intervalos de endereços usados por sua organização.</span><span class="sxs-lookup"><span data-stu-id="376bd-122">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="376bd-123">Em seguida, siga as instruções em [Configurar locais nomeados no Active Directory do Azure](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) para adicionar os endereços ou intervalos de endereços como locais nomeados.</span><span class="sxs-lookup"><span data-stu-id="376bd-123">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="376bd-124">Fase 4: Configurar write-back de senha</span><span class="sxs-lookup"><span data-stu-id="376bd-124">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="376bd-125">Siga as instruções da [Fase 2 do Guia do Laboratório de Teste de write-back de senha](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="376bd-125">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="376bd-126">Fase 5: Configurar a redefinição da senha de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="376bd-126">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="376bd-127">Siga as instruções na [Fase 3 do Guia do Laboratório de Teste de redefinição de senha](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="376bd-127">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="376bd-128">Ao habilitar a redefinição de senha para as contas em um grupo específico do Azure AD, adicione essas contas ao grupo **Redefinição de senha**:</span><span class="sxs-lookup"><span data-stu-id="376bd-128">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="376bd-129">Usuário 2</span><span class="sxs-lookup"><span data-stu-id="376bd-129">User: %2</span></span>
- <span data-ttu-id="376bd-130">Usuário 3</span><span class="sxs-lookup"><span data-stu-id="376bd-130">User Defined 3</span></span>
- <span data-ttu-id="376bd-131">Usuário 4</span><span class="sxs-lookup"><span data-stu-id="376bd-131">User: %4</span></span>
- <span data-ttu-id="376bd-132">Usuário 5</span><span class="sxs-lookup"><span data-stu-id="376bd-132">User 5</span></span>

<span data-ttu-id="376bd-133">Teste a redefinição de senha somente para a conta do Usuário 2.</span><span class="sxs-lookup"><span data-stu-id="376bd-133">Next, you test password reset for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="376bd-134">Fase 6: Configurar a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="376bd-134">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="376bd-135">Siga as instruções na [Fase 2 do Guia do Laboratório de Teste de autenticação multifator](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) para as seguintes contas de usuário:</span><span class="sxs-lookup"><span data-stu-id="376bd-135">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="376bd-136">Usuário 2</span><span class="sxs-lookup"><span data-stu-id="376bd-136">User: %2</span></span>
- <span data-ttu-id="376bd-137">Usuário 3</span><span class="sxs-lookup"><span data-stu-id="376bd-137">User Defined 3</span></span>
- <span data-ttu-id="376bd-138">Usuário 4</span><span class="sxs-lookup"><span data-stu-id="376bd-138">User: %4</span></span>
- <span data-ttu-id="376bd-139">Usuário 5</span><span class="sxs-lookup"><span data-stu-id="376bd-139">User 5</span></span>

<span data-ttu-id="376bd-140">Teste a autenticação de vários fatores somente para a conta do Usuário 2.</span><span class="sxs-lookup"><span data-stu-id="376bd-140">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="376bd-141">Fase 7: ativar a proteção de identidade do Azure AD</span><span class="sxs-lookup"><span data-stu-id="376bd-141">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="376bd-142">Siga as instruções na [Fase 2 do Guia do Laboratório de Teste do Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="376bd-142">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="376bd-143">Fase 8: habilite a autenticação moderna para o Exchange Online e o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="376bd-143">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="376bd-144">Para o Exchange Online, siga [estas instruções](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="376bd-144">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="376bd-145">Para o Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="376bd-145">Skype for Business Online</span></span>

1. <span data-ttu-id="376bd-146">Conecte-se ao [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="376bd-146">[Migrate to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). (Administrator)</span></span>

2. <span data-ttu-id="376bd-147">Execute este comando.</span><span class="sxs-lookup"><span data-stu-id="376bd-147">Run this command:</span></span>

  ```
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="376bd-148">Verifique se a mudança foi bem sucedida com este comando.</span><span class="sxs-lookup"><span data-stu-id="376bd-148">Ensure that the download was successful with this command.</span></span>

  ```
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="376bd-149">O resultado é um ambiente de teste que atende aos requisitos de [configuração de pré-requisito de sincronização de hash de senha do Active Directory](identity-access-prerequisites.md#prerequisites) para acesso a identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="376bd-149">The result is a test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="376bd-150">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="376bd-150">Next step</span></span>

<span data-ttu-id="376bd-151">Use [Políticas comuns de acesso a identidades e dispositivos](identity-access-policies.md) para configurar as políticas criadas com base nos pré-requisitos e proteger identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="376bd-151">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="376bd-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="376bd-152">See also</span></span>

[<span data-ttu-id="376bd-153">Guias adicionais de laboratório de teste de identidade</span><span class="sxs-lookup"><span data-stu-id="376bd-153">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="376bd-154">Fase 2: Identidade</span><span class="sxs-lookup"><span data-stu-id="376bd-154">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="376bd-155">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="376bd-155">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="376bd-156">Implantação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="376bd-156">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="376bd-157">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="376bd-157">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
