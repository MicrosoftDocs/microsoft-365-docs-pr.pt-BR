---
title: Isolamento de locatário do Microsoft 365 no Microsoft Graph e delve
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
description: Neste artigo, encontre uma explicação sobre como o isolamento de locatário do Microsoft 365 funciona no Office Graph e no Delve.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 966f02726a2cce18e30e4d5bc7ab0beb5db51a29
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332383"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Isolamento de locatário do Microsoft 365 no Microsoft Graph e delve

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Isolamento de locatário no Microsoft Graph

A atividade de modelos do [Microsoft Graph](https://developer.microsoft.com/graph) nos serviços do Microsoft 365, incluindo o Exchange Online, o SharePoint Online, o Yammer, o Skype for Business, o Azure Active Directory e muito mais e em serviços externos, como outros serviços da Microsoft ou serviços de terceiros. Os componentes do Microsoft Graph são usados em todo o Microsoft 365. O Microsoft Graph representa uma coleção de conteúdo e atividade e as relações entre elas que ocorrem em todo o pacote do Office. Ele usa técnicas sofisticadas de aprendizado de máquina para conectar as pessoas ao conteúdo relevante, conversas e pessoas à sua volta. Por exemplo, o índice de locatário no SharePoint Online tem um índice do Microsoft Graph que é usado para atender a consultas do Delve, o Mecanismo de Processamento de Análise no SharePoint Online é usado para armazenar sinais e calcular insights e o Exchange Online calcula o cache de destinatários de cada usuário como entrada na análise de locatário.

O Microsoft Graph contém informações sobre objetos corporativos, como pessoas e documentos, bem como as relações e interações entre esses objetos. Os relacionamentos e interações são representados como *bordas*. O Microsoft Graph é segmentado por locatário de forma que as bordas só possam existir entre *nós* no mesmo locatário. Um *nó* é uma entidade com um URI (Uniform Resource Identifier), tipo de nó, lista de controle de acesso e um conjunto de facetas contendo metadados *e* bordas. Cada nó tem metadados e bordas associados, organizados em *facetas* como no Modelo de Conhecimento Comum. *Os metadados* são propriedades nomeadas armazenadas em um nó que podem ser usadas para pesquisa, filtragem ou análise no Microsoft Graph. Uma *faceta é* uma coleção lógica de metadados e bordas em um nó. Cada faceta descreve um aspecto de um nó. 

O Microsoft Graph não traz todos os dados para um único repositório; em vez disso, ele armazena metadados e relações sobre dados que residem em outro lugar. O Microsoft Graph consiste em vários armazenamentos de dados e componentes de processamento:

- O Locatário Graph Store fornece armazenamento em massa otimizado para análise eficiente.
- O Cache de Conteúdo Ativo fornece acesso aleatório rápido ao nó ativo e bordas para impulsionar as experiências do usuário.
- O roteador de entrada notifica componentes internos e externos de alterações no gráfico do locatário.

A análise em cada carga de trabalho dedua percepções relevantes para os cálculos de todo o locatário e as empurra para o gráfico do locatário. Motivos de análise do locatário sobre todas as atividades em um locatário para produzir insights sobre padrões de comportamento. Por exemplo, o Exchange Online calcula o cache de destinatários para cada usuário com análises que explicam com eficiência a caixa de correio de cada usuário. Essas análises por usuário produzem um conjunto de Bordas *recipientCache* em cada pessoa, que, por sua vez, são enviadas para o gráfico do locatário. Isso mantém o máximo do processamento da análise o mais próximo possível dos dados de origem.

## <a name="tenant-isolation-in-delve"></a>Isolamento de locatário no Delve

Conforme mencionado anteriormente, o Microsoft Graph alimenta experiências que ajudam as pessoas a descobrir e colaborar em atividades atuais em sua empresa e fornece uma plataforma centrada na entidade para análise para o motivo do conteúdo e das atividades em cargas de trabalho e além do Microsoft 365. O Delve é a primeira experiência da plataforma Microsoft Graph.
O Delve é uma experiência da Web do Microsoft 365 que apresenta o conteúdo do Microsoft 365 e do Yammer Enterprise para os usuários do Microsoft 365 por meio do Microsoft Graph. A experiência da Web exibe dados como diferentes tabuleiros, cada um com um determinado tópico, como *Tendências* ao meu redor ou *Modificado por mim.* Cada quadro consiste em vários cartões de documento que exibem texto de resumo e uma imagem do documento. O cartão permite que os usuários abram o documento ou uma página do Yammer para o documento. Há uma página para cada pessoa em um locatário do Microsoft 365 que exibe os documentos mais relevantes para essa pessoa e ícones que podem invocar o Exchange Online ou o Skype for Business para interagir com essa pessoa. Como o Delve é baseado na API do Microsoft Graph, ele é limitado pelo isolamento baseado no locatário dessa API.