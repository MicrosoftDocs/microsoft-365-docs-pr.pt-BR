---
title: Políticas de acesso de dispositivo e identidade para permitir acesso B2B e de convidado externo-Microsoft 365 for Enterprise | Microsoft docs
description: Descreve o acesso condicional recomendado e as políticas relacionadas para proteger o acesso de usuários externos e convidados.
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: c61526139111885ec345bc4a4dd3cd6b147370e6
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950803"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>Políticas para permitir acesso B2B e de convidado externo

Este artigo descreve como ajustar as políticas comuns de acesso de dispositivo e identidades recomendadas para permitir acesso à conta de B2B (entre empresas) (usuários convidados e externos). Este guia é baseado nas [políticas comuns de acesso de dispositivo e identidade](identity-access-policies.md).

Essas recomendações foram projetadas para aplicar à camada de **linha de base** da proteção. No entanto, você também pode ajustar as recomendações com base na granularidade de suas necessidades de proteção **confidencial** e **altamente regulamentada** . 

Fornecer um caminho para que os usuários B2B autentiquem com seu locatário do Azure Active Directory (Azure AD) não concede a esses usuários acesso a todo o seu ambiente. Os usuários B2B têm acesso apenas aos recursos que são compartilhados com eles (como arquivos) nos serviços concedidos nas políticas de acesso condicional.

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>Atualizando as políticas comuns para permitir e proteger o acesso externo e de convidados 

Para proteger o acesso externo e de convidados, o diagrama a seguir ilustra quais políticas serão adicionadas ou atualizadas das políticas comuns de acesso de identidade e de dispositivo. 

[![Resumo das atualizações de política para proteger o acesso de convidados](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[Veja uma versão maior desta imagem](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

A tabela a seguir lista as políticas que você precisa atualizar ou criar novas. O link de políticas comuns para as instruções de configuração associadas no artigo [Common Identity and Device Access Policies](identity-access-policies.md) .

|Nível de Proteção|Políticas|Mais informações|
|:---------------|:-------|:----------------|
|**Baseline**|[Exigir a MFA sempre para usuários convidados e externos](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Crie essa nova política e aplique-a somente a convidados e usuários externos. Em **risco de entrada**, deixe todas as opções desmarcadas para sempre impor a autenticação multifator (MFA).|
|        |[Exigir MFA quando o risco de entrada for *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Modifique esta política para excluir usuários convidados e externos.|
|        |[Exigir PCs compatíveis](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Modifique esta política para excluir usuários convidados e externos.|

Para incluir ou excluir convidados e usuários externos em políticas de acesso condicional, clique na guia **incluir** ou **excluir** e marque **todos os convidados e usuários externos**.

![captura de tela de controles para excluir convidados](../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Mais informações

### <a name="guests-vs-external-users"></a>Convidados vs. usuários externos
No Azure AD, os usuários convidados e externos são os mesmos. O tipo de usuário para ambos é Guest. Os usuários convidados são usuários B2B.

O Microsoft Teams diferencia entre usuários convidados e usuários externos dentro do aplicativo. Os usuários convidados têm contas B2B do Azure AD e podem ser adicionados ao Microsoft Teams. Usuários externos só podem participar de chamadas, chats e reuniões. Para obter mais informações, consulte [esta comparação entre usuários convidados e externos para o Microsoft Teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).

Consulte as [recomendações de política para proteger chats, grupos e arquivos de equipes](teams-access-policies.md) para obter mais informações sobre a proteção de identidade e acesso de dispositivo para o Microsoft Teams

### <a name="require-mfa-always-for-guest-and-external-users"></a>Exigir a MFA sempre para usuários convidados e externos
Essa política solicita que os convidados registrem a MFA em seu locatário, independentemente de estarem ou não registrados para MFA em seu locatário de casa. Ao acessar recursos em seu locatário, convidados e usuários externos precisam usar a MFA para cada solicitação. 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>Excluindo usuários convidados e externos da MFA baseada em riscos
Enquanto as organizações podem reforçar políticas com base em risco para usuários B2B usando a proteção de identidade do Azure AD, há limitações na implementação da proteção de identidade do Azure AD para usuários de colaboração B2B em um diretório de recursos devido à sua identidade existente em seu diretório base. Devido a essas limitações, a Microsoft recomenda que você exclua os usuários convidados das políticas de MFA baseadas em risco e exija que esses usuários sempre usem a MFA. 

Para obter mais informações, consulte [limitações de proteção de identidade para usuários de colaboração B2B](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users). 

### <a name="excluding-guest-and-external-users-from-device-management"></a>Excluindo usuários convidados e externos do gerenciamento de dispositivos 
Somente uma organização pode gerenciar um dispositivo. Se você não excluir usuários convidados e externos de políticas que exigem conformidade de dispositivos, essas políticas bloquearão esses usuários. 

## <a name="next-step"></a>Próxima etapa

![Etapa 4: políticas para aplicativos em nuvem da Microsoft 365](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configure as políticas de acesso condicional para:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](secure-email-recommended-policies.md)

