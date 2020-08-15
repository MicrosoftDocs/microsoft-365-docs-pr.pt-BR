---
title: Isolamento de locatário do Microsoft 365 no Microsoft Graph e no Delve
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
- M365-security-compliance
f1.keywords:
- NOCSH
description: Neste artigo, encontre uma explicação sobre como o isolamento de locatário do Microsoft 365 funciona no Office Graph e no Delve.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ab9b216656e076cc3ba02a4ef6c75b25b94547fe
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687251"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Isolamento de locatário do Microsoft 365 no Microsoft Graph e no Delve

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Isolamento de locatário no Microsoft Graph

A atividade de modelos do [Microsoft Graph](https://developer.microsoft.com/graph) nos serviços do Microsoft 365, incluindo Exchange Online, SharePoint Online, Yammer, Skype for Business, Azure Active Directory e mais e em serviços externos, como outros serviços da Microsoft ou serviços de terceiros. Os componentes do Microsoft Graph são usados em todo o Microsoft 365. O Microsoft Graph representa uma coleção de conteúdo e atividade e as relações entre elas que ocorrem em todo o pacote do Office. Ele usa técnicas de aprendizado de máquina sofisticadas para conectar pessoas ao conteúdo relevante, conversas e pessoas em torno delas. Por exemplo, o índice de locatário no SharePoint Online tem um índice do Microsoft Graph que é usado para servir consultas de Delve, o mecanismo de processamento de análise no SharePoint Online é usado para armazenar sinais e calcular insights, e o Exchange Online calcula o cache de destinatários de cada usuário como entrada na análise de locatários.

O Microsoft Graph contém informações sobre objetos da empresa, como pessoas e documentos, bem como as relações e interações entre esses objetos. Os relacionamentos e interações são representados como *bordas*. O Microsoft Graph é segmentado por locatário, de forma que as bordas só podem existir entre *nós* na mesma locação. Um *nó* é uma entidade com um URI (Uniform Resource Identifier), tipo de nó, lista de controle de acesso e um conjunto de facetas contendo *metadados* e bordas. Cada nó tem metadados e bordas associados, organizados em *facetas* como no modelo de conhecimento comum. Os *metadados* são denominados Propriedades armazenadas em um nó que pode ser usado para pesquisa, filtragem ou análise no Microsoft Graph. Uma *faceta* é uma coleção lógica de metadados e bordas em um nó. Cada faceta descreve um aspecto de um nó. 

O Microsoft Graph não reúne todos os dados em um único repositório; em vez disso, ele armazena metadados e relações sobre dados que residem em outros locais. O Microsoft Graph consiste em vários repositórios de dados e componentes de processamento:

- O repositório de gráficos do locatário fornece armazenamento em massa otimizado para análise eficiente.
- O cache de conteúdo ativo oferece acesso aleatório rápido ao nó ativo e às bordas para conduzir as experiências do usuário.
- O roteador de entrada notifica os componentes internos e externos das alterações no gráfico do locatário.

A análise em cada carga de trabalho deduz as ideias relevantes aos cálculos em todo o locatário e empurre-as para o gráfico do locatário. Os motivos da análise do locatário em todas as atividades de uma locação para produzir informações sobre padrões de comportamento. Por exemplo, o Exchange Online calcula o cache do destinatário para cada usuário com a análise que tem um motivo eficiente sobre a caixa de correio de cada usuário. Essas análises por usuário produzem um conjunto de *bordas RecipientCache* em cada pessoa, que por sua vez é enviado para o gráfico do locatário. Isso mantém o máximo de processamento de análise o mais próximo possível dos dados de origem.

## <a name="tenant-isolation-in-delve"></a>Isolamento de locatário no Delve

Como mencionado anteriormente, o Microsoft Graph oferece experiências que ajudam as pessoas a descobrir e colaborar em atividades atuais em sua empresa e fornece uma plataforma centrada em entidade para análise do motivo de conteúdo e atividade em cargas de trabalho e além do Microsoft 365. O Delve é a primeira experiência do Microsoft Graph.
O Delve é uma experiência da Web da Microsoft 365 que superfícies o conteúdo do Microsoft 365 e do Yammer Enterprise para usuários do Microsoft 365 por meio do Microsoft Graph. A experiência da Web exibe dados como diferentes placas, cada uma com um determinado tópico, como a *tendência de me mostrar* ou *modificado por mim*. Cada placa consiste em vários cartões de documento que exibem o texto de resumo e uma imagem do documento. O cartão permite que os usuários façam coisas como abrir o documento ou uma página do Yammer para o documento. Há uma página para cada pessoa em um locatário do Microsoft 365 que exibe os documentos mais relevantes para esta pessoa e ícones que podem invocar o Exchange Online ou o Skype for Business para interagir com essa pessoa. Como o Delve é baseado na API do Microsoft Graph, ele é limitado pelo isolamento baseado em locatário dessa API.