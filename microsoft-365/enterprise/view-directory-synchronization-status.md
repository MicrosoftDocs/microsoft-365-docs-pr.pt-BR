---
title: Exibir o status de sincronização do diretório no Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: Neste artigo, saiba como você pode verificar o status da sua sincronização de diretórios no Office 365.
ms.openlocfilehash: c77898b58b58c6ae91492debd7ad66f395d80d52
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687260"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>Exibir o status de sincronização do diretório no Microsoft 365

Se você integrou o Active Directory local ao Azure AD sincronizando seu ambiente local com o Microsoft 365, você também pode verificar o status da sua sincronização.
  
## <a name="view-directory-synchronization-status"></a>Exibir o status da sincronização de diretórios

- Entre no centro de [Administração do Microsoft 365](https://admin.microsoft.com) e escolha **status DirSync** na página inicial.
- Como alternativa, você pode ir para **Users** \> **usuários ativos**do usuário e, na página **usuários ativos** , escolha **mais** \> **sincronização de diretórios**. No painel de **sincronização de diretórios** , escolha **ir para gerenciamento DirSync**.

## <a name="information-on-the-manage-directory-synchronization-page"></a>Informações na página Gerenciar sincronização de diretório

A tabela a seguir lista os recursos para os quais você pode obter informações na página.
  
Se houver um problema com a sincronização de diretório, os erros também serão listados nessa página. Para obter mais informações sobre diferentes erros que você pode encontrar, consulte [identificar erros de sincronização de diretório no Microsoft 365](identify-directory-synchronization-errors.md).
  
|**Item**|**Para que serve**|
|:-----|:-----|
|**Domínios verificados** | Número de domínios em seu locatário do Microsoft 365 que você verificou você possui. |
|**Domínios não verificados** | Domínios que você adicionou, mas não verificados. |
|**Sincronização de diretório habilitada** |True ou false. Especifica se você habilitou a sincronização de diretório. |
|**Sincronização de diretório mais recente** | Última vez em que a sincronização de diretório foi executada. Exibirá um aviso e um link para uma ferramenta de solução de problemas se a última sincronização tiver mais de três dias. |
|**Sincronização de senha habilitada** | True ou false. Especifica se a sincronização de hash de senha deve ser sincronizada entre o seu locatário do Microsoft 365 e no local. |
|**Última sincronização de senha** | Última vez em que a sincronização de hash de senha foi executada. Exibirá um aviso e um link para uma ferramenta de solução de problemas se a última sincronização tiver mais de três dias. |
|**Versão do cliente de sincronização de diretório** | Contém um link de download se uma nova versão do Azure AD Connect foi liberada. |
|**Conta de serviço de sincronização de diretório** | Exibe o nome da sua conta de serviço de sincronização de diretório do Microsoft 365. |