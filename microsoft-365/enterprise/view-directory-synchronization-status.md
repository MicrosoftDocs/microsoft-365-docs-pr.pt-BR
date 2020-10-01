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
ms.openlocfilehash: 7577ed358a262d5b0ef2932bc73cf61941bec31b
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326944"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>Exibir o status de sincronização do diretório no Microsoft 365

Se você tiver integrado os serviços de domínio do Active Directory (AD DS) local com o Azure Active Directory (Azure AD) sincronizando seu ambiente local com o Microsoft 365, também é possível verificar o status da sua sincronização.
  
## <a name="view-directory-synchronization-status"></a>Visualizar o status de sincronização de diretório

- Entre no centro de [Administração do Microsoft 365](https://admin.microsoft.com) e escolha **status DirSync** na página inicial.
- Como alternativa, você pode ir para **Users** \> **usuários ativos**do usuário e, na página **usuários ativos** , escolha **mais** \> **sincronização de diretórios**. No painel de **sincronização de diretórios** , escolha **ir para gerenciamento DirSync**.

## <a name="information-on-the-manage-directory-synchronization-page"></a>Informações na página Gerenciar sincronização de diretório

A tabela a seguir lista os recursos para os quais você pode obter informações na página.
  
Se houver um problema com a sincronização de diretório, os erros também serão listados nessa página. Para obter mais informações sobre diferentes erros que você pode encontrar, consulte [identificar erros de sincronização de diretório no Microsoft 365](identify-directory-synchronization-errors.md).
  
|Item|Para que serve|
|:-----|:-----|
|**Domínios verificados** | Número de domínios em seu locatário do Microsoft 365 que você verificou você possui. |
|**Domínios não verificados** | Domínios que você adicionou, mas não verificados. |
|**Sincronização de diretório habilitada** |True ou false. Especifica se você habilitou a sincronização de diretório. |
|**Sincronização de diretório mais recente** | Última vez em que a sincronização de diretório foi executada. Exibirá um aviso e um link para uma ferramenta de solução de problemas se a última sincronização tiver mais de três dias. |
|**Sincronização de senha habilitada** | True ou false. Especifica se a sincronização de hash de senha deve ser sincronizada entre o seu locatário do Microsoft 365 e no local. |
|**Última sincronização de senha** | Última vez em que a sincronização de hash de senha foi executada. Exibirá um aviso e um link para uma ferramenta de solução de problemas se a última sincronização tiver mais de três dias. |
|**Versão do cliente de sincronização de diretório** | Contém um link de download se uma nova versão do Azure AD Connect foi liberada. |
|**Conta de serviço de sincronização de diretório** | Exibe o nome da sua conta de serviço de sincronização de diretório do Microsoft 365. |
|||

## <a name="monitor-synchronization-health"></a>Monitorar a integridade da sincronização

Nesta seção, você instalará um agente do Azure AD Connect Health em cada um dos seus controladores de domínio AD DS locais para monitorar sua infraestrutura de identidade e os serviços de sincronização fornecidos pelo Azure AD Connect. As informações de monitoramento são disponibilizadas em um portal do Azure AD Connect Health, onde você pode ver alertas, monitoramento de desempenho, análise de uso e outras informações.

A decisão da estrutura principal de como usar o Azure AD Connect Health baseia-se em como o Azure AD Connect está sendo usado:

- Se você estiver usando a opção de **autenticação gerenciada**, comece [usando o Azure AD Connect Health com a sincronização](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) para entender e configurar o Azure AD Connect Health.
- Se você estiver sincronizando apenas os nomes das contas e dos grupos usando a **autenticação federada** com os Serviços de Federação do Active Directory (AD FS), comece [usando o Azure AD Connect Health com os AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) para entender e configurar o Azure AD Connect Health.

Ao concluir, você terá:

- Terá instalado o agente do Azure AD Connect Health nos servidores do provedor de identidade local.
- Poderá ver, no portal do Azure AD Connect Health, o estado atual de sua infraestrutura local e das atividades de sincronização com o locatário do Azure AD para suas assinaturas do Microsoft 365.

