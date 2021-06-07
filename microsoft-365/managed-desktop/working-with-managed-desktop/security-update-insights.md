---
title: Percepções de atualização da segurança do Windows
description: ''
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3b1f43217b3be285f20925065bf9710a38f9606
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739755"
---
# <a name="windows-security-update-insights"></a>Percepções de atualização da segurança do Windows
Esta exibição fornece uma visão geral do status das atualizações de segurança para seus Área de Trabalho Gerenciada da Microsoft dispositivos. 

Para exibir dados de uso, selecione a <strong>guia Windows atualizações de segurança.</strong>

![Windows painel de atualizações de segurança: gráficos de barras do status do dispositivo e a versão de atualização na coluna esquerda, atualizar o progresso da implantação ao longo do tempo na coluna central e a porcentagem de dispositivos ativos por grupo de implantação, bem como o número de dias que levar para alcançar o destino de implantação de 95% na coluna direita.](../../media/update-insights.jpg)

## <a name="device-status"></a>Status do dispositivo

Para que os dispositivos sejam atualizados pelo Windows Update, eles devem estar conectados à Internet e não hibernando por pelo menos seis horas, dois dos quais devem ser contínuos. Embora seja possível que um dispositivo que não atender a esses requisitos seja atualizado, os dispositivos que os atendem têm a maior probabilidade de serem atualizados. 

Categorizamos a atividade do dispositivo no contexto do Windows Update com estes termos:

- <strong>Ativo:</strong> Dispositivos que tenham atendido aos critérios mínimos de atividade (seis horas, duas contínuas) para a versão de atualização de segurança mais recente e que tenham feito check-in com Microsoft Intune pelo menos a cada cinco dias
- <strong>Sincronizado:</strong> Dispositivos que efetuaram check-in com o Intune nos últimos 28 dias
- <strong>Fora de sincronização:</strong> Dispositivos que <i>não</i> efetuaram check-in com o Intune nos últimos 28 dias




## <a name="update-version-status"></a>Atualizar status da versão

A Microsoft lança atualizações de segurança a cada segunda terça-feira do mês. Cada versão adiciona atualizações importantes para vulnerabilidades de segurança conhecidas. Área de Trabalho Gerenciada da Microsoft garante que 95% de seus dispositivos gerenciados sejam atualizados com a atualização de segurança disponível mais recente todos os meses. Às vezes, as atualizações de segurança são lançadas em outras ocasiões para resolver com urgência novas ameaças. Área de Trabalho Gerenciada da Microsoft implanta essas atualizações de maneira semelhante.

Categorizamos o status das versões de atualização de segurança com estes termos:

- <strong>Atual:</strong> Dispositivos que estão executando a atualização lançada no mês atual
- <strong>Anterior:</strong> Dispositivos que executam a atualização lançada no mês anterior
- <strong>Mais antigo:</strong> Dispositivos que executam qualquer atualização de segurança lançada antes do mês anterior

Você deve ver poucos dispositivos na categoria <strong>Mais</strong> Antiga, uma população grande ou crescente provavelmente indica um problema sistêmico que você deve relatar Área de Trabalho Gerenciada da Microsoft para que possamos investigar.


## <a name="deployment-progress"></a>Progresso da implantação

No início de cada ciclo de lançamento de atualização de segurança, Área de Trabalho Gerenciada da Microsoft tira um instantâneo da população de dispositivos e define sua meta de implantação em 95% dessa população. A <strong>área de progresso</strong> de implantação mostra uma tendência histórica, atualizada diariamente, acompanhando a proximidade com que a implantação de atualização atende a essa meta para cada versão. Este gráfico mostra apenas dispositivos com status Ativo.

Você pode exibir esses dados para ciclos de atualização anteriores usando o menu suspenso no canto superior direito. O período selecionado neste menu se aplica a todas as informações na página inteira.

A <strong>área De dispositivos ativos atualizados por</strong> grupo de implantação oferece uma exibição diferente mostrando o progresso da instalação da atualização para cada um dos grupos de Área de Trabalho Gerenciada da Microsoft de implantação.

A <strong>área de destino</strong> Days to reach exibe quanto tempo levou para 95% do número total de dispositivos a serem atualizados com a atualização de segurança atual. Enquanto a implantação está em andamento, essa área exibe <strong>Ainda atualizando</strong> até que o destino 95% seja atingido para a atualização selecionada.

## <a name="device-details-area"></a>Área de detalhes do dispositivo

A parte inferior do painel é uma tabela mostrando informações detalhadas para seus dispositivos, incluindo o [status](#device-status) do dispositivo e o [status da versão update.](#update-version-status) Você pode pesquisar essa lista ou filtre-a por qualquer valor listado.


![Tabela de detalhes do dispositivo mostrando colunas para nome do dispositivo, usuário atribuído, status do dispositivo, versão de atualização, versão do sistema operacional e a data em que o dispositivo foi sincronizado pela última vez.](../../media/security-update-insights-device-table-sterile.png)
