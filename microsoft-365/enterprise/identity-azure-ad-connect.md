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
# <a name="step-7-synchronize-identities"></a>Etapa 7: Sincronizar as identidades

*Esta etapa é obrigatória para ambientes híbridos e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Nesta etapa, você sincronizará seu Windows Server Active Directory (AD) local com o locatário do Azure Active Directory (AD) usado por suas assinaturas do Office 365 e Enterprise Mobility + Security (EMS).

O Azure AD Connect é a ferramenta da Microsoft compatível que orienta você para sincronizar apenas as identidades de que você realmente precisa de ambientes Windows Server AD com uma ou várias florestas para seu locatário do Azure AD.

![Como o Azure AD Connect sincroniza seu diretório local ao Azure AD](./media/identity-azure-ad-connect/azure-ad-connect.png)

*Como o Azure AD Connect sincroniza seu diretório local ao Azure AD*

A primeira decisão em sua solução de identidade híbrida é o requisito de autenticação. As alternativas a seguir são opções:

- Com a **autenticação gerenciada**, o Azure AD lida com o processo de autenticação do login do usuário. Há dois métodos de autenticação gerenciada: 
    - **Sincronização de Hash de Senha (PHS)** [Recomendada e obrigatória para alguns recursos premium]. Essa é a maneira mais simples para habilitar a autenticação para objetos de diretório locais no Azure AD. O Azure AD Connect extrai senha hash do AD do Windows Server, executa o processamento de segurança adicional na senha e a salva no Azure AD. Para saber mais, confira [Implementar a sincronização de hash de senha com a sincronização do Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).
    - A **Autenticação Passagem (PTA)** fornece uma solução de validação de senha simples para serviços baseados no Azure AD. A PTA usa um agente em um ou mais servidores locais para validar as autenticações do usuário diretamente com o Windows Server AD local. Para saber mais, confira [Login de usuário com a Autenticação de Passagem do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).
- Com a **autenticação federada**, o processo de autenticação é redirecionado para outro provedor de identidade por meio de um servidor de federação de identidade, como os Serviços de Federação do Active Directory (AD FS) para o login de um usuário. O provedor de identidade pode fornecer métodos de autenticação adicionais, como a autenticação baseada em cartão inteligente. Para saber mais, confira [Escolhendo o método de autenticação correto para sua solução de identidade híbrida do Azure Active Directory](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).

Depois de determinar sua solução de identidade híbrida, baixe e execute a [Ferramenta de Correção de Erros de Sincronização de Diretórios IdFix](https://www.microsoft.com/download/details.aspx?id=36832) para verificar se seu Windows Server AD tem problemas.

Depois de resolver todos os problemas identificados pela ferramenta IdFix, confira [Implementar a sincronização de hash de senha](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) para obter instruções sobre como instalar a ferramenta Azure AD Connect e configurar a sincronização de diretórios entre o Windows Server AD local e o locatário do Azure AD para suas assinaturas do Office 365 e do EMS. Depois que a sincronização for iniciada, você manterá suas contas de usuários e grupos com seu provedor de identidade local, como o Windows Server AD.

A Microsoft fornece um conjunto de recomendações para [acesso de dispositivo e identidade](microsoft-365-policies-configurations.md) para garantir uma força de trabalho segura e produtiva. 
- Para obter os requisitos recomendados para ambientes híbridos, confira a coluna **Active Directory com sincronização de hash de senha** em [pré-requisitos](identity-access-prerequisites.md#prerequisites). 

- Para obter requisitos recomendados para ambientes somente de nuvem, confira a coluna **Somente de nuvem** em [pré-requisitos](identity-access-prerequisites.md#prerequisites).

|||
|:-------|:-----|
|![Guias de laboratório de teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia de laboratório de teste: Sincronização de hash de senha](password-hash-sync-m365-ent-test-environment.md)<br> [Guia de laboratório de teste: Autenticação passagem](pass-through-auth-m365-ent-test-environment.md) |
|||

Como ponto de verificação provisório, você pode consultar os [critérios de saída](identity-exit-criteria.md#crit-identity-sync) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step8.png)| [Monitorar integridades de sincronização](identity-azure-ad-connect-health.md) |

