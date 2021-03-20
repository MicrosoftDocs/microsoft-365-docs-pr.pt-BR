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
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como exigir MFA e configurar políticas de acesso condicional para o Microsoft 365 para empresas.
ms.openlocfilehash: dcb79ed060dd15fd288cdcfb9e3739a788f5fbc2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912181"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>Exigir autenticação multifacional e configurar políticas de acesso condicional

Você protege o acesso aos seus dados com autenticação multifacional e políticas de acesso condicional. Eles adicionam segurança adicional substancial. A Microsoft fornece um conjunto de políticas de acesso condicional de linha de base recomendadas para todos os clientes. As políticas de linha de base são um conjunto de políticas predefinidas que ajudam a proteger as organizações contra muitos ataques comuns. Esses ataques comuns podem incluir spray de senha, repetição e phishing.

Essas políticas exigem que os administradores e usuários insiram uma segunda forma de autenticação (chamada autenticação multifatória ou MFA) em determinadas condições. Por exemplo, se um usuário em sua organização tentar entrar no Microsoft 365 de um país diferente ou de um dispositivo desconhecido, a entrada pode ser considerada arriscada. O usuário deve fornecer uma forma extra de autenticação (como uma impressão digital ou um código) para provar sua identidade.

Atualmente, as políticas de linha de base incluem as seguintes políticas:

- Configurar no Centro de administração do Microsoft 365:
  - **Exigir MFA para administradores**: requer autenticação multifatória para as funções de administrador mais privilegiadas, incluindo o administrador global.
  - **Proteção do usuário final**: requer autenticação multifafa para os usuários somente quando uma login é arriscada. 
- Configurar no portal do Azure Active Directory:
  - **Bloquear autenticação herdada**: aplicativos cliente mais antigos e alguns novos aplicativos não usam protocolos de autenticação mais novos, mais seguros. Esses aplicativos mais antigos podem ignorar políticas de acesso condicional e obter acesso não autorizado ao seu ambiente. Essa política bloqueia o acesso de clientes que não suportam acesso condicional. 
  - **Exigir MFA para Gerenciamento de Serviço**: requer autenticação multifacional para acesso a ferramentas de gerenciamento, incluindo o portal do Azure (onde você configura políticas de linha de base).

Recomendamos que você habilita todas essas políticas de linha de base. Depois que essas políticas são habilitadas, os administradores e os usuários serão solicitados a se registrarem para a Autenticação Multifator do Azure AD.

Para obter mais informações sobre essas políticas, consulte [O que são políticas de linha de base](/azure/active-directory/conditional-access/concept-baseline-protection)?

## <a name="require-mfa"></a>Exigir MFA

Para exigir que todos os usuários entre com uma segunda forma de ID:

1. Vá para o centro de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> e escolha **Instalação**.

2. Na página Instalação, escolha **Exibir** no **cartão Tornar entrar mais** seguro.

    ![Tornar o cartão de acesso mais seguro.](../media/setupmfa.png)
3. Na página Tornar a conexão mais segura, escolha **Começar**.

4. No painel Fortalecer a segurança de entrada, selecione  as caixas de seleção ao lado de Exigir autenticação multifator para administradores e Exigir que os usuários se registrem para autenticação multifator e bloqueiem o acesso se o risco for **detectado**.
    Certifique-se de excluir a [conta de](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) administrador de emergência ou "quebra de vidro" do requisito MFA na caixa **Encontrar usuários.**

    ![Fortalecer a página de segurança de canto.](../media/requiremfa.png)

5. Escolha **Criar política** na parte inferior da página.

## <a name="set-up-baseline-policies"></a>Configurar políticas de linha de base

1. Vá para o [portal do Azure](https://portal.azure.com)e navegue até Acesso Condicional de Segurança do **Azure Active Directory** para criar uma nova \>  \>  **política.**

Consulte as seguintes instruções específicas para cada política: <br>
    - [Exigir MFA para administradores](/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [Exigir MFA para usuários](/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [Bloquear autenticação herdda](/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [Exigir MFA para gerenciamento de serviço](/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> Políticas de visualização não existem mais e os usuários precisarão criar suas próprias políticas.

Você pode configurar políticas extras, como exigir aplicativos cliente aprovados. Para obter mais informações, consulte [a documentação do Acesso Condicional](/azure/active-directory/conditional-access/).