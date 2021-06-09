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
description: Use o Editor de Comunicações para alterar o texto e mesclar variáveis de campo ao formatar seu conteúdo.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769156"
---
# <a name="use-the-communications-editor"></a>Usar o editor de comunicações

À medida que você define o conteúdo do seu conteúdo de portal, notificações de responsabilidade legal e lembretes/escalações relacionados, você pode usar o Editor de Comunicações para formatar e personalizar dinamicamente seu conteúdo.

## <a name="rich-text-editor"></a>Editor de texto rich

O Editor de Comunicações permite que o usuário personalize o texto usando as opções do editor. Por exemplo, os usuários podem alterar tipos de fonte, criar listas com marcador, realçar conteúdo e muito mais.

## <a name="merge-field-variables"></a>Mesclar variáveis de campo

Você pode usar variáveis de mesclagem de email do Editor de Comunicações para incorporar atributos de custodiante personalizados no texto do corpo de uma comunicação. Quando enviado para o custodiante, o campo de mesclagem será preenchido com o campo correspondente. Por exemplo, quando enviado para o custodiante John Smith, o campo de mesclagem [Nome da Custodiação] seria convertido com o nome correspondente.

Você pode usar campos de mala direta selecionando os ícones do campo **Mesclar** na parte superior do controle editor de rich-text. O espaço reservado será adicionado com base no local do cursor dos usuários.

### <a name="list-of-merge-field-variables"></a>Lista de variáveis de campo de mesclagem

| Nome do campo                  | Detalhes de campo |
| :------------------- | :------------------- |
| Nome de exibição  | O nome e o sobrenome do custodiado. | 
| Link de Confirmação | Um link personalizado para registrar o reconhecimento de cada custodiado.|                 |
| Portal Link     | Um link personalizado para o Portal de Conformidade do custodiado.|                |
| Diretor de emissão                   | O endereço de email do oficial de emissão especificado.|                   |
| Data de emissão                   | A data em que o aviso foi emitido (UTC).              |
|||
