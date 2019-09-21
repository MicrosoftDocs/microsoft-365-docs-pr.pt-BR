---
title: Configurar usuários e casos na descoberta eletrônica avançada do Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 'Saiba como configurar funções de usuário, criar ocorrências e atribuir usuários a casos na descoberta eletrônica avançada do Office 365.  '
ms.openlocfilehash: e53d304445aa7d171766d38496d95a0d6cb47792
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073110"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a>Configurar usuários e casos na descoberta eletrônica avançada do Office 365

Este tópico descreve como configurar usuários e casos para a descoberta eletrônica avançada do Office 365.
  
> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="prerequisites"></a>Pré-requisitos

Antes de configurar casos e usuários na descoberta eletrônica avançada, é necessário o seguinte:
  
- Para analisar os dados de um usuário usando a descoberta eletrônica avançada, o usuário (o responsáveis dos dados) deve receber uma licença do Office 365 e5. Como alternativa, os usuários com uma licença do Office 365 E1 ou E3 podem receber uma licença autônoma de descoberta eletrônica avançada. Administradores e gerentes de conformidade atribuídos aos casos e usar a descoberta eletrônica avançada para analisar os dados não precisam de uma licença e5. 
    
- Você precisa ser membro do grupo de função Gerenciador de descoberta eletrônica no centro de conformidade de &amp; segurança do Office 365 para criar um caso de descoberta eletrônica e adicionar membros a ele. Para se adicionar ao grupo de funções Gerenciador de descoberta eletrônica &amp; no centro de conformidade de segurança, você precisa ser um administrador global em sua organização do Office 365. Se você não for um administrador global, será necessário pedir a um administrador global para adicioná-lo ao grupo de funções Gerenciador de descoberta eletrônica. Para obter mais informações, consulte:
    
  - [Permissões no centro de conformidade de &amp; segurança do Microsoft 365](/security/office-365-security/protect-against-threats.md)
    
  - [Atribuir permissões de descoberta eletrônica no centro de &amp; conformidade de segurança do Microsoft 365](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a>Etapa 1: atribuir permissões de descoberta eletrônica de usuários

A primeira etapa é atribuir aos usuários as permissões de requisito no centro &amp; de conformidade de segurança para que eles possam ser adicionados como um membro de uma ocorrência de descoberta eletrônica. Após um usuário ser adicionado como um membro de um caso no centro de &amp; conformidade de segurança, ele poderá acessar o caso na descoberta eletrônica avançada.
  
Para atribuir a um usuário as permissões necessárias para que possam ser adicionadas como um membro de um caso de descoberta eletrônica, confira a etapa 1 em [casos &amp; de descoberta eletrônica no centro de conformidade de segurança do Microsoft 365](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a>Etapa 2: criar um caso de descoberta eletrônica e adicionar membros

A próxima etapa é criar uma nova ocorrência de descoberta eletrônica no centro &amp; de conformidade de segurança e adicionar membros. Os membros do caso serão capazes de acessar o caso na descoberta eletrônica avançada.
  
1. Para criar uma nova ocorrência de descoberta eletrônica, confira a etapa 2 em [casos de descoberta &amp; eletrônica no centro de conformidade de segurança do Microsoft 365](ediscovery-cases.md#step-2-create-a-new-case).
    
2. Para adicionar membros a um caso de descoberta eletrônica, confira a etapa 3 em [casos de descoberta &amp; eletrônica no centro de conformidade de segurança do Microsoft 365](ediscovery-cases.md#step-3-add-members-to-a-case)
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a>Etapa 3: usar uma descoberta eletrônica avançada

Após criar um caso de descoberta eletrônica e adicionar membros, você (ou qualquer membro do caso) pode acessar o caso correspondente na descoberta eletrônica avançada. Para acessar um caso na descoberta eletrônica avançada, confira a etapa 8 em [casos de descoberta eletrônica &amp; no centro de conformidade de segurança do Microsoft 365](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).
  
## <a name="see-also"></a>Confira também

[Descoberta Eletrônica Avançada do Office 365](office-365-advanced-ediscovery.md)
  
[Preparação de dados](prepare-data-for-advanced-ediscovery.md)
 
