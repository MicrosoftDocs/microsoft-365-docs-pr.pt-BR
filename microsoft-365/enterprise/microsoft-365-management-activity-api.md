---
title: API da Atividade de Gerenciamento do Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-analytics
f1.keywords:
- NOCSH
description: Neste artigo, você pode encontrar um breve resumo sobre a API da atividade de gerenciamento do Office 365 e as informações que ele fornece dos logs de atividades.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ea08673f4c26c9ee4b7093ba420b69bed91abc81
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687395"
---
# <a name="office-365-management-activity-api"></a>API da Atividade de Gerenciamento do Office 365

A Microsoft fornece o Reporting Services que você pode usar para obter informações transacionais agregadas sobre o locatário do Office 365. A [API de atividade de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview#office-365-management-activity-api) usa um design RESTful padrão da indústria e o OAuth v2 para autenticação. Isso facilita a tarefa de começar a experimentar a recuperação de dados e a inclusão em ferramentas e aplicativos de visualização. A API fornece um feed de dados com informações sobre o usuário, administrador, operações e atividade de segurança no Office 365. Os dados podem ser mantidos por razões regulamentares ou combinados com os dados de log obtidos de uma infraestrutura local ou de outras fontes. Isso ajuda a criar uma solução de monitoramento para operações, segurança e conformidade em toda a empresa.

A API da Atividade de Gerenciamento do Office 365 fornece informações sobre várias ações e eventos de usuário, administração, sistema e políticas dos logs de atividades do Office 365 e do Azure Active Directory. A API fornece um esquema de auditoria consistente com mais de 10 campos comuns em todos os serviços. A API permite que as organizações façam conexões fáceis entre eventos e permite que as novas maneiras de fazer isso nos dados.

Dezenas de ISVs (fornecedores independentes de software) parceiros com a Microsoft e criaram soluções com base na API. Algumas soluções se concentram exclusivamente nos dados do Office 365 e outros dados de origem de vários provedores de nuvem e sistemas locais para criar uma visão unificada das operações, segurança e atividade relacionada à conformidade. 

Para obter mais informações, consulte a [referência da API da atividade de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).
