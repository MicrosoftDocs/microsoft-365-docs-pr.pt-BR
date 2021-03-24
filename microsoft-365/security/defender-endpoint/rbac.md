---
title: Usar o controle de acesso baseado em função para conceder acesso fino ao Centro de Segurança do Microsoft Defender
description: Crie funções e grupos em suas operações de segurança para conceder acesso ao portal.
keywords: rbac, role, based, access, control, groups, control, tier, aad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d95163bd7caf6e05295fc35b3f9c2bf95230dc83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053294"
---
# <a name="manage-portal-access-using-role-based-access-control"></a>Gerenciar o acesso ao portal usando o controle de acesso baseado em função

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- Azure Active Directory
- Office 365

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-rbac-abovefoldlink)

Usando o controle de acesso baseado em função (RBAC), você pode criar funções e grupos em sua equipe de operações de segurança para conceder acesso apropriado ao portal. Com base nas funções e grupos que você cria, você tem um controle fino sobre o que os usuários com acesso ao portal podem ver e fazer. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bJ2a]

Grandes equipes de operações de segurança distribuídas geográficas geralmente adotam um modelo baseado em camadas para atribuir e autorizar o acesso a portais de segurança. As camadas típicas incluem os três níveis a seguir:

Camada | Descrição
:---|:---
Camada 1 | **Equipe de operações de segurança local/equipe de IT** <br> Essa equipe geralmente triagem e investiga alertas contidos em sua localização geográfica e escalona para a Camada 2 nos casos em que uma correção ativa é necessária.
Camada 2 | **Equipe de operações de segurança regional** <br> Essa equipe pode ver todos os dispositivos de sua região e executar ações de correção.
Camada 3 | **Equipe de operações de segurança global** <br> Essa equipe consiste em especialistas em segurança e está autorizada a ver e executar todas as ações do portal.

O Defender for Endpoint RBAC foi projetado para dar suporte ao seu modelo de escolha baseado em camada ou função e oferece controle granular sobre quais funções podem ser vistas, dispositivos que podem acessar e ações que podem ser tomadas. A estrutura do RBAC é centralizada em torno dos seguintes controles:

- **Controlar quem pode tomar medidas específicas**
  - Crie funções personalizadas e controle quais recursos do Defender for Endpoint podem acessar com granularidade.
 
- **Controlar quem pode ver informações sobre grupos ou grupos específicos de dispositivos**
  - [Crie grupos](machine-groups.md) de dispositivos por critérios específicos, como nomes, marcas, domínios e outros, em seguida, conceda acesso a função a eles usando um grupo de usuários específico do Azure Active Directory (Azure AD).

Para implementar o acesso baseado em função, você precisará definir funções de administrador, atribuir permissões correspondentes e atribuir grupos de usuários do Azure AD atribuídos às funções.


### <a name="before-you-begin"></a>Antes de começar
Antes de usar o RBAC, é importante que você entenda as funções que podem conceder permissões e as consequências de ligar o RBAC.


> [!WARNING]
> Antes de ativar o recurso, é importante que você tenha uma função de Administrador Global ou uma função de Administrador de Segurança no Azure AD e que você tenha seus grupos do Azure AD prontos para reduzir o risco de ser bloqueado fora do portal. 

Quando você faz logon pela primeira vez no Centro de Segurança do Microsoft Defender, você tem acesso total ou somente leitura. Direitos de acesso completo são concedidos aos usuários com funções de Administrador de Segurança ou Administrador Global no Azure AD. O acesso somente leitura é concedido aos usuários com uma função de Leitor de Segurança no Azure AD. 

Alguém com uma função de administrador do Defender para Ponto de Extremidade Global tem acesso irrestrito a todos os dispositivos, independentemente da associação do grupo de dispositivos e das atribuições de grupos de usuários do Azure AD

> [!WARNING]
> Inicialmente, somente aqueles com direitos de Administrador Global do Azure AD ou Administrador de Segurança poderão criar e atribuir funções no Centro de Segurança do Microsoft Defender, portanto, é importante ter os grupos certos prontos no Azure AD.
>
> **A ação do controle de acesso baseado em função fará com que os usuários com permissões somente leitura (por exemplo, usuários atribuídos à função de leitor de Segurança do Azure AD) percam acesso até que sejam atribuídos a uma função.** 
>
>Os usuários com permissões de administrador são atribuídos automaticamente à função de administrador global interna padrão do Defender para o Ponto de Extremidade com permissões completas. Depois de optar por usar o RBAC, você pode atribuir usuários adicionais que não sejam Azure AD Global ou Administradores de Segurança à função de administrador global do Defender for Endpoint. 
>
> Depois de optar por usar o RBAC, não é possível reverter para as funções iniciais como quando você fez logor pela primeira vez no portal. 



## <a name="related-topic"></a>Tópicos relacionados
- [Criar e gerenciar grupos de dispositivos no Microsoft Defender para Ponto de Extremidade](machine-groups.md)
