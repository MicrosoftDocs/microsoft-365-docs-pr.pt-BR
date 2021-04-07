---
title: Políticas de acesso de dispositivo e identidade para permitir acesso B2B de usuários convidados e externos - Microsoft 365 para empresas | Microsoft Docs
description: Descreve o Acesso Condicional recomendado e políticas relacionadas para proteger o acesso de convidados e usuários externos.
ms.prod: m365-security
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
audience: Admin
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
ms.technology: mdo
ms.openlocfilehash: 4ce52c40e622f55b0fd231ec634c4897fea1d6f5
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615490"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a>Políticas para permitir acesso de convidados e acesso de usuário externo B2B

Este artigo discute o ajuste das políticas recomendadas de acesso a dispositivos e identidades para permitir o acesso a convidados e usuários externos que tenham uma conta do Azure Active Directory (Azure AD) Business-to-Business (B2B). Essa orientação se baseia nas políticas [comuns de identidade e acesso a dispositivos.](identity-access-policies.md)

Essas recomendações foram projetadas para se aplicar à camada **de linha** de base de proteção. Mas você também pode ajustar as recomendações com base em suas necessidades específicas para **proteção** sensível **e altamente regulamentada.**

Fornecer um caminho para contas B2B autenticar com seu locatário do Azure AD não dá a essas contas acesso a todo o seu ambiente. Os usuários B2B e suas contas têm acesso a serviços e recursos, como arquivos, compartilhados com eles pela política de Acesso Condicional.

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a>Atualizando as políticas comuns para permitir e proteger convidados e acesso de usuário externo

Este diagrama mostra quais políticas adicionar ou atualizar entre as políticas comuns de acesso a dispositivos e identidade, para acesso de usuário externo e convidado B2B.

[![Resumo das atualizações de política para proteger o acesso de convidados](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

A tabela a seguir lista as políticas que você precisa criar e atualizar. As políticas comuns vinculam-se às instruções de configuração associadas no [artigo Common identity and device access policies.](identity-access-policies.md)

|Nível de Proteção|Políticas|Mais informações|
|---|---|---|
|**Baseline**|[Exigir MFA sempre para convidados e usuários externos](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Crie essa nova política e configure: <ul><li>Para **atribuições > Usuários** e grupos > Incluir , escolha **Selecionar** usuários e grupos e selecione Todos os usuários convidados **e externos**.</li><li>Para **Atribuições > Condições > Entrar,** deixe todas as opções desmarcadas para sempre impor a autenticação multifatória (MFA).</li></ul>|
||[Exigir MFA quando o risco de entrar é *médio* ou *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Modifique essa política para excluir convidados e usuários externos.|
||[Exigir PCs compatíveis](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Modifique essa política para excluir convidados e usuários externos.|

Para incluir ou excluir convidados e usuários externos em políticas de Acesso Condicional, para atribuições > Usuários e grupos > Incluir ou Excluir **,** verifique Todos os usuários convidados e **externos.** 

![captura de tela de controles para excluir convidados e usuários externos](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Mais informações

### <a name="guests-and-external-user-access-with-microsoft-teams"></a>Convidados e acesso de usuário externo com o Microsoft Teams

O Microsoft Teams define os seguintes usuários:

- **O acesso de** convidados usa uma conta B2B do Azure AD que pode ser adicionada como membro de uma equipe e ter acesso às comunicações e recursos da equipe.

- **O acesso** externo é para um usuário externo que não tem uma conta B2B. O acesso de usuário externo inclui convites, chamadas, chats e reuniões, mas não inclui a associação à equipe e o acesso aos recursos da equipe.

Para obter mais informações, consulte a [comparação entre convidados e acesso de usuário externo para equipes](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).

Para obter mais informações sobre como proteger políticas de acesso de identidade e dispositivo para o Teams, consulte Recomendações de política para proteger [chats,](teams-access-policies.md)grupos e arquivos do Teams.

### <a name="require-mfa-always-for-guest-and-external-users"></a>Exigir MFA sempre para usuários convidados e externos

Esta política solicita que os convidados se registrem no MFA em seu locatário, independentemente de eles estar registrados para MFA em seu locatário ínteco. Ao acessar recursos em seu locatário, os convidados e os usuários externos devem usar o MFA para cada solicitação.

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a>Excluindo convidados e usuários externos do MFA baseado em risco

Embora as organizações possam impor políticas baseadas em risco para usuários B2B usando a Proteção de Identidade do Azure AD, há limitações na implementação da Proteção de Identidade do Azure AD para usuários de colaboração B2B em um diretório de recursos devido à sua identidade existente em seu diretório inicial. Devido a essas limitações, a Microsoft recomenda excluir convidados de políticas MFA baseadas em risco e exigir que esses usuários sempre usem mFA.

Para obter mais informações, consulte [Limitações da Proteção de Identidade para usuários de colaboração B2B.](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)

### <a name="excluding-guests-and-external-users-from-device-management"></a>Excluindo convidados e usuários externos do gerenciamento de dispositivos

Somente uma organização pode gerenciar um dispositivo. Se você não excluir convidados e usuários externos de políticas que exigem conformidade com o dispositivo, essas políticas bloquearão esses usuários.

## <a name="next-step"></a>Próxima etapa

![Etapa 4: Políticas para aplicativos de nuvem do Microsoft 365 e Segurança do Microsoft Cloud App](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configurar políticas de Acesso Condicional para:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
- [Microsoft Cloud App Security](mcas-saas-access-policies.md)
 