---
title: Percepções de atualização da segurança do Windows
description: ''
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 772d1d52e977a067ff9bc3517de9cb2ae6c8c9a3
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950362"
---
# <a name="windows-security-update-insights"></a>Percepções de atualização da segurança do Windows
Este modo de exibição fornece uma visão geral do status das atualizações de segurança para seus dispositivos de área de trabalho gerenciada da Microsoft. 

Para exibir os dados de uso, selecione a guia <strong>atualizações de segurança do Windows</strong> .

![Painel de atualizações de segurança do Windows: barras de gráfico de status do dispositivo e versão de atualização na coluna à esquerda, atualize o progresso da implantação ao longo do tempo na coluna central e a porcentagem de dispositivos ativos por grupo de implantação, bem como o número de dias obtidos para chegar à coluna direito de destino de implantação de 95%.](../../media/update-insights.jpg)

## <a name="device-status"></a>Status do dispositivo

Para que os dispositivos sejam atualizados pelo Windows Update, eles devem estar conectados à Internet e não em hibernação por um mínimo de seis horas, dois dos quais devem ser contínuos. Contanto que um dispositivo esteja conectado e não em hibernação, ele será considerado como "em uso". Embora seja possível que um dispositivo que não atenda a esses requisitos seja atualizado, os dispositivos que atendem a eles têm a maior possibilidade de ser atualizado. 

Categorizamos a atividade do dispositivo no contexto do Windows Update com estes termos:

- <strong>Ativo:</strong> Dispositivos que atenderam aos critérios de uso mínimo (seis horas, dois contínuos) para a versão mais recente da atualização de segurança e fizeram check-in com o Microsoft Intune pelo menos a cada cinco dias
- <strong>Sincronizado:</strong> Dispositivos com check-in no Intune nos últimos 28 dias
- <strong>Fora de sincronização:</strong> Dispositivos que <i>não</i> fizeram check-in com o Intune nos últimos 28 dias




## <a name="update-version-status"></a>Atualizar status da versão

A Microsoft lança atualizações de segurança a cada segunda terça-feira do mês. Cada versão adiciona atualizações importantes para vulnerabilidades de segurança conhecidas. A área de trabalho gerenciada da Microsoft garante que 95% dos seus dispositivos gerenciados sejam atualizados com a atualização de segurança mais recente disponível a cada mês. As atualizações de segurança às vezes são lançadas em outros horários para lidar com urgência novas ameaças. O Microsoft Managed desktop implanta essas atualizações de maneira semelhante.

Categorizamos o status das versões de atualização de segurança com estes termos:

- <strong>Atual:</strong> Dispositivos que estão executando a atualização liberada no mês atual
- <strong>Anterior:</strong> Dispositivos executando a atualização lançada no mês anterior
- <strong>Mais antigo:</strong> Dispositivos executando qualquer atualização de segurança lançada antes do mês anterior

Você deve ver alguns dispositivos na categoria <strong>antigo</strong> – uma população grande ou crescente provavelmente indica um problema do sistema que você deve relatar à área de trabalho gerenciada da Microsoft para que possamos investigar.


## <a name="deployment-progress"></a>Progresso da implantação

No início de cada ciclo de lançamento de atualização de segurança, a área de trabalho gerenciada da Microsoft faz um instantâneo da população de dispositivos e define seu destino de implantação em 95% dessa população. A área de <strong>progresso da implantação</strong> mostra uma tendência histórica, atualizada diariamente, controlando o quanto a implantação da atualização atende a esse destino para cada versão. Este gráfico mostra apenas dispositivos com status ativo.

Você pode exibir esses dados para ciclos de atualização anteriores usando o menu suspenso no canto superior direito. O período selecionado neste menu aplica-se a todas as informações na página inteira.

A área atualização de <strong>dispositivos ativos por grupo de implantação</strong> oferece um modo de exibição diferente mostrando o progresso da instalação da atualização para cada um dos grupos de implantação de área de trabalho gerenciada da Microsoft.

Os <strong>dias para atingir a área de destino</strong> exibe quanto tempo levou para 95% do número total de dispositivos a serem atualizados com a atualização de segurança atual. Enquanto a implantação estiver em andamento, esta área exibirá a <strong>atualização ainda</strong> até que o destino de 95% seja alcançado para a atualização selecionada.

## <a name="device-details-area"></a>Área de detalhes do dispositivo

A parte inferior do painel é uma tabela que mostra informações detalhadas para seus dispositivos, incluindo o [status do dispositivo](#device-status) e o status da versão da [atualização](#update-version-status). Você pode pesquisar esta lista ou filtrá-la por qualquer valor listado.


![Tabela de detalhes do dispositivo mostrando colunas para nome do dispositivo, usuário atribuído, status do dispositivo, versão da atualização, versão do sistema operacional e a data em que o dispositivo foi sincronizado pela última vez.](../../media/security-update-insights-device-table-sterile.png)
