---
title: Identidade e dispositivo comuns acessar diretivas - Microsoft 365 Enterprise | Documentos do Microsoft
description: Descreve as políticas para as recomendações da Microsoft sobre como aplicar as configurações e políticas de dispositivo e identidade.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: ab8454c27cd57b6bd5cc8df6e1526ee2950ac998
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865314"
---
# <a name="common-identity-and-device-access-policies"></a><span data-ttu-id="10c43-103">Identidade comum e políticas de acesso ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="10c43-103">Common identity and device access policies</span></span>
<span data-ttu-id="10c43-104">Este artigo descreve o comum recomendado políticas para proteger o acesso para a nuvem de serviços, incluindo aplicativos de local publicado com Proxy de aplicativo do Windows Azure AD.</span><span class="sxs-lookup"><span data-stu-id="10c43-104">This article describes the common recommended policies for securing access to cloud services, including on-premises applications published with Azure AD Application Proxy.</span></span> 

<span data-ttu-id="10c43-p101">Esta orientação discute como implantar as diretivas recomendadas em um ambiente recentemente provisionado. Configurando a essas políticas em um ambiente de laboratório separado permite compreender e avaliar as políticas recomendadas antes de preparar a distribuição para os ambientes de pré-produção e de produção. Seu ambiente recém-provisionado pode ser somente nuvem ou híbridas.</span><span class="sxs-lookup"><span data-stu-id="10c43-p101">This guidance discusses how to deploy the recommended policies in a newly-provisioned environment. Setting up these policies in a separate lab environment allows you to understand and evaluate the recommended policies before staging the rollout to your preproduction and production environments. Your newly provisioned environment may be cloud-only or hybrid.</span></span>  

## <a name="policy-set"></a><span data-ttu-id="10c43-108">Conjunto de política</span><span class="sxs-lookup"><span data-stu-id="10c43-108">Policy set</span></span> 

<span data-ttu-id="10c43-p102">O diagrama a seguir ilustra o conjunto recomendado de diretivas. Ela mostra quais camadas de proteção cada política se aplica e se as diretivas serão aplicadas PCs ou telefones e tablets ou ambas as categorias de dispositivos. Ele também indica onde essas diretivas são configuradas.</span><span class="sxs-lookup"><span data-stu-id="10c43-p102">The following diagram illustrates the recommended set of policies. It shows which tier of protections each policy applies to and whether the policies apply to PCs or phones and tablets, or both categories of devices. It also indicates where these policies are configured.</span></span>

![Políticas comuns para configurar o acesso de dispositivo e identidade](../images/Identity_device_access_policies_byplan.png)


<span data-ttu-id="10c43-113">O restante deste artigo descreve como configurar essas diretivas.</span><span class="sxs-lookup"><span data-stu-id="10c43-113">The rest of this article describes how to configure these policies.</span></span> 

<span data-ttu-id="10c43-p103">Usar a autenticação multifator é recomendado antes de inscrição de dispositivos em Intune para garantia de que o dispositivo está em posse do usuário desejado. Você também deve registrar os dispositivos em Intune antes da aplicação de políticas de conformidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="10c43-p103">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user. You must also enroll devices into Intune before enforcing device compliance policies.</span></span>

<span data-ttu-id="10c43-p104">Dar tempo para realizar essas tarefas, recomendamos a implementação das diretivas de linha de base na ordem listada nesta tabela. No entanto, as diretivas MFA para proteção confidencial e altamente regulamentada podem ser implementadas a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="10c43-p104">To give you time to accomplish these tasks, we recommend implementing the baseline policies in the order listed in this table. However, the MFA policies for sensitive and highly regulated protection can be implemented at any time.</span></span>


|<span data-ttu-id="10c43-118">Nível de Proteção</span><span class="sxs-lookup"><span data-stu-id="10c43-118">Protection level</span></span>|<span data-ttu-id="10c43-119">Diretivas</span><span class="sxs-lookup"><span data-stu-id="10c43-119">Policies</span></span>|<span data-ttu-id="10c43-120">Mais informações</span><span class="sxs-lookup"><span data-stu-id="10c43-120">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="10c43-121">**Linha de base**</span><span class="sxs-lookup"><span data-stu-id="10c43-121">**Baseline**</span></span>|[<span data-ttu-id="10c43-122">Exige MFA após a entrada risco *média* ou *alta*</span><span class="sxs-lookup"><span data-stu-id="10c43-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|        |[<span data-ttu-id="10c43-123">Bloquear os clientes que não oferecem suporte a autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="10c43-123">Block clients that don't support modern authentication</span></span>](#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="10c43-124">Clientes que não usam autenticação moderna poderá ignorar regras de acesso condicional, portanto, é importante bloquear essas</span><span class="sxs-lookup"><span data-stu-id="10c43-124">Clients that do not use modern authentication can bypass conditional access rules, so it's important to block these</span></span>|
|        |[<span data-ttu-id="10c43-125">Usuários de alto risco devem alterar a senha</span><span class="sxs-lookup"><span data-stu-id="10c43-125">High risk users must change password</span></span>](#high-risk-users-must-change-password)|<span data-ttu-id="10c43-126">Força os usuários a alterarem suas senhas quando entrando se forem detectadas atividades de alto risco para sua conta</span><span class="sxs-lookup"><span data-stu-id="10c43-126">Forces users to change their password when signing in if high-risk activity is detected for their account</span></span>|
|        |[<span data-ttu-id="10c43-127">Definir políticas de proteção de aplicativos</span><span class="sxs-lookup"><span data-stu-id="10c43-127">Define app protection policies</span></span>](#define-app-protection-policies)|<span data-ttu-id="10c43-128">Uma política por plataforma (iOS, Android, Windows).</span><span class="sxs-lookup"><span data-stu-id="10c43-128">One policy per platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="10c43-129">Exigem aplicativos aprovados</span><span class="sxs-lookup"><span data-stu-id="10c43-129">Require approved apps</span></span>](#require-approved-apps)|<span data-ttu-id="10c43-130">Impõe a proteção de aplicativos móveis para telefones e tablets</span><span class="sxs-lookup"><span data-stu-id="10c43-130">Enforces mobile app protection for phones and tablets</span></span>|
|        |[<span data-ttu-id="10c43-131">Definir políticas de conformidade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="10c43-131">Define device compliance policies</span></span>](#define-device-compliance-policies)|<span data-ttu-id="10c43-132">Uma política em cada plataforma</span><span class="sxs-lookup"><span data-stu-id="10c43-132">One policy for each platform</span></span>|
|        |[<span data-ttu-id="10c43-133">Exigir compatível com PCs</span><span class="sxs-lookup"><span data-stu-id="10c43-133">Require compliant PCs</span></span>](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="10c43-134">Impõe Intune gerenciamento de PCs</span><span class="sxs-lookup"><span data-stu-id="10c43-134">Enforces Intune management of PCs</span></span>|
|<span data-ttu-id="10c43-135">**Confidencial**</span><span class="sxs-lookup"><span data-stu-id="10c43-135">**Sensitive**</span></span>|[<span data-ttu-id="10c43-136">Exige MFA após a entrada risco *baixa*, *média* ou *alta*</span><span class="sxs-lookup"><span data-stu-id="10c43-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|         |[<span data-ttu-id="10c43-137">Exigir compatível com PCs *e* dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="10c43-137">Require compliant PCs *and* mobile devices</span></span>](#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="10c43-138">Impõe Intune gerenciamento para PCs e telefone/tablets</span><span class="sxs-lookup"><span data-stu-id="10c43-138">Enforces Intune management for PCs and phone/tablets</span></span>|
|<span data-ttu-id="10c43-139">**Altamente controlado**</span><span class="sxs-lookup"><span data-stu-id="10c43-139">**Highly regulated**</span></span>|[<span data-ttu-id="10c43-140">*Sempre* solicitar MFA</span><span class="sxs-lookup"><span data-stu-id="10c43-140">*Always* require MFA</span></span>](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a><span data-ttu-id="10c43-141">Atribuir políticas aos usuários</span><span class="sxs-lookup"><span data-stu-id="10c43-141">Assigning policies to users</span></span>
<span data-ttu-id="10c43-p105">Antes de configurar políticas, identifique os grupos do Azure AD que você está usando para cada camada de proteção. Normalmente, a proteção de linha de base aplica-se a todas as pessoas na organização. Um usuário que está incluído por base e proteção confidencial terá todas as políticas de linha de base aplicadas plus as políticas confidenciais. Proteção é cumulativa e a política mais restritiva é aplicada.</span><span class="sxs-lookup"><span data-stu-id="10c43-p105">Before configuring policies, identify the Azure AD groups you are using for each tier of protection. Typically, baseline protection applies to everybody in the organization. A user who is included for both baseline and sensitive protection will have all the baseline policies applied plus the sensitive policies. Protection is cumulative and the most restrictive policy is enforced.</span></span> 

<span data-ttu-id="10c43-p106">Uma prática recomendada é criar um grupo do Azure AD para exclusão de acesso condicional. Adicione a esse grupo para todas as regras de acesso condicional em "Excluir". Isso proporciona um método para fornecer acesso a um usuário enquanto você solucionar problemas de acesso. Isso é recomendado apenas uma solução temporária. Monitorar a este grupo para que as alterações e certifique-se de que o grupo de exclusão está sendo usado apenas como pretendido.</span><span class="sxs-lookup"><span data-stu-id="10c43-p106">A recommended practice is to create an Azure AD group for conditional access exclusion. Add this group to all of your conditional access rules under "Exclude". This gives you a method to provide access to a user while you troubleshoot access issues. This is recommended as a temporary solution only. Monitor this group for changes and be sure the exclusion group is being used only as intended.</span></span> 

<span data-ttu-id="10c43-151">O diagrama a seguir fornece um exemplo de atribuição de usuário e exclusões.</span><span class="sxs-lookup"><span data-stu-id="10c43-151">The following diagram provides an example of user assignment and exclusions.</span></span>

![Atribuição de usuário de exemplo e exclusões para regras MFA](../images/identity-access-policies-assignment.png)

<span data-ttu-id="10c43-p107">Na ilustração "superior secreta equipe do projeto X" é atribuído uma política de acesso condicional que requer MFA *sempre*. Ser criterioso ao aplicar níveis mais altos de proteção aos usuários. Membros da equipe projeto deverão fornecer duas formas de autenticação toda vez que efetuam logon, mesmo se eles não estão exibindo o conteúdo altamente regulamentado.</span><span class="sxs-lookup"><span data-stu-id="10c43-p107">In the illustration the "Top secret project X team" is assigned a conditional access policy that requires MFA *always*. Be judicious when applying higher levels of protection to users. Members of this project team will be required to provide two forms of authentication every time they log on, even if they are not viewing highly-regulated content.</span></span>  

<span data-ttu-id="10c43-p108">Todos os grupos do Azure AD criados como parte dessas recomendações deve ser criado como grupos do Office 365. Isso é especificamente importante para a implantação de proteção de informações do Windows Azure (AIP) quando a proteção de documentos no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="10c43-p108">All Azure AD groups created as part of these recommendations must be created as Office 365 groups. This is specifically important for the deployment of Azure Information Protection (AIP) when securing documents in SharePoint Online.</span></span>

![Captura de tela de criação de grupos do Office 365](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a><span data-ttu-id="10c43-159">Exigir MFA com base na entrada risco</span><span class="sxs-lookup"><span data-stu-id="10c43-159">Require MFA based on sign-in risk</span></span>
<span data-ttu-id="10c43-p109">Antes de solicitar a MFA, use uma política de registro de MFA de proteção de identidade para registrar os usuários para MFA. Depois que os usuários estão registrados, você pode impor MFA para entrar. O [trabalho de pré-requisito](identity-access-prerequisites.md) inclui registrando todos os usuários com MFA.</span><span class="sxs-lookup"><span data-stu-id="10c43-p109">Before requiring MFA, first use an Identity Protection MFA registration policy to register users for MFA. After users are registered you can enforce MFA for sign-in. The [prerequisite work](identity-access-prerequisites.md) includes registering all users with MFA.</span></span>

<span data-ttu-id="10c43-163">Para criar uma nova política de acesso condicional:</span><span class="sxs-lookup"><span data-stu-id="10c43-163">To create a new conditional access policy:</span></span> 

1. <span data-ttu-id="10c43-p110">Vá para o [portal do Windows Azure](https://portal.azure.com)e entrar com suas credenciais. Depois que você tiver entrado com êxito, você verá o painel de controle Azure.</span><span class="sxs-lookup"><span data-stu-id="10c43-p110">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="10c43-166">Escolha **Azure Active Directory** no menu à esquerda.</span><span class="sxs-lookup"><span data-stu-id="10c43-166">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="10c43-167">Na seção **Segurança**, escolha **Acesso condicional**.</span><span class="sxs-lookup"><span data-stu-id="10c43-167">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="10c43-168">Escolha **Nova política**.</span><span class="sxs-lookup"><span data-stu-id="10c43-168">Choose **New policy**.</span></span>

![Política de AC de linha de base](./media/secure-email/CA-EXO-policy-1.png)

 <span data-ttu-id="10c43-170">As tabelas a seguir descreve as configurações de política de acesso condicional implementar para esta diretiva.</span><span class="sxs-lookup"><span data-stu-id="10c43-170">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="10c43-171">**Atribuições**</span><span class="sxs-lookup"><span data-stu-id="10c43-171">**Assignments**</span></span>

|<span data-ttu-id="10c43-172">Tipo</span><span class="sxs-lookup"><span data-stu-id="10c43-172">Type</span></span>|<span data-ttu-id="10c43-173">Propriedades</span><span class="sxs-lookup"><span data-stu-id="10c43-173">Properties</span></span>|<span data-ttu-id="10c43-174">Valores</span><span class="sxs-lookup"><span data-stu-id="10c43-174">Values</span></span>|<span data-ttu-id="10c43-175">Notas</span><span class="sxs-lookup"><span data-stu-id="10c43-175">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="10c43-176">Usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="10c43-176">Users and groups</span></span>|<span data-ttu-id="10c43-177">Incluir</span><span class="sxs-lookup"><span data-stu-id="10c43-177">Include</span></span>|<span data-ttu-id="10c43-178">Selecionar usuários e grupos – selecione grupos de segurança específicos que contém os usuários de destino</span><span class="sxs-lookup"><span data-stu-id="10c43-178">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="10c43-179">Inicie com o grupo de segurança, incluindo usuários piloto</span><span class="sxs-lookup"><span data-stu-id="10c43-179">Start with security group including pilot users</span></span>|
||<span data-ttu-id="10c43-180">Excluir</span><span class="sxs-lookup"><span data-stu-id="10c43-180">Exclude</span></span>|<span data-ttu-id="10c43-181">Grupo de segurança de exceção, contas de serviço (identidades de aplicativo)</span><span class="sxs-lookup"><span data-stu-id="10c43-181">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="10c43-182">Associação modificada em uma base temporário conforme necessário</span><span class="sxs-lookup"><span data-stu-id="10c43-182">Membership modified on an as-needed temporary basis</span></span>|
|<span data-ttu-id="10c43-183">Aplicativos em nuvem</span><span class="sxs-lookup"><span data-stu-id="10c43-183">Cloud apps</span></span>|<span data-ttu-id="10c43-184">Incluir</span><span class="sxs-lookup"><span data-stu-id="10c43-184">Include</span></span>|<span data-ttu-id="10c43-p111">Selecione os aplicativos que você deseja que esta regra se aplique. Por exemplo, selecione Exchange Online do Office 365</span><span class="sxs-lookup"><span data-stu-id="10c43-p111">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="10c43-187">Condições</span><span class="sxs-lookup"><span data-stu-id="10c43-187">Conditions</span></span>|<span data-ttu-id="10c43-188">Configurado</span><span class="sxs-lookup"><span data-stu-id="10c43-188">Configured</span></span>|<span data-ttu-id="10c43-189">Sim</span><span class="sxs-lookup"><span data-stu-id="10c43-189">Yes</span></span>|<span data-ttu-id="10c43-190">Configure específicos para suas necessidades e ambiente</span><span class="sxs-lookup"><span data-stu-id="10c43-190">Configure specific to your environment and needs</span></span>|
|<span data-ttu-id="10c43-191">Risco de entrada</span><span class="sxs-lookup"><span data-stu-id="10c43-191">Sign-in risk</span></span>|<span data-ttu-id="10c43-192">Nível de risco</span><span class="sxs-lookup"><span data-stu-id="10c43-192">Risk level</span></span>||<span data-ttu-id="10c43-193">Consulte as orientações na tabela a seguir</span><span class="sxs-lookup"><span data-stu-id="10c43-193">See the guidance in the following table</span></span>|

<span data-ttu-id="10c43-194">**Risco de entrada**</span><span class="sxs-lookup"><span data-stu-id="10c43-194">**Sign-in risk**</span></span>

<span data-ttu-id="10c43-195">Aplica as configurações com base no nível de proteção que você está direcionando.</span><span class="sxs-lookup"><span data-stu-id="10c43-195">Apply the settings based on the protection level you are targeting.</span></span>

|<span data-ttu-id="10c43-196">Propriedade</span><span class="sxs-lookup"><span data-stu-id="10c43-196">Property</span></span>|<span data-ttu-id="10c43-197">Nível de proteção</span><span class="sxs-lookup"><span data-stu-id="10c43-197">Level of protection</span></span>|<span data-ttu-id="10c43-198">Valores</span><span class="sxs-lookup"><span data-stu-id="10c43-198">Values</span></span>|<span data-ttu-id="10c43-199">Notas</span><span class="sxs-lookup"><span data-stu-id="10c43-199">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="10c43-200">Nível de risco</span><span class="sxs-lookup"><span data-stu-id="10c43-200">Risk level</span></span>|<span data-ttu-id="10c43-201">Linha de base</span><span class="sxs-lookup"><span data-stu-id="10c43-201">Baseline</span></span>|<span data-ttu-id="10c43-202">Alto, médio</span><span class="sxs-lookup"><span data-stu-id="10c43-202">High, medium</span></span>|<span data-ttu-id="10c43-203">Marque ambos</span><span class="sxs-lookup"><span data-stu-id="10c43-203">Check both</span></span>|
| |<span data-ttu-id="10c43-204">Confidencial</span><span class="sxs-lookup"><span data-stu-id="10c43-204">Sensitive</span></span>|<span data-ttu-id="10c43-205">Alta, média, baixa</span><span class="sxs-lookup"><span data-stu-id="10c43-205">High, medium, low</span></span>|<span data-ttu-id="10c43-206">Marque todos os três</span><span class="sxs-lookup"><span data-stu-id="10c43-206">Check all three</span></span>|
| |<span data-ttu-id="10c43-207">Altamente controlado</span><span class="sxs-lookup"><span data-stu-id="10c43-207">Highly regulated</span></span>| |<span data-ttu-id="10c43-208">Deixe todas as opções desmarcada para impor sempre MFA</span><span class="sxs-lookup"><span data-stu-id="10c43-208">Leave all options unchecked to always enforce MFA</span></span>|

<span data-ttu-id="10c43-209">**Controles de acesso**</span><span class="sxs-lookup"><span data-stu-id="10c43-209">**Access controls**</span></span>

|<span data-ttu-id="10c43-210">Tipo</span><span class="sxs-lookup"><span data-stu-id="10c43-210">Type</span></span>|<span data-ttu-id="10c43-211">Propriedades</span><span class="sxs-lookup"><span data-stu-id="10c43-211">Properties</span></span>|<span data-ttu-id="10c43-212">Valores</span><span class="sxs-lookup"><span data-stu-id="10c43-212">Values</span></span>|<span data-ttu-id="10c43-213">Notas</span><span class="sxs-lookup"><span data-stu-id="10c43-213">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="10c43-214">Conceder</span><span class="sxs-lookup"><span data-stu-id="10c43-214">Grant</span></span>|<span data-ttu-id="10c43-215">Conceder acesso</span><span class="sxs-lookup"><span data-stu-id="10c43-215">Grant access</span></span>|<span data-ttu-id="10c43-216">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="10c43-216">True</span></span>|<span data-ttu-id="10c43-217">Selecionada</span><span class="sxs-lookup"><span data-stu-id="10c43-217">Selected</span></span>|
||<span data-ttu-id="10c43-218">Exigir MFA</span><span class="sxs-lookup"><span data-stu-id="10c43-218">Require MFA</span></span>|<span data-ttu-id="10c43-219">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="10c43-219">True</span></span>|<span data-ttu-id="10c43-220">Verificar</span><span class="sxs-lookup"><span data-stu-id="10c43-220">Check</span></span>|
||<span data-ttu-id="10c43-221">Exigir o dispositivo para ser marcado como compatível</span><span class="sxs-lookup"><span data-stu-id="10c43-221">Require device to be marked as compliant</span></span>|<span data-ttu-id="10c43-222">Falso</span><span class="sxs-lookup"><span data-stu-id="10c43-222">False</span></span>||
||<span data-ttu-id="10c43-223">Exigir híbrida Azure dispositivo associado ao AD</span><span class="sxs-lookup"><span data-stu-id="10c43-223">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="10c43-224">Falso</span><span class="sxs-lookup"><span data-stu-id="10c43-224">False</span></span>||
||<span data-ttu-id="10c43-225">Requer aplicativo cliente aprovado</span><span class="sxs-lookup"><span data-stu-id="10c43-225">Require approved client app</span></span>|<span data-ttu-id="10c43-226">Falso</span><span class="sxs-lookup"><span data-stu-id="10c43-226">False</span></span>||
||<span data-ttu-id="10c43-227">Exigir todos os controles selecionados</span><span class="sxs-lookup"><span data-stu-id="10c43-227">Require all the selected controls</span></span>|<span data-ttu-id="10c43-228">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="10c43-228">True</span></span>|<span data-ttu-id="10c43-229">Selecionada</span><span class="sxs-lookup"><span data-stu-id="10c43-229">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="10c43-p112">Certifique-se de que habilite essa diretiva, escolhendo **em**. Também considere usando a ferramenta [se](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para testar a diretiva.</span><span class="sxs-lookup"><span data-stu-id="10c43-p112">Be sure to enable this policy, by choosing **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="block-clients-that-dont-support-modern-authentication"></a><span data-ttu-id="10c43-232">Bloquear os clientes que não oferecem suporte a autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="10c43-232">Block clients that don't support modern authentication</span></span>
1. <span data-ttu-id="10c43-p113">Vá para o [portal do Windows Azure](https://portal.azure.com)e entrar com suas credenciais. Depois que você tiver entrado com êxito, você verá o painel de controle Azure.</span><span class="sxs-lookup"><span data-stu-id="10c43-p113">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="10c43-235">Escolha **Azure Active Directory** no menu à esquerda.</span><span class="sxs-lookup"><span data-stu-id="10c43-235">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="10c43-236">Na seção **Segurança**, escolha **Acesso condicional**.</span><span class="sxs-lookup"><span data-stu-id="10c43-236">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="10c43-237">Escolha **Nova política**.</span><span class="sxs-lookup"><span data-stu-id="10c43-237">Choose **New policy**.</span></span>

<span data-ttu-id="10c43-238">As tabelas a seguir descreve as configurações de política de acesso condicional implementar para esta diretiva.</span><span class="sxs-lookup"><span data-stu-id="10c43-238">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="10c43-239">**Atribuições**</span><span class="sxs-lookup"><span data-stu-id="10c43-239">**Assignments**</span></span>

|<span data-ttu-id="10c43-240">Tipo</span><span class="sxs-lookup"><span data-stu-id="10c43-240">Type</span></span>|<span data-ttu-id="10c43-241">Propriedades</span><span class="sxs-lookup"><span data-stu-id="10c43-241">Properties</span></span>|<span data-ttu-id="10c43-242">Valores</span><span class="sxs-lookup"><span data-stu-id="10c43-242">Values</span></span>|<span data-ttu-id="10c43-243">Notas</span><span class="sxs-lookup"><span data-stu-id="10c43-243">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="10c43-244">Usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="10c43-244">Users and groups</span></span>|<span data-ttu-id="10c43-245">Incluir</span><span class="sxs-lookup"><span data-stu-id="10c43-245">Include</span></span>|<span data-ttu-id="10c43-246">Selecionar usuários e grupos – selecione grupos de segurança específicos que contém os usuários de destino</span><span class="sxs-lookup"><span data-stu-id="10c43-246">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="10c43-247">Inicie com o grupo de segurança, incluindo usuários piloto</span><span class="sxs-lookup"><span data-stu-id="10c43-247">Start with security group including pilot users</span></span>|
||<span data-ttu-id="10c43-248">Excluir</span><span class="sxs-lookup"><span data-stu-id="10c43-248">Exclude</span></span>|<span data-ttu-id="10c43-249">Grupo de segurança de exceção, contas de serviço (identidades de aplicativo)</span><span class="sxs-lookup"><span data-stu-id="10c43-249">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="10c43-250">Associação modificada de forma temporária, conforme o necessário</span><span class="sxs-lookup"><span data-stu-id="10c43-250">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="10c43-251">Aplicativos em nuvem</span><span class="sxs-lookup"><span data-stu-id="10c43-251">Cloud apps</span></span>|<span data-ttu-id="10c43-252">Incluir</span><span class="sxs-lookup"><span data-stu-id="10c43-252">Include</span></span>|<span data-ttu-id="10c43-p114">Selecione os aplicativos que você deseja que esta regra se aplique. Por exemplo, selecione Exchange Online do Office 365</span><span class="sxs-lookup"><span data-stu-id="10c43-p114">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="10c43-255">Condições</span><span class="sxs-lookup"><span data-stu-id="10c43-255">Conditions</span></span>|<span data-ttu-id="10c43-256">Configurado</span><span class="sxs-lookup"><span data-stu-id="10c43-256">Configured</span></span>|<span data-ttu-id="10c43-257">Sim</span><span class="sxs-lookup"><span data-stu-id="10c43-257">Yes</span></span>|<span data-ttu-id="10c43-258">Configurar aplicativos do cliente</span><span class="sxs-lookup"><span data-stu-id="10c43-258">Configure Client apps</span></span>|
|<span data-ttu-id="10c43-259">Aplicativos do cliente</span><span class="sxs-lookup"><span data-stu-id="10c43-259">Client apps</span></span>|<span data-ttu-id="10c43-260">Configurado</span><span class="sxs-lookup"><span data-stu-id="10c43-260">Configured</span></span>|<span data-ttu-id="10c43-261">Sim</span><span class="sxs-lookup"><span data-stu-id="10c43-261">Yes</span></span>|<span data-ttu-id="10c43-262">Aplicativos móveis e clientes de área de trabalho, outros clientes (selecione ambos)</span><span class="sxs-lookup"><span data-stu-id="10c43-262">Mobile apps and desktop clients, Other clients (select both)</span></span>|

<span data-ttu-id="10c43-263">**Controles de acesso**</span><span class="sxs-lookup"><span data-stu-id="10c43-263">**Access controls**</span></span>

|<span data-ttu-id="10c43-264">Tipo</span><span class="sxs-lookup"><span data-stu-id="10c43-264">Type</span></span>|<span data-ttu-id="10c43-265">Propriedades</span><span class="sxs-lookup"><span data-stu-id="10c43-265">Properties</span></span>|<span data-ttu-id="10c43-266">Valores</span><span class="sxs-lookup"><span data-stu-id="10c43-266">Values</span></span>|<span data-ttu-id="10c43-267">Notas</span><span class="sxs-lookup"><span data-stu-id="10c43-267">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="10c43-268">Conceder</span><span class="sxs-lookup"><span data-stu-id="10c43-268">Grant</span></span>|<span data-ttu-id="10c43-269">Bloquear acesso</span><span class="sxs-lookup"><span data-stu-id="10c43-269">Block access</span></span>|<span data-ttu-id="10c43-270">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="10c43-270">True</span></span>|<span data-ttu-id="10c43-271">Selecionada</span><span class="sxs-lookup"><span data-stu-id="10c43-271">Selected</span></span>|
||<span data-ttu-id="10c43-272">Exigir MFA</span><span class="sxs-lookup"><span data-stu-id="10c43-272">Require MFA</span></span>|<span data-ttu-id="10c43-273">Falso</span><span class="sxs-lookup"><span data-stu-id="10c43-273">False</span></span>||
||<span data-ttu-id="10c43-274">Exigir o dispositivo para ser marcado como compatível</span><span class="sxs-lookup"><span data-stu-id="10c43-274">Require device to be marked as compliant</span></span>|<span data-ttu-id="10c43-275">Falso</span><span class="sxs-lookup"><span data-stu-id="10c43-275">False</span></span>||
||<span data-ttu-id="10c43-276">Exigir híbrida Azure dispositivo associado ao AD</span><span class="sxs-lookup"><span data-stu-id="10c43-276">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="10c43-277">Falso</span><span class="sxs-lookup"><span data-stu-id="10c43-277">False</span></span>||
||<span data-ttu-id="10c43-278">Requer aplicativo cliente aprovado</span><span class="sxs-lookup"><span data-stu-id="10c43-278">Require approved client app</span></span>|<span data-ttu-id="10c43-279">Falso</span><span class="sxs-lookup"><span data-stu-id="10c43-279">False</span></span>||
||<span data-ttu-id="10c43-280">Exigir todos os controles selecionados</span><span class="sxs-lookup"><span data-stu-id="10c43-280">Require all the selected controls</span></span>|<span data-ttu-id="10c43-281">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="10c43-281">True</span></span>|<span data-ttu-id="10c43-282">Selecionada</span><span class="sxs-lookup"><span data-stu-id="10c43-282">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="10c43-p115">Certifique-se de que habilite essa diretiva, escolhendo **em**. Também considere usando a ferramenta [se](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para testar a diretiva.</span><span class="sxs-lookup"><span data-stu-id="10c43-p115">Be sure to enable this policy, by choosing **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="high-risk-users-must-change-password"></a><span data-ttu-id="10c43-285">Usuários de alto risco devem alterar a senha</span><span class="sxs-lookup"><span data-stu-id="10c43-285">High risk users must change password</span></span>
<span data-ttu-id="10c43-286">Para garantir que as contas de todos os usuários alto risco comprometidas são forçados a realizar uma alteração de senha ao entrar no serviço, você deve aplicar a política a seguir.</span><span class="sxs-lookup"><span data-stu-id="10c43-286">To ensure that all high-risk users' compromised accounts are forced to perform a password change when signing-in, you must apply the following policy.</span></span>

<span data-ttu-id="10c43-287">Faça logon no [portal do Microsoft Azure (http://portal.azure.com) ](http://portal.azure.com/) com suas credenciais de administrador e navegue até **proteção de identidade do Windows Azure AD > política de risco de usuário**.</span><span class="sxs-lookup"><span data-stu-id="10c43-287">Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.</span></span>

<span data-ttu-id="10c43-288">**Atribuições**</span><span class="sxs-lookup"><span data-stu-id="10c43-288">**Assignments**</span></span>

|<span data-ttu-id="10c43-289">Tipo</span><span class="sxs-lookup"><span data-stu-id="10c43-289">Type</span></span>|<span data-ttu-id="10c43-290">Propriedades</span><span class="sxs-lookup"><span data-stu-id="10c43-290">Properties</span></span>|<span data-ttu-id="10c43-291">Valores</span><span class="sxs-lookup"><span data-stu-id="10c43-291">Values</span></span>|<span data-ttu-id="10c43-292">Notas</span><span class="sxs-lookup"><span data-stu-id="10c43-292">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="10c43-293">Usuários</span><span class="sxs-lookup"><span data-stu-id="10c43-293">Users</span></span>|<span data-ttu-id="10c43-294">Incluir</span><span class="sxs-lookup"><span data-stu-id="10c43-294">Include</span></span>|<span data-ttu-id="10c43-295">todos os usuários</span><span class="sxs-lookup"><span data-stu-id="10c43-295">All users</span></span>|<span data-ttu-id="10c43-296">Selecionada</span><span class="sxs-lookup"><span data-stu-id="10c43-296">Selected</span></span>|
||<span data-ttu-id="10c43-297">Excluir</span><span class="sxs-lookup"><span data-stu-id="10c43-297">Exclude</span></span>|<span data-ttu-id="10c43-298">Nenhum</span><span class="sxs-lookup"><span data-stu-id="10c43-298">None</span></span>||
|<span data-ttu-id="10c43-299">Condições</span><span class="sxs-lookup"><span data-stu-id="10c43-299">Conditions</span></span>|<span data-ttu-id="10c43-300">Risco do usuário</span><span class="sxs-lookup"><span data-stu-id="10c43-300">User risk</span></span>|<span data-ttu-id="10c43-301">Alta</span><span class="sxs-lookup"><span data-stu-id="10c43-301">High</span></span>|<span data-ttu-id="10c43-302">Selecionada</span><span class="sxs-lookup"><span data-stu-id="10c43-302">Selected</span></span>|

<span data-ttu-id="10c43-303">**Controles**</span><span class="sxs-lookup"><span data-stu-id="10c43-303">**Controls**</span></span>

| <span data-ttu-id="10c43-304">Tipo</span><span class="sxs-lookup"><span data-stu-id="10c43-304">Type</span></span> | <span data-ttu-id="10c43-305">Propriedades</span><span class="sxs-lookup"><span data-stu-id="10c43-305">Properties</span></span> | <span data-ttu-id="10c43-306">Valores</span><span class="sxs-lookup"><span data-stu-id="10c43-306">Values</span></span>                  | <span data-ttu-id="10c43-307">Observações</span><span class="sxs-lookup"><span data-stu-id="10c43-307">Notes</span></span> |
|:-----|:-----------|:------------------------|:------|
|      | <span data-ttu-id="10c43-308">Acessar</span><span class="sxs-lookup"><span data-stu-id="10c43-308">Access</span></span>     | <span data-ttu-id="10c43-309">Permitir acesso</span><span class="sxs-lookup"><span data-stu-id="10c43-309">Allow access</span></span>            | <span data-ttu-id="10c43-310">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="10c43-310">True</span></span>  |
|      | <span data-ttu-id="10c43-311">Acessar</span><span class="sxs-lookup"><span data-stu-id="10c43-311">Access</span></span>     | <span data-ttu-id="10c43-312">Requer a alteração de senha</span><span class="sxs-lookup"><span data-stu-id="10c43-312">Require password change</span></span> | <span data-ttu-id="10c43-313">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="10c43-313">True</span></span>  |

<span data-ttu-id="10c43-314">**Revisão:** não aplicável</span><span class="sxs-lookup"><span data-stu-id="10c43-314">**Review:** not applicable</span></span>

> [!NOTE]
> <span data-ttu-id="10c43-p116">Certifique-se de que habilite essa diretiva, escolhendo **em**. Também considere usando a ferramenta [se](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para testar a diretiva</span><span class="sxs-lookup"><span data-stu-id="10c43-p116">Be sure to enable this policy, by choosing **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>

## <a name="define-app-protection-policies"></a><span data-ttu-id="10c43-317">Definir políticas de proteção de aplicativos</span><span class="sxs-lookup"><span data-stu-id="10c43-317">Define app protection policies</span></span>
<span data-ttu-id="10c43-p117">Políticas de proteção de aplicativos que definem quais aplicativos são permitidos e as ações que eles podem executar com dados de sua organização. Crie Intune app políticas de proteção de dentro do portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="10c43-p117">App protection policies define which apps are allowed and the actions they can take with your organization's data. Create Intune app protection policies from within the Azure portal.</span></span> 

<span data-ttu-id="10c43-320">Crie uma diretiva em cada plataforma:</span><span class="sxs-lookup"><span data-stu-id="10c43-320">Create a policy for each platform:</span></span>
- <span data-ttu-id="10c43-321">iOS</span><span class="sxs-lookup"><span data-stu-id="10c43-321">iOS</span></span>
- <span data-ttu-id="10c43-322">Android</span><span class="sxs-lookup"><span data-stu-id="10c43-322">Android</span></span>
- <span data-ttu-id="10c43-323">Windows 10</span><span class="sxs-lookup"><span data-stu-id="10c43-323">Windows 10</span></span>

<span data-ttu-id="10c43-p118">Para criar uma nova política de proteção de aplicativo, faça logon no portal do Microsoft Azure com suas credenciais de administrador e navegue até **aplicativos móveis > políticas de proteção de aplicativos**. Escolha **Adicionar uma política**.</span><span class="sxs-lookup"><span data-stu-id="10c43-p118">To create a new app protection policy, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Mobile apps > App protection policies**. Choose **Add a policy**.</span></span>

<span data-ttu-id="10c43-p119">Há pequenas diferenças na proteção app com opções de política entre iOS e Android. O abaixo política é especificamente para Android. Use esta opção como um guia para as outras políticas.</span><span class="sxs-lookup"><span data-stu-id="10c43-p119">There are slight differences in the app protection policy options between iOS and Android. The below policy is specifically for Android. Use this as a guide for your other policies.</span></span>

<span data-ttu-id="10c43-329">Lista de aplicativos recomendada inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="10c43-329">The recommended list of apps includes the following:</span></span>
- <span data-ttu-id="10c43-330">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="10c43-330">PowerPoint</span></span>
- <span data-ttu-id="10c43-331">Excel</span><span class="sxs-lookup"><span data-stu-id="10c43-331">Excel</span></span>
- <span data-ttu-id="10c43-332">Word</span><span class="sxs-lookup"><span data-stu-id="10c43-332">Word</span></span>
- <span data-ttu-id="10c43-333">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="10c43-333">Microsoft Teams</span></span>
- <span data-ttu-id="10c43-334">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="10c43-334">Microsoft SharePoint</span></span>
- <span data-ttu-id="10c43-335">Visualizador do Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="10c43-335">Microsoft Visio Viewer</span></span>
- <span data-ttu-id="10c43-336">OneDrive</span><span class="sxs-lookup"><span data-stu-id="10c43-336">OneDrive</span></span>
- <span data-ttu-id="10c43-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="10c43-337">OneNote</span></span>
- <span data-ttu-id="10c43-338">Outlook</span><span class="sxs-lookup"><span data-stu-id="10c43-338">Outlook</span></span>

<span data-ttu-id="10c43-339">As tabelas a seguir descrevem as configurações recomendadas:</span><span class="sxs-lookup"><span data-stu-id="10c43-339">The following tables describe the recommended settings:</span></span>

|<span data-ttu-id="10c43-340">Tipo</span><span class="sxs-lookup"><span data-stu-id="10c43-340">Type</span></span>|<span data-ttu-id="10c43-341">Propriedades</span><span class="sxs-lookup"><span data-stu-id="10c43-341">Properties</span></span>|<span data-ttu-id="10c43-342">Valores</span><span class="sxs-lookup"><span data-stu-id="10c43-342">Values</span></span>|<span data-ttu-id="10c43-343">Notas</span><span class="sxs-lookup"><span data-stu-id="10c43-343">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="10c43-344">Realocação de dados</span><span class="sxs-lookup"><span data-stu-id="10c43-344">Data relocation</span></span>|<span data-ttu-id="10c43-345">Impedir backup do Android</span><span class="sxs-lookup"><span data-stu-id="10c43-345">Prevent Android backup</span></span>|<span data-ttu-id="10c43-346">Sim</span><span class="sxs-lookup"><span data-stu-id="10c43-346">Yes</span></span>|<span data-ttu-id="10c43-347">No iOS isso especificamente indicará o iTunes e o iCloud</span><span class="sxs-lookup"><span data-stu-id="10c43-347">On iOS this will specifically call out iTunes and iCloud</span></span>|
||<span data-ttu-id="10c43-348">Permitir que o aplicativo transfira dados para outros aplicativos</span><span class="sxs-lookup"><span data-stu-id="10c43-348">Allow app to transfer data to other apps</span></span>|<span data-ttu-id="10c43-349">Aplicativos gerenciados por política</span><span class="sxs-lookup"><span data-stu-id="10c43-349">Policy managed apps</span></span>||
||<span data-ttu-id="10c43-350">Permitir que o aplicativo receba dados de outros aplicativos</span><span class="sxs-lookup"><span data-stu-id="10c43-350">Allow app to receive data from other apps</span></span>|<span data-ttu-id="10c43-351">Aplicativos gerenciados por política</span><span class="sxs-lookup"><span data-stu-id="10c43-351">Policy managed apps</span></span>||
||<span data-ttu-id="10c43-352">Impedir "Salvar como"</span><span class="sxs-lookup"><span data-stu-id="10c43-352">Prevent "Save As"</span></span>|<span data-ttu-id="10c43-353">Sim</span><span class="sxs-lookup"><span data-stu-id="10c43-353">Yes</span></span>||
||<span data-ttu-id="10c43-354">Selecione em quais serviços de armazenamento os dados corporativos podem ser salvos</span><span class="sxs-lookup"><span data-stu-id="10c43-354">Select which storage services corporate data can be saved to</span></span>|<span data-ttu-id="10c43-355">OneDrive for Business, do SharePoint</span><span class="sxs-lookup"><span data-stu-id="10c43-355">OneDrive for Business, SharePoint</span></span>||
||<span data-ttu-id="10c43-356">Restringir recortar, copiar e colar com outros aplicativos</span><span class="sxs-lookup"><span data-stu-id="10c43-356">Restrict cut, copy, and paste with other apps</span></span>|<span data-ttu-id="10c43-357">Aplicativos com Colar no gerenciada de política</span><span class="sxs-lookup"><span data-stu-id="10c43-357">Policy managed apps with paste in</span></span>||
||<span data-ttu-id="10c43-358">Restringir a exibição de conteúdo da Web no Managed Browser</span><span class="sxs-lookup"><span data-stu-id="10c43-358">Restrict web content to display in the managed browser</span></span>|<span data-ttu-id="10c43-359">Não</span><span class="sxs-lookup"><span data-stu-id="10c43-359">No</span></span>||
||<span data-ttu-id="10c43-360">Criptografar dados do aplicativo</span><span class="sxs-lookup"><span data-stu-id="10c43-360">Encrypt app data</span></span>|<span data-ttu-id="10c43-361">Sim</span><span class="sxs-lookup"><span data-stu-id="10c43-361">Yes</span></span>|<span data-ttu-id="10c43-362">No iOS, selecione a opção: Quando o dispositivo está bloqueado</span><span class="sxs-lookup"><span data-stu-id="10c43-362">On iOS select option: When device is locked</span></span>|
||<span data-ttu-id="10c43-363">Desabilitar a criptografia do aplicativo quando o dispositivo está habilitado</span><span class="sxs-lookup"><span data-stu-id="10c43-363">Disable app encryption when device is enabled</span></span>|<span data-ttu-id="10c43-364">Sim</span><span class="sxs-lookup"><span data-stu-id="10c43-364">Yes</span></span>|<span data-ttu-id="10c43-365">Desative esta configuração para evitar a criptografia dupla</span><span class="sxs-lookup"><span data-stu-id="10c43-365">Disable this setting to avoid double encryption</span></span>|
||<span data-ttu-id="10c43-366">Desabilitar a sincronização de contatos</span><span class="sxs-lookup"><span data-stu-id="10c43-366">Disable contacts sync</span></span>|<span data-ttu-id="10c43-367">Não</span><span class="sxs-lookup"><span data-stu-id="10c43-367">No</span></span>||
||<span data-ttu-id="10c43-368">Desabilitar a impressão</span><span class="sxs-lookup"><span data-stu-id="10c43-368">Disable printing</span></span>|<span data-ttu-id="10c43-369">Não</span><span class="sxs-lookup"><span data-stu-id="10c43-369">No</span></span>||
|<span data-ttu-id="10c43-370">Acessar</span><span class="sxs-lookup"><span data-stu-id="10c43-370">Access</span></span>|<span data-ttu-id="10c43-371">Solicitar PIN para acesso</span><span class="sxs-lookup"><span data-stu-id="10c43-371">Require PIN for access</span></span>|<span data-ttu-id="10c43-372">Sim</span><span class="sxs-lookup"><span data-stu-id="10c43-372">Yes</span></span>||
||<span data-ttu-id="10c43-373">Selecione o tipo</span><span class="sxs-lookup"><span data-stu-id="10c43-373">Select Type</span></span>|<span data-ttu-id="10c43-374">Numérico</span><span class="sxs-lookup"><span data-stu-id="10c43-374">Numeric</span></span>||
||<span data-ttu-id="10c43-375">Permitir PIN simples</span><span class="sxs-lookup"><span data-stu-id="10c43-375">Allow simple PIN</span></span>|<span data-ttu-id="10c43-376">Não</span><span class="sxs-lookup"><span data-stu-id="10c43-376">No</span></span>||
||<span data-ttu-id="10c43-377">Tamanho do PIN</span><span class="sxs-lookup"><span data-stu-id="10c43-377">PIN length</span></span>|<span data-ttu-id="10c43-378">6</span><span class="sxs-lookup"><span data-stu-id="10c43-378">6</span></span>||
||<span data-ttu-id="10c43-379">Permitir a impressão digital em vez do PIN</span><span class="sxs-lookup"><span data-stu-id="10c43-379">Allow fingerprint instead of PIN</span></span>|<span data-ttu-id="10c43-380">Sim</span><span class="sxs-lookup"><span data-stu-id="10c43-380">Yes</span></span>||
||<span data-ttu-id="10c43-381">Desabilitar app PIN quando o PIN do dispositivo é gerenciado</span><span class="sxs-lookup"><span data-stu-id="10c43-381">Disable app PIN when device PIN is managed</span></span>|<span data-ttu-id="10c43-382">Sim</span><span class="sxs-lookup"><span data-stu-id="10c43-382">Yes</span></span>||
||<span data-ttu-id="10c43-383">Exigem credenciais corporativas para acesso</span><span class="sxs-lookup"><span data-stu-id="10c43-383">Require corporate credentials for access</span></span>|<span data-ttu-id="10c43-384">Não</span><span class="sxs-lookup"><span data-stu-id="10c43-384">No</span></span>||
||<span data-ttu-id="10c43-385">Verificar novamente o requisito de acesso após (minutos)</span><span class="sxs-lookup"><span data-stu-id="10c43-385">Recheck the access requirement after (minutes)</span></span>|<span data-ttu-id="10c43-386">30</span><span class="sxs-lookup"><span data-stu-id="10c43-386">30</span></span>||
||<span data-ttu-id="10c43-387">Bloquear captura de tela e Assistente do Android</span><span class="sxs-lookup"><span data-stu-id="10c43-387">Block screen capture and Android assistant</span></span>|<span data-ttu-id="10c43-388">Não</span><span class="sxs-lookup"><span data-stu-id="10c43-388">No</span></span>|<span data-ttu-id="10c43-389">No iOS isso não é uma opção disponível</span><span class="sxs-lookup"><span data-stu-id="10c43-389">On iOS this is not an available option</span></span>|
|<span data-ttu-id="10c43-390">Requisitos de segurança de entrada</span><span class="sxs-lookup"><span data-stu-id="10c43-390">Sign-in security requirements</span></span>|<span data-ttu-id="10c43-391">Tentativas máximas PIN</span><span class="sxs-lookup"><span data-stu-id="10c43-391">Max PIN attempts</span></span>|<span data-ttu-id="10c43-392">5</span><span class="sxs-lookup"><span data-stu-id="10c43-392">5</span></span>|<span data-ttu-id="10c43-393">Redefinir Pin</span><span class="sxs-lookup"><span data-stu-id="10c43-393">Reset Pin</span></span>|
||<span data-ttu-id="10c43-394">Período de cortesia offline</span><span class="sxs-lookup"><span data-stu-id="10c43-394">Offline grace period</span></span>|<span data-ttu-id="10c43-395">720</span><span class="sxs-lookup"><span data-stu-id="10c43-395">720</span></span>|<span data-ttu-id="10c43-396">Bloquear acesso</span><span class="sxs-lookup"><span data-stu-id="10c43-396">Block access</span></span>|
||<span data-ttu-id="10c43-397">Intervalo offline (dias) antes do apagamento dos dados do aplicativo</span><span class="sxs-lookup"><span data-stu-id="10c43-397">Offline interval (days) before app data is wiped</span></span>|<span data-ttu-id="10c43-398">90</span><span class="sxs-lookup"><span data-stu-id="10c43-398">90</span></span>|<span data-ttu-id="10c43-399">Apagar dados</span><span class="sxs-lookup"><span data-stu-id="10c43-399">Wipe data</span></span>|
||<span data-ttu-id="10c43-400">Dispositivos Jailbroken/raiz</span><span class="sxs-lookup"><span data-stu-id="10c43-400">Jailbroken/rooted devices</span></span>| |<span data-ttu-id="10c43-401">Apagar dados</span><span class="sxs-lookup"><span data-stu-id="10c43-401">Wipe data</span></span>|

<span data-ttu-id="10c43-p120">Quando concluir, lembre-se de selecionar "Criar". Repita as etapas acima e substitua a plataforma selecionada (suspenso) iOS. Isso cria duas diretivas de aplicativo, portanto depois de criar a política, em seguida, atribuir grupos à diretiva e implantá-la.</span><span class="sxs-lookup"><span data-stu-id="10c43-p120">When complete, remember to select "Create". Repeat the above steps and replace the selected platform (dropdown) with iOS. This creates two app policies, so once you create the policy, then assign groups to the policy and deploy it.</span></span>

<span data-ttu-id="10c43-405">Para editar as políticas e atribuir essas políticas a usuários, consulte [como criar e atribuir políticas de proteção de aplicativos](https://docs.microsoft.com/intune/app-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="10c43-405">To edit the policies and assign these policies to users, see [How to create and assign app protection policies](https://docs.microsoft.com/intune/app-protection-policies).</span></span> 

## <a name="require-approved-apps"></a><span data-ttu-id="10c43-406">Exigem aplicativos aprovados</span><span class="sxs-lookup"><span data-stu-id="10c43-406">Require approved apps</span></span>
<span data-ttu-id="10c43-407">Para exigir a aplicativos aprovados:</span><span class="sxs-lookup"><span data-stu-id="10c43-407">To require approved apps:</span></span>

1. <span data-ttu-id="10c43-p121">Vá para o [portal do Windows Azure](https://portal.azure.com)e entrar com suas credenciais. Depois que você tiver entrado com êxito, você verá o painel de controle Azure.</span><span class="sxs-lookup"><span data-stu-id="10c43-p121">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="10c43-410">Escolha **Azure Active Directory** no menu à esquerda.</span><span class="sxs-lookup"><span data-stu-id="10c43-410">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="10c43-411">Na seção **Segurança**, escolha **Acesso condicional**.</span><span class="sxs-lookup"><span data-stu-id="10c43-411">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="10c43-412">Escolha **Nova política**.</span><span class="sxs-lookup"><span data-stu-id="10c43-412">Choose **New policy**.</span></span>

5. <span data-ttu-id="10c43-413">Insira um nome para a política e escolha os **Usuários e grupos** aos quais deseja aplicar a política.</span><span class="sxs-lookup"><span data-stu-id="10c43-413">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="10c43-414">Escolha **Aplicativos na nuvem**.</span><span class="sxs-lookup"><span data-stu-id="10c43-414">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="10c43-p122">Escolha **Selecionar aplicativos**, selecione os aplicativos desejados na lista de **aplicativos na nuvem** . Por exemplo, selecione Exchange Online do Office 365. Escolha **Selecionar** e **feito**.</span><span class="sxs-lookup"><span data-stu-id="10c43-p122">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="10c43-418">Escolha **Conceder** na seção **Controles de acesso**.</span><span class="sxs-lookup"><span data-stu-id="10c43-418">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="10c43-p123">Escolha **conceder acesso**, selecione **exigir aprovados pelo aplicativo cliente**. Para vários controles, selecione **exigir os controles selecionados**e selecione **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="10c43-p123">Choose **Grant access**, select **Require approved client app**. For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="10c43-421">Escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="10c43-421">Choose **Create**.</span></span>

## <a name="define-device-compliance-policies"></a><span data-ttu-id="10c43-422">Definir políticas de conformidade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="10c43-422">Define device-compliance policies</span></span>

<span data-ttu-id="10c43-p124">Políticas de conformidade do dispositivo definem os requisitos que dispositivos devem aderir para ser marcado como compatível. Crie o dispositivo Intune políticas de conformidade de dentro do portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="10c43-p124">Device-compliance policies define the requirements that devices must adhere to in order to be marked as compliant. Create Intune device compliance policies from within the Azure portal.</span></span> 

<span data-ttu-id="10c43-425">Crie uma diretiva em cada plataforma:</span><span class="sxs-lookup"><span data-stu-id="10c43-425">Create a policy for each platform:</span></span>
- <span data-ttu-id="10c43-426">Android</span><span class="sxs-lookup"><span data-stu-id="10c43-426">Android</span></span>
- <span data-ttu-id="10c43-427">Android enterprise</span><span class="sxs-lookup"><span data-stu-id="10c43-427">Android enterprise</span></span>
- <span data-ttu-id="10c43-428">iOS</span><span class="sxs-lookup"><span data-stu-id="10c43-428">iOS</span></span>
- <span data-ttu-id="10c43-429">macOS</span><span class="sxs-lookup"><span data-stu-id="10c43-429">macOS</span></span>
- <span data-ttu-id="10c43-430">Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="10c43-430">Windows Phone 8.1</span></span>
- <span data-ttu-id="10c43-431">Windows 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="10c43-431">Windows 8.1 and later</span></span>
- <span data-ttu-id="10c43-432">Windows 10 e posterior</span><span class="sxs-lookup"><span data-stu-id="10c43-432">Windows 10 and later</span></span>

<span data-ttu-id="10c43-p125">Para criar políticas de conformidade de dispositivo, faça logon no portal do Microsoft Azure com suas credenciais de administrador e navegue até **Intune > conformidade do dispositivo**. Selecione **Criar política**.</span><span class="sxs-lookup"><span data-stu-id="10c43-p125">To create device compliance policies, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Intune > Device compliance**. Select **Create policy**.</span></span>

<span data-ttu-id="10c43-435">As configurações a seguir são recomendadas para Windows 10.</span><span class="sxs-lookup"><span data-stu-id="10c43-435">The following settings are recommended for Windows 10.</span></span>

<span data-ttu-id="10c43-436">**Integridade de dispositivo: as regras de avaliação do serviço de certificação de integridade do Windows**</span><span class="sxs-lookup"><span data-stu-id="10c43-436">**Device health: Windows Health Attestation Service evaluation rules**</span></span>

|<span data-ttu-id="10c43-437">Propriedades</span><span class="sxs-lookup"><span data-stu-id="10c43-437">Properties</span></span>|<span data-ttu-id="10c43-438">Valores</span><span class="sxs-lookup"><span data-stu-id="10c43-438">Values</span></span>|<span data-ttu-id="10c43-439">Notas</span><span class="sxs-lookup"><span data-stu-id="10c43-439">Notes</span></span>|
|:---------|:-----|:----|
|<span data-ttu-id="10c43-440">Requerer BitLocker</span><span class="sxs-lookup"><span data-stu-id="10c43-440">Require BitLocker</span></span>|<span data-ttu-id="10c43-441">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="10c43-441">Require</span></span>||
|<span data-ttu-id="10c43-442">Exigir inicialização seguro a ser habilitada no dispositivo</span><span class="sxs-lookup"><span data-stu-id="10c43-442">Require Secure Boot to be enabled on the device</span></span>|<span data-ttu-id="10c43-443">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="10c43-443">Require</span></span>||
|<span data-ttu-id="10c43-444">Requer integridade de código</span><span class="sxs-lookup"><span data-stu-id="10c43-444">Require code integrity</span></span>|<span data-ttu-id="10c43-445">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="10c43-445">Require</span></span>||


<span data-ttu-id="10c43-446">**Propriedades do dispositivo**</span><span class="sxs-lookup"><span data-stu-id="10c43-446">**Device properties**</span></span>

|<span data-ttu-id="10c43-447">Tipo</span><span class="sxs-lookup"><span data-stu-id="10c43-447">Type</span></span>|<span data-ttu-id="10c43-448">Propriedades</span><span class="sxs-lookup"><span data-stu-id="10c43-448">Properties</span></span>|<span data-ttu-id="10c43-449">Valores</span><span class="sxs-lookup"><span data-stu-id="10c43-449">Values</span></span>|<span data-ttu-id="10c43-450">Notas</span><span class="sxs-lookup"><span data-stu-id="10c43-450">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="10c43-451">Versão do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="10c43-451">Operating system version</span></span>|<span data-ttu-id="10c43-452">Tudo</span><span class="sxs-lookup"><span data-stu-id="10c43-452">All</span></span>|<span data-ttu-id="10c43-453">Não configurado</span><span class="sxs-lookup"><span data-stu-id="10c43-453">Not configured</span></span>||

<span data-ttu-id="10c43-p126">Para todas as políticas acima devem ser considerados implantadas, eles precisa ser direcionados a grupos de usuários. Você pode fazer isso criando a política (ao salvar) ou posterior, selecionando **Gerenciar Deployment** na seção **política** (mesmo nível Add).</span><span class="sxs-lookup"><span data-stu-id="10c43-p126">For all the above policies to be considered deployed, they must be targeted at user groups. You can do this by creating the policy (on Save) or later by selecting **Manage Deployment** in the **Policy** section (same level as Add).</span></span>

<span data-ttu-id="10c43-456">**Segurança do sistema**</span><span class="sxs-lookup"><span data-stu-id="10c43-456">**System security**</span></span>

|<span data-ttu-id="10c43-457">Tipo</span><span class="sxs-lookup"><span data-stu-id="10c43-457">Type</span></span>|<span data-ttu-id="10c43-458">Propriedades</span><span class="sxs-lookup"><span data-stu-id="10c43-458">Properties</span></span>|<span data-ttu-id="10c43-459">Valores</span><span class="sxs-lookup"><span data-stu-id="10c43-459">Values</span></span>|<span data-ttu-id="10c43-460">Notas</span><span class="sxs-lookup"><span data-stu-id="10c43-460">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="10c43-461">Senha</span><span class="sxs-lookup"><span data-stu-id="10c43-461">Password</span></span>|<span data-ttu-id="10c43-462">Exigir uma senha para desbloquear os dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="10c43-462">Require a password to unlock mobile devices</span></span>|<span data-ttu-id="10c43-463">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="10c43-463">Require</span></span>||
||<span data-ttu-id="10c43-464">Senhas simples</span><span class="sxs-lookup"><span data-stu-id="10c43-464">Simple passwords</span></span>|<span data-ttu-id="10c43-465">Bloquear</span><span class="sxs-lookup"><span data-stu-id="10c43-465">Block</span></span>||
||<span data-ttu-id="10c43-466">Tipo de senha</span><span class="sxs-lookup"><span data-stu-id="10c43-466">Password type</span></span>|<span data-ttu-id="10c43-467">Padrão de dispositivo</span><span class="sxs-lookup"><span data-stu-id="10c43-467">Device default</span></span>||
||<span data-ttu-id="10c43-468">Tamanho mínimo da senha</span><span class="sxs-lookup"><span data-stu-id="10c43-468">Minimum password length</span></span>|<span data-ttu-id="10c43-469">6</span><span class="sxs-lookup"><span data-stu-id="10c43-469">6</span></span>||
||<span data-ttu-id="10c43-470">Máximo de minutos de inatividade antes que a senha é obrigatória</span><span class="sxs-lookup"><span data-stu-id="10c43-470">Maximum minutes of inactivity before password is required</span></span>|<span data-ttu-id="10c43-471">15 </span><span class="sxs-lookup"><span data-stu-id="10c43-471">15</span></span>|<span data-ttu-id="10c43-p127">Essa configuração é suportada para Android versões 4.0 e acima ou KNOX 4.0 e acima. Para dispositivos iOS, ela é suportada para iOS 8.0 e acima</span><span class="sxs-lookup"><span data-stu-id="10c43-p127">This setting is supported for Android versions 4.0 and above or KNOX 4.0 and above. For iOS devices, it’s supported for iOS 8.0 and above</span></span>|
||<span data-ttu-id="10c43-474">Vencimento da senha (dias)</span><span class="sxs-lookup"><span data-stu-id="10c43-474">Password expiration (days)</span></span>|<span data-ttu-id="10c43-475">41</span><span class="sxs-lookup"><span data-stu-id="10c43-475">41</span></span>||
||<span data-ttu-id="10c43-476">Número de senhas anteriores para evitar a reutilização</span><span class="sxs-lookup"><span data-stu-id="10c43-476">Number of previous passwords to prevent reuse</span></span>|<span data-ttu-id="10c43-477">5</span><span class="sxs-lookup"><span data-stu-id="10c43-477">5</span></span>||
||<span data-ttu-id="10c43-478">Exigir senha quando o dispositivo retorna a partir de um estado ocioso (Mobile e Holographic)</span><span class="sxs-lookup"><span data-stu-id="10c43-478">Require password when device returns from idle state (Mobile and Holographic)</span></span>|<span data-ttu-id="10c43-479">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="10c43-479">Require</span></span>|<span data-ttu-id="10c43-480">Disponível para o Windows 10 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="10c43-480">Available for Windows 10 and later</span></span>|
|<span data-ttu-id="10c43-481">Criptografia</span><span class="sxs-lookup"><span data-stu-id="10c43-481">Encryption</span></span>|<span data-ttu-id="10c43-482">Criptografia de armazenamento de dados no dispositivo</span><span class="sxs-lookup"><span data-stu-id="10c43-482">Encryption of data storage on device</span></span>|<span data-ttu-id="10c43-483">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="10c43-483">Require</span></span>||
|<span data-ttu-id="10c43-484">Segurança de dispositivo</span><span class="sxs-lookup"><span data-stu-id="10c43-484">Device Security</span></span>|<span data-ttu-id="10c43-485">Firewall</span><span class="sxs-lookup"><span data-stu-id="10c43-485">Firewall</span></span>|<span data-ttu-id="10c43-486">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="10c43-486">Require</span></span>||
||<span data-ttu-id="10c43-487">Antivírus</span><span class="sxs-lookup"><span data-stu-id="10c43-487">Antivirus</span></span>|<span data-ttu-id="10c43-488">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="10c43-488">Require</span></span>||
||<span data-ttu-id="10c43-489">AntiSpyware</span><span class="sxs-lookup"><span data-stu-id="10c43-489">Antispyware</span></span>|<span data-ttu-id="10c43-490">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="10c43-490">Require</span></span>|<span data-ttu-id="10c43-491">Esta configuração exige uma solução antispyware registrada na Central de segurança do Windows</span><span class="sxs-lookup"><span data-stu-id="10c43-491">This setting requires an Anti-Spyware solution registered with Windows Security Center</span></span>|
|<span data-ttu-id="10c43-492">Defender</span><span class="sxs-lookup"><span data-stu-id="10c43-492">Defender</span></span>|<span data-ttu-id="10c43-493">Windows Defender Antimalware</span><span class="sxs-lookup"><span data-stu-id="10c43-493">Windows Defender Antimalware</span></span>|<span data-ttu-id="10c43-494">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="10c43-494">Require</span></span>||
||<span data-ttu-id="10c43-495">Versão mínima do Windows Defender Antimalware</span><span class="sxs-lookup"><span data-stu-id="10c43-495">Windows Defender Antimalware minimum version</span></span>||<span data-ttu-id="10c43-p128">Só tem suporte para desktop do Windows 10. A Microsoft recomenda versões não mais de cinco por trás da versão mais recente</span><span class="sxs-lookup"><span data-stu-id="10c43-p128">Only supported for Windows 10 desktop. Microsoft recommends versions no more than five behind from the most recent version</span></span>|
||<span data-ttu-id="10c43-498">Assinatura do Windows Defender Antimalware atualizada</span><span class="sxs-lookup"><span data-stu-id="10c43-498">Windows Defender Antimalware signature up to date</span></span>|<span data-ttu-id="10c43-499">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="10c43-499">Require</span></span>||
||<span data-ttu-id="10c43-500">Proteção em tempo real</span><span class="sxs-lookup"><span data-stu-id="10c43-500">Real-time protection</span></span>|<span data-ttu-id="10c43-501">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="10c43-501">Require</span></span>|<span data-ttu-id="10c43-502">Só tem suporte para a área de trabalho do Windows 10</span><span class="sxs-lookup"><span data-stu-id="10c43-502">Only supported for Windows 10 desktop</span></span>|

<span data-ttu-id="10c43-503">**Windows Defender ATP**</span><span class="sxs-lookup"><span data-stu-id="10c43-503">**Windows Defender ATP**</span></span>

|<span data-ttu-id="10c43-504">Tipo</span><span class="sxs-lookup"><span data-stu-id="10c43-504">Type</span></span>|<span data-ttu-id="10c43-505">Propriedades</span><span class="sxs-lookup"><span data-stu-id="10c43-505">Properties</span></span>|<span data-ttu-id="10c43-506">Valores</span><span class="sxs-lookup"><span data-stu-id="10c43-506">Values</span></span>|<span data-ttu-id="10c43-507">Notas</span><span class="sxs-lookup"><span data-stu-id="10c43-507">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="10c43-508">Regras de proteção de ameaça avançado do Windows Defender</span><span class="sxs-lookup"><span data-stu-id="10c43-508">Windows Defender Advanced Threat Protection rules</span></span>|<span data-ttu-id="10c43-509">Exigir o dispositivo esteja em ou subordinadas a pontuação de risco de máquina</span><span class="sxs-lookup"><span data-stu-id="10c43-509">Require the device to be at or under the machine-risk score</span></span>|<span data-ttu-id="10c43-510">Médio</span><span class="sxs-lookup"><span data-stu-id="10c43-510">Medium</span></span>||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a><span data-ttu-id="10c43-511">Exigir compatível com PCs (mas não compatível com telefones e tablets)</span><span class="sxs-lookup"><span data-stu-id="10c43-511">Require compliant PCs (but not compliant phones and tablets)</span></span>
<span data-ttu-id="10c43-p129">Antes de adicionar uma diretiva para exigir compatível com PCs, certifique-se de registrar os dispositivos de gerenciamento em Intune. Usar a autenticação multifator é recomendado antes de inscrição de dispositivos em Intune para garantia de que o dispositivo está em posse do usuário desejado.</span><span class="sxs-lookup"><span data-stu-id="10c43-p129">Before adding a policy to require compliant PCs, be sure to enroll devices for management into Intune. Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> 

<span data-ttu-id="10c43-514">Para exigir PCs compatível com:</span><span class="sxs-lookup"><span data-stu-id="10c43-514">To require compliant PCs:</span></span>

1. <span data-ttu-id="10c43-p130">Vá para o [portal do Windows Azure](https://portal.azure.com)e entrar com suas credenciais. Depois que você tiver entrado com êxito, você verá o painel de controle Azure.</span><span class="sxs-lookup"><span data-stu-id="10c43-p130">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="10c43-517">Escolha **Azure Active Directory** no menu à esquerda.</span><span class="sxs-lookup"><span data-stu-id="10c43-517">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="10c43-518">Na seção **Segurança**, escolha **Acesso condicional**.</span><span class="sxs-lookup"><span data-stu-id="10c43-518">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="10c43-519">Escolha **Nova política**.</span><span class="sxs-lookup"><span data-stu-id="10c43-519">Choose **New policy**.</span></span>

5. <span data-ttu-id="10c43-520">Insira um nome para a política e escolha os **Usuários e grupos** aos quais deseja aplicar a política.</span><span class="sxs-lookup"><span data-stu-id="10c43-520">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="10c43-521">Escolha **Aplicativos na nuvem**.</span><span class="sxs-lookup"><span data-stu-id="10c43-521">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="10c43-p131">Escolha **Selecionar aplicativos**, selecione os aplicativos desejados na lista de **aplicativos na nuvem** . Por exemplo, selecione Exchange Online do Office 365. Escolha **Selecionar** e **feito**.</span><span class="sxs-lookup"><span data-stu-id="10c43-p131">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="10c43-p132">Para exigir compatível com PCs, mas não compatível com telefones e tablets, escolha **plataformas de dispositivo**e **condições** . Escolha **Selecionar plataformas de dispositivo** e selecione **Windows** e **macOS**.</span><span class="sxs-lookup"><span data-stu-id="10c43-p132">To require compliant PCs, but not compliant phones and tablets, choose **Conditions** and **Device platforms**. Choose **Select device platforms** and select **Windows** and **macOS**.</span></span>

9. <span data-ttu-id="10c43-527">Escolha **Conceder** na seção **Controles de acesso**.</span><span class="sxs-lookup"><span data-stu-id="10c43-527">Choose **Grant** from the **Access controls** section.</span></span>

10. <span data-ttu-id="10c43-p133">Escolha **conceder acesso**, selecione **exigir o dispositivo deve ser marcado como compatível com**. Para vários controles, selecione **exigir todos os controles selecionados**e selecione **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="10c43-p133">Choose **Grant access**, select **Require device to be marked as compliant**. For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

11. <span data-ttu-id="10c43-530">Escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="10c43-530">Choose **Create**.</span></span>

<span data-ttu-id="10c43-p134">Se o seu objetivo é exigem compatível com PCs *e* dispositivos móveis, não marque plataformas. Impõe a conformidade para todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="10c43-p134">If your objective is to require compliant PCs *and* mobile devices, do not select platforms. This enforces compliance for all devices.</span></span> 

## <a name="require-compliant-pcs-and-mobile-devices"></a><span data-ttu-id="10c43-533">Exigir compatível com PCs *e* dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="10c43-533">Require compliant PCs *and* mobile devices</span></span>

<span data-ttu-id="10c43-534">Para exigir a conformidade para todos os dispositivos:</span><span class="sxs-lookup"><span data-stu-id="10c43-534">To require compliance for all devices:</span></span>

1. <span data-ttu-id="10c43-p135">Vá para o [portal do Windows Azure](https://portal.azure.com)e entrar com suas credenciais. Depois que você tiver entrado com êxito, você verá o painel de controle Azure.</span><span class="sxs-lookup"><span data-stu-id="10c43-p135">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="10c43-537">Escolha **Azure Active Directory** no menu à esquerda.</span><span class="sxs-lookup"><span data-stu-id="10c43-537">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="10c43-538">Na seção **Segurança**, escolha **Acesso condicional**.</span><span class="sxs-lookup"><span data-stu-id="10c43-538">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="10c43-539">Escolha **Nova política**.</span><span class="sxs-lookup"><span data-stu-id="10c43-539">Choose **New policy**.</span></span>

5. <span data-ttu-id="10c43-540">Insira um nome para a política e escolha os **Usuários e grupos** aos quais deseja aplicar a política.</span><span class="sxs-lookup"><span data-stu-id="10c43-540">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="10c43-541">Escolha **Aplicativos na nuvem**.</span><span class="sxs-lookup"><span data-stu-id="10c43-541">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="10c43-p136">Escolha **Selecionar aplicativos**, selecione os aplicativos desejados na lista de **aplicativos na nuvem** . Por exemplo, selecione Exchange Online do Office 365. Escolha **Selecionar** e **feito**.</span><span class="sxs-lookup"><span data-stu-id="10c43-p136">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="10c43-545">Escolha **Conceder** na seção **Controles de acesso**.</span><span class="sxs-lookup"><span data-stu-id="10c43-545">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="10c43-p137">Escolha **conceder acesso**, selecione **exigir o dispositivo deve ser marcado como compatível com**. Para vários controles, selecione **exigir todos os controles selecionados**e selecione **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="10c43-p137">Choose **Grant access**, select **Require device to be marked as compliant**. For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="10c43-548">Escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="10c43-548">Choose **Create**.</span></span>

<span data-ttu-id="10c43-p138">Ao criar essa diretiva, não marque plataformas. Aplica a dispositivos incompatíveis.</span><span class="sxs-lookup"><span data-stu-id="10c43-p138">When creating this policy, do not select platforms. This enforces compliant devices.</span></span>




<!---
#### Data loss prevention
The goal for your device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain or enroll their PCs into management with Microsoft Intune or System Center Configuration Manager.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact

For most organizations, it is important to be able to set user expectations around when and for which conditions they will be expected to sign into Office 365 to access their email.  

Users typically benefit from single sign-on (SSO) except during the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users may be asked to MFA whenever a **medium or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Sensitive
This section describes the recommendations for the sensitive tier of data, identity, and device protection. These recommendations are for customers who have a subset of data that must be protected at higher levels or require all data to be protected at these higher levels.

You can apply increased protection to all or specific data sets in your Office 365 environment. For example, you can apply policies to ensure sensitive data is only shared between protected apps to prevent data loss. We recommend protecting identities and devices that access sensitive data with comparable levels of security.

### Conditional access policy settings
#### Identity protection

You can give users single sign-on (SSO) experience as described in earlier sections. You only need to intervene when necessary based on [risk events](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Require MFA on **low or above** risk sessions
* Require secure password change for high risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data loss prevention

The goal for these device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their PCs to an Active Directory Domain or enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 email.

Users typically benefit from single sign-on (SSO) except under the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to MFA whenever a **low or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Highly regulated
This section describes the recommendations for the highly regulated tier of data, identity, and device protection. These recommendations are for customers who may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

### Conditional access policy settings
#### Identity protection

For the highly regulated tier Microsoft recommends enforcing MFA for all new sessions.
* Require MFA for all new sessions
* Require secure password change for **high** risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data Loss Prevention
The goal for these device and app management policies is to prevent data loss in the event of a lost or stolen device. This is done by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

For the highly regulated tier, we recommend requiring apps that support Intune App Protection policy running only on Intune compliant or domain-joined devices.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain, **or** enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that devices used to access Office 365 email and files are managed by Intune or company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are Low risk as determined by a third-party MTP like Lookout or SkyCure.|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 files.

* Users configured as highly regulated will be required to re-authenticate with MFA after their session expires.
* When users at risk sign-in they will be asked to change their password after completing MFA.
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to perform MFA whenever they begin a new session.  
  * Users will be required to use email apps that support the Intune App Protection SDK
  * Users will be required to access emails from Intune compliant or AD domain-joined devices.
--->
## <a name="next-steps"></a><span data-ttu-id="10c43-551">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="10c43-551">Next steps</span></span>

[<span data-ttu-id="10c43-552">Saiba mais sobre recomendações de política para proteger o email</span><span class="sxs-lookup"><span data-stu-id="10c43-552">Learn about policy recommendations for securing email</span></span>](secure-email-recommended-policies.md)
