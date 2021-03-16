---
title: Usando a prevenção contra perda de dados do Ponto de extremidade
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Saiba como configurar as políticas de prevenção contra perda de dados (DLP) para usar os locais de prevenção contra perda de dados do Ponto de extremidade (EPDLP) do Microsoft 365.
ms.openlocfilehash: 1bb4013069b8f4890ba420f13a0203eb63973121
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "50820183"
---
# <a name="using-endpoint-data-loss-prevention"></a><span data-ttu-id="3b110-103">Usando a prevenção contra perda de dados do Endpoint</span><span class="sxs-lookup"><span data-stu-id="3b110-103">Using Endpoint data loss prevention</span></span>

<span data-ttu-id="3b110-104">Este artigo o conduz por três cenários em que você cria e modifica uma política DLP que usa dispositivos como um local.</span><span class="sxs-lookup"><span data-stu-id="3b110-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="3b110-105">Configurações de DLP</span><span class="sxs-lookup"><span data-stu-id="3b110-105">DLP settings</span></span>

<span data-ttu-id="3b110-106">Antes de começar, você deve configurar suas configurações de DLP, aplicadas a todas as políticas DLP para dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3b110-106">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices.</span></span> <span data-ttu-id="3b110-107">Você deve configurá-los se pretende criar políticas que impõem:</span><span class="sxs-lookup"><span data-stu-id="3b110-107">You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="3b110-108">restrições de saída de nuvem</span><span class="sxs-lookup"><span data-stu-id="3b110-108">cloud egress restrictions</span></span>
- <span data-ttu-id="3b110-109">restrições de aplicativos não permitidos</span><span class="sxs-lookup"><span data-stu-id="3b110-109">unallowed apps restrictions</span></span>

<span data-ttu-id="3b110-110">Ou</span><span class="sxs-lookup"><span data-stu-id="3b110-110">Or</span></span>

- <span data-ttu-id="3b110-111">Se você deseja excluir os caminhos de arquivo barulhentos do monitoramento</span><span class="sxs-lookup"><span data-stu-id="3b110-111">If you want to exclude noisy file paths from monitoring</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="3b110-112">![Configurações de DLP](../media/endpoint-dlp-1-using-dlp-settings.png)</span><span class="sxs-lookup"><span data-stu-id="3b110-112">![DLP settings](../media/endpoint-dlp-1-using-dlp-settings.png)</span></span>

### <a name="file-path-exclusions"></a><span data-ttu-id="3b110-113">Exclusões de caminho de arquivo</span><span class="sxs-lookup"><span data-stu-id="3b110-113">File path exclusions</span></span>

<span data-ttu-id="3b110-114">Talvez você queira excluir determinados caminhos de monitoramento DLP, alertas DLP e imposição de política de DLP em seus dispositivos porque eles são muito barulhentos ou não contêm arquivos nos quais você está interessado.</span><span class="sxs-lookup"><span data-stu-id="3b110-114">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in.</span></span> <span data-ttu-id="3b110-115">Os arquivos nesses locais não serão auditados e os arquivos criados ou modificados nesses locais não estarão sujeitos à imposição da política de DLP.</span><span class="sxs-lookup"><span data-stu-id="3b110-115">Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement.</span></span> <span data-ttu-id="3b110-116">Você pode configurar exclusões de caminho nas configurações DLP.</span><span class="sxs-lookup"><span data-stu-id="3b110-116">You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="3b110-117">Você pode usar essa lógica para construir seus caminhos de exclusão:</span><span class="sxs-lookup"><span data-stu-id="3b110-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="3b110-118">Caminho de arquivo válido que termina com "\", o que significa somente os arquivos da pasta.</span><span class="sxs-lookup"><span data-stu-id="3b110-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <br/><span data-ttu-id="3b110-119">Por exemplo: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="3b110-119">For example: C:\Temp</span></span>\

- <span data-ttu-id="3b110-120">Caminho de arquivo válido que termina com “\*”, o que significa somente os arquivos em subpastas, além dos arquivos diretamente na pasta.</span><span class="sxs-lookup"><span data-stu-id="3b110-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <br/><span data-ttu-id="3b110-121">Por exemplo: C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="3b110-121">For example: C:\Temp\*</span></span>

- <span data-ttu-id="3b110-122">Caminho de arquivo válido que termina com "\" ou “\*”, o que significa somente os arquivos da pasta e todas as subpastas.</span><span class="sxs-lookup"><span data-stu-id="3b110-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <br/><span data-ttu-id="3b110-123">Por exemplo: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="3b110-123">For example: C:\Temp</span></span>

- <span data-ttu-id="3b110-124">Um caminho com o curinga entre "\" de cada lado.</span><span class="sxs-lookup"><span data-stu-id="3b110-124">A path with wildcard between ‘\’ from each side.</span></span> <br/><span data-ttu-id="3b110-125">Por exemplo: C:\Users\*\Desktop</span><span class="sxs-lookup"><span data-stu-id="3b110-125">For example: C:\Users\*\Desktop</span></span>\

- <span data-ttu-id="3b110-126">Um caminho com curinga entre "\" de cada lado e com '(número)' para atribuir um número exato de subpastas.</span><span class="sxs-lookup"><span data-stu-id="3b110-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <br/><span data-ttu-id="3b110-127">Por exemplo: C:\Users\*(1) \Downloads</span><span class="sxs-lookup"><span data-stu-id="3b110-127">For example: C:\Users\*(1)\Downloads</span></span>\

- <span data-ttu-id="3b110-128">Um caminho com variáveis de ambiente do sistema.</span><span class="sxs-lookup"><span data-stu-id="3b110-128">A path with SYSTEM environment variables.</span></span> <br/><span data-ttu-id="3b110-129">Por exemplo: %SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="3b110-129">For example: %SystemDrive%\Test\*</span></span>

- <span data-ttu-id="3b110-130">Uma mistura de todas as acima.</span><span class="sxs-lookup"><span data-stu-id="3b110-130">A mix of all the above.</span></span> <br/><span data-ttu-id="3b110-131">Por exemplo: %SystemDrive%\Users\*\Documents\*(2)\Sub</span><span class="sxs-lookup"><span data-stu-id="3b110-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub</span></span>\

### <a name="unallowed-apps"></a><span data-ttu-id="3b110-132">Aplicativos não permitidos</span><span class="sxs-lookup"><span data-stu-id="3b110-132">Unallowed apps</span></span>

<span data-ttu-id="3b110-133">Quando a configuração de **Acesso a uma política por meio de aplicativos e navegadores não permitidos** estiver ativada e os usuários tentarem usar esses aplicativos para acessar um arquivo protegido, a atividade será permitida, bloqueada ou bloqueada, mas os usuários poderão substituir a restrição.</span><span class="sxs-lookup"><span data-stu-id="3b110-133">When a policy's **Access by unallowed apps and browsers** setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction.</span></span> <span data-ttu-id="3b110-134">Todas as atividades são auditadas e estão disponíveis para revisão no explorador de atividades.</span><span class="sxs-lookup"><span data-stu-id="3b110-134">All activity is audited and available to review in activity explorer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b110-135">Não inclua o caminho para o executável, apenas o nome do executável (por exemplo, browser.exe).</span><span class="sxs-lookup"><span data-stu-id="3b110-135">Do not include the path to the executable, but only the executable name (such as browser.exe).</span></span>


### <a name="browser-and-domain-restrictions"></a><span data-ttu-id="3b110-136">Restrições de navegador e domínio</span><span class="sxs-lookup"><span data-stu-id="3b110-136">Browser and domain restrictions</span></span>
<span data-ttu-id="3b110-137">Restringir arquivos confidenciais que correspondam a suas políticas contra domínios de serviço de nuvem irrestritos.</span><span class="sxs-lookup"><span data-stu-id="3b110-137">Restrict sensitive files that match your policies from being shared with unrestricted cloud service domains.</span></span>

#### <a name="service-domains"></a><span data-ttu-id="3b110-138">Domínios de serviço</span><span class="sxs-lookup"><span data-stu-id="3b110-138">Service domains</span></span>

<span data-ttu-id="3b110-139">É possível controlar se os arquivos confidenciais protegidos por suas políticas podem ser carregados para domínios de serviço específicos no Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="3b110-139">You can control whether sensitive files protected by your policies can be uploaded to specific service domains from Microsoft Edge.</span></span>

<span data-ttu-id="3b110-140">Se o modo de lista estiver definido como **Bloquear**, o usuário não poderá carregar itens confidenciais para esses domínios.</span><span class="sxs-lookup"><span data-stu-id="3b110-140">If the list mode is set to **Block**, then user will not be able to upload sensitive items to those domains.</span></span> <span data-ttu-id="3b110-141">Quando uma ação de carregamento é bloqueada porque um item corresponde a uma política DLP, a DLP gera um aviso ou bloqueia o carregamento do item confidenciais.</span><span class="sxs-lookup"><span data-stu-id="3b110-141">When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="3b110-142">Se o modo de lista estiver definido como **Permitir**, os usuários poderão fazer upload de itens confidenciais **_apenas_** para esses domínios, e o acesso de upload a todos os outros domínios não é permitido.</span><span class="sxs-lookup"><span data-stu-id="3b110-142">If the list mode is set to **Allow**, then users will be able to upload sensitive items **_only_** to those domains, and upload access to all other domains is not allowed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b110-143">Quando o modo de restrição de serviço é definido como "Permitir", você deve ter pelo menos um domínio de serviço configurado antes que as restrições sejam aplicadas.</span><span class="sxs-lookup"><span data-stu-id="3b110-143">When the service restriction mode is set to "Allow", you must have at least one service domain configured before restrictions are enforced.</span></span>

#### <a name="unallowed-browsers"></a><span data-ttu-id="3b110-144">Navegadores não permitidos</span><span class="sxs-lookup"><span data-stu-id="3b110-144">Unallowed browsers</span></span>

<span data-ttu-id="3b110-145">Adicione navegadores, identificados por seus nomes executáveis, que serão impedidos de acessar arquivos que correspondam às condições de uma política de DLP, em que a restrição de upload para serviços de nuvem está definida para bloquear ou para substituição de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="3b110-145">You add browsers, identified by their executable names, that will be blocked from accessing files that match the conditions of an enforced a DLP policy where the upload to cloud services restriction is set to block or block override.</span></span> <span data-ttu-id="3b110-146">Quando estes navegadores estiverem bloqueados de acessar um arquivo, os usuários finais verão uma notificação do sistema solicitando que eles abram o arquivo por meio do Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="3b110-146">When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>

### <a name="business-justification-in-policy-tips"></a><span data-ttu-id="3b110-147">Justificativa de negócios em dicas de política</span><span class="sxs-lookup"><span data-stu-id="3b110-147">Business justification in policy tips</span></span>

<span data-ttu-id="3b110-148">Você pode controlar como os usuários interagem com a opção de justificativa de negócios nas notificações de dica de política DLP.</span><span class="sxs-lookup"><span data-stu-id="3b110-148">You can control how users interact with the business justification option in DLP policy tip notifications.</span></span> <span data-ttu-id="3b110-149">Esta opção aparece quando os usuários realizam uma atividade protegida pela configuração **Bloquear com substituição** em uma política DLP.</span><span class="sxs-lookup"><span data-stu-id="3b110-149">This option appears when users perform an activity that's protected by the **Block with override** setting in a DLP policy.</span></span> <span data-ttu-id="3b110-150">Você pode escolher uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="3b110-150">You can choose from one the following options:</span></span>

- <span data-ttu-id="3b110-151">Por padrão, os usuários podem selecionar uma justificativa interna ou inserir seu próprio texto.</span><span class="sxs-lookup"><span data-stu-id="3b110-151">By default, users can select either a built-in justification, or enter their own text.</span></span>
- <span data-ttu-id="3b110-152">Os usuários podem selecionar apenas uma justificativa embutida.</span><span class="sxs-lookup"><span data-stu-id="3b110-152">Users can only select a built-in justification.</span></span>
- <span data-ttu-id="3b110-153">Os usuários só podem inserir sua própria justificativa.</span><span class="sxs-lookup"><span data-stu-id="3b110-153">Users can only enter their own justification.</span></span>


## <a name="tying-dlp-settings-together"></a><span data-ttu-id="3b110-154">Como ligar as configurações da DLP</span><span class="sxs-lookup"><span data-stu-id="3b110-154">Tying DLP settings together</span></span>

<span data-ttu-id="3b110-155">Com o Endpoint DPL e o navegador Edge Chromium, você pode restringir o compartilhamento não voluntariado de itens confidenciais a serviços e aplicativos na nuvem não permitidos.</span><span class="sxs-lookup"><span data-stu-id="3b110-155">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services.</span></span> <span data-ttu-id="3b110-156">Edge Chromium entende quando um item é restrito por uma política de Endpoint DLP e impõe restrições de acesso.</span><span class="sxs-lookup"><span data-stu-id="3b110-156">Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="3b110-157">Quando você usa o Endpoint DLP como um local em uma política DLP corretamente configurada e o navegador Edge Chromium, os navegadores não permitidos que você definiu nestas configurações serão impedidos de acessar os itens confidenciais que correspondem a seus controles de política de DLP.</span><span class="sxs-lookup"><span data-stu-id="3b110-157">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls.</span></span> <span data-ttu-id="3b110-158">Em vez disso, os usuários serão redirecionados para usar o Edge Chromium e o Edge Chromium, com o entendimento das restrições impõe a DLP, poderá bloquear ou restringir atividades quando as condições na política DLP forem atendidas.</span><span class="sxs-lookup"><span data-stu-id="3b110-158">Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="3b110-159">Para usar essa restrição, você precisará configurar três partes importantes:</span><span class="sxs-lookup"><span data-stu-id="3b110-159">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="3b110-160">Especifique os locais (serviços, domínios e endereços IP) que deseja impedir que os itens confidenciais sejam compartilhados.</span><span class="sxs-lookup"><span data-stu-id="3b110-160">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to.</span></span>

2. <span data-ttu-id="3b110-161">Adicione os navegadores que não têm permissão para acessar determinados itens confidenciais quando ocorre uma correspondência de política DLP.</span><span class="sxs-lookup"><span data-stu-id="3b110-161">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs.</span></span>

3. <span data-ttu-id="3b110-162">Configure as políticas DLP para definir os tipos de itens confidenciais para os quais o carregamento deve ser restrito a esses lugares, ativando **Carregar nos serviços de nuvem** e **Acesso a partir do navegador não permitido**.</span><span class="sxs-lookup"><span data-stu-id="3b110-162">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on **Upload to cloud services** and **Access from unallowed browser**.</span></span>

<span data-ttu-id="3b110-163">Você pode continuar a adicionar novos serviços, aplicativos e políticas para estender e aprimorar suas restrições para atender às suas necessidades de negócios e proteger dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="3b110-163">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="3b110-164">Essa configuração ajudará a garantir a segurança dos seus dados, além de evitar restrições desnecessárias, que impedem ou impedem que os usuários acessem e compartilhem itens não confidenciais.</span><span class="sxs-lookup"><span data-stu-id="3b110-164">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="3b110-165">Cenários de política do Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="3b110-165">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="3b110-166">Para ajudar você a se familiarizar com os recursos d Endpoint DLP e como eles são emergem nas políticas de DLP, juntamos alguns cenários que você pode seguir.</span><span class="sxs-lookup"><span data-stu-id="3b110-166">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b110-167">Esses cenários do Endpoint DLP não são os procedimentos oficiais para criar e ajustar as políticas DLP.</span><span class="sxs-lookup"><span data-stu-id="3b110-167">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="3b110-168">Confira os tópicos a seguir quando você precisar trabalhar com políticas de DLP em situações gerais:</span><span class="sxs-lookup"><span data-stu-id="3b110-168">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="3b110-169">Visão geral da prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="3b110-169">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
>- [<span data-ttu-id="3b110-170">Introdução à política DLP padrão</span><span class="sxs-lookup"><span data-stu-id="3b110-170">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="3b110-171">Criar uma política DLP a partir de um modelo</span><span class="sxs-lookup"><span data-stu-id="3b110-171">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="3b110-172">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="3b110-172">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="3b110-173">Cenário 1: Criar uma política a partir de um modelo, somente auditoria</span><span class="sxs-lookup"><span data-stu-id="3b110-173">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="3b110-174">Esses cenários exigem que você já tenha dispositivos integrados e relatados no Explorador de atividades.</span><span class="sxs-lookup"><span data-stu-id="3b110-174">These scenarios require that you already have devices onboarded and reporting into Activity explorer.</span></span> <span data-ttu-id="3b110-175">Se ainda não tiver integrado os dispositivos, confira [Introdução à prevenção contra perda de dados do Ponto de extremidade](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="3b110-175">If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="3b110-176">Abra a página [Prevenção contra perda de dados](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="3b110-176">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="3b110-177">Escolha **Criar política**.</span><span class="sxs-lookup"><span data-stu-id="3b110-177">Choose **Create policy**.</span></span>

3. <span data-ttu-id="3b110-178">Para esse cenário, escolha **Privacidade**, em seguida, **Dados de Informações de Identificação Pessoal (PII) dos EUA** e escolha **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3b110-178">For this scenario, choose **Privacy**, then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>

4. <span data-ttu-id="3b110-179">Alterne o campo **Status** para desativado em todos os locais, exceto os **Dispositivos**. </span><span class="sxs-lookup"><span data-stu-id="3b110-179">Toggle the **Status** field to off for all locations except **Devices**.</span></span> <span data-ttu-id="3b110-180">Escolha **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3b110-180">Choose **Next**.</span></span>

5. <span data-ttu-id="3b110-181">Aceite a seleção padrão **Revisar e personalizar as configurações do modelo** e escolha **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3b110-181">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>

6. <span data-ttu-id="3b110-182">Aceite os valores padrão de **Ações de proteção** e escolha **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3b110-182">Accept the default **Protection actions** values and choose **Next**.</span></span>

7. <span data-ttu-id="3b110-183">Selecione **Auditoria ou restringir atividades em dispositivos de Windows** e deixe as ações definidas como **Somente auditar**.</span><span class="sxs-lookup"><span data-stu-id="3b110-183">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**.</span></span> <span data-ttu-id="3b110-184">Escolha **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3b110-184">Choose **Next**.</span></span>

8. <span data-ttu-id="3b110-185">Aceite o valor padrão **Eu quero testá-lo primeiro** e escolha **Mostrar dicas de política enquanto estiver no modo de teste**.</span><span class="sxs-lookup"><span data-stu-id="3b110-185">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**.</span></span> <span data-ttu-id="3b110-186">Escolha **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3b110-186">Choose **Next**.</span></span>

9. <span data-ttu-id="3b110-187">Examine as configurações e escolha **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="3b110-187">Review your settings and choose **Submit**.</span></span>

10. <span data-ttu-id="3b110-188">A nova política DLP será exibida na lista de políticas.</span><span class="sxs-lookup"><span data-stu-id="3b110-188">The new DLP policy will appear in the policy list.</span></span>

11. <span data-ttu-id="3b110-189">Verificar o Explorador de atividade para obter pontos de extremidade monitorados.</span><span class="sxs-lookup"><span data-stu-id="3b110-189">Check Activity explorer for data from the monitored endpoints.</span></span> <span data-ttu-id="3b110-190">Defina o filtro local para dispositivos e adicione a política, em seguida, filtre por nome da política para ver o impacto dessa política.</span><span class="sxs-lookup"><span data-stu-id="3b110-190">Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy.</span></span> <span data-ttu-id="3b110-191">Confira [Começar a usar o explorador de atividades](data-classification-activity-explorer.md) se necessário.</span><span class="sxs-lookup"><span data-stu-id="3b110-191">See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>

12. <span data-ttu-id="3b110-192">Tentativa de compartilhar um teste contendo conteúdo que disparará a Condição de Dados de Informações de Identificação Pessoal (PII) dos EUA com alguém fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="3b110-192">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="3b110-193">Isso deve desencadear a política.</span><span class="sxs-lookup"><span data-stu-id="3b110-193">This should trigger the policy.</span></span>

13. <span data-ttu-id="3b110-194">Verifique o Explorador de atividades para obter o evento.</span><span class="sxs-lookup"><span data-stu-id="3b110-194">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="3b110-195">Cenário 2: Modificar a política existente, definir um alerta</span><span class="sxs-lookup"><span data-stu-id="3b110-195">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="3b110-196">Abra a página [Prevenção de perda de dados](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="3b110-196">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="3b110-197">Escolha as políticas de **Dados de Informações de Identificação Pessoal (PII) dos EUA** criadas cenário 1.</span><span class="sxs-lookup"><span data-stu-id="3b110-197">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="3b110-198">Escolha **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="3b110-198">Choose **edit policy**.</span></span>

4. <span data-ttu-id="3b110-199">Vá para a página **Regras avançadas de DLP** e edite o **Baixo volume de conteúdo detectado nas Informações de Identificação Pessoal dos EUA**.</span><span class="sxs-lookup"><span data-stu-id="3b110-199">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="3b110-200">Role para baixo até a seção **Relatório de incidentes** e configure **Envie um alerta para administradores quando uma correspondência de regra ocorrer** para **No**.</span><span class="sxs-lookup"><span data-stu-id="3b110-200">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**.</span></span> <span data-ttu-id="3b110-201">Os alertas de email serão enviados automaticamente para o administrador e qualquer pessoa que você adicionar à lista de destinatários.</span><span class="sxs-lookup"><span data-stu-id="3b110-201">Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3b110-202">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="3b110-202">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
   
6. <span data-ttu-id="3b110-203">Para fins deste cenário, escolha **Enviar alerta sempre que uma atividade corresponder à regra**.</span><span class="sxs-lookup"><span data-stu-id="3b110-203">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>

7. <span data-ttu-id="3b110-204">Escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3b110-204">Choose **Save**.</span></span>

8. <span data-ttu-id="3b110-205">Mantenha todas as suas configurações anteriores escolhendo **Próximo** e **Enviar** as alterações de política.</span><span class="sxs-lookup"><span data-stu-id="3b110-205">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="3b110-206">Tentativa de compartilhar um teste contendo conteúdo que disparará a Condição de Dados de Informações de Identificação Pessoal (PII) dos EUA com alguém fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="3b110-206">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="3b110-207">Isso deve desencadear a política.</span><span class="sxs-lookup"><span data-stu-id="3b110-207">This should trigger the policy.</span></span>

10. <span data-ttu-id="3b110-208">Verifique o Explorador de atividades para obter o evento.</span><span class="sxs-lookup"><span data-stu-id="3b110-208">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="3b110-209">Cenário 3: Modificar a política existente, bloquear a ação com permitir substituição</span><span class="sxs-lookup"><span data-stu-id="3b110-209">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="3b110-210">Abra a página [Prevenção de perda de dados](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="3b110-210">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="3b110-211">Escolha as políticas de **Dados de Informações de Identificação Pessoal (PII) dos EUA** criadas cenário 1.</span><span class="sxs-lookup"><span data-stu-id="3b110-211">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="3b110-212">Escolha **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="3b110-212">Choose **edit policy**.</span></span>

4. <span data-ttu-id="3b110-213">Vá para a página **Regras avançadas de DLP** e edite o **Baixo volume de conteúdo detectado nas Informações de Identificação Pessoal dos EUA**.</span><span class="sxs-lookup"><span data-stu-id="3b110-213">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="3b110-214">Role a tela para baixo até a seção **Auditoria ou restringir atividades nos dispositivos do Windows** e para cada atividade defina a ação correspondente para **Bloquear com substituir**.</span><span class="sxs-lookup"><span data-stu-id="3b110-214">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3b110-215">![definir o bloco com substituir ação](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="3b110-215">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
   
6. <span data-ttu-id="3b110-216">Escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3b110-216">Choose **Save**.</span></span>

7. <span data-ttu-id="3b110-217">Repita as etapas 4-7 para o **Alto volume de conteúdo detectado nas Informações de Identificação Pessoal dos EUA**.</span><span class="sxs-lookup"><span data-stu-id="3b110-217">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>

8. <span data-ttu-id="3b110-218">Mantenha todas as suas configurações anteriores escolhendo **Próximo** e **Enviar** as alterações de política.</span><span class="sxs-lookup"><span data-stu-id="3b110-218">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="3b110-219">Tentativa de compartilhar um teste contendo conteúdo que disparará a Condição de Dados de Informações de Identificação Pessoal (PII) dos EUA com alguém fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="3b110-219">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="3b110-220">Isso deve desencadear a política.</span><span class="sxs-lookup"><span data-stu-id="3b110-220">This should trigger the policy.</span></span>

   <span data-ttu-id="3b110-221">Você verá um pop-up assim no dispositivo do cliente:</span><span class="sxs-lookup"><span data-stu-id="3b110-221">You'll see a popup like this on the client device:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3b110-222">![cliente dlp do ponto de extremidade bloqueado na notificação de substituição](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span><span class="sxs-lookup"><span data-stu-id="3b110-222">![endpoint dlp client blocked override notification](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span></span>

10. <span data-ttu-id="3b110-223">Verifique o Explorador de atividades para obter o evento.</span><span class="sxs-lookup"><span data-stu-id="3b110-223">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b110-224">Confira também</span><span class="sxs-lookup"><span data-stu-id="3b110-224">See also</span></span>

- [<span data-ttu-id="3b110-225">Saiba mais sobre a Prevenção contra perda de dados do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="3b110-225">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="3b110-226">Introdução à Prevenção contra perda de dados do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="3b110-226">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="3b110-227">Visão geral da prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="3b110-227">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="3b110-228">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="3b110-228">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="3b110-229">Começar a usar o Explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="3b110-229">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="3b110-230">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="3b110-230">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="3b110-231">Ferramentas e métodos de integração para computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="3b110-231">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="3b110-232">Assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3b110-232">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="3b110-233">Associados a Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="3b110-233">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="3b110-234">Baixar o novo Microsoft Edge baseado em Chromium</span><span class="sxs-lookup"><span data-stu-id="3b110-234">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [<span data-ttu-id="3b110-235">Introdução à política DLP padrão</span><span class="sxs-lookup"><span data-stu-id="3b110-235">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="3b110-236">Criar uma política DLP a partir de um modelo</span><span class="sxs-lookup"><span data-stu-id="3b110-236">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
