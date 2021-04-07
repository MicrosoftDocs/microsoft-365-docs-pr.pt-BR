---
title: Políticas recomendadas do Teams - Microsoft 365 para empresas | Microsoft Docs
description: Descreve as políticas para recomendações da Microsoft sobre como proteger a comunicação e o acesso a arquivos do Teams.
author: MicrosoftHeidi
manager: serdars
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 09/30/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 52e6709d18bd5ecbc91755a6c0e7be336d346f0c
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599598"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Recomendações de política para proteger chats, grupos e arquivos do Teams

Este artigo descreve como implementar as políticas recomendadas de identidade e acesso a dispositivos para proteger chats, grupos e conteúdos do Microsoft Teams, como arquivos e calendários. Essa orientação se baseia nas políticas comuns de identidade e acesso [a](identity-access-policies.md)dispositivos , com informações adicionais específicas do Teams. Como o Teams se integra com nossos outros produtos, consulte Também recomendações de política para proteger sites e arquivos do [SharePoint](sharepoint-file-access-policies.md) e recomendações de política para proteger [emails.](secure-email-recommended-policies.md)

Essas recomendações se baseiam em três camadas diferentes de segurança e proteção para o Teams que podem ser aplicadas com base na granularidade de suas necessidades: linha de base, sensível e altamente regulamentada. Você pode saber mais sobre essas camadas de segurança e as políticas recomendadas referenciadas por essas recomendações nas configurações de identidade e acesso [a dispositivos.](microsoft-365-policies-configurations.md)

Mais recomendações específicas para a implantação do Teams estão incluídas neste artigo para abranger circunstâncias de autenticação específicas, inclusive para usuários fora da sua organização. Você precisará seguir essas diretrizes para uma experiência de segurança completa.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>Começar com o Teams antes de outros serviços dependentes

Você não precisa habilitar serviços dependentes para começar com o Microsoft Teams. Esses serviços "funcionarão apenas". No entanto, você precisa estar preparado para gerenciar os seguintes elementos relacionados ao serviço:

- Grupos do Microsoft 365
- Sites de equipe do SharePoint
- OneDrive for Business
- Caixas de correio do Exchange
- Transmitir vídeos e planos do Planner (se esses serviços estão habilitados)

## <a name="updating-common-policies-to-include-teams"></a>Atualizando políticas comuns para incluir o Teams

Para proteger o chat, grupos e conteúdo no Teams, o diagrama a seguir ilustra quais políticas atualizar das políticas comuns de identidade e acesso a dispositivos. Para que cada política seja atualizada, certifique-se de que o Teams e os serviços dependentes sejam incluídos na atribuição de aplicativos de nuvem.

[![Resumo das atualizações de política para proteger o acesso ao Teams e seus serviços dependentes](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

Esses serviços são os serviços dependentes a incluir na atribuição de aplicativos de nuvem para o Teams:

- Microsoft Teams
- SharePoint e OneDrive for Business
- Exchange Online
- Skype for Business Online
- Microsoft Stream (gravações de reunião)
- Microsoft Planner (tarefas do Planner e planejar dados)

Esta tabela lista as políticas que precisam ser revisitadas e links para cada política nas políticas comuns de identidade e acesso a [dispositivos](identity-access-policies.md), que tem a política mais ampla definida para todos os aplicativos do Office.

|Nível de Proteção|Políticas|Mais informações sobre a implementação do Teams|
|---|---|---|
|**Baseline**|[Exigir MFA quando o risco de entrar é *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Certifique-se de que o Teams e os serviços dependentes estão incluídos na lista de aplicativos. O Teams também tem regras de Acesso para Convidados e Acesso Externo a considerar, você aprenderá mais sobre essas regras mais adiante neste artigo.|
||[Bloquear clientes sem suporte para a autenticação moderna](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Inclua o Teams e os serviços dependentes na atribuição de aplicativos de nuvem.|
||[Usuários de alto risco devem alterar a senha](identity-access-policies.md#high-risk-users-must-change-password)|Força os usuários do Teams a alterar sua senha ao entrar se a atividade de alto risco for detectada para sua conta. Certifique-se de que o Teams e os serviços dependentes estão incluídos na lista de aplicativos.|
||[Aplicar políticas de proteção de dados do APP](identity-access-policies.md#apply-app-data-protection-policies)|Certifique-se de que o Teams e os serviços dependentes estão incluídos na lista de aplicativos. Atualize a política para cada plataforma (iOS, Android, Windows).|
||[Definir políticas de conformidade de dispositivo](identity-access-policies.md#define-device-compliance-policies)|Inclua o Teams e os serviços dependentes nesta política.|
||[Exigir PCs compatíveis](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Inclua o Teams e os serviços dependentes nesta política.|
|**Confidencial**|[Exigir MFA quando o risco de entrar é *baixo,* *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|O Teams também tem regras de Acesso para Convidados e Acesso Externo a considerar, você aprenderá mais sobre essas regras mais adiante neste artigo. Inclua o Teams e os serviços dependentes nesta política.|
||[Exigir PCs e *dispositivos* móveis compatíveis](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Inclua o Teams e os serviços dependentes nesta política.|
|**Altamente controlado**|[*Sempre* exigir MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Independentemente da identidade do usuário, o MFA será usado pela sua organização. Inclua o Teams e os serviços dependentes nesta política. |
|

## <a name="teams-dependent-services-architecture"></a>Arquitetura de serviços dependentes do Teams

Para referência, o diagrama a seguir ilustra os serviços nos quais o Teams depende. Para obter mais informações e ilustrações, consulte [Microsoft Teams and related productivity services in Microsoft 365 for IT architects](../../solutions/productivity-illustrations.md).

[![Diagrama mostrando as dependências do Teams no SharePoint, no OneDrive for Business e no Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[Consulte uma versão maior dessa imagem](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>Acesso convidado e externo para o Teams

O Microsoft Teams define os seguintes tipos de acesso:

-  O acesso de convidados usa uma conta B2B do Azure AD para um usuário convidado ou externo que pode ser adicionado como membro de uma equipe e tem todo o acesso autorizado à comunicação e aos recursos da equipe.

- **O acesso** externo é para um usuário externo que não tem uma conta B2B do Azure AD. O acesso externo pode incluir convites e participação em chamadas, chats e reuniões, mas não inclui a associação à equipe e o acesso aos recursos da equipe.

As políticas de Acesso Condicional só se aplicam ao acesso de convidados no Teams porque há uma conta do Azure AD B2B correspondente.

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

Para políticas recomendadas para permitir acesso a usuários convidados e externos com uma conta B2B do Azure AD, consulte Policies for allow guest and [external B2B account access](identity-access-policies-guest-access.md).

### <a name="guest-access-in-teams"></a>Acesso de convidado ao Teams

Além das políticas para usuários internos da sua empresa ou organização, os administradores podem permitir que o acesso de convidados, em uma base de usuário por usuário, as pessoas externas à sua empresa ou organização acessem recursos do Teams e interajam com pessoas internas para coisas como conversas de grupo, chat e reuniões.

Para obter mais informações sobre o acesso de convidados e como implementá-lo, consulte [Acesso de convidados do Teams.](/microsoftteams/guest-access)

### <a name="external-access-in-teams"></a>Acesso externo no Teams

Às vezes, o acesso externo é confundido com o acesso de convidados, portanto, é importante deixar claro que esses dois mecanismos de acesso não internos são tipos diferentes de acesso.

O acesso externo é uma maneira de os usuários do Teams de um domínio externo inteiro encontrar, chamar, conversar e configurar reuniões com seus usuários no Teams. Os administradores do Teams configuram o acesso externo no nível da organização. Para obter mais informações, consulte [Gerenciar acesso externo no Microsoft Teams](/microsoftteams/manage-external-access).

Os usuários de acesso externo têm menos acesso e funcionalidade do que um indivíduo que foi adicionado por meio do acesso de convidados. Por exemplo, os usuários de acesso externo podem conversar com seus usuários internos com o Teams, mas não podem acessar canais de equipe, arquivos ou outros recursos.

O acesso externo não usa contas de usuário do Azure AD B2B e, portanto, não usa políticas de Acesso Condicional.

## <a name="teams-policies"></a>Políticas do Teams

Fora das políticas comuns listadas acima, há políticas específicas do Teams que podem e devem ser configuradas para gerenciar várias funcionalidades do Teams.

### <a name="teams-and-channels-policies"></a>Políticas de equipes e canais

As equipes e canais são dois elementos comumente usados no Microsoft Teams, e há políticas que você pode colocar em prática para controlar o que os usuários podem ou não fazer ao usar equipes e canais. Embora você possa criar uma equipe global, se sua organização tiver 5.000 usuários ou menos, provavelmente será útil ter equipes e canais menores para fins específicos, em linha com suas necessidades organizacionais.

Alterar a política padrão ou criar políticas personalizadas seria recomendável e você pode saber mais sobre como gerenciar suas políticas neste link: Gerenciar políticas de equipe [no Microsoft Teams](/microsoftteams/teams-policies).

### <a name="messaging-policies"></a>Políticas de mensagens

As mensagens ou o chat também podem ser gerenciados por meio da política global padrão ou por meio de políticas personalizadas, e isso pode ajudar os usuários a se comunicarem entre si de forma apropriada para sua organização. Essas informações podem ser revisadas em [Managing messaging policies in Teams](/microsoftteams/messaging-policies-in-teams).

### <a name="meeting-policies"></a>Políticas de reunião

Nenhuma discussão sobre o Teams seria concluída sem o planejamento e a implementação de políticas em torno das reuniões do Teams. As reuniões são um componente essencial do Teams, permitindo que as pessoas se reúnem formalmente e apresentem a muitos usuários ao mesmo tempo e compartilhem conteúdo relevante para a reunião. Definir as políticas corretas para sua organização em torno de reuniões é essencial.

Para obter mais informações, revise [Gerenciar políticas de reunião no Teams](/microsoftteams/meeting-policies-in-teams).

### <a name="app-permission-policies"></a>Políticas de permissão de aplicativo

O Teams também permite que você use aplicativos em vários locais, como canais ou chats pessoais. Ter políticas em torno de quais aplicativos podem ser adicionados e usados e onde é essencial para manter um ambiente rico em conteúdo que também é seguro.

Para saber mais sobre Políticas de Permissão de Aplicativo, confira Gerenciar políticas [de permissão de aplicativo no Microsoft Teams](/microsoftteams/teams-app-permission-policies).

## <a name="next-steps"></a>Próximas etapas

![Etapa 4: Políticas para aplicativos de nuvem do Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configurar políticas de Acesso Condicional para:

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)