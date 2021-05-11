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
description: Durante uma investigação, você pode usar o botão Repetir para resolver Pesquisas de Conteúdo que têm erros de localização de conteúdo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fb85a882ef111aa38a73dbe155a9ad0ef57dd3de
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311815"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>Repetir uma Pesquisa de Conteúdo para resolver um erro de local de conteúdo

Quando você usa a Pesquisa de Conteúdo no centro de segurança e conformidade para pesquisar um grande número de caixas de correio, você pode obter erros de pesquisa semelhantes ao erro:

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

Esses erros (com códigos de erro de CS001-002, CS003-002, CS008-009, CS012-002 e outros erros do formulário CS0XX-0XX) indicam que a Pesquisa de Conteúdo falhou ao pesquisar locais de conteúdo específicos; neste exemplo, duas caixas de correio não foram pesquisadas. Esses erros são exibidos na página de detalhes do status da Pesquisa de Conteúdo.

## <a name="cause-of-content-location-errors"></a>Causa de erros de localização de conteúdo

Ao pesquisar um grande número de caixas de correio, a pesquisa é distribuída entre milhares de servidores em um datacenter da Microsoft. A qualquer momento, servidores específicos podem estar em estado de reinicialização ou em processo de falha em cópias redundantes. Em qualquer um desses casos, a solicitação da Pesquisa de Conteúdo para recuperar dados passará do tempo. No exemplo anterior, os erros das caixas de correio que falharam eram o resultado do tempo de pesquisa.

## <a name="resolving-content-location-errors"></a>Resolução de erros de localização de conteúdo

A reinicialização da pesquisa geralmente resultará em erros semelhantes em servidores diferentes. Em vez de reiniciar a pesquisa, clique no botão **Repetir** exibido na parte superior da página de resultados da pesquisa.

![Clique no botão Repetir para resolver erros de local de conteúdo](../media/retrycontentsearch3.png)

Isso resultará na tentativa de repetir a pesquisa apenas para as caixas de correio que falharam. Quando você repetir a pesquisa, os outros resultados retornados com êxito serão mantidos.

## <a name="tips-to-avoid-content-location-errors"></a>Dicas para evitar erros de localização de conteúdo

Aqui estão algumas causas adicionais de erros de localização de conteúdo e algumas dicas para ajudá-lo a evitá-los ao pesquisar um grande número de caixas de correio.

- A caixa de correio que está sendo pesquisada pode estar ocupada devido à atividade do usuário. Nesse caso, o serviço de pesquisa pode se controlar para impedir que a caixa de correio fique indisponível. Para evitar isso, tente executar pesquisas durante o horário não comercial.

- A consulta de pesquisa pode estar recuperando muito conteúdo da caixa de correio. Se possível, tente restringir o escopo da pesquisa usando palavras-chave, intervalos de datas e condições de pesquisa.

- Muitas palavras-chave ou frases de palavra-chave ao criar uma consulta de pesquisa usando a lista [de palavras-chave](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches). Quando você executa uma consulta de pesquisa que usa a lista de palavras-chave, o serviço executa essencialmente uma pesquisa separada para cada linha na lista de palavras-chave para que as estatísticas possam ser geradas. Se você estiver usando a lista de palavras-chave nas consultas de pesquisa, minimize o número de linhas na lista de palavras-chave ou divida as palavras-chave de número em listas menores e crie uma pesquisa diferente para cada lista de palavras-chave.

  > [!NOTE]
  > Para ajudar a reduzir problemas causados por listas de palavras-chave grandes, agora você está limitado a no máximo 20 linhas na lista de palavras-chave de uma consulta de pesquisa.

- Muitas pesquisas estão sendo realizadas na mesma caixa de correio ao mesmo tempo. Se possível, tente executar uma pesquisa por vez em qualquer caixa de correio.

- Pesquisar muitas caixas de correio em uma única pesquisa. A probabilidade de erros de localização de conteúdo aumenta ao pesquisar um grande número de caixas de correio. Se possível, tente executar várias pesquisas para que cada pesquisa inclua um subconjunto de caixas de correio em sua organização.

- A manutenção necessária está sendo executada na caixa de correio. Embora essa causa provavelmente ocorra com pouca freqüência, aguarde um pouco depois de receber o erro de local de conteúdo e, em seguida, repetir a pesquisa.
