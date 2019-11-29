---
title: Usando o explorador de conteúdo de classificação de dados (visualização)
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
description: O explorador de conteúdo permite que se veja nativamente os itens rotulados.
ms.openlocfilehash: 6f062901acbf149f6fc56c266d10b370ed0c1112
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2019
ms.locfileid: "39268415"
---
# <a name="using-data-classification-content-explorer-preview"></a>Usando o explorador de conteúdo de classificação de dados (visualização)

O explorador de conteúdo de classificação de dados permite que os itens que foram resumidos na página visão geral sejam exibidos nativamente.

## <a name="content-explorer"></a>Explorador de conteúdo

O Explorador de conteúdo é uma representação atual dos itens que têm um rótulo de confidencialidade, um rótulo de retenção ou foram classificados como um tipo de informação confidencial em sua organização.

![captura de tela do explorador de conteúdo](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a>Permissões

Há duas funções que concedem acesso ao Explorador de conteúdo:

- **Visualizador de Listas do Explorador de Conteúdo**: a associação nesta função permite que você veja cada item e seu local.

- **Visualizador de Conteúdos do Explorador de Conteúdo**: a associação nesta função permite exibir o conteúdo de cada item na lista.

A conta que você usa para acessar o Explorador de conteúdo deve estar em uma ou em ambas as funções. Essas são funções independentes e não cumulativas. Por exemplo, se você deseja conceder a uma conta a capacidade de exibir apenas os itens e seus locais, conceda direitos ao visualizador de Listas do Explorador de Conteúdo. Se você deseja que a mesma conta também possa exibir o conteúdo dos itens da lista, conceda também direitos ao visualizador de Conteúdos do Explorador de Conteúdo.

### <a name="how-to-use-content-explorer"></a>Como usar o explorador de conteúdo

1. Abra o **centro de conformidade do Microsoft 365**  > **Classificação de dados** > ** Explorador de conteúdo**.
2. Se souber o nome do rótulo ou o tipo de informação confidencial, digite-o na caixa Pesquisar.
3. Como alternativa, você pode procurar o item expandindo o tipo de rótulo e selecionando o rótulo da lista; um dos itens da parte de rótulo de retenção da lista é mostrado abaixo.
4. Selecione um local em **Todas as localizações** e faça uma busca detalhada na estrutura de pastas para o item.
5. Clique duas vezes para abrir o item nativamente no explorador de conteúdo.

## <a name="see-also"></a>Confira também

- [Rótulos de confidencialidade](sensitivity-labels.md)
- [Rótulos de retenção](labels.md)
- [O que os tipos de informação confidencial procuram](what-the-sensitive-information-types-look-for.md)
- [Visão geral de políticas de retenção](retention-policies.md)
