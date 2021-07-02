---
title: Criar indicadores para arquivos
ms.reviewer: ''
description: Crie indicadores para um hash de arquivo que define a detecção, a prevenção e a exclusão de entidades.
keywords: file, hash, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
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
ms.openlocfilehash: b56a18e1b35b65629318ab29f2189ef1f73373f5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256910"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="ab479-104">Criar indicadores para arquivos</span><span class="sxs-lookup"><span data-stu-id="ab479-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ab479-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ab479-105">**Applies to:**</span></span>
- [<span data-ttu-id="ab479-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ab479-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ab479-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab479-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="ab479-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="ab479-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ab479-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="ab479-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="ab479-110">Impedir a propagação de um ataque em sua organização proibindo arquivos potencialmente mal-intencionados ou malwares suspeitos.</span><span class="sxs-lookup"><span data-stu-id="ab479-110">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="ab479-111">Se você conhecer um arquivo executável portátil potencialmente mal-intencionado (PE), poderá bloqueá-lo.</span><span class="sxs-lookup"><span data-stu-id="ab479-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="ab479-112">Essa operação impedirá que ela seja lida, escrita ou executada em dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ab479-112">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="ab479-113">Há três maneiras de criar indicadores para arquivos:</span><span class="sxs-lookup"><span data-stu-id="ab479-113">There are three ways you can create indicators for files:</span></span>

- <span data-ttu-id="ab479-114">Criando um indicador por meio da página de configurações</span><span class="sxs-lookup"><span data-stu-id="ab479-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="ab479-115">Criando um indicador contextual usando o botão adicionar indicador na página de detalhes do arquivo</span><span class="sxs-lookup"><span data-stu-id="ab479-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>
- <span data-ttu-id="ab479-116">Criando um indicador por meio da [API de indicador](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="ab479-116">By creating an indicator through the [Indicator API](ti-indicator.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ab479-117">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="ab479-117">Before you begin</span></span>

<span data-ttu-id="ab479-118">É importante entender os seguintes pré-requisitos antes da criação de indicadores para arquivos:</span><span class="sxs-lookup"><span data-stu-id="ab479-118">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="ab479-119">Esse recurso estará disponível se sua organização usar Microsoft Defender Antivírus **(no** modo ativo) e a proteção baseada em **nuvem estiver habilitada.**</span><span class="sxs-lookup"><span data-stu-id="ab479-119">This feature is available if your organization uses **Microsoft Defender Antivirus (in active mode)** and **Cloud-based protection is enabled**.</span></span> <span data-ttu-id="ab479-120">Para obter mais informações, consulte [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="ab479-120">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>

- <span data-ttu-id="ab479-121">A versão do cliente Antimalware deve ser 4.18.1901.x ou posterior.</span><span class="sxs-lookup"><span data-stu-id="ab479-121">The Antimalware client version must be 4.18.1901.x or later.</span></span> <span data-ttu-id="ab479-122">Consulte [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span><span class="sxs-lookup"><span data-stu-id="ab479-122">See [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span></span>

- <span data-ttu-id="ab479-123">Compatível com dispositivos com Windows 10, versão 1703 ou posterior, Windows Server 2016 e 2019.</span><span class="sxs-lookup"><span data-stu-id="ab479-123">Supported on devices with Windows 10, version 1703 or later, Windows Server 2016 and 2019.</span></span>

- <span data-ttu-id="ab479-124">Para começar a bloquear arquivos, primeiro você precisa ativar o recurso ["bloquear ou permitir"](advanced-features.md) no Configurações.</span><span class="sxs-lookup"><span data-stu-id="ab479-124">To start blocking files, you first need to [turn on the "block or allow" feature](advanced-features.md) in Settings.</span></span>

<span data-ttu-id="ab479-125">Esse recurso foi projetado para impedir que o malware suspeito (ou arquivos potencialmente mal-intencionados) seja baixado da Web.</span><span class="sxs-lookup"><span data-stu-id="ab479-125">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="ab479-126">Atualmente, ele dá suporte a arquivos pe (executáveis portáteis), incluindo arquivos .exe e .dll portáteis.</span><span class="sxs-lookup"><span data-stu-id="ab479-126">It currently supports portable executable (PE) files, including .exe and .dll files.</span></span> <span data-ttu-id="ab479-127">A cobertura será estendida ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="ab479-127">The coverage will be extended over time.</span></span>

## <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="ab479-128">Criar um indicador para arquivos na página de configurações</span><span class="sxs-lookup"><span data-stu-id="ab479-128">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="ab479-129">No painel de navegação, selecione Configurações > **Indicadores**.</span><span class="sxs-lookup"><span data-stu-id="ab479-129">In the navigation pane, select **Settings > Indicators**.</span></span>

2. <span data-ttu-id="ab479-130">Selecione a **guia Hash de**   arquivo.</span><span class="sxs-lookup"><span data-stu-id="ab479-130">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="ab479-131">Selecione **Adicionar indicador**.</span><span class="sxs-lookup"><span data-stu-id="ab479-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="ab479-132">Especifique os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="ab479-132">Specify the following details:</span></span>
    - <span data-ttu-id="ab479-133">Indicador - Especifique os detalhes da entidade e defina a expiração do indicador.</span><span class="sxs-lookup"><span data-stu-id="ab479-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
    - <span data-ttu-id="ab479-134">Ação - Especifique a ação a ser tomada e forneça uma descrição.</span><span class="sxs-lookup"><span data-stu-id="ab479-134">Action - Specify the action to be taken and provide a description.</span></span>
    - <span data-ttu-id="ab479-135">Escopo - Definir o escopo do grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ab479-135">Scope - Define the scope of the device group.</span></span>

5. <span data-ttu-id="ab479-136">Revise os detalhes na guia Resumo e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ab479-136">Review the details in the Summary tab, then select **Save**.</span></span>

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="ab479-137">Criar um indicador contextual na página de detalhes do arquivo</span><span class="sxs-lookup"><span data-stu-id="ab479-137">Create a contextual indicator from the file details page</span></span>

<span data-ttu-id="ab479-138">Uma das opções ao tomar ações [de resposta em um arquivo é](respond-file-alerts.md)adicionar um indicador para o   arquivo.</span><span class="sxs-lookup"><span data-stu-id="ab479-138">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> <span data-ttu-id="ab479-139">Quando você adiciona um hash de indicador para um arquivo, você pode optar por levantar um alerta e bloquear o arquivo sempre que um dispositivo em sua organização tentar execute-o.</span><span class="sxs-lookup"><span data-stu-id="ab479-139">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="ab479-140">Os arquivos bloqueados automaticamente por um indicador não aparecerão no Centro de Ações do arquivo, mas os alertas ainda estarão visíveis na fila alertas.</span><span class="sxs-lookup"><span data-stu-id="ab479-140">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="ab479-141">Normalmente, os blocos de arquivos são impostos e removidos em alguns minutos, mas podem levar mais de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="ab479-141">Typically, file blocks are enforced and removed within a couple of minutes, but can take upwards of 30 minutes.</span></span>
> 
>- <span data-ttu-id="ab479-142">Se houver políticas de IoC de arquivo conflitantes com o mesmo tipo de imposição e destino, a política do hash mais seguro será aplicada.</span><span class="sxs-lookup"><span data-stu-id="ab479-142">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure hash will be applied.</span></span> <span data-ttu-id="ab479-143">Uma política de IoC de hash de arquivo SHA-256 vencerá uma política de IoC de hash de arquivo SHA-1, que vencerá uma política de IoC de hash de arquivo MD5 se os tipos de hash definirem o mesmo arquivo.</span><span class="sxs-lookup"><span data-stu-id="ab479-143">An SHA-256 file hash IoC policy will win over an SHA-1 file hash IoC policy, which will win over an MD5 file hash IoC policy if the hash types define the same file.</span></span> <span data-ttu-id="ab479-144">Isso sempre é verdadeiro independentemente do grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ab479-144">This is always true regardless of the device group.</span></span> 
>   <span data-ttu-id="ab479-145">Em todos os outros casos, se as políticas de IoC de arquivo conflitantes com o mesmo destino de imposição são aplicadas a todos os dispositivos e ao grupo do dispositivo, em seguida, para um dispositivo, a política no grupo de dispositivos vencerá.</span><span class="sxs-lookup"><span data-stu-id="ab479-145">In all other cases, if conflicting file IoC policies with the same enforcement target are applied to all devices and to the device’s group, then for a device, the policy in the device group will win.</span></span> 
>   
>- <span data-ttu-id="ab479-146">Se a política de grupo EnableFileHashComputation estiver desabilitada, a precisão de bloqueio do IoC de arquivo será reduzida.</span><span class="sxs-lookup"><span data-stu-id="ab479-146">If the EnableFileHashComputation group policy is disabled, the blocking accuracy of the file IoC is reduced.</span></span> <span data-ttu-id="ab479-147">No entanto, a habilitação `EnableFileHashComputation` pode afetar o desempenho do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ab479-147">However, enabling `EnableFileHashComputation` may impact device performance.</span></span> <span data-ttu-id="ab479-148">Por exemplo, copiar arquivos grandes de um compartilhamento de rede em seu dispositivo local, especialmente em uma conexão VPN, pode ter um efeito no desempenho do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ab479-148">For example, copying large files from a network share onto your local device, especially over a VPN connection, might have an effect on device performance.</span></span>
>
>   <span data-ttu-id="ab479-149">Para obter mais informações sobre a política de grupo EnableFileHashComputation, consulte [Defender CSP](/windows/client-management/mdm/defender-csp)</span><span class="sxs-lookup"><span data-stu-id="ab479-149">For more information about the EnableFileHashComputation group policy, see [Defender CSP](/windows/client-management/mdm/defender-csp)</span></span>

## <a name="policy-conflict-handling"></a><span data-ttu-id="ab479-150">Tratamento de conflitos de política</span><span class="sxs-lookup"><span data-stu-id="ab479-150">Policy conflict handling</span></span>  

<span data-ttu-id="ab479-151">O conflito de tratamento de política de Certificado e IoC de arquivo seguirá a seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="ab479-151">Cert and File IoC policy handling conflict will follow the below order:</span></span>

- <span data-ttu-id="ab479-152">Se o arquivo não for permitido Windows Defender Controle de Aplicativo e AppLocker impor políticas/políticas de modo, **então Bloquear**</span><span class="sxs-lookup"><span data-stu-id="ab479-152">If the file is not allowed by Windows Defender Application Control and AppLocker enforce mode policy/policies, then **Block**</span></span>

- <span data-ttu-id="ab479-153">Se o arquivo for permitido pela exclusão Microsoft Defender Antivírus, **então Permitir**</span><span class="sxs-lookup"><span data-stu-id="ab479-153">Else if the file is allowed by the Microsoft Defender Antivirus exclusion, then **Allow**</span></span>

- <span data-ttu-id="ab479-154">Se o arquivo for bloqueado ou avisado por um IoC de arquivo de bloqueio ou aviso, **bloquear/avisar**</span><span class="sxs-lookup"><span data-stu-id="ab479-154">Else if the file is blocked or warned by a block or warn file IoC, then **Block/Warn**</span></span>

- <span data-ttu-id="ab479-155">Se o arquivo for permitido por uma política de IoC de arquivo permitido, **então Permitir**</span><span class="sxs-lookup"><span data-stu-id="ab479-155">Else if the file is allowed by an allow file IoC policy, then **Allow**</span></span>

- <span data-ttu-id="ab479-156">Senão, se o arquivo for bloqueado por regras ASR, CFA, AV, SmartScreen **e,** em seguida, Bloquear</span><span class="sxs-lookup"><span data-stu-id="ab479-156">Else if the file is blocked by ASR rules, CFA, AV, SmartScreen, then **Block**</span></span>  

- <span data-ttu-id="ab479-157">Else **Allow** (passa Windows Defender política de Controle de Aplicativo & AppLocker, nenhuma regra IoC se aplica a ela)</span><span class="sxs-lookup"><span data-stu-id="ab479-157">Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span></span>

<span data-ttu-id="ab479-158">Se houver políticas de IoC de arquivo conflitantes com o mesmo tipo de imposição e destino, a política do hash mais seguro (ou seja, mais longo) será aplicada.</span><span class="sxs-lookup"><span data-stu-id="ab479-158">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure (meaning longer) hash will be applied.</span></span> <span data-ttu-id="ab479-159">Por exemplo, uma política de IoC de hash de arquivo SHA-256 vencerá uma política de IoC de hash de arquivo MD5 se ambos os tipos de hash definirem o mesmo arquivo.</span><span class="sxs-lookup"><span data-stu-id="ab479-159">For example, an SHA-256 file hash IoC policy will win over an MD5 file hash IoC policy if both hash types define the same file.</span></span>

<span data-ttu-id="ab479-160">Os recursos Gerenciamento de Vulnerabilidades de aplicativo vulnerável usam os IoCs de arquivo para imposição e seguirão a ordem de tratamento de conflitos acima.</span><span class="sxs-lookup"><span data-stu-id="ab479-160">Threat and vulnerability management's block vulnerable application features uses the file IoCs for enforcement and will follow the above conflict handling order.</span></span>

### <a name="examples"></a><span data-ttu-id="ab479-161">Exemplos</span><span class="sxs-lookup"><span data-stu-id="ab479-161">Examples</span></span>

|<span data-ttu-id="ab479-162">Componente</span><span class="sxs-lookup"><span data-stu-id="ab479-162">Component</span></span> |<span data-ttu-id="ab479-163">Imposição de componentes</span><span class="sxs-lookup"><span data-stu-id="ab479-163">Component enforcement</span></span> |<span data-ttu-id="ab479-164">Ação do indicador de arquivo</span><span class="sxs-lookup"><span data-stu-id="ab479-164">File indicator Action</span></span> |<span data-ttu-id="ab479-165">Resultado</span><span class="sxs-lookup"><span data-stu-id="ab479-165">Result</span></span>
|--|--|--|--|
|<span data-ttu-id="ab479-166">Exclusão do caminho do arquivo de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="ab479-166">Attack surface reduction file path exclusion</span></span> |<span data-ttu-id="ab479-167">Permitir</span><span class="sxs-lookup"><span data-stu-id="ab479-167">Allow</span></span> |<span data-ttu-id="ab479-168">Bloquear</span><span class="sxs-lookup"><span data-stu-id="ab479-168">Block</span></span> |<span data-ttu-id="ab479-169">Bloquear</span><span class="sxs-lookup"><span data-stu-id="ab479-169">Block</span></span>
|<span data-ttu-id="ab479-170">Regra de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="ab479-170">Attack surface reduction rule</span></span> |<span data-ttu-id="ab479-171">Bloquear</span><span class="sxs-lookup"><span data-stu-id="ab479-171">Block</span></span> |<span data-ttu-id="ab479-172">Permitir</span><span class="sxs-lookup"><span data-stu-id="ab479-172">Allow</span></span> |<span data-ttu-id="ab479-173">Permitir</span><span class="sxs-lookup"><span data-stu-id="ab479-173">Allow</span></span>
|<span data-ttu-id="ab479-174">Controle de Aplicativos do Windows Defender</span><span class="sxs-lookup"><span data-stu-id="ab479-174">Windows Defender Application Control</span></span> |<span data-ttu-id="ab479-175">Permitir</span><span class="sxs-lookup"><span data-stu-id="ab479-175">Allow</span></span> |<span data-ttu-id="ab479-176">Bloquear</span><span class="sxs-lookup"><span data-stu-id="ab479-176">Block</span></span> |<span data-ttu-id="ab479-177">Permitir</span><span class="sxs-lookup"><span data-stu-id="ab479-177">Allow</span></span> |
|<span data-ttu-id="ab479-178">Controle de Aplicativos do Windows Defender</span><span class="sxs-lookup"><span data-stu-id="ab479-178">Windows Defender Application Control</span></span> |<span data-ttu-id="ab479-179">Bloquear</span><span class="sxs-lookup"><span data-stu-id="ab479-179">Block</span></span> |<span data-ttu-id="ab479-180">Permitir</span><span class="sxs-lookup"><span data-stu-id="ab479-180">Allow</span></span> |<span data-ttu-id="ab479-181">Bloquear</span><span class="sxs-lookup"><span data-stu-id="ab479-181">Block</span></span>
|<span data-ttu-id="ab479-182">Microsoft Defender Antivírus exclusão</span><span class="sxs-lookup"><span data-stu-id="ab479-182">Microsoft Defender Antivirus exclusion</span></span> |<span data-ttu-id="ab479-183">Permitir</span><span class="sxs-lookup"><span data-stu-id="ab479-183">Allow</span></span> |<span data-ttu-id="ab479-184">Bloquear</span><span class="sxs-lookup"><span data-stu-id="ab479-184">Block</span></span> |<span data-ttu-id="ab479-185">Permitir</span><span class="sxs-lookup"><span data-stu-id="ab479-185">Allow</span></span>

## <a name="see-also"></a><span data-ttu-id="ab479-186">Confira também</span><span class="sxs-lookup"><span data-stu-id="ab479-186">See also</span></span>

- [<span data-ttu-id="ab479-187">Criar indicadores</span><span class="sxs-lookup"><span data-stu-id="ab479-187">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="ab479-188">Criar indicadores para IPs e URLs/domínios</span><span class="sxs-lookup"><span data-stu-id="ab479-188">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="ab479-189">Criar indicadores com base em certificados</span><span class="sxs-lookup"><span data-stu-id="ab479-189">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="ab479-190">Gerenciar indicadores</span><span class="sxs-lookup"><span data-stu-id="ab479-190">Manage indicators</span></span>](indicator-manage.md)
