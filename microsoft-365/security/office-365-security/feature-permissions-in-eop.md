---
title: Permissões de recurso no EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/30/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: As permissões necessárias para realizar tarefas para gerenciar o Microsoft Proteção do Exchange Online (EOP) variam dependendo do recurso que você está gerenciando.
ms.openlocfilehash: e3b41ea2b58397a9af2a1cb8ba979b5f816b416b
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031906"
---
# <a name="feature-permissions-in-eop"></a>Permissões de recurso no EOP

As permissões necessárias para executar tarefas para gerenciar o Exchange Online Protection (EOP) variam dependendo do recurso que você está gerenciando.

Para configurar o EOP, você precisa ser um Administrador Global do Office 365 ou um Administrador da Empresa do Exchange (o grupo de funções Gerenciamento de Organização).

## <a name="exchange-online-protection-permissions"></a>Permissões do Exchange Online Protection

Para descobrir quais permissões são necessárias para gerenciar os recursos do EOP, consulte a tabela a seguir. Se um recurso listar mais de um grupo de função, você só precisa estar atribuído a um dos grupos de função para usar o recurso.

|**Recurso**|**Permissões obrigatórias**|
|:-----|:-----|
|Antimalware|[Organization Management](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Gerenciamento de Higienização](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Antispam|[Gerenciamento da Organização](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Gerenciamento de Higienização](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Regras do fluxo de email|[Gerenciamento da Organização](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Records Management](https://technet.microsoft.com/library/0e0c95ce-6109-4591-b86d-c6cfd44d21f5.aspx)|
|Domínios|[Organization Management](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx)|
|Proteção avançada contra ameaças (ATP)|[Organization Management](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Gerenciamento de Higienização](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Office 365 conectores|[Organization Management](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx)|
|Rastreamento de mensagens|[Organization Management](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx)|
|Configuração da organização|[Organization Management](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx)|
|Quarentena|[Organization Management](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Usuários, contatos e grupos de função|[Organization Management](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Grupos de Distribuição e Grupos de Segurança|[Organization Management](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Exibir relatórios|[Organization Management](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) - os usuários têm acesso a relatórios de proteção de emails.  <br/> [View-Only Recipients](https://technet.microsoft.com/library/37e66b92-81d3-412f-b7a9-e1bb8cbeb468.aspx) - os usuários têm acesso a relatórios de proteção de emails.  <br/> [Compliance Management](https://technet.microsoft.com/library/b91b23a4-e9c7-4bd0-9ee3-ec5cb498da15.aspx) - os usuários têm acesso a relatórios de proteção de emails e relatórios DLP (Prevenção de Perda de Dados), desde que suas assinaturas tenham recursos DLP.|
