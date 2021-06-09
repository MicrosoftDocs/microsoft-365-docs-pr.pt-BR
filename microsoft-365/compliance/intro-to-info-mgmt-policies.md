---
title: Introdução às políticas de gerenciamento de informações
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2014
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- WSU150
- SPO160
- OSU150
- MET150
ms.assetid: 63a0b501-ba59-44b7-a35c-999f3be057b2
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Saiba como usar políticas de gerenciamento de informações para controlar e rastrear coisas como por quanto tempo o conteúdo é mantido ou quais ações os usuários podem tomar com esse conteúdo.
ms.openlocfilehash: dfb1aeb3dbd3a2b17f18bbd03d5f4d3e198e4c47
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815508"
---
# <a name="introduction-to-information-management-policies"></a>Introdução às políticas de gerenciamento de informações

Uma política de gerenciamento de informações é um conjunto de regras aplicáveis a um tipo de conteúdo. As políticas de gerenciamento de informações permitem que as organizações controlem e rastreiem o tempo em que um documento é retido ou quais ações os usuários podem realizar com esse conteúdo, dentre outras coisas. Essas políticas podem ajudar as organizações a cumprir regulamentações legais ou governamentais, ou podem simplesmente impor processos comerciais internos. 
  
Por exemplo, uma organização que deve seguir as regulamentações governamentais que exigem que eles demonstrem "controles adequados" de suas demonstrações financeiras pode criar uma ou mais políticas de gerenciamento de informações que auditam ações específicas no processo de criação e aprovação de todos os documentos relacionados a arquivamentos financeiros.
  
Para obter informações sobre como fazer isso, consulte [Criar e aplicar políticas de gerenciamento de informações.](create-info-mgmt-policies.md)
  
## <a name="features-of-information-management-policies"></a>Recursos das políticas de gerenciamento de informações
<a name="__top"> </a>

Há quatro categorias básicas de recursos de política predefinidos que as organizações podem usar individualmente ou em combinação para gerenciar conteúdo e processos. 
  
![Tipos de políticas de conteúdo](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
O recurso de política de auditoria ajuda as organizações a analisar como seus sistemas de gerenciamento de conteúdo são usados por eventos de registro em log e operações executadas em documentos e itens de lista. Você pode configurar o recurso de política de Auditoria para registrar eventos, como quando um documento ou item é editado, exibido, verificado, check-out, excluído ou tem suas permissões alteradas. Todas as informações de auditoria são armazenadas em um único log de auditoria no servidor, e os administradores do site podem executar relatórios nele. 
  
O recurso de política de expiração ajuda as organizações a excluir ou remover conteúdo desapagado de seus sites de forma consistente e rastreável. Isso ajuda você a gerenciar o custo e o risco associados à retenção de conteúdo desassociado. Você pode configurar uma política de Expiração para especificar que determinados tipos de conteúdo expiram em uma data específica ou dentro de um período de tempo após a criação ou última modificação do documento.
  
As organizações também podem criar e implantar recursos de política personalizados para atender a necessidades específicas. Por exemplo, uma organização de manufatura pode querer definir uma política de gerenciamento de informações para todos os documentos de especificação de design de produto de rascunho que proíbem os usuários de imprimir cópias desses documentos em impressoras não seguras. Para definir esse tipo de política de gerenciamento de informações, você pode criar e implantar um recurso de política de Restrição de Impressão que pode ser adicionado à política de gerenciamento de informações relevante para o tipo de conteúdo de especificação de design do produto.
  
## <a name="locations-to-use-an-information-management-policy"></a>Locais para usar uma política de gerenciamento de informações
<a name="__toc340213528"> </a>

Para implementar uma política de gerenciamento de informações, você deve adicioná-la a uma lista, biblioteca ou tipo de conteúdo em um site. O local onde você cria ou adiciona uma política de gerenciamento de informações afeta a ampla aplicação da política ou a ampla utilização dela. Você pode:
  
 **Criar uma política de conjunto de sites e, em seguida, adicionar essa política a um tipo de conteúdo, lista ou biblioteca** Você pode criar uma política de conjunto de sites na lista Políticas no site de nível superior de um conjunto de sites. Depois de criar uma política de conjunto de sites, você pode exportá-la para que os administradores de outros conjunto de sites possam importá-la para sua lista de Políticas. A criação de uma política de conjunto de sites exportável permite padronizar as políticas de gerenciamento de informações em todos os sites em sua organização. 
  
Quando você adiciona uma política de conjunto de sites a um tipo de conteúdo de site e uma instância desse tipo de conteúdo de site é adicionada a uma lista ou biblioteca, o proprietário dessa lista ou biblioteca não pode modificar a política de conjunto de sites para a lista ou biblioteca. Adicionar uma política de conjunto de sites a um tipo de conteúdo de site é uma boa maneira de garantir que as políticas de conjunto de sites sejam impostas em cada nível da hierarquia do site.
  
![Link modelo de política de tipo de conteúdo na página Site Configurações página](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
 **Crie uma política de gerenciamento** de informações para um tipo de conteúdo de site na Galeria de Tipos de Conteúdo de Site de nível superior e adicione esse tipo de conteúdo a uma ou mais listas ou bibliotecas Você também pode criar uma política de gerenciamento de informações diretamente para um tipo de conteúdo de site e associar uma instância desse tipo de conteúdo de site a várias listas ou bibliotecas. Se você criar uma política de gerenciamento de informações dessa forma, cada item no conjunto de sites desse tipo de conteúdo ou um tipo de conteúdo herdado desse tipo de conteúdo terá a política. No entanto, se você criar uma política de gerenciamento de informações diretamente para um tipo de conteúdo de site, será mais difícil reutilizar essa política de gerenciamento de informações em outros conjunto de sites, pois as políticas criadas dessa forma não podem ser exportadas. 
  
![Link de tipos de conteúdo do site na página Site Configurações site](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
![Link de política de gerenciamento de informações na página configurações de um tipo de conteúdo de site](../media/15d83a34-6c8f-4b6e-b6ee-e9b0a70cbb4b.png)
  
Observação Para controlar quais políticas são usadas em um conjunto de sites, os administradores do conjunto de sites podem desabilitar a capacidade de definir recursos de política diretamente em um tipo de conteúdo. Quando essa restrição está em vigor, os usuários que criam tipos de conteúdo são limitados à seleção de políticas na lista Políticas do conjunto de sites.
  
 **Criar uma política de gerenciamento de informações para uma lista ou biblioteca** Se sua organização precisar aplicar uma política de gerenciamento de informações específica a um conjunto muito limitado de conteúdo, você poderá criar uma política de gerenciamento de informações que se aplique apenas a uma lista ou biblioteca individual. Esse método de criação de uma política de gerenciamento de informações é o menos flexível, pois a política se aplica apenas a um local e não pode ser exportada ou reutilizável para outros locais. No entanto, às vezes, talvez seja necessário criar políticas exclusivas de gerenciamento de informações com aplicabilidade limitada para resolver situações específicas. 
  
![Link de políticas de gerenciamento de informações na página configurações da biblioteca de documentos](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
Observações 
  
Você só poderá criar uma política de gerenciamento de informações para uma lista ou biblioteca se essa lista ou biblioteca não suportar vários tipos de conteúdo. Se uma lista ou biblioteca for compatível com vários tipos de conteúdo, você precisará definir uma política de gerenciamento de informações para cada tipo de conteúdo de lista individual associado a essa lista ou biblioteca. (Instâncias de um tipo de conteúdo de site associado a uma lista ou biblioteca específica são conhecidas como tipos de conteúdo de lista.)
  
Para controlar quais políticas são usadas em um conjunto de sites, os administradores do conjunto de sites podem desabilitar a capacidade de definir recursos de política diretamente em uma lista ou biblioteca. Quando essa restrição está em vigor, os usuários que gerenciam listas ou bibliotecas são limitados a selecionar políticas na lista Políticas do conjunto de sites.
  
[Uma política de gerenciamento de informações é um conjunto de regras para um tipo de conteúdo. As políticas de gerenciamento de informações permitem que as organizações controlem e rastreiem coisas como por quanto tempo o conteúdo é mantido ou quais ações os usuários podem tomar com esse conteúdo. As políticas de gerenciamento de informações podem ajudar as organizações a cumprir regulamentos legais ou governamentais ou podem simplesmente impor processos comerciais internos. Por exemplo, uma organização que deve seguir as regulamentações governamentais que exigem que eles demonstrem "controles adequados" de suas demonstrações financeiras pode criar uma ou mais políticas de gerenciamento de informações que auditam ações específicas no processo de criação e aprovação de todos os documentos relacionados a arquivamentos financeiros. Para obter informações sobre como fazer isso, consulte Criar e aplicar políticas de gerenciamento de informações.](intro-to-info-mgmt-policies.md#__top)
  

