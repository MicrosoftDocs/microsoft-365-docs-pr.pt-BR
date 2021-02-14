---
title: Percepções da bateria
description: ''
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f339fc98ea94c291c533045e9906f626f4b74e2a
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529834"
---
# <a name="battery-insights"></a>Percepções da bateria
Essa exibição fornece métricas de uso de energia, bateria e aplicativos para seus dispositivos da Área de Trabalho Gerenciada da Microsoft. Para essas finalidades, um aplicativo é considerado "em uso" se estiver em execução e em foco.

Para exibir dados de uso, selecione a **guia** Bateria.

![Painel de bateria: duração prevista da bateria por modelo de dispositivo no canto superior esquerdo, principais consumidores de energia (por aplicativo) no canto superior direito, tabela insights na parte inferior. Link da documentação no canto superior direito.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>Duração prevista da bateria

Na área **de duração prevista da bateria,** fornecemos previsões para a duração esperada da bateria para seus dispositivos, organizadas por modelo de dispositivo.

> [!NOTE]
> Esses dados são derivados do uso de energia de <em></em> amostragem, do tempo de uso e da capacidade da bateria de uma seleção aleatória dos dispositivos em sua implantação da Área de Trabalho Gerenciada da Microsoft que também estão relatando dados.

A tabela fornece a duração prevista da bateria (em horas), a duração média da bateria para os mesmos modelos em outras implantações da Área de Trabalho Gerenciada da Microsoft e o número de dispositivos que relatam esses dados em seu ambiente. Classificar os dados selecionando os títulos de coluna.



## <a name="top-energy-consumers"></a>Principais consumidores de energia

Na área **Principais consumidores de** energia, você encontrará os aplicativos em seu ambiente que consomem mais energia em miliKw-hours (mWh). Os aplicativos mostrados são por dispositivo específico, que você seleciona na seção **Duração** prevista da bateria à esquerda. Por exemplo, para ver o consumo por aplicativo para seus dispositivos Microsoft Surface Book 2, selecione essa linha na área de duração da bateria. Se você não selecionar qualquer modelo, os dados de consumo de aplicativo mostrados são para todos os aplicativos para os quais temos dados coletivamente.

 Para cada aplicativo, os segmentos coloridos mostram a distribuição do uso de energia do aplicativo entre essas categorias:

- CPU
- Display
- Rede
- Outros

"Outros" podem incluir o consumo de energia por várias fontes, como atividade de disco, uso de banda larga móvel e energia perdida para resistência interna. 

Você pode filtrar essa exibição para mostrar somente aplicativos em primeiro plano, aplicativos em segundo plano ou ambos usando o menu no canto superior direito. Os aplicativos em primeiro plano são aqueles que tiveram interação do usuário nos últimos 28 dias, como selecionar algo com um mouse.

## <a name="insights"></a>Insights

A **área Insights** mostra os três principais consumidores de energia nas categorias de CPU e rede. Esses itens estão consumindo energia superior à média em comparação com todas as implantações da Área de Trabalho Gerenciada da Microsoft. Não mostramos o recurso de exibição porque ele depende muito do tempo de uso do dispositivo e das configurações de brilho da tela. 

Selecione as listagem na coluna **Detalhes** para obter mais informações.

## <a name="battery-optimization"></a>Otimização de bateria

O Windows 10 oferece várias configurações de dispositivo para melhorar o uso de energia e aumentar a duração da bateria dos [dispositivos](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) da Área de Trabalho Gerenciada da Microsoft. Algumas dessas configurações podem diminuir outras funcionalidades do Windows, portanto, você também terá que considerar outros fatores, como a função do dispositivo em sua organização. O suporte do Windows mantém uma lista dessas dicas [de economia de bateria.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)

Os usuários podem ajustar algumas configurações por conta própria sem a necessidade de elevação ou suporte do administrador. Outras configurações exigem suporte do administrador de IT da sua organização.
