---
title: Configurar políticas antispam
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 6/9/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 31279431-828d-48bd-b979-20b6de15fa4a
ms.collection:
- M365-security-compliance
description: A filtragem de spam é automaticamente habilitada em toda a empresa por meio das políticas antispam padrão (filtro de conexão, filtro de spam e spam de saída). Como administrador, você pode exibir e editar, mas não excluir, as políticas antispam padrão de forma que elas sejam ajustadas para atender melhor às necessidades da sua organização. Para maior granularidade, você também pode criar políticas personalizadas e aplicá-las a usuários, grupos ou domínios especificados em sua organização. Por padrão, as políticas personalizadas têm precedência sobre a política padrão, mas é possível alterar a prioridade de suas políticas.
ms.openlocfilehash: 2ee5833bf476123a84411a7ad645b9f8c5d0b2b8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599578"
---
# <a name="configure-the-anti-spam-policies"></a>Configurar políticas antispam

A filtragem de spam é automaticamente habilitada em toda a empresa por meio das políticas antispam padrão (filtro de conexão, filtro de spam e spam de saída). Como administrador, você pode exibir e editar, mas não excluir, as políticas antispam padrão de forma que elas sejam ajustadas para atender melhor às necessidades da sua organização. Para maior granularidade, você também pode criar políticas personalizadas e aplicá-las a usuários, grupos ou domínios especificados em sua organização. Por padrão, as políticas personalizadas têm precedência sobre a política padrão, mas é possível alterar a prioridade de suas políticas. 
  
Para obter mais informações sobre como configurar suas políticas contra spam, consulte os seguintes tópicos:
  
[Configurar a política do filtro de conexão](configure-the-connection-filter-policy.md)
  
[Configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> Para os clientes independentes do EOP: Por padrão, os filtros de conteúdo do EOP enviam as mensagens detectadas como spam para a pasta Lixo Eletrônico de cada destinatário. No entanto, para garantir que a ação **mover mensagem para a pasta lixo eletrônico** funcione com caixas de correio locais, você deve configurar duas regras de fluxo de mensagens do Exchange (também conhecidas como regras de transporte) em seus servidores locais para detectar cabeçalhos de spam adicionados pelo EOP. Para obter detalhes, consulte [Garantir que o spam seja direcionado para a pasta Lixo Eletrônico de cada usuário](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
[Configuração da política de spam de saída](configure-the-outbound-spam-policy.md)
  

