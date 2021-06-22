---
title: Gerenciar contratos usando uma solução do Microsoft 365
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
ms.collection: m365solution-managecontracts m365solution-overview
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Saiba como gerenciar contratos usando uma solução Microsoft 365 de SharePoint Syntex, SharePoint Listas, Microsoft Teams e Power Automate.
ms.openlocfilehash: d3be12dbddabbcddc41f7c9d882db5473350266e
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054762"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a>Gerenciar contratos usando uma solução do Microsoft 365

Este artigo descreve como criar uma solução de gerenciamento de contratos para sua organização usando SharePoint Syntex e componentes de Microsoft 365. Ele fornece uma estrutura para ajudá-lo a planejar e criar uma solução que se ajuste às suas necessidades de negócios exclusivas. Mesmo se essa solução não atender às suas necessidades de negócios como um todo, partes dela podem ser adotadas em seu planejamento para criar uma solução de gerenciamento de contratos personalizada.

*Esse conjunto de conteúdo documenta uma Microsoft 365 desenvolvida por Thomas Molbach com a Equipe de Estratégia de Solução de Trabalho Moderna da Microsoft.*

## <a name="identify-the-business-problem"></a>Identificar o problema de negócios

A primeira etapa no planejamento do sistema de gerenciamento de contratos é entender o problema que você está tentando resolver. Para essa solução, quatro problemas principais precisam ser resolvidos:

- **Identificar contratos**. Sua organização trabalha com muitos documentos, como faturas, contratos, instruções de trabalho e assim por diante.  Alguns são ativos digitais enviados por email e alguns são ativos de papel enviados por email tradicional. Você precisa de uma maneira de identificar todos os contratos de clientes de todos os outros documentos e classificá-los como tal.

- **Acompanhe o histórico de aprovações de contrato.** Sua organização precisa de uma maneira confiável de descobrir se os contratos foram aprovados ou rejeitados e se o pagamento foi processado. 

- **Site para gerenciar aprovações de contrato**. Sua organização precisa configurar um site colaborativo no qual todos os participantes necessários possam revisar facilmente contratos. As partes interessadas devem ser capazes de revisar todo o contrato, se necessário, mas principalmente se preocupam em ver vários campos principais de cada contrato (por exemplo, nome do cliente, número de PO e custo total). As partes interessadas devem ser capazes de aprovar ou rejeitar facilmente contratos de entrada.

- **Roteia contratos revisados**. Contratos aprovados e rejeitados precisam ser roteados por meio de um fluxo de trabalho específico. Os contratos aprovados precisam ser roteados para um aplicativo de terceiros para processamento de pagamento. Os contratos rejeitados precisam ser roteados para revisão adicional.

## <a name="overview-of-the-solution"></a>Visão geral da solução

  ![Diagrama da solução usando SharePoint Syntex, SharePoint listas, Teams e Power Automate.](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

Esta orientação de solução de gerenciamento de contratos inclui quatro componentes de Microsoft 365:

- **Microsoft SharePoint Syntex:** crie modelos para identificar e classificar seus arquivos de contrato e, em seguida, extrair os dados apropriados deles.

- **Listas SharePoint** Microsoft : Use a formatação disponível em listas SharePoint modernas para apresentar contratos em um formato amigável para os negócios.

- **Microsoft Teams**: use a funcionalidade de um canal Teams e guias associadas para permitir que seus participantes revisem e gerenciem contratos.

- **Power Automate**: use fluxos para orientar contratos por meio do processo de aprovação e, em seguida, para um aplicativo de terceiros para pagamento.

### <a name="how-it-all-works"></a>Como tudo funciona

  ![Diagrama da solução mostrando o fluxo de trabalho para carregar documentos, extrair dados, notificar as partes interessadas e aprovar ou rejeitar o contrato.](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. Os documentos são carregados em uma biblioteca SharePoint de documentos. Um SharePoint Syntex de entendimento de documentos foi aplicado à biblioteca de documentos. Ele verifica cada arquivo para ver se algum corresponder a um tipo de conteúdo "contrato" que ele está treinado para procurar. Se encontrar uma combinação, ele classifica o arquivo como um "contrato" e atualiza o tipo de conteúdo do documento.

2. O modelo também retira dados específicos de cada arquivo de contrato que as partes interessadas em ver, como *o Cliente,* o Prestador *de* Serviços e o valor da *taxa.*

    A página a seguir é um exemplo de um contrato que o modelo é treinado para identificar.

      ![Exemplo de um contrato.](../media/content-understanding/contract.png)

3. No Microsoft Teams, todos os participantes são membros de um canal seguro Teams no qual todos os contratos na biblioteca de documentos ficam visíveis para aprovação ou rejeição. Usando Teams funcionalidade, todas as partes interessadas são notificadas quando novos contratos precisam ser revistos.
 
4. Usando o Power Automate, os contratos são movidos pelo processo de aprovação no Teams canal. Quando um membro aprova um contrato, o status do contrato é alterado para aprovar, todos os membros são notificados por meio de uma postagem de Teams e um item de linha é criado para mostrar que o contrato está pronto para pagamento. Esse processo pode ser estendido para gravar diretamente em um aplicativo financeiro de terceiros para pagamento.

5.  Quando um membro rejeita um contrato, o status é alterado para rejeitado e todos os membros são notificados por meio de Teams postagem.

6. O resultado final dessa solução é um processo de negócios automatizado para sua organização. Os funcionários podem usar facilmente a exibição de Teams para iniciar e monitorar o fluxo de trabalho de aprovação de seus documentos. 

     ![Guia Contratos.](../media/content-understanding/tile-view.png)

### <a name="licensing-requirements"></a>Requisitos de licenciamento

Essa solução se baseia na seguinte funcionalidade, tudo disponível como parte de uma licença de Microsoft 365 Enterprise (E1, E3, E5, F3) ou Business (Basic, Standard ou Premium).

-   Microsoft SharePoint Syntex
-   Microsoft Teams
-   Power Automate

## <a name="create-the-solution"></a>Criar a solução

As próximas seções entrarão em detalhes sobre como configurar a solução de gerenciamento de contratos. Ele é dividido em três etapas:

- [Etapa 1. Use SharePoint Syntex para identificar arquivos de contrato e extrair dados](solution-manage-contracts-step1.md)
- [Etapa 2. Use Microsoft Teams para criar seu canal de gerenciamento de contratos](solution-manage-contracts-step2.md)
- [Etapa 3. Use Power Automate para criar seu fluxo para processar seus contratos](solution-manage-contracts-step3.md)
