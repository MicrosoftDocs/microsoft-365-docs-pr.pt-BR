---
title: Redirecionando contas do Microsoft Defender para o Ponto de Extremidade para o centro de segurança do Microsoft 365
description: Como redirecionar contas e sessões do Defender para o Ponto de Extremidade para o centro de segurança do Microsoft 365.
keywords: Centro de segurança do Microsoft 365, Iniciando o centro de segurança do Microsoft 365, redirecionamento do centro de segurança
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
ms.openlocfilehash: c993977e0f052a7dc2e7827ff5bdefacee19ac2d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053495"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-the-microsoft-365-security-center"></a>Redirecionando contas do Microsoft Defender para o Ponto de Extremidade para o centro de segurança do Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Aplica-se a:**
- Microsoft 365 Defender
- Defender para Ponto de Extremidade

Em alinhamento com a abordagem entre domínios da Microsoft para proteção contra ameaças com SIEM e XDR (Detecção e resposta estendida), renomeamos a Proteção Avançada contra Ameaças do Microsoft Defender como Microsoft Defender para Ponto de Extremidade e unificamos-a em um único portal integrado - o Centro de segurança do Microsoft 365.

Este guia explica como rotear contas para o centro de segurança do Microsoft 365 habilitando o redirecionamento automático do antigo portal do Microsoft Defender para Ponto de Extremidade (securitycenter.windows.com ou securitycenter.microsoft.com), para o portal do Centro de Segurança do Microsoft 365 (security.microsoft.com).

> [!NOTE]
> O Microsoft Defender for Endpoint no centro de segurança do Microsoft 365 dá suporte à concessão de acesso a [MSSPs (provedores](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) de serviços de segurança gerenciados) da mesma forma que o acesso é concedido no centro de segurança do [Microsoft Defender.](./mssp-access.md)

## <a name="what-to-expect"></a>O que esperar
Depois que o redirecionamento automático for habilitado, as contas que acessam o antigo portal do Microsoft Defender para Ponto de Extremidade no securitycenter.windows.com ou securitycenter.microsoft.com, serão roteados automaticamente para o portal do Centro de Segurança do Microsoft 365 em security.microsoft.com.
 
Saiba mais sobre o que mudou: Microsoft Defender para Ponto de Extremidade no centro de segurança [do Microsoft 365.](microsoft-365-security-center-mde.md)

Isso inclui redirecionamento para acesso direto ao portal anterior por meio do navegador, incluindo links apontando para o antigo portal securitycenter.windows.com - como links em notificações de email e links retornados por chamadas de API SIEM.  

 Links externos de notificações por email ou APIs SIEM atualmente contêm links para ambos os portais. Depois que o redirecionamento for habilitado, ambos os links apontarão para o centro de segurança do Microsoft 365 até que o link antigo seja removido. Recomendamos que você adote o novo link apontando para o centro de segurança do Microsoft 365.

Consulte a tabela abaixo para obter mais informações sobre links e roteamento.
## <a name="siem-api-routing"></a>Roteamento de API SIEM

|**Propriedade**  |**Destino quando o redirecionamento está OFF**  |**Destino quando o redirecionamento está ON** | 
|---------|---------|---------|
| LinkToWDATP | Página de alerta no securitycenter.windows.com | Página de alerta em security.microsoft.com  |
| IncidentLinkToWDATP | Página incidente no securitycenter.windows.com  | Página de incidentes em security.microsoft.com  |
| LinkToMTP | Página de alerta em security.microsoft.com | Página de alerta em security.microsoft.com  |
| IncidentLinkToMTP | Página de incidentes em security.microsoft.com  | Página de incidentes em security.microsoft.com  

## <a name="email-alert-notifications"></a>Notificações de alerta de email

|**Propriedade**  |**Destino quando o redirecionamento está OFF**  |**Destino quando o redirecionamento está ON** |
|---------|---------|---------|
| Página alerta  | Página de alerta no securitycenter.windows.com  | Página de alerta em security.microsoft.com  |
| Página incidente  |Página incidente no securitycenter.windows.com  | Página de incidentes em security.microsoft.com  
| Página de alerta no portal do Centro de Segurança | Página de alerta em security.microsoft.com | Página de alerta em security.microsoft.com | 
| Página de incidentes no portal da central de segurança | Página de incidentes em security.microsoft.com  | Página de incidentes em security.microsoft.com  |

## <a name="when-does-this-take-effect"></a>Quando isso tem efeito? 
Depois de habilitada, essa atualização pode ter efeito quase imediatamente para algumas contas. Mas o redirecionamento pode levar mais tempo para se propagar para todas as contas da sua organização. As contas em sessões ativas enquanto essa configuração é aplicada não serão ejetadas de suas sessões e serão roteadas apenas para o centro de segurança do Microsoft 365 depois de encerrar a sessão atual e entrar novamente.  

### <a name="set-up-portal-redirection"></a>Configurar redirecionamento de portal
Para iniciar o roteamento de contas para o centro de segurança do Microsoft 365:
1. Certifique-se de ser um administrador global ou ter permissões de administrador de segurança no Azure Active directory 

2. [Entre no](https://security.microsoft.com/) centro de segurança do Microsoft 365.

3. Navegue **até Configurações**  >  **Endpoints**  >  **Redirecionamento**  >  **geral do Portal** ou clique [aqui](https://security.microsoft.com/preferences2/portal_redirection).  

4. Alterne a configuração de redirecionamento automático para **On**.

5. Clique **em Habilitar** para aplicar redirecionamento automático ao portal do Centro de Segurança do Microsoft 365.

>[!IMPORTANT]
>A habilitação dessa configuração não encerrará sessões de usuário ativas. As contas que estão em uma sessão ativa enquanto essa configuração é aplicada serão direcionadas apenas ao centro de segurança do Microsoft 365 depois de encerrar a sessão atual e entrar novamente.

>[!NOTE]
>Você deve ser um administrador global ou ter permissões de administrador de segurança no Azure Active Directory para habilitar ou desabilitar essa configuração.  

## <a name="can-i-go-back-to-using-the-former-portal"></a>Posso voltar a usar o portal anterior?
Se algo não estiver funcionando para você ou se houver algo que você não consiga concluir por meio do portal do Centro de Segurança do Microsoft 365, queremos saber mais sobre isso. Se você tiver encontrado algum problema com redirecionamento, recomendamos que você nos avise usando o formulário De envio de comentários.

Para reverter para o antigo portal do Microsoft Defender para Ponto de Extremidade:

1. [Entre no](https://security.microsoft.com/) centro de segurança do Microsoft 365 como administrador global ou usando e conta com permissões de administrador de segurança no Azure Active directory.

2. Navegue **até Configurações**  >  **Endpoints**  >  **Redirecionamento**  >  **geral do Portal** ou abra a página [aqui](https://security.microsoft.com/preferences2/portal_redirection).  

3. Alterne a configuração de redirecionamento automático para **Off**.

4. Clique **em Desabilitar** & comentários de compartilhamento quando solicitado.

Essa configuração pode ser habilitada novamente a qualquer momento. 

Depois de desabilitada, as contas não serão mais roteadas para security.microsoft.com, e você terá novamente acesso ao portal anterior - securitycenter.windows.com ou securitycenter.microsoft.com. 

## <a name="related-information"></a>Informações relacionadas
- [Visão geral do Centro de segurança do Microsoft 365](overview-security-center.md)
- [Microsoft Defender para Ponto de Extremidade no centro de segurança do Microsoft 365](microsoft-365-security-center-mde.md)
- [A Microsoft oferece SIEM e XDR unificados para modernizar operações de segurança](https://www.microsoft.com/security/blog/?p=91813) 
- [Infográfico XDR versus SIEM](https://afrait.com/blog/xdr-versus-siem/) 
- [O Novo Defensor](https://afrait.com/blog/the-new-defender/) 
- [Sobre o Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Portais de segurança e centros de administração da Microsoft](portals.md)