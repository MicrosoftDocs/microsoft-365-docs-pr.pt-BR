---
title: Redirecionando contas do Office 365 De segurança e conformidade para o novo centro de Microsoft 365 de segurança
description: Como redirecionar do Defender para Office 365 para o Microsoft 365 de segurança.
keywords: Microsoft 365 de segurança, Iniciando com o centro de segurança Microsoft 365, redirecionamento do centro de segurança
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
ms.openlocfilehash: 703d3c3c9086aa2bdfada560c009e8738dffbb18
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768964"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-security-center"></a>Redirecionando contas do Office 365 De segurança e conformidade para Microsoft 365 central de segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender
- O que é o Defender para Office 365?

Este artigo explica como rotear contas para o centro de segurança do Microsoft 365 habilitando o redirecionamento automático do antigo Centro de Conformidade e Segurança do Office 365 (protection.office.com) para o centro de segurança Microsoft 365 (security.microsoft.com).

## <a name="what-to-expect"></a>O que esperar
Depois que o redirecionamento automático for habilitado e ativo, os usuários que acessarem os recursos relacionados à segurança no Office 365 Security and Compliance (protection.office.com), serão automaticamente roteados para o centro de segurança do Microsoft 365 ( https://security.microsoft.com) .  

Saiba mais sobre o que mudou: [o Microsoft Defender para Office 365 no centro Microsoft 365 segurança.](microsoft-365-security-center-mdo.md)

Com o redirecionamento automático ligado, os usuários serão roteados para o centro de segurança Microsoft 365 quando usarem recursos de segurança no Centro de Conformidade e Segurança Office 365.

Eles incluem recursos na seção Gerenciamento de Ameaças e no painel e relatórios de Gerenciamento de Ameaças. Os itens no centro Office 365 segurança e conformidade que não estão relacionados à segurança não são redirecionados para o Microsoft 365 de segurança.

Os itens relacionados à conformidade podem ser encontrados no centro de conformidade do Microsoft 365, e os itens relacionados ao fluxo de emails podem ser encontrados no centro de administração Exchange de email.

Todos os outros recursos, sejam eles relacionados à conformidade ou aos recursos que atendem a ambos, não são afetados pelo redirecionamento. Office 365 alertas de segurança aparecem no centro de segurança Microsoft 365 e no centro Office 365 Segurança e Conformidade, sem redirecionamento.  

### <a name="set-up-portal-redirection"></a>Configurar redirecionamento de portal
Para iniciar o roteamento de contas para o Microsoft 365 de segurança em security.microsoft.com:

1. Certifique-se de ser um administrador global ou ter permissões de administrador de segurança no Azure Active directory.
2. [Entre no](https://security.microsoft.com/) centro de Microsoft 365 segurança.
3. Navegue **até Configurações** Email &  >  **portal** de colaboração  >  **redirecionamento**.  
4. Alterne a configuração de redirecionamento automático para **On**.
5. Clique **em Habilitar** para aplicar redirecionamento automático ao portal Microsoft 365 central de segurança.

> [!NOTE]
> Depois que o redirecionamento estiver habilitado, as contas em sessões ativas enquanto essa configuração for aplicada não serão ejetadas de suas sessões e serão roteadas apenas para o centro de segurança do Microsoft 365 depois de encerrar a sessão atual e entrar novamente.

## <a name="can-i-go-back-to-using-the-former-portal"></a>Posso voltar a usar o portal anterior?
Se algo não estiver funcionando para você ou se houver algo que você não consiga concluir por meio do portal do centro de segurança do Microsoft 365, queremos ouvir sobre isso usando a opção comentários do portal. Se você tiver encontrado algum problema com redirecionamento, por favor, nos avise.

Para reverter para o portal anterior:

1. [Entre no](https://security.microsoft.com/) centro de segurança Microsoft 365 como administrador global ou usando e conta com permissões de administrador de segurança no Azure Active directory.

2. Navegue **até Configurações** Email &  >  **portal** de colaboração  >  **redirecionamento**.   

3. Alterne a configuração de redirecionamento automático para **Off**.

4. Clique **em Desabilitar** & comentários de compartilhamento quando solicitado.

Essa configuração pode ser habilitada novamente a qualquer momento.

Depois de desabilitada, as contas não serão mais roteadas para security.microsoft.com, e você terá novamente acesso ao portal anterior — securitycenter.windows.com ou securitycenter.microsoft.com.

## <a name="related-information"></a>Informações relacionadas
- [Visão geral do Centro de segurança do Microsoft 365](overview-security-center.md)
- [Microsoft Defender para Ponto de Extremidade no centro de Microsoft 365 de segurança](microsoft-365-security-center-mde.md)
- [A Microsoft oferece SIEM e XDR unificados para modernizar operações de segurança](https://www.microsoft.com/security/blog/?p=91813) 
- [Infográfico XDR versus SIEM](https://afrait.com/blog/xdr-versus-siem/) 
- [O Novo Defensor](https://afrait.com/blog/the-new-defender/) 
- [Sobre Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Portais de segurança e centros de administração da Microsoft](portals.md)
