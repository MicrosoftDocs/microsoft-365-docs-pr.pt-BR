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
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: c2c01278831433c02e5c869dba83f223eea57d27
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683230"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>Políticas para permitir acesso B2B e de convidado externo

Este artigo descreve como ajustar as políticas comuns de acesso de dispositivo e identidades recomendadas para permitir o acesso a usuários convidados e externos que tenham uma conta de B2B (Business-to-Business) do Azure Active Directory (Azure AD). Este guia é baseado nas [políticas comuns de acesso de dispositivo e identidade](identity-access-policies.md).

Essas recomendações foram projetadas para aplicar à camada de **linha de base** da proteção. No entanto, você também pode ajustar as recomendações com base na granularidade de suas necessidades de proteção **confidencial** e **altamente regulamentada** .

Fornecer um caminho para contas B2B para autenticar com seu locatário do Azure AD não concede a essas contas acesso a todo o seu ambiente. Os usuários B2B e suas contas têm acesso apenas aos recursos que são compartilhados com eles (como arquivos) nos serviços concedidos em políticas de acesso condicional.

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>Atualizando as políticas comuns para permitir e proteger o acesso externo e de convidados

Para proteger o acesso externo e de convidados com as contas B2B do Azure AD, o diagrama a seguir ilustra quais políticas serão adicionadas ou atualizadas das políticas comuns de acesso de dispositivo e identidade.

[![Resumo das atualizações de política para proteger o acesso de convidados](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[Veja uma versão maior desta imagem](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

A tabela a seguir lista as políticas que você precisa criar e atualizar. O link de políticas comuns para as instruções de configuração associadas no artigo [Common Identity and Device Access Policies](identity-access-policies.md) .

|Nível de Proteção|Políticas|Mais informações|
|---|---|---|
|**Baseline**|[Exigir a MFA sempre para usuários convidados e externos](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Crie essa nova política e configure: <ul><li> Para as **atribuições > usuários e grupos > incluir**, escolha **Selecionar usuários e grupos** e, em seguida, selecione **todos os usuários convidados e externos**. </li><li> Para **atribuições > condições > entrar**, deixe todas as opções desmarcadas para sempre impor a autenticação multifator (MFA).</li>|
||[Exigir MFA quando o risco de entrada for *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Modifique esta política para excluir usuários convidados e externos.|
||[Exigir PCs compatíveis](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Modifique esta política para excluir usuários convidados e externos.|

Para incluir ou excluir usuários convidados e externos em políticas de acesso condicional, para **atribuições > usuários e grupos > incluir** ou **excluir**, verifique **todos os usuários convidados e externos**.

![captura de tela de controles para exclusão de usuários convidados e externos](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Mais informações

### <a name="guest-and-external-access-with-microsoft-teams"></a>Acesso externo e de convidados com o Microsoft Teams

O Microsoft Teams define o seguinte:

- O **acesso de convidados** usa uma conta de B2B do Azure AD que pode ser adicionada como um membro de uma equipe e ter todos os acessos com permissão para as comunicações e recursos da equipe.

- O **acesso externo** é para um usuário externo que não tem uma conta B2B. O acesso externo pode incluir convites e participação em chamadas, chats e reuniões, mas não inclui Associação de equipe e acesso aos recursos da equipe.

Para obter mais informações, consulte a [comparação entre o convidado e o acesso externo para o Microsoft Teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).

Consulte [recomendações de política para proteger chats, grupos e arquivos de equipes](teams-access-policies.md) para obter mais informações sobre como proteger as políticas de acesso de dispositivo e identidade para o Microsoft Teams.

### <a name="require-mfa-always-for-guest-and-external-users"></a>Exigir a MFA sempre para usuários convidados e externos

Essa política solicita que os convidados registrem a MFA em seu locatário, independentemente de estarem ou não registrados para MFA em seu locatário de casa. Ao acessar recursos em seu locatário, os usuários convidados e externos precisam usar a MFA para cada solicitação.

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>Excluindo usuários convidados e externos da MFA baseada em riscos

Enquanto as organizações podem reforçar políticas com base em risco para usuários B2B usando a proteção de identidade do Azure AD, há limitações na implementação da proteção de identidade do Azure AD para usuários de colaboração B2B em um diretório de recursos devido à sua identidade existente em seu diretório base. Devido a essas limitações, a Microsoft recomenda que você exclua os usuários convidados das políticas de MFA baseadas em risco e exija que esses usuários sempre usem a MFA.

Para obter mais informações, consulte [limitações de proteção de identidade para usuários de colaboração B2B](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).

### <a name="excluding-guest-and-external-users-from-device-management"></a>Excluindo usuários convidados e externos do gerenciamento de dispositivos

Somente uma organização pode gerenciar um dispositivo. Se você não excluir usuários convidados e externos de políticas que exigem conformidade de dispositivos, essas políticas bloquearão esses usuários.

## <a name="next-step"></a>Próxima etapa

![Etapa 4: políticas para aplicativos em nuvem da Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configure as políticas de acesso condicional para:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
