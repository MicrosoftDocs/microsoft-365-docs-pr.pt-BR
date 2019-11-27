---
title: Usando o explorador de atividade de classificação de dados
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
description: O explorador de atividade dá o toque final na funcionalidade do recurso de classificação de dados, permitindo que você veja e filtre as ações que os usuários estão executando no conteúdo rotulado.
ms.openlocfilehash: 272de0400e89f9829b3ead5d4523db27789c0c44
ms.sourcegitcommit: 9d0a025ea9e265d515a034de0102eabcf47d11f5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2019
ms.locfileid: "39268941"
---
# <a name="view-activity-on-your-labeled-content-preview"></a>Exibir atividade do seu conteúdo rotulado (visualização)

As guias visão geral de classificação de dados e explorador de conteúdo dão visibilidade ao conteúdo que foi descoberto e rotulado e mostra onde está esse conteúdo. O explorador de atividade arremata esse pacote de funcionalidade permitindo monitorar o que está sendo feito com o conteúdo rotulado. O explorador de atividades fornece um modo de exibição histórica.

![Visão geral da captura de tela do Explorador de atividades](media/data-classification-activity-explorer-1.png)

Você pode filtrar os dados de acordo com:

- intervalo de datas
- tipo de atividade
- localização
- usuário
- rótulo de confidencialidade
- rótulo de retenção


Você pode exibir os dados como uma lista ou como um gráfico de barras.

## <a name="activity-type"></a>Tipo de atividade

O Microsoft 365 monitora e relata 12 tipos de atividades em todo o SharePoint Online, OneDrive e pontos de extremidade. Os pontos de extremidade são dispositivos de usuário que executam o Windows 10.

- Arquivo foi criado
- Arquivo foi modificado
- Arquivo foi renomeado
- Arquivo foi copiado para a nuvem
- Arquivo foi acessado por aplicativo que não tem permissão de acesso
- Arquivo foi impresso
- Arquivo foi copiado para mídia removível
- Arquivo copiado ser compartilhado na rede
- Arquivo foi lido
- Arquivo foi copiado para a área de transferência
- Rótulo foi aplicado
- Rótulo foi alterado (atualizado, regredido ou removido)

O vantagem de ficar sabendo que ações estão sendo tomadas com o conteúdo rotulado como confidencial é que você pode verificar se os controles que você já colocou em ação, tais como as [políticas de prevenção de perda de dados](data-loss-prevention-policies.md) estão sendo eficazes ou não. Se elas não estiverem funcionando, ou se você descobrir algo inesperado, como um grande número de itens que foram rotulados `highly confidential` e regredidos `general`, você pode gerenciar suas diversas políticas e executar novas ações para restringir o comportamento indesejado.

Depois de definir os filtros, você poderá:

- Passe o mouse sobre um segmento do gráfico de barras para ver o número de itens que se encontram nessa categoria ![imagem do explorador de atividade ao passar o mouse](media/data-classification-activity-explorer-hover-over-2.png)
- exportar os dados
- selecione um determinado item na lista e exiba os detalhes da ação no submenu

![detalhes do submenu do explorador de atividade](media/data-classification-activity-explorer-fly-out-3.png)

## <a name="see-also"></a>Confira também
- [Rótulos de confidencialidade](sensitivity-labels.md)
- [Rótulos de retenção](labels.md)
- [O que os tipos de informação confidencial procuram](what-the-sensitive-information-types-look-for.md)
- [Visão geral de políticas de retenção](retention-policies.md)