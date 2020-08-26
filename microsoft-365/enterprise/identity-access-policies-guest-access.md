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
ms.openlocfilehash: ad1203543db1c2bd0ea9e9bdd3433aad58db320b
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898099"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>Políticas para permitir acesso B2B e de convidado externo
Este artigo descreve como ajustar as políticas comuns de acesso de dispositivo e identidades recomendadas para permitir o acesso de contas de B2B (convidados e usuários externos). Este guia é baseado nas [políticas comuns de acesso de dispositivo e identidade](identity-access-policies.md).

Essas recomendações foram projetadas para aplicar à camada de **linha de base** da proteção. No entanto, você pode ajustar as recomendações com base na granularidade de suas necessidades de proteção **confidencial** e **altamente regulamentada** . 

O fornecimento de um caminho para que os usuários B2B autentiquem com seu locatário do Azure AD não concede a esses usuários acesso a todo o seu ambiente. Os usuários B2B têm acesso apenas aos recursos que são compartilhados com eles (como arquivos) nos serviços concedidos nas políticas de acesso condicional.

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>Atualizando as políticas comuns para permitir e proteger o acesso externo e de convidados 

O diagrama a seguir ilustra as políticas comuns de acesso de dispositivo e identidades e indica (com um ícone de lápis) quais políticas serão adicionadas ou atualizadas para proteger o acesso externo e convidado. 

![Resumo das atualizações de política para proteger o acesso de convidados](../media/identity-access-ruleset-guest.png)

A tabela a seguir lista as políticas que você precisa atualizar ou criar novas. O link de políticas comuns para as instruções de configuração associadas no artigo [Common Identity and Device Access Policies](identity-access-policies.md) .

|Nível de Proteção|Políticas|Mais informações|
|:---------------|:-------|:----------------|
|**Baseline**|[Exigir a MFA sempre para usuários convidados e externos](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Crie essa nova regra e aplique-a somente a convidados e usuários externos. Em risco de entrada, deixe todas as opções desmarcadas para sempre impor a MFA.|
|        |[Exigir MFA quando o risco de entrada for *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Modifique esta regra para excluir usuários convidados e externos.|
|        |[Exigir PCs compatíveis](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Modifique esta regra para excluir usuários convidados e externos.|

Para incluir ou excluir convidados e usuários externos nas regras de acesso condicional, clique na guia incluir ou excluir e marque **todos os convidados e usuários externos**.

![captura de tela de controles para excluir convidados](../media/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Mais informações

### <a name="guests-vs-external-users"></a>Convidados vs. usuários externos
No Azure AD, os usuários convidados e externos são os mesmos. O tipo de usuário para ambos é Guest. Os usuários convidados são usuários B2B.

O Microsoft Teams diferencia entre usuários convidados e usuários externos dentro do aplicativo, mas são usuários de B2B durante a autenticação. Para obter mais informações sobre os usuários convidados e externos do Teams, consulte [habilitar o convidado e o acesso externo para o Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).

### <a name="require-mfa-always-for-guest-and-external-users"></a>Exigir a MFA sempre para usuários convidados e externos
Essa regra solicita que os convidados registrem a MFA em seu locatário, independentemente de estarem ou não registrados para a MFA em seu locatário inicial. Ao acessar recursos em seu locatário, convidados e usuários externos precisam usar a MFA para cada solicitação. 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>Excluindo usuários convidados e externos da MFA baseada em riscos
Enquanto as organizações podem aplicar políticas com base em risco para usuários B2B usando a proteção de identidade, há limitações na implementação da proteção de identidade para usuários de colaboração B2B em um diretório de recursos devido à sua identidade existente em seu diretório base. Devido a essas limitações, a Microsoft recomenda que você exclua os usuários convidados das políticas de MFA baseadas em risco e exija que esses usuários sempre usem a MFA. 

Para obter mais informações, consulte [limitações de proteção de identidade para usuários de colaboração B2B](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users). 

### <a name="excluding-guest-and-external-users-from-device-management"></a>Excluindo usuários convidados e externos do gerenciamento de dispositivos 
Somente uma organização pode gerenciar um dispositivo. Se você não excluir usuários convidados e externos de políticas que exigem conformidade de dispositivos, essas políticas bloquearão esses usuários. 

## <a name="next-steps"></a>Próximas etapas

[Saiba como habilitar o acesso condicional do teams](teams-access-policies.md)

