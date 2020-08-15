---
title: Políticas de equipe recomendadas-Microsoft 365 for Enterprise | Microsoft docs
description: Descreve as políticas para as recomendações da Microsoft sobre como proteger a comunicação de equipes e o acesso a arquivos.
author: MicrosoftHeidi
manager: serdars
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 10/31/2019
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 41ead64a7a94dcd5afb22a311d7637326949fc7c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685649"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Recomendações de política para proteger chats, grupos e arquivos de equipes

Este artigo descreve como implementar a identidade recomendada e as políticas de acesso a dispositivos para proteger bate-papos, grupos e conteúdo do Teams, como arquivos e calendários. Este guia baseia-se nas [políticas comuns de acesso de dispositivo e identidade](identity-access-policies.md), com informações adicionais específicas para equipes. Como as equipes se integram com nossos outros produtos, também Confira [recomendações de política para proteger sites e arquivos do SharePoint](sharepoint-file-access-policies.md) e [recomendações de política para proteger o email](secure-email-recommended-policies.md).

Essas recomendações são baseadas em três camadas diferentes de segurança e proteção para equipes que podem ser aplicadas com base na granularidade das suas necessidades: linha de base, confidencial e altamente regulamentada. Você pode saber mais sobre essas camadas de segurança e as políticas recomendadas referenciadas por essas recomendações nas [configurações de acesso de dispositivo e identidade](microsoft-365-policies-configurations.md).

Recomendações adicionais específicas para a implantação do teams estão incluídas neste artigo para abranger circunstâncias de autenticação específicas, incluindo para usuários fora da sua organização. Será necessário seguir estas orientações para uma experiência de segurança completa.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>Introdução ao Teams antes de outros serviços dependentes

Você não precisa habilitar os serviços dependentes para começar a usar o Microsoft Teams. Isso tudo funcionará. No entanto, você precisa estar preparado para gerenciar o seguinte:

- Grupos do Microsoft 365
- Sites de equipe do SharePoint
- OneDrive for Business
- Caixas de correio
- Transmitir vídeos e planos do Planner (se esses serviços estiverem habilitados)

## <a name="updating-common-policies-to-include-teams"></a>Atualizando políticas comuns para incluir o Microsoft Teams

O diagrama a seguir ilustra o conjunto de políticas recomendadas para proteger o chat, os grupos e o conteúdo no Microsoft Teams. O ícone de lápis indica quais políticas precisam ser revisitadas para garantir que as equipes e os serviços dependentes estejam incluídos na atribuição de aplicativos em nuvem.

![Um diagrama mostrando como usar o Microsoft Teams em vários dispositivos.](../media/identity-access-ruleset-teams.png)

Estes são os serviços dependentes a serem incluídos na atribuição de aplicativos de nuvem para o Teams:

- Microsoft Teams
- SharePoint Online e OneDrive for Business
- Exchange Online
- Skype for Business Online
- Microsoft Stream (gravações de reunião)
- Microsoft Planner (tarefas do Planner e planejar dados)

Esta tabela lista as políticas que precisam ser revisitadas e links para cada política em [políticas comuns de acesso de dispositivo e identidade](identity-access-policies.md), que tem o conjunto de regras mais amplo para todos os aplicativos do Office.

|Nível de Proteção|Políticas|Informações adicionais para implementação do teams|
|:---------------|:-------|:----------------|
|**Baseline**|[Exigir MFA quando o risco de entrada for *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Certifique-se de que as equipes e os serviços dependentes estão incluídos na lista de aplicativos. O Microsoft Teams tem acesso de convidado e regras de acesso externo para considerar também, você aprenderá mais sobre eles posteriormente neste artigo.|
|        |[Bloquear clientes sem suporte para a autenticação moderna](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Inclua equipes e serviços dependentes na atribuição de aplicativos em nuvem.|
|        |[Usuários de alto risco devem alterar a senha](identity-access-policies.md#high-risk-users-must-change-password)|Obriga os usuários do teams a alterarem suas senhas ao entrarem se uma atividade de alto risco for detectada para sua conta. Certifique-se de que as equipes e os serviços dependentes estão incluídos na lista de aplicativos.|
|        |[Aplicar políticas de proteção de dados do aplicativo](identity-access-policies.md#apply-app-data-protection-policies)|Certifique-se de que as equipes e os serviços dependentes estão incluídos na lista de aplicativos. Atualize a política para cada plataforma (iOS, Android, Windows).|
|        |[Exigir aplicativos aprovados e proteção de aplicativos](identity-access-policies.md#require-approved-apps-and-app-protection)|Inclua equipes e serviços dependentes nessa política.|
|        |[Definir políticas de conformidade do dispositivo](identity-access-policies.md#define-device-compliance-policies)|Inclua equipes e serviços dependentes nessa política.|
|        |[Exigir PCs compatíveis](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Inclua equipes e serviços dependentes nessa política.|
|**Confidencial**|[Exigir MFA quando o risco de entrada for *baixo*, *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|O Microsoft Teams tem acesso de convidado e regras de acesso externo para considerar também, você aprenderá mais sobre eles posteriormente neste artigo. Inclua equipes e serviços dependentes nessa política.|
|         |[Exigir computadores *em conformidade e* dispositivos móveis](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Inclua equipes e serviços dependentes nessa política.|
|**Altamente controlado**|[*Sempre* exigir MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Independentemente da identidade do usuário, a MFA será usada pela sua organização. Inclua equipes e serviços dependentes nessa política.
| | |

## <a name="teams-dependent-services-architecture"></a>Arquitetura de serviços dependentes do teams

Para referência, o diagrama a seguir ilustra a equipe de serviços que se baseia no. Para obter mais informações e ilustrações adicionais, consulte [Microsoft Teams e serviços de produtividade relacionados no microsoft 365 para arquitetos de ti](../solutions/productivity-illustrations.md).

![Diagrama mostrando dependências do teams no SharePoint Online, no OneDrive for Business e no Exchange.](../media/identity-access-logical-architecture-teams.png)

## <a name="enabling-guest-and-external-access-for-teams"></a>Habilitando o acesso externo e de convidados para o Teams

No Azure AD, os usuários convidados e externos são os mesmos. O tipo de usuário para ambos é Guest. Os usuários convidados são usuários B2B. O Microsoft Teams diferencia entre usuários convidados e usuários externos no aplicativo. Embora seja importante compreender como cada um deles é tratado no Microsoft Teams, os dois tipos de usuários são usuários B2B no Azure AD e as políticas recomendadas para usuários B2B se aplicam a ambos. Para obter as políticas recomendadas para permitir o acesso de convidados, confira [políticas para permitir o acesso B2B e de convidado externo](identity-access-policies-guest-access.md).

### <a name="guest-access-in-teams"></a>Acesso de convidados no Teams

Além das políticas para usuários internos à sua empresa ou organização, os administradores podem habilitar o acesso de convidados para permitir, em uma base de usuário por usuário, as pessoas que são externas à sua empresa ou organização para acessar os recursos do Teams e interagir com pessoas internas para tarefas como conversas de grupo, chat e reuniões. Você pode saber mais sobre o acesso de convidados no seguinte link: [acesso de convidados às equipes](https://docs.microsoft.com/microsoftteams/guest-access)

### <a name="external-access-in-teams"></a>Acesso externo no Teams

O acesso externo às vezes é confundido com acesso de convidados, portanto, é importante ficar claro que esses dois mecanismos de acesso não internos são realmente muito diferentes. Enquanto o acesso de convidados ocorre em uma base por usuário (você adiciona um usuário de cada vez), quando um administrador habilita o acesso externo, ele permite que você adicione todos os usuários de um domínio externo ao mesmo tempo para o Microsoft Teams. No entanto, os usuários externos têm menos acesso e funcionalidade do que um indivíduo que tenha sido adicionado por meio de acesso de convidados. Usuários de acesso externo podem bater papo com seus usuários internos via Teams.

Para obter mais informações sobre acesso externo e como implementá-lo, caso precise, revise [gerenciar o acesso externo no Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access)

## <a name="teams-policies"></a>Políticas de equipes

Fora das políticas comuns listadas acima, há políticas específicas de equipes que podem e devem ser configuradas para gerenciar várias funcionalidades de equipes.

### <a name="teams-and-channels-policies"></a>Políticas de equipes e canais

Equipes e canais são dois elementos comumente usados no Microsoft Teams, e há políticas que podem ser colocadas em vigor para controlar o que os usuários podem ou não fazer ao usar equipes e canais. Embora você possa criar uma equipe global, se sua organização tiver 5000 usuários ou menos, é provável que você ache útil ter equipes e canais menores para fins específicos, em linha com suas necessidades organizacionais.

É recomendável alterar a política padrão ou criar políticas personalizadas, e você pode saber mais sobre o gerenciamento de suas políticas neste link: [gerenciar políticas de equipes no Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-policies).

### <a name="messaging-policies"></a>Políticas de mensagens

Mensagens, ou chat, também podem ser gerenciadas por meio da política global padrão, ou por meio de políticas personalizadas, e isso pode ajudar os usuários a se comunicar uns com os outros de forma adequada à sua organização. Essas informações podem ser revisadas no [Gerenciamento de políticas de mensagens no Microsoft Teams](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams).

### <a name="meeting-policies"></a>Políticas de reunião

Nenhuma discussão sobre o Teams seria concluída sem planejamento e implementação de políticas em relação às reuniões do teams. As reuniões são um componente essencial do Teams, permitindo que as pessoas atendam formalmente e apresentem vários usuários de uma só vez, além de compartilhar conteúdo relevante para a reunião. A definição das políticas corretas para sua organização em relação às reuniões é essencial.

Consulte [gerenciar políticas de reunião no Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) para obter mais informações.

### <a name="app-permission-policies"></a>Políticas de permissão de aplicativo

O Microsoft Teams também permite que você use aplicativos em vários lugares, como canais ou chats pessoais. Ter políticas em torno de quais aplicativos podem ser adicionados e usados e, em que, é essencial manter um ambiente rico em conteúdo que também é seguro.

Para obter mais informações sobre políticas de permissão de aplicativo, confira [Manage app Permission Policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies).

## <a name="next-steps"></a>Próximas etapas

[Saiba como habilitar o acesso condicional para o Exchange Online](secure-email-recommended-policies.md)


