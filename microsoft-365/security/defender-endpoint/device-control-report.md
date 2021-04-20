---
title: Proteger dados da sua organização com controle de dispositivo
description: Monitore a segurança de dados da sua organização por meio de relatórios de controle de dispositivo.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.author: dansimp
author: dansimp
ms.reviewer: dansimp
ms.topic: article
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: ee8e7be20076bde41867981008e53a70c134e47e
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893659"
---
# <a name="protect-your-organizations-data-with-device-control"></a>Proteger dados da sua organização com controle de dispositivo

**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2069559)

O controle de dispositivo do Microsoft Defender for Endpoint protege contra perda de dados, monitorando e controlando o uso de mídia por dispositivos em sua organização, como o uso de dispositivos de armazenamento removíveis e unidades USB.

Com o relatório de controle de dispositivo, você pode exibir eventos relacionados ao uso de mídia, como:

- **Eventos de auditoria:** Mostra o número de eventos de auditoria que ocorrem quando a mídia externa está conectada.
- **Eventos de política:** Mostra o número de eventos de política que ocorrem quando uma política de controle de dispositivo é disparada.

> [!NOTE]
> O evento de auditoria para controlar o uso de mídia é habilitado por padrão para dispositivos conectados ao Microsoft Defender para Ponto de Extremidade.

## <a name="understanding-the-audit-events"></a>Noções básicas sobre os eventos de auditoria

Os eventos de auditoria incluem:

- **Montagem e desmontagem da** unidade USB: Eventos de auditoria gerados quando uma unidade USB é montada ou desmontada.
- **PnP:** Os eventos de auditoria Plug and Play são gerados quando o armazenamento removível, uma impressora ou Bluetooth mídia está conectada.

## <a name="monitor-device-control-security"></a>Monitorar a segurança do controle de dispositivo

O controle de dispositivo no Microsoft Defender para Ponto de Extremidade capacita os administradores de segurança com ferramentas que permitem controlar a segurança de controle de dispositivos da organização por meio de relatórios. Você pode encontrar o relatório de controle de dispositivo no centro de segurança do Microsoft 365 indo para **Relatórios > Proteção de dispositivos.**

O cartão de proteção de dispositivo no painel **Relatórios** mostra o número de eventos de auditoria gerados pelo tipo de mídia, nos últimos 180 dias.

> [!div class="mx-imgBorder"]
> ![DeviceControlReportCard](images/devicecontrolcard.png)

O **botão Exibir detalhes** mostra mais dados de uso de mídia na página relatório de controle **do** dispositivo.

A página fornece um painel com o número agregado de eventos por tipo e uma lista de eventos. Os administradores podem filtrar o intervalo de tempo, o nome da classe de mídia e a ID do dispositivo.

> [!div class="mx-imgBorder"]
> ![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)

Quando você seleciona um evento, um flyout é exibido que mostra mais informações:

- **Detalhes gerais:** Data, modo ação e a política deste evento.
- **Informações de mídia:** As informações de mídia incluem nome de mídia, nome da classe, GUID de classe, ID do dispositivo, ID do fornecedor, volume, número de série e tipo de Barramento.
- **Detalhes do local:** Nome do dispositivo e ID do dispositivo MDATP.

> [!div class="mx-imgBorder"]
> ![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)

Para ver a atividade em tempo real para essa mídia em toda a organização, selecione o **botão Abrir Busca Avançada.** Isso inclui uma consulta incorporada e pré-definida.

> [!div class="mx-imgBorder"]
> ![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)

Para ver a segurança do dispositivo, selecione o botão Abrir página **do** dispositivo no sobrevoo. Este botão abre a página entidade do dispositivo.

> [!div class="mx-imgBorder"]
> ![DeviceEntityPage](images/Devicesecuritypage.png)

## <a name="reporting-delays"></a>Atrasos de relatórios

O relatório de controle de dispositivo pode ter um atraso de 12 horas a partir do momento em que uma conexão de mídia ocorre até o momento em que o evento é refletido no cartão ou na lista de domínios.
