---
title: Relatório de proteção contra ameaças no Microsoft Defender para Ponto de Extremidade
description: Rastrear detecções, categorias e gravidade de alerta usando o relatório de proteção contra ameaças
keywords: detecção de alerta, origem, alerta por categoria, gravidade do alerta, classificação de alerta, determinação
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d32ab04f4acda60f65316719a4607c6c9bbd6447
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688976"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a>Relatório de proteção contra ameaças no Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

O relatório de proteção contra ameaças fornece informações de alto nível sobre alertas gerados em sua organização. O relatório inclui informações de tendência que mostram as fontes de detecção, categorias, gravidades, status, classificações e determinações de alertas ao longo do tempo.

O painel é estruturado em duas seções:

![Imagem do relatório de proteção contra ameaças](images/threat-protection-reports.png)

Section | Descrição 
:---|:---
1 | Tendências de alertas
2 | Resumo do alerta

## <a name="alert-trends"></a>Tendências de alerta
Por padrão, as tendências de alerta exibem informações de alerta do período de 30 dias que termina no último dia completo. Para obter uma perspectiva melhor sobre as tendências que ocorrem em sua organização, você pode ajustar o período de relatório ajustando o período de tempo mostrado. Para ajustar o período de tempo, selecione um intervalo de tempo nas opções listadas:

- 30 dias
- 3 meses
- 6 meses
- Personalizado

>[!NOTE]
>Esses filtros só são aplicados na seção tendências de alerta. Ele não afeta a seção resumo do alerta.


## <a name="alert-summary"></a>Resumo do alerta
Embora as tendências de alerta mostrem informações de alerta tendência, o resumo de alerta mostra informações de alerta com escopo para o dia atual.

 O resumo do alerta permite que você faça uma pesquisa em uma fila de alertas específica com o filtro correspondente aplicado a ela. Por exemplo, clicar na barra EDR no cartão Detecção de fontes trará a fila de alertas com resultados mostrando apenas alertas gerados EDR detecções. 

>[!NOTE]
>Os dados refletidos na seção resumo são escopos para 180 dias antes da data atual. Por exemplo, se a data de hoje for 5 de novembro de 2019, os dados da seção de resumo refletirão números que começam de 5 de maio de 2019 a 5 de novembro de 2019.<br>
> O filtro aplicado na seção tendências não é aplicado na seção resumo. 

## <a name="alert-attributes"></a>Atributos de alerta
O relatório é feito de cartões que exibem os seguintes atributos de alerta:

- **Fontes de detecção**: mostra informações sobre os sensores e tecnologias de detecção que fornecem os dados usados pelo Microsoft Defender para Endpoint para disparar alertas.

- **Categorias de** ameaça : mostra os tipos de atividade de ameaça ou ataque que dispararam alertas, indicando possíveis áreas de foco para suas operações de segurança.

- **Severidade**: mostra o nível de gravidade dos alertas, indicando o impacto potencial coletivo das ameaças à sua organização e o nível de resposta necessário para lidar com eles.

- **Status**: mostra o status de resolução dos alertas, indicando a eficiência de suas respostas de alerta manual e de correção automatizada (se habilitada). 

- **Classificação &** determinação : mostra como você classificou alertas após a resolução, se você os classificou como ameaças reais (alertas verdadeiros) ou como detecções incorretas (alertas falsos). Esses cartões também mostram a determinação de alertas resolvidos, fornecendo informações adicionais, como os tipos de ameaças reais encontradas ou as atividades legítimas detectadas incorretamente.


 

## <a name="filter-data"></a>Filtrar dados

Use os filtros fornecidos para incluir ou excluir alertas com determinados atributos.

>[!NOTE]
>Esses filtros se aplicam **a** todos os cartões do relatório.

Por exemplo, para mostrar dados somente sobre alertas de alta gravidade:

1. Em **Filtros > Severidade,** selecione **Alta**
2. Certifique-se de que todas as outras opções **em Gravidade** sejam deselegidas.
3. Selecione **Aplicar**. 

## <a name="related-topic"></a>Tópicos relacionados
- [Relatório de conformidade e saúde do dispositivo](machine-reports.md)
