---
title: Redirecionando contas do Office 365 De segurança e conformidade para o novo Microsoft 365 Defender
description: Como redirecionar do Defender para Office 365 para Microsoft 365 Defender.
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
ms.openlocfilehash: f13e8235eb5f70e2d851b9b8b7600913d4e4023f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842513"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a>Redirecionando contas do Office 365 De segurança e conformidade para o Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender
- O que é o Defender para Office 365?

Este artigo explica como rotear contas para o Microsoft 365 Defender habilitando o redirecionamento automático do antigo Centro de Conformidade e Segurança do Office 365 (protection.office.com) para o Microsoft 365 Defender (security.microsoft.com).

## <a name="what-to-expect"></a>O que esperar
Depois que o redirecionamento automático for habilitado e ativo, os usuários que acessarem os recursos relacionados à segurança no Office 365 Security and Compliance (protection.office.com), serão automaticamente roteados para o Microsoft 365 Defender ( https://security.microsoft.com) .  

Saiba mais sobre o que mudou: [Microsoft Defender para Office 365 no Microsoft 365 Defender](microsoft-365-security-center-mdo.md).

Com o redirecionamento automático ligado, os usuários serão roteados para o Microsoft 365 Defender quando usarem recursos de segurança no Centro de Conformidade e Segurança Office 365.

Eles incluem recursos na seção Gerenciamento de Ameaças e no painel e relatórios de Gerenciamento de Ameaças. Os itens no centro Office 365 segurança e conformidade que não estão relacionados à segurança não são redirecionados para o Microsoft 365 Defender.

Os itens relacionados à conformidade podem ser encontrados no centro de conformidade do Microsoft 365, e os itens relacionados ao fluxo de emails podem ser encontrados no centro de administração Exchange de email.

Todos os outros recursos, sejam eles relacionados à conformidade ou aos recursos que atendem a ambos, não são afetados pelo redirecionamento. Office 365 alertas de segurança aparecem no Microsoft 365 Defender e no centro Office 365 Segurança e Conformidade, sem redirecionamento.  

### <a name="set-up-portal-redirection"></a>Configurar redirecionamento de portal
Para iniciar o roteamento de contas Microsoft 365 Defender em security.microsoft.com:

1. Certifique-se de ser um administrador global ou ter permissões de administrador de segurança no Azure Active directory.
2. [Entre no](https://security.microsoft.com/) Microsoft 365 Defender.
3. Navegue **até Configurações** Email &  >  **portal** de colaboração  >  **redirecionamento**.  
4. Alterne a configuração de redirecionamento automático para **On**.
5. Clique **em Habilitar** para aplicar redirecionamento automático ao Microsoft 365 Defender.

> [!NOTE]
> Depois que o redirecionamento estiver habilitado, as contas em sessões ativas enquanto essa configuração for aplicada não serão ejetadas de suas sessões e serão roteadas somente para o Microsoft 365 Defender depois de encerrar a sessão atual e entrar novamente.

## <a name="can-i-go-back-to-using-the-former-portal"></a>Posso voltar a usar o portal anterior?
Se algo não estiver funcionando para você ou se houver algo que você não consiga concluir por meio do Microsoft 365 Defender, queremos ouvir sobre isso usando a opção de feedback do portal. Se você tiver encontrado algum problema com redirecionamento, por favor, nos avise.

Para reverter para o portal anterior:

1. [Entre no](https://security.microsoft.com/) Microsoft 365 Defender como administrador global ou usando e conta com permissões de administrador de segurança no Azure Active directory.

2. Navegue **até Configurações** Email &  >  **portal** de colaboração  >  **redirecionamento**.   

3. Alterne a configuração de redirecionamento automático para **Off**.

4. Clique **em Desabilitar** & comentários de compartilhamento quando solicitado.

Essa configuração pode ser habilitada novamente a qualquer momento.

Depois de desabilitada, as contas não serão mais roteadas para security.microsoft.com, e você terá novamente acesso ao portal anterior — securitycenter.windows.com ou securitycenter.microsoft.com.

## <a name="related-information"></a>Informações relacionadas
- [Microsoft 365 Visão geral do Defender](overview-security-center.md)
- [Microsoft Defender para Ponto de Extremidade no Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [A Microsoft oferece SIEM e XDR unificados para modernizar operações de segurança](https://www.microsoft.com/security/blog/?p=91813) 
- [Infográfico XDR versus SIEM](https://afrait.com/blog/xdr-versus-siem/) 
- [O Novo Defensor](https://afrait.com/blog/the-new-defender/) 
- [Sobre Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Portais de segurança e centros de administração da Microsoft](portals.md)
