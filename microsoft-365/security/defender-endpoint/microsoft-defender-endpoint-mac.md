---
title: Microsoft Defender para Ponto de Extremidade no Mac
ms.reviewer: ''
description: Saiba como instalar, configurar, atualizar e usar o Microsoft Defender para Ponto de Extremidade no Mac.
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, big sur, catalina, mojave, mde for mac
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 705b1fffbc38282441f66e0dc411cf09699cb3f9
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903761"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="e494a-104">Microsoft Defender para Ponto de Extremidade no Mac</span><span class="sxs-lookup"><span data-stu-id="e494a-104">Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e494a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e494a-105">**Applies to:**</span></span>
- [<span data-ttu-id="e494a-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e494a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e494a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e494a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e494a-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="e494a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e494a-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="e494a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="e494a-110">Este tópico descreve como instalar, configurar, atualizar e usar o Defender para Ponto de Extremidade no Mac.</span><span class="sxs-lookup"><span data-stu-id="e494a-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Mac.</span></span>

> [!CAUTION]
> <span data-ttu-id="e494a-111">A execução de outros produtos de proteção de ponto de extremidade de terceiros juntamente com o Microsoft Defender para Ponto de Extremidade no Mac provavelmente levará a problemas de desempenho e efeitos colaterais imprevisíveis.</span><span class="sxs-lookup"><span data-stu-id="e494a-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Mac is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="e494a-112">Se a proteção de ponto de extremidade que não é da Microsoft for um requisito absoluto em seu ambiente, você ainda poderá aproveitar com segurança o Defender para o Ponto de Extremidade na funcionalidade do Mac EDR depois de configurar a funcionalidade antivírus para ser executado no modo [Passivo.](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="e494a-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Mac EDR functionality after configuring the antivirus functionality to run in [Passive mode](mac-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="whats-new-in-the-latest-release"></a><span data-ttu-id="e494a-113">Novidades na versão mais recente</span><span class="sxs-lookup"><span data-stu-id="e494a-113">What’s new in the latest release</span></span>

[<span data-ttu-id="e494a-114">Novidades no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e494a-114">What's new in Microsoft Defender for Endpoint</span></span>](whats-new-in-microsoft-defender-atp.md)

[<span data-ttu-id="e494a-115">Novidades do Microsoft Defender para Ponto de Extremidade no Mac</span><span class="sxs-lookup"><span data-stu-id="e494a-115">What's new in Microsoft Defender for Endpoint on Mac</span></span>](mac-whatsnew.md)

> [!TIP]
> <span data-ttu-id="e494a-116">Se você tiver algum comentário que gostaria de compartilhar, envie-o abrindo o Microsoft Defender para Ponto de Extremidade no Mac em seu dispositivo e navegando para Ajudar a  >  **enviar comentários.**</span><span class="sxs-lookup"><span data-stu-id="e494a-116">If you have any feedback that you would like to share, submit it by opening Microsoft Defender for Endpoint on Mac on your device and navigating to **Help** > **Send feedback**.</span></span>

<span data-ttu-id="e494a-117">Para obter os recursos mais recentes, incluindo recursos de visualização (como detecção de ponto de extremidade e resposta para seus dispositivos Mac), configure seu dispositivo macOS executando o Microsoft Defender para Ponto de Extremidade como um dispositivo "Insider".</span><span class="sxs-lookup"><span data-stu-id="e494a-117">To get the latest features, including preview capabilities (such as endpoint detection and response for your Mac devices), configure your macOS device running Microsoft Defender for Endpoint to be an "Insider" device.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="e494a-118">Como instalar o Microsoft Defender para Ponto de Extremidade no Mac</span><span class="sxs-lookup"><span data-stu-id="e494a-118">How to install Microsoft Defender for Endpoint on Mac</span></span>

### <a name="prerequisites"></a><span data-ttu-id="e494a-119">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e494a-119">Prerequisites</span></span>

- <span data-ttu-id="e494a-120">Uma assinatura do Defender para Ponto de Extremidade e acesso ao portal do Centro de Segurança do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e494a-120">A Defender for Endpoint subscription and access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="e494a-121">Experiência de nível iniciante em scripts macOS e BASH</span><span class="sxs-lookup"><span data-stu-id="e494a-121">Beginner-level experience in macOS and BASH scripting</span></span>
- <span data-ttu-id="e494a-122">Privilégios administrativos no dispositivo (em caso de implantação manual)</span><span class="sxs-lookup"><span data-stu-id="e494a-122">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="e494a-123">Instruções de instalação</span><span class="sxs-lookup"><span data-stu-id="e494a-123">Installation instructions</span></span>

<span data-ttu-id="e494a-124">Há vários métodos e ferramentas de implantação que você pode usar para instalar e configurar o Defender para Ponto de Extremidade no Mac.</span><span class="sxs-lookup"><span data-stu-id="e494a-124">There are several methods and deployment tools that you can use to install and configure Defender for Endpoint on Mac.</span></span>

- <span data-ttu-id="e494a-125">Ferramentas de gerenciamento de terceiros:</span><span class="sxs-lookup"><span data-stu-id="e494a-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="e494a-126">Implantação baseada no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e494a-126">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md)
    - [<span data-ttu-id="e494a-127">Implantação baseada em JAMF</span><span class="sxs-lookup"><span data-stu-id="e494a-127">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
    - [<span data-ttu-id="e494a-128">Outros produtos MDM</span><span class="sxs-lookup"><span data-stu-id="e494a-128">Other MDM products</span></span>](mac-install-with-other-mdm.md)

- <span data-ttu-id="e494a-129">Ferramenta de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="e494a-129">Command-line tool:</span></span>
    - [<span data-ttu-id="e494a-130">Implantação manual</span><span class="sxs-lookup"><span data-stu-id="e494a-130">Manual deployment</span></span>](mac-install-manually.md)

### <a name="system-requirements"></a><span data-ttu-id="e494a-131">Requisitos do sistema</span><span class="sxs-lookup"><span data-stu-id="e494a-131">System requirements</span></span>

<span data-ttu-id="e494a-132">As três versões principais mais recentes do macOS são suportadas.</span><span class="sxs-lookup"><span data-stu-id="e494a-132">The three most recent major releases of macOS are supported.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e494a-133">No macOS 11 (Big Sur), o Microsoft Defender para Endpoint requer perfis de configuração adicionais.</span><span class="sxs-lookup"><span data-stu-id="e494a-133">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="e494a-134">Se você for um cliente existente atualizando de versões anteriores do macOS, certifique-se de implantar os perfis de configuração adicionais listados em Novos perfis de configuração para [macOS Catalina](mac-sysext-policies.md)e versões mais recentes do macOS .</span><span class="sxs-lookup"><span data-stu-id="e494a-134">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [New configuration profiles for macOS Catalina and newer versions of macOS](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e494a-135">O suporte para macOS 10.13 (High Sierra) foi descontinuado a partir de 15 de fevereiro de 2021.</span><span class="sxs-lookup"><span data-stu-id="e494a-135">Support for macOS 10.13 (High Sierra) has been discontinued as of February 15th, 2021.</span></span>

- <span data-ttu-id="e494a-136">11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave)</span><span class="sxs-lookup"><span data-stu-id="e494a-136">11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave)</span></span>
- <span data-ttu-id="e494a-137">Espaço em disco: 1 GB</span><span class="sxs-lookup"><span data-stu-id="e494a-137">Disk space: 1GB</span></span>

<span data-ttu-id="e494a-138">Não há suporte para versões beta do macOS.</span><span class="sxs-lookup"><span data-stu-id="e494a-138">Beta versions of macOS are not supported.</span></span>

<span data-ttu-id="e494a-139">Não há suporte para dispositivos macOS com processadores M1.</span><span class="sxs-lookup"><span data-stu-id="e494a-139">macOS devices with M1 processors are not supported.</span></span>

<span data-ttu-id="e494a-140">Depois de habilitar o serviço, talvez seja necessário configurar sua rede ou firewall para permitir conexões de saída entre ele e seus pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="e494a-140">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="e494a-141">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="e494a-141">Licensing requirements</span></span>

<span data-ttu-id="e494a-142">O Microsoft Defender para Ponto de Extremidade no Mac requer uma das seguintes ofertas de Licenciamento por Volume da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="e494a-142">Microsoft Defender for Endpoint on Mac requires one of the following Microsoft Volume Licensing offers:</span></span>

- <span data-ttu-id="e494a-143">Microsoft 365 E5 (M365 E5)</span><span class="sxs-lookup"><span data-stu-id="e494a-143">Microsoft 365 E5 (M365 E5)</span></span>
- <span data-ttu-id="e494a-144">Segurança do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e494a-144">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="e494a-145">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="e494a-145">Microsoft 365 A5 (M365 A5)</span></span>

> [!NOTE]
> <span data-ttu-id="e494a-146">Os usuários licenciados qualificados podem usar o Microsoft Defender para Ponto de Extremidade em até cinco dispositivos simultâneos.</span><span class="sxs-lookup"><span data-stu-id="e494a-146">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="e494a-147">O Microsoft Defender para Ponto de Extremidade também está disponível para compra de um Provedor de Soluções na Nuvem (CSP).</span><span class="sxs-lookup"><span data-stu-id="e494a-147">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span> <span data-ttu-id="e494a-148">Quando comprado por meio de um CSP, ele não exige ofertas de Licenciamento por Volume da Microsoft listadas.</span><span class="sxs-lookup"><span data-stu-id="e494a-148">When purchased via a CSP, it does not require Microsoft Volume Licensing offers listed.</span></span>

### <a name="network-connections"></a><span data-ttu-id="e494a-149">Conexões de rede</span><span class="sxs-lookup"><span data-stu-id="e494a-149">Network connections</span></span>

<span data-ttu-id="e494a-150">A planilha baixável a seguir lista os serviços e as URLs associadas às quais sua rede deve ser capaz de se conectar.</span><span class="sxs-lookup"><span data-stu-id="e494a-150">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="e494a-151">Você deve garantir que não haja regras de filtragem de rede ou firewall que neguem o acesso *a* essas URLs, ou talvez seja necessário criar uma regra de autorização especificamente para elas.</span><span class="sxs-lookup"><span data-stu-id="e494a-151">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>



|<span data-ttu-id="e494a-152">**Planilha de lista de domínios**</span><span class="sxs-lookup"><span data-stu-id="e494a-152">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="e494a-153">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e494a-153">**Description**</span></span>|
|:-----|:-----|
|![Imagem em miniatura da planilha URLs do Microsoft Defender para Endpoint](images/mdatp-urls.png)<br/>  | <span data-ttu-id="e494a-155">Planilha de registros DNS específicos para locais de serviço, localizações geográficas e sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="e494a-155">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br><span data-ttu-id="e494a-156">Baixe a planilha aqui: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).</span><span class="sxs-lookup"><span data-stu-id="e494a-156">Download the spreadsheet here: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).</span></span>

<span data-ttu-id="e494a-157">O Microsoft Defender para Ponto de Extremidade pode descobrir um servidor proxy usando os seguintes métodos de descoberta:</span><span class="sxs-lookup"><span data-stu-id="e494a-157">Microsoft Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="e494a-158">Configuração automática de proxy (PAC)</span><span class="sxs-lookup"><span data-stu-id="e494a-158">Proxy autoconfig (PAC)</span></span>
- <span data-ttu-id="e494a-159">Protocolo de Descoberta Automática de Proxy da Web (WPAD)</span><span class="sxs-lookup"><span data-stu-id="e494a-159">Web Proxy Autodiscovery Protocol (WPAD)</span></span>
- <span data-ttu-id="e494a-160">Configuração de proxy estático manual</span><span class="sxs-lookup"><span data-stu-id="e494a-160">Manual static proxy configuration</span></span>

<span data-ttu-id="e494a-161">Se um proxy ou firewall estiver bloqueando o tráfego anônimo, certifique-se de que o tráfego anônimo seja permitido nas URLs listadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e494a-161">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="e494a-162">Proxies autenticados não são suportados.</span><span class="sxs-lookup"><span data-stu-id="e494a-162">Authenticated proxies are not supported.</span></span> <span data-ttu-id="e494a-163">Verifique se apenas PAC, WPAD ou um proxy estático estão sendo usados.</span><span class="sxs-lookup"><span data-stu-id="e494a-163">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span>
>
> <span data-ttu-id="e494a-164">Os proxies de inspeção e interceptação de SSL também não são suportados por motivos de segurança.</span><span class="sxs-lookup"><span data-stu-id="e494a-164">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="e494a-165">Configure uma exceção para a inspeção SSL e seu servidor proxy passar diretamente os dados do Microsoft Defender para o Ponto de Extremidade no macOS para as URLs relevantes sem interceptação.</span><span class="sxs-lookup"><span data-stu-id="e494a-165">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint on macOS to the relevant URLs without interception.</span></span> <span data-ttu-id="e494a-166">Adicionar seu certificado de interceptação ao armazenamento global não permitirá interceptação.</span><span class="sxs-lookup"><span data-stu-id="e494a-166">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="e494a-167">Para testar se uma conexão não está bloqueada, abra [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) e em um navegador.</span><span class="sxs-lookup"><span data-stu-id="e494a-167">To test that a connection is not blocked, open [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) and [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) in a browser.</span></span>

<span data-ttu-id="e494a-168">Se preferir a linha de comando, você também poderá verificar a conexão executando o seguinte comando no Terminal:</span><span class="sxs-lookup"><span data-stu-id="e494a-168">If you prefer the command line, you can also check the connection by running the following command in Terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="e494a-169">A saída deste comando deve ser semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="e494a-169">The output from this command should be similar to the following:</span></span>

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> <span data-ttu-id="e494a-170">Recomendamos que você mantenha [a Proteção de Integridade do Sistema](https://support.apple.com/en-us/HT204899) (SIP) habilitada em dispositivos cliente.</span><span class="sxs-lookup"><span data-stu-id="e494a-170">We recommend that you keep [System Integrity Protection](https://support.apple.com/en-us/HT204899) (SIP) enabled on client devices.</span></span> <span data-ttu-id="e494a-171">SIP é um recurso de segurança do macOS integrado que impede a adulteração de baixo nível no sistema operacional e é habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="e494a-171">SIP is a built-in macOS security feature that prevents low-level tampering with the OS, and is enabled by default.</span></span>

<span data-ttu-id="e494a-172">Depois que o Microsoft Defender for Endpoint estiver instalado, a conectividade poderá ser validada executando o seguinte comando no Terminal:</span><span class="sxs-lookup"><span data-stu-id="e494a-172">Once Microsoft Defender for Endpoint is installed, connectivity can be validated by running the following command in Terminal:</span></span>
```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="e494a-173">Como atualizar o Microsoft Defender para Ponto de Extremidade no Mac</span><span class="sxs-lookup"><span data-stu-id="e494a-173">How to update Microsoft Defender for Endpoint on Mac</span></span>

<span data-ttu-id="e494a-174">A Microsoft publica regularmente atualizações de software para melhorar o desempenho, a segurança e fornecer novos recursos.</span><span class="sxs-lookup"><span data-stu-id="e494a-174">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="e494a-175">Para atualizar o Microsoft Defender para Ponto de Extremidade no Mac, um programa chamado Microsoft AutoUpdate (MAU) é usado.</span><span class="sxs-lookup"><span data-stu-id="e494a-175">To update Microsoft Defender for Endpoint on Mac, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="e494a-176">Para saber mais, consulte [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span><span class="sxs-lookup"><span data-stu-id="e494a-176">To learn more, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="e494a-177">Como configurar o Microsoft Defender para Ponto de Extremidade no Mac</span><span class="sxs-lookup"><span data-stu-id="e494a-177">How to configure Microsoft Defender for Endpoint on Mac</span></span>

<span data-ttu-id="e494a-178">As diretrizes sobre como configurar o produto em ambientes corporativos estão disponíveis em [Definir preferências](mac-preferences.md)do Microsoft Defender para Ponto de Extremidade no Mac .</span><span class="sxs-lookup"><span data-stu-id="e494a-178">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Mac](mac-preferences.md).</span></span>

## <a name="macos-kernel-and-system-extensions"></a><span data-ttu-id="e494a-179">Extensões do sistema e kernel do macOS</span><span class="sxs-lookup"><span data-stu-id="e494a-179">macOS kernel and system extensions</span></span>

<span data-ttu-id="e494a-180">Em alinhamento com a evolução do macOS, estamos preparando um Microsoft Defender para Endpoint no Mac update que aproveita extensões do sistema em vez de extensões de kernel.</span><span class="sxs-lookup"><span data-stu-id="e494a-180">In alignment with macOS evolution, we are preparing a Microsoft Defender for Endpoint on Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="e494a-181">Para obter detalhes relevantes, consulte [Novidades no Microsoft Defender para Ponto de Extremidade no Mac](mac-whatsnew.md).</span><span class="sxs-lookup"><span data-stu-id="e494a-181">For relevant details, see [What's new in Microsoft Defender for Endpoint on Mac](mac-whatsnew.md).</span></span>

## <a name="resources"></a><span data-ttu-id="e494a-182">Recursos</span><span class="sxs-lookup"><span data-stu-id="e494a-182">Resources</span></span>

- <span data-ttu-id="e494a-183">Para obter mais informações sobre registro em log, desinstalação ou outros tópicos, consulte [Resources for Microsoft Defender for Endpoint on Mac](mac-resources.md).</span><span class="sxs-lookup"><span data-stu-id="e494a-183">For more information about logging, uninstalling, or other topics, see [Resources for Microsoft Defender for Endpoint on Mac](mac-resources.md).</span></span>

- <span data-ttu-id="e494a-184">[Privacidade do Microsoft Defender para Ponto de Extremidade no Mac](mac-privacy.md).</span><span class="sxs-lookup"><span data-stu-id="e494a-184">[Privacy for Microsoft Defender for Endpoint on Mac](mac-privacy.md).</span></span>
