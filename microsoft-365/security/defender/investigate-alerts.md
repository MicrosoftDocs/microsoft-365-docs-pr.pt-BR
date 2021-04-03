---
title: Investigar alertas no Microsoft 365 Defender
description: Investigue alertas vistos em dispositivos, usuários e caixas de correio.
keywords: incidentes, alertas, investigar, correlação, ataque, máquinas, dispositivos, usuários, identidades, identidade, caixa de correio, email, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 989574a860bea798c48e077f5633c31eb857e85e
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500941"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>Investigar alertas no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Os alertas são a base de todos os incidentes e indicam a ocorrência de eventos mal-intencionados ou suspeitos em seu ambiente. Os alertas geralmente fazem parte de um ataque mais amplo e fornecem pistas sobre um incidente.

No Microsoft 365 Defender, os alertas relacionados são agregados em incidentes de formulário. Os incidentes sempre fornecerão o contexto mais amplo de um ataque, no entanto, a investigação de alertas pode ser valiosa quando uma análise mais profunda é necessária. 



## <a name="using-alert-pages-in-investigations"></a>Usando páginas de alerta em investigações

Na guia Alertas de qualquer página de incidente, selecionar um alerta o leva às páginas de alerta individuais. Uma página de alerta é composta por três seções: ativos afetados, o alerta e o painel de detalhes.

![Imagem da página de alerta de exemplo](../../media/new-alert-page2.png)

Ao longo de uma página de alerta, você pode selecionar o ícone de três pontos (**...**) ao lado de qualquer entidade para que você possa ver ações disponíveis, como abrir a página de ativo específica ou realizar etapas de correção específicas.

### <a name="analyze-affected-assets"></a>Analisar ativos afetados
A seção ativos afetados lista caixas de correio, dispositivos e usuários afetados por esse alerta. Selecionar qualquer um dos cartões de ativos preenche o painel de detalhes com informações, incluindo outros alertas que ocorreram envolvendo os ativos, se for o caso.


### <a name="trace-an-alerts-role-in-the-alert-story"></a>Rastrear a função de um alerta no artigo de alerta
O artigo de alerta exibe todos os ativos ou entidades relacionados ao alerta em uma exibição de árvore de processo. O alerta no título é aquele em foco quando você aterra pela primeira vez na página do alerta selecionado. Os ativos no artigo de alerta são expansíveis e clicáveis. Eles fornecem informações adicionais e aceleram a resposta permitindo que você tome ações imediatamente no contexto da página de alerta. 

> [!NOTE]
> A seção de texto do alerta pode conter mais de um alerta, com alertas adicionais relacionados à mesma árvore de execução que aparece antes ou depois do alerta selecionado.

### <a name="view-more-alert-information-in-the-details-pane"></a>Exibir mais informações de alerta no painel de detalhes

O painel de detalhes mostra os detalhes do alerta selecionado no início, com detalhes e ações relacionadas a ele. Se você selecionar qualquer um dos ativos ou entidades afetados no histórico de alertas, o painel de detalhes muda para fornecer informações contextuais e ações para o objeto selecionado.

Depois de selecionar uma entidade de interesse, o painel de detalhes muda para exibir informações sobre o tipo de entidade selecionado, informações históricas quando ela estiver disponível e opções para tomar medidas nessa entidade diretamente na página de alerta.

### <a name="manage-alerts"></a>Gerenciar alertas

Depois de terminar de investigar os alertas, você pode voltar ao alerta com o que começou, marcar o status do alerta como Resolvido e classificá-lo como um alerta False ou True. Classificar alertas ajuda a ajustar seu produto para fornecer alertas mais verdadeiros e menos alertas falsos.

> [!NOTE]
> Uma maneira de gerenciar o alerta por meio do uso de marcas. O recurso de marcação do Microsoft Defender para Office 365 está sendo lançado incrementalmente e está atualmente em visualização. <br>
> Atualmente, os nomes de marcas modificadas só são aplicados a alertas criados *após* a atualização. Os alertas gerados antes da modificação não refletirão o nome da marca atualizado. 


## <a name="manage-the-unified-alert-queue"></a>Gerenciar a fila de alertas unificada

Selecionar Alertas em Incidentes & alertas no painel de navegação do Centro de Segurança do Microsoft 365 o leva à fila de alertas unificada. Alertas de diferentes soluções de segurança da Microsoft, como o Microsoft Defender para Ponto de Extremidade, o Microsoft Defender para Office 365 e o Microsoft 365 Defender aparecem nesta seção. 

![Imagem da página de alerta de exemplo](../../media/unified-alert-queue.png)

A fila Alertas mostra uma lista de alertas que foram sinalizados em sua rede. Por padrão, a fila exibe alertas vistos nos últimos 30 dias. Os alertas mais recentes são mostrados na parte superior da lista, ajudando você a ver os alertas mais recentes primeiro.

> [!NOTE]
> No momento do início, a fila de alertas unificados terá apenas 7 dias de alertas do Microsoft Defender para Office 365 disponíveis. A fila continuará a ser construída ao longo do tempo. Se você precisar triagem de alertas antes do início da fila de alertas unificados, use a fila de alertas no Centro de Segurança [e Conformidade.](https://protection.office.com/viewalerts)


Na navegação superior, você pode:

- Aplicar filtros
- Personalizar colunas para adicionar ou remover colunas
- Exportar dados

Você também pode filtrar alertas de acordo com diferentes critérios:

- Severity
- Status
- Categoria
- Fonte de detecção
- Política
- Ativos afetados
- Primeira atividade
- Última atividade


Para iniciar uma investigação sobre um incidente, leia [Investigar incidentes no Microsoft 365 Defender](investigate-incidents.md)
## <a name="see-also"></a>Confira também

- [Visão geral dos incidentes](incidents-overview.md)
- [Investigar incidentes](investigate-incidents.md)
- [Gerenciar incidentes](manage-incidents.md)
