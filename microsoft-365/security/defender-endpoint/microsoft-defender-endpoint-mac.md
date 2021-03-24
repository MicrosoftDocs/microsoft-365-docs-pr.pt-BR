---
title: Microsoft Defender ATP para Mac
ms.reviewer: ''
description: Saiba como instalar, configurar, atualizar e usar o Microsoft Defender para Ponto de Extremidade para Mac.
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 3e96cf09fd13a4d99546a1c18f9c61f40c362bf8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052731"
---
# <a name="microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="2ee11-104">Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="2ee11-104">Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2ee11-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2ee11-105">**Applies to:**</span></span>
- [<span data-ttu-id="2ee11-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2ee11-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="2ee11-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ee11-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2ee11-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="2ee11-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2ee11-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="2ee11-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="2ee11-110">Este tópico descreve como instalar, configurar, atualizar e usar o Defender para Ponto de Extremidade para Mac.</span><span class="sxs-lookup"><span data-stu-id="2ee11-110">This topic describes how to install, configure, update, and use Defender for Endpoint for Mac.</span></span>

> [!CAUTION]
> <span data-ttu-id="2ee11-111">A execução de outros produtos de proteção de ponto de extremidade de terceiros juntamente com o Defender for Endpoint para Mac provavelmente levará a problemas de desempenho e efeitos colaterais imprevisíveis.</span><span class="sxs-lookup"><span data-stu-id="2ee11-111">Running other third-party endpoint protection products alongside Defender for Endpoint for Mac is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="2ee11-112">Se a proteção de ponto de extremidade que não é da Microsoft for um requisito absoluto em seu ambiente, você ainda poderá aproveitar com segurança a funcionalidade MDATP para Mac EDR depois de configurar a funcionalidade de antivírus do MDATP para Mac para ser executado no modo [Passivo.](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="2ee11-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of MDATP for Mac EDR functionality after configuring MDATP for Mac antivirus functionality to run in [Passive mode](mac-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="whats-new-in-the-latest-release"></a><span data-ttu-id="2ee11-113">Novidades na versão mais recente</span><span class="sxs-lookup"><span data-stu-id="2ee11-113">What’s new in the latest release</span></span>

[<span data-ttu-id="2ee11-114">Novidades no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2ee11-114">What's new in Microsoft Defender for Endpoint</span></span>](whats-new-in-microsoft-defender-atp.md)

[<span data-ttu-id="2ee11-115">Novidades no Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="2ee11-115">What's new in Microsoft Defender for Endpoint for Mac</span></span>](mac-whatsnew.md)

> [!TIP]
> <span data-ttu-id="2ee11-116">Se você tiver algum comentário que gostaria de compartilhar, envie-o abrindo o Microsoft Defender para Ponto de Extremidade para Mac em seu dispositivo e navegando para Ajudar a  >  **enviar comentários.**</span><span class="sxs-lookup"><span data-stu-id="2ee11-116">If you have any feedback that you would like to share, submit it by opening Microsoft Defender for Endpoint for Mac on your device and navigating to **Help** > **Send feedback**.</span></span>

<span data-ttu-id="2ee11-117">Para obter os recursos mais recentes, incluindo recursos de visualização (como detecção de ponto de extremidade e resposta para seus dispositivos Mac), configure seu dispositivo macOS executando o Microsoft Defender para Ponto de Extremidade como um dispositivo "Insider".</span><span class="sxs-lookup"><span data-stu-id="2ee11-117">To get the latest features, including preview capabilities (such as endpoint detection and response for your Mac devices), configure your macOS device running Microsoft Defender for Endpoint to be an "Insider" device.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="2ee11-118">Como instalar o Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="2ee11-118">How to install Microsoft Defender for Endpoint for Mac</span></span>

### <a name="prerequisites"></a><span data-ttu-id="2ee11-119">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2ee11-119">Prerequisites</span></span>

- <span data-ttu-id="2ee11-120">Uma assinatura do Defender para Ponto de Extremidade e acesso ao portal do Centro de Segurança do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2ee11-120">A Defender for Endpoint subscription and access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="2ee11-121">Experiência de nível iniciante em scripts macOS e BASH</span><span class="sxs-lookup"><span data-stu-id="2ee11-121">Beginner-level experience in macOS and BASH scripting</span></span>
- <span data-ttu-id="2ee11-122">Privilégios administrativos no dispositivo (em caso de implantação manual)</span><span class="sxs-lookup"><span data-stu-id="2ee11-122">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="2ee11-123">Instruções de instalação</span><span class="sxs-lookup"><span data-stu-id="2ee11-123">Installation instructions</span></span>

<span data-ttu-id="2ee11-124">Há vários métodos e ferramentas de implantação que você pode usar para instalar e configurar o Defender para Ponto de Extremidade para Mac.</span><span class="sxs-lookup"><span data-stu-id="2ee11-124">There are several methods and deployment tools that you can use to install and configure Defender for Endpoint for Mac.</span></span>

- <span data-ttu-id="2ee11-125">Ferramentas de gerenciamento de terceiros:</span><span class="sxs-lookup"><span data-stu-id="2ee11-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="2ee11-126">Implantação baseada no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2ee11-126">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md)
    - [<span data-ttu-id="2ee11-127">Implantação baseada em JAMF</span><span class="sxs-lookup"><span data-stu-id="2ee11-127">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
    - [<span data-ttu-id="2ee11-128">Outros produtos MDM</span><span class="sxs-lookup"><span data-stu-id="2ee11-128">Other MDM products</span></span>](mac-install-with-other-mdm.md)

- <span data-ttu-id="2ee11-129">Ferramenta de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="2ee11-129">Command-line tool:</span></span>
    - [<span data-ttu-id="2ee11-130">Implantação manual</span><span class="sxs-lookup"><span data-stu-id="2ee11-130">Manual deployment</span></span>](mac-install-manually.md)

### <a name="system-requirements"></a><span data-ttu-id="2ee11-131">Requisitos do sistema</span><span class="sxs-lookup"><span data-stu-id="2ee11-131">System requirements</span></span>

<span data-ttu-id="2ee11-132">As três versões principais mais recentes do macOS são suportadas.</span><span class="sxs-lookup"><span data-stu-id="2ee11-132">The three most recent major releases of macOS are supported.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ee11-133">No macOS 11 (Big Sur), o Microsoft Defender para Endpoint requer perfis de configuração adicionais.</span><span class="sxs-lookup"><span data-stu-id="2ee11-133">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="2ee11-134">Se você for um cliente existente atualizando de versões anteriores do macOS, certifique-se de implantar os perfis de configuração adicionais listados em Novos perfis de configuração para [macOS Catalina](mac-sysext-policies.md)e versões mais recentes do macOS .</span><span class="sxs-lookup"><span data-stu-id="2ee11-134">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [New configuration profiles for macOS Catalina and newer versions of macOS](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ee11-135">O suporte para macOS 10.13 (High Sierra) será descontinuado em 15 de fevereiro de 2021.</span><span class="sxs-lookup"><span data-stu-id="2ee11-135">Support for macOS 10.13 (High Sierra) will be discontinued on February 15th, 2021.</span></span>

- <span data-ttu-id="2ee11-136">11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave), 10.13 (Alta Sierra)</span><span class="sxs-lookup"><span data-stu-id="2ee11-136">11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave), 10.13 (High Sierra)</span></span>
- <span data-ttu-id="2ee11-137">Espaço em disco: 1 GB</span><span class="sxs-lookup"><span data-stu-id="2ee11-137">Disk space: 1GB</span></span>

<span data-ttu-id="2ee11-138">Não há suporte para versões beta do macOS.</span><span class="sxs-lookup"><span data-stu-id="2ee11-138">Beta versions of macOS are not supported.</span></span>

<span data-ttu-id="2ee11-139">Depois de habilitar o serviço, talvez seja necessário configurar sua rede ou firewall para permitir conexões de saída entre ele e seus pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="2ee11-139">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="2ee11-140">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="2ee11-140">Licensing requirements</span></span>

<span data-ttu-id="2ee11-141">O Microsoft Defender para Ponto de Extremidade para Mac requer uma das seguintes ofertas de Licenciamento por Volume da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="2ee11-141">Microsoft Defender for Endpoint for Mac requires one of the following Microsoft Volume Licensing offers:</span></span>

- <span data-ttu-id="2ee11-142">Microsoft 365 E5 (M365 E5)</span><span class="sxs-lookup"><span data-stu-id="2ee11-142">Microsoft 365 E5 (M365 E5)</span></span>
- <span data-ttu-id="2ee11-143">Segurança do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="2ee11-143">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="2ee11-144">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="2ee11-144">Microsoft 365 A5 (M365 A5)</span></span>

> [!NOTE]
> <span data-ttu-id="2ee11-145">Os usuários licenciados qualificados podem usar o Microsoft Defender para Ponto de Extremidade em até cinco dispositivos simultâneos.</span><span class="sxs-lookup"><span data-stu-id="2ee11-145">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="2ee11-146">O Microsoft Defender para Ponto de Extremidade também está disponível para compra de um Provedor de Soluções na Nuvem (CSP).</span><span class="sxs-lookup"><span data-stu-id="2ee11-146">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span> <span data-ttu-id="2ee11-147">Quando comprado por meio de um CSP, ele não exige ofertas de Licenciamento por Volume da Microsoft listadas.</span><span class="sxs-lookup"><span data-stu-id="2ee11-147">When purchased via a CSP, it does not require Microsoft Volume Licensing offers listed.</span></span>

### <a name="network-connections"></a><span data-ttu-id="2ee11-148">Conexões de rede</span><span class="sxs-lookup"><span data-stu-id="2ee11-148">Network connections</span></span>

<span data-ttu-id="2ee11-149">A planilha baixável a seguir lista os serviços e as URLs associadas às quais sua rede deve ser capaz de se conectar.</span><span class="sxs-lookup"><span data-stu-id="2ee11-149">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="2ee11-150">Você deve garantir que não haja regras de filtragem de rede ou firewall que neguem o acesso *a* essas URLs, ou talvez seja necessário criar uma regra de autorização especificamente para elas.</span><span class="sxs-lookup"><span data-stu-id="2ee11-150">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>



|<span data-ttu-id="2ee11-151">**Planilha de lista de domínios**</span><span class="sxs-lookup"><span data-stu-id="2ee11-151">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="2ee11-152">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2ee11-152">**Description**</span></span>|
|:-----|:-----|
|![Imagem em miniatura da planilha URLs do Microsoft Defender para Endpoint](images/mdatp-urls.png)<br/>  | <span data-ttu-id="2ee11-154">Planilha de registros DNS específicos para locais de serviço, localizações geográficas e sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="2ee11-154">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br><span data-ttu-id="2ee11-155">Baixe a planilha aqui: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).</span><span class="sxs-lookup"><span data-stu-id="2ee11-155">Download the spreadsheet here: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).</span></span>

<span data-ttu-id="2ee11-156">O Microsoft Defender para Ponto de Extremidade pode descobrir um servidor proxy usando os seguintes métodos de descoberta:</span><span class="sxs-lookup"><span data-stu-id="2ee11-156">Microsoft Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="2ee11-157">Configuração automática de proxy (PAC)</span><span class="sxs-lookup"><span data-stu-id="2ee11-157">Proxy autoconfig (PAC)</span></span>
- <span data-ttu-id="2ee11-158">Protocolo de Descoberta Automática de Proxy da Web (WPAD)</span><span class="sxs-lookup"><span data-stu-id="2ee11-158">Web Proxy Autodiscovery Protocol (WPAD)</span></span>
- <span data-ttu-id="2ee11-159">Configuração de proxy estático manual</span><span class="sxs-lookup"><span data-stu-id="2ee11-159">Manual static proxy configuration</span></span>

<span data-ttu-id="2ee11-160">Se um proxy ou firewall estiver bloqueando o tráfego anônimo, certifique-se de que o tráfego anônimo seja permitido nas URLs listadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2ee11-160">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="2ee11-161">Proxies autenticados não são suportados.</span><span class="sxs-lookup"><span data-stu-id="2ee11-161">Authenticated proxies are not supported.</span></span> <span data-ttu-id="2ee11-162">Verifique se apenas PAC, WPAD ou um proxy estático estão sendo usados.</span><span class="sxs-lookup"><span data-stu-id="2ee11-162">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span>
>
> <span data-ttu-id="2ee11-163">Os proxies de inspeção e interceptação de SSL também não são suportados por motivos de segurança.</span><span class="sxs-lookup"><span data-stu-id="2ee11-163">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="2ee11-164">Configure uma exceção para a inspeção SSL e seu servidor proxy passar diretamente os dados do Microsoft Defender para o Ponto de Extremidade para Mac para as URLs relevantes sem interceptação.</span><span class="sxs-lookup"><span data-stu-id="2ee11-164">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint for Mac to the relevant URLs without interception.</span></span> <span data-ttu-id="2ee11-165">Adicionar seu certificado de interceptação ao armazenamento global não permitirá interceptação.</span><span class="sxs-lookup"><span data-stu-id="2ee11-165">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="2ee11-166">Para testar se uma conexão não está bloqueada, abra [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) e em um navegador.</span><span class="sxs-lookup"><span data-stu-id="2ee11-166">To test that a connection is not blocked, open [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) and [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) in a browser.</span></span>

<span data-ttu-id="2ee11-167">Se preferir a linha de comando, você também poderá verificar a conexão executando o seguinte comando no Terminal:</span><span class="sxs-lookup"><span data-stu-id="2ee11-167">If you prefer the command line, you can also check the connection by running the following command in Terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="2ee11-168">A saída deste comando deve ser semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="2ee11-168">The output from this command should be similar to the following:</span></span>

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> <span data-ttu-id="2ee11-169">Recomendamos que você mantenha [a Proteção de Integridade do Sistema](https://support.apple.com/en-us/HT204899) (SIP) habilitada em dispositivos cliente.</span><span class="sxs-lookup"><span data-stu-id="2ee11-169">We recommend that you keep [System Integrity Protection](https://support.apple.com/en-us/HT204899) (SIP) enabled on client devices.</span></span> <span data-ttu-id="2ee11-170">SIP é um recurso de segurança do macOS integrado que impede a adulteração de baixo nível no sistema operacional e é habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="2ee11-170">SIP is a built-in macOS security feature that prevents low-level tampering with the OS, and is enabled by default.</span></span>

<span data-ttu-id="2ee11-171">Depois que o Microsoft Defender for Endpoint estiver instalado, a conectividade poderá ser validada executando o seguinte comando no Terminal:</span><span class="sxs-lookup"><span data-stu-id="2ee11-171">Once Microsoft Defender for Endpoint is installed, connectivity can be validated by running the following command in Terminal:</span></span>
```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="2ee11-172">Como atualizar o Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="2ee11-172">How to update Microsoft Defender for Endpoint for Mac</span></span>

<span data-ttu-id="2ee11-173">A Microsoft publica regularmente atualizações de software para melhorar o desempenho, a segurança e fornecer novos recursos.</span><span class="sxs-lookup"><span data-stu-id="2ee11-173">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="2ee11-174">Para atualizar o Microsoft Defender para Ponto de Extremidade para Mac, um programa chamado Microsoft AutoUpdate (MAU) é usado.</span><span class="sxs-lookup"><span data-stu-id="2ee11-174">To update Microsoft Defender for Endpoint for Mac, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="2ee11-175">Para saber mais, consulte [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md).</span><span class="sxs-lookup"><span data-stu-id="2ee11-175">To learn more, see [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="2ee11-176">Como configurar o Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="2ee11-176">How to configure Microsoft Defender for Endpoint for Mac</span></span>

<span data-ttu-id="2ee11-177">As diretrizes sobre como configurar o produto em ambientes corporativos estão disponíveis em [Definir preferências](mac-preferences.md)do Microsoft Defender para Ponto de Extremidade para Mac .</span><span class="sxs-lookup"><span data-stu-id="2ee11-177">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

## <a name="macos-kernel-and-system-extensions"></a><span data-ttu-id="2ee11-178">Extensões do sistema e kernel do macOS</span><span class="sxs-lookup"><span data-stu-id="2ee11-178">macOS kernel and system extensions</span></span>

<span data-ttu-id="2ee11-179">Em alinhamento com a evolução do macOS, estamos preparando uma atualização do Microsoft Defender para Endpoint para Mac que aproveita extensões do sistema em vez de extensões de kernel.</span><span class="sxs-lookup"><span data-stu-id="2ee11-179">In alignment with macOS evolution, we are preparing a Microsoft Defender for Endpoint for Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="2ee11-180">Para obter detalhes relevantes, consulte [Novidades no Microsoft Defender para Ponto de Extremidade para Mac](mac-whatsnew.md).</span><span class="sxs-lookup"><span data-stu-id="2ee11-180">For relevant details, see [What's new in Microsoft Defender for Endpoint for Mac](mac-whatsnew.md).</span></span>

## <a name="resources"></a><span data-ttu-id="2ee11-181">Recursos</span><span class="sxs-lookup"><span data-stu-id="2ee11-181">Resources</span></span>

- <span data-ttu-id="2ee11-182">Para obter mais informações sobre log, desinstalação ou outros tópicos, consulte [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md).</span><span class="sxs-lookup"><span data-stu-id="2ee11-182">For more information about logging, uninstalling, or other topics, see [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md).</span></span>

- <span data-ttu-id="2ee11-183">[Privacidade do Microsoft Defender para Ponto de Extremidade para Mac](mac-privacy.md).</span><span class="sxs-lookup"><span data-stu-id="2ee11-183">[Privacy for Microsoft Defender for Endpoint for Mac](mac-privacy.md).</span></span>
