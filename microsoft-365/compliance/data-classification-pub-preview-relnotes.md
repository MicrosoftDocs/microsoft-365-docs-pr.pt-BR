---
title: Notas de versão de classificação de dados
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
description: Notas de versão para a classificação de dados.
ms.openlocfilehash: bbef6729680db2c9a6aec4caa9036ec23fad6949
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327594"
---
# <a name="data-classification-release-notes"></a>Notas de versão de classificação de dados

Examine estas notas de versão para ter a melhor experiência com a classificação de dados.

## <a name="exchange-mailbox-count"></a>Contagem de caixa de correio do Exchange

Você observará que uma pequena dica de ferramenta é exibida quando você detalha as caixas de correio do Exchange. Isso é para destacar o fato de que a contagem agregada exibida para tipo de informações confidenciais, rótulo de confidencialidade e rótulo de retenção pode não corresponder exatamente ao número de itens que você encontrará dentro da caixa de correio. Isso ocorre porque o detalhamento da pasta busca a visualização dinâmica de conteúdo, que é classificada, enquanto a contagem agregada é calculada.


## <a name="rendering-of-encrypted-documents"></a>Processamento de documentos criptografados

Os arquivos do SharePoint, Exchange e OneDrive que estão criptografados não serão renderizados no Gerenciador de conteúdo. Esse é um problema sensível que exige um equilíbrio entre a necessidade de ver o conteúdo do arquivo no Gerenciador de conteúdo e a necessidade de manter o conteúdo criptografado. Com as permissões concedidas pelo **Visualizador de lista do Gerenciador de conteúdo **e **Visualizador de conteúdo do Gerenciador de conteúdo** grupos de funções, você verá uma exibição de lista dos arquivos, os metadados do arquivo e um link que você pode usar para acessar o conteúdo pelo cliente da Web.

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>Caracteres com suporte em nomes de rótulo de retenção na pesquisa do SharePoint

O SharePoint Search não oferece suporte a nomes de rótulo de retenção com `-`ou `_` neles. Por exemplo `Label-MIP` e `Label_MIP` não têm suporte. A pesquisa do SharePoint oferece suporte a esses caracteres em nomes de rótulos e informações confidenciais.

## <a name="onedrive-remains-in-preview"></a>O OneDrive permanece no modo versão prévia

Ouvimos seus comentários sobre a integração do OneDrive durante nosso programa de versão prévia. Enquanto percorrermos os detalhes, pode ser que você encontre dados/fluxos inconsistentes. Continuaremos a exibir o OneDrive na visualização até que todas as correções estejam disponíveis. Agradecemos o seu apoio contínuo neste tema.


## <a name="see-also"></a>Confira também

- [Introdução à classificação de dados (visualização)](data-classification-overview.md)
- [Exibir atividade do rótulo (visualização)](data-classification-activity-explorer.md)
- [Exibir conteúdo rotulado (visualização)](data-classification-content-explorer.md)
- [Rótulos de confidencialidade ](sensitivity-labels.md)
- [Rótulos de retenção](labels.md)
- [Definições da entidade por tipo de informações confidenciais](sensitive-information-type-entity-definitions.md)