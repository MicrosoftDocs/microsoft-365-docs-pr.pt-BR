---
title: 'Adoção do Microsoft SharePoint Syntex: Começar'
description: Saiba como usar e implementar o SharePoint Syntex em sua organização para ajudá-lo a resolver seus problemas de negócios.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: e88a7de1c81995b878dbf8a9308fbc774583289e
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597053"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Adoção do Microsoft SharePoint Syntex: Começar

Pense nos serviços de conteúdo inteligentes disponíveis no SharePoint Syntex como tendo três partes:

- **Noções básicas sobre o conteúdo:** crie modelos de IA sem código para classificar e extrair informações do conteúdo para aplicar metadados automaticamente para descoberta e reutilização de conhecimento. Saiba mais sobre a [compreensão de conteúdo.](document-understanding-overview.md)
- **Processamento de conteúdo:** Automatize a captura, a ingestão e a categorização de conteúdo e simplifique processos centrados em conteúdo usando o Power Automate. Saiba mais sobre [o processamento de conteúdo.](form-processing-overview.md)
- **Conformidade de conteúdo:** Controle e gerencie o conteúdo para melhorar a segurança e a governança com a integração com a Proteção de Informações da Microsoft.

Com novos serviços e recursos de IA, você pode criar aplicativos de compreensão e classificação de conteúdo diretamente no fluxo de gerenciamento de conteúdo usando o SharePoint Syntex. Há duas maneiras diferentes de entender seu conteúdo. O tipo de modelo que você usa baseia-se no formato de arquivo e no caso de uso:

| Processamento de formulário | Compreensão do documento |
|:-------|:-------|
| Criado a partir da biblioteca de documentos. | Criado no centro de conteúdo, parte do SharePoint Syntex. |
| Modelo criado no construtor de IA. | Modelo criado na interface nativa. |
| Usado para formatos de arquivo semiestruturados. | Usado para formatos de arquivo não estruturados. |
| Classificador settable. | Classificador treinável com extratores opcionais. |
| Restrito a uma única biblioteca. | Pode ser aplicado a várias bibliotecas. |
| Treine em PDF, JPG, formato PNG, total de 50 MB/500 pp. | Treine em arquivos PDF, Office ou email de 5 a 10, incluindo exemplos negativos. |

Para obter uma comparação mais completa dos recursos, consulte [Difference between document understanding and form processing models](difference-between-document-understanding-and-form-processing-model.md).

## <a name="identify-pilot-business-scenarios-to-optimize"></a>Identificar cenários de negócios piloto para otimizar

Para se preparar para usar o SharePoint Syntex em sua organização, primeiro você precisa entender os cenários em que ele será útil. O "por que" ajuda a determinar qual modelo será necessário e como estruturar sua organização com base em onde o modelo será aplicado. Aqui estão alguns cenários em que a compreensão de documentos pode ajudar sua organização:

- **Processamento de conteúdo:** Processe contratos, instruções de trabalho e outros documentos parecidos com formulário. A ingestão dos formulários, treine o modelo para entender e mapear os campos e, em seguida, execute seus formulários para coletar automaticamente os dados. Para obter mais informações, consulte [Visão geral do processamento de formulário.](form-processing-overview.md)
- **Análise de fatura:** Retire os detalhes relevantes de suas faturas e certifique-se de que elas estão em conformidade com a política ou que estão sendo processadas adequadamente.

Pense em maneiras que o SharePoint Syntex pode ajudar sua organização:

- Automatizar processos de negócios
- Melhorar a precisão da pesquisa
- Gerenciar riscos de conformidade

Ao pensar em quais cenários de negócios considerar, faça a si mesmo as seguintes perguntas:

- Isso resolve um problema real?
- Será amplamente usado ou terá um impacto amplo?
- É possível obter?
- Você pode medir o sucesso?

Priorizar cenários com base no impacto e na facilidade de implementação. Tornar sua área de foco inicial cenários de maior impacto que também podem ser facilmente implementados. Des priorize cenários de menor impacto difíceis de implementar.

Use os cenários de exemplo a seguir para solicitar ideias sobre como você pode usar o SharePoint Syntex em sua organização.

### <a name="scenario-track-data-from-invoices-with-form-processing"></a>Cenário: Rastrear dados de faturas com processamento de formulário

Por exemplo, você pode configurar um processo usando recursos do SharePoint Syntex e do Power Automate para rastrear e monitorar faturas.

1. Configurar uma biblioteca para armazenar os documentos da fatura.
1. Treine o modelo para reconhecer campos nos documentos.
1. Extraia os campos que você deseja rastrear em uma lista.
1. Configurar um fluxo para notificá-lo para eventos específicos, como:
    - Uma nova fatura é adicionada.
    - Uma fatura já passou da data de vencimento.
    - Uma fatura é para um valor maior do que o valor de aprovação automática.

![Rastrear e monitorar faturas com o SharePoint Syntex e o Power Automate](../media/content-understanding/process-invoices-flow.png)

Ao automatizar esse cenário, você pode:

- Economize tempo e dinheiro extraindo automaticamente dados das faturas em vez de fazê-los manualmente.
- Reduza possíveis erros e garanta uma melhor conformidade usando fluxos de trabalho para verificar faturas e notificá-lo de quaisquer problemas.

### <a name="scenario-track-information-from-contracts-with-document-understanding"></a>Cenário: rastrear informações de contratos com o entendimento de documentos

Como outro exemplo, você pode configurar um processo para identificar contratos que sua empresa tem com outras empresas ou indivíduos. Configurar um modelo para extrair informações importantes desses contratos, como o nome do cliente, taxas, datas ou outras informações importantes e adicionar as informações à biblioteca como campos que você pode exibir rapidamente. Aplique um rótulo de retenção na biblioteca de documentos para garantir que os contratos não possam ser excluídos antes de um período específico de tempo para conformidade apropriada com os regulamentos de negócios.

1. Comece no centro de conteúdo e crie um novo modelo de compreensão de documentos para contratos.
1. Carregue documentos de exemplo para exemplos positivos e negativos e execute o treinamento para identificar documentos de contrato e revisar os resultados.
1. Treine o extrator para identificar campos nos contratos, como o nome do cliente, a taxa e a data e, em seguida, teste o extrator.
1. Quando o modelo for concluído, aplique o modelo a uma biblioteca onde você pode carregar contratos.
1. Aplique um rótulo de retenção ao campo de data, para que os contratos sejam mantidos na biblioteca pelo período de tempo necessário.

![Rastrear e monitorar contratos com o SharePoint Syntex e rótulos de retenção](../media/content-understanding/process-contracts-flow.png)

Ao automatizar esse cenário, você pode:

- Economize tempo e dinheiro extraindo automaticamente dados dos contratos em vez de fazê-los manualmente.
- Garanta uma melhor conformidade usando rótulos de retenção para garantir que os contratos sejam mantidos adequadamente.

### <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a>Cenário: evitar riscos com gerenciamento de registros, governança de documentos e processos de conformidade com base no SharePoint Syntex

Reduzir riscos é uma meta comum para a maioria das empresas. Talvez seja necessário:

- Uma melhor maneira de fornecer/impor a governança de informações em seu locatário.
- Para melhorar o sistema de classificação de documentos, emails e outras formas de comunicação consideradas 'registros' para projetos.
- Para auditar recibos, contratos e assim por diante, para garantir a conformidade com as políticas da empresa.
- Para garantir que os projetos tenham toda a documentação necessária para conformidade.

Configurar alguns processos para conformidade com o SharePoint Syntex para capturar e classificar adequadamente, auditar e sinalizar documentos e formulários que precisam de melhor governança. Você pode contar com o SharePoint Syntex para classificar automaticamente o conteúdo em vez de depender dos usuários finais para marcar manualmente ou da equipe de conformidade para aplicar manualmente regras de governança e arquivamento. E você pode habilitar uma experiência de pesquisa simplificada, gerenciar volumes de dados, aplicar políticas de gerenciamento e retenção de registros, garantir a conformidade e práticas recomendadas de arquivamento e depuração.

Ao automatizar esse cenário, você pode se sentir seguro de que:

- A conformidade é mantida e o risco é reduzido.
- O gerenciamento de taxonomia e registros é aplicado de forma consistente e precisa.
- Os volumes de conteúdo são controlados.
- Os funcionários podem descobrir facilmente as informações certas no contexto correto.

### <a name="scenario-capture-information-from-previously-inaccessible-documents"></a>Cenário: Capturar informações de documentos inacessíveis anteriormente

A maioria das organizações tem grandes repositórios de documentos legais, políticas, contratos, documentos de RH e diretrizes de governança. Extrair esses armazenamentos de dados para extrair informações valiosas como: projetos, setores, temas, pessoas, áreas geográficas e assim por diante.

Por exemplo, um diretor de RH precisa acessar rapidamente todos os documentos de RH , incluindo currículos, políticas de RH e outros formulários. E eles querem identificar rapidamente as informações necessárias de currículos e outros documentos relacionados ao RH sem fazer uma análise manual dos documentos. Eles estão procurando uma solução que permita que eles encontrem rapidamente as informações necessárias sem precisar procurar manualmente milhares de currículos, políticas de RH e outras documentações que podem ser distribuídas em vários sites.

Ao automatizar esse cenário, você pode:

- Desbloqueie o conhecimento do conteúdo digital.
- Classificar políticas de RH, currículos, documentos de vendas, projetos técnicos, planos de conta e extrair informações.
- Encontre rapidamente as informações corretas ou o documento que você está procurando.
- Obter acesso instantâneo às informações mais recentes.
- Reduza os tempos de pesquisa.

### <a name="scenario-improve-data-processing-to-provide-insights--analytics"></a>Cenário: melhorar o processamento de dados para fornecer insights & análise

Por exemplo, uma empresa de produtos farmacêuticos poderia usar o SharePoint Syntex para extrair informações de documentos da FDA para responder a perguntas que seus líderes têm. Ter as respostas mais facilmente acessíveis pode reduzir o tempo necessário para produzir essas respostas e aumentar a disponibilidade de dados para gerar respostas mais precisas para perguntas de liderança.

Por exemplo, um gerente de projeto precisa fornecer rapidamente respostas para perguntas relacionadas ao produto da minha equipe de liderança. Eles precisam encontrar informações e métricas relacionadas a consultas em um painel consolidado. Eles estão procurando uma solução que extraia as informações de que precisam de rótulos de produtos, folhetos de produtos e outros materiais e gera um relatório consolidado que eles podem usar ao relatar para sua equipe de liderança.

Ao automatizar esse cenário, você pode:

- Reduza o tempo para produzir respostas.
- Aumente a disponibilidade de dados.
- Forneça respostas mais precisas.

### <a name="scenario-automate-order-processing"></a>Cenário: Automatizar o processamento de ordem

Com o SharePoint Syntex, você pode reduzir o tempo de processamento manual de pedidos de clientes. Por exemplo, você pode carregar pedidos de fax, email ou papel no SharePoint usando o processamento OCR e, em seguida, extrair os metadados desses pedidos para que você possa cumpri-los usando processos automatizados.

Por exemplo, um gerente de cadeia de fornecimento deseja reduzir os erros causados pela entrada manual de dados. Eles querem evitar a revisão manual e a entrada de dados de pedidos de clientes de entrada (papel, fax ou email) para reduzir os erros de entrada em seus sistemas de negócios. Eles querem uma solução que aplique técnicas de AI e aprendizado de máquina para validar as informações de ordem de entrada, extrair dados principais e enviar automaticamente para seu sistema ERP, para atendimento de ordem e reconciliação.

Ao automatizar esse cenário, você pode garantir que:

- A precisão da ordem e da remessa aumenta.
- As taxas ou as sanções associadas a erros de pedido ou de envio são reduzidas.
- Os atrasos na faturamento ou nos pagamentos diminuem.
- Os custos de pessoal são reduzidos.

### <a name="scenario-simplify-visa-renewal-process"></a>Cenário: simplificar o processo de renovação de visto

O SharePoint Syntex pode ajudá-lo a automatizar lembretes e renovações para informações importantes do contrato. Por exemplo, um diretor de RH precisa garantir que os vistos dos funcionários sejam atualizados e/ou renovados a tempo. Eles querem dar às pessoas um processo simples e intuitivo para atualizar seus Vistos. Eles precisam de uma solução que extraia as datas de renovação dos contratos e envia automaticamente lembretes aos funcionários quando suas datas de renovação estão se aproximando.

Ao automatizar esse cenário, você pode garantir que:

- Os níveis de não conformidade são reduzidos.
- O número de lembretes manuais é reduzido.
- O número de multas por não conformidade é reduzido.

## <a name="identify-roles--responsibilities"></a>Identificar funções & responsabilidades

Determinar quem na sua organização criará e gerenciará os modelos? As seguintes funções podem estar envolvidas:

| Administrador do SharePoint/Conhecimento | Administrador da Plataforma Power | Gerente de conhecimento | Proprietário do modelo |
|:-------|:-------|:-------|:-------|
| Função AAD| Função AAD | Função AAD | Campeões |
| Configurar o processamento de formulário | Configurar o ambiente comum de serviço de dados para processamento de formulário | Reunir casos de uso | Reunir casos de uso comercial |
| Gerenciar centros de conteúdo e permissões| Comprar e alocar créditos do AIB | Estabelecer práticas recomendadas e análise de modelo de revisão | Criar e aplicar modelos |

O gerente de conhecimento, o proprietário do processo de negócios e o proprietário do modelo de conteúdo criam modelos de exemplo e defendem a adoção na organização.
Outros que podem estar envolvidos: administrador de conformidade, gerentes de taxonomia.

Onde eles criarão e aplicarão os modelos? Existem processos ou repositórios existentes que podem ser aprimorados?

- Processamento de formulário: decida quais sites receberão a ação de processamento de formulário.
- Noções básicas sobre documentos: você pode criar vários centros de conteúdo para diferentes áreas de negócios.

## <a name="strategic-positioning"></a>Posicionamento estratégico

Trabalhe com as partes interessadas para garantir que estejam alinhadas à estratégia de uso do SharePoint Syntex. Pesquise e forneça os seguintes recursos para ajudar com esse posicionamento:

- Resultados de negócios:
  - Resultados fiscais potenciais
  - Resultados de agilidade potenciais
  - Modelo de resultado de negócios
- Stakeholders/Exec sponsor buy-in/alignment
  - Decks de caso de negócios
  - Modelos financeiros
  - Preparação da empresa - cultura

## <a name="identify-stakeholders"></a>Identificar participantes

Identifique os participantes do seu projeto.

|Função |Responsabilidades |Department |
|:-------|:-------|:--------|
| Patrocinadores executivos   | Comunicar visão e valores de alto nível à empresa   |  Liderança executiva   |
| Lead(s) project lead(s) | Supervisionar todo o processo de execução e lançamento de lançamento | Gerenciamento de projeto |
| Administradores de conhecimento| Criar e gerenciar os centros de conteúdo | IT ou outro departamento|
| Gerentes de conteúdo e proprietários de modelos| Reunir casos de uso e criar e aplicar modelos | Qualquer departamento|
| Campeões | Ajudar a evangelizar e gerenciar o tratamento de objeções | Qualquer departamento (equipe) |
| Administrador de locatários | Configurar configurações no nível do locatário | Departamento de IT|
| Administrador da Plataforma Power| Configurar o ambiente de serviços de dados comuns | Departamento de IT|

> [!Note]
> Embora seja recomendável que cada uma dessas funções seja cumprida ao longo da sua lançamento, você pode descobrir que não é necessário que todas elas sejam iniciadas com sua solução identificada.

## <a name="readiness-checklist"></a>Lista de verificação de preparação

Para se preparar para implementar o SharePoint Syntex, você precisa:

![Preparação para a compreensão de conteúdo](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. Planejar o estado final
    - Modelos de compreensão de documentos são os meios, não o final.
    - Planejar a utilização do valor de metadados extraídos com:
      - Pesquisa
      - Filtragem e formatação de exibição
      - Conformidade
      - Automação
2. Identificar
    - Entenda o uso de recursos de gerenciamento de conteúdo e arquitetura de informações existentes.
    - Os tipos de conteúdo existentes são bons candidatos para modelos?
    - Quais processos existentes seriam aprimorados por metadados?
3. Design
    - Projetar sua abordagem para arquitetura de informações, metadados gerenciados e tipos de conteúdo
    - Projete o processo para definição, criação, gerenciamento.

## <a name="engage-your-organization"></a>Envolver sua organização

1. Identifique os titulares da participação, confirme cenários e desenvolva o plano de projeto.
1. Configurar configurações e aplicar licenças.
1. Começar a conscientização e treinamento – Recrutar Campeões.
1. Rolar em estágios.  
1. Coletar comentários e iterar.
1. À medida que o uso aumenta o plano para quaisquer créditos do Construtor de AI conforme necessário.
