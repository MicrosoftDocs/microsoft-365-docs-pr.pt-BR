---
title: Políticas Teams recomendadas - Microsoft 365 para empresas | Microsoft Docs
description: Descreve as políticas para recomendações da Microsoft sobre como proteger Teams comunicação e acesso a arquivos.
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
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Recomendações de política para proteger Teams chats, grupos e arquivos

Este artigo descreve como implementar as políticas recomendadas de identidade e acesso a dispositivos para proteger Microsoft Teams chats, grupos e conteúdo, como arquivos e calendários. Essa orientação se baseia nas políticas comuns de identidade e acesso a [dispositivos](identity-access-policies.md), com informações adicionais Teams específicas. Como Teams integra-se com nossos outros produtos, consulte Também recomendações de política para proteger SharePoint [sites](sharepoint-file-access-policies.md) e arquivos e recomendações de política para proteger [emails.](secure-email-recommended-policies.md)

Essas recomendações se baseiam em três camadas diferentes de segurança e proteção para Teams que podem ser aplicadas com base na granularidade de suas necessidades: linha de base, sensível e altamente regulamentada. Você pode saber mais sobre essas camadas de segurança e as políticas recomendadas referenciadas por essas recomendações nas configurações de identidade e acesso [a dispositivos.](microsoft-365-policies-configurations.md)

Mais recomendações específicas para Teams implantação estão incluídas neste artigo para abranger circunstâncias de autenticação específicas, inclusive para usuários fora da sua organização. Você precisará seguir essas diretrizes para uma experiência de segurança completa.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>Começar a Teams antes de outros serviços dependentes

Você não precisa habilitar serviços dependentes para começar a Microsoft Teams. Esses serviços "funcionarão apenas". No entanto, você precisa estar preparado para gerenciar os seguintes elementos relacionados ao serviço:

- Grupos do Microsoft 365
- Sites de equipe do SharePoint
- OneDrive for Business
- Caixas de correio do Exchange
- Transmitir vídeos e planos do Planner (se esses serviços estão habilitados)

## <a name="updating-common-policies-to-include-teams"></a>Atualizando políticas comuns para incluir Teams

Para proteger o chat, grupos e conteúdo no Teams, o diagrama a seguir ilustra quais políticas atualizar das políticas comuns de acesso a dispositivos e identidades. Para que cada política seja atualizada, certifique-se de que os serviços Teams e dependentes sejam incluídos na atribuição de aplicativos de nuvem.

[![Resumo das atualizações de política para proteger o acesso ao Teams e seus serviços dependentes](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

Esses serviços são os serviços dependentes a incluir na atribuição de aplicativos de nuvem para Teams:

- Microsoft Teams
- SharePoint e OneDrive for Business
- Exchange Online
- Skype for Business Online
- Microsoft Stream (gravações de reunião)
- Microsoft Planner (tarefas do Planner e planejar dados)

Esta tabela lista as políticas que precisam ser revisitadas e links para cada política nas políticas comuns de acesso a dispositivos e identidades [,](identity-access-policies.md)que tem a política mais ampla definida para todos os aplicativos Office.

|Nível de Proteção|Políticas|Mais informações para Teams implementação|
|---|---|---|
|**Baseline**|[Exigir MFA quando o risco de entrar é *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Certifique-se Teams e os serviços dependentes estão incluídos na lista de aplicativos. Teams regras de Acesso para Convidados e Acesso Externo a considerar também, você aprenderá mais sobre essas regras mais adiante neste artigo.|
||[Bloquear clientes sem suporte para a autenticação moderna](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Inclua Teams e serviços dependentes na atribuição de aplicativos de nuvem.|
||[Usuários de alto risco devem alterar a senha](identity-access-policies.md#high-risk-users-must-change-password)|Força Teams os usuários a alterarem sua senha ao entrar se a atividade de alto risco for detectada para sua conta. Certifique-se Teams e os serviços dependentes estão incluídos na lista de aplicativos.|
||[Aplicar políticas de proteção de dados do APP](identity-access-policies.md#apply-app-data-protection-policies)|Certifique-se Teams e os serviços dependentes estão incluídos na lista de aplicativos. Atualize a política para cada plataforma (iOS, Android, Windows).|
||[Definir políticas de conformidade de dispositivo](identity-access-policies.md#define-device-compliance-policies)|Inclua Teams e serviços dependentes nesta política.|
||[Exigir PCs compatíveis](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Inclua Teams e serviços dependentes nesta política.|
|**Confidencial**|[Exigir MFA quando o risco de entrar é *baixo,* *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams regras de Acesso para Convidados e Acesso Externo a considerar também, você aprenderá mais sobre essas regras mais adiante neste artigo. Inclua Teams e serviços dependentes nesta política.|
||[Exigir PCs e *dispositivos* móveis compatíveis](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Inclua Teams e serviços dependentes nesta política.|
|**Altamente controlado**|[*Sempre* exigir MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Independentemente da identidade do usuário, o MFA será usado pela sua organização. Inclua Teams e serviços dependentes nesta política. |
|

## <a name="teams-dependent-services-architecture"></a>Teams de serviços dependentes

Para referência, o diagrama a seguir ilustra os serviços Teams se baseia. Para obter mais informações e ilustrações, consulte Microsoft Teams e serviços de produtividade relacionados [Microsoft 365 para arquitetos de IT.](../../solutions/productivity-illustrations.md)

[![Diagrama mostrando Teams dependências de SharePoint, OneDrive for Business e Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[Consulte uma versão maior dessa imagem](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>Acesso de convidados e externos para Teams

Microsoft Teams define os seguintes tipos de acesso:

-  O acesso de convidados usa uma conta B2B do Azure AD para um usuário convidado ou externo que pode ser adicionado como membro de uma equipe e tem todo o acesso autorizado à comunicação e aos recursos da equipe.

- **O acesso** externo é para um usuário externo que não tem uma conta B2B do Azure AD. O acesso externo pode incluir convites e participação em chamadas, chats e reuniões, mas não inclui a associação à equipe e o acesso aos recursos da equipe.

As políticas de Acesso Condicional só se aplicam ao acesso de convidados Teams porque há uma conta do Azure AD B2B correspondente.

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

Para políticas recomendadas para permitir acesso a usuários convidados e externos com uma conta B2B do Azure AD, consulte Policies for allow guest and [external B2B account access](identity-access-policies-guest-access.md).

### <a name="guest-access-in-teams"></a>Acesso de convidado ao Teams

Além das políticas para usuários internos da sua empresa ou organização, os administradores podem permitir que o acesso de convidados, em uma base de usuário por usuário, as pessoas que são externas à sua empresa ou organização acessem recursos Teams e interajam com pessoas internas para coisas como conversas de grupo, chat e reuniões.

Para obter mais informações sobre o acesso de convidados e como implementá-lo, [consulte Teams acesso de convidados.](/microsoftteams/guest-access)

### <a name="external-access-in-teams"></a>Acesso externo no Teams

Às vezes, o acesso externo é confundido com o acesso de convidados, portanto, é importante deixar claro que esses dois mecanismos de acesso não internos são tipos diferentes de acesso.

O acesso externo é uma maneira Teams usuários de um domínio externo inteiro para encontrar, chamar, conversar e configurar reuniões com seus usuários em Teams. Teams os administradores configuram o acesso externo no nível da organização. Para obter mais informações, consulte [Manage external access in Microsoft Teams](/microsoftteams/manage-external-access).

Os usuários de acesso externo têm menos acesso e funcionalidade do que um indivíduo que foi adicionado por meio do acesso de convidados. Por exemplo, os usuários de acesso externo podem conversar com seus usuários internos com Teams, mas não podem acessar canais de equipe, arquivos ou outros recursos.

O acesso externo não usa contas de usuário do Azure AD B2B e, portanto, não usa políticas de Acesso Condicional.

## <a name="teams-policies"></a>Teams políticas

Fora das políticas comuns listadas acima, há Teams específicas que podem e devem ser configuradas para gerenciar várias funcionalidades Teams de segurança.

### <a name="teams-and-channels-policies"></a>Teams e políticas de canais

Teams e canais são dois elementos comumente usados no Microsoft Teams, e há políticas que você pode colocar em prática para controlar o que os usuários podem e não podem fazer ao usar equipes e canais. Embora você possa criar uma equipe global, se sua organização tiver 5.000 usuários ou menos, provavelmente será útil ter equipes e canais menores para fins específicos, em linha com suas necessidades organizacionais.

Alterar a política padrão ou criar políticas personalizadas seria recomendável e você pode saber mais sobre como gerenciar suas políticas neste link: [Gerenciar](/microsoftteams/teams-policies)políticas de equipes em Microsoft Teams .

### <a name="messaging-policies"></a>Política de mensagens

As mensagens ou o chat também podem ser gerenciados por meio da política global padrão ou por meio de políticas personalizadas, e isso pode ajudar os usuários a se comunicarem entre si de forma apropriada para sua organização. Essas informações podem ser revisadas em [Managing messaging policies in Teams](/microsoftteams/messaging-policies-in-teams).

### <a name="meeting-policies"></a>Políticas de reunião

Nenhuma discussão sobre Teams seria concluída sem o planejamento e a implementação de políticas em torno Teams reuniões. As reuniões são um componente essencial da Teams, permitindo que as pessoas se reúnem e apresentem formalmente a muitos usuários de uma só vez e compartilhem conteúdo relevante para a reunião. Definir as políticas corretas para sua organização em torno de reuniões é essencial.

Para obter mais informações, consulte [Gerenciar políticas de reunião em Teams](/microsoftteams/meeting-policies-in-teams).

### <a name="app-permission-policies"></a>Políticas de permissão do aplicativo

Teams também permite que você use aplicativos em vários locais, como canais ou chats pessoais. Ter políticas em torno de quais aplicativos podem ser adicionados e usados e onde é essencial para manter um ambiente rico em conteúdo que também é seguro.

Para saber mais sobre políticas de permissão de aplicativo, confira Gerenciar políticas de permissão de [aplicativo em Microsoft Teams](/microsoftteams/teams-app-permission-policies).

## <a name="next-steps"></a>Próximas etapas

![Etapa 4: Políticas para aplicativos Microsoft 365 nuvem](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configurar políticas de Acesso Condicional para:

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)