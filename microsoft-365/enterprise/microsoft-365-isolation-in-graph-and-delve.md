---
title: Microsoft 365 Isolamento de locatários no microsoft Graph e Delve
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
description: Neste artigo, encontre uma explicação de como o isolamento Microsoft 365 locatário funciona no Office Graph e no Delve.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 966f02726a2cce18e30e4d5bc7ab0beb5db51a29
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332383"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Microsoft 365 Isolamento de locatários no microsoft Graph e Delve

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Isolamento de locatários no microsoft Graph

A atividade de modelos do [Microsoft Graph](https://developer.microsoft.com/graph) em serviços Microsoft 365, incluindo Exchange Online, SharePoint Online, Yammer, Skype for Business, Azure Active Directory e muito mais, e em serviços externos, como outros serviços serviços Microsoft ou de terceiros. Os Graph microsoft são usados em todo o Microsoft 365. O microsoft Graph representa uma coleção de conteúdo e atividade e as relações entre eles que ocorrem em todo o Office pacote. Ele usa técnicas sofisticadas de aprendizado de máquina para conectar as pessoas ao conteúdo relevante, conversas e pessoas ao seu redor. Por exemplo, o índice de locatário no SharePoint Online tem um índice do Microsoft Graph que é usado para atender Delve consultas, o Mecanismo de Processamento de Análise no SharePoint Online é usado para armazenar sinais e calcular insights, e Exchange Online calcula o cache de destinatário de cada usuário como entrada na análise de locatários.

O microsoft Graph contém informações sobre objetos corporativos, como pessoas e documentos, bem como as relações e interações entre esses objetos. Os relacionamentos e interações são representados como *bordas*. O microsoft Graph é segmentado por locatário para  que as bordas só possam existir entre nós na mesma locação. Um *nó* é uma entidade com um URI (Uniform Resource Identifier), tipo de nó, lista de controle de acesso e um conjunto de facetas contendo *metadados* e bordas. Cada nó tem metadados e bordas associados, organizados em *facetas* como no Modelo de Conhecimento Comum. *Os metadados* são propriedades nomeadas armazenadas em um nó que podem ser usados para pesquisa, filtragem ou análise no microsoft Graph. Uma *faceta é* uma coleção lógica de metadados e bordas em um nó. Cada faceta descreve um aspecto de um nó. 

O microsoft Graph não traz todos os dados para um único repositório; em vez disso, armazena metadados e relações sobre dados que residem em outro lugar. O microsoft Graph consiste em vários armazenamentos de dados e componentes de processamento:

- O Locatário Graph Store fornece armazenamento em massa otimizado para análises eficientes.
- O Cache de Conteúdo Ativo fornece acesso aleatório rápido a nós e bordas ativos para impulsionar as experiências do usuário.
- O roteador de entrada notifica componentes internos e externos de alterações no gráfico do locatário.

A análise em cada carga de trabalho dedua percepções relevantes para os cálculos em todo o locatário e os empurra para o gráfico de locatários. Motivos de análise de locatários sobre todas as atividades em uma locação para produzir ideias sobre padrões de comportamento. Por exemplo, Exchange Online calcula o cache de destinatário para cada usuário com análises que explicam com eficiência a caixa de correio de cada usuário. Essas análises por usuário produzem um conjunto de *Bordas recipientCache* em cada pessoa, que, por sua vez, são empurradas para o gráfico de locatários. Isso mantém a maior parte do processamento de análise o mais próximo possível dos dados de origem.

## <a name="tenant-isolation-in-delve"></a>Isolamento de locatários Delve

Como mencionado anteriormente, o Microsoft Graph permite experiências que ajudam as pessoas a descobrir e colaborar nas atividades atuais em sua empresa e fornece uma plataforma centrada em entidades para análise para o raciocínio sobre o conteúdo e a atividade em cargas de trabalho e além Microsoft 365. Delve é a primeira experiência do microsoft Graph.
Delve é uma experiência Microsoft 365 web que apresenta conteúdo do Microsoft 365 e do Yammer Enterprise para Microsoft 365 usuários por meio do Microsoft Graph. A experiência da Web exibe dados como diferentes placas, cada uma com um determinado tópico, como *Tendências* ao meu redor ou *Modificado por mim.* Cada quadro consiste em vários cartões de documento que exibem texto de resumo e uma imagem do documento. O cartão permite que os usuários abram o documento ou uma página Yammer para o documento. Há uma página para cada pessoa em um locatário Microsoft 365 que exibe os documentos mais relevantes para essa pessoa e ícones que podem invocar Exchange Online ou Skype for Business para interagir com essa pessoa. Como Delve se baseia na API do Microsoft Graph, ela está vinculada ao isolamento baseado em locatário dessa API.