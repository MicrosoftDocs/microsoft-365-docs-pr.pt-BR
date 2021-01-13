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
description: Use ocorrências de Descoberta e No Centro de Conformidade & segurança no Office 365 para gerenciar a investigação legal da sua organização.
ms.openlocfilehash: 7a02bd47f93a85e643694efea4dcc140847916e0
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840700"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Gerenciar investigações legais no Microsoft 365

As organizações têm muitos motivos para responder a um caso jurídico envolvendo determinados executivos ou outros funcionários em sua organização. Isso pode envolver a localização e a retenção rápidas de informações específicas da investigação em emails, documentos, conversas de mensagens instantâneas e outros locais de conteúdo usados por pessoas em suas tarefas diárias de trabalho. Você pode executar essas e muitas outras atividades semelhantes usando as ferramentas de ocorrência de Descoberta e No centro de conformidade e segurança.
  
**Quer saber como a Microsoft gerencia suas investigações de Descobertas EDiscovery?** Aqui está um [white paper](https://go.microsoft.com/fwlink/?linkid=852161) técnico que você pode baixar e explica como usamos as mesmas ferramentas de pesquisa e investigação para gerenciar nosso fluxo de trabalho de Descoberta Eletrônico interno.

## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Gerenciar investigações legais com ocorrências de Descobertas

Os casos de Descoberta In-loco permitem controlar quem pode criar, acessar e gerenciar ocorrências de Descobertas Na organização. Use casos para adicionar membros e controlar quais tipos de ações eles podem executar, colocar uma espera em locais de conteúdo relevantes para um caso jurídico e usar a ferramenta de Pesquisa de Conteúdo para pesquisar os locais em espera por conteúdo que possa responder ao seu caso. Em seguida, você também pode exportar e baixar esses resultados para investigação posterior por revisores externos.
  
- [Gerencie seu fluxo de](ediscovery-cases.md) trabalho de Descoberta Eletrônico criando e usando ocorrências de Descoberta Eletrônico para cada investigação legal que sua organização precisa realizar.

- [Atribua permissões de Descoberta e para](assign-ediscovery-permissions.md) controlar quem pode criar e gerenciar ocorrências de Descobertas Na organização.

- [Configurar limites de conformidade para](set-up-compliance-boundaries.md) controlar os locais de conteúdo do usuário que os gerentes de Descobertas Descobertas podem pesquisar.

- [Pesquise](search-for-content.md) conteúdo em sua organização.

### <a name="use-scripts-for-advanced-scenarios"></a>Usar scripts para cenários avançados

Como a seção anterior que listou scripts para cenários de pesquisa de conteúdo &, também criamos alguns scripts do PowerShell do Centro de Conformidade e Segurança para ajudá-lo a gerenciar casos de Descoberta eDiscovery.
  
- [Crie um relatório de espera de](create-a-report-on-holds-in-ediscovery-cases.md) Descoberta eDiscovery que contenha informações sobre todas as retém associadas a ocorrências de Descobertas e Descobertas Na sua organização.

- [Adicione caixas de correio e locais do OneDrive](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) para uma lista de usuários a uma espera de Descoberta Eletrônico.
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>Gerenciar investigações legais com a solução descoberta de eDiscovery Avançada no Microsoft 365

A solução de Descoberta Avançada no Microsoft 365 se baseia nos recursos existentes de descoberta e análise no Office 365. Essa nova solução, chamada Decoberta Avançada, fornece um fluxo de trabalho de ponta a ponta para preservar, coletar, revisar, analisar e exportar conteúdo que responde às investigações internas e externas da sua organização.  Ele também permite que as equipes jurídicas gerenciem todo o fluxo de trabalho de notificação de responsabilidade legal para se comunicar com os responsáveis envolvidos em um caso.

A Descoberta Avançada exige uma assinatura do E5 para sua organização do Microsoft 365 ou Office 365. Para obter mais informações sobre licenciamento, [consulte Configurar a Descoberta Avançada.](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)

Aqui está uma visão geral rápida do fluxo de trabalho integrado na Descoberta Avançada. Para obter mais informações, [consulte Gerenciar o fluxo de trabalho de Descoberta Eletrônico Avançada.](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow)

- [Crie uma ocorrência](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case) para começar.

- [Gerencie custodiantes](managing-custodians.md) adicionando-os a uma ocorrência e colocando uma responsabilidade legal sobre o conteúdo em suas caixas de correio, conta do OneDrive e Microsoft Teams das qual eles são membros.

- [Gerencie](managing-custodian-communications.md) comunicações com custodiantes automatizando o processo de notificação de espera legal.

- [Index custodian data](processing-data-for-case.md) and fix indexing errors so you can effectively collect data for your investigations.

- [Coletar dados](collecting-data-for-ediscovery.md) para uma ocorrência e [adicioná-los a um conjunto de revisão para](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) investigação posterior.

- [Exibir](view-documents-in-review-set.md) documentos, [dados de consulta](review-set-search.md) e itens de [marca](tagging-documents.md) em um conjunto de revisão.

- [Analisar dados de caso](analyzing-data-in-review-set.md) com ferramentas de análise avançadas.

- [Exportar dados de caso](exporting-data-ediscover20.md) para revisão por consultoria externa.

- [Gerencie trabalhos de longa](managing-jobs-ediscovery20.md) duração na Descoberta Avançada.
