---
title: Guias do Laboratório de Teste do Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Use estes Guias de Laboratório de Teste para configurar a demonstração, prova de conceito ou ambientes de desenvolvimento/teste para o Microsoft 365 para empresas.
ms.openlocfilehash: 685bf25db330b4bf43a3a7258aeb43517c239e81
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686761"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a><span data-ttu-id="c3afb-103">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="c3afb-103">Microsoft 365 for enterprise Test Lab Guides</span></span>

<span data-ttu-id="c3afb-104">*Isso se aplica ao Microsoft 365 para empresas e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c3afb-104">*This applies to both Microsoft 365 for enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c3afb-p101">Os TLGs (Guias de Laboratório de Teste) ajudam a aprender rapidamente sobre os produtos da Microsoft. Eles fornecem instruções dirigidas para configurar os ambientes de testes representativos, mas simplificados. Você pode usar esses ambientes para demonstração, personalização ou criação de provas complexas de conceito durante a vigência de uma assinatura de avaliação ou paga.</span><span class="sxs-lookup"><span data-stu-id="c3afb-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="c3afb-p102">Os TLGs foram projetados para serem modulares. Eles se complementam para criar várias configurações que correspondem melhor às suas necessidades de configuração de teste ou aprendizado. A experiência prática no estilo "criei por conta própria e funciona" ajuda você a entender os requisitos de implantação de um novo produto ou cenário para poder planejar melhor sua hospedagem em produção.</span><span class="sxs-lookup"><span data-stu-id="c3afb-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="c3afb-111">Você também pode usar os TLGs para criar ambientes representativos de desenvolvimento e teste de aplicativos, conhecidos como ambientes de desenvolvimento/teste.</span><span class="sxs-lookup"><span data-stu-id="c3afb-111">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="c3afb-113">Acesse [Pilha de guias do laboratório de teste](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para obter um mapa visual de todos os artigos na Pilha de guias de laboratório de teste do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="c3afb-113">Go to the [Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

<span data-ttu-id="c3afb-114">[![A pilha da Guia do Laboratório de Teste do Microsoft 365 para empresas](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="c3afb-114">[![The Microsoft 365 for enterprise Test Lab Guide stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="c3afb-115">Configuração base</span><span class="sxs-lookup"><span data-stu-id="c3afb-115">Base configuration</span></span>

<span data-ttu-id="c3afb-p103">Primeiro, você cria um ambiente de teste para [o Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/). Você pode criar dois tipos diferentes de configurações básicas:</span><span class="sxs-lookup"><span data-stu-id="c3afb-p103">First, you create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/). You can create two different types of base configurations:</span></span>

- <span data-ttu-id="c3afb-118">Use a [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md) quando quiser configurar e demonstrar recursos e capacidades do Microsoft 365 para empresas em um ambiente exclusivamente em nuvem, que não inclui nenhum componente local.</span><span class="sxs-lookup"><span data-stu-id="c3afb-118">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="c3afb-119">Use a [configuração básica corporativa simulada](simulated-ent-base-configuration-microsoft-365-enterprise.md) quando quiser configurar e demonstrar recursos e capacidades do Microsoft 365 para empresas em um ambiente exclusivamente em nuvem híbrida, que usa componentes locais como o domínio dos Serviços de Domínio do Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="c3afb-119">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="c3afb-120">Você também pode criar ambientes de teste do Office 365 E5, não adicionando a licença da Microsoft 365 E5 ao seu ambiente de avaliação ou produção.</span><span class="sxs-lookup"><span data-stu-id="c3afb-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="c3afb-121">Identidade</span><span class="sxs-lookup"><span data-stu-id="c3afb-121">Identity</span></span>

<span data-ttu-id="c3afb-122">Para demonstrar recursos e capacidades relacionados à identidade, confira:</span><span class="sxs-lookup"><span data-stu-id="c3afb-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="c3afb-123">Sincronização de hash de senha</span><span class="sxs-lookup"><span data-stu-id="c3afb-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="c3afb-124">Habilite e teste a sincronização de diretório baseado em hash de senha de um controlador de domínio do AD DS.</span><span class="sxs-lookup"><span data-stu-id="c3afb-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="c3afb-125">Autenticação de passagem</span><span class="sxs-lookup"><span data-stu-id="c3afb-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="c3afb-126">Habilite e teste a autenticação de passagem para um controlador de domínio do AD DS.</span><span class="sxs-lookup"><span data-stu-id="c3afb-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="c3afb-127">Autenticação federada</span><span class="sxs-lookup"><span data-stu-id="c3afb-127">Federated authentication</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
   <span data-ttu-id="c3afb-128">Habilite e teste a autenticação federada para um controlador de domínio do AD DS.</span><span class="sxs-lookup"><span data-stu-id="c3afb-128">Enable and test federated authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="c3afb-129">Logon único contínuo do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c3afb-129">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="c3afb-130">Habilite e teste o Logon Único Contínuo (SSO) do Azure AD com um controlador de domínio do AD DS.</span><span class="sxs-lookup"><span data-stu-id="c3afb-130">Enable and test Azure AD Seamless Single Sign-on (SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="c3afb-131">Autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="c3afb-131">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="c3afb-132">Habilite e teste a autenticação multifator com base em smartphone para uma conta de usuário específica.</span><span class="sxs-lookup"><span data-stu-id="c3afb-132">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="c3afb-133">Proteger contas de administradores globais</span><span class="sxs-lookup"><span data-stu-id="c3afb-133">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="c3afb-134">Bloqueie suas contas globais de administrador com políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="c3afb-134">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="c3afb-135">Senha write-back</span><span class="sxs-lookup"><span data-stu-id="c3afb-135">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="c3afb-136">Use senha write-back para alternar a senha na sua conta de usuário do AD DS do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c3afb-136">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="c3afb-137">Redefinição de senha</span><span class="sxs-lookup"><span data-stu-id="c3afb-137">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="c3afb-138">Use SSPR (Redefinição de senha de autoatendimento) para redefinir sua senha.</span><span class="sxs-lookup"><span data-stu-id="c3afb-138">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="c3afb-139">Licenciamento automático e associação de grupo</span><span class="sxs-lookup"><span data-stu-id="c3afb-139">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="c3afb-140">Faça com que administrar novas contas seja mais fácil do que nunca com o licenciamento automático e associação dinâmica a grupos.</span><span class="sxs-lookup"><span data-stu-id="c3afb-140">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="c3afb-141">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="c3afb-141">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="c3afb-142">Verifique a existência de vulnerabilidades na sua conta de usuário atual.</span><span class="sxs-lookup"><span data-stu-id="c3afb-142">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="c3afb-143">Acesso a identidades e dispositivos</span><span class="sxs-lookup"><span data-stu-id="c3afb-143">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="c3afb-144">Crie um ambiente para testar configurações recomendadas de acesso a identidades e dispositivos e políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="c3afb-144">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>


## <a name="mobile-device-management"></a><span data-ttu-id="c3afb-145">Gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="c3afb-145">Mobile device management</span></span>

<span data-ttu-id="c3afb-146">Para demonstrar recursos relacionados ao gerenciamento de dispositivo móvel, confira:</span><span class="sxs-lookup"><span data-stu-id="c3afb-146">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="c3afb-147">Políticas de conformidade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="c3afb-147">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="c3afb-148">Criar uma política de conformidade do dispositivo e um grupo de usuários para dispositivos com Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c3afb-148">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="c3afb-149">Registrar dispositivos iOS e Android</span><span class="sxs-lookup"><span data-stu-id="c3afb-149">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="c3afb-150">Registre os dispositivos iOS ou Android e gerencie-os remotamente.</span><span class="sxs-lookup"><span data-stu-id="c3afb-150">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="c3afb-151">Proteção de informações</span><span class="sxs-lookup"><span data-stu-id="c3afb-151">Information protection</span></span>

<span data-ttu-id="c3afb-152">Para demonstrar recursos e capacidades relacionados à proteção da informação, confira:</span><span class="sxs-lookup"><span data-stu-id="c3afb-152">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="c3afb-153">Segurança do Microsoft 365 aumentada</span><span class="sxs-lookup"><span data-stu-id="c3afb-153">Increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="c3afb-154">Defina as configurações para aumentar a segurança do Microsoft 365 e investigar as ferramentas de segurança internas.</span><span class="sxs-lookup"><span data-stu-id="c3afb-154">Configure settings for increased Microsoft 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="c3afb-155">Classificação de dados</span><span class="sxs-lookup"><span data-stu-id="c3afb-155">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="c3afb-156">Configure e aplique rótulos a um documento em um site de equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c3afb-156">Configure and apply labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="c3afb-157">Gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="c3afb-157">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="c3afb-158">Configure o gerenciamento de acesso privilegiado para acesso na hora certa às tarefas elevadas e privilegiadas na sua organização.</span><span class="sxs-lookup"><span data-stu-id="c3afb-158">Configure privileged access management for just-in-time access to elevated and privileged tasks in your organization.</span></span>


