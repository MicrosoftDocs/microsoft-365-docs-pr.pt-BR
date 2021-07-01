---
title: Configurar as configurações de proxy e conexão com a Internet do dispositivo para ponto de extremidade DLP
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Saiba como configurar as configurações de proxy e conexão com a Internet do dispositivo para ponto de extremidade DLP.
ms.openlocfilehash: 801f3cf4f2215002fb80f7c4d68c2f5b83f5d04d
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226702"
---
# <a name="configure-device-proxy-and-internet-connection-settings-for-endpoint-dlp"></a>Configurar as configurações de proxy e conexão com a Internet do dispositivo para ponto de extremidade DLP

O ponto de extremidade DLP da Microsoft usa o Microsoft Windows HTTP (WinHTTP) para relatar dados e se comunicar com o serviço em nuvem do ponto de extremidade da Microsoft. O ponto de extremidade DLP integrado é executado no contexto do sistema usando a conta LocalSystem.

> [!TIP]
> Para organizações que usam proxies de envio como gateway para a Internet, você pode usar a proteção de rede para investigar por trás de um proxy. Para saber mais, veja [Investigar eventos de conexão que ocorrem por meio de proxies de encaminhamento](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).

A definição da configuração do WinHTTP é independente das configurações de proxy de navegação da Internet do Windows (WinINet) e só pode descobrir um servidor proxy usando os seguintes métodos de descoberta automática:

- Proxy transparente
- Protocolo de Descoberta Automática de Proxy da Web (WPAD)

> [!NOTE]
> Se estiver usando proxy transparente ou WPAD na topologia de rede, você não precisa de configurações especiais. Para saber mais sobre o sobre o Defender para exclusões de URL do ponto de extremidade no proxy, veja [Habilitar acesso para URLs do serviço em nuvem do ponto de extremidade DLP no servidor proxy](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).

- Configuração manual de proxy estático:
  - Configuração baseada em registro
  - WinHTTP configurado usando o comando netsh - Adequado apenas para desktops em uma topologia estável (por exemplo: um desktop em uma rede corporativa atrás do mesmo proxy)

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>Configure o servidor proxy manualmente usando um proxy estático baseado no registro

Para dispositivos de ponto de extremidade sem permissão para se conectar à Internet, você precisa configurar um proxy estático baseado no registro. Você precisa configurar isso para permitir que apenas o ponto de extremidade DLP da Microsoft relate dados de diagnóstico e se comunique com o serviço em nuvem do ponto de extremidade da Microsoft.

O proxy estático é configurável por meio da Política de Grupo (GP). A política do grupo pode ser encontrada em:

1. Abra **Modelos Administrativos > Componentes do Windows > Coleta de Dados e Compilações de Visualização > Configurar o uso de proxy autenticado para a experiência do usuário conectado e serviço de telemetria**

2. Selecione para **Habilitado** e selecione **Desabilitar uso de proxy autenticado**:

   ![Imagem das configurações da Política de Grupo 1](../media/atp-gpo-proxy1.png)

3. Abra **Modelos Administrativos > Componentes do Windows > Coleta de Dados e Compilações de Visualização > Configurar experiências de usuário conectado e telemetria**:

   Configurar o proxy

   ![Imagem das configurações da Política de Grupo 2](../media/atp-gpo-proxy2.png)

   A política define dois valores de registro `TelemetryProxyServer` como REG_SZ e `DisableEnterpriseAuthProxy` como REG_DWORD na chave de registro `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.

   O valor de registro TelemetryProxyServer está neste formato \<server name or ip\>:\<port\>. Por exemplo: **10.0.0.6:8080**

   O valor de registro `DisableEnterpriseAuthProxy` deve ser definido como 1.

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>Configure o servidor proxy manualmente usando o comando "netsh"

Use netsh para configurar um proxy estático de todo o sistema.

> [!NOTE]
> Isso afetará todos os aplicativos, incluindo serviços do Windows que usam WinHTTP com proxy padrão. - Laptops que estão mudando de topologia (por exemplo: do escritório para casa) terão mau funcionamento com o netsh. Use a configuração de proxy estático com base no registro.

1. Abra uma linha de comando com privilégios elevados:
    1. Vá para **Iniciar** e digite **cmd**
    2. Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.

2. Insira o seguinte comando e pressione **Enter**:

   `netsh winhttp set proxy <proxy>:<port>`

   Por exemplo: **netsh winhttp set proxy 10.0.0.6:8080**

3. Para redefinir o proxy winhttp, insira o seguinte comando e pressione **Enter**:

   `netsh winhttp reset proxy`

Para saber mais, veja [Sintaxe, Contextos e Formatação do Comando Netsh](/windows-server/networking/technologies/netsh/netsh-contexts).

## <a name="enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server"></a>Habilitar acesso para URLs do serviço em nuvem do ponto de extremidade DLP no servidor proxy

Se um proxy ou firewall está bloqueando por padrão todo o tráfego e permitindo apenas a passagem de domínios específicos, adicione os domínios listados na planilha para download à lista de domínios permitidos.

Esta [planilha para download](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) lista os serviços e os seus URLs associados que a sua rede deve ser capaz de se conectar. Você deve garantir que não hajam regras de firewall ou de filtragem de rede que neguem o acesso a esses URLs, ou pode ser necessário criar uma regra de permissão especificamente para eles.

Se um proxy ou firewall tiver verificação HTTPS habilitada (inspeção SSL), exclua os domínios listados na tabela acima da verificação HTTPS.
Se um proxy ou firewall estiver bloqueando o tráfego anônimo, como o ponto de extremidade DLP está se conectando a partir do contexto do sistema, certifique-se de que o tráfego anônimo seja permitido nos URLs listados anteriormente.

## <a name="verify-client-connectivity-to-microsoft-cloud-service-urls"></a>Verifique a conectividade do cliente com os URLs do serviço de nuvem da Microsoft

Verifique se a configuração do proxy foi concluída com êxito, se o WinHTTP pode descobrir e se comunicar por meio do servidor proxy em seu ambiente e se o servidor proxy permite o tráfego para os URLs do serviço Defender para Ponto de Extremidade.

1. Baixe a [ferramenta MDATP Client Analyzer](https://aka.ms/mdatpanalyzer) para o PC onde o ponto de extremidade DLP está sendo executado.
2. Extraia o conteúdo de MDATPClientAnalyzer.zip no dispositivo.
3. Abra uma linha de comando com privilégios elevados:
    1. Vá para **Iniciar** e digite **cmd**.
    1. Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.
4. Insira o seguinte comando e pressione **Enter**:

   `HardDrivePath\MDATPClientAnalyzer.cmd`

   Substitua *HardDrivePath* pelo caminho para onde a ferramenta MDATPClientAnalyzer foi baixada, por exemplo

   **C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**

5. Extraia o **MDATPClientAnalyzerResult.zip** _ criado pela ferramenta na pasta usada no _HardDrivePath *.

6. Abra **MDATPClientAnalyzerResult.txt** e verifique se você executou as etapas de configuração do proxy para permitir a descoberta do servidor e o acesso às URLs de serviço.  A ferramenta verifica a conectividade dos URLs do serviço Defender para Ponto de Extremidade com os quais o Defender para ponto de extremidade do cliente está configurado para interagir. Em seguida, ele imprime os resultados no arquivo **MDATPClientAnalyzerResult.txt** para cada URL que pode ser potencialmente usado para se comunicar com os serviços do Defender para Ponto de Extremidade. Por exemplo:

   ```DOS
   Testing URL: https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command-line proxy: Doesn't exist
   ```

Se pelo menos uma das opções de conectividade retornar um status (200), então o Defender para ponto de extremidade do cliente pode se comunicar corretamente com o URL testado usando este método de conectividade.

No entanto, se os resultados da verificação de conectividade indicarem uma falha, um erro HTTP será exibido (consulte Códigos de status HTTP). Você pode então usar os URLs na tabela mostrada em[Habilitar acesso para URLs do serviço em nuvem do ponto de extremidade DLP no servidor proxy](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server). Os URLs que você usará dependerão da região selecionada durante o procedimento de integração.

> [!NOTE]
>
> A ferramenta Connectivity Analyzer não é compatível com a regra ASR [Bloqueie as criações de processos originadas de comandos PSExec e WMI](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules). Você precisará desativar temporariamente esta regra para executar a ferramenta de conectividade.
>
> Quando o TelemetryProxyServer é definido, no Registro ou via Política de Grupo, o Defender para Ponto de Extremidade voltará a ser direto se não puder acessar o proxy definido. Tópicos relacionados:
>
> - Dispositivos integrados do Windows 10
> - Solucionar problemas de integração do ponto de extremidade DLP da Microsoft

## <a name="see-also"></a>Confira também

- [Saiba mais sobre a Prevenção contra perda de dados do ponto de extremidade](endpoint-dlp-learn-about.md)
- [Usando a Prevenção contra perda de dados de ponto de extremidade](endpoint-dlp-using.md)
- [Saiba mais sobre prevenção contra perda de dados](dlp-learn-about-dlp.md)
- [Criar, testar e ajustar uma política DLP](create-test-tune-dlp-policy.md)
- [Começar a usar o Explorador de atividades](data-classification-activity-explorer.md)
- [Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/)
- [Ferramentas e métodos de integração para computadores Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Dispositivos associados ao Microsoft Azure AD](/azure/active-directory/devices/concept-azure-ad-join)
- [Baixar o novo Microsoft Edge baseado em Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
