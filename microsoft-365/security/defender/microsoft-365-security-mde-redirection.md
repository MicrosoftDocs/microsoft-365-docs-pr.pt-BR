---
title: Redirecionando contas do Microsoft Defender para o Ponto de Extremidade para Microsoft 365 Defender
description: Como redirecionar contas e sessões do Defender para o Ponto de Extremidade para Microsoft 365 Defender.
keywords: Microsoft 365 Defender, Iniciando o Microsoft 365 Defender, redirecionamento do centro de segurança
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c678cb8d9eece9ff3a900a7d2b0c6bf95ad8eda9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842561"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-microsoft-365-defender"></a>Redirecionando contas do Microsoft Defender para o Ponto de Extremidade para Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender
- Defender para Ponto de Extremidade

Em alinhamento com a abordagem entre domínios da Microsoft para proteção contra ameaças com SIEM e XDR (Detecção e resposta estendida), renomeamos o Proteção Avançada contra Ameaças do Microsoft Defender como Microsoft Defender para Ponto de Extremidade e unificamos-o em um único portal integrado - Microsoft 365 Defender.

Este guia explica como rotear contas para o Microsoft 365 Defender habilitando o redirecionamento automático do antigo portal do Microsoft Defender para Ponto de Extremidade (securitycenter.windows.com ou securitycenter.microsoft.com), para o portal do Defender (Microsoft 365) (security.microsoft.com).

> [!NOTE]
> O Microsoft Defender for Endpoint no Microsoft 365 Defender dá suporte à concessão de acesso a [MSSPs (provedores](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) de serviços de segurança gerenciados) da mesma forma que o acesso é concedido no centro de segurança do [Microsoft Defender.](./mssp-access.md)

## <a name="what-to-expect"></a>O que esperar
Depois que o redirecionamento automático for habilitado, as contas que acessam o antigo portal do Microsoft Defender para Ponto de Extremidade no securitycenter.windows.com ou securitycenter.microsoft.com, serão roteados automaticamente para o portal do Microsoft 365 Defender no security.microsoft.com.
 
Saiba mais sobre o que mudou: Microsoft Defender para Ponto de [Extremidade no Microsoft 365 Defender](microsoft-365-security-center-mde.md).

Isso inclui redirecionamento para acesso direto ao portal anterior por meio do navegador, incluindo links apontando para o antigo portal securitycenter.windows.com - como links em notificações de email e links retornados por chamadas de API SIEM.  

 Links externos de notificações por email ou APIs SIEM atualmente contêm links para ambos os portais. Depois que o redirecionamento for habilitado, ambos os links apontarão para Microsoft 365 Defender até que o link antigo seja removido. Recomendamos que você adote o novo link apontando para Microsoft 365 Defender.

Consulte a tabela abaixo para obter mais informações sobre links e roteamento.
## <a name="siem-api-routing"></a>Roteamento de API SIEM

|**Property**  |**Destino quando o redirecionamento está OFF**  |**Destino quando o redirecionamento está ON** | 
|---------|---------|---------|
| LinkToWDATP | Página de alerta no securitycenter.windows.com | Página de alerta em security.microsoft.com  |
| IncidentLinkToWDATP | Página incidente no securitycenter.windows.com  | Página de incidentes em security.microsoft.com  |
| LinkToMTP | Página de alerta em security.microsoft.com | Página de alerta em security.microsoft.com  |
| IncidentLinkToMTP | Página de incidentes em security.microsoft.com  | Página de incidentes em security.microsoft.com  

## <a name="email-alert-notifications"></a>Notificações de alerta de email

|**Property**  |**Destino quando o redirecionamento está OFF**  |**Destino quando o redirecionamento está ON** |
|---------|---------|---------|
| Página alerta  | Página de alerta no securitycenter.windows.com  | Página de alerta em security.microsoft.com  |
| Página incidente  |Página incidente no securitycenter.windows.com  | Página de incidentes em security.microsoft.com  
| Página de alerta no portal do Centro de Segurança | Página de alerta em security.microsoft.com | Página de alerta em security.microsoft.com | 
| Página de incidentes no portal da central de segurança | Página de incidentes em security.microsoft.com  | Página de incidentes em security.microsoft.com  |

## <a name="when-does-this-take-effect"></a>Quando isso tem efeito? 
Depois de habilitada, essa atualização pode ter efeito quase imediatamente para algumas contas. Mas o redirecionamento pode levar mais tempo para se propagar para todas as contas da sua organização. As contas em sessões ativas enquanto essa configuração é aplicada não serão ejetadas de suas sessões e serão roteadas apenas para o Microsoft 365 Defender após o término da sessão atual e a sessão de logon novamente.  

### <a name="set-up-portal-redirection"></a>Configurar redirecionamento de portal
Para iniciar o roteamento de contas para Microsoft 365 Defender:
1. Certifique-se de ser um administrador global ou ter permissões de administrador de segurança no Azure Active directory 

2. [Entre no](https://security.microsoft.com/) Microsoft 365 Defender.

3. Navegue **Configurações**  >  **redirecionamento geral** do Portal de Pontos de  >    >  **Extremidade** ou clique [aqui](https://security.microsoft.com/preferences2/portal_redirection).  

4. Alterne a configuração de redirecionamento automático para **On**.

5. Clique **em Habilitar** para aplicar redirecionamento automático ao Microsoft 365 Defender.

>[!IMPORTANT]
>A habilitação dessa configuração não encerrará sessões de usuário ativas. As contas que estão em uma sessão ativa enquanto essa configuração é aplicada serão direcionadas Microsoft 365 Defender depois de encerrar a sessão atual e entrar novamente.

>[!NOTE]
>Você deve ser um administrador global ou ter permissões de administrador de segurança Azure Active Directory habilitar ou desabilitar essa configuração.  

## <a name="can-i-go-back-to-using-the-former-portal"></a>Posso voltar a usar o portal anterior?
Se algo não estiver funcionando para você ou se houver algo que você não consiga concluir por meio do Microsoft 365 Defender, queremos ouvir sobre isso. Se você tiver encontrado algum problema com redirecionamento, recomendamos que você nos avise usando o formulário De envio de comentários.

Para reverter para o antigo portal do Microsoft Defender para Ponto de Extremidade:

1. [Entre no](https://security.microsoft.com/) Microsoft 365 Defender como administrador global ou usando e conta com permissões de administrador de segurança no Azure Active directory.

2. Navegue **Configurações**  >  **redirecionamento geral** do Portal de Pontos de  >    >  **Extremidade** ou abra a página [aqui](https://security.microsoft.com/preferences2/portal_redirection).  

3. Alterne a configuração de redirecionamento automático para **Off**.

4. Clique **em Desabilitar** & comentários de compartilhamento quando solicitado.

Essa configuração pode ser habilitada novamente a qualquer momento. 

Depois de desabilitada, as contas não serão mais roteadas para security.microsoft.com, e você terá novamente acesso ao portal anterior - securitycenter.windows.com ou securitycenter.microsoft.com. 

## <a name="related-information"></a>Informações relacionadas
- [Microsoft 365 Visão geral do Defender](overview-security-center.md)
- [Microsoft Defender para Ponto de Extremidade no Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [A Microsoft oferece SIEM e XDR unificados para modernizar operações de segurança](https://www.microsoft.com/security/blog/?p=91813) 
- [Infográfico XDR versus SIEM](https://afrait.com/blog/xdr-versus-siem/) 
- [O Novo Defensor](https://afrait.com/blog/the-new-defender/) 
- [Sobre Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Portais de segurança e centros de administração da Microsoft](portals.md)