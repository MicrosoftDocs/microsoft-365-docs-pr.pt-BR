---
title: Criar uma pesquisa
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba como criar, definir e escolher custodiantes e locais de custodiante para uma pesquisa em um caso de Descoberta Avançada.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1d9051824ff3f28484d0750b982edd70334a9b88
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035763"
---
# <a name="create-a-search"></a>Criar uma pesquisa

Na guia **Pesquisas,** no seu caso, você pode criar uma nova pesquisa clicando em **Nova pesquisa** e seguindo o assistente.

![O assistente de pesquisa em um caso de Descoberta Virtual Avançada](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a>Nomear a pesquisa e dar a ela uma descrição

Cada pesquisa com uma ocorrência deve ter um nome exclusivo. Opcionalmente, você pode fornecer uma descrição para sua pesquisa. 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a>Escolha os custodiantes e locais de custodiante para pesquisar

Escolha locais de conteúdo custodiante para pesquisar especificando os custodiantes que você adicionou à ocorrência. Selecionando um custodiante, você executará a pesquisa em todas as fontes de dados mapeadas para o custodiante. Você também tem a opção de restringir a pesquisa a fontes de dados selecionadas para cada custodiante. Para obter mais informações sobre como adicionar custodiantes e gerenciar suas fontes de dados, consulte [Trabalhar com custodiantes](managing-custodians.md).

## <a name="choose-non-custodial-locations"></a>Escolher locais sem custodiante

Em alguns casos, talvez você queira pesquisar fontes de dados que não estão associadas a um custodiante. Nesse caso, você pode especificar os locais que deseja pesquisar ou escolher pesquisar todos os locais de conteúdo para um serviço específico da Microsoft (como pesquisar todas as caixas de correio do Exchange ou todos os sites do SharePoint e contas do OneDrive).

## <a name="define-the-search-query-and-conditions"></a>Definir a consulta de pesquisa e as condições

Você pode definir a consulta de palavras-chave e quaisquer condições para a pesquisa usando os cartões de condição pré-construídos ou usando a Linguagem de Consulta de Palavra-chave (KQL). Para obter mais informações, consulte [Criar consultas de pesquisa.](building-search-queries.md)
