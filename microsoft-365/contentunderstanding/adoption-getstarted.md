---
title: 'Adoção do Syntex do Microsoft SharePoint: introdução'
description: Saiba como usar e implementar o SharePoint Syntex em sua organização para ajudá-lo a resolver seus problemas de negócios.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: db54ff053dcb1c9c1c608608ab1a37da8090cdb3
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087506"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Adoção do Syntex do Microsoft SharePoint: introdução

Pense nos serviços de conteúdo inteligente disponíveis no SharePoint Syntex como tendo três partes:

- **Compreensão do conteúdo:** Crie modelos do ai sem código para classificar e extrair informações do conteúdo para aplicar metadados automaticamente para descoberta e reutilização de conhecimento. Saiba mais sobre a [compreensão do conteúdo](document-understanding-overview.md).
- **Processamento do conteúdo:** Automatizar a captura, a inclusão e a categorização de conteúdo e simplificar processos centrados em conteúdo usando automatização de energia. Saiba mais sobre o [processamento de conteúdo](form-processing-overview.md).
- **Conformidade de conteúdo:** Controlar e gerenciar conteúdo para melhorar a segurança e a governança com a integração com a proteção de informações da Microsoft.

Com novos serviços e recursos do AI, você pode criar aplicativos de compreensão e classificação de conteúdo diretamente no fluxo de gerenciamento de conteúdo usando o Syntex do SharePoint:

|Entrada manual| Processamento de formulários | Noções básicas sobre documentos |
|:-------|:--------|:--------|
| Entrada de dados e trabalho intensivo em qualquer conteúdo | Processar conteúdo digital-fotos, varreduras, recibos, cartões de visita, vídeos com texto de & OCR |  Capturar tipos de conteúdo e metadados de contratos, currículos e outros documentos estruturados |
| Interativo   | Pré-criados, automatizado   | Personalizado, auxiliado   | Personalizado, compatível |
| Pessoas executando o trabalho | Ensinado pelos especialistas no assunto (SMEs). Capture os tipos de conteúdo e metadados de contratos, currículos, outros documentos não estruturados. | Os SMEs estão menos envolvidos. de pedidos de compra, aplicativos, outros documentos semi-estruturados e estruturados |

A tabela a seguir explica o que você obtém ao usar o Syntex do SharePoint:

| Processamento de formulários | Noções básicas sobre documentos |
|:-------|:-------|
| Disponível na América do leste, Austrália, Canadá, UE, JP, BRm, Reino Unido | Disponível em todas as regiões |
| Usa créditos do Construtor AI-créditos de 1M = 2000 páginas; O consumo é de cerca de 2000 faturas = 2 unidades. A automatização de energia é necessária-se você precisar de mais você pode adicioná-la. créditos de 1M alocados para mais de 300 licenças adquiridas. Você também pode adquirir créditos separadamente. | Os modelos funcionam em todos os idiomas do alfabeto latino. Além de inglês: alemão, Sueco, francês, espanhol, italiano e Português. |
| Provisionado em relação ao ambiente padrão de serviço de dados comuns| Não tem restrições de capacidade. |

Há duas maneiras diferentes de entender seu conteúdo. O tipo de modelo usado é baseado no formato de arquivo e no caso de uso:

| Processamento de formulários | Noções básicas sobre documentos |
|:-------|:-------|
| Criado na biblioteca de documentos | Criado no centro de conteúdo, parte do SharePoint Syntex |
| Modelo criado no Construtor AI | Modelo criado na interface nativa |
| Usado para formatos de arquivo semi-estruturados | Usado para formatos de arquivo não estruturados |
| Classificador configurável | Classificador treinado com extratores opcionais |
| Restrito a uma única biblioteca | Pode ser aplicado a várias bibliotecas |
| Treinamento em PDF, JPG, formato PNG, total de 50 MB/500 PP | Treine no 5-10 PDF, Office ou arquivos de email, incluindo exemplos negativos |

O SharePoint Syntex integra-se aos recursos de conformidade do Microsoft 365, como:

- Rótulos de retenção que definem a política de registros com base na idade do documento ou eventos externos.
- Rótulos de confidencialidade que definem políticas DLP, de criptografia, compartilhamento e acesso condicional.

Os usuários podem aplicar rótulos ou podem ser aplicados automaticamente pelos modelos do Syntex AI do SharePoint. Os planos de análise e de arquivos oferecem gerenciamento em escala de uso de rótulo e políticas.

## <a name="identify-pilot-business-scenarios-to-optimize"></a>Identificar cenários de negócios piloto para otimizar

Para se preparar para usar o Syntex do SharePoint em sua organização, primeiro você precisa entender os cenários em que ele será útil. O porquê ajuda a determinar qual modelo será necessário e como estruturar sua organização com base no local onde o modelo será aplicado. Aqui estão alguns cenários nos quais o documento entendendo pode ajudar sua organização a:

- Processamento de conteúdo: contratos de processo, declarações de trabalho e outros documentos semelhantes a formulários. Ingestão de formulários, treine o modelo para compreender e mapear os campos e, em seguida, execute os formulários através de para coletar automaticamente os dados. Para mais informações, consulte [visão geral do processamento de formulários](form-processing-overview.md).
- Análise de faturas: Retire os detalhes relevantes de suas faturas e verifique se eles estão em conformidade com a política ou estão sendo processados de forma adequada.

Pense em como as Syntex do SharePoint podem ajudar sua organização a:

- Automatizar processos de negócios
- Melhorar a precisão da pesquisa
- Gerenciar o risco de conformidade

### <a name="form-processing-scenario-example"></a>Exemplo de cenário de processamento de formulário

Por exemplo, você pode configurar um processo usando o SharePoint Syntex e recursos de automatização de energia para rastrear e monitorar faturas.

1. Configurar uma biblioteca para armazenar os documentos de fatura.
1. Treine o modelo para reconhecer campos nos documentos.
1. Extraia os campos que você deseja controlar em uma lista.
1. Configurar um fluxo para notificá-lo sobre eventos específicos, como:
    - Uma nova fatura é adicionada.
    - Uma fatura ultrapassa sua data de vencimento.
    - Uma fatura é maior que o valor de aprovação automático.

![Rastrear e monitorar faturas com o SharePoint Syntex e automatizar a energia](../media/content-understanding/process-invoices-flow.png)

Ao automatizar esse cenário, você pode:

- Economize tempo e dinheiro, extraindo dados automaticamente das faturas, em vez de fazê-lo manualmente.
- Reduza possíveis erros e assegure a melhor conformidade usando fluxos de trabalho para agir nas faturas e notificá-lo de qualquer problema.

### <a name="document-understanding-scenario-example"></a>Exemplo de cenário de compreensão de documento

Como outro exemplo, você pode configurar um processo para identificar contratos que sua empresa tem com outras empresas ou indivíduos. Você pode configurar um modelo para extrair informações importantes desses contratos, como o nome do cliente, as taxas, as datas ou outras informações importantes e adicioná-las à biblioteca como campos que podem ser rapidamente exibidos. E você pode aplicar um rótulo de retenção na biblioteca de documentos para garantir que os contratos não possam ser excluídos antes de um período específico de tempo para conformidade adequada com suas regulamentações comerciais.

1. Inicie no centro de conteúdo e crie um novo documento entendendo o modelo para contratos.
1. Carregar documentos de exemplo para exemplos positivos e negativos e, em seguida, execute o treinamento para identificar documentos de contrato e revisar os resultados.
1. Treine o extrator para identificar os campos nos contratos, como o nome do cliente, a taxa e a data e, em seguida, teste o extrador.
1. Quando o modelo estiver concluído, aplique o modelo a uma biblioteca onde você pode carregar contratos.
1. Aplicar um rótulo de retenção ao campo de data, de modo que os contratos sejam mantidos na biblioteca pelo período de tempo que sua organização requer para contratos.

![Controlar e monitorar contratos com Syntex e rótulos de retenção do SharePoint](../media/content-understanding/process-contracts-flow.png)

Ao automatizar esse cenário, você pode:

- Economize tempo e dinheiro, extraindo automaticamente os dados dos contratos, em vez de fazê-lo manualmente.
- Garantir melhor conformidade usando rótulos de retenção para garantir que os contratos sejam retidos adequadamente.

### <a name="tips-for-identifying-scenarios"></a>Dicas para identificar cenários

Ao pensar em quais cenários de negócios devem ser considerados, faça as seguintes perguntas:

- Ele resolve um problema real?
- Será amplamente usado ou terá um impacto amplo?
- É possível?
- Você pode medir o sucesso?

Priorize os cenários com base no impacto e na facilidade de implementação. Torne a área de foco inicial cenários de impacto maior que também podem ser facilmente implementados. Despriorize os cenários de impacto mais baixo que são difíceis de implementar.

## <a name="identify-roles--responsibilities"></a>Identificar funções & responsabilidades

Determinar quem em sua organização vai criar e gerenciar os modelos? As seguintes funções podem estar envolvidas:

| Administração do SharePoint/conhecimento | Administrador da plataforma de energia | Gerente de conhecimento | Proprietário do modelo |
|:-------|:-------|:-------|:-------|
| Função AAD| Adicionar função | Função AAD | Campeões |
| Configurar o processamento de formulário | Configurar o ambiente de serviço de dados comuns para processamento de formulários | Reunir casos de uso | Reunir casos de uso comercial |
| Gerenciar centros de conteúdo e permissões| Comprar e alocar créditos do AIB | Estabelecer práticas recomendadas e analisar análises de modelos | Criar e aplicar modelos |

Gerente de conhecimento, proprietário do processo empresarial e proprietário do modelo de conteúdo criar modelos de amostra e adoção de especialista na organização.
Outras pessoas que podem estar envolvidas: administração de conformidade, gerentes de taxonomia.

Onde serão criados e aplicados os modelos? Há processos ou repositórios que podem ser aprimorados?

- Processamento de formulários: decida quais sites receberão a ação de processamento de formulários.
- Noções básicas sobre documentos: você pode criar vários centros de conteúdo para diferentes áreas de negócios.

## <a name="strategic-positioning"></a>Posicionamento estratégico

Trabalhe com os participantes para garantir que eles estejam alinhados na estratégia de uso do SharePoint Syntex. Pesquise e forneça os seguintes recursos para ajudá-lo com esse posicionamento:

- Resultados de negócios:
  - Possíveis resultados fiscais
  - Resultados de agilidade em potencial
  - Modelo de resultado comercial
- Participantes/alinhamento do patrocinador de exec
  - Baralho de caso comercial
  - Modelos financeiros
  - Preparação da empresa-cultura

## <a name="identify-stakeholders"></a>Identificar participantes

Identifique os participantes do seu projeto.

|Role |Responsabilidades |Department |
|:-------|:-------|:--------|
| Patrocinador executivo (es)   | Transmitir valores e visão de alto nível para a empresa   |  Liderança executiva   |
| Líder de projeto (s) | Supervisionar todo o processo de execução e distribuição do lançamento | Gerenciamento de projeto |
| Administradores de conhecimento| Criar e gerenciar os centros de conteúdo | TI ou outro departamento|
| Gerentes de conteúdo e proprietários de modelo| Reunir casos de uso e criar e aplicar modelos | Qualquer departamento|
| Campeões | Ajudar a evangelize e gerenciar a manipulação de objeções | Qualquer departamento (equipe) |
| Administrador de locatários | Definir configurações no nível do locatário | Departamento de ti|
| Administrador de plataforma de energia| Configurar o ambiente de serviços de dados comuns | Departamento de ti|

> [!Note]
> Embora seja recomendável ter cada uma dessas funções atendidas por toda a sua distribuição, você pode achar que você não precisará delas para começar a usar sua solução identificada.

## <a name="readiness-checklist"></a>Lista de verificação de preparação

Para se preparar para implementar o SharePoint Syntex, você precisa:

![Preparação para a compreensão do conteúdo](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. Planejar o estado final
    - Modelos de compreensão de documentos são os meios, e não os finais.
    - Planejar o aproveitamento do valor de metadados extraídos com:
      - Pesquisa
      - Filtragem e visualização da formatação
      - Conformidade
      - Automação
2. Identificar
    - Entender a arquitetura de informações e o uso do recurso de gerenciamento de conteúdo existentes.
    - Os tipos de conteúdo existentes são bons candidatos para modelos?
    - Quais processos existentes seriam aprimorados pelos metadados?
3. Design
    - Criar sua abordagem para arquitetura de informações, metadados gerenciados e tipos de conteúdo
    - Projete o processo de definição, criação e gerenciamento.

## <a name="engage-your-organization"></a>Participar da sua organização

1. Identifique os contentores de apostas, confirme os cenários e desenvolva o plano de projeto.
1. Defina as configurações e aplique licenças.
1. Comece a conscientização e treinamento – campeões de recrutamento.
1. Distribuição em estágios.  
1. Coletar comentários e iterar.
1. Como o uso aumenta o plano para qualquer crédito do Construtor AI, conforme necessário.
