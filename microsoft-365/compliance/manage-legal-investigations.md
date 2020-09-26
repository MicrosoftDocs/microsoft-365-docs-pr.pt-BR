---
title: Gerenciar investigações legais no Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
ms.custom:
- seo-marvel-apr2020
description: Use casos de descoberta eletrônica no centro de conformidade & segurança no Office 365 para gerenciar a investigação legal da sua organização.
ms.openlocfilehash: edc9835cdbefa611af4c0906be5d3e1d0404c635
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285647"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Gerenciar investigações legais no Microsoft 365

As organizações têm vários motivos para responder a um caso jurídico que envolve determinados executivos ou outros funcionários em sua organização. Isso pode envolver rapidamente a localização e a retenção de informações específicas de investigação em emails, documentos, conversas de mensagens instantâneas e outros locais de conteúdo usados por pessoas em suas tarefas de trabalho diárias. Você pode executar essas e muitas outras atividades semelhantes usando as ferramentas de casos de descoberta eletrônica no centro de segurança e conformidade.
  
**Deseja saber como a Microsoft gerencia suas investigações de eDiscovery?** Este é um [White paper técnico](https://go.microsoft.com/fwlink/?linkid=852161) que você pode baixar, que explica como usamos as mesmas ferramentas de pesquisa e investigação para gerenciar nosso fluxo de trabalho de eDiscovery interno.
   
## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Gerenciar investigações legais com ocorrências de descoberta eletrônica

as ocorrências de descoberta eletrônica permitem que você controle quem pode criar, acessar e gerenciar casos de descoberta eletrônica em sua organização. Casos de uso para adicionar membros e controlar os tipos de ações que eles podem executar, colocar em espera os locais de conteúdo relevantes para um caso jurídico e usar a ferramenta de pesquisa de conteúdo para pesquisar os locais em espera para o conteúdo que pode ser responsivo ao seu caso. Em seguida, você também pode exportar e baixar esses resultados para obter mais investigações por revisores externos.
  
- [Gerencie seu fluxo de trabalho de descoberta eletrônica](ediscovery-cases.md) criando e usando casos de descoberta eletrônica para cada investigação legal que sua organização tenha para realizar 
    
- [Atribuir permissões de descoberta eletrônica](assign-ediscovery-permissions.md) para controlar quem pode criar e gerenciar ocorrências de descoberta eletrônica em sua organização 
    
- [Configurar limites de conformidade](tagging-and-assessment-in-advanced-ediscovery.md) para controlar os locais de conteúdo do usuário que os gerentes de descoberta eletrônica podem pesquisar 
    
- [Pesquisar conteúdo](search-for-content.md) em sua organização 
    
### <a name="use-scripts-for-advanced-scenarios"></a>Usar scripts para cenários avançados

Como a seção anterior que listava scripts para cenários de pesquisa de conteúdo, também criamos alguns scripts do PowerShell de segurança & centro de conformidade para ajudá-lo a gerenciar ocorrências de descoberta eletrônica.
  
- [Criar um relatório de retenção de descoberta eletrônica](create-a-report-on-holds-in-ediscovery-cases.md) que contenha informações sobre todas as isenções associadas a ocorrências de descoberta eletrônica em sua organização 
    
- [Adicionar caixas de correio e locais do onedrive](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) para uma lista de usuários a uma retenção de descoberta eletrônica 
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>Gerenciar investigações legais com a solução de descoberta eletrônica avançada no Microsoft 365

A solução de descoberta eletrônica avançada no Microsoft 365 baseia-se nos recursos de descoberta eletrônica e análise existentes no Office 365. Essa nova solução, chamada de *descoberta eletrônica avançada*, fornece um fluxo de trabalho de ponta a ponta para preservar, coletar, analisar, analisar e exportar conteúdo que responde às investigações internas e externas da sua organização. Também permite que as equipes jurídicas gerenciem todo o fluxo de trabalho de notificação de retenção legal para se comunicarem com os responsáveis envolvidos em um caso.

A descoberta eletrônica avançada requer uma assinatura E5 para sua organização do Microsoft 365 ou do Office 365. Para obter mais informações sobre licenciamento, confira [introdução à descoberta eletrônica avançada](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).

Veja uma rápida visão geral do fluxo de trabalho interno na descoberta eletrônica avançada. Para obter mais informações, consulte [explorar o fluxo de trabalho de descoberta eletrônica avançada](get-started-with-advanced-ediscovery.md#explore-the-advanced-ediscovery-workflow).

- [Criar uma ocorrência](create-new-ediscovery-case.md) para começar

- [Gerencie os responsáveis](managing-custodians.md) adicionando-os a um caso e colocando um bloqueio legal no conteúdo da caixa de correio, da conta do onedrive e do Microsoft Teams dos quais eles são membros

- [Gerenciar comunicações](managing-custodian-communications.md) com os responsáveis automatizando o processo de notificação de retenção legal

- [Indexar dados dos responsáveis](processing-data-for-case.md) e corrigir erros de indexação para que você possa coletar dados efetivamente para suas investigações

- [Coletar dados](collecting-data-for-ediscovery.md) de um caso e adicionar [o suplemento a um conjunto de revisão para uma](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) investigação adicional

- [Exibir ](view-documents-in-review-set.md) documentos, dados de [consulta](review-set-search.md) e itens de [marca](tagging-documents.md) em um conjunto de revisão

- [Analisar dados de caso](analyzing-data-in-review-set.md) com ferramentas avançadas de análise

- [Exportar dados de caso](exporting-data-ediscover20.md) para análise por consultor exterior

- [Gerenciar trabalhos de longa execução](managing-jobs-ediscovery20.md) na descoberta eletrônica avançada
