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
ms.openlocfilehash: 2129df7faaa977d59f8af8082291520d33bc9cc7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599308"
---
# <a name="feature-permissions-in-eop"></a>Permissões de recurso no EOP

As permissões necessárias para executar tarefas para gerenciar o Exchange Online Protection (EOP) variam dependendo do recurso que você está gerenciando.

Para configurar o EOP, você precisa ser um Administrador Global do Office 365 ou um Administrador da Empresa do Exchange (o grupo de funções Gerenciamento de Organização).

## <a name="exchange-online-protection-permissions"></a>Permissões do Exchange Online Protection

Para descobrir quais permissões são necessárias para gerenciar os recursos do EOP, consulte a tabela a seguir. Se um recurso listar mais de um grupo de função, você só precisa estar atribuído a um dos grupos de função para usar o recurso.

|**Recurso**|**Permissões obrigatórias**|
|:-----|:-----|
|Antimalware|Gerenciamento de Organização <br/><br/> Gerenciamento de Higienização|
|Antispam|Gerenciamento de Organização <br/><br/> Gerenciamento de Higienização|
|Regras do fluxo de email|Gerenciamento de Organização <br/><br/> Gerenciamento de Registros|
|Domínios|Gerenciamento de Organização <br/><br/> Gerenciamento de Organização Somente Exibição|
|Proteção Avançada contra Ameaças (ATP)|Gerenciamento de Organização <br/><br/> Gerenciamento de Higienização|
|Office 365 conectores|Gerenciamento de Organização|
|Rastreamento de mensagens|Gerenciamento de Organização <br/><br/> Gerenciamento de Organização Somente Exibição|
|Configuração da organização|Gerenciamento de Organização|
|Quarentena|Gerenciamento de Organização <br/><br/> Gerenciamento de Organização Somente Exibição <br/><br/> Gerenciamento de Higienização|
|Usuários, contatos e grupos de função|Gerenciamento de Organização <br/><br/> Gerenciamento de Organização Somente Exibição <br/><br/> Gerenciamento de Higienização|
|Grupos de Distribuição e Grupos de Segurança|Gerenciamento de Organização <br/><br/> Gerenciamento de Organização Somente Exibição <br/><br/> Gerenciamento de Higienização|
|Exibir relatórios|Gerenciamento da organização: acesso a relatórios de proteção de email. <br/><br/> Destinatários somente para exibição: acesso a relatórios de proteção de email.  <br/><br/> Gerenciamento de conformidade: acesso a relatórios de proteção de email e relatórios de prevenção contra perda de dados (DLP) (se sua assinatura tiver recursos de DLP).|
