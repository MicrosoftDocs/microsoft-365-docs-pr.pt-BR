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
description: Use os casos de Descoberta eDiscovery no Centro de Conformidade & segurança no Office 365 para gerenciar a investigação legal da sua organização.
ms.openlocfilehash: c052daab8de33e21cccc3c638ab4995a007f60fb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903455"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Gerenciar investigações legais no Microsoft 365

As organizações têm muitos motivos para responder a um caso jurídico envolvendo determinados executivos ou outros funcionários em sua organização. Isso pode envolver a localização e a retenção rápidas para obter mais informações específicas da investigação em emails, documentos, conversas de mensagens instantâneas e outros locais de conteúdo usados pelas pessoas em suas tarefas de trabalho diárias. Você pode executar essas e muitas outras atividades semelhantes usando as ferramentas de caso de Descoberta eDiscovery no centro de segurança e conformidade.
  
**Quer saber como a Microsoft gerencia suas investigações de Descobertas EDiscovery?** Aqui está um white [paper](https://go.microsoft.com/fwlink/?linkid=852161) técnico que você pode baixar que explica como usamos as mesmas ferramentas de pesquisa e investigação para gerenciar nosso fluxo de trabalho de Descoberta Eletrônico interno.

## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Gerenciar investigações legais com casos de Descoberta e Descoberta

Os casos de Descoberta Livre permitem que você controle quem pode criar, acessar e gerenciar casos de Descoberta eDiscovery em sua organização. Use os casos para adicionar membros e controlar quais tipos de ações podem ser realizadas, colocar uma responsabilidade sobre locais de conteúdo relevantes para um caso legal e usar a ferramenta Pesquisa de Conteúdo para pesquisar os locais em espera por conteúdo que possa responder ao seu caso. Em seguida, você também pode exportar e baixar esses resultados para investigação posterior por revisores externos.
  
- [Gerencie seu fluxo de](./get-started-core-ediscovery.md) trabalho de Descoberta Eletrônico criando e usando casos de Descoberta Eletrônico para cada investigação legal que sua organização precisa realizar.

- [Atribua permissões de Descoberta eDiscovery](assign-ediscovery-permissions.md) para controlar quem pode criar e gerenciar casos de Descoberta eDiscovery em sua organização.

- [Configurar limites de conformidade para](set-up-compliance-boundaries.md) controlar os locais de conteúdo do usuário que os gerentes de Descoberta Desdiscovery podem pesquisar.

- [Pesquise](search-for-content.md) conteúdo em sua organização.

### <a name="use-scripts-for-advanced-scenarios"></a>Usar scripts para cenários avançados

Como a seção anterior que listava scripts para cenários de pesquisa de conteúdo &, também criamos alguns scripts do Centro de Conformidade e Segurança do PowerShell para ajudá-lo a gerenciar casos de Descoberta eDiscovery.
  
- [Crie um relatório de](create-a-report-on-holds-in-ediscovery-cases.md) responsabilidade de Descoberta e Que contém informações sobre todas as resções associadas a casos de Descoberta eDiscovery em sua organização.

- [Adicione caixas de correio e OneDrive locais](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) para uma lista de usuários a uma espera de Descoberta Eletrônico.
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>Gerenciar investigações legais com a solução Advanced eDiscovery no Microsoft 365

A Advanced eDiscovery em Microsoft 365 se baseia nos recursos existentes de Descoberta e análise em Office 365. Essa nova solução, chamada *Advanced eDiscovery*, fornece um fluxo de trabalho de ponta a ponta para preservar, coletar, revisar, analisar e exportar conteúdo que responde às investigações internas e externas da sua organização. Ele também permite que sua equipe jurídica gerencie todo o fluxo de trabalho de notificação de responsabilidade para se comunicar com pessoas envolvidas no caso.

Advanced eDiscovery requer uma assinatura do E5 para sua Microsoft 365 ou Office 365 organização. Para obter mais informações sobre licenciamento, consulte [Configurar Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).

Aqui está uma visão geral rápida do fluxo de trabalho integrado no Advanced eDiscovery. Para obter mais informações, consulte [Manage the Advanced eDiscovery workflow](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow).

- [Crie um caso](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case) para começar.

- [Gerencie](managing-custodians.md) os custodiantes adicionando-os a um caso e colocando uma responsabilidade legal sobre o conteúdo em sua caixa de correio, OneDrive conta e Microsoft Teams que eles são membros.

- [Gerencie](managing-custodian-communications.md) comunicações com custodiantes automatizando o processo de notificação de espera legal.

- [Indexe dados de custodiante](processing-data-for-case.md) e corrige erros de indexação para que você possa coletar dados efetivamente para suas investigações.

- [Colete dados](collecting-data-for-ediscovery.md) para um caso e [adicione-os a um conjunto de revisão para](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) investigação posterior.

- [Exibir](view-documents-in-review-set.md) documentos, [dados de consulta](review-set-search.md) e itens de [marca](tagging-documents.md) em um conjunto de revisão.

- [Analisar dados de caso](analyzing-data-in-review-set.md) com ferramentas de análise avançadas.

- [Exportar dados de caso](exporting-data-ediscover20.md) para revisão por consultores externos.

- [Gerencie trabalhos de](managing-jobs-ediscovery20.md) longa duração Advanced eDiscovery.