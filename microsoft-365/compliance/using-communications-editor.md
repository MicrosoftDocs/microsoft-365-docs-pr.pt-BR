---
title: Usar o editor de comunicações
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
description: Use o Editor de Comunicações para alterar variáveis de campo de texto e mesclagem ao formatar o conteúdo.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769156"
---
# <a name="use-the-communications-editor"></a>Usar o editor de comunicações

À medida que você define o conteúdo do conteúdo do portal, as notificações de responsabilidade legal e os lembretes/escalonamentos relacionados, você pode usar o Editor de Comunicações para formatar e personalizar dinamicamente o conteúdo.

## <a name="rich-text-editor"></a>Editor de rich text

O Editor de Comunicações permite que o usuário personalize o texto usando as opções do editor. Por exemplo, os usuários podem alterar tipos de fonte, criar listas com marcador, realçar o conteúdo e muito mais.

## <a name="merge-field-variables"></a>Mesclar variáveis de campo

Você pode usar variáveis de mala direta de email do Editor de Comunicações para incorporar atributos custodiantes personalizados no corpo do texto de uma comunicação. Quando enviado para o custodiante, o campo de mesclagem será preenchido com o campo correspondente. Por exemplo, quando enviado para o custodiante John Smith, o campo de mesclagem [Nome custodiante] seria traduzido com o nome correspondente.

Você pode usar campos de mala direta selecionando **os** ícones do campo Mesclar na parte superior do controle do editor de rich text. O espaço reservado será adicionado com base no local do cursor do usuário.

### <a name="list-of-merge-field-variables"></a>Lista de variáveis de campo de mesclagem

| Nome do campo                  | Detalhes do campo |
| :------------------- | :------------------- |
| Nome de exibição  | O nome e o sobrenome do custodiatário. | 
| Link de confirmação | Um link personalizado para registrar a confirmação de cada custodiado.|                 |
| Portal Link     | Um link personalizado para o Portal de Conformidade do custodiatário.|                |
| Diretor de emissão                   | O endereço de email do responsável pela emissão especificado.|                   |
| Data de emissão                   | A data em que o aviso foi emitido (UTC).              |
|||
