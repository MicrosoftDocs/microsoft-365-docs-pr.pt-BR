---
title: Microsoft 365 lidando com corrupção de dados
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: Este artigo explica a corrupção de dados no Microsoft 365 e os esforços feitos pela Microsoft para impedir e recuperar dados.
ms.openlocfilehash: 767be71bb08c49070488cc965165ac86e98836bd
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47331867"
---
# <a name="dealing-with-data-corruption-in-microsoft-365"></a>Lidando com corrupção de dados no Microsoft 365

Um dos aspectos desafiadores de execução de um serviço de nuvem em larga escala é como lidar com a corrupção de dados, considerando o grande volume de dados e sistemas independentes. A corrupção dos dados pode ser causada por:

- Erros de infraestrutura ou aplicativo, corrompendo parte ou todo o estado do aplicativo
- Problemas de hardware que resultam em perda de dados ou incapacidade de ler dados
- Erros operacionais humanos
- Hackers mal-intencionados e funcionários descontentes
- Incidentes em serviços externos que resultam em alguma perda de dados

Como a maior resiliência na integridade dos dados significa menos incidentes de corrupção de dados, a Microsoft criou os mecanismos de proteção da Microsoft 365 para evitar que os danos ocorram, bem como sistemas e processos que nos permitem recuperar dados, se o fizer. Os cheques e processos existem dentro dos vários estágios do processo de lançamento da engenharia para aumentar a resiliência contra corrupção de dados, incluindo:

- Design de sistema
- Organização e estrutura de código
- Revisão de código
- Testes de unidade, testes de integração e testes de sistema
- Testes/Gates dos fios de viagem

Nos ambientes de produção do Microsoft 365, a replicação de mesmo nível entre datacenters garante que haja sempre várias cópias ao vivo de qualquer dado. Imagens e scripts padrão são usados para recuperar servidores perdidos e dados replicados são usados para restaurar dados do cliente. Devido às verificações e processos de resiliência de dados internos, a Microsoft mantém backups somente da documentação do sistema de informações da Microsoft 365 (incluindo a documentação relacionada à segurança), usando a replicação interna do SharePoint Online e nossa ferramenta de repositório de código interno, depósito de origem. A documentação do sistema está armazenada no SharePoint Online e o depósito de origem contém imagens de sistema e de aplicativo. O SharePoint Online e o Source Depot usam o controle de versão e são replicados praticamente em tempo real.
