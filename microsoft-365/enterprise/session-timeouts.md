---
title: Tempo de sessão para Microsoft 365
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
description: Saiba como os tempos de sessão são usados para equilibrar a segurança e a facilidade de acesso Microsoft 365 aplicativos cliente.
ms.openlocfilehash: b85ed8a45727e8a8eed2537fa2233125cd05ece7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924911"
---
# <a name="session-timeouts-for-microsoft-365"></a>Tempo de sessão para Microsoft 365

Os tempos de vida das sessões são uma parte importante da autenticação para Microsoft 365 e são um componente importante no balanceamento de segurança e o número de vezes que os usuários são solicitados para suas credenciais.

## <a name="session-times-for-microsoft-365-services"></a>Horários de sessão para Microsoft 365 serviços

Quando os usuários autenticam em qualquer um dos aplicativos Microsoft 365 Web ou aplicativos móveis, uma sessão é estabelecida. Durante a sessão, os usuários não precisarão se autenticar. As sessões podem expirar quando os usuários estão inativos, quando fecham o navegador ou a guia, ou quando o token de autenticação expira por outros motivos, como quando a senha foi redefinida. Os Microsoft 365 de sessão têm tempos-de-tempo de sessão diferentes para corresponder ao uso típico de cada serviço.

A tabela a seguir lista os tempos de vida da sessão para Microsoft 365 serviços:

| Serviço Microsoft 365 | Tempo de sessão |
|:-----|:-----|
|Centro de administração do Microsoft 365  <br/> |Você deve fornecer credenciais para o centro de administração a cada 8 horas.  <br/> |
|SharePoint Online  <br/> |5 dias de inatividade, desde que os usuários **escolham Keep me signed in**. Se o usuário acessar o SharePoint Online novamente depois que 24 ou mais horas passaram da entrada anterior, o valor de tempo-de-tempo será redefinido para 5 dias.  <br/> |
|Outlook Web App  <br/> |Seis horas.  <br/> Você pode alterar esse valor usando o _parâmetro ActivityBasedAuthenticationTimeoutInterval_ no cmdlet [Set-OrganizationConfig.](/powershell/module/exchange/set-organizationconfig)  <br/> |
|Azure Active Directory  <br/> (Usado por aplicativos Office e Microsoft 365 em clientes Windows com autenticação moderna habilitada)  <br/> | A autenticação moderna usa tokens de acesso e tokens de atualização para conceder ao usuário acesso Microsoft 365 recursos usando Azure Active Directory. Um token de acesso é um Token Web JSON fornecido após uma autenticação bem-sucedida e é válido por 1 hora. Um token de atualização com uma vida útil mais longa também é fornecido. Quando os tokens de acesso expiram, Office os clientes usam um token de atualização válido para obter um novo token de acesso. Essa troca será bem-sucedida se a autenticação inicial do usuário ainda for válida.  <br/>  Os tokens de atualização são válidos por 90 dias e, com uso contínuo, eles podem ser válidos até revogados.  <br/>  Tokens de atualização podem ser invalidados por vários eventos, como:  <br/>  A senha do usuário foi alterada desde que o token de atualização foi emitido.  <br/>  Um administrador pode aplicar políticas de acesso condicional que restringem o acesso ao recurso que o usuário está tentando acessar.  <br/> |
|SharePoint e OneDrive aplicativos móveis para Android, iOS e Windows 10  <br/> |O tempo de vida padrão do token de acesso é de 1 hora. O tempo máximo máximo inativo padrão do token de atualização é de 90 dias.  <br/> [Saiba mais sobre tokens e como configurar tempo de vida útil do token](/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> Para revogar o token de atualização, você pode redefinir a senha Microsoft 365 usuário  <br/> |
|Yammer com Microsoft 365 Sign-In  <br/> |Tempo de vida do navegador. Se os usuários fecharem o navegador e acessarem Yammer em um novo navegador, Yammer os autenticarão com Microsoft 365. Se os usuários usarem navegadores de terceiros que armazenam cookies em cache, talvez não precisem se autenticar novamente quando reabrirem o navegador.  <br/> > [!NOTE]> Isso só é válido para redes que usam Microsoft 365 Sign-In para Yammer.           |