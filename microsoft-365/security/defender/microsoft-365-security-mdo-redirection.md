---
title: Redirecionando contas do Microsoft Defender para o Office 365 para o novo centro de segurança do Microsoft 365
description: Como redirecionar do Defender para o Office 365 para o centro de segurança do Microsoft 365.
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
ms.openlocfilehash: ce8c178b4c46a00b83833f008080b776f4dc7e60
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053494"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a>Redirecionando contas do Microsoft Defender para o Office 365 para o centro de segurança do Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender
- O que é o Defender para Office 365?

Este artigo explica como rotear contas para o centro de segurança do Microsoft 365 habilitando o redirecionamento automático do antigo Centro de Conformidade e Segurança da Microsoft (protection.office.com ou securitycenter.microsoft.com), para o centro de segurança do Microsoft 365 (security.microsoft.com).

>[!NOTE]
> O recurso de redirecionamento de portal está disponível apenas para clientes do Office 365 E5 e do Microsoft Defender para Office P2

## <a name="what-to-expect"></a>O que esperar
Depois que o redirecionamento automático for habilitado e ativo, os usuários que acessarem os recursos relacionados à segurança no Office 365 Security and Compliance (protection.office.com), serão automaticamente roteados para o centro de segurança do Microsoft 365 ( https://security.microsoft.com) .  

Saiba mais sobre o que mudou: Microsoft Defender para Office 365 no centro de segurança [do Microsoft 365.](microsoft-365-security-center-mdo.md)

Com o redirecionamento automático ligado, os usuários serão roteados para o Centro de Segurança do Microsoft 365 quando usarem recursos de segurança no Centro de Conformidade e Segurança do Office 365.

Eles incluem recursos na seção Gerenciamento de Ameaças e no painel e relatórios de Gerenciamento de Ameaças. Itens no Centro de Conformidade e Segurança do Office 365 que não estão relacionados à segurança não são redirecionados para o centro de segurança do Microsoft 365.

Os itens relacionados à conformidade podem ser encontrados no centro de conformidade do Microsoft 365 e os itens relacionados ao fluxo de emails podem ser encontrados no centro de administração do Exchange.

Todos os outros recursos, sejam eles relacionados à conformidade ou aos recursos que atendem a ambos, não são afetados pelo redirecionamento. Os alertas de segurança do Office 365 aparecem no Centro de segurança do Microsoft 365 e no Centro de Conformidade e Segurança do Office 365, sem redirecionamento.  

### <a name="set-up-portal-redirection"></a>Configurar redirecionamento de portal
Para iniciar o roteamento de contas para o centro de segurança do Microsoft 365 em security.microsoft.com:

1. Certifique-se de ser um administrador global ou ter permissões de administrador de segurança no Azure Active directory.
2. [Entre no](https://security.microsoft.com/) centro de segurança do Microsoft 365.
3. Navegue **até Configurações**  >  **Email &**  >  **redirecionamento do Portal de colaboração**.  
4. Alterne a configuração de redirecionamento automático para **On**.
5. Clique **em Habilitar** para aplicar redirecionamento automático ao portal do Centro de Segurança do Microsoft 365.

> [!NOTE]
> Depois que o redirecionamento estiver habilitado, as contas em sessões ativas enquanto essa configuração for aplicada não serão ejetadas de suas sessões e serão roteadas apenas para o centro de segurança do Microsoft 365 depois de encerrar a sessão atual e entrar novamente.

## <a name="can-i-go-back-to-using-the-former-portal"></a>Posso voltar a usar o portal anterior?
Se algo não estiver funcionando para você ou se houver algo que você não consiga concluir por meio do portal do Centro de Segurança do Microsoft 365, queremos ouvir sobre isso usando a opção comentários do portal. Se você tiver encontrado algum problema com redirecionamento, recomendamos que você entre em contato com seu parceiro de PM diretamente por meio da visualização privada ou nos avise por meio do formulário De envio de comentários.

Para reverter para o portal anterior:

1. [Entre no](https://security.microsoft.com/) centro de segurança do Microsoft 365 como administrador global ou usando e conta com permissões de administrador de segurança no Azure Active directory.

2. Navegue **até Configurações**  >  **Endpoints**  >  **Redirecionamento**  >  **geral do Portal**.  

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