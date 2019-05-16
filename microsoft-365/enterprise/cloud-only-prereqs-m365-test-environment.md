---
title: Pré-requisitos de acesso ao dispositivo e identidade somente nuvem no seu ambiente de teste do Microsoft 365.
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
description: Crie um ambiente do Microsoft 365 para testar o acesso de dispositivo e identidade com os pré-requisitos para autenticação somente nuvem.
ms.openlocfilehash: 9721d2972990998ca345f1d48d96494096f9190e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072561"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="26b74-103">Pré-requisitos de acesso ao dispositivo e identidade somente nuvem no seu ambiente de teste do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26b74-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="26b74-104">[Configurações de acesso de dispositivo e identidade](microsoft-365-policies-configurations.md) são um conjunto políticas de acesso condicional e configurações para proteger o acesso a todos os serviços que são integrados ao Azure Active Directory (Azure AD), incluindo o Office 365 e do Enterprise Mobility + Security (EMS) no Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="26b74-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="26b74-105">Este artigo descreve como configurar um ambiente de teste do Microsoft 365 que atenda aos requisitos das [ configurações com pré-requisitos somente nuvem ](identity-access-prerequisites.md#prerequisites) para acesso ao dispositivo e identidade.</span><span class="sxs-lookup"><span data-stu-id="26b74-105">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="26b74-106">Há sete fases para configurar esse ambiente de teste:</span><span class="sxs-lookup"><span data-stu-id="26b74-106">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="26b74-107">Criar seu ambiente de teste simples</span><span class="sxs-lookup"><span data-stu-id="26b74-107">Build out your lightweight test environment</span></span>
2.  <span data-ttu-id="26b74-108">Configurar localizações nomeadas</span><span class="sxs-lookup"><span data-stu-id="26b74-108">Configure named locations</span></span>
3.  <span data-ttu-id="26b74-109">Configurar o write-back de senha</span><span class="sxs-lookup"><span data-stu-id="26b74-109">Configure password writeback</span></span>
4.  <span data-ttu-id="26b74-110">Configurar a redefinição de senha de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="26b74-110">Configure self-service password resets</span></span>
5.  <span data-ttu-id="26b74-111">Configurar autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="26b74-111">Configure multifactor authentication</span></span>
6.  <span data-ttu-id="26b74-112">Habilitar o Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="26b74-112">Azure AD Identity Protection</span></span>
7.  <span data-ttu-id="26b74-113">Habilitar a autenticação moderna do Exchange Online e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="26b74-113">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="26b74-114">Fase 1: Criar seu ambiente de teste simples do Microsoft 365 </span><span class="sxs-lookup"><span data-stu-id="26b74-114">Phase 1: Build out your lightweight or simulated enterprise Office 365 dev/test environment</span></span>

<span data-ttu-id="26b74-115">Siga as instruções em [Configuração de base leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="26b74-115">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="26b74-116">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="26b74-116">Here is the resulting configuration.</span></span>

![O ambiente de teste leve do Microsoft 3656 Enterprise](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="26b74-118">Fase 2: Configurar localizações nomeadas</span><span class="sxs-lookup"><span data-stu-id="26b74-118">Phase 2: Configure named locations</span></span>

<span data-ttu-id="26b74-119">Primeiro, determine os endereços IP públicos ou intervalos de endereços usados pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="26b74-119">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="26b74-120">Em seguida, siga as instruções em [Configurar locais nomeados no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) para adicionar os endereços ou intervalos de endereços como locais nomeados.</span><span class="sxs-lookup"><span data-stu-id="26b74-120">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-password-writeback"></a><span data-ttu-id="26b74-121">Fase 3: Configurar o write-back de senha</span><span class="sxs-lookup"><span data-stu-id="26b74-121">Phase 3: Configure password writeback</span></span>

<span data-ttu-id="26b74-122">Siga as instruções em [Fase 2 do write-back de senha do Guia de Laboratório de Teste](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="26b74-122">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-4-configure-self-service-password-reset"></a><span data-ttu-id="26b74-123">Fase 4: Configurar a redefinição de senha de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="26b74-123">Phase 4: Configure self-service password reset</span></span>

<span data-ttu-id="26b74-124">Siga as instruções em [Fase 3 da redefinição de senha do Guia do Laboratório de Teste](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="26b74-124">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="26b74-125">Ao habilitar a redefinição de senha para as contas em um grupo específico do Azure AD, adicione essas contas ao grupo **Redefinição de senha**:</span><span class="sxs-lookup"><span data-stu-id="26b74-125">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="26b74-126">Usuário 2</span><span class="sxs-lookup"><span data-stu-id="26b74-126">User: %2</span></span>
- <span data-ttu-id="26b74-127">Usuário 3</span><span class="sxs-lookup"><span data-stu-id="26b74-127">User Defined 3</span></span>
- <span data-ttu-id="26b74-128">Usuário 4</span><span class="sxs-lookup"><span data-stu-id="26b74-128">User: %4</span></span>
- <span data-ttu-id="26b74-129">Usuário 5</span><span class="sxs-lookup"><span data-stu-id="26b74-129">User 5</span></span>

<span data-ttu-id="26b74-130">Teste a redefinição de senha apenas na conta do Usuário 2.</span><span class="sxs-lookup"><span data-stu-id="26b74-130">Next, you test password reset for the User 2 account.</span></span>

## <a name="phase-5-configure-multi-factor-authentication"></a><span data-ttu-id="26b74-131">Fase 5: Configurar autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="26b74-131">Phase 5: Configure multi-factor authentication</span></span>

<span data-ttu-id="26b74-132">Siga as instruções na [Fase 2 de autenticação multifator do Guia de Laboratório de Teste](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) para as seguintes contas de usuário:</span><span class="sxs-lookup"><span data-stu-id="26b74-132">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="26b74-133">Usuário 2</span><span class="sxs-lookup"><span data-stu-id="26b74-133">User: %2</span></span>
- <span data-ttu-id="26b74-134">Usuário 3</span><span class="sxs-lookup"><span data-stu-id="26b74-134">User Defined 3</span></span>
- <span data-ttu-id="26b74-135">Usuário 4</span><span class="sxs-lookup"><span data-stu-id="26b74-135">User: %4</span></span>
- <span data-ttu-id="26b74-136">Usuário 5</span><span class="sxs-lookup"><span data-stu-id="26b74-136">User 5</span></span>

<span data-ttu-id="26b74-137">Teste a autenticação multifator apenas para a conta de Usuário 2.</span><span class="sxs-lookup"><span data-stu-id="26b74-137">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-6-enable-azure-ad-identity-protection"></a><span data-ttu-id="26b74-138">Fase 6: Habilitar o Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="26b74-138">Phase 6: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="26b74-139">Siga as instruções em [Fase 2 Azure AD Identity Protection do Guia do Laboratório de Teste](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="26b74-139">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="26b74-140">Fase 7: Habilitar a autenticação moderna do Exchange Online e do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="26b74-140">Phase 7: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="26b74-141">Para o Exchange Online, siga [estas instruções](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span><span class="sxs-lookup"><span data-stu-id="26b74-141">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="26b74-142">Para o Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="26b74-142">Skype for Business Online</span></span>

1. <span data-ttu-id="26b74-143">Conecte-se ao [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="26b74-143">[Migrate to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). (Administrator)</span></span>

2. <span data-ttu-id="26b74-144">Execute este comando.</span><span class="sxs-lookup"><span data-stu-id="26b74-144">Run this command:</span></span>

  ```
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="26b74-145">Verifique se a alteração foi bem-sucedida com esse comando.</span><span class="sxs-lookup"><span data-stu-id="26b74-145">Ensure that the download was successful with this command.</span></span>

  ```
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="26b74-146">O resultado é um ambiente de teste que atende aos requisitos das [ configurações com pré-requisitos somente nuvem ](identity-access-prerequisites.md#prerequisites) para acesso ao dispositivo e identidade.</span><span class="sxs-lookup"><span data-stu-id="26b74-146">The result is a test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="26b74-147">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="26b74-147">Next step</span></span>

<span data-ttu-id="26b74-148">Use [Políticas comuns de acesso a identidades e dispositivos](identity-access-policies.md) para configurar as políticas criadas com base nos pré-requisitos e proteger identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="26b74-148">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="26b74-149">Confira também</span><span class="sxs-lookup"><span data-stu-id="26b74-149">See also</span></span>

[<span data-ttu-id="26b74-150">Guias adicionais de laboratório de teste de identidade</span><span class="sxs-lookup"><span data-stu-id="26b74-150">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="26b74-151">Fase 2: Identidade</span><span class="sxs-lookup"><span data-stu-id="26b74-151">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="26b74-152">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="26b74-152">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="26b74-153">Implantação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="26b74-153">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="26b74-154">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="26b74-154">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
