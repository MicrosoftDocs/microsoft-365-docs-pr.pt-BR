---
title: Configurar o Micro Focus ArcSight para puxar o Microsoft Defender para detecções de ponto de extremidade
description: Configurar o Micro Focus ArcSight para receber e puxar detecções do Centro de Segurança do Microsoft Defender
keywords: configurar o Micro Focus ArcSight, as ferramentas de gerenciamento de informações e eventos de segurança, arcsight
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
ms.openlocfilehash: a52f810647c387c5a5726b9d31998c34add4092e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166180"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a><span data-ttu-id="f7a3c-104">Configurar o Micro Focus ArcSight para puxar o Defender para detecções de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="f7a3c-104">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f7a3c-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f7a3c-105">**Applies to:**</span></span>
- [<span data-ttu-id="f7a3c-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f7a3c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f7a3c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7a3c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="f7a3c-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="f7a3c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f7a3c-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink) 

<span data-ttu-id="f7a3c-110">Você precisará instalar e configurar alguns arquivos e ferramentas para usar o Micro Focus ArcSight para que ele possa puxar o Defender para detecções de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-110">You'll need to install and configure some files and tools to use Micro Focus ArcSight so that it can pull Defender for Endpoint detections.</span></span>

>[!Note]
>- <span data-ttu-id="f7a3c-111">[O Alerta do Defender para Ponto](alerts.md) de Extremidade é composto por uma ou mais detecções</span><span class="sxs-lookup"><span data-stu-id="f7a3c-111">[Defender for Endpoint Alert](alerts.md) is composed from one or more detections</span></span>
>- <span data-ttu-id="f7a3c-112">[O Defender para Detecção de Ponto](api-portal-mapping.md) de Extremidade é composto do evento suspeito ocorrido no Device e seus detalhes de Alerta relacionados.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-112">[Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f7a3c-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="f7a3c-113">Before you begin</span></span>

<span data-ttu-id="f7a3c-114">A configuração da ferramenta Conector Do Micro Focus ArcSight requer vários arquivos de configuração para que ele puxe e analisar detecções do seu aplicativo do Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="f7a3c-114">Configuring the Micro Focus ArcSight Connector tool requires several configuration files for it to pull and parse detections from your Azure Active Directory (AAD) application.</span></span>

<span data-ttu-id="f7a3c-115">Esta seção orienta você a obter as informações necessárias para definir e usar os arquivos de configuração necessários corretamente.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-115">This section guides you in getting the necessary information to set and use the required configuration files correctly.</span></span>

- <span data-ttu-id="f7a3c-116">Certifique-se de ter habilitado o recurso de integração SIEM no menu **Configurações.**</span><span class="sxs-lookup"><span data-stu-id="f7a3c-116">Make sure you have enabled the SIEM integration feature from the **Settings** menu.</span></span> <span data-ttu-id="f7a3c-117">Para obter mais informações, consulte [Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md).</span><span class="sxs-lookup"><span data-stu-id="f7a3c-117">For more information, see [Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="f7a3c-118">Tenha o arquivo salvo da habilitação do recurso de integração SIEM pronto.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-118">Have the file you saved from enabling the SIEM integration feature ready.</span></span> <span data-ttu-id="f7a3c-119">Você precisará obter os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="f7a3c-119">You'll need to get the following values:</span></span>
  - <span data-ttu-id="f7a3c-120">URL de atualização do token OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="f7a3c-120">OAuth 2.0 Token refresh URL</span></span>
  - <span data-ttu-id="f7a3c-121">ID do cliente OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="f7a3c-121">OAuth 2.0 Client ID</span></span>
  - <span data-ttu-id="f7a3c-122">Segredo do cliente OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="f7a3c-122">OAuth 2.0 Client secret</span></span>

- <span data-ttu-id="f7a3c-123">Tenha os seguintes arquivos de configuração prontos:</span><span class="sxs-lookup"><span data-stu-id="f7a3c-123">Have the following configuration files ready:</span></span>
  - <span data-ttu-id="f7a3c-124">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="f7a3c-124">WDATP-connector.properties</span></span>
  - <span data-ttu-id="f7a3c-125">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="f7a3c-125">WDATP-connector.jsonparser.properties</span></span>

    <span data-ttu-id="f7a3c-126">Você teria salvo um arquivo .zip que contém esses dois arquivos quando escolheu Micro Focus ArcSight como o tipo SIEM que você usa em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-126">You would have saved a .zip file which contains these two files when you chose Micro Focus ArcSight as the SIEM type you use in your organization.</span></span>

- <span data-ttu-id="f7a3c-127">Certifique-se de gerar os seguintes tokens e se eles estão prontos:</span><span class="sxs-lookup"><span data-stu-id="f7a3c-127">Make sure you generate the following tokens and have them ready:</span></span>
  - <span data-ttu-id="f7a3c-128">Token de acesso</span><span class="sxs-lookup"><span data-stu-id="f7a3c-128">Access token</span></span>
  - <span data-ttu-id="f7a3c-129">Token de atualização</span><span class="sxs-lookup"><span data-stu-id="f7a3c-129">Refresh token</span></span>

  <span data-ttu-id="f7a3c-130">Você pode gerar esses tokens a partir da seção de instalação de integração **siem** do portal.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-130">You can generate these tokens from the **SIEM integration** setup section of the portal.</span></span>

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a><span data-ttu-id="f7a3c-131">Instalar e configurar o Micro Focus ArcSight FlexConnector</span><span class="sxs-lookup"><span data-stu-id="f7a3c-131">Install and configure Micro Focus ArcSight FlexConnector</span></span>

<span data-ttu-id="f7a3c-132">As etapas a seguir pressupom que você concluiu todas as etapas necessárias em [Before you begin](#before-you-begin).</span><span class="sxs-lookup"><span data-stu-id="f7a3c-132">The following steps assume that you have completed all the required steps in [Before you begin](#before-you-begin).</span></span>

1. <span data-ttu-id="f7a3c-133">Instale o instalador mais recente do Windows FlexConnector de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-133">Install the latest 32-bit Windows FlexConnector installer.</span></span> <span data-ttu-id="f7a3c-134">Você pode encontrar isso no Centro de Software HPE.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-134">You can find this in the HPE Software center.</span></span> <span data-ttu-id="f7a3c-135">Normalmente, a ferramenta é instalada no seguinte local padrão: `C:\Program Files\ArcSightFlexConnectors\current\bin` .</span><span class="sxs-lookup"><span data-stu-id="f7a3c-135">The tool is typically installed in the following default location: `C:\Program Files\ArcSightFlexConnectors\current\bin`.</span></span></br></br><span data-ttu-id="f7a3c-136">Você pode escolher onde salvar a ferramenta, por exemplo, C: \\ *folder_location*\current\bin onde folder_location representa o local da instalação. </span><span class="sxs-lookup"><span data-stu-id="f7a3c-136">You can choose where to save the tool, for example C:\\*folder_location*\current\bin where *folder_location* represents the installation location.</span></span>

2. <span data-ttu-id="f7a3c-137">Siga o assistente de instalação pelas seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="f7a3c-137">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="f7a3c-138">Introdução</span><span class="sxs-lookup"><span data-stu-id="f7a3c-138">Introduction</span></span>
   - <span data-ttu-id="f7a3c-139">Escolha Instalar Pasta</span><span class="sxs-lookup"><span data-stu-id="f7a3c-139">Choose Install Folder</span></span>
   - <span data-ttu-id="f7a3c-140">Escolha Instalar Conjunto</span><span class="sxs-lookup"><span data-stu-id="f7a3c-140">Choose Install Set</span></span>
   - <span data-ttu-id="f7a3c-141">Escolha Pasta de Atalho</span><span class="sxs-lookup"><span data-stu-id="f7a3c-141">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="f7a3c-142">Resumo da pré-instalação</span><span class="sxs-lookup"><span data-stu-id="f7a3c-142">Pre-Installation Summary</span></span>
   - <span data-ttu-id="f7a3c-143">Instalando...</span><span class="sxs-lookup"><span data-stu-id="f7a3c-143">Installing...</span></span>

   <span data-ttu-id="f7a3c-144">Você pode manter os valores padrão para cada uma dessas tarefas ou modificar a seleção para atender aos seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-144">You can keep the default values for each of these tasks or modify the selection to suit your requirements.</span></span>

3. <span data-ttu-id="f7a3c-145">Abra o Explorador de Arquivos e localize os dois arquivos de configuração salvos ao habilitar o recurso de integração SIEM.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-145">Open File Explorer and locate the two configuration files you saved when you enabled the SIEM integration feature.</span></span> <span data-ttu-id="f7a3c-146">Coloque os dois arquivos no local de instalação do FlexConnector, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f7a3c-146">Put the two files in the FlexConnector installation location, for example:</span></span>

   - <span data-ttu-id="f7a3c-147">WDATP-connector.jsonparser.properties: C: \\ *folder_location*\current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="f7a3c-147">WDATP-connector.jsonparser.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   - <span data-ttu-id="f7a3c-148">WDATP-connector.properties: C: \\ *folder_location*\current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="f7a3c-148">WDATP-connector.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   > [!NOTE]
   > 
   > <span data-ttu-id="f7a3c-149">Você deve colocar os arquivos de configuração nesse local, onde folder_location *representa* o local onde você instalou a ferramenta.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-149">You must put the configuration files in this location, where *folder_location* represents the location where you installed the tool.</span></span>

4. <span data-ttu-id="f7a3c-150">Depois que a instalação do conector principal é concluída, a janela de Instalação do Conector é aberta.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-150">After the installation of the core connector completes, the Connector Setup window opens.</span></span> <span data-ttu-id="f7a3c-151">Na janela Configuração do Conector, selecione **Adicionar um Conector**.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-151">In the Connector Setup window, select **Add a Connector**.</span></span>

5. <span data-ttu-id="f7a3c-152">Selecione Tipo: **ArcSight FlexConnector REST** e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-152">Select Type: **ArcSight FlexConnector REST** and click **Next**.</span></span>

6. <span data-ttu-id="f7a3c-153">Digite as informações a seguir no formulário de detalhes do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-153">Type the following information in the parameter details form.</span></span> <span data-ttu-id="f7a3c-154">Todos os outros valores no formulário são opcionais e podem ser deixados em branco.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-154">All other values in the form are optional and can be left blank.</span></span>

   <table>
    <tbody style="vertical-align:top;">
    <tr>
    <th><span data-ttu-id="f7a3c-155">Campo</span><span class="sxs-lookup"><span data-stu-id="f7a3c-155">Field</span></span></th>
    <th><span data-ttu-id="f7a3c-156">Valor</span><span class="sxs-lookup"><span data-stu-id="f7a3c-156">Value</span></span></th>
    </tr>
    <tr>
    <td><span data-ttu-id="f7a3c-157">Arquivo de Configuração</span><span class="sxs-lookup"><span data-stu-id="f7a3c-157">Configuration File</span></span></td>
    <td><span data-ttu-id="f7a3c-158">Digite o nome do arquivo de propriedade do cliente.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-158">Type in the name of the client property file.</span></span> <span data-ttu-id="f7a3c-159">O nome deve corresponder ao arquivo fornecido no .zip que você baixou.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-159">The name must match the file provided in the .zip that you downloaded.</span></span>
<span data-ttu-id="f7a3c-160">Por exemplo, se o arquivo de configuração no diretório flexagent for chamado &quot; &quot;WDATP-Connector.js&quot; onparser.properties, digite &quot; &quot; WDATP-Connector &quot; como o nome do arquivo de propriedade do cliente.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-160">For example, if the configuration file in &quot;flexagent&quot; directory is named &quot;WDATP-Connector.jsonparser.properties&quot;, you must type &quot;WDATP-Connector&quot; as the name of the client property file.</span></span></td>
    </tr>
    <td><span data-ttu-id="f7a3c-161">URL de eventos</span><span class="sxs-lookup"><span data-stu-id="f7a3c-161">Events URL</span></span></td>
    <td><span data-ttu-id="f7a3c-162">Dependendo do local do datacenter, selecione a URL da UE ou dos EUA:</span><span class="sxs-lookup"><span data-stu-id="f7a3c-162">Depending on the location of your datacenter, select either the EU or the US URL:</span></span> </br></br> <span data-ttu-id="f7a3c-163"><b>Para a UE</b>: https:// <i></i> wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="f7a3c-163"><b>For EU</b>:  https://<i></i>wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br>
   </br><span data-ttu-id="f7a3c-164"><b>Para OS:</b> https:// <i></i> wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="f7a3c-164"><b>For US:</b> https://<i></i>wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br> <br> <span data-ttu-id="f7a3c-165"><b>Para o</b>Reino Unido : https:// <i></i> wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="f7a3c-165"><b>For UK</b>:  https://<i></i>wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span></td>
    <tr>
    <td><span data-ttu-id="f7a3c-166">Tipo de autenticação</span><span class="sxs-lookup"><span data-stu-id="f7a3c-166">Authentication Type</span></span></td>
    <td><span data-ttu-id="f7a3c-167">OAuth 2</span><span class="sxs-lookup"><span data-stu-id="f7a3c-167">OAuth 2</span></span></td>
    </tr>
    <td><span data-ttu-id="f7a3c-168">Arquivo propriedades do cliente OAuth 2</span><span class="sxs-lookup"><span data-stu-id="f7a3c-168">OAuth 2 Client Properties file</span></span></td>
    <td><span data-ttu-id="f7a3c-169">Navegue até o local do <em>arquivo wdatp-connector.properties.</em></span><span class="sxs-lookup"><span data-stu-id="f7a3c-169">Browse to the location of the <em>wdatp-connector.properties</em> file.</span></span> <span data-ttu-id="f7a3c-170">O nome deve corresponder ao arquivo fornecido no .zip que você baixou.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-170">The name must match the file provided in the .zip that you downloaded.</span></span></td>
    <tr>
    <td><span data-ttu-id="f7a3c-171">Token de atualização</span><span class="sxs-lookup"><span data-stu-id="f7a3c-171">Refresh Token</span></span></td>
    <td><span data-ttu-id="f7a3c-172">Você pode obter um token de atualização de duas maneiras: gerando um token de atualização a partir da página de configurações <b>siem</b> ou usando a ferramenta restutil.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-172">You can obtain a refresh token in two ways: by generating a refresh token from the <b>SIEM settings</b> page or using the restutil tool.</span></span> <br><br> <span data-ttu-id="f7a3c-173">Para obter mais informações sobre como gerar um token de atualização da configuração <b>Preferências,</b> consulte <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Enable SIEM integration in Defender for Endpoint</a>.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-173">For more information on generating a refresh token from the <b>Preferences setup</b> , see <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Enable SIEM integration in Defender for Endpoint</a>.</span></span> </br> </br><span data-ttu-id="f7a3c-174"><b>Obter seu token de atualização usando a ferramenta restutil:</b> </span><span class="sxs-lookup"><span data-stu-id="f7a3c-174"><b>Get your refresh token using the restutil tool:</b> </span></span></br> <span data-ttu-id="f7a3c-175">a.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-175">a.</span></span> <span data-ttu-id="f7a3c-176">Abra um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-176">Open a command prompt.</span></span> <span data-ttu-id="f7a3c-177">Navegue até C:\<em>folder_location</em>\current\bin onde folder_location <em>representa</em> o local onde você instalou a ferramenta.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-177">Navigate to C:\<em>folder_location</em>\current\bin where <em>folder_location</em> represents the location where you installed the tool.</span></span> </br></br> <span data-ttu-id="f7a3c-178">b.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-178">b.</span></span> <span data-ttu-id="f7a3c-179">Tipo: <code>arcsight restutil token -config</code> do diretório bin. Por exemplo: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> Uma janela do navegador da Web será aberta.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-179">Type: <code>arcsight restutil token -config</code> from the bin directory.For example: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> A Web browser window will open.</span></span> </br> </br><span data-ttu-id="f7a3c-180">c.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-180">c.</span></span> <span data-ttu-id="f7a3c-181">Digite suas credenciais e clique no campo senha para permitir que a página seja redirecionada.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-181">Type in your credentials then click on the password field to let the page redirect.</span></span> <span data-ttu-id="f7a3c-182">No prompt de logon, insira suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-182">In the login prompt, enter your credentials.</span></span> </br> </br><span data-ttu-id="f7a3c-183">d.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-183">d.</span></span> <span data-ttu-id="f7a3c-184">Um token de atualização é mostrado no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-184">A refresh token is shown in the command prompt.</span></span> </br></br> <span data-ttu-id="f7a3c-185">e.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-185">e.</span></span> <span data-ttu-id="f7a3c-186">Copie e colar no campo <b>Token de Atualização.</b></span><span class="sxs-lookup"><span data-stu-id="f7a3c-186">Copy and paste it into the <b>Refresh Token</b> field.</span></span>
    </td>
    </tr>
    </tr>
    </table><br/>
    
7. <span data-ttu-id="f7a3c-187">Uma janela do navegador é aberta pelo conector.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-187">A browser window is opened by the connector.</span></span> <span data-ttu-id="f7a3c-188">Faça logon com suas credenciais de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-188">Login with your application credentials.</span></span> <span data-ttu-id="f7a3c-189">Depois de fazer logon, você será solicitado a dar permissão ao cliente OAuth2.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-189">After you log in, you'll be asked to give permission to your OAuth2 Client.</span></span> <span data-ttu-id="f7a3c-190">Você deve dar permissão ao cliente OAuth 2 para que a configuração do conector possa ser autenticada.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-190">You must give permission to your OAuth 2 Client so that the connector configuration can authenticate.</span></span>

   <span data-ttu-id="f7a3c-191">Se for <code>redirect_uri</code> uma URL https, você será redirecionado para uma URL no host local.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-191">If the <code>redirect_uri</code> is a https URL, you'll be redirected to a URL on the local host.</span></span> <span data-ttu-id="f7a3c-192">Você verá uma página que solicita que você confie no certificado fornecido pelo conector em execução no host local.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-192">You'll see a page that requests for you to trust the certificate supplied by the connector running on the local host.</span></span> <span data-ttu-id="f7a3c-193">Você precisará confiar nesse certificado se o redirect_uri for um https.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-193">You'll need to trust this certificate if the redirect_uri is a https.</span></span>
   
   <span data-ttu-id="f7a3c-194">Se, no entanto, você especificar uma URL http para o redirect_uri, não será necessário fornecer consentimento para confiar no certificado.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-194">If however you specify a http URL for the redirect_uri, you do not need to provide consent in trusting the certificate.</span></span>

8. <span data-ttu-id="f7a3c-195">Continue com a configuração do conector retornando à janela de Instalação do Conector do Micro Focus ArcSight.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-195">Continue with the connector setup by returning to the Micro Focus ArcSight Connector Setup window.</span></span>

9. <span data-ttu-id="f7a3c-196">Selecione o **Gerenciador ArcSight (criptografado)** como o destino e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-196">Select the **ArcSight Manager (encrypted)** as the destination and click **Next**.</span></span>

10. <span data-ttu-id="f7a3c-197">Digite o IP/nome do host de destino no **Nome do Host do Gerente** e suas credenciais no formulário de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-197">Type in the destination IP/hostname in **Manager Hostname** and your credentials in the parameters form.</span></span> <span data-ttu-id="f7a3c-198">Todos os outros valores no formulário devem ser mantidos com os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-198">All other values in the form should be retained with the default values.</span></span> <span data-ttu-id="f7a3c-199">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-199">Click **Next**.</span></span>

11. <span data-ttu-id="f7a3c-200">Digite um nome para o conector no formulário de detalhes do conector.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-200">Type in a name for the connector in the connector details form.</span></span> <span data-ttu-id="f7a3c-201">Todos os outros valores no formulário são opcionais e podem ser deixados em branco.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-201">All other values in the form are optional and can be left blank.</span></span> <span data-ttu-id="f7a3c-202">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-202">Click **Next**.</span></span>

12. <span data-ttu-id="f7a3c-203">A janela de certificado de importação do Gerenciador de ESM é mostrada.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-203">The ESM Manager import certificate window is shown.</span></span> <span data-ttu-id="f7a3c-204">Selecione **Importar o certificado para conector do destino e** clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-204">Select **Import the certificate to connector from destination** and click **Next**.</span></span> <span data-ttu-id="f7a3c-205">A **janela Adicionar resumo do** conector é exibida e o certificado é importado.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-205">The **Add connector Summary** window is displayed and the certificate is imported.</span></span>

13. <span data-ttu-id="f7a3c-206">Verifique se os detalhes na janela Adicionar resumo **do** conector estão corretos e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-206">Verify that the details in the **Add connector Summary** window is correct, then click **Next**.</span></span>

14. <span data-ttu-id="f7a3c-207">Selecione **Instalar como um serviço e** clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-207">Select **Install as a service** and click **Next**.</span></span>

15. <span data-ttu-id="f7a3c-208">Digite um nome no campo **Nome Interno do** Serviço.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-208">Type a name in the **Service Internal Name** field.</span></span> <span data-ttu-id="f7a3c-209">Todos os outros valores no formulário podem ser mantidos com os valores padrão ou deixados em branco .</span><span class="sxs-lookup"><span data-stu-id="f7a3c-209">All other values in the form can be retained with the default values or left blank .</span></span> <span data-ttu-id="f7a3c-210">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-210">Click **Next**.</span></span>

16. <span data-ttu-id="f7a3c-211">Digite os parâmetros de serviço e clique em **Next**.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-211">Type in the service parameters and click **Next**.</span></span> <span data-ttu-id="f7a3c-212">Uma janela com o **Resumo do Serviço de Instalação** é mostrada.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-212">A window with the **Install Service Summary** is shown.</span></span> <span data-ttu-id="f7a3c-213">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-213">Click **Next**.</span></span>

17. <span data-ttu-id="f7a3c-214">Termine a instalação selecionando **Exit** e **Next.**</span><span class="sxs-lookup"><span data-stu-id="f7a3c-214">Finish the installation by selecting **Exit** and **Next**.</span></span>

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a><span data-ttu-id="f7a3c-215">Instalar e configurar o console ArcSight de Foco Micro</span><span class="sxs-lookup"><span data-stu-id="f7a3c-215">Install and configure the Micro Focus ArcSight console</span></span>

1. <span data-ttu-id="f7a3c-216">Siga o assistente de instalação pelas seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="f7a3c-216">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="f7a3c-217">Introdução</span><span class="sxs-lookup"><span data-stu-id="f7a3c-217">Introduction</span></span>
   - <span data-ttu-id="f7a3c-218">Contrato de Licença</span><span class="sxs-lookup"><span data-stu-id="f7a3c-218">License Agreement</span></span>
   - <span data-ttu-id="f7a3c-219">Aviso Especial</span><span class="sxs-lookup"><span data-stu-id="f7a3c-219">Special Notice</span></span>
   - <span data-ttu-id="f7a3c-220">Escolha Diretório de instalação arcSight</span><span class="sxs-lookup"><span data-stu-id="f7a3c-220">Choose ArcSight installation directory</span></span>
   - <span data-ttu-id="f7a3c-221">Escolha Pasta de Atalho</span><span class="sxs-lookup"><span data-stu-id="f7a3c-221">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="f7a3c-222">Resumo da pré-instalação</span><span class="sxs-lookup"><span data-stu-id="f7a3c-222">Pre-Installation Summary</span></span>

2. <span data-ttu-id="f7a3c-223">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-223">Click **Install**.</span></span> <span data-ttu-id="f7a3c-224">Após a conclusão da instalação, o Assistente de Configuração do Console ArcSight será aberto.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-224">After the installation completes, the ArcSight Console Configuration Wizard opens.</span></span>

3. <span data-ttu-id="f7a3c-225">Digite localhost no **Nome do Host do Gerente** e 8443 na Porta do **Gerente** e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-225">Type localhost in **Manager Host Name** and 8443 in **Manager Port** then click **Next**.</span></span>

4. <span data-ttu-id="f7a3c-226">Selecione **Usar conexão direta** e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-226">Select **Use direct connection**, then click **Next**.</span></span>

5. <span data-ttu-id="f7a3c-227">Selecione **Autenticação Baseada em Senha** e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-227">Select **Password Based Authentication**, then click **Next**.</span></span>

6. <span data-ttu-id="f7a3c-228">Selecione **Esta é uma única instalação do usuário. (Recomendado)**, em seguida, clique **em Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-228">Select **This is a single user installation. (Recommended)**, then click **Next**.</span></span>

7. <span data-ttu-id="f7a3c-229">Clique **em Feito** para sair do instalador.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-229">Click **Done** to quit the installer.</span></span>

8. <span data-ttu-id="f7a3c-230">Faça logon no console ArcSight de Foco Micro.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-230">Login to the Micro Focus ArcSight console.</span></span>

9. <span data-ttu-id="f7a3c-231">Navegue até **Active channel set** New  >  **Condition**  >    >  **Device Device Product**.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-231">Navigate to **Active channel set** > **New Condition** > **Device** > **Device Product**.</span></span>

10. <span data-ttu-id="f7a3c-232">Definir **Produto do Dispositivo = Microsoft Defender ATP**.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-232">Set **Device Product = Microsoft Defender ATP**.</span></span> <span data-ttu-id="f7a3c-233">Quando você verificar se os eventos estão fluindo para a ferramenta, pare o processo novamente e vá para o Windows Services e inicie o ARCSight FlexConnector REST.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-233">When you've verified that events are flowing to the tool, stop the process again and go to Windows Services and start the ArcSight FlexConnector REST.</span></span>

<span data-ttu-id="f7a3c-234">Agora você pode executar consultas no console Do Micro Focus ArcSight.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-234">You can now run queries in the Micro Focus ArcSight console.</span></span>

<span data-ttu-id="f7a3c-235">O Defender para detecções de ponto de extremidade aparecerá como eventos discretos, com "Microsoft" como o fornecedor e "Windows Defender ATP" como o nome do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-235">Defender for Endpoint detections will appear as discrete events, with "Microsoft” as the vendor and “Windows Defender ATP” as the device name.</span></span>


## <a name="troubleshooting-micro-focus-arcsight-connection"></a><span data-ttu-id="f7a3c-236">Solução de problemas da conexão Micro Focus ArcSight</span><span class="sxs-lookup"><span data-stu-id="f7a3c-236">Troubleshooting Micro Focus ArcSight connection</span></span>

<span data-ttu-id="f7a3c-237">**Problema:** Falha ao atualizar o token.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-237">**Problem:** Failed to refresh the token.</span></span> <span data-ttu-id="f7a3c-238">Você pode encontrar o log localizado em C: folder_location \current\logs onde folder_location representa o local onde \\ você instalou a ferramenta. </span><span class="sxs-lookup"><span data-stu-id="f7a3c-238">You can find the log located in C:\\*folder_location*\current\logs where *folder_location* represents the location where you installed the tool.</span></span> <span data-ttu-id="f7a3c-239">Abra _agent.log_ e procure `ERROR/FATAL/WARN` por .</span><span class="sxs-lookup"><span data-stu-id="f7a3c-239">Open _agent.log_ and look for `ERROR/FATAL/WARN`.</span></span>

<span data-ttu-id="f7a3c-240">**Sintoma:** Você recebeu a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="f7a3c-240">**Symptom:** You get the following error message:</span></span>

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

<span data-ttu-id="f7a3c-241">**Solução:**</span><span class="sxs-lookup"><span data-stu-id="f7a3c-241">**Solution:**</span></span>

1. <span data-ttu-id="f7a3c-242">Pare o processo clicando em Ctrl + C na janela Conector.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-242">Stop the process by clicking Ctrl + C on the Connector window.</span></span> <span data-ttu-id="f7a3c-243">Clique **em Y** quando perguntado "Encerrar o trabalho em lote Y/N?".</span><span class="sxs-lookup"><span data-stu-id="f7a3c-243">Click **Y** when asked "Terminate batch job Y/N?".</span></span>

2. <span data-ttu-id="f7a3c-244">Navegue até a pasta onde você armazenou o arquivo WDATP-connector.properties e edite-o para adicionar o seguinte valor: `reauthenticate=true` .</span><span class="sxs-lookup"><span data-stu-id="f7a3c-244">Navigate to the folder where you stored the WDATP-connector.properties file and edit it to add the following value: `reauthenticate=true`.</span></span>

3. <span data-ttu-id="f7a3c-245">Reinicie o conector executando o seguinte comando: `arcsight.bat connectors` .</span><span class="sxs-lookup"><span data-stu-id="f7a3c-245">Restart the connector by running the following command: `arcsight.bat connectors`.</span></span>

   <span data-ttu-id="f7a3c-246">Uma janela do navegador é exibida.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-246">A browser window appears.</span></span> <span data-ttu-id="f7a3c-247">Permita que ele seja executado, ele deve desaparecer e o conector agora deve estar em execução.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-247">Allow it to run, it should disappear, and the connector should now be running.</span></span>

> [!NOTE]
> <span data-ttu-id="f7a3c-248">Verifique se o conector está sendo executado interrompendo o processo novamente.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-248">Verify that the connector is running by stopping the process again.</span></span> <span data-ttu-id="f7a3c-249">Em seguida, inicie o conector novamente e nenhuma janela do navegador deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="f7a3c-249">Then start the connector again, and no browser window should appear.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f7a3c-250">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f7a3c-250">Related topics</span></span>
- [<span data-ttu-id="f7a3c-251">Habilitar a integração do SIEM no Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f7a3c-251">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="f7a3c-252">Pull detections to your SIEM tools</span><span class="sxs-lookup"><span data-stu-id="f7a3c-252">Pull detections to your SIEM tools</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [<span data-ttu-id="f7a3c-253">Pull Defender para detecções de ponto de extremidade usando a API REST</span><span class="sxs-lookup"><span data-stu-id="f7a3c-253">Pull Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="f7a3c-254">Solucionar problemas de integração de ferramentas SIEM</span><span class="sxs-lookup"><span data-stu-id="f7a3c-254">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
