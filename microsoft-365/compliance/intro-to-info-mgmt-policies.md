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
description: Uma política de gerenciamento de informações é um conjunto de regras aplicáveis a um tipo de conteúdo. As políticas de gerenciamento de informações permitem que as organizações controlem e rastreiem o tempo em que um documento é retido ou quais ações os usuários podem realizar com esse conteúdo, dentre outras coisas. Essas políticas podem ajudar as organizações a cumprir regulamentações legais ou governamentais, ou podem simplesmente impor processos comerciais internos.
ms.openlocfilehash: 7f977090b147eca427fcd2e4b536821890493950
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072663"
---
# <a name="introduction-to-information-management-policies"></a>Introdução às políticas de gerenciamento de informações

Uma política de gerenciamento de informações é um conjunto de regras aplicáveis a um tipo de conteúdo. As políticas de gerenciamento de informações permitem que as organizações controlem e rastreiem o tempo em que um documento é retido ou quais ações os usuários podem realizar com esse conteúdo, dentre outras coisas. Essas políticas podem ajudar as organizações a cumprir regulamentações legais ou governamentais, ou podem simplesmente impor processos comerciais internos. 
  
Por exemplo, uma organização que deve seguir normas governamentais que exijam que eles demonstrem "controles adequados" de seus demonstrativos financeiros podem criar uma ou mais políticas de gerenciamento de informações que auditam ações específicas na criação e processo de aprovação para todos os documentos relacionados a arquivamentos financeiros.
  
Para obter informações sobre como fazer, confira [criar e aplicar políticas de gerenciamento de informações](create-info-mgmt-policies.md).
  
## <a name="features-of-information-management-policies"></a>Recursos de políticas de gerenciamento de informações
<a name="__top"> </a>

Há quatro categorias básicas de recursos predefinidos de política que as organizações podem usar individualmente ou em combinação para gerenciar o conteúdo e os processos. 
  
![Tipos de políticas de conteúdo](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
O recurso de política de auditoria ajuda as organizações a analisar como seus sistemas de gerenciamento de conteúdo são usados pelo registro em log de eventos e operações realizadas em documentos e itens de lista. Você pode configurar o recurso de política de auditoria para registrar eventos, como quando um documento ou item é editado, exibido, verificado, com check-out, excluído ou tem suas permissões alteradas. Todas as informações de auditoria são armazenadas em um único log de auditoria no servidor, e os administradores de site podem executar relatórios nele. 
  
O recurso de política de expiração ajuda as organizações a excluir ou remover conteúdo desatualizado de seus sites de forma consistente e rastreável. Isso ajuda você a gerenciar o custo e o risco associados à retenção de conteúdo desatualizado. Você pode configurar uma política de expiração para especificar que determinados tipos de conteúdo expirem em uma determinada data ou dentro de um período de tempo após o documento ter sido criado ou modificado pela última vez.
  
As organizações também podem criar e implantar recursos de política personalizados para atender a necessidades específicas. Por exemplo, uma organização de fabricação pode querer definir uma política de gerenciamento de informações para todos os documentos de especificação de design de produto de rascunho que proíbem os usuários de imprimir cópias desses documentos em impressoras não seguras. Para definir esse tipo de política de gerenciamento de informações, você pode criar e implantar um recurso de política de restrição de impressão que pode ser adicionado à política de gerenciamento de informações relevantes para o tipo de conteúdo de especificação de design de produto.
  
## <a name="locations-to-use-an-information-management-policy"></a>Locais para usar uma política de gerenciamento de informações
<a name="__toc340213528"> </a>

Para implementar uma política de gerenciamento de informações, você deve adicioná-la a uma lista, biblioteca ou tipo de conteúdo em um site. O local em que você cria ou adiciona uma política de gerenciamento de informações afeta o quão amplamente a política se aplica ou como ela pode ser usada de maneira ampla. Você pode:
  
 **Criar uma política de conjunto de sites e, em seguida, adicionar essa política a um tipo de conteúdo, lista ou biblioteca** Você pode criar uma política de conjunto de sites na lista de políticas no site de nível superior de um conjunto de sites. Depois de criar uma política de conjunto de sites, você pode exportá-la para que os administradores de outros conjuntos de sites possam importá-lo para a lista de políticas. A criação de uma política de conjunto de sites exportáveis permite padronizar as políticas de gerenciamento de informações nos sites da sua organização. 
  
Quando você adiciona uma política de conjunto de sites a um tipo de conteúdo de site e uma instância desse tipo de conteúdo de site é adicionada a uma lista ou biblioteca, o proprietário dessa lista ou biblioteca não pode modificar a política de conjunto de sites para a lista ou biblioteca. A adição de uma política de conjunto de sites a um tipo de conteúdo de site é uma boa maneira de garantir que as políticas de conjunto de sites sejam aplicadas em cada nível da hierarquia do site.
  
![Link do modelo de política de tipo de conteúdo na página Definições do site](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
 **Criar uma política de gerenciamento de informações para um tipo de conteúdo de site na Galeria de tipos de conteúdo do site de nível superior e adicionar esse tipo de conteúdo a uma ou mais listas ou bibliotecas** Você também pode criar uma política de gerenciamento de informações diretamente para um tipo de conteúdo de site e, em seguida, associar uma instância desse tipo de conteúdo de site a várias listas ou bibliotecas. Se você criar uma política de gerenciamento de informações dessa forma, cada item no conjunto de sites desse tipo de conteúdo ou um tipo de conteúdo que herda desse tipo de conteúdo terá a política. No entanto, se você criar uma política de gerenciamento de informações diretamente para um tipo de conteúdo de site, será mais difícil reutilizar essa política de gerenciamento de informações em outros conjuntos de sites, porque as políticas criadas dessa forma não podem ser exportadas. 
  
![Link tipos de conteúdo do site na página Configurações do site](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
![Link de política de gerenciamento de informações na página de configurações de um tipo de conteúdo de site](../media/15d83a34-6c8f-4b6e-b6ee-e9b0a70cbb4b.png)
  
Observação para controlar quais políticas são usadas em um conjunto de sites, os administradores de conjunto de sites podem desabilitar a capacidade de definir recursos de política diretamente em um tipo de conteúdo. Quando essa restrição é ativada, os usuários que criam tipos de conteúdo são limitados à seleção de políticas na lista de políticas de conjunto de sites.
  
 **Criar uma política de gerenciamento de informações para uma lista ou biblioteca** Se sua organização precisar aplicar uma política de gerenciamento de informações específica a um conjunto muito limitado de conteúdo, você pode criar uma política de gerenciamento de informações que se aplica apenas a uma lista ou biblioteca individual. Esse método de criação de uma política de gerenciamento de informações é o menos flexível, porque a política se aplica apenas a um local e não pode ser exportada ou reutilizada para outros locais. No entanto, às vezes você pode precisar criar políticas exclusivas de gerenciamento de informações com aplicabilidade limitada para tratar de situações específicas. 
  
![Link de políticas de gerenciamento de informações na página de configurações da biblioteca de documentos](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
Observações 
  
Você pode criar uma política de gerenciamento de informações para uma lista ou biblioteca somente se essa lista ou biblioteca não oferecer suporte a vários tipos de conteúdo. Se uma lista ou biblioteca oferecer suporte a vários tipos de conteúdo, você precisará definir uma política de gerenciamento de informações para cada tipo de conteúdo de lista individual associado a essa lista ou biblioteca. (Instâncias de um tipo de conteúdo de site que estão associados a uma lista ou biblioteca específica são conhecidas como tipos de conteúdo de lista.)
  
Para controlar quais políticas são usadas em um conjunto de sites, os administradores de conjunto de sites podem desabilitar a capacidade de definir recursos de política diretamente em uma lista ou biblioteca. Quando essa restrição estiver em vigor, os usuários que gerenciam listas ou bibliotecas são limitados a selecionar políticas na lista de políticas de conjunto de sites.
  
[Uma política de gerenciamento de informações é um conjunto de regras para um tipo de conteúdo. As políticas de gerenciamento de informações permitem que as organizações controlem e controlem coisas como o tempo de retenção de conteúdo ou as ações que os usuários podem realizar com esse conteúdo. As políticas de gerenciamento de informações podem ajudar as organizações a cumprir normas legais ou governamentais, ou podem simplesmente impor processos comerciais internos. Por exemplo, uma organização que deve seguir normas governamentais que exijam que eles demonstrem "controles adequados" de seus demonstrativos financeiros podem criar uma ou mais políticas de gerenciamento de informações que auditam ações específicas na criação e processo de aprovação para todos os documentos relacionados a arquivamentos financeiros. Para obter informações sobre como fazer, confira criar e aplicar políticas de gerenciamento de informações.](intro-to-info-mgmt-policies.md#__top)
  

