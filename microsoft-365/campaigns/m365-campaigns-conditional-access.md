---
title: Configurar políticas de acesso condicional
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como exigir a MFA e configurar as políticas de acesso condicional para o Microsoft 365 Business.
ms.openlocfilehash: 7898ded24bb66545b903ab98f3c7aa78d95860f1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42056395"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>Exigir autenticação multifator e configurar políticas de acesso condicional

Você protege o acesso aos seus dados com a autenticação multifator e políticas de acesso condicional. Eles adicionam segurança adicional substancial. A Microsoft fornece um conjunto de políticas de acesso condicional de linha de base que são recomendadas para todos os clientes. As políticas de linha de base são um conjunto de políticas predefinidas que ajudam a proteger as organizações contra vários ataques comuns. Esses ataques comuns podem incluir a irrigação de senha, a repetição e o phishing.

Essas políticas exigem que administradores e usuários insiram uma segunda forma de autenticação (chamada de autenticação multifator, ou MFA) quando determinadas condições são atendidas. Por exemplo, se um usuário em sua organização tentar entrar no Microsoft 365 de um país diferente ou de um dispositivo desconhecido, o logon poderá ser considerado arriscado. O usuário deve fornecer uma forma extra de autenticação (como uma impressão digital ou um código) para provar sua identidade. 

No momento, as políticas de linha de base incluem o seguinte:
- Configurado no centro de administração do Microsoft 365:
    - **Exigir MFA para administradores** — requer autenticação multifator para as funções de administrador mais privilegiadas, incluindo administrador global.
    - **Proteção do usuário final** — requer autenticação multifator para usuários somente quando uma entrada é arriscada. 
- Configurado no portal do Azure Active Directory:
    - **Bloquear autenticação herdada** — aplicativos cliente mais antigos e alguns aplicativos novos não usam protocolos de autenticação mais recentes, mais seguros. Esses aplicativos antigos podem ignorar as políticas de acesso condicional e obter acesso não autorizado ao seu ambiente. Esta política bloqueia o acesso de clientes que não dão suporte ao acesso condicional. 
    - **Requer MFA para gerenciamento de serviços** — requer a autenticação multifator para acessar ferramentas de gerenciamento, incluindo o portal do Azure (onde você configura as políticas de linha de base). 

A Microsoft recomenda que você habilite todas essas políticas de linha de base. Após a habilitação dessas políticas, os administradores e os usuários serão solicitados a registrar a autenticação multifator do Azure.

Para obter mais informações sobre essas políticas, consulte [o que são políticas de linha de base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?


## <a name="require-mfa"></a>Exigir MFA

Para exigir que todos os usuários entrem com uma segunda forma de ID:

1. Vá para o centro de administração <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> em e escolha **configuração**.

2. Na página configuração, escolha **Exibir** no cartão de **entrada tornar login** .


    ![Crie um cartão de logon mais seguro.](../media/setupmfa.png)
3. Na página tornar o login mais seguro, escolha **introdução**.
 
4. No painel de segurança reforçar a entrada, marque as caixas de seleção ao lado de **exigir autenticação multifator para administradores** e **exigir que os usuários se registrem para a autenticação multifator e bloquear o acesso se o risco for detectado**.
    Certifique-se de excluir a conta de administrador de [emergência](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) ou de "quebra-vidro" do requisito da MFA na caixa **localizar usuários** .
    
    ![Fortaleça a página de segurança de entrada.](../media/requiremfa.png)

5. Escolha **criar política** na parte inferior da página.

## <a name="set-up-baseline-policies"></a>Configurar políticas de linha de base

1. Vá para [portal do Azure](https://portal.azure.com)e navegue até **acesso condicional** **do Azure Active Directory** \> .
    
    As políticas de linha de base estão listadas na página e você pode ver que **exigir MFA para administradores** e **proteção do usuário final** já está habilitada após a conclusão das etapas em [exigir MFA](#require-mfa).

    ![Página que lista as políticas de linha de base para acesso condicional.](../media/casettings.png)
2. Consulte as seguintes instruções específicas para cada política:

    - [Exigir MFA para administradores](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
    - [Exigir MFA para usuários](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [Bloquear autenticação herdada](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
    - [Exigir MFA para gerenciamento de serviços](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

Você pode configurar políticas adicionais, como exigir aplicativos cliente aprovados. Para obter mais informações, consulte a [documentação de acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/).
