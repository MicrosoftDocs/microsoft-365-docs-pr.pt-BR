---
title: Técnicas na linha do tempo do dispositivo
description: Noções básicas sobre a linha do tempo do dispositivo no Microsoft Defender para Ponto de Extremidade
keywords: linha do tempo do dispositivo, ponto de extremidade, MITRE, MITRE ATT&CK, técnicas, táticas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d6e2c18bd3710e659b5f9887844bc92528da4607
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052859"
---
# <a name="techniques-in-the-device-timeline"></a>Técnicas na linha do tempo do dispositivo


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)


Você pode obter mais informações em uma investigação analisando os eventos que aconteceram em um dispositivo específico. Primeiro, selecione o dispositivo de interesse na lista [Dispositivos](machines-view-overview.md). Na página do dispositivo, você pode selecionar a guia **Linha** do Tempo para exibir todos os eventos que ocorreram no dispositivo.

## <a name="understand-techniques-in-the-timeline"></a>Compreender técnicas na linha do tempo

>[!IMPORTANT]
>Algumas informações se relacionam a um recurso de produto pré-lançado na visualização pública que pode ser substancialmente modificado antes de ser lançado comercialmente. A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.

No Microsoft Defender para Ponto de Extremidade, **as** técnicas são um tipo de dados adicional na linha do tempo do evento. As técnicas fornecem mais informações sobre as atividades associadas ao [MITRE ATT&](https://attack.mitre.org/) técnicas de CK ou sub-técnicas. 

Esse recurso simplifica a experiência de investigação ajudando os analistas a entender as atividades observadas em um dispositivo. Os analistas podem, então, decidir investigar mais.

Para visualização pública, as técnicas estão disponíveis por padrão e mostradas em conjunto com eventos quando a linha do tempo de um dispositivo é exibida. 

![Técnicas na captura de tela da linha do tempo do dispositivo](images/device-timeline-2.png)

As técnicas são realçadas em negrito e aparecem com um ícone azul à esquerda. O nome e a técnica correspondentes do MITRE ATT&ID de CK também aparecem como marcas em Informações adicionais. 

Opções de pesquisa e exportação também estão disponíveis para Técnicas.

## <a name="investigate-using-the-side-pane"></a>Investigar usando o painel lateral

Selecione uma Técnica para abrir seu painel lateral correspondente. Aqui você pode ver informações adicionais e insights como att&técnicas de CK relacionadas, táticas e descrições. 

Selecione a técnica *de Ataque específica* para abrir a página de técnica de CK&ATT relacionada, onde você pode encontrar mais informações sobre ele.

Você pode copiar os detalhes de uma entidade quando vir um ícone azul à direita. Por exemplo, para copiar SHA1 de um arquivo relacionado, selecione o ícone de página azul.

![Copiar detalhes da entidade](images/techniques-side-pane-clickable.png)

Você pode fazer o mesmo para linhas de comando.

![Copiar linha de comando](images/techniques-side-pane-command.png)


## <a name="investigate-related-events"></a>Investigar eventos relacionados

Para usar [a busca avançada](advanced-hunting-overview.md) para encontrar eventos relacionados à Técnica selecionada, selecione Procurar eventos **relacionados.** Isso leva à página de busca avançada com uma consulta para encontrar eventos relacionados à Técnica.

![Busca por eventos relacionados](images/techniques-hunt-for-related-events.png)

>[!NOTE]
>A consulta usando o botão **Procurar** eventos relacionados a partir de um painel lateral de Técnica exibe todos os eventos relacionados à técnica identificada, mas não inclui a técnica em si nos resultados da consulta.


## <a name="customize-your-device-timeline"></a>Personalizar a linha do tempo do dispositivo

No lado superior direito da linha do tempo do dispositivo, você pode escolher um intervalo de datas para limitar o número de eventos e técnicas na linha do tempo. 

Você pode personalizar quais colunas expor. Você também pode filtrar eventos sinalizados por tipo de dados ou por grupo de eventos.

### <a name="choose-columns-to-expose"></a>Escolher colunas para expor
Você pode escolher quais colunas expor na linha do tempo selecionando o **botão Escolher colunas.**

![Personalizar colunas](images/filter-customize-columns.png)

A partir daí, você pode selecionar quais informações serão definidas para incluir.

### <a name="filter-to-view-techniques-or-events-only"></a>Filtrar para exibir apenas técnicas ou eventos

Para exibir apenas eventos ou técnicas, selecione **Filtros** na linha do tempo do dispositivo e escolha seu tipo de dados preferencial para exibir.

![Filtra captura de tela](images/device-timeline-filters.png)



## <a name="see-also"></a>Confira também
- [Exibir e organizar a lista Dispositivos](machines-view-overview.md)
- [Sinalizadores de eventos de linha do tempo do dispositivo do Microsoft Defender for Endpoint](device-timeline-event-flag.md) 


 
