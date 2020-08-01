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
Este modo de exibição fornece métricas de energia, bateria e uso do aplicativo para seus dispositivos de área de trabalho gerenciada da Microsoft. Para esses fins, um aplicativo é considerado "em uso" se estiver em execução e em foco.

Para exibir os dados de uso, selecione a guia **bateria** .

![Painel da bateria: vida prevista da bateria por modelo de dispositivo no canto superior esquerdo, os principais consumidores de energia (por aplicativo) na parte superior direita, a tabela insights na parte inferior. Link de documentação no canto superior direito.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>Vida prevista da bateria

Na área de **vida prevista da bateria** , fornecemos previsões para a vida útil esperada da bateria para seus dispositivos, organizadas por um modelo de dispositivo.

> [!NOTE]
> Esses dados são derivados de amostragem de uso de energia, tempo de uso e capacidade da bateria de uma <em>seleção</em> aleatória de dispositivos em sua implantação de área de trabalho gerenciada da Microsoft que também estão relatando dados.

A tabela fornece a duração prevista da bateria (em horas), a duração média da bateria para os mesmos modelos em outras implantações de área de trabalho gerenciada pela Microsoft e o número de dispositivos que relatam esses dados em seu ambiente. Classifique os dados selecionando os títulos de coluna.



## <a name="top-energy-consumers"></a>Principais consumidores de energia

Na área de **consumidores de energia superior** , você encontrará os aplicativos em seu ambiente que consomem mais energia em milliWatt-hours (MWh). Os aplicativos mostrados são por dispositivo específico, que você seleciona na seção **vida útil da bateria prevista** para a esquerda. Por exemplo, para ver o consumo por aplicativo para seus dispositivos do catálogo de superfície 2 da Microsoft, selecione essa linha na área de vida da bateria. Se você não selecionar nenhum modelo, os dados de consumo do aplicativo mostrados serão para todos os aplicativos que têm dados para o coletivamente.

 Para cada aplicativo, os segmentos coloridos mostram a distribuição do uso de energia do aplicativo entre estas categorias:

- CPU
- Display
- Rede
- Outros

"Outros" podem incluir consumo de energia por uma variedade de fontes, como atividade de disco, uso de banda larga móvel e energia perdida para resistência interna. 

Você pode filtrar esse modo de exibição para mostrar apenas aplicativos de primeiro plano, aplicativos de segundo plano ou ambos, usando o menu no canto superior direito. Os aplicativos de primeiro plano são aqueles que tiveram a interação do usuário nos últimos 28 dias, como selecionar algo com um mouse.

## <a name="insights"></a>Informações

A área do **insights** mostra os três principais consumidores de energia nas categorias CPU e rede. Esses itens estão consumindo mais do que a média de energia em comparação com todas as implantações do Microsoft Managed desktop. Não mostramos o recurso de exibição porque depende muito do tempo de uso do dispositivo e das configurações de brilho da tela. 

Selecione as listagens na coluna **detalhes** para obter mais informações.

## <a name="battery-optimization"></a>Otimização da bateria

O Windows 10 oferece numerosas [configurações de dispositivo](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) para melhorar o uso de energia e aumentar a duração da bateria de seus dispositivos de área de trabalho gerenciados da Microsoft. Algumas dessas configurações podem reduzir outras funcionalidades do Windows, portanto, você também precisará considerar outros fatores como a função do dispositivo em sua organização. O suporte do Windows mantém uma lista dessas [dicas de economia de bateria](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).

Os usuários podem ajustar algumas configurações por conta própria, sem a necessidade de elevação ou suporte de administrador. Outras configurações exigem suporte do administrador de ti da sua organização.
