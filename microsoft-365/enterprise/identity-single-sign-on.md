---
title: 'Etapa 10: Simplificar entrada de usuários'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda e configure o logon único contínuo (SSO Contínuo) do Azure Active Directory.
ms.openlocfilehash: 9d18cb559d3a4a9ee401e0f94fb53bc6360d88c8
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865222"
---
# <a name="step-10-simplify-user-sign-in"></a><span data-ttu-id="62560-103">Etapa 10: Simplificar entrada de usuários</span><span class="sxs-lookup"><span data-stu-id="62560-103">Step 10: Simplify user sign-in</span></span>

<span data-ttu-id="62560-104">*Esta etapa é opcional para ambientes híbridos e se aplica para as versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="62560-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="62560-p101">Nesta etapa, você vai configurar o logon único contínuo do Azure Active Directory (SSO Contínuo do Azure Active Directory) para permitir que os usuários entrem em serviços que usam as contas de usuário do Azure Active Directory sem precisar digitar as senhas e, em muitos casos, os nomes de usuário. Isso facilita o acesso dos usuários aos aplicativos baseados em nuvem, como o Office 365, sem precisar adicionar componentes locais, como servidores de federação de identidades.</span><span class="sxs-lookup"><span data-stu-id="62560-p101">In Step 8, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames. This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="62560-107">Você configurará o SSO Contínuo do Azure Active Directory com a ferramenta Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="62560-107">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="62560-108">Confira as [instruções para configurar o SSO Contínuo do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="62560-108">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="62560-110">Guia do Laboratório de Teste: Logon Único Contínuo do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="62560-110">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="62560-111">Como um ponto de verificação provisório, é possível ver os [critérios de saída](identity-exit-criteria.md#crit-identity-sso) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="62560-111">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="62560-112">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="62560-112">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step11.png)| [<span data-ttu-id="62560-113">Personalizar páginas de entrada do Office 365</span><span class="sxs-lookup"><span data-stu-id="62560-113">Customize the Office 365 sign-in page</span></span>](identity-customize-office-365-sign-in.md) |

