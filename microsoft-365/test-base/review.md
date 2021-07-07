---
title: Analisar
description: Revise a seção após a integração.
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 3bbd4959dd2f595e6e33e7967a719cf64072c06f
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322492"
---
# <a name="step-6-review-your-selections-to-create-your-package"></a>Etapa 6: Revise suas seleções para criar seu pacote.

1.  Nesta guia, o serviço exibe os detalhes do teste e executa uma verificação de conclusão rápida. 

    Uma ```Validation passed``` mensagem ou mostra se você pode prosseguir para as ```Validation failed``` próximas etapas ou não.

2.  Revise os detalhes do teste e, se satisfeito, clique no ```Create``` botão. 

![Exibir validação](Media/validation.png)

3.  Isso integra seu pacote ao ambiente base de teste. Se o pacote for criado com êxito, um teste automatizado que verificará se o pacote pode ser executado com êxito no Azure será acionado.

![Resultado bem-sucedido](Media/successful.png)

> [!Note]
> Você receberá uma notificação do portal do Azure para notificá-lo sobre o sucesso ou falha da verificação do pacote. 
>
> Observe que o processo pode levar até 24 horas, portanto, é provável que sua página da Web tenha tempo de vida se você não estiver ativo nele e, portanto, a notificação não informará sobre a conclusão dessa execução sob demanda. 

  - Se isso acontecer, você poderá exibir o status do pacote na ```Manage packages``` guia.

![Imagem para gerenciar pacotes](Media/managepackages.png)

  - Para testes bem-feitos, seus resultados podem ser vistos por meio dos , e páginas em intervalos agendados, geralmente começando alguns dias após ```Test Summary``` ```Security Updates Results``` o ```Feature Updates Results``` carregamento.
  
  - Embora tenha falhado nos testes, exige que você carregue um novo pacote. 
  
    Você pode baixar o ```test logs``` para análise mais detalhada das páginas ' e ```Security update results``` ```Feature updates results``` .

  - Se você experimentar falhas de teste repetidas, entre em contato testbasepreview@microsoft.com com detalhes do seu erro. 

## <a name="next-steps"></a>Próximas etapas

Descubra nossas Diretrizes de Conteúdo por meio do link abaixo.
> [!div class="nextstepaction"]
> [Próxima etapa](contentguideline.md)
