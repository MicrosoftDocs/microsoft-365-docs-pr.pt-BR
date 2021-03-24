---
title: Relatório de conformidade e saúde do dispositivo no Microsoft Defender ATP
description: Rastrear detecções de estado de saúde do dispositivo, status do antivírus, plataforma do sistema operacional e versões do Windows 10 usando o relatório de conformidade e saúde do dispositivo
keywords: estado de saúde, antivírus, plataforma do sistema operacional, versão do windows 10, versão, saúde, conformidade, estado
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
ms.openlocfilehash: 9d41071fc5849f3a11061437af2bb88b117ec4a8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053348"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a>Relatório de conformidade e saúde do dispositivo no Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

O relatório de status dos dispositivos fornece informações de alto nível sobre os dispositivos em sua organização. O relatório inclui informações de tendência mostrando o estado de saúde do sensor, o status do antivírus, as plataformas do sistema operacional e as versões do Windows 10.

O painel é estruturado em duas seções: ![ Imagem do relatório do dispositivo](images/device-reports.png)
 
Seção | Descrição
:---|:---
1 | Tendências de dispositivo
2 | Resumo do dispositivo (dia atual)
 
 
## <a name="device-trends"></a>Tendências de dispositivo 
Por padrão, as tendências do dispositivo exibem informações do dispositivo do período de 30 dias que terminam no último dia completo. Para obter uma perspectiva melhor sobre as tendências que ocorrem em sua organização, você pode ajustar o período de relatório ajustando o período de tempo mostrado. Para ajustar o período de tempo, selecione um intervalo de tempo nas opções listadas:
 
- 30 dias
- 3 meses
- 6 meses
- Personalizado

>[!NOTE]
>Esses filtros só são aplicados na seção tendências do dispositivo. Ele não afeta a seção resumo do dispositivo.

## <a name="device-summary"></a>Resumo do dispositivo 
Embora as tendências de dispositivos mostrem informações de dispositivos tendências, o resumo do dispositivo mostra as informações do dispositivo com escopo até o dia atual. 

>[!NOTE]
>Os dados refletidos na seção resumo são escopos para 180 dias antes da data atual. Por exemplo, se a data de hoje for 27 de março de 2019, os dados da seção de resumo refletirão números a partir de 28 de setembro de 2018 a 27 de março de 2019.<br>
> O filtro aplicado na seção tendências não é aplicado na seção resumo. 
 
A seção tendências do dispositivo permite detalhar a lista de dispositivos com o filtro correspondente aplicado a ela. Por exemplo, clicar na barra Inativa no cartão de estado de estado do sensor levará a lista de dispositivos com resultados mostrando apenas dispositivos cujo status do sensor está inativo. 
 
 
 
## <a name="device-attributes"></a>Atributos do dispositivo
O relatório é feito de cartões que exibem os seguintes atributos de dispositivo:
 
- **Estado de** saúde : mostra informações sobre o estado do sensor em dispositivos, fornecendo uma exibição agregada de dispositivos que estão ativos, com comunicações prejudicadas, inativas ou onde nenhum dado do sensor é visto.
  
- **Status do antivírus para dispositivos Windows 10** ativos : mostra o número de dispositivos e o status do Microsoft Defender Antivírus.
    
- **Plataformas do sistema operacional**: mostra a distribuição de plataformas do sistema operacional existentes em sua organização. 
 
- **Versões do Windows 10**: mostra a distribuição de dispositivos Windows 10 e suas versões em sua organização.
 
 
 
## <a name="filter-data"></a>Filtrar dados
 
Use os filtros fornecidos para incluir ou excluir dispositivos com determinados atributos.

Você pode selecionar vários filtros para aplicar a partir dos atributos do dispositivo. 
 
>[!NOTE]
>Esses filtros se aplicam **a** todos os cartões do relatório.
 
Por exemplo, para mostrar dados sobre dispositivos Windows 10 com estado de saúde do sensor ativo:
 
1. Em **Filtros > estado de saúde do sensor > Ativo**.
2. Em seguida, **selecione plataformas do sistema operacional > Windows 10**.
3. Selecione **Aplicar**.


## <a name="related-topic"></a>Tópicos relacionados
- [Relatório de proteção contra ameaças](threat-protection-reports.md)
