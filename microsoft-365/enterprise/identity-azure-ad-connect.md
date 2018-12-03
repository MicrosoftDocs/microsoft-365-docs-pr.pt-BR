---
title: 'Etapa 7: Sincronizar as identidades'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/09/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda as opções de identidade e configure o Azure AD Connect para sincronizar seu Windows Server AD local com o Azure AD.
ms.openlocfilehash: 2391ee11a1706bbbfdeb248c5967822d3ea68f72
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864753"
---
# <a name="step-7-synchronize-identities"></a><span data-ttu-id="23150-103">Etapa 7: Sincronizar as identidades</span><span class="sxs-lookup"><span data-stu-id="23150-103">Step 7: Synchronize identities</span></span>

<span data-ttu-id="23150-104">*Esta etapa é obrigatória para ambientes híbridos e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="23150-104">*This step is required for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="23150-105">Nesta etapa, você sincronizará seu Windows Server Active Directory (AD) local com o locatário do Azure Active Directory (AD) usado por suas assinaturas do Office 365 e Enterprise Mobility + Security (EMS).</span><span class="sxs-lookup"><span data-stu-id="23150-105">In this step, you'll synchronize your on-premises Windows Server Active Directory (AD) with the Azure Active Directory (AD) tenant used by your Office 365 and Enterprise Mobility + Security (EMS) subscriptions.</span></span>

<span data-ttu-id="23150-106">O Azure AD Connect é a ferramenta da Microsoft compatível que orienta você para sincronizar apenas as identidades de que você realmente precisa de ambientes Windows Server AD com uma ou várias florestas para seu locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="23150-106">Azure AD Connect is the supported Microsoft tool that guides you through synchronizing only the identities you really need from single or multi-forest Windows Server AD environments to your Azure AD tenant.</span></span>

![Como o Azure AD Connect sincroniza seu diretório local ao Azure AD](./media/identity-azure-ad-connect/azure-ad-connect.png)

<span data-ttu-id="23150-108">*Como o Azure AD Connect sincroniza seu diretório local ao Azure AD*</span><span class="sxs-lookup"><span data-stu-id="23150-108">*How Azure AD Connect synchronizes your on-premises directory with Azure AD*</span></span>

<span data-ttu-id="23150-p101">A primeira decisão em sua solução de identidade híbrida é o requisito de autenticação. As alternativas a seguir são opções:</span><span class="sxs-lookup"><span data-stu-id="23150-p101">The first decision in your hybrid identity solution is your authentication requirement. The following options are options:</span></span>

- <span data-ttu-id="23150-p102">Com a **autenticação gerenciada**, o Azure AD lida com o processo de autenticação do login do usuário. Há dois métodos de autenticação gerenciada:</span><span class="sxs-lookup"><span data-stu-id="23150-p102">With **managed authentication**, Azure AD handles the authentication process for user sign-in. There are two methods for managed authentication:</span></span> 
    - <span data-ttu-id="23150-p103">**Sincronização de Hash de Senha (PHS)** [Recomendada e obrigatória para alguns recursos premium]. Essa é a maneira mais simples para habilitar a autenticação para objetos de diretório locais no Azure AD. O Azure AD Connect extrai senha hash do AD do Windows Server, executa o processamento de segurança adicional na senha e a salva no Azure AD. Para saber mais, confira [Implementar a sincronização de hash de senha com a sincronização do Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).</span><span class="sxs-lookup"><span data-stu-id="23150-p103">**Password Hash Sync (PHS)** [Recommended and required for some premium features]. This is the simplest way to enable authentication for on-premises directory objects in Azure AD. Azure AD Connect extracts the hashed password from Windows Server AD, does extra security processing on the password, and saves it in Azure AD. For more information, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).</span></span>
    - <span data-ttu-id="23150-p104">A **Autenticação Passagem (PTA)** fornece uma solução de validação de senha simples para serviços baseados no Azure AD. A PTA usa um agente em um ou mais servidores locais para validar as autenticações do usuário diretamente com o Windows Server AD local. Para saber mais, confira [Login de usuário com a Autenticação de Passagem do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span><span class="sxs-lookup"><span data-stu-id="23150-p104">**Pass-through Authentication (PTA)** provides a simple password validation solution for Azure AD-based services. PTA uses an agent running on one or more on-premises servers to validate the user authentications directly with your on-premises Windows Server AD. For more information, see [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span></span>
- <span data-ttu-id="23150-p105">Com a **autenticação federada**, o processo de autenticação é redirecionado para outro provedor de identidade por meio de um servidor de federação de identidade, como os Serviços de Federação do Active Directory (AD FS) para o login de um usuário. O provedor de identidade pode fornecer métodos de autenticação adicionais, como a autenticação baseada em cartão inteligente. Para saber mais, confira [Escolhendo o método de autenticação correto para sua solução de identidade híbrida do Azure Active Directory](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span><span class="sxs-lookup"><span data-stu-id="23150-p105">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in. The identity provider can provide additional authentication methods, such as smartcard-based authentication. For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span></span>

<span data-ttu-id="23150-123">Depois de determinar sua solução de identidade híbrida, baixe e execute a [Ferramenta de Correção de Erros de Sincronização de Diretórios IdFix](https://www.microsoft.com/download/details.aspx?id=36832) para verificar se seu Windows Server AD tem problemas.</span><span class="sxs-lookup"><span data-stu-id="23150-123">After you've determined your hybrid identity solution, download and run the [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) to analyze your Windows Server AD for issues.</span></span>

<span data-ttu-id="23150-p106">Depois de resolver todos os problemas identificados pela ferramenta IdFix, confira [Implementar a sincronização de hash de senha](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) para obter instruções sobre como instalar a ferramenta Azure AD Connect e configurar a sincronização de diretórios entre o Windows Server AD local e o locatário do Azure AD para suas assinaturas do Office 365 e do EMS. Depois que a sincronização for iniciada, você manterá suas contas de usuários e grupos com seu provedor de identidade local, como o Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="23150-p106">After resolving all of the issues identified by the IdFix tool, see [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) for guidance on installing the Azure AD Connect tool and configuring directory synchronization between your on-premises Windows Server AD and the Azure AD tenant for your Office 365 and EMS subscriptions. After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as Windows Server AD.</span></span>

<span data-ttu-id="23150-126">A Microsoft fornece um conjunto de recomendações para [acesso de dispositivo e identidade](microsoft-365-policies-configurations.md) para garantir uma força de trabalho segura e produtiva.</span><span class="sxs-lookup"><span data-stu-id="23150-126">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> 
- <span data-ttu-id="23150-127">Para obter os requisitos recomendados para ambientes híbridos, confira a coluna **Active Directory com sincronização de hash de senha** em [pré-requisitos](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="23150-127">For recommended requirements for hybrid environments, see the **Active Directory with password hash sync** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span> 

- <span data-ttu-id="23150-128">Para obter requisitos recomendados para ambientes somente de nuvem, confira a coluna **Somente de nuvem** em [pré-requisitos](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="23150-128">For recommended requirements for cloud only environments, see the **Cloud only** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span>

|||
|:-------|:-----|
|![Guias de laboratório de teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="23150-130">Guia de laboratório de teste: Sincronização de hash de senha</span><span class="sxs-lookup"><span data-stu-id="23150-130">Test Lab Guide: Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)<br> [<span data-ttu-id="23150-131">Guia de laboratório de teste: Autenticação passagem</span><span class="sxs-lookup"><span data-stu-id="23150-131">Test Lab Guide: Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md) |
|||

<span data-ttu-id="23150-132">Como ponto de verificação provisório, você pode consultar os [critérios de saída](identity-exit-criteria.md#crit-identity-sync) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="23150-132">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="23150-133">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="23150-133">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step8.png)| [<span data-ttu-id="23150-134">Monitorar integridades de sincronização</span><span class="sxs-lookup"><span data-stu-id="23150-134">Monitor synchronization health</span></span>](identity-azure-ad-connect-health.md) |

