---
title: Autenticação multifator para Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: A autenticação multifato (MFA) usa uma senha, que deve ser forte, e um método de verificação adicional.
ms.openlocfilehash: 6e1c43bdd66849a0043c0a1a927f48d925e0806e
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635769"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a>Autenticação multifator para Microsoft 365

As senhas são o método mais comum de autenticação de uma assinatura em um computador ou serviço online, mas também são as mais vulneráveis. As pessoas podem escolher senhas fáceis e usar as mesmas senhas para vários logins em computadores e serviços diferentes.

Para fornecer um nível adicional de segurança para entrar, você deve usar a autenticação multifato (MFA), que usa uma senha, que deve ser forte, e um método de verificação adicional com base em:

- Algo que você tem com você que não é facilmente duplicado, como um telefone inteligente.
- Algo que você tem de forma exclusiva e biologicamente, como suas impressões digitais, face ou outro atributo biométrico.

O método de verificação adicional não é empregado até que a senha do usuário seja verificada. Com o MFA, mesmo que uma senha de usuário forte seja comprometida, o invasor não tem seu smartphone ou sua impressão digital para concluir a login.

## <a name="mfa-support-in-microsoft-365"></a>Suporte A MFA no Microsoft 365

Por padrão, os Microsoft 365 e Office 365 suportam MFA para contas de usuário usando:

- Uma mensagem de texto enviada para um telefone que exige que o usuário digite um código de verificação.
- Uma chamada telefônica.
- O Microsoft Authenticator de telefone inteligente.

Em ambos os casos, a assinatura MFA está usando o método "algo que você tem com você que não é facilmente duplicado" para a verificação adicional. Há várias maneiras de habilitar o MFA para Microsoft 365 e Office 365:

- Com padrões de segurança
- Com políticas de Acesso Condicional
- Para cada conta de usuário individual (não recomendada)

Essas maneiras se baseiam no seu Microsoft 365 plano.

|Plano|Recomendação|Tipo de cliente|
|---|---|---|
|Todos os Microsoft 365 planos|Use padrões de segurança, que exigem MFA para todas as contas de usuário. <p> Você também pode configurar o MFA por usuário em contas de usuário individuais, mas isso não é recomendado.|Pequena empresa|
|Microsoft 365 Business Premium <p> Microsoft 365 E3 <p> Azure Active Directory (Azure AD) Premium P1|Use políticas de Acesso Condicional para exigir MFA para contas de usuário com base em associação a grupos, aplicativos ou outros critérios.|Pequenas empresas para empresas|
|Microsoft 365 E5 <p> Licenças do Azure AD Premium P2|Use a Proteção de Identidade do Azure AD para exigir MFA com base nos critérios de risco de login.|Corporativo|
||||

### <a name="security-defaults"></a>Padrões de segurança

Os padrões de segurança são um novo recurso para assinaturas pagas ou de avaliação do Microsoft 365 e Office 365 criadas após 21 de outubro de 2019. Essas assinaturas têm padrões de segurança ativas, que:

- Exige que todos os usuários usem o MFA com o Microsoft Authenticator app.
- Bloqueia a autenticação herdda.

Os usuários têm 14 dias para se registrar na MFA com o aplicativo Microsoft Authenticator em seus smartphones, que começa na primeira vez em que eles entram depois de os padrões de segurança terem sido habilitados. Após 14 dias, o usuário não poderá entrar até que o registro da MFA seja concluído.

Os padrões de segurança garantem que todas as organizações tenham um nível básico de segurança para a entrada do usuário, que é habilitado por padrão. Você pode desabilitar os padrões de segurança em favor do MFA com políticas de Acesso Condicional.

Você habilita ou desabilita os padrões de segurança no painel **Propriedades** do Azure AD no portal do Azure.

![Imagem da página Propriedades do diretório.](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

Você pode usar padrões de segurança com qualquer Microsoft 365 plano.

Para obter mais informações, confira esta [visão geral dos padrões de segurança](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

### <a name="conditional-access-policies"></a>Políticas de Acesso Condicional

As políticas de acesso condicional são um conjunto de regras que especificam as condições sob as quais as entradas são avaliadas e permitidas. Por exemplo, você pode criar uma política de acesso condicional que declare:

- Se o nome da conta de usuário for membro de um grupo para usuários a quem são atribuídas as funções de administrador do Exchange, de usuário, de senha, de segurança, do SharePoint ou global, exija a MFA antes de permitir o acesso.

Essa política permite exigir a MFA com base na associação ao grupo, em vez de tentar configurar contas de usuário individuais para a MFA quando elas são atribuídas ou não a essas funções de administrador.

Você também pode usar políticas de Acesso Condicional para recursos mais avançados, como exigir MFA para aplicativos específicos ou que a entrada é feita a partir de um dispositivo compatível, como seu laptop executando Windows 10.

Você configura políticas de Acesso Condicional no **painel** Segurança do Azure AD no portal do Azure.

![Imagem da opção de menu para Acesso Condicional](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

Você pode usar políticas de Acesso Condicional com:

- Microsoft 365 Business Premium
- Microsoft 365 E3 e E5
- Licenças do Azure AD Premium P1 e Azure AD Premium P2

Para pequenas empresas com Microsoft 365 Business Premium, você pode usar facilmente as políticas de Acesso Condicional com as seguintes etapas:

1. Crie um grupo para conter as contas de usuário que exigem MFA.
2. Habilita **a política Exigir MFA para administradores globais.**
3. Crie uma política de Acesso Condicional baseada em grupo com estas configurações:
    - Atribuições > Usuários e grupos: o nome do seu grupo da Etapa 1 acima.
    - Atribuições > aplicativos ou ações na nuvem: todos os aplicativos de nuvem.
    - Controles de acesso > conceder > conceder acesso > exigir autenticação multifagássion.
4. Habilita a política.
5. Adicione uma conta de usuário ao grupo criado na Etapa 1 acima e teste.
6. Para exigir MFA para contas de usuário adicionais, adicione-as ao grupo criado na Etapa 1.

Esta política de Acesso Condicional permite que você íntega o requisito de MFA para seus usuários em seu próprio ritmo.

As empresas devem usar [políticas comuns de Acesso Condicional](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) para configurar as seguintes políticas:

- [Exigir MFA para administradores](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [Exigir MFA para todos os usuários](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Bloquear autenticação herdada](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

Para mais informações, confira esta [visão geral do Acesso Condicional](/azure/active-directory/conditional-access/overview).

### <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

Com a Proteção de Identidade do Azure AD, você pode criar uma política de Acesso Condicional adicional para exigir MFA quando o risco de entrada [for médio ou alto.](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)

Você pode usar a Proteção de Identidade do Azure AD e políticas de Acesso Condicional baseadas em risco com:

- Microsoft 365 E5
- Licenças do Azure AD Premium P2

Para obter mais informações, confira esta [visão geral da Azure Active Directory Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).

### <a name="legacy-per-user-mfa-not-recommended"></a>MFA herdda por usuário (não recomendado)

Você deve estar usando os padrões de segurança ou políticas de Acesso Condicional para exigir MFA para suas inserções de conta de usuário. No entanto, se um desses não puder ser usado, a Microsoft recomenda fortemente o MFA para contas de usuário que tenham funções de administrador, especialmente a função de administrador global, para qualquer assinatura de tamanho.

Você habilita o MFA para contas de usuário individuais no **painel** Usuário Ativo do Microsoft 365 de administração.

![Imagem da opção de autenticação de vários fatores na página Usuários ativos](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

Depois de habilitado, na próxima vez que o usuário entrar, ele será solicitado a se registrar no MFA e escolher e testar o método de verificação adicional.

### <a name="using-these-methods-together"></a>Usando esses métodos juntos

Esta tabela mostra os resultados da ativação da MFA com padrões de segurança, políticas de Acesso Condicional e configurações de conta por usuário.

||Habilitado|Desabilitado|Método de autenticação secundária|
|---|---|---|---|
|**Padrões de segurança**|Não é possível usar políticas de Acesso Condicional|Pode usar políticas de Acesso Condicional|Aplicativo Microsoft Authenticator|
|**Políticas de Acesso Condicional**|Se algum estiver habilitado, você não poderá habilitar os padrões de segurança|Se todas estiverem desabilitadas, você poderá habilitar os padrões de segurança|Especificado pelo usuário durante o registro da MFA|
|**MFA herdda por usuário (não recomendado)**|Substitui os padrões de segurança e as políticas de Acesso Condicional que exigem MFA em cada entrada|Substituído por padrões de segurança e políticas de Acesso Condicional|Especificado pelo usuário durante o registro da MFA|
||||

Se os padrões de segurança estão habilitados, todos os novos usuários são solicitados a solicitar o registro MFA e o uso do aplicativo Microsoft Authenticator em sua próxima login.

## <a name="ways-to-manage-mfa-settings"></a>Maneiras de gerenciar configurações de MFA

Há duas maneiras de gerenciar configurações de MFA.

No portal do Azure, você pode:

- Habilitar e desabilitar padrões de segurança
- Configurar políticas de Acesso Condicional

No centro Microsoft 365 de administração, você pode configurar as configurações de MFA por usuário e serviço.

## <a name="next-steps"></a>Próximas etapas

[Configurar o MFA para Microsoft 365](set-up-multi-factor-authentication.md)

## <a name="related-content"></a>Conteúdo relacionado

[Ativar a autenticação multifator](../../business-video/turn-on-mfa.md) (vídeo)\
[Ativar a autenticação multifator para seu telefone](../../business-video/set-up-mfa.md) (vídeo)