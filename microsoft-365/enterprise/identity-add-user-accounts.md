---
title: 'Fase 4: adicionar suas contas de usuário'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Adicione contas de usuários e grupos diretamente na nuvem ou sincronizando-as com o diretório local.
ms.openlocfilehash: 2a54044737f5b924bd619d5a6c7c72091dc7a0d1
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005829"
---
# <a name="step-4-add-your-user-accounts"></a>Fase 4: adicionar suas contas de usuário

![Fase 2 – Identidade](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-cloud-only"></a>
## <a name="create-your-user-accounts-for-cloud-only-identity"></a>Criar contas de usuário para identidade somente na nuvem

Para identidade somente na nuvem, crie seus usuários e grupos no Azure AD (Azure Active Directory). Você pode usar:

- O Centro de administração do Microsoft 365
- O Portal do Azure
- Azure PowerShell

<a name="identity-sync"></a>
## <a name="synchronize-identities-for-hybrid-identity"></a>Sincronizar identidades para identidade híbrida

*Isso é obrigatório para ambientes híbridos e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

Nesta seção, você sincronizará seus Serviços de Domínio do Active Directory (AD DS) local com o locatário do Azure AD usado pelo Office 365, Microsoft Intune e outros serviços baseados em nuvem incluídos no Microsoft 365 Enterprise.

O Azure AD Connect é a ferramenta da Microsoft com suporte que guia você pela sincronização somente das identidades que você realmente precisa de ambientes AD DS de floresta única ou de várias florestas para o seu locatário do Azure AD. A figura a seguir mostra o processo básico para a sincronização do Azure AD Connect.

![Como o Azure AD Connect sincroniza seu diretório local ao Azure AD](../media/identity-add-user-accounts/azure-ad-connect.png)

1. O Azure AD Connect em execução em um servidor sonda o AD DS para mudanças em contas, grupos e contatos.
2. O Azure AD Connect envia essas mudanças para o locatário do Azure AD para a sua assinatura do Microsoft 365.

A primeira decisão em sua solução de identidade híbrida é o requisito de autenticação. As alternativas a seguir são opções:

- Com a **autenticação gerenciada**, o Azure AD lida com o processo de autenticação do login do usuário. Há dois métodos de autenticação gerenciada: 
    - **Sincronização de hash de senha (PHS)** [Recomendado e obrigatório para alguns recursos premium]. Esta é a forma mais simples de habilitar a autenticação para objetos de diretório locais no Azure AD. O Azure AD Connect extrai a senha especificada como hash do AD DS, realiza o processamento de segurança adicional no hash de senha e a sincroniza com o Azure AD. Para obter mais informações, consulte [Implementar a sincronização de senha com a sincronização do Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).
    - A **Autenticação de passagem (PTA)** fornece uma solução de validação de senha simples para os serviços baseados no Azure AD. PTA usa um agente em execução em um ou mais servidores locais para validar as autenticações de usuário diretamente com seu AD DS local. Para saber mais, confira [Entrada do usuário com autenticação de passagem do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).
- Com a **autenticação federada**, o processo de autenticação é redirecionado para outro provedor de identidade por meio de um servidor de federação de identidade, como os Serviços de Federação do Active Directory (AD FS) para o login de um usuário. O provedor de identidade pode fornecer métodos de autenticação adicionais, como a autenticação baseada em cartão inteligente. Para saber mais, confira [Escolhendo o método de autenticação correto para sua solução de identidade híbrida do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn).

Assista a este vídeo para ter uma visão geral dos modelos de identidade e autenticação do Microsoft 365 Enterprise.

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

Depois que você tiver determinado sua solução de identidade híbrida, baixe e execute a [Ferramenta de Correção de Erros de Sincronização do Diretório da IdFix](https://www.microsoft.com/download/details.aspx?id=36832) para analisar seu AD DS para problemas.

Depois de resolver todos os problemas identificados pela ferramenta IdFix, confira [Implementar a sincronização da senha hash](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization)para obter instruções sobre como instalar a ferramenta Azure AD Connect e configurar a sincronização de diretórios entre o seu AD DS local e o locatário Azure AD para as suas assinaturas do Microsoft 365. Depois que a sincronização começar, você deve manter suas contas e grupos de usuário com seu provedor de identidade local, como o AD DS.

A Microsoft fornece um conjunto de recomendações para [acesso de dispositivo e identidade](microsoft-365-policies-configurations.md) para garantir uma força de trabalho segura e produtiva. 

- Para obter os requisitos recomendados para ambientes híbridos, confira a coluna **Active Directory com sincronização de hash de senha** em [pré-requisitos](identity-access-prerequisites.md#prerequisites). 

- Para obter requisitos recomendados para ambientes somente de nuvem, confira a coluna **Somente de nuvem** em [pré-requisitos](identity-access-prerequisites.md#prerequisites).

Quando seus usuários e grupos locais estiverem no Azure AD, você poderá começar a atribuir licenças e a usar cargas de trabalho de produtividade como o OneDrive for Business e o Exchange Online.

|||
|:-------|:-----|
|![Guias de laboratório de teste da Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia de laboratório de teste: Sincronização de hash de senha](password-hash-sync-m365-ent-test-environment.md)<br> [Guia de laboratório de teste: Autenticação passagem](pass-through-auth-m365-ent-test-environment.md) |
|||

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-sync) correspondentes a esta seção.

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a>Monitorar a integridade da sincronização

*Isso é opcional e se aplica tanto à versão E3 quanto à versão E5 do Microsoft 365* 

Nesta seção, você instalará um agente do Azure AD Connect Health em cada um dos seus controladores de domínio AD DS locais para monitorar sua infraestrutura de identidade e os serviços de sincronização fornecidos pelo Azure AD Connect. As informações de monitoramento são disponibilizadas em um portal do Azure AD Connect Health, onde você pode ver alertas, monitoramento de desempenho, análise de uso e outras informações.

![Componentes do Azure AD Connect Health](../media/identity-add-user-accounts/identity-azure-ad-connect-health.png)

A decisão da estrutura principal de como usar o Azure AD Connect Health baseia-se em como o Azure AD Connect está sendo usado:

- Se você estiver usando a opção de **autenticação gerenciada**, comece [usando o Azure AD Connect Health com a sincronização](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) para entender e configurar o Azure AD Connect Health.
- Se você estiver sincronizando apenas os nomes das contas e dos grupos usando a **autenticação federada** com os Serviços de Federação do Active Directory (AD FS), comece [usando o Azure AD Connect Health com os AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) para entender e configurar o Azure AD Connect Health.

Quando você completar esta seção, você:

- Terá instalado o agente do Azure AD Connect Health nos servidores do provedor de identidade local.
- Poderá ver, no portal do Azure AD Connect Health, o estado atual de sua infraestrutura local e das atividades de sincronização com o locatário do Azure AD para suas assinaturas do Microsoft 365.

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-sync-health) desta seção.



<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a>Simplificar as atualizações de senha

*Isso é opcional para ambientes híbridos e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

Nesta seção, você permitirá que os usuários redefinam suas senhas através do Azure Active Directory (Azure AD) que depois é replicada para os seus serviços locais de domínio do Active Directory (AD DS). Este processo é conhecido como write-back de senha. Com o write-back de senha, os usuários não precisam atualizar suas senhas através dos serviços locais de domínio do AD DS, onde as contas de usuário e seus atributos são armazenados. Isso é valioso para usuários móveis ou remotos que não têm uma conexão de acesso remoto à rede local.

O write-back de senha é necessário para o uso por completo das capacidades de Proteção de Identidade do Azure AD, por exemplo para exigir que os usuários alterem a senha local quando for detectado um alto risco de comprometimento da conta.

Para obter mais informações e instruções de configuração, consulte o artigo sobre o [Azure AD SSPR com o write-back de senha](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).

>[!Note]
>Atualize para a versão mais recente do Azure AD Connect a fim de garantir a melhor experiência possível e o acesso a novos recursos à medida que são lançados. Para saber mais, consulte as informações sobre a [instalação personalizada do Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

|||
|:-------|:-----|
|![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia de laboratório de teste: write-back de senha](password-writeback-m365-ent-test-environment.md) |
|||

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-pw-writeback) desta seção.

|||
|:-------|:-----|
|![Etapa 5](../media/stepnumbers/Step5.png)| [Usar grupos de gerenciamento](identity-use-group-management.md) |
