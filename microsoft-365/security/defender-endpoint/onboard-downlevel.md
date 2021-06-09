---
title: Integração de versões anteriores Windows no Microsoft Defender para Ponto de Extremidade
description: A integração suportava versões anteriores Windows dispositivos de modo que eles possam enviar dados do sensor para o sensor do Microsoft Defender para Ponto de Extremidade
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
ms.openlocfilehash: d0cb4a3d01c1380f4fd06999c8f81a4054e2fd00
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844425"
---
# <a name="onboard-previous-versions-of-windows"></a>Versões anteriores integradas do Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plataformas**
- Windows 7 sp1 Enterprise
- Windows 7 sp1 Pro
- Windows 8.1 Pro
- Windows 8.1 Enterprise


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).

O Defender for Endpoint estende o suporte para incluir sistemas operacionais de nível inferior, fornecendo recursos avançados de detecção e investigação de ataques em versões Windows suportadas.

Para fazer a integração de pontos de extremidade Windows cliente para o Defender para Ponto de Extremidade, você precisará:
- Configure e atualize System Center Endpoint Protection clientes.
- Instale e configure Microsoft Monitoring Agent (MMA) para relatar dados do sensor ao Defender para Ponto de Extremidade, conforme instruído a seguir.

> [!TIP]
> Após a integração do dispositivo, você pode optar por executar um teste de detecção para verificar se ele está corretamente conectado ao serviço. Para obter mais informações, [consulte Execute a detection test on a newly onboarded Defender for Endpoint endpoint endpoint endpoint](run-detection-test.md).

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>Configurar e atualizar System Center Endpoint Protection clientes
> [!IMPORTANT]
> Esta etapa só será necessária se sua organização usar System Center Endpoint Protection (SCEP).

O Defender for Endpoint se integra ao System Center Endpoint Protection para fornecer visibilidade a detecções de malware e parar a propagação de um ataque em sua organização, proibindo arquivos potencialmente mal-intencionados ou malware suspeito. 

As etapas a seguir são necessárias para habilitar essa integração: 
- Instalar a atualização da plataforma anti-malware de janeiro de [2017 para Endpoint Protection clientes](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie) 
- Configurar a associação do Serviço de Proteção de Nuvem do cliente SCEP à **configuração** Avançada
- Configure sua rede para permitir conexões com a Microsoft Defender Antivírus nuvem. Para obter mais informações, consulte [Allow connections to the Microsoft Defender Antivírus cloud](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>Instalar e configurar o Microsoft Monitoring Agent (MMA) para relatar dados do sensor ao Microsoft Defender para Ponto de Extremidade

### <a name="before-you-begin"></a>Antes de começar
Revise os seguintes detalhes para verificar os requisitos mínimos do sistema:
- Instalar a atualização mensal de fevereiro de [2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
  
  > [!NOTE]
  > Aplicável apenas para Windows 7 sp1 Enterprise e Windows 7 sp1 Pro. 

- Instalar a [telemetria de](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) diagnóstico e a experiência do cliente

- Instalar o [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (ou posterior) ou [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > Aplicável apenas para Windows 7 sp1 Enterprise e Windows 7 sp1 Pro.
    > Não instale o .NET Framework 4.0.x, pois isso negará a instalação acima.

- Atender aos requisitos mínimos do sistema do agente do Azure Log Analytics. Para obter mais informações, consulte [Coletar dados de computadores em seu ambiente com o Log Analytics.](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)



1. Baixe o arquivo de instalação do agente: Windows agente de [64 bits](https://go.microsoft.com/fwlink/?LinkId=828603) ou Windows agente [de 32 bits.](https://go.microsoft.com/fwlink/?LinkId=828604)

2. Obtenha a ID do espaço de trabalho:
   - No painel de navegação Defender para Ponto de Extremidade, selecione Configurações > **Gerenciamento de dispositivos > Integração**
   - Selecione **Windows 7 SP1 e 8.1** como o sistema operacional
   - Copie a ID do espaço de trabalho e a chave do espaço de trabalho

3. Usando a ID do Espaço de Trabalho e a tecla Workspace, escolha qualquer um dos seguintes métodos de instalação para instalar o agente:
    - [Instale manualmente o agente usando a instalação](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard). <br>
      Na página **Opções de Instalação do** Agente, selecione Conexão o agente para **OMS (Análise de Log do Azure)**
    - [Instale o agente usando a linha de comando](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).
    - [Configure o agente usando um script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).

   > [!NOTE]
   > Se você for um cliente do Governo dos EUA [,](gov.md)em "Nuvem do Azure" precisará escolher "Azure US Government" se estiver usando o assistente de instalação ou se estiver usando uma linha de comando ou um script , de definir o parâmetro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" como 1.

4. Se você estiver usando um proxy para se conectar à Internet, consulte a seção Configurar configurações de proxy.

Depois de concluído, você deverá ver pontos de extremidade integrados no portal dentro de uma hora.

### <a name="configure-proxy-and-internet-connectivity-settings"></a>Definir as configurações de proxy e conectividade com a Internet
 
- Cada Windows ponto de extremidade deve ser capaz de se conectar à Internet usando HTTPS. Essa conexão pode ser direta, usando um proxy ou por meio do [Gateway OMS.](/azure/log-analytics/log-analytics-oms-gateway)
- Se um proxy ou firewall estiver bloqueando todo o tráfego por padrão e permitindo apenas domínios específicos por meio ou a verificação de HTTPS (inspeção SSL) estiver habilitada, certifique-se de que você habilita o acesso a [URLs](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)de serviço do Defender para Ponto de Extremidade.

## <a name="offboard-client-endpoints"></a>Pontos de extremidade do cliente de offboard
Para offboard, você pode desinstalar o agente MMA do ponto de extremidade ou desconecta-lo do relatório para o seu espaço de trabalho do Defender para Ponto de Extremidade. Depois de fazer o offboard do agente, o ponto de extremidade não enviará mais dados do sensor para o Defender para o Ponto de Extremidade. 

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).
