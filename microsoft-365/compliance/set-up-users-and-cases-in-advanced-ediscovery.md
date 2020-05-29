---
title: Configurar usuários e casos na descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 'Saiba como configurar funções de usuário, criar ocorrências e atribuir usuários a casos na descoberta eletrônica avançada.  '
ms.openlocfilehash: 386be1201b30e6b0e7a46c9de47dd6cf2fc4b53c
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412800"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a>Configurar usuários e casos na descoberta eletrônica avançada (clássico)

Este tópico descreve como configurar usuários e casos para descoberta eletrônica avançada (clássica).
  
> [!IMPORTANT]
> À medida que continuamos investindo em versões mais recentes da Descoberta Eletrônica Avançada, anunciamos a retirada da Descoberta Eletrônica Avançada, também conhecida como *Descoberta Eletrônica Avançada (clássica)* ou *Descoberta Eletrônica Avançada v1.0*. Se você ainda estiver usando a Descoberta Eletrônica Avançada v1.0, faça a transição para o [Descoberta Eletrônica Avançada v2.0](overview-ediscovery-20.md) (também conhecida como * solução de Descoberta Eletrônica Avançada no Microsoft 365*) o mais rápido possível. O Descoberta Eletrônica Avançada 2.0 contém funcionalidade semelhante encontrada na Descoberta Eletrônica Avançada v1.0, mas também oferece muitos recursos novos, como gerenciamento de custódia, gerenciamento de comunicações e conjuntos de revisão. Para saber mais sobre a desativação da Descoberta Eletrônica Avançada v1.0, confira [Desativação de ferramentas legadas de Descoberta Eletrônica](legacy-ediscovery-retirement.md#advanced-ediscovery-v10). 
  
## <a name="prerequisites"></a>Pré-requisitos

Antes de configurar casos e usuários na descoberta eletrônica avançada, é necessário o seguinte:
  
- Para analisar os dados de um usuário usando a descoberta eletrônica avançada, o usuário (o responsáveis dos dados) deve receber uma licença do Office 365 e5. Como alternativa, os usuários com uma licença do Office 365 E1 ou E3 podem receber uma licença autônoma de descoberta eletrônica avançada. Administradores e gerentes de conformidade atribuídos aos casos e usar a descoberta eletrônica avançada para analisar os dados não precisam de uma licença e5. 
    
- Você precisa ser membro do grupo de função Gerenciador de descoberta eletrônica no centro de &amp; conformidade de segurança para criar um caso de descoberta eletrônica e adicionar membros a ela. Para se adicionar ao grupo de funções Gerenciador de descoberta eletrônica no centro de conformidade de segurança &amp; , você precisa ser um administrador global em sua organização. Se você não for um administrador global, será necessário pedir a um administrador global para adicioná-lo ao grupo de funções Gerenciador de descoberta eletrônica. Para saber mais, confira:
    
  - [Permissões no centro de conformidade de segurança do Microsoft 365 &amp;](~/security/office-365-security/protect-against-threats.md)
    
  - [Atribuir permissões de descoberta eletrônica no centro de conformidade de segurança do Microsoft 365 &amp;](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a>Etapa 1: atribuir permissões de descoberta eletrônica de usuários

A primeira etapa é atribuir aos usuários as permissões de requisito no centro de conformidade de segurança &amp; para que eles possam ser adicionados como um membro de uma ocorrência de descoberta eletrônica. Após um usuário ser adicionado como um membro de um caso no centro de &amp; conformidade de segurança, ele poderá acessar o caso na descoberta eletrônica avançada.
  
Para atribuir a um usuário as permissões necessárias para que possam ser adicionadas como um membro de um caso de descoberta eletrônica, confira a etapa 1 em [casos de descoberta eletrônica no &amp; centro de conformidade de segurança do Microsoft 365](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a>Etapa 2: criar um caso de descoberta eletrônica e adicionar membros

A próxima etapa é criar uma nova ocorrência de descoberta eletrônica no centro de conformidade & segurança e adicionar membros. Os membros do caso serão capazes de acessar o caso na descoberta eletrônica avançada.
  
1. Para criar uma nova ocorrência de descoberta eletrônica, confira a etapa 3 em introdução [à descoberta eletrônica Core](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case).

2. Para adicionar membros a um caso de descoberta eletrônica, confira a etapa 4 em introdução [à descoberta eletrônica principal](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)

## <a name="step-3-go-a-case-in-advanced-ediscovery"></a>Etapa 3: usar uma descoberta eletrônica avançada

Após criar um caso de descoberta eletrônica e adicionar membros, você (ou qualquer membro do caso) pode acessar o caso correspondente na descoberta eletrônica avançada. Para acessar um caso na descoberta eletrônica avançada, consulte [acessando um caso na descoberta eletrônica avançada](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery).
  
## <a name="see-also"></a>Também consulte

[Descoberta Eletrônica Avançada (clássica)](office-365-advanced-ediscovery.md)
  
[Preparando dados para descoberta eletrônica avançada (clássico)](prepare-data-for-advanced-ediscovery.md)
 