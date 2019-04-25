---
title: 'Etapa 1: Planeje para usuários e grupos'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Planeje para o conjunto de usuários e grupos que trabalharão para sua organização.
ms.openlocfilehash: f8b3df73518e33c7750c0b72b2cb9f36bc8e9745
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283780"
---
# <a name="step-1-plan-for-users-and-groups"></a>Etapa 1: Planeje para usuários e grupos

*Esta etapa é obrigatória e se aplica para as versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Nesta etapa, você criará sua infraestrutura de identidade que combina usuários, grupos e associações a grupos com recursos de segurança na configuração correta. Isso permite que você:

- Mantenha o controle sobre quem tem acesso aos recursos em seu ambiente.
- Proteja o acesso com controles que garantem a identidade (os usuários são quem dizem ser) e o acesso de dispositivos seguros.
- Provisione recursos em seu ambiente com permissões apropriadas para reduzir o potencial para danos e vazamento de dados. 
- Monitore o seu ambiente para identificar comportamentos de usuários anômalos e automaticamente tomar medidas.

## <a name="plan-your-primary-identity-provider"></a>Planejar seu provedor de identidade principal

Para criar sua infraestrutura de identidade, você designará um provedor de identidade principal. Esse serviço armazena contas de usuário e seus atributos, grupos e seus membros e oferece suporte para sua administração contínua.

Quando sua organização adotar o Microsoft 365 Enterprise, seu provedor de identidade principal será:

- **Serviços de Domínio do Active Directory (AD DS)**, um provedor de identidade intranet hospedado em computadores que executam o Windows Server. Ele normalmente é usado por empresas que têm um provedor de identidade local existente.
- **Azure Active Directory (Azure AD)**, uma identidade como um serviço baseada em nuvem (IDaaS) que oferece uma ampla variedade de recursos para gerenciar e proteger o seu ambiente. Ele normalmente é usado por empresas que não têm uma infraestrutura local existente.

Se sua organização tiver um provedor de identidade local existente, você deverá sincronizar suas contas e grupos de usuários dos Serviços de Domínio do Active Directory (AD DS) para o Azure AD para fornecer acesso mais eficaz aos serviços baseados na nuvem do Microsoft 365 Enterprise.  Você também pode usar o Azure AD para criar e gerenciar grupos que existam somente na nuvem da Microsoft.

Quando você tiver seus usuários e grupos no Azure AD, você poderá:

- Gerenciar todas as contas do Azure AD para todos os aplicativos de nuvem. 
- Usar o mesmo conjunto de controles para proteger o acesso a aplicativos em seu ambiente.
- Colaborar com parceiros externos.
- Monitorar comportamentos de contas anômalos, como tentativas suspeitas de login, e tomar medidas automaticamente.

Siga as instruções nas próximas duas seções para planejar e implementar suas contas e grupos de usuários.

## <a name="categorize-your-users"></a>Categorizar seus usuários
Os usuários em organizações podem ser categorizados de várias maneiras. Por exemplo, alguns são funcionários e têm status permanente. Alguns são fornecedores, prestadores de serviços ou parceiros que têm status temporário. Alguns são usuários externos que não têm contas de usuário, mas que ainda devem ter acesso a recursos e serviços específicos para permitir a interação e colaboração. Por exemplo:

- As contas do locatário representam os usuários em sua organização para os quais você atribui uma licença para os serviços de nuvem
- As contas entre empresas (B2B) representam usuários de fora da sua organização que você convida para colaborar

Analise os tipos de usuários em sua organização. Quais são os grupos? Por exemplo, você pode agrupar usuários por função ou propósito geral em sua organização.

Além disso, alguns serviços de nuvem podem ser compartilhados com usuários de fora de sua organização que não tenham contas de usuário. Você também precisará identificar esses grupos de usuários.

## <a name="plan-for-ad-ds-and-azure-ad-groups"></a>Planejar grupos do AD DS e Azure AD.

Você pode usar grupos no Azure AD para várias finalidades que simplifiquem o gerenciamento de seu ambiente de nuvem. Por exemplo, para grupos do Azure AD, você pode:

- Usar o licenciamento baseado em grupo para atribuir licenças do Office 365 e do Enterprise Mobility + Security (EMS) às suas contas de usuário automaticamente assim que elas forem adicionadas ao Azure AD ou sincronizadas do AD DS. 
- Adicionar contas de usuário para grupos específicos de forma dinâmica com base em atributos das contas de usuário, como o departamento.  
- Provisionar usuários automaticamente para aplicativos de Software como um Serviço (SaaS) e para proteger o acesso a esses aplicativos com a autenticação multifator e outras regras de acesso condicional.
- Configurar permissões e níveis de acesso para sites de equipe do SharePoint Online. Grupos do Azure AD também podem ser usados com as políticas de Proteção de Informações do Azure com escopo para proteger os arquivos com criptografia e permissões. 

## <a name="results"></a>Resultados

Ao concluir esta etapa, você terá:

- Uma lista de contas de usuário no Azure AD que correspondem aos funcionários da sua organização e aos fornecedores, prestadores de serviços e parceiros externos que trabalham para ou com a sua organização.
- Um conjunto de grupos e seus membros no Azure AD que refletem conjuntos lógicos de contas de usuário e outros grupos para o provisionamento automático de licenciamento para as configurações de segurança para os serviços de nuvem da Microsoft.

Como um ponto de verificação provisório, é possível ver os [critérios de saída](identity-exit-criteria.md#crit-identity-user-groups) para esta etapa.

Quando seus usuários e grupos do Azure AD forem criados, você poderá começar a atribuir licenças e a usar o Exchange Online. Para implantar o Exchange Online para os seus usuários, confira [Implantar o Exchange Online para o Microsoft 365 Enterprise](exchangeonline-workload.md).

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [Proteger suas identidades privilegiadas](identity-designate-protect-admin-accounts.md) |

