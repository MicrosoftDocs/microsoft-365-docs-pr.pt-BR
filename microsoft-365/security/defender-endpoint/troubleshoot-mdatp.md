---
title: Solucionar problemas de serviço do Microsoft Defender para Ponto de Extremidade
description: Encontre soluções e soluções alternativas para problemas conhecidos, como erros de servidor ao tentar acessar o serviço.
keywords: solução de problemas do Microsoft Defender para Ponto de Extremidade, erro de servidor, acesso negado, credenciais inválidas, sem dados, portal de painel, permitir, visualizador de eventos
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 8aaea65c617300a16f99a9a3e3a62d94b7983198
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538346"
---
# <a name="troubleshoot-service-issues"></a>Solucionar problemas de serviço

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


Esta seção aborda problemas que podem surgir à medida que você usa o serviço Microsoft Defender para Ponto de Extremidade.

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a>Erro do servidor - o acesso é negado devido a credenciais inválidas
Se você encontrar um erro de servidor ao tentar acessar o serviço, precisará alterar as configurações de cookie do navegador.
Configure seu navegador para permitir cookies.

## <a name="elements-or-data-missing-on-the-portal"></a>Elementos ou dados ausentes no portal
Se alguns elementos ou dados estão faltando Central de Segurança do Microsoft Defender é possível que as configurações de proxy os bloqueem.

Certifique-se de `*.securitycenter.windows.com` que está incluída a lista de autorizações de proxy.


> [!NOTE]
> Você deve usar o protocolo HTTPS ao adicionar os seguintes pontos de extremidade.

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a>O serviço do Microsoft Defender para Ponto de Extremidade mostra logs de evento ou erro no Visualizador de Eventos

Consulte [Review events and errors using Event Viewer](event-error-codes.md) for a list of event IDs that are reported by the Microsoft Defender for Endpoint service. O artigo também contém etapas de solução de problemas para erros de evento.

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a>O serviço do Microsoft Defender para Ponto de Extremidade falha ao iniciar após uma reinicialização e mostra o erro 577

Se a integração de dispositivos for concluída com êxito, mas o Microsoft Defender for Endpoint não começar após uma reinicialização e mostrar o erro 577, verifique se o Windows Defender não está desabilitado por uma política.

Para obter mais informações, [consulte Ensure that Microsoft Defender Antivírus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).

## <a name="known-issues-with-regional-formats"></a>Problemas conhecidos com formatos regionais

**Formatos de data e hora**<br>
Há alguns problemas conhecidos com os formatos de data e hora. 

Os seguintes formatos de data são suportados:
- MM/dd/yyyy
- dd/MM/yyyy

No momento, não há suporte para os seguintes formatos de data e hora:
- Formato de data yyyy/MM/dd
- Formato de data dd/MM/yy
- Formato de data com yy. Mostrará somente yyyy.
- O formato de hora HH:mm:ss não tem suporte (não há suporte para o formato AM/PM de 12 horas). Há suporte apenas para o formato de 24 horas.

**Uso de vírgulas para indicar mil**<br>
Não há suporte para o uso de vírgulas como separador em números. Regiões onde um número é separado com uma vírgula para indicar mil, só verão o uso de um ponto como separador. Por exemplo, 15,5K é exibido como 15,5K.

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a>O locatário do Microsoft Defender para Ponto de Extremidade foi criado automaticamente na Europa
Quando você usa o Azure Defender para monitorar servidores, um locatário do Microsoft Defender for Endpoint é criado automaticamente. Os dados do Microsoft Defender para Ponto de Extremidade são armazenados na Europa por padrão.





## <a name="related-topics"></a>Tópicos relacionados
- [Solucionar problemas de integração do Microsoft Defender para pontos de extremidade](troubleshoot-onboarding.md)
- [Revisar eventos e erros usando o Visualizador de Eventos](event-error-codes.md)
