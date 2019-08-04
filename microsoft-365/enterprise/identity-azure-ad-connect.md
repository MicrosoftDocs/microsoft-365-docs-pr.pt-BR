---
title: 'Etapa 3: Configurar identidade híbrida'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda as opções de identidade e configure o Azure AD Connect para sincronizar seus Serviços de Domínio do Active Directory locais com Azure AD.
ms.openlocfilehash: 0b494047f984d9fd830e840d2d1f4fafa06fe8ab
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073821"
---
# <a name="step-3-configure-hybrid-identity"></a>Etapa 3: Configurar identidade híbrida

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-sync"></a>
## <a name="synchronize-identities"></a>Sincronizar as identidades

*Isso é obrigatório para ambientes híbridos e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

Nesta seção, você sincronizará seus Serviços de Domínio do Active Directory local (AD DS) com o locatário do Azure Active Directory (Azure AD) usado pelas suas assinaturas do Office 365 e Enterprise Mobility + Security (EMS).

O Azure AD Connect é a ferramenta da Microsoft com suporte que guia você pela sincronização somente das identidades que você realmente precisa de ambientes AD DS de floresta única ou de várias florestas para o seu locatário do Azure AD. A figura a seguir mostra o processo básico para a sincronização do Azure AD Connect.

![Como o Azure AD Connect sincroniza seu diretório local ao Azure AD](./media/identity-azure-ad-connect/azure-ad-connect.png)

1. O Azure AD Connect em execução em um servidor sonda o AD DS para mudanças em contas, grupos e contatos.
2. O Azure AD Connect envia essas mudanças para o locatário do Azure AD para a sua assinatura do Microsoft 365.

A primeira decisão em sua solução de identidade híbrida é o requisito de autenticação. As alternativas a seguir são opções:

- Com a **autenticação gerenciada**, o Azure AD lida com o processo de autenticação do login do usuário. Há dois métodos de autenticação gerenciada: 
    - **Sincronização de hash de senha (PHS)** [Recomendado e obrigatório para alguns recursos premium]. Esta é a forma mais simples de habilitar a autenticação para objetos de diretório locais no Azure AD. O Azure AD Connect extrai a senha especificada como hash do AD DS, realiza o processamento de segurança adicional na senha e a salva no Azure AD. Para obter mais informações, consulte [Implementar a sincronização de senha com a sincronização do Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).
    - A **Autenticação de passagem (PTA)** fornece uma solução de validação de senha simples para os serviços baseados no Azure AD. PTA usa um agente em execução em um ou mais servidores locais para validar as autenticações de usuário diretamente com seu AD DS local. Para saber mais, confira [Entrada do usuário com autenticação de passagem do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).
- Com a **autenticação federada**, o processo de autenticação é redirecionado para outro provedor de identidade por meio de um servidor de federação de identidade, como os Serviços de Federação do Active Directory (AD FS) para o login de um usuário. O provedor de identidade pode fornecer métodos de autenticação adicionais, como a autenticação baseada em cartão inteligente. Para saber mais, confira [Escolhendo o método de autenticação correto para sua solução de identidade híbrida do Azure Active Directory](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).

Depois que você tiver determinado sua solução de identidade híbrida, baixe e execute a [Ferramenta de Correção de Erros de Sincronização do Diretório da IdFix](https://www.microsoft.com/download/details.aspx?id=36832) para analisar seu AD DS para problemas.

Depois de resolver todos os problemas identificados pela ferramenta IdFix, confira [Implementar a sincronização da senha hash](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization)para obter instruções sobre como instalar a ferramenta Azure AD Connect e configurar a sincronização de diretórios entre o seu AD DS local e o locatário Azure AD para as suas assinaturas do Office 365 e EMS. Depois que a sincronização começar, você deve manter suas contas e grupos de usuário com seu provedor de identidade local, como o AD DS.

A Microsoft fornece um conjunto de recomendações para [acesso de dispositivo e identidade](microsoft-365-policies-configurations.md) para garantir uma força de trabalho segura e produtiva. 

- Para obter os requisitos recomendados para ambientes híbridos, confira a coluna **Active Directory com sincronização de hash de senha** em [pré-requisitos](identity-access-prerequisites.md#prerequisites). 

- Para obter requisitos recomendados para ambientes somente de nuvem, confira a coluna **Somente de nuvem** em [pré-requisitos](identity-access-prerequisites.md#prerequisites).

Quando seus usuários e grupos locais estiverem no Azure AD, você pode começar a atribuir licenças e a usar o Exchange Online. Para implantar o Exchange Online para os seus usuários e migrar caixas de correio locais, confira [Implantar o Exchange Online para Microsoft 365 Enterprise](exchangeonline-workload.md).

|||
|:-------|:-----|
|![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia de laboratório de teste: Sincronização de hash de senha](password-hash-sync-m365-ent-test-environment.md)<br> [Guia de laboratório de teste: Autenticação passagem](pass-through-auth-m365-ent-test-environment.md) |
|||

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-sync) correspondentes a esta seção.

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a>Monitorar a integridade da sincronização

*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

Nesta seção, você instalará um agente do Azure AD Connect Health em cada um dos seus servidores locais de identidade para monitorar sua infraestrutura de identidade e os serviços de sincronização fornecidos pelo Azure AD Connect. As informações de monitoramento são disponibilizadas em um portal do Azure AD Connect Health, onde você pode ver alertas, monitoramento de desempenho, análise de uso e outras informações.

![Componentes do Azure AD Connect Health](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

A decisão da estrutura principal de como usar o Azure AD Connect Health baseia-se em como o Azure AD Connect está sendo usado:

- Se você estiver usando a opção de **autenticação gerenciada**, comece [usando o Azure AD Connect Health com a sincronização](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) para entender e configurar o Azure AD Connect Health.
- Se você estiver sincronizando apenas os nomes das contas e dos grupos usando a **autenticação federada** com os Serviços de Federação do Active Directory (AD FS), comece [usando o Azure AD Connect Health com os AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) para entender e configurar o Azure AD Connect Health.

Quando você completar esta seção, você:

- Terá instalado o agente do Azure AD Connect Health nos servidores do provedor de identidade local.
- Poderá ver, no portal do Azure AD Connect Health, o estado atual de sua infraestrutura local e das atividades de sincronização com o locatário do Azure AD para suas assinaturas do Office 365 e EMS.

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-sync-health) para esta seção.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
![](./media/stepnumbers/Step4.png)| [Configurar autenticação de usuário segura](identity-multi-factor-authentication.md)
