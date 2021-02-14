---
title: Repetir uma Pesquisa de Conteúdo para resolver um erro de local de conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Durante uma investigação, você pode usar o botão Repetir para resolver Pesquisas de Conteúdo com erros de localização de conteúdo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b3aed9c1d2d1fe3c40adb64b4854ef359f931bcb
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357551"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>Repetir uma Pesquisa de Conteúdo para resolver um erro de local de conteúdo

Ao usar a Pesquisa de Conteúdo no centro de conformidade e segurança para pesquisar um grande número de caixas de correio, você pode receber erros de pesquisa semelhantes ao erro:

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

Esses erros (com códigos de erro CS001-002, CS003-002, CS008-009, CS012-002 e outros erros no formato CS0XX-0XX) indicam que a Pesquisa de Conteúdo falhou ao pesquisar locais de conteúdo específicos; neste exemplo, duas caixas de correio não foram pesquisadas. Esses erros são exibidos na página do flyout de detalhes de status da Pesquisa de Conteúdo.

## <a name="cause-of-content-location-errors"></a>Causa dos erros de localização do conteúdo

Ao pesquisar um grande número de caixas de correio, a pesquisa é distribuída por milhares de servidores em um datacenter da Microsoft. A qualquer momento, servidores específicos podem estar no estado de reinicialização ou em processo de fazer o failing over para cópias redundantes. Em qualquer um desses casos, a solicitação da Pesquisa de Conteúdo para recuperar dados irá passar do tempo. No exemplo anterior, os erros das caixas de correio que falharam foram o resultado do tempo de pesquisa.

## <a name="resolving-content-location-errors"></a>Resolvendo erros de localização de conteúdo

Reiniciar a pesquisa geralmente resultará em erros semelhantes em servidores diferentes. Em vez de reiniciar a  pesquisa, clique no botão Repetir exibido na parte superior da página de resultados da pesquisa.

![Clique no botão Repetir para resolver erros de localização de conteúdo](../media/retrycontentsearch3.png)

Isso resultará em repetir a pesquisa apenas para as caixas de correio que falharam. Quando você repetir a pesquisa, os outros resultados retornados com êxito serão mantidos.

## <a name="tips-to-avoid-content-location-errors"></a>Dicas para evitar erros de localização de conteúdo

Aqui estão algumas causas adicionais de erros de localização de conteúdo e algumas dicas para ajudá-lo a evitá-los ao pesquisar um grande número de caixas de correio.

- A caixa de correio que está sendo pesquisada pode estar ocupada devido à atividade do usuário. Nesse caso, o serviço de pesquisa pode se acelerar para impedir que a caixa de correio fique indisponível. Para evitar isso, tente executar pesquisas fora do horário comercial.

- A consulta de pesquisa pode estar recuperando muito conteúdo da caixa de correio. Se possível, tente restringir o escopo da pesquisa usando palavras-chave, intervalos de datas e condições de pesquisa.

- Muitas palavras-chave ou frases de palavra-chave ao criar uma consulta de pesquisa usando a lista [de palavras-chave.](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches) Quando você executa uma consulta de pesquisa que usa a lista de palavras-chave, o serviço basicamente executa uma pesquisa separada para cada linha na lista de palavras-chave para que as estatísticas possam ser geradas. Se você estiver usando a lista de palavras-chave em consultas de pesquisa, minimize o número de linhas na lista de palavras-chave ou divida o número de palavras-chave em listas menores e crie uma pesquisa diferente para cada lista de palavras-chave.

  > [!NOTE]
  > Para ajudar a reduzir problemas causados por listas de palavras-chave grandes, agora você está limitado a um máximo de 20 linhas na lista de palavras-chave de uma consulta de pesquisa.

- Muitas pesquisas estão sendo executadas na mesma caixa de correio ao mesmo tempo. Se possível, tente executar uma pesquisa por vez em qualquer caixa de correio.

- Pesquisar muitas caixas de correio em uma única pesquisa. A probabilidade de erros de localização do conteúdo aumenta ao pesquisar um grande número de caixas de correio. Se possível, tente executar várias pesquisas para que cada pesquisa inclua um subconjunto de caixas de correio em sua organização.

- A manutenção necessária está sendo executada na caixa de correio. Embora essa causa provavelmente ocorra com pouca freqüência, aguarde um pouco depois de receber o erro de local de conteúdo e, em seguida, repetir a pesquisa.
