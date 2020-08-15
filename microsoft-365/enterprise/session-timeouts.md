---
title: Tempos limite de sessão para o Microsoft 365
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: 37a5c116-5b07-4f70-8333-5b86fd2c3c40
ms.collection:
- M365-security-compliance
description: Saiba como os tempos limite de sessão são usados para equilibrar a segurança e a facilidade de acesso nos aplicativos cliente Microsoft 365.
ms.openlocfilehash: 8fbbb526fe4b0ac136f79acd564b268489841e0b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686979"
---
# <a name="session-timeouts-for-microsoft-365"></a>Tempos limite de sessão para o Microsoft 365

Os tempos de vida da sessão são uma parte importante da autenticação do Microsoft 365 e são um componente importante no equilíbrio de segurança e o número de vezes que os usuários são solicitados por suas credenciais.
  
## <a name="session-times-for-microsoft-365-services"></a>Tempos de sessão para serviços do Microsoft 365

Quando os usuários autenticam em qualquer um dos aplicativos da Web ou aplicativos móveis do Microsoft 365, uma sessão é estabelecida. Para a duração da sessão, os usuários não precisarão autenticar novamente. As sessões podem expirar quando os usuários estão inativos, quando fecham o navegador ou guia, ou quando o token de autenticação expira por outros motivos, como quando a senha foi redefinida. Os serviços do Microsoft 365 têm tempos limites de sessão diferentes para corresponder ao uso típico de cada serviço.
  
A tabela a seguir lista os tempos de vida da sessão para os serviços do Microsoft 365:
  
|**Serviço da Microsoft 365**|**Tempo limite da sessão**|
|:-----|:-----|
|Centro de administração do Microsoft 365  <br/> |Você será solicitado a fornecer credenciais para o centro de administração a cada 8 horas.  <br/> |
|SharePoint Online  <br/> |5 dias de inatividade, desde que os usuários decidam **entrar**. Se o usuário acessar o SharePoint Online novamente após 24 ou mais horas passadas da entrada anterior, o valor de tempo limite é redefinido como 5 dias.  <br/> |
|Outlook Web App  <br/> |6 horas.  <br/> Você pode alterar esse valor usando o parâmetro  _ActivityBasedAuthenticationTimeoutInterval_ no cmdlet [Set-OrganizationConfig](https://go.microsoft.com/fwlink/p/?LinkId=615378) .  <br/> |
|Azure Active Directory  <br/> (Usado por clientes do Windows 2013 com autenticação moderna habilitada)  <br/> | A autenticação moderna usa tokens de acesso e atualiza tokens para conceder ao usuário acesso aos recursos do Microsoft 365 usando o Azure Active Directory. Um token de acesso é um token Web JSON fornecido após uma autenticação bem-sucedida e é válido por 1 hora. Um token de atualização com um tempo de vida maior também é fornecido. Quando os tokens de acesso expiram, os clientes do Office usam um token de atualização válido para obter um novo token de acesso. Esse Exchange será bem-sucedido se a autenticação inicial do usuário ainda for válida.  <br/>  Os tokens de atualização são válidos por 90 dias e com o uso contínuo, eles podem ser válidos até serem revogados.  <br/>  Os tokens de atualização podem ser invalidados por vários eventos, como:  <br/>  A senha do usuário foi alterada desde a emissão do token de atualização.  <br/>  Um administrador pode aplicar as políticas de acesso condicional que restringem o acesso ao recurso que o usuário está tentando acessar.  <br/> |
|Aplicativos móveis do SharePoint e do OneDrive para Android, iOS e Windows 10  <br/> |O tempo de vida padrão para o token de acesso é de 1 hora. O tempo máximo de inatividade padrão do token de atualização é de 90 dias.  <br/> [Saiba mais sobre tokens e como configurar tempos de vida do token](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> Para revogar o token de atualização, você pode redefinir a senha do Microsoft 365 do usuário  <br/> |
|Yammer com o Microsoft 365 entrar  <br/> |Tempo de vida do navegador. Se o usuário fechar o navegador e acessar o yammer em um novo navegador, o Yammer o autenticará novamente com o Microsoft 365. Se os usuários usarem navegadores de terceiros que armazenam cookies em cache, talvez não precisem se autenticar novamente quando abrirem novamente o navegador.  <br/> > [!NOTE]> isso é válido somente para redes que usam o Microsoft 365 entrar no Yammer.           |
   

