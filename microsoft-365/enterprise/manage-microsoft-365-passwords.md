---
title: Gerenciar Microsoft 365 senhas de conta de usuário
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Saiba mais sobre como gerenciar Microsoft 365 senhas de conta de usuário.
ms.openlocfilehash: 2062da49310121ec18f7ce21f523531f10d6df9b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905087"
---
# <a name="manage-microsoft-365-user-account-passwords"></a>Gerenciar Microsoft 365 senhas de conta de usuário

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Você pode gerenciar Microsoft 365 senhas de conta de usuário de várias maneiras diferentes, dependendo de sua configuração de identidade. Você pode gerenciar contas de usuário no centro de administração do Microsoft 365 [,](../admin/add-users/index.yml)nos Serviços de Domínio do Active Directory (AD DS) ou no centro de administração Azure Active Directory (Azure AD).

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a>Planejar onde e como você gerenciará suas senhas de conta de usuário

Onde e como você pode gerenciar suas contas de usuário depende do modelo de identidade que você deseja usar para sua Microsoft 365. Os dois modelos são somente na nuvem e híbridos.
  
### <a name="cloud-only"></a>Apenas Nuvem

Você gerencia senhas de conta de usuário em:

- [O Centro de administração do Microsoft 365](../admin/add-users/index.yml)
- Centro de administração do Azure AD
    
### <a name="hybrid"></a>Híbrido

Com a identidade híbrida, as senhas são armazenadas no AD DS, portanto, você deve usar as ferramentas locais do AD DS para gerenciar senhas de conta de usuário. Mesmo ao usar a Sincronização de Hash de Senha (PHS), na qual o Azure AD armazena uma versão com hash da versão já com hash no AD DS, você e os usuários devem gerenciar suas senhas no AD DS.

Com [o writeback de senha,](#pw_writeback)os usuários podem alterar suas senhas do AD DS por meio do Azure AD.

## <a name="prevent-bad-passwords"></a>Evitar o uso de senhas ruins

Todos os usuários devem usar as [Diretrizes de senhas da Microsoft](https://www.microsoft.com/research/publication/password-guidance) para criar senhas de conta de usuário.

Para impedir que os usuários criem senhas que possam ser facilmente descobertas, use a proteção de senhas do Azure AD, que usa uma lista geral e uma opcional personalizada de senhas proibidas, sendo a última especificada por você. Você pode, por exemplo, usar termos específicos da sua organização, como:

- Nomes de marcas
- Nomes de produtos
- Locais (por exemplo, sedes de empresas)
- Termos internos específicos da empresa
- Abreviaturas com significados específicos da empresa.

Você pode proibir senhas [incorretas na](/azure/active-directory/authentication/concept-password-ban-bad) nuvem e para o [AD DS](/azure/active-directory/authentication/concept-password-ban-bad-on-premises)local.

## <a name="simplify-user-sign-in"></a>Simplificar a entrada do usuário

O Azure AD Seamless Single Sign-On (SSO Contínuo do Azure AD) funciona com PHS e autenticação Pass-Through (PTA), para permitir que seus usuários entre em serviços que usam contas de usuário do Azure AD sem precisar digitar suas senhas e, em muitos casos, seus nomes de usuário. Isso facilita o acesso de seus usuários a aplicativos baseados na nuvem, como o Office 365, sem precisar de nenhum componente adicional local, como servidores de federação de identidades.

Você configura o SSO Contínuo do Azure Active Directory com a ferramenta Azure AD Connect. Confira as [instruções para configurar o SSO Contínuo do Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a>Simplificar atualizações de senha para o AD DS

Com o writeback de senha, você pode permitir que os usuários redefinirem suas senhas por meio do Azure AD, que é replicado para o AD DS. Os usuários não precisam acessar o AD DS local para atualizar suas senhas. Isso é valioso para usuários móveis ou remotos que não têm uma conexão de acesso remoto à rede local.

O write-back de senha é necessário para o uso por completo das capacidades de Proteção de Identidade do Azure AD, por exemplo para exigir que os usuários alterem a senha local quando for detectado um alto risco de comprometimento da conta.

Para obter mais informações e instruções de configuração, consulte o artigo sobre o [Azure AD SSPR com o write-back de senha](/azure/active-directory/active-directory-passwords-writeback).

>[!Note]
>Atualize para a versão mais recente do Azure AD Connect a fim de garantir a melhor experiência possível e o acesso a novos recursos à medida que são lançados. Para saber mais, consulte as informações sobre a [instalação personalizada do Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

## <a name="simplify-password-resets"></a>Simplificar as redefinições de senha

A redefinição de senha de autoatendados (SSPR) permite que os usuários redefinir ou desbloquear suas senhas ou contas. Para ser alertado sobre uso indevido ou abuso, você pode usar os relatórios detalhados que rastreiam quando usuários acessam o sistema, junto com as notificações. Você deve [habilitar o writeback de senha](#pw_writeback) antes de implantar redefinições de senha.

Confira as[instruções para implantar redefinição de senha](/azure/active-directory/authentication/howto-sspr-deployment).