---
title: Configurar configurações de proxy de dispositivo e conexão com a Internet
description: Configure as configurações de proxy e internet do Microsoft Defender para Endpoint para habilitar a comunicação com o serviço de nuvem.
keywords: configurar, proxy, internet, conectividade com a Internet, configurações, configurações de proxy, netsh, winhttp, servidor proxy
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
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0de55eefe2f7dd8c9f891fbe126a68a49699ecd3
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594092"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Definir as configurações de proxy de dispositivo e conectividade com a Internet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

O sensor Defender para Ponto de Extremidade requer que a Microsoft Windows HTTP (WinHTTP) para relatar dados do sensor e se comunicar com o serviço Defender para Ponto de Extremidade.

O sensor Defender para Ponto de Extremidade incorporado é executado no contexto do sistema usando a conta LocalSystem. O sensor usa o Microsoft Windows HTTP Services (WinHTTP) para habilitar a comunicação com o serviço de nuvem do Defender for Endpoint.

>[!TIP]
>Para organizações que usam proxies de envio como gateway para a Internet, você pode usar a proteção de rede para investigar por trás de um proxy. Para saber mais, veja [Investigar eventos de conexão que ocorrem por meio de proxies de encaminhamento](investigate-behind-proxy.md).

A configuração winhttp é independente das configurações de proxy de navegação na Internet (WinINet) Windows internet e só pode descobrir um servidor proxy usando os seguintes métodos de descoberta:

- Métodos de descoberta automática:

  - Proxy transparente

  - Protocolo de Descoberta Automática de Proxy da Web (WPAD)

    > [!NOTE]
    > Se você estiver usando proxy transparente ou WPAD em sua topologia de rede, não precisará de configurações especiais. Para obter mais informações sobre exclusões de URL do Defender para Ponto de Extremidade no proxy, consulte Enable access [to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).

- Configuração manual de proxy estático:

  - Configuração baseada no registro

  - WinHTTP configurado usando o comando netsh - Adequado apenas para desktops em uma topologia estável (por exemplo: um desktop em uma rede corporativa atrás do mesmo proxy)

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>Configure o servidor proxy manualmente usando um proxy estático baseado no registro

Configure um proxy estático baseado no Registro para permitir que apenas o sensor Defender for Endpoint reporte dados de diagnóstico e se comunique com o Defender para serviços de Ponto de Extremidade se um computador não tiver permissão para se conectar à Internet.

> [!NOTE]
> Ao usar essa opção no Windows 10 ou Windows Server 2019, é recomendável ter a seguinte com build (ou posterior) e acúmulo cumulativo de atualizações:
>
> - Windows 10, versão 1809 ou Windows Server 2019 -https://support.microsoft.com/kb/5001384
> - Windows 10, versão 1909 -https://support.microsoft.com/kb/4601380
> - Windows 10, versão 2004 -https://support.microsoft.com/kb/4601382
> - Windows 10, versão 20H2 -https://support.microsoft.com/kb/4601382
>
> Essas atualizações melhoram a conectividade e a confiabilidade do canal CnC (Comando e Controle).

O proxy estático é configurável por meio da Política de Grupo (GP). A política do grupo pode ser encontrada em:

- **Modelos Administrativos > Windows componentes > de dados e builds de visualização > configurar o uso de Proxy Autenticado para o Serviço de Telemetria e Experiência do Usuário Conectado**

  De defini-lo **como Habilitado e** selecione **Desabilitar o uso de Proxy Autenticado.**

  ![Imagem da configuração da Política de Grupo1](images/atp-gpo-proxy1.png)

- **Modelos Administrativos > Windows componentes >** de dados e builds de visualização > Configurar experiências de usuário conectados e telemetria :

  Configurar o proxy

  ![Imagem da configuração da Política de Grupo2](images/atp-gpo-proxy2.png)

  A política define dois valores do Registro, como REG_SZ e como `TelemetryProxyServer` `DisableEnterpriseAuthProxy` REG_DWORD, sob a chave do Registro `HKLM\Software\Policies\Microsoft\Windows\DataCollection` .

  O valor do Registro `TelemetryProxyServer` assume o seguinte formato de cadeia de caracteres:

  ```text
  <server name or ip>:<port>
  ```

  Por exemplo: 10.0.0.6:8080

  O valor de registro `DisableEnterpriseAuthProxy` deve ser definido como 1.

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>Configurar o servidor proxy manualmente usando o comando netsh

Use netsh para configurar um proxy estático de todo o sistema.

> [!NOTE]
> - Isso afetará todos os aplicativos, incluindo serviços do Windows que usam WinHTTP com proxy padrão.</br>
> - Laptops que estão alterando a topologia (por exemplo: do office para o home) não funcionarão com netsh. Use a configuração de proxy estático com base no registro.

1. Abra uma linha de comando com privilégios elevados:

   1. Vá para **Iniciar** e digite **cmd**.

   1. Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.

2. Insira o seguinte comando e pressione **Enter**:

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   Por exemplo: `netsh winhttp set proxy 10.0.0.6:8080`

Para redefinir o proxy winhttp, insira o seguinte comando e pressione **Enter**:

```PowerShell
netsh winhttp reset proxy
```

Para saber mais, veja [Sintaxe, Contextos e Formatação do Comando Netsh](/windows-server/networking/technologies/netsh/netsh-contexts).

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a>Habilitar o acesso a URLs de serviço do Microsoft Defender para Ponto de Extremidade no servidor proxy

Se um proxy ou firewall está bloqueando por padrão todo o tráfego e permitindo apenas a passagem de domínios específicos, adicione os domínios listados na planilha para download à lista de domínios permitidos.

A planilha baixável a seguir lista os serviços e as URLs associadas às quais sua rede deve ser capaz de se conectar. Você deve garantir que não haja regras de filtragem de rede ou firewall que neguem o acesso *a* essas URLs, ou talvez seja necessário criar uma regra de autorização especificamente para elas.


| Planilha de lista de domínios | Descrição |
|:-----|:-----|
|![Imagem em miniatura da planilha URLs do Microsoft Defender para Endpoint](images/mdatp-urls.png)<br/>  | Planilha de registros DNS específicos para locais de serviço, localizações geográficas e sistema operacional. <br><br>[Baixe a planilha aqui.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


Se um proxy ou firewall tiver verificação HTTPS habilitada (inspeção SSL), exclua os domínios listados na tabela acima da verificação HTTPS.

> [!NOTE]
> settings-win.data.microsoft.com só será necessário se você tiver Windows 10 dispositivos executando a versão 1803 ou anterior.<br>


> [!NOTE]
> URLs que incluem v20 neles são necessárias apenas se você tiver Windows 10 que executam a versão 1803 ou posterior. Por exemplo, é necessário para um dispositivo Windows 10 que executa a versão 1803 ou posterior e está conectado à região `us-v20.events.data.microsoft.com` Armazenamento dados dos EUA.


> [!NOTE]
> Se você estiver usando Microsoft Defender Antivírus em seu ambiente, consulte [Configure network connections to the Microsoft Defender Antivírus cloud service](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).

Se um proxy ou firewall estiver bloqueando o tráfego anônimo, como o sensor Defender for Endpoint está se conectando do contexto do sistema, certifique-se de que o tráfego anônimo seja permitido nas URLs listadas anteriormente.

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a>Microsoft Monitoring Agent (MMA) - requisitos de proxy e firewall para versões mais antigas do cliente Windows ou Windows Server

As informações a seguir listam as informações de configuração de proxy e firewall necessárias para se comunicar com o agente do Log Analytics (geralmente chamado de Microsoft Monitoring Agent) para as versões anteriores do Windows, como Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 e Windows Server 2016.

|Recurso agent|Portas |Direção |Ignorar inspeção HTTPS|
|------|---------|--------|--------|   
|*.ods.opinsights.azure.com |Porta 443 |Saída|Sim |  
|*.oms.opinsights.azure.com |Porta 443 |Saída|Sim |  
|*.blob.core.windows.net |Porta 443 |Saída|Sim |
|*.azure-automation.net |Porta 443 |Saída|Sim |  


> [!NOTE]
> Como uma solução baseada em nuvem, o intervalo ip pode mudar. É recomendável mover para a configuração de resolução de DNS.

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a>Confirmar Microsoft Monitoring Agent de URL de serviço (MMA) 

Consulte as seguintes diretrizes para eliminar o requisito curinga (*) para seu ambiente específico ao usar o Microsoft Monitoring Agent (MMA) para versões anteriores do Windows.

1.  Integração de um sistema operacional anterior com o Microsoft Monitoring Agent (MMA) no Defender for Endpoint (para obter mais informações, consulte Onboard previous [versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and Onboard Windows [servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).

2.  Verifique se o computador está relatando com êxito no portal Central de Segurança do Microsoft Defender.

3.  Execute a TestCloudConnection.exe de "C:\Program Files\Microsoft Monitoring Agent\Agent" para validar a conectividade e ver as URLs necessárias para seu espaço de trabalho específico.

4.  Verifique a lista URLs do Microsoft Defender para Pontos de Extremidade para a lista completa de requisitos para sua região (consulte a Planilha urls de [serviço](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).

    ![Imagem do administrador no Windows PowerShell](images/admin-powershell.png)

Os curingas (*) usados em *.ods.opinsights.azure.com, *.oms.opinsights.azure.com e *.agentsvc.azure-automation.net url podem ser substituídos por sua ID específica do Workspace. A ID do Espaço de Trabalho é específica para seu ambiente e espaço de trabalho e pode ser encontrada na seção Integração do seu locatário no portal Central de Segurança do Microsoft Defender.

O ponto de extremidade da URL *.blob.core.windows.net pode ser substituído por URLs mostradas na seção "Regra de Firewall: *.blob.core.windows.net" dos resultados do teste. 

> [!NOTE]
> No caso de integração por meio do Azure Defender, vários espaços de trabalho talvez usados. Você precisará executar o procedimento TestCloudConnection.exe acima em uma máquina interna de cada espaço de trabalho (para determinar se há alterações nas URLs *.blob.core.windows.net entre os espaços de trabalho).

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a>Verificar a conectividade do cliente com o Microsoft Defender para URLs de serviço de ponto de extremidade

Verifique se a configuração do proxy foi concluída com êxito, se o WinHTTP pode descobrir e se comunicar por meio do servidor proxy em seu ambiente e se o servidor proxy permite o tráfego para os URLs do serviço Defender para Ponto de Extremidade.

1. Baixe a [MDATP do Analisador](https://aka.ms/mdatpanalyzer) de Cliente para o computador em que o sensor defender for Endpoint está sendo executado.

2. Extraia o conteúdo de MDATPClientAnalyzer.zip no dispositivo.

3. Abra uma linha de comando com privilégios elevados:

   1. Vá para **Iniciar** e digite **cmd**.

   1.  Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.

4. Insira o seguinte comando e pressione **Enter**:

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    Substitua *HardDrivePath* pelo caminho para o qual a ferramenta MDATPClientAnalyzer foi baixada, por exemplo:

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. Extraia *oMDATPClientAnalyzerResult.zip* criado pela ferramenta na pasta usada no *HardDrivePath*.

6. Abra *MDATPClientAnalyzerResult.txt* e verifique se você executou as etapas de configuração do proxy para permitir a descoberta do servidor e o acesso às URLs de serviço.

   A ferramenta verifica a conectividade dos URLs do serviço Defender para Ponto de Extremidade com os quais o Defender para ponto de extremidade do cliente está configurado para interagir. Em seguida, ele imprime os resultados no arquivo *MDATPClientAnalyzerResult.txt* para cada URL que pode ser potencialmente usado para se comunicar com os serviços do Defender para Ponto de Extremidade. Por exemplo:

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

Se pelo menos uma das opções de conectividade retornar um status (200), então o Defender para ponto de extremidade do cliente pode se comunicar corretamente com o URL testado usando este método de conectividade.

No entanto, se os resultados da verificação de conectividade indicarem uma falha, um erro HTTP será exibido (consulte Códigos de status HTTP). Em seguida, você pode usar as URLs na tabela mostrada em Habilitar o acesso a [URLs](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)de serviço do Defender para Ponto de Extremidade no servidor proxy . As URLs que você usará dependerão da região selecionada durante o procedimento de integração.

> [!NOTE]
>  A ferramenta Connectivity Analyzer não é compatível com a regra ASR [Bloqueie as criações de processos originadas de comandos PSExec e WMI](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules). Você precisará desativar temporariamente esta regra para executar a ferramenta de conectividade.


> [!NOTE]
> Quando o TelemetryProxyServer for definido, no Registro ou por meio da Política de Grupo, o Defender para Ponto de Extremidade retornará ao direto se não puder acessar o proxy definido.

## <a name="related-topics"></a>Tópicos relacionados

- [Dispositivos integrados do Windows 10](configure-endpoints.md)
- [Solucionar problemas de integração do Microsoft Defender para pontos de extremidade](troubleshoot-onboarding.md)
