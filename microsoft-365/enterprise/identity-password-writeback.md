---
title: 'Etapa 9: Simplificar as atualizações de senha'
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
description: Entender e configurar o write-back de senha para ambientes híbridos.
ms.openlocfilehash: 55da101ca729de804ae76dafbe35a46969af9d8d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864861"
---
# <a name="step-9-simplify-password-updates"></a><span data-ttu-id="c5a14-103">Etapa 9: Simplificar as atualizações de senha</span><span class="sxs-lookup"><span data-stu-id="c5a14-103">Step 9: Simplify password updates</span></span>

<span data-ttu-id="c5a14-104">*Esta etapa é opcional para ambientes híbridos e se aplica para as versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="c5a14-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="c5a14-p101">Nesta etapa, você vai permitir aos usuários que redefinam as senhas pelo Azure Active Directory (AD), o que é então replicado para o Windows Server Active Directory (AD) local. Esse processo é conhecido como write-back de senha. Com o write-back de senha, os usuários não precisam atualizar suas senhas por meio do Windows Server AD local, onde estão armazenadas as contas de usuários e seus atributos. Isso é importante para usuários remotos ou para aqueles em roaming que não têm conexão de acesso remoto à rede local.</span><span class="sxs-lookup"><span data-stu-id="c5a14-p101">In this step, you'll allow users to reset their passwords through Azure Active Directory (AD), which is then replicated to your local Windows Server Active Directory (AD). This process is known as password writeback. With password writeback, users don’t need to update their passwords through the on-premises Windows Server AD where user accounts and their attributes are stored. This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="c5a14-109">O write-back de senha é necessário para utilizar completamente as capacidades de recursos de Proteção de Identidade, por exemplo para exigir que os usuários alterem a senha local quando for detectado um alto risco de comprometimento da conta.</span><span class="sxs-lookup"><span data-stu-id="c5a14-109">Password writeback is required to fully utilize Identity Protection feature capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="c5a14-110">Para obter mais informações e instruções de configuração, consulte o artigo sobre o [Azure AD SSPR com o write-back de senha](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="c5a14-110">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="c5a14-p102">Atualize para a versão mais recente do Azure AD Connect a fim de garantir a melhor experiência possível e o acesso a novos recursos à medida que são lançados. Para saber mais, consulte as informações sobre a [instalação personalizada do Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="c5a14-p102">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

<span data-ttu-id="c5a14-113">Como ponto de verificação provisório, você pode consultar os [critérios de saída](identity-exit-criteria.md#crit-identity-pw-writeback) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="c5a14-113">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="c5a14-114">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="c5a14-114">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step10.png)| [<span data-ttu-id="c5a14-115">Simplificar a entrada do usuário</span><span class="sxs-lookup"><span data-stu-id="c5a14-115">Simplify user sign-in</span></span>](identity-single-sign-on.md) |

