---
title: Dispositivos de integração sem acesso à Internet ao Microsoft Defender para Ponto de Extremidade
ms.reviewer: ''
description: Dispositivos integrados sem acesso à Internet para que eles possam enviar dados do sensor para o sensor do Microsoft Defender para Ponto de Extremidade
keywords: onboard, servers, vm, on-premise, oms gateway, log analytics, azure log analytics, mma
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
ms.openlocfilehash: fb5a9a4d35af2d400cdff1e417727e662738514e
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861342"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>Dispositivos de integração sem acesso à Internet ao Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Para os dispositivos de integração sem acesso à Internet, você precisará seguir as seguintes etapas gerais:

> [!IMPORTANT] 
> As etapas a seguir são aplicáveis apenas a dispositivos que executam versões anteriores do Windows, como: Windows Server 2016 e anterior ou Windows 8.1 e anteriores.

> [!NOTE]
> - Um servidor de gateway OMS não pode ser usado como proxy para dispositivos Windows 10 ou Windows Server 2019 desconectados quando configurado por meio do Registro ou GPO "TelemetryProxyServer".
> - Para Windows 10 ou Windows Server 2019 - embora você possa usar TelemetryProxyServer, ele deve apontar para um dispositivo ou dispositivo proxy padrão.
> - Além disso, o Windows 10 ou o Windows Server 2019 em ambientes desconectados devem ser capazes de atualizar listas de confiança de certificado offline por meio de um arquivo interno ou servidor Web.
> - Para obter mais informações sobre como atualizar CTLs offline, consulte [Configure a file or web server to download the CTL files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).

Para obter mais informações sobre métodos de integração, consulte os seguintes artigos:
- [Versões anteriores integradas do Windows](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [Servidores de integração para o serviço do Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [Configurar configurações de proxy de dispositivo e conectividade com a Internet](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premise-devices"></a>Dispositivos locais

- Configurar o Azure Log Analytics (anteriormente conhecido como Gateway OMS) para atuar como proxy ou hub:
  - [Agente de Análise de Log do Azure](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - [Instalar e configurar o Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) aponte para o Defender for Endpoint Workspace key & ID

- Dispositivos offline na mesma rede do Azure Log Analytics
  -  Configurar o MMA para apontar para:
     - IP do Azure Log Analytics como proxy
     - Chave de espaço de trabalho do Defender para Ponto de Extremidade & ID

## <a name="azure-virtual-machines"></a>Máquinas virtuais do Azure
- Configurar e habilitar o espaço de trabalho [do Azure Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)

    - Configurar o Gateway de Análise de Log do Azure (anteriormente conhecido como Gateway OMS) para atuar como proxy ou hub:
      - [Gateway de Análise de Log do Azure](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - [Instalar e configurar o Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) aponte para o Defender for Endpoint Workspace key & ID
    - VMs offline do Azure na mesma rede do Gateway OMS
      - Configurar o IP do Azure Log Analytics como proxy
      - Chave de Espaço de Trabalho do Azure Log Analytics & ID

    - Centro de Segurança do Azure (ASC)
      - [Espaço de Trabalho \> de Análise de Log de Política de Segurança](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [Detecção de \> ameaças Permitir que o Defender para o Ponto de Extremidade acesse meus dados](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        Para obter mais informações, consulte [Trabalhando com políticas de segurança](https://docs.microsoft.com/azure/security-center/tutorial-security-policy).
