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
ms.openlocfilehash: 7bef08ba10413f95fb23707ce2ecc4ac248c4bc2
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673317"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a><span data-ttu-id="cb692-103">Pré-requisitos de acesso a identidades e dispositivos para autenticação de passagem no seu ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb692-103">Identity and device access prerequisites for pass-through authentication in your Microsoft 365 test environment</span></span>

<span data-ttu-id="cb692-104">*Este Guia de Laboratório de Testes pode ser usado apenas em ambientes de teste do Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="cb692-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="cb692-105">As [configurações de acesso a identidades e dispositivos](microsoft-365-policies-configurations.md) são um conjunto de configurações e políticas de acesso condicional para proteger o acesso a todos os serviços integrados ao Azure Active Directory (Azure AD), incluindo o Office 365 e o Enterprise Mobility + Security (EMS) no Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="cb692-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="cb692-106">Este artigo descreve como você pode configurar um ambiente de teste do Microsoft 365 que atenda aos requisitos da [Configuração de pré-requisitos de autenticação de passagem](identity-access-prerequisites.md#prerequisites) para acesso a identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="cb692-106">This article describes how you can configure a Microsoft 365 test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="cb692-107">Existem oito fases para configurar este ambiente de teste:</span><span class="sxs-lookup"><span data-stu-id="cb692-107">There are eight phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="cb692-108">Crie sua empresa simulada com autenticação de passagem no ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb692-108">Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>
2.  <span data-ttu-id="cb692-109">Configurar logon único contínuo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="cb692-109">Configure Azure AD seamless single sign-on</span></span>
3.  <span data-ttu-id="cb692-110">Configurar localizações nomeadas</span><span class="sxs-lookup"><span data-stu-id="cb692-110">Configure named locations</span></span>
4.  <span data-ttu-id="cb692-111">Configurar o write-back de senha</span><span class="sxs-lookup"><span data-stu-id="cb692-111">Configure password writeback</span></span>
5.  <span data-ttu-id="cb692-112">Configurar a redefinição de senha de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="cb692-112">Configure self-service password reset</span></span>
6.  <span data-ttu-id="cb692-113">Configurar autenticação multifatorial</span><span class="sxs-lookup"><span data-stu-id="cb692-113">Configure multifactor authentication</span></span>
7.  <span data-ttu-id="cb692-114">Habilitar o Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="cb692-114">Enable Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="cb692-115">Habilite a autenticação moderna para o Exchange Online e o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cb692-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a><span data-ttu-id="cb692-116">Fase 1: crie sua empresa simulada com autenticação de passagem no ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb692-116">Phase 1: Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>

<span data-ttu-id="cb692-117">Siga as instruções em [Autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="cb692-117">Follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

<span data-ttu-id="cb692-118">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="cb692-118">Here is the resulting configuration.</span></span>

![A empresa simulada com ambiente de teste de autenticação de passagem](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="cb692-120">Fase 2: configurar o logon único contínuo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="cb692-120">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="cb692-121">Siga as instruções na [Fase 2 do Guia do Laboratório de Testes de Logon Único Contínuo do Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="cb692-121">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="cb692-122">Fase 3: Configurar locais nomeados</span><span class="sxs-lookup"><span data-stu-id="cb692-122">Phase 3: Configure named locations</span></span>

<span data-ttu-id="cb692-123">Primeiro, determine os endereços IP públicos ou os intervalos de endereços usados por sua organização.</span><span class="sxs-lookup"><span data-stu-id="cb692-123">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="cb692-124">Em seguida, siga as instruções em [Configurar locais nomeados no Active Directory do Azure](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) para adicionar os endereços ou intervalos de endereços como locais nomeados.</span><span class="sxs-lookup"><span data-stu-id="cb692-124">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="cb692-125">Fase 4: Configurar write-back de senha</span><span class="sxs-lookup"><span data-stu-id="cb692-125">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="cb692-126">Siga as instruções da [Fase 2 do Guia do Laboratório de Teste de write-back de senha](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="cb692-126">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="cb692-127">Fase 5: Configurar a redefinição da senha de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="cb692-127">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="cb692-128">Siga as instruções na [Fase 3 do Guia do Laboratório de Teste de redefinição de senha](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="cb692-128">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="cb692-129">Ao habilitar a redefinição de senha para as contas em um grupo específico do Azure AD, adicione essas contas ao grupo **Redefinição de senha**:</span><span class="sxs-lookup"><span data-stu-id="cb692-129">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="cb692-130">Usuário 2</span><span class="sxs-lookup"><span data-stu-id="cb692-130">User 2</span></span>
- <span data-ttu-id="cb692-131">Usuário 3</span><span class="sxs-lookup"><span data-stu-id="cb692-131">User 3</span></span>
- <span data-ttu-id="cb692-132">Usuário 4</span><span class="sxs-lookup"><span data-stu-id="cb692-132">User 4</span></span>
- <span data-ttu-id="cb692-133">Usuário 5</span><span class="sxs-lookup"><span data-stu-id="cb692-133">User 5</span></span>

<span data-ttu-id="cb692-134">Teste a redefinição de senha somente para a conta do Usuário 2.</span><span class="sxs-lookup"><span data-stu-id="cb692-134">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="cb692-135">Fase 6: Configurar a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="cb692-135">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="cb692-136">Siga as instruções na [Fase 2 do Guia do Laboratório de Teste de autenticação multifator](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) para as seguintes contas de usuário:</span><span class="sxs-lookup"><span data-stu-id="cb692-136">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="cb692-137">Usuário 2</span><span class="sxs-lookup"><span data-stu-id="cb692-137">User 2</span></span>
- <span data-ttu-id="cb692-138">Usuário 3</span><span class="sxs-lookup"><span data-stu-id="cb692-138">User 3</span></span>
- <span data-ttu-id="cb692-139">Usuário 4</span><span class="sxs-lookup"><span data-stu-id="cb692-139">User 4</span></span>
- <span data-ttu-id="cb692-140">Usuário 5</span><span class="sxs-lookup"><span data-stu-id="cb692-140">User 5</span></span>

<span data-ttu-id="cb692-141">Teste a autenticação de vários fatores somente para a conta do Usuário 2.</span><span class="sxs-lookup"><span data-stu-id="cb692-141">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="cb692-142">Fase 7: ativar a proteção de identidade do Azure AD</span><span class="sxs-lookup"><span data-stu-id="cb692-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="cb692-143">Siga as instruções na [Fase 2 do Guia do Laboratório de Teste do Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="cb692-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="cb692-144">Fase 8: habilite a autenticação moderna para o Exchange Online e o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cb692-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="cb692-145">Para o Exchange Online, siga [estas instruções](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="cb692-145">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="cb692-146">Para o Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="cb692-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="cb692-147">Conecte-se ao [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="cb692-147">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="cb692-148">Execute este comando.</span><span class="sxs-lookup"><span data-stu-id="cb692-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="cb692-149">Verifique se a mudança foi bem sucedida com este comando.</span><span class="sxs-lookup"><span data-stu-id="cb692-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="cb692-150">O resultado é um ambiente de teste que atende aos requisitos da [configuração de pré-requisito de autenticação de passagem](identity-access-prerequisites.md#prerequisites) para acesso a identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="cb692-150">The result is a test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="cb692-151">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="cb692-151">Next step</span></span>

<span data-ttu-id="cb692-152">Use [Políticas comuns de acesso a identidades e dispositivos](identity-access-policies.md) para configurar as políticas criadas com base nos pré-requisitos e proteger identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="cb692-152">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb692-153">Confira também</span><span class="sxs-lookup"><span data-stu-id="cb692-153">See also</span></span>

[<span data-ttu-id="cb692-154">Guias adicionais de laboratório de teste de identidade</span><span class="sxs-lookup"><span data-stu-id="cb692-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="cb692-155">Fase 2: Identidade</span><span class="sxs-lookup"><span data-stu-id="cb692-155">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="cb692-156">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cb692-156">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="cb692-157">Implantação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cb692-157">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="cb692-158">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cb692-158">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

