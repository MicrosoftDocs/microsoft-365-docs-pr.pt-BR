---
title: Permissões de recurso no EOP
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 146bf34f157eb30e680ad9e0c3e53501d6e7b425
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638113"
---
# <a name="feature-permissions-in-eop"></a>Permissões de recurso no EOP

As permissões necessárias para executar tarefas para gerenciar o Exchange Online Protection (EOP) variam dependendo do recurso que você está gerenciando.

Para configurar o EOP, você deve ser um administrador global ou um administrador da empresa do Exchange (o grupo de funções Gerenciamento da organização).

## <a name="exchange-online-protection-permissions"></a>Permissões do Exchange Online Protection

Para descobrir quais permissões são necessárias para gerenciar os recursos do EOP, consulte a tabela a seguir. Se um recurso listar mais de um grupo de função, você só precisa estar atribuído a um dos grupos de função para usar o recurso.

|**Recurso**|**Permissões obrigatórias**|
|:-----|:-----|
|Antimalware|Gerenciamento de Organização <br/><br/> Gerenciamento de Higienização|
|Antispam|Gerenciamento de Organização <br/><br/> Gerenciamento de Higienização|
|Regras do fluxo de email|Gerenciamento de Organização <br/><br/> Gerenciamento de Registros|
|Domínios|Gerenciamento de Organização <br/><br/> Gerenciamento de Organização Somente Exibição|
|Proteção Avançada contra Ameaças (ATP)|Gerenciamento de Organização <br/><br/> Gerenciamento de Higienização|
|Conectores do Microsoft 365|Gerenciamento de Organização|
|Rastreamento de mensagens|Gerenciamento de Organização <br/><br/> Gerenciamento de Organização Somente Exibição|
|Configuração da organização|Gerenciamento de Organização|
|Quarentena|Gerenciamento de Organização <br/><br/> Gerenciamento de Organização Somente Exibição <br/><br/> Gerenciamento de Higienização|
|Usuários, contatos e grupos de função|Gerenciamento de Organização <br/><br/> Gerenciamento de Organização Somente Exibição <br/><br/> Gerenciamento de Higienização|
|Grupos de Distribuição e Grupos de Segurança|Gerenciamento de Organização <br/><br/> Gerenciamento de Organização Somente Exibição <br/><br/> Gerenciamento de Higienização|
|Exibir relatórios|Gerenciamento da organização: acesso a relatórios de proteção de email. <br/><br/> Destinatários somente para exibição: acesso a relatórios de proteção de email.  <br/><br/> Gerenciamento de conformidade: acesso a relatórios de proteção de email e relatórios de prevenção contra perda de dados (DLP) (se sua assinatura tiver recursos de DLP).|
