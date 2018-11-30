---
title: 'Etapa 6: Proteger contra o comprometimento de credenciais'
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
description: Entender e configurar a Azure AD Identity Protection.
ms.openlocfilehash: b1dea9d2917c45bf87bd972f56c9eac2b074c252
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865323"
---
# <a name="step-6-protect-against-credential-compromise"></a>Etapa 6: Proteger contra o comprometimento de credenciais

*Esta etapa é opcional e aplica-se apenas à versão E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Nesta etapa, você vai aprender a configurar as políticas de proteção contra o comprometimento de credenciais, que ocorre quando um invasor determina o nome de conta do usuário e a senha para ter acesso aos serviços de nuvem e dados da organização. A Azure AD Identity Protection fornece várias maneiras de ajudar a impedir que um invasor percorra todas as suas contas e grupos e posteriormente acesse seus dados mais importantes.

Com a Azure AD Identity Protection, você pode:

|||
|:---------|:---------|
|Determinar e administrar possíveis vulnerabilidades nas identidades da organização|O Azure AD utiliza o aprendizado de máquina para detectar anomalias e atividades suspeitas, como atividades de entrada e pós-entrada. Usando esses dados, a Proteção de Identidade gera relatórios e alertas que lhe ajudarão a avaliar os problemas e a tomar as medidas necessárias.|
|Detectar ações suspeitas relacionadas às identidades da organização e responder a essas suspeitas automaticamente|Você pode configurar as políticas baseadas em risco que são acionadas automaticamente para detectar problemas quando um nível de risco específico é atingido. Essas políticas, além de outros controles de acesso condicional fornecidos pelo Azure Active Directory e pelo Enterprise Mobility + Security EMS (), podem bloquear automaticamente o acesso ou realizar ações corretivas, incluindo a redefinição de senha e exigindo a autenticação multifator para entradas subsequentes.|
|Investigar incidentes suspeitos e resolvê-los com medidas administrativas|Você pode investigar eventos de risco usando informações sobre o incidente de segurança. Fluxos básicos de trabalho estão disponíveis para controlar investigações e iniciar ações de correção, como a redefinição de senhas.|

Consulte mais [informações sobre a Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).

Consulte as [etapas para habilitar a Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).

Os resultados desta etapa incluem a habilitação da Azure AD Identity Protection e o uso dessa para:

- Solucionar possíveis vulnerabilidades de identidade.
- Detectar possíveis tentativas de ataque à credencial.
- Investigar e resolver incidentes suspeitos e contínuos relacionados a questões de identidade.

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do Laboratório de Teste: Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

Como ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-ident-prot) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [Sincronizar diretórios](identity-azure-ad-connect.md) |


