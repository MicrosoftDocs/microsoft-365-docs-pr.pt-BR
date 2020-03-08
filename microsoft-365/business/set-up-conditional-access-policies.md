---
title: Configurar políticas de acesso condicional para campanhas do Microsoft 365
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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como configurar políticas de acesso condicional para o Microsoft 365 Campaigns para adicionar mais segurança substancial.
ms.openlocfilehash: eda65e335df2a7c2c443d7095f7b35b5c1cf27e4
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561211"
---
# <a name="set-up-conditional-access-policies"></a>Configurar políticas de acesso condicional

As políticas de [acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) adicionam mais segurança substancial. A Microsoft fornece um conjunto de políticas de acesso condicional de linha de base que são recomendadas para todos os clientes. As políticas de linha de base são um conjunto de políticas predefinidas que ajudam a proteger as organizações contra vários ataques comuns. Esses ataques comuns podem incluir a irrigação de senha, a repetição e o phishing.

Essas políticas exigem que administradores e usuários insiram uma segunda forma de autenticação (chamada de autenticação multifator, ou MFA) quando determinadas condições são atendidas. Por exemplo, se um usuário estiver entrando em um país diferente, o logon poderá ser considerado arriscado e o usuário deverá fornecer uma forma adicional de autenticação. 

No momento, as políticas de linha de base incluem o seguinte:
- **Exigir MFA para administradores** &ndash; requer autenticação multifator para as funções de administrador mais privilegiadas, incluindo administrador global.
- A **proteção** &ndash; do usuário final requer a autenticação multifator para usuários somente quando um logon é arriscado. 
- **Bloquear autenticação** &ndash; herdada aplicativos cliente mais antigos e alguns aplicativos novos não usam protocolos de autenticação mais recentes e mais seguros. Esses aplicativos antigos podem ignorar as políticas de acesso condicional e obter acesso não autorizado ao seu ambiente. Esta política bloqueia o acesso de clientes que não dão suporte ao acesso condicional. 
- **Exigir MFA para gerenciamento** &ndash; de serviços requer autenticação multifator para acessar ferramentas de gerenciamento, incluindo o portal do Azure (onde você configura as políticas de linha de base). 

A Microsoft recomenda que você habilite todas essas políticas de linha de base. Depois que essas políticas forem habilitadas, os administradores e os usuários serão solicitados a registrar a autenticação de fator de vários grupos do Azure.

Para obter mais informações sobre essas políticas, consulte [o que são políticas de linha de base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?


## <a name="set-up-baseline-policies"></a>Configurar políticas de linha de base

1. Vá para [portal do Azure](https://portal.azure.com)e navegue até **acesso condicional** **do Azure Active Directory** \> .
    
    As políticas de linha de base são listadas na página. <br/> <br/>
    ![Página que lista as políticas de linha de base para acesso condicional.](../media/baslinepolicies.png)
1. Consulte as seguintes instruções específicas para cada política:

  - [Exigir MFA para administradores](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [Exigir MFA para usuários](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [Bloquear autenticação herdada](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [Exigir MFA para gerenciamento de serviços](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

Você pode configurar várias políticas adicionais, como exigir aplicativos cliente aprovados. Para obter mais informações, consulte a [documentação de acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/).
