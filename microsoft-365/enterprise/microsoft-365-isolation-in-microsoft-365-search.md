---
title: Isolamento de locatário no Microsoft 365 Search
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
description: Neste artigo, encontre uma explicação de como o isolamento de locatário funciona para separar os dados de locatário na Pesquisa do Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3416afdeceaa7000b516ec89b4a2a1e59d8708d0
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332395"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a>Isolamento de locatário no Microsoft 365 Search

A pesquisa do SharePoint Online usa um modelo de separação de locatário que equilibra a eficiência de estruturas de dados compartilhadas com proteção contra vazamento de informações entre locatários. Com esse modelo, impedimos os recursos de Pesquisa de:

- Retornando resultados de consulta que contêm documentos de outros locatários
- Expor informações suficientes em resultados de consulta que um usuário qualificado poderia inferir informações sobre outros locatários
- Mostrando esquema ou configurações de outro locatário
- Misturar informações de processamento de análise entre locatários ou armazenar resultados no locatário errado
- Usando entradas de dicionário de outro locatário

Para cada tipo de dados de locatário, usamos uma ou mais camadas de proteção no código para evitar o vazamento acidental de informações. Os dados mais críticos têm a maioria das camadas de proteção para garantir que um único defeito não resulte em vazamento de informações real ou percebido.

## <a name="tenant-separation-for-the-search-index"></a>Separação de locatário para o índice de pesquisa

O índice de pesquisa é armazenado em disco nos servidores que hospedam os componentes do índice e os locatários compartilham os arquivos de índice. Os documentos indexados de um locatário são visíveis apenas para consultas desse locatário. Três mecanismos independentes impedem o vazamento de informações:

- Filtragem de ID de locatário
- Prefixação de termos de ID de locatário
- Verificações de ACL

Todos os três mecanismos teriam que falhar para que a Pesquisa retornasse documentos para o locatário errado.

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>Filtragem de ID de Locatário e Prefixação de Termos de ID de Locatário

A pesquisa prefixa cada termo indexado no índice de texto completo com a ID de locatário. Por exemplo, quando o termo "*foo*" é indexado para um locatário com uma ID de "*123*", a entrada no índice de texto completo é "*123foo ".*

Cada consulta é convertida para incluir a ID de locatário usando um processo chamado filtragem de ID de locatário. Por exemplo, a consulta "*foo*" é convertida em "<*guid*>. *foo* AND *tenantID*:<*guid*>", onde <*guid*> representa o locatário executando a consulta. Essa conversão de consulta ocorre em cada nó de índice e nem a consulta nem o processamento do conteúdo podem influenciá-la. Como a ID de locatário é adicionada a cada consulta, a frequência de um termo em outros locatários não pode ser inferida, observando a melhor classificação de melhor combinação em um locatário.

O prefixo do termo de ID do locatário ocorre somente no índice de texto completo. Pesquisas em campo, como "*title:foo*", vão para um índice de pesquisa sintética onde os termos não são prefixados pela ID de locatário. Em vez disso, as pesquisas em campo são prefixadas com o nome do campo. Por exemplo, a consulta "*title:foo*" é convertida em "*fields.title:foo AND fields.tenantID*:<*guid*>". Como a frequência de um termo não influencia a classificação de acertos no índice de pesquisa sintética, não há necessidade de separação de locatário pela prefixação de termos. Para uma pesquisa em campo como "*title:foo*", a separação de conteúdo do locatário depende da filtragem de ID do locatário por conversão de consulta.

## <a name="document-access-control-list-checks"></a>Verificações da Lista de Controle de Acesso a Documentos

A pesquisa controla o acesso a documentos por meio de ACLs salvas no índice de pesquisa. Cada item é indexado com um conjunto de termos em um campo ACL especial. O campo ACL contém um termo por grupo ou usuário que pode exibir o documento. Cada consulta é aumentada com uma lista de termos de entrada de controle de acesso (ACE), um para cada grupo ao qual o usuário autenticado pertence.

Por exemplo, uma consulta como "<*guid*>. *foo AND tenantID*:<*guid*>" se torna: "<*guid*>. *foo AND tenantID*:<*guid* >  *AND* (*docACL:* < *ace1* >  *OR docACL*:<*ace2* >  *OR docACL*:<*ace3* >  *...*)"

Como os identificadores de usuário e grupo e, portanto, as ACEs são exclusivas, isso fornece um nível extra de segurança entre locatários para documentos que são visíveis apenas para alguns usuários. O mesmo ocorre com a ACE especial "Todos exceto os usuários externos" que concede acesso a usuários regulares no locatário. Porém, como as ACEs para "Todos" são as mesmas para todos os locatários, a separação de locatários para documentos públicos depende da filtragem de ID de locatário. Negar ACEs também são suportados. O aumento da consulta adiciona uma cláusula que remove um documento do resultado quando há uma combinação com uma ACE de negação.

Na pesquisa do Exchange Online, o índice é particionado na ID de caixa de correio para caixas de correio de usuários individuais em vez de ID de locatário (ID de assinatura) como no SharePoint Online. O mecanismo de particionamento é o mesmo que o SharePoint Online, mas não há filtragem de ACL.
