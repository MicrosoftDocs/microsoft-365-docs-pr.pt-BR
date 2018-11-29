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
# <a name="step-9-simplify-password-updates"></a>Etapa 9: Simplificar as atualizações de senha

*Esta etapa é opcional para ambientes híbridos e se aplica para as versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Nesta etapa, você vai permitir aos usuários que redefinam as senhas pelo Azure Active Directory (AD), o que é então replicado para o Windows Server Active Directory (AD) local. Esse processo é conhecido como write-back de senha. Com o write-back de senha, os usuários não precisam atualizar suas senhas por meio do Windows Server AD local, onde estão armazenadas as contas de usuários e seus atributos. Isso é importante para usuários remotos ou para aqueles em roaming que não têm conexão de acesso remoto à rede local.

O write-back de senha é necessário para utilizar completamente as capacidades de recursos de Proteção de Identidade, por exemplo para exigir que os usuários alterem a senha local quando for detectado um alto risco de comprometimento da conta.

Para obter mais informações e instruções de configuração, consulte o artigo sobre o [Azure AD SSPR com o write-back de senha](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).

>[!Note]
>Atualize para a versão mais recente do Azure AD Connect a fim de garantir a melhor experiência possível e o acesso a novos recursos à medida que são lançados. Para saber mais, consulte as informações sobre a [instalação personalizada do Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

Como ponto de verificação provisório, você pode consultar os [critérios de saída](identity-exit-criteria.md#crit-identity-pw-writeback) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step10.png)| [Simplificar a entrada do usuário](identity-single-sign-on.md) |

