---
title: Exibir o status de sincronização de diretórios no Microsoft 365
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
description: Neste artigo, saiba como verificar o status da sincronização de diretórios no Office 365.
ms.openlocfilehash: 7577ed358a262d5b0ef2932bc73cf61941bec31b
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326944"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>Exibir o status de sincronização de diretórios no Microsoft 365

Se você tiver integrado seus Serviços de Domínio do Active Directory (AD DS) local com o Azure Active Directory (Azure AD) sincronizando seu ambiente local com o Microsoft 365, também poderá verificar o status de sua sincronização.
  
## <a name="view-directory-synchronization-status"></a>Visualizar o status de sincronização de diretório

- Entre no centro [de administração do Microsoft 365](https://admin.microsoft.com) e escolha o Status do **DirSync** na home page.
- Como alternativa, você pode ir para **Usuários** Ativos e, na página Usuários ativos, \> escolher **Mais**  \> **Sincronização de Diretório.** No painel **Sincronização de** Diretórios, escolha **Ir para gerenciamento dirSync**.

## <a name="information-on-the-manage-directory-synchronization-page"></a>Informações na página Gerenciar sincronização de diretórios

A tabela a seguir lista os recursos sobre os que você pode obter informações na página.
  
Se houver um problema com a sincronização de diretórios, os erros também serão listados nessa página. Para saber mais sobre os diferentes erros que você pode encontrar, confira Identificar erros de sincronização [de diretório no Microsoft 365.](identify-directory-synchronization-errors.md)
  
|Item|Para que serve|
|:-----|:-----|
|**Domínios verificados** | Número de domínios no locatário do Microsoft 365 que você verificou que possui. |
|**Domínios não verificados** | Domínios adicionados, mas não verificados. |
|**Sincronização de diretório habilitada** |Verdadeiro ou Falso. Especifica se você habilitar a sincronização de diretórios. |
|**Sincronização de diretório mais recente** | Última vez em que a sincronização de diretórios foi bem-passada. Exibirá um aviso e um link para uma ferramenta de solução de problemas se a última sincronização tiver sido há mais de três dias. |
|**Sincronização de senha habilitada** | Verdadeiro ou Falso. Especifica se você tem sincronização de hash de senha entre o locatário local e o locatário do Microsoft 365. |
|**Última Sincronização de Senha** | Última vez em que a sincronização de hash de senha foi usada. Exibirá um aviso e um link para uma ferramenta de solução de problemas se a última sincronização tiver sido há mais de três dias. |
|**Versão do cliente de sincronização de diretório** | Contém um link de download se uma nova versão do Azure AD Connect tiver sido lançada. |
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

