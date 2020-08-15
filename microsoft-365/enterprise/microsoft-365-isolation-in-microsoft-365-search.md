---
title: Isolamento de locatário no Microsoft 365 Search
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
description: Neste artigo, encontre uma explicação sobre como o isolamento de locatário funciona para separar dados de locatários na pesquisa do Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9b204e9c1f3ef459852900f3403a21f7ea40541f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686938"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a>Isolamento de locatário no Microsoft 365 Search

A pesquisa do SharePoint Online usa um modelo de separação de locatários que equilibra a eficiência de estruturas de dados compartilhadas com proteção contra vazamento de informações entre locatários. Com esse modelo, impedimos os recursos de pesquisa de:

- Retornar resultados de consulta que contenham documentos de outros locatários
- Expor informações suficientes nos resultados de consulta que um usuário experiente pode inferir informações sobre outros locatários
- Mostrando o esquema ou as configurações de outro locatário
- Misturar informações de processamento de análise entre locatários ou armazenar resultados no locatário incorreto
- Usando entradas de dicionário de outro locatário

Para cada tipo de dados de locatário, usamos uma ou mais camadas de proteção no código para evitar vazamento acidental de informações. Os dados mais importantes têm mais camadas de proteção para garantir que um único defeito não resulte em vazamento real ou percebido.

## <a name="tenant-separation-for-the-search-index"></a>Separação de locatário para o índice de pesquisa

O índice de pesquisa é armazenado em disco nos servidores que hospedam os componentes do índice e os locatários compartilham os arquivos de índice. Os documentos indexados de um locatário são visíveis apenas para consultas para o locatário. Três mecanismos independentes impedem o vazamento de informações:

- Filtragem de ID de locatário
- Prefixação de termo de ID de locatário
- Verificações de ACL

Todos os três mecanismos teriam falhado para a pesquisa retornar documentos ao locatário errado.

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>Filtragem de ID de locatário e prefixação de termos de ID de locatário

Os prefixos de pesquisa a cada termo indexado no índice de texto completo com a ID do locatário. Por exemplo, quando o termo "*foo*" é indexado para um locatário com uma ID de "*123*", a entrada no índice de texto completo é "*123foo".*

Cada consulta é convertida para incluir a ID de locatário usando um processo chamado filtragem de ID de locatário. Por exemplo, a consulta "*foo*" é convertida em "<> *GUID* . *foo* E *tenantid*: <*GUID*> ", onde <*GUID*> representa o locatário executando a consulta. Essa conversão de consulta ocorre em cada nó de índice, e nenhuma consulta ou o processamento de conteúdo pode influenciar. Como a ID do locatário é adicionada a todas as consultas, a frequência de um termo em outros locatários não pode ser deduzida examinando a melhor classificação de correspondência em um locatário.

A prefixação de termos de ID de locatário ocorre somente no índice de texto completo. Pesquisas em campo, como "*título: foo*", acesse um índice de pesquisa sintético em que os termos não são prefixados por ID de locatário. Em vez disso, as pesquisas de campo são prefixadas com o nome do campo. Por exemplo, a consulta "*título: foo*" é convertida em "*Fields. title: foo e Fields. tenantid*: <*GUID*>". Como a frequência de um termo não influencia a classificação de acertos no índice de pesquisa sintética, não há necessidade de separação de locatários por prefixação de termos. Para uma pesquisa em campo como "*título: foo*", a separação de conteúdo do locatário depende da filtragem da ID do locatário por conversão de consulta.

## <a name="document-access-control-list-checks"></a>Verificações de lista de controle de acesso a documentos

A pesquisa controla o acesso a documentos por meio de ACLs salvas no índice de pesquisa. Cada item é indexado com um conjunto de termos em um campo de ACL especial. O campo ACL contém um termo por grupo ou usuário que pode exibir o documento. Cada consulta é aumentada com uma lista de termos de ACE (entrada de controle de acesso), uma para cada grupo ao qual o usuário autenticado pertence.

Por exemplo, uma consulta como "<*guid*>. *foo e tenantid*: <*GUID*> "torna-se:" <> *GUID* . *foo e tenantid*: <*GUID* >  *e* (*docacls:* < *ACE1* >  *ou docacls*: <*ACE2* >  *ou docacls*: <*ace3* >  *...*) "

Como os identificadores de usuário e de grupo e as ACEs são exclusivos, isso fornece um nível extra de segurança entre os locatários para documentos que são visíveis apenas para alguns usuários. O mesmo é o caso da ACE especial "todos exceto usuários externos" que concede acesso a usuários regulares no locatário. No entanto, como as ACEs de "todos" são as mesmas para todos os locatários, a separação de locatários para documentos públicos depende da filtragem da ID do locatário. As ACEs de negação também são suportadas. O aumento da consulta adiciona uma cláusula que remove um documento do resultado quando há uma correspondência com uma ACE de negação.

Na pesquisa do Exchange Online, o índice é particionado na ID da caixa de correio para caixas de correio do usuário individual em vez de ID do locatário (ID da assinatura) como no SharePoint Online. O mecanismo de particionamento é o mesmo que o SharePoint Online, mas não há filtragem de ACL.
