---
title: Notas de versão de visualização de dados (visualização)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Notas de versão para a visualização pública de classificação de dados.
ms.openlocfilehash: fecf643d12cf544c16570c173b15bb1e0dc043f0
ms.sourcegitcommit: 3d17c1d6b80672719b1878e2f321f0de39595226
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887329"
---
# <a name="data-classification-public-preview-release-notes-preview"></a>Notas de versão de visualização pública de classificação de dados (visualização)

Esta versão pública apresenta a nova funcionalidade em que a verificação de conteúdo confidencial e o conteúdo rotulado começa *antes* de você criar as políticas. Isso se chama **gerenciamento de alterações zero**. Isso permite que você veja o impacto de que todos os rótulos de retenção e sensibilidade estão tendo no ambiente e capacitam você a começar a avaliar a proteção e as necessidades de políticas de governança.

Examine estas notas de versão para ter a melhor experiência com esta visualização pública. Vamos trabalhar no tratamento desses pontos entre agora e disponibilidade geral (GA).

## <a name="permissions-for-accessing-content-explorer"></a>Permissões para acessar o Gerenciador de conteúdo

O acesso ao Gerenciador de conteúdo é altamente restrito porque permite ler o conteúdo dos arquivos digitalizados. O acesso ao Gerenciador de conteúdo exige associação no **Visualizador de lista do conteúdo do Explorer**e **Visualizador de conteúdo do Gerenciador de conteúdo** grupos de funções. Nenhuma conta tem acesso ao Gerenciador de conteúdo por padrão. Confira, [Usando o explorador de conteúdo de classificação de dados (visualização)](data-classification-content-explorer.md#permissions). Um administrador global, um administrador de conformidade ou um administrador de dados pode atribuir o **Visualizador de lista do Gerenciador de conteúdo ** necessário e **Visualizador de conteúdo do Gerenciador de conteúdo** a associação do grupo de função.

> [!TIP]
> O **Visualizador de lista Gerenciador de conteúdo**e o **Visualizador de conteúdo do Gerenciador de conteúdo** grupos de funções podem não aparecer na página permissões enquanto o controle de acesso baseado em função (RBAC) está sendo implantado em todo o mundo. Se eles não estiverem aparecendo na página permissões, você deverá criar um grupo de funções personalizado e atribuir a função `data classification list viewer` e ou as funções `data classification content viewer` ao seu grupo de funções personalizadas.

## <a name="exchange-mailbox-count"></a>Contagem de caixa de correio do Exchange

Você observará que uma pequena dica de ferramenta é exibida quando você detalha as caixas de correio do Exchange. Isso é para destacar o fato de que a contagem agregada exibida para tipo de informações confidenciais, rótulo de confidencialidade e rótulo de retenção pode não corresponder exatamente ao número de itens que você encontrará dentro da caixa de correio. Isso ocorre porque o detalhamento da pasta busca a visualização dinâmica de conteúdo, que é classificada, enquanto a contagem agregada é calculada.

## <a name="seeing-guids-instead-of-label-names"></a>Vendo GUIDs em vez de nomes de rótulos

Os clientes de visualização particular viram instâncias em que a exclusão de um rótulo que tem o conteúdo já foi carimbada com resultados em nomes de etiquetas que resolvem um GUID de 32 bits no Gerenciador de conteúdo e o explorador de atividades, em vez do nome do rótulo. 

## <a name="rendering-of-encrypted-documents"></a>Processamento de documentos criptografados

Os arquivos do SharePoint, Exchange e OneDrive que estão criptografados não serão renderizados no Gerenciador de conteúdo. Esse é um problema sensível que exige um equilíbrio entre a necessidade de ver o conteúdo do arquivo no Gerenciador de conteúdo e a necessidade de manter o conteúdo criptografado. Com as permissões concedidas pelo **Visualizador de lista do Gerenciador de conteúdo **e **Visualizador de conteúdo do Gerenciador de conteúdo** grupos de funções, você verá uma exibição de lista dos arquivos, os metadados do arquivo e um link que você pode usar para acessar o conteúdo pelo cliente da Web.

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>Caracteres com suporte em nomes de rótulo de retenção na pesquisa do SharePoint

O SharePoint Search não oferece suporte a nomes de rótulo de retenção com `-`ou `_` neles. Por exemplo `Label-MIP` e `Label_MIP` não têm suporte. A pesquisa do SharePoint oferece suporte a esses caracteres em nomes de rótulos e informações confidenciais.

## <a name="see-also"></a>Confira também

- [Introdução à classificação de dados (visualização)](data-classification-overview.md)
- [Exibir atividade do rótulo (visualização)](data-classification-activity-explorer.md)
- [Exibir conteúdo rotulado (visualização)](data-classification-content-explorer.md)
- [Rótulos de confidencialidade ](sensitivity-labels.md)
- [Rótulos de retenção](labels.md)
- [O que os tipos de informação confidencial procuram](what-the-sensitive-information-types-look-for.md)

