---
title: Integração de versões anteriores do Windows no Microsoft Defender ATP
description: Integração com versões anteriores de dispositivos Windows para que eles possam enviar dados do sensor para o sensor do Microsoft Defender ATP
keywords: onboard, windows, 7, 81, oms, sp1, enterprise, pro, down level
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
ms.openlocfilehash: b180e7555bb3339324d3b99956d8f8ad73dc13c3
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186384"
---
# <a name="onboard-previous-versions-of-windows"></a>Integração de versões anteriores do Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plataformas**
- Windows 7 SP1 Enterprise
- Windows 7 SP1 Pro
- Windows 8.1 Pro
- Windows 8.1 Enterprise


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).

O Defender for Endpoint estende o suporte para incluir sistemas operacionais de nível inferior, fornecendo recursos avançados de detecção e investigação de ataques em versões com suporte do Windows.

Para fazer a integração de pontos de extremidade de cliente do Windows no Nível Inferior do Defender para Ponto de Extremidade, você precisará:
- Configurar e atualizar clientes de Proteção de Ponto de Extremidade do System Center.
- Instale e configure o Microsoft Monitoring Agent (MMA) para relatar dados do sensor ao Defender para o Ponto de Extremidade, conforme instruído a seguir.

> [!TIP]
> Após a integração do dispositivo, você pode optar por executar um teste de detecção para verificar se ele está corretamente conectado ao serviço. Para obter mais informações, [consulte Execute a detection test on a newly onboarded Defender for Endpoint endpoint endpoint endpoint](run-detection-test.md).

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>Configurar e atualizar clientes de Proteção de Ponto de Extremidade do System Center
> [!IMPORTANT]
> Esta etapa só será necessária se sua organização usar o System Center Endpoint Protection (SCEP).

O Defender for Endpoint integra-se à Proteção de Ponto de Extremidade do System Center para fornecer visibilidade a detecções de malware e parar a propagação de um ataque em sua organização, proibindo arquivos potencialmente mal-intencionados ou malwares suspeitos. 

As etapas a seguir são necessárias para habilitar essa integração: 
- Instalar a atualização da plataforma anti-malware de janeiro de [2017](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie) para clientes de Proteção de Ponto de Extremidade 
- Configurar a associação do Serviço de Proteção de Nuvem do cliente SCEP à **configuração** Avançada
- Configure sua rede para permitir conexões com a nuvem do Microsoft Defender Antivírus. Para obter mais informações, consulte [Permitir conexões com a nuvem do Microsoft Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>Instalar e configurar o Microsoft Monitoring Agent (MMA) para relatar dados do sensor ao Microsoft Defender para Ponto de Extremidade

### <a name="before-you-begin"></a>Antes de começar
Revise os seguintes detalhes para verificar os requisitos mínimos do sistema:
- Instalar a atualização mensal de fevereiro de [2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
  
  > [!NOTE]
  > Aplicável somente para Windows 7 SP1 Enterprise e Windows 7 SP1 Pro. 

- Instalar a [telemetria de](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) diagnóstico e a experiência do cliente

- Instalar o [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (ou posterior) ou [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > Aplicável somente para Windows 7 SP1 Enterprise e Windows 7 SP1 Pro.
    > Não instale o .NET Framework 4.0.x, pois isso negará a instalação acima.

- Atender aos requisitos mínimos do sistema do agente do Azure Log Analytics. Para obter mais informações, consulte [Coletar dados de computadores em seu ambiente com o Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)



1. Baixe o arquivo de instalação do agente: [agente do Windows 64 ou](https://go.microsoft.com/fwlink/?LinkId=828603) agente do Windows [32 bits.](https://go.microsoft.com/fwlink/?LinkId=828604)

2. Obtenha a ID do espaço de trabalho:
   - No painel de navegação Defender para Ponto de Extremidade, selecione Configurações > Gerenciamento de **dispositivos > Integração**
   - Selecione **Windows 7 SP1 e 8.1** como o sistema operacional
   - Copie a ID do espaço de trabalho e a chave do espaço de trabalho

3. Usando a ID do Espaço de Trabalho e a tecla Workspace, escolha qualquer um dos seguintes métodos de instalação para instalar o agente:
    - [Instale manualmente o agente usando a instalação](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard). <br>
      Na página **Opções de Instalação do** Agente, selecione Conectar o agente ao **OMS (Análise de Log do Azure)**
    - [Instale o agente usando a linha de comando](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).
    - [Configure o agente usando um script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).

   > [!NOTE]
   > Se você for um cliente do Governo dos EUA [,](gov.md)em "Nuvem do Azure" precisará escolher "Azure US Government" se estiver usando o assistente de instalação ou se estiver usando uma linha de comando ou um script , de definir o parâmetro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" como 1.

4. Se você estiver usando um proxy para se conectar à Internet, consulte a seção Configurar configurações de proxy.

Depois de concluído, você deverá ver pontos de extremidade integrados no portal dentro de uma hora.

### <a name="configure-proxy-and-internet-connectivity-settings"></a>Configurar configurações de conectividade de proxy e Internet
 
- Cada ponto de extremidade do Windows deve ser capaz de se conectar à Internet usando HTTPS. Essa conexão pode ser direta, usando um proxy ou por meio do [Gateway OMS.](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway)
- Se um proxy ou firewall estiver bloqueando todo o tráfego por padrão e permitindo apenas domínios específicos por meio ou a verificação de HTTPS (inspeção SSL) estiver habilitada, certifique-se de que você habilita o acesso a [URLs](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)de serviço do Defender para Ponto de Extremidade.

## <a name="offboard-client-endpoints"></a>Pontos de extremidade do cliente de offboard
Para offboard, você pode desinstalar o agente MMA do ponto de extremidade ou desconecta-lo do relatório para o seu espaço de trabalho do Defender para Ponto de Extremidade. Depois de fazer o offboard do agente, o ponto de extremidade não enviará mais dados do sensor para o Defender para o Ponto de Extremidade. 

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).

