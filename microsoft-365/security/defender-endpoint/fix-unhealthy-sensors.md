---
title: Corrigir sensores não salubres no Microsoft Defender para Ponto de Extremidade
description: Correção de sensores de dispositivo que estão relatando como mal configurados ou inativos para que o serviço receba dados do dispositivo.
keywords: misconfigured, inactive, fix sensor, sensor health, no sensor data, sensor data, sensor data, comunicações prejudicadas, comunicação
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
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: 3a26951a796d72237f992e520e1b793654e467e3
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893396"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a>Corrigir sensores não salubres no Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-fixsensor-abovefoldlink)

Dispositivos categorizados como mal configurados ou inativos podem ser sinalizados devido a causas variáveis. Esta seção fornece algumas explicações sobre o que pode ter causado a categorização de um dispositivo como inativo ou mal configurado.

## <a name="inactive-devices"></a>Dispositivos inativos

Um dispositivo inativo não é necessariamente sinalizado devido a um problema. As seguintes ações tomadas em um dispositivo podem fazer com que um dispositivo seja categorizado como inativo:

### <a name="device-is-not-in-use"></a>O dispositivo não está em uso

Se o dispositivo não estiver em uso por mais de sete dias por qualquer motivo, ele permanecerá em um status 'Inativo' no portal.

### <a name="device-was-reinstalled-or-renamed"></a>O dispositivo foi reinstalado ou renomeado
Um dispositivo reinstalado ou renomeado gerará uma nova entidade de dispositivo no Centro de Segurança do Microsoft Defender. A entidade de dispositivo anterior permanecerá com um status 'Inativo' no portal. Se você reinstalou um dispositivo e implantou o pacote do Defender for Endpoint, procure o novo nome do dispositivo para verificar se o dispositivo está relatando normalmente.

### <a name="device-was-offboarded"></a>O dispositivo foi desligado
Se o dispositivo foi desligado, ele ainda aparecerá na lista de dispositivos. Após sete dias, o estado de saúde do dispositivo deve mudar para inativo.

### <a name="device-is-not-sending-signals"></a>O dispositivo não está enviando sinais
Se o dispositivo não estiver enviando sinais por mais de sete dias para qualquer um dos canais do Microsoft Defender para Ponto de Extremidade por qualquer motivo, incluindo condições que se enquadram na classificação de dispositivos mal configurados, um dispositivo pode ser considerado inativo. 

Você espera que um dispositivo está no status 'Ativo'? [Abra um tíquete de suporte](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).

## <a name="misconfigured-devices"></a>Dispositivos mal configurados
Dispositivos mal configurados ainda podem ser classificados para:
- Comunicações prejudicadas
- Sem dados do sensor

### <a name="impaired-communications"></a>Comunicações prejudicadas
Esse status indica que há comunicação limitada entre o dispositivo e o serviço.

As seguintes ações sugeridas podem ajudar a corrigir problemas relacionados a um dispositivo mal configurado com comunicações prejudicadas:

- [Verifique se o dispositivo tem conexão com a Internet](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  O sensor Windows Defender ATP exige que o Microsoft Windows HTTP (WinHTTP) reporte dados do sensor e se comunique com o serviço Microsoft Defender para Ponto de Extremidade.

- [Verificar a conectividade do cliente com o Microsoft Defender para URLs de serviço de ponto de extremidade](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  Verifique se a configuração de proxy foi concluída com êxito, se o WinHTTP pode descobrir e se comunicar por meio do servidor proxy em seu ambiente e se o servidor proxy permite o tráfego para as URLs de serviço do Microsoft Defender para Ponto de Extremidade.

Se você tiver ações corretivas e o status do dispositivo ainda estiver configurado incorretamente, [abra um tíquete de suporte](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).

### <a name="no-sensor-data"></a>Sem dados do sensor
Um dispositivo mal configurado com o status 'Sem dados do sensor' tem comunicação com o serviço, mas só pode relatar dados parciais do sensor.
Siga estas ações para corrigir problemas conhecidos relacionados a um dispositivo mal configurado com o status 'Sem dados do sensor':

- [Verifique se o dispositivo tem conexão com a Internet](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  O sensor Windows Defender ATP exige que o Microsoft Windows HTTP (WinHTTP) reporte dados do sensor e se comunique com o serviço Microsoft Defender para Ponto de Extremidade.

- [Verificar a conectividade do cliente com o Microsoft Defender para URLs de serviço de ponto de extremidade](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  Verifique se a configuração de proxy foi concluída com êxito, se o WinHTTP pode descobrir e se comunicar por meio do servidor proxy em seu ambiente e se o servidor proxy permite o tráfego para as URLs de serviço do Microsoft Defender para Ponto de Extremidade.

- [Verifique se o serviço de dados de diagnóstico está habilitado](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
Se os dispositivos não estão relatando corretamente, talvez seja necessário verificar se o serviço de dados de diagnóstico do Windows 10 está definido para iniciar automaticamente e está sendo executado no ponto de extremidade.

- [Verifique se o Microsoft Defender Antivírus não está desabilitado por política](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
Se seus dispositivos estão executando um cliente antimalware de terceiros, o agente defender para ponto de extremidade precisa do driver antimalware de início antecipado do Microsoft Defender Antivírus (ELAM) para ser habilitado.

Se você tiver ações corretivas e o status do dispositivo ainda estiver configurado incorretamente, [abra um tíquete de suporte](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).

## <a name="see-also"></a>Confira também
- [Verificar o estado de saúde do sensor no Microsoft Defender para Ponto de Extremidade](check-sensor-status.md)
