---
title: Configurar o Microsoft Defender para implantação do Ponto de Extremidade
description: Saiba como configurar a implantação do Microsoft Defender para Ponto de Extremidade
keywords: implantar, configurar, validação de licenciamento, configuração de locatário, configuração de rede
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
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8965594789c3c96c043e3cd1a8922d9ba996ef47
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222436"
---
# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a>Configurar o Microsoft Defender para implantação do Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Implantar o Defender para Ponto de Extremidade é um processo de três fases:

| [![fase de implantação - preparar](images/phase-diagrams/prepare.png)](prepare-deployment.md)<br>[Fase 1: Preparar](prepare-deployment.md) | ![fase de implantação - instalação](images/phase-diagrams/setup.png)<br>Fase 2: Instalação | [![fase de implantação - onboard](images/phase-diagrams/onboard.png)](onboarding.md)<br>[Fase 3: Onboard](onboarding.md) |
| ----- | ----- | ----- |
| | *Você está aqui!*||

No momento, você está na fase de configuração.

Neste cenário de implantação, você será orientado pelas etapas em:
- Validação de licenciamento
- Configuração de locatário
- Configuração da rede


>[!NOTE]
>Para orientar você por meio de uma implantação típica, esse cenário só abrange o uso do Microsoft Endpoint Configuration Manager. O Defender for Endpoint dá suporte ao uso de outras ferramentas de integração, mas não abrange esses cenários no guia de implantação. Para obter mais informações, consulte [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).

## <a name="check-license-state"></a>Verificar o estado da licença

Verificar o estado da licença e se ele foi provisionado corretamente, pode ser feito por meio do centro de administração ou por meio do portal do **Microsoft Azure.**

1. Para exibir suas licenças, acesse o portal do **Microsoft Azure** e navegue até a seção licença [do portal do Microsoft Azure.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)

   ![Imagem da página Licenciamento do Azure](images/atp-licensing-azure-portal.png)

1. Como alternativa, no centro de administração, navegue até **Cobrança**  >  **de Assinaturas**.

    Na tela, você verá todas as licenças provisionadas e seu **Status atual.**

    ![Imagem das licenças de cobrança](images/atp-billing-subscriptions.png)


## <a name="cloud-service-provider-validation"></a>Validação do Provedor de Serviços na Nuvem

Para obter acesso a quais licenças são provisionadas para sua empresa e verificar o estado das licenças, vá para o centro de administração.

1. No **portal parceiro,** selecione **Administrar serviços > Office 365**.

2. Clicar no link **portal do** Parceiro abrirá a opção Administrador em **nome** e lhe dará acesso ao centro de administração do cliente.

   ![Imagem do portal de administração do O365](images/atp-O365-admin-portal-customer.png)



## <a name="tenant-configuration"></a>Configuração do Locatário

Ao acessar o Centro de Segurança do Microsoft Defender pela primeira vez, um assistente que o guiará por algumas etapas iniciais. No final do assistente de instalação, haverá uma instância de nuvem dedicada do Defender para Ponto de Extremidade criada. O método mais fácil é executar essas etapas de um dispositivo cliente Windows 10.

1. Em um navegador da Web, navegue até <https://securitycenter.windows.com> .

    ![Imagem de Configurar suas permissões para o Microsoft Defender para Ponto de Extremidade](images/atp-setup-permissions-wdatp-portal.png)

2. Se passar por uma licença TRIAL, vá para o link ( <https://signup.microsoft.com/Signup?OfferId=6033e4b5-c320-4008-a936-909c2825d83c&dl=WIN_DEF_ATP&pc=xxxxxxx-xxxxxx-xxx-x> )

    Depois que a etapa de autorização for concluída, a tela **de** boas-vindas será exibida.
3. Vá pelas etapas de autorização.

    ![Imagem da tela de boas-vindas para a configuração do portal](images/welcome1.png)

4. Configurar preferências.

   **Local de armazenamento de** dados - É importante configurar isso corretamente. Determine onde o cliente deseja ser hospedado principalmente: EUA, UE ou Reino Unido. Não é possível alterar o local após essa configuração e a Microsoft não transferirá os dados da localização geográfica especificada. 

    **Retenção de dados** - O padrão é de seis meses.

    **Habilitar recursos de** visualização - O padrão está ativado, pode ser alterado posteriormente.

    ![Imagem da localização geográfica na configuração](images/setup-preferences.png)

5. Selecione **Avançar**.

     ![Imagem da configuração de preferência final](images/setup-preferences2.png)

6. Selecione **Continuar**.


## <a name="network-configuration"></a>Configuração da rede
Se a organização não exigir que os pontos de extremidade usem um Proxy para acessar a Internet, ignore esta seção.

O sensor Microsoft Defender ATP requer o Microsoft Windows HTTP (WinHTTP) para relatar os dados do sensor e se comunicar com o serviço Microsoft Defender ATP. O sensor incorporado do Microsoft Defender para Ponto de Extremidade é executado no contexto do sistema usando a conta LocalSystem. O sensor usa o Microsoft Windows HTTP Services (WinHTTP) para permitir a comunicação com o serviço de nuvem Microsoft Defender ATP. A configuração do WinHTTP é independente das configurações de proxy de navegação da Internet do Windows (WinINet) e só pode descobrir um servidor proxy usando os seguintes métodos de descoberta:

**Métodos de Descoberta Automática:**

-   Proxy transparente

-   Protocolo de Descoberta Automática de Proxy da Web (WPAD)

Se um proxy transparente ou WPAD tiver sido implementado na topologia de rede, não será necessário definir configurações especiais. Para obter mais informações sobre as exclusões de URL do Microsoft Defender for Endpoint no proxy, consulte a seção [URLs](production-deployment.md#proxy-service-urls) do Serviço proxy neste documento para a lista de urls allowlist ou em Configure device proxy and [Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).

**Configuração manual de proxy estático:**

-   Configuração baseada em registro

-   WinHTTP configurado usando o comando netsh <br> Adequado apenas para áreas de trabalho em uma topologia estável (por exemplo: uma área de trabalho em uma rede corporativa por trás do mesmo proxy)

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>Configure o servidor proxy manualmente usando um proxy estático baseado no registro

Configure um proxy estático baseado no Registro para permitir que apenas o microsoft Defender para sensor de ponto de extremidade reporte dados de diagnóstico e se comunique com o Microsoft Defender para serviços de Ponto de Extremidade se um computador não tiver permissão para se conectar à Internet. O proxy estático é configurável por meio da Política de Grupo (GP). A política do grupo pode ser encontrada em:

 - Modelos Administrativos \> Windows Components Data Collection and Preview \> Builds Configure \> Authenticated Proxy usage for the Connected User Experience and Telemetry Service
     - De defini-lo **como Habilitado e** selecione **Desabilitar o uso de Proxy Autenticado**

1. Abra o Console de Gerenciamento de Política de Grupo.
2. Crie uma política ou edite uma política existente com base nas práticas organizacionais.
3. Edite a Política de Grupo e navegue até Modelos Administrativos Componentes do Windows Data Collection and **\> Preview \> Builds Configure \> Authenticated Proxy usage for the Connected User Experience and Telemetry Service**. 
    ![Imagem da configuração da Política de Grupo](images/atp-gpo-proxy1.png)

4. Selecione **Habilitado**.
5. Selecione **Desabilitar o uso de Proxy Autenticado**.
   
6. Navegue até **Modelos Administrativos \> Windows Components Data Collection and Preview \> Builds Configure connected user experiences and \> telemetry**.
    ![Imagem da configuração da Política de Grupo](images/atp-gpo-proxy2.png)
7. Selecione **Habilitado**.
8. Insira o **Nome do Servidor Proxy**.

A política define dois valores de registro `TelemetryProxyServer` como REG_SZ e `DisableEnterpriseAuthProxy` como REG_DWORD na chave de registro `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.

O valor do Registro `TelemetryProxyServer` assume o seguinte formato de cadeia de caracteres:

```text
<server name or ip>:<port>
```

Por exemplo: 10.0.0.6:8080

O valor de registro `DisableEnterpriseAuthProxy` deve ser definido como 1.

###  <a name="configure-the-proxy-server-manually-using-netsh-command"></a>Configurar o servidor proxy manualmente usando o comando netsh

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

   Por exemplo: netsh winhttp set proxy 10.0.0.6:8080


###  <a name="proxy-configuration-for-down-level-devices"></a>Configuração de Proxy para dispositivos de nível inferior

Down-Level dispositivos incluem estações de trabalho do Windows 7 SP1 e Windows 8.1, bem como Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 e versões do Windows Server 2016 antes do Windows Server CB 1803. Esses sistemas operacionais terão o proxy configurado como parte do Agente de Gerenciamento da Microsoft para manipular a comunicação do ponto de extremidade para o Azure. Consulte o Guia de Implantação Rápida do Agente de Gerenciamento da Microsoft para obter informações sobre como um proxy é configurado nesses dispositivos.

### <a name="proxy-service-urls"></a>URLs do Serviço proxy
AS URLs que incluem v20 neles só serão necessárias se você tiver o Windows 10, versão 1803 ou dispositivos posteriores. Por exemplo, só será necessário se o dispositivo estiver no ```us-v20.events.data.microsoft.com``` Windows 10, versão 1803 ou posterior.
 

Se um proxy ou firewall estiver bloqueando o tráfego anônimo, como o sensor do Microsoft Defender para Ponto de Extremidade está se conectando do contexto do sistema, certifique-se de que o tráfego anônimo seja permitido nas URLs listadas.

A planilha baixável a seguir lista os serviços e as URLs associadas às quais sua rede deve ser capaz de se conectar. Verifique se não há regras de filtragem de rede ou firewall que negariam o acesso a essas URLs, ou talvez seja necessário criar uma regra *de* autorização especificamente para elas.

|**Planilha de lista de domínios**|**Descrição**|
|:-----|:-----|
|![Imagem em miniatura da planilha URLs do Microsoft Defender para Endpoint](images/mdatp-urls.png)<br/>  | Planilha de registros DNS específicos para locais de serviço, localizações geográficas e sistema operacional. <br><br>[Baixe a planilha aqui.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


###  <a name="microsoft-defender-for-endpoint-service-backend-ip-ranges"></a>Intervalos de IP de back-end do Serviço do Microsoft Defender para Ponto de Extremidade

Se seus dispositivos de rede não suportam regras baseadas em DNS, use intervalos IP.

O Defender para Ponto de Extremidade é criado na nuvem do Azure, implantado nas seguintes regiões:

- AzureCloud.eastus
- AzureCloud.eastus2
- AzureCloud.westcentralus
- AzureCloud.northeurope
- AzureCloud.westeurope
- AzureCloud.uksouth
- AzureCloud.ukwest

Você pode encontrar os intervalos de IP do Azure em Intervalos IP do Azure e Marcas de Serviço [– Nuvem Pública.](https://www.microsoft.com/download/details.aspx?id=56519)

> [!NOTE]
> Como uma solução baseada em nuvem, os intervalos de endereços IP podem mudar. É recomendável mover para regras baseadas em DNS.

> [!NOTE]
> Se você for um cliente do Governo dos EUA, consulte a seção correspondente na [página Defender for Endpoint for US Government.](gov.md#service-backend-ip-ranges)

## <a name="next-step"></a>Próxima etapa

![**Fase 3: Onboard**](images/onboard.png) <br>[Fase 3: Integração](onboarding.md): Integração de dispositivos ao serviço para que o serviço do Microsoft Defender para Ponto de Extremidade possa obter dados do sensor a partir deles. 
