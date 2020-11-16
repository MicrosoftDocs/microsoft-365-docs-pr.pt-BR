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
ms.openlocfilehash: 64cdfeab4b527dd3b84e7586d1419e5bf8b383df
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073100"
---
# <a name="using-endpoint-data-loss-prevention"></a><span data-ttu-id="508b2-103">Usando a prevenção contra perda de dados do Endpoint</span><span class="sxs-lookup"><span data-stu-id="508b2-103">Using Endpoint data loss prevention</span></span>

<span data-ttu-id="508b2-104">Este artigo o conduz por três cenários em que você cria e modifica uma política DLP que usa dispositivos como um local.</span><span class="sxs-lookup"><span data-stu-id="508b2-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="508b2-105">Configurações de DLP</span><span class="sxs-lookup"><span data-stu-id="508b2-105">DLP settings</span></span>

<span data-ttu-id="508b2-p101">Antes de começar, defina suas configurações de DLP, aplicadas a todas as políticas DLP para dispositivos. Configure-as se pretende criar políticas que impõem:</span><span class="sxs-lookup"><span data-stu-id="508b2-p101">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices. You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="508b2-108">restrições de saída de nuvem</span><span class="sxs-lookup"><span data-stu-id="508b2-108">cloud egress restrictions</span></span>
- <span data-ttu-id="508b2-109">restrições de aplicativos não permitidos</span><span class="sxs-lookup"><span data-stu-id="508b2-109">unallowed apps restrictions</span></span>

<span data-ttu-id="508b2-110">Ou</span><span class="sxs-lookup"><span data-stu-id="508b2-110">Or</span></span>

- <span data-ttu-id="508b2-111">Se você deseja excluir os caminhos de arquivo barulhentos do monitoramento</span><span class="sxs-lookup"><span data-stu-id="508b2-111">If you want to exclude noisy file paths from monitoring</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="508b2-112">![Configurações de DLP](../media/endpoint-dlp-1-using-dlp-settings.png)</span><span class="sxs-lookup"><span data-stu-id="508b2-112">![DLP settings](../media/endpoint-dlp-1-using-dlp-settings.png)</span></span>

### <a name="file-path-exclusions"></a><span data-ttu-id="508b2-113">Exclusões de caminho de arquivo</span><span class="sxs-lookup"><span data-stu-id="508b2-113">File path exclusions</span></span>

<span data-ttu-id="508b2-p102">Talvez você queira excluir certos caminhos do monitoramento DLP, alertas DLP e aplicações de política DLP de seus dispositivos porque eles são muito ruidosos ou não contêm arquivos de seu interesse. Os arquivos nesses locais não serão auditados e todos os arquivos criados ou modificados nesses locais não estarão sujeitos à aplicação da política DLP. É possível configurar exclusões de caminho nas configurações de DLP.</span><span class="sxs-lookup"><span data-stu-id="508b2-p102">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in. Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement. You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="508b2-117">Use essa lógica para construir seus caminhos de exclusão:</span><span class="sxs-lookup"><span data-stu-id="508b2-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="508b2-118">Caminho de arquivo válido que termina com "\", o que significa somente os arquivos da pasta.</span><span class="sxs-lookup"><span data-stu-id="508b2-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <br/><span data-ttu-id="508b2-119">Por exemplo: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="508b2-119">For example: C:\Temp</span></span>\

- <span data-ttu-id="508b2-120">Caminho de arquivo válido que termina com “\*”, o que significa somente os arquivos em subpastas, além dos arquivos diretamente na pasta.</span><span class="sxs-lookup"><span data-stu-id="508b2-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <br/><span data-ttu-id="508b2-121">Por exemplo: C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="508b2-121">For example: C:\Temp\*</span></span>

- <span data-ttu-id="508b2-122">Caminho de arquivo válido que termina com "\" ou “\*”, o que significa somente os arquivos da pasta e todas as subpastas.</span><span class="sxs-lookup"><span data-stu-id="508b2-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <br/><span data-ttu-id="508b2-123">Por exemplo: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="508b2-123">For example: C:\Temp</span></span>

- <span data-ttu-id="508b2-124">Um caminho com o curinga entre "\" de cada lado.</span><span class="sxs-lookup"><span data-stu-id="508b2-124">A path with wildcard between ‘\’ from each side.</span></span> <br/><span data-ttu-id="508b2-125">Por exemplo: C:\Users\*\Desktop</span><span class="sxs-lookup"><span data-stu-id="508b2-125">For example: C:\Users\*\Desktop</span></span>\

- <span data-ttu-id="508b2-126">Um caminho com curinga entre "\" de cada lado e com '(número)' para atribuir um número exato de subpastas.</span><span class="sxs-lookup"><span data-stu-id="508b2-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <br/><span data-ttu-id="508b2-127">Por exemplo: C:\Users\*(1) \Downloads</span><span class="sxs-lookup"><span data-stu-id="508b2-127">For example: C:\Users\*(1)\Downloads</span></span>\

- <span data-ttu-id="508b2-128">Um caminho com variáveis de ambiente do sistema.</span><span class="sxs-lookup"><span data-stu-id="508b2-128">A path with SYSTEM environment variables.</span></span> <br/><span data-ttu-id="508b2-129">Por exemplo: %SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="508b2-129">For example: %SystemDrive%\Test\*</span></span>

- <span data-ttu-id="508b2-130">Uma mistura de todas as acima.</span><span class="sxs-lookup"><span data-stu-id="508b2-130">A mix of all the above.</span></span> <br/><span data-ttu-id="508b2-131">Por exemplo: %SystemDrive%\Users\*\Documents\*(2)\Sub</span><span class="sxs-lookup"><span data-stu-id="508b2-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub</span></span>\

### <a name="service-domains"></a><span data-ttu-id="508b2-132">Domínios de serviço</span><span class="sxs-lookup"><span data-stu-id="508b2-132">Service domains</span></span>

<span data-ttu-id="508b2-133">Adicione domínios a esta lista aos quais o Edge Chromium se referirá ao aplicar a restrição de acesso de carregamento na nuvem da política DLP de Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="508b2-133">You can add domains to this list that Edge Chromium will refer to when enforcing the Endpoint DLP policy cloud upload access restriction.</span></span> 

<span data-ttu-id="508b2-p103">Se o modo de lista for definido como **Bloquear** , o usuário não poderá carregar itens confidenciais para esses domínios. Quando uma ação de carregamento for bloqueada devido a um item corresponde a uma política DLP, a DLP irá gerar um aviso ou bloqueará o carregamento do item confidencial.</span><span class="sxs-lookup"><span data-stu-id="508b2-p103">If the list mode is set to **Block** , then user will not be able to upload sensitive items to those domains. When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="508b2-136">Se o modo de lista estiver definido como **Permitir** , os usuários poderão carregar itens confidenciais \* *_apenas_* _ a esses domínios, e carregar o acesso a todos os outros domínios não será permitido.</span><span class="sxs-lookup"><span data-stu-id="508b2-136">If the list mode is set to **Allow** , then users will be able to upload sensitive items \* *_only_* _ to those domains, and upload access to all other domains is not allowed.</span></span>

### <a name="unallowed-apps"></a><span data-ttu-id="508b2-137">Aplicativos não permitidos</span><span class="sxs-lookup"><span data-stu-id="508b2-137">Unallowed apps</span></span>

<span data-ttu-id="508b2-p104">Quando a configuração de _ *Acesso por navegadores e aplicativos não permitidos* \* de uma política estiver ativada e os usuários tentarem usar esses aplicativos para acessar um arquivo protegido, a atividade será permitida ou bloqueada, ou bloqueada com os usuários podendo ignorar a restrição. Todas as atividades são auditadas e disponibilizadas para revisão no explorador de atividades.</span><span class="sxs-lookup"><span data-stu-id="508b2-p104">When a policy's _ *Access by unallowed apps and browsers* \* setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction. All activity is audited and available to review in activity explorer.</span></span>

### <a name="unallowed-browsers"></a><span data-ttu-id="508b2-140">Navegadores não permitidos</span><span class="sxs-lookup"><span data-stu-id="508b2-140">Unallowed browsers</span></span>

<span data-ttu-id="508b2-p105">Adicione navegadores, identificados por seus nomes executáveis, que serão impedidos de acessar arquivos que correspondam às condições de uma política DLP aplicada quando a restrição de carregamento para serviços em nuvem estiver definida para bloquear ou ignorar o bloqueio. Quando esses navegadores são impedidos de acessar um arquivo, os usuários finais verão uma notificação do sistema solicitando que abram o arquivo através do Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="508b2-p105">You add browsers, identified by their executable names, that will be blocked from accessing files that match the conditions of an enforced a DLP policy where the upload to cloud services restriction is set to block or block override. When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>

[!IMPORTANT]
<span data-ttu-id="508b2-143">Não inclua o caminho para o executável, apenas o nome do executável (por exemplo, browser.exe).</span><span class="sxs-lookup"><span data-stu-id="508b2-143">Do not include the path to the executable, but only the executable name (i.e., browser.exe).</span></span>

## <a name="tying-dlp-settings-together"></a><span data-ttu-id="508b2-144">Como ligar as configurações de DLP</span><span class="sxs-lookup"><span data-stu-id="508b2-144">Tying DLP settings together</span></span>

<span data-ttu-id="508b2-p106">Com a DLP de Ponto de Extremidade e o navegador da Web Edge Chromium, restrinja o compartilhamento não intencional de itens confidenciais a aplicativos e serviços em nuvem não permitidos. O Edge Chromium entende quando um item é restringido por uma política DLP de Ponto de Extremidade e impõe restrições de acesso.</span><span class="sxs-lookup"><span data-stu-id="508b2-p106">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services. Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="508b2-p107">Ao usar a DLP de Ponto de Extremidade, como um local em uma política DLP configurada corretamente, e o navegador Edge Chromium, os navegadores não permitidos definidos nessas configurações serão impedidos de acessar os itens confidenciais que correspondem aos seus controles de política DLP. Em vez disso, os usuários serão redirecionados para usar o Edge Chromium, que com o entendimento das restrições impostas pela DLP, poderá bloquear ou restringir atividades quando as condições da política de DLP forem atendidas.</span><span class="sxs-lookup"><span data-stu-id="508b2-p107">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls. Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="508b2-149">Para usar essa restrição, será necessário configurar três partes importantes:</span><span class="sxs-lookup"><span data-stu-id="508b2-149">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="508b2-150">Especifique os locais (serviços, domínios e endereços IP) que deseja impedir que os itens confidenciais sejam compartilhados.</span><span class="sxs-lookup"><span data-stu-id="508b2-150">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to.</span></span>

2. <span data-ttu-id="508b2-151">Adicione os navegadores que não têm permissão para acessar determinados itens confidenciais quando ocorre uma correspondência de política DLP.</span><span class="sxs-lookup"><span data-stu-id="508b2-151">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs.</span></span>

3. <span data-ttu-id="508b2-152">Configure as políticas DLP para definir os tipos de itens confidenciais para os quais o carregamento deve ser restrito a esses lugares, ativando **Carregar nos serviços de nuvem** e **Acesso a partir do navegador não permitido**.</span><span class="sxs-lookup"><span data-stu-id="508b2-152">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on **Upload to cloud services** and **Access from unallowed browser**.</span></span>

<span data-ttu-id="508b2-153">Você pode continuar a adicionar novos serviços, aplicativos e políticas para estender e aprimorar suas restrições para atender às suas necessidades de negócios e proteger dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="508b2-153">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="508b2-154">Essa configuração ajudará a garantir a segurança dos seus dados, além de evitar restrições desnecessárias, que impedem ou impedem que os usuários acessem e compartilhem itens não confidenciais.</span><span class="sxs-lookup"><span data-stu-id="508b2-154">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="508b2-155">Cenários de política da DLP de Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="508b2-155">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="508b2-p108">Para ajudar a se familiarizar com os recursos da DLP de Ponto de Extremidade e como eles aparecem nas políticas DLP, reunimos alguns cenários para você seguir. Todo o conteúdo da DLP de Ponto de Extremidade será incluído no conteúdo principal da DLP definido quando a DLP de Ponto de Extremidade estiver disponível em geral.</span><span class="sxs-lookup"><span data-stu-id="508b2-p108">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow. All the Endpoint DLP content will be folded in to the main DLP content set when Endpoint DLP becomes generally available.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="508b2-p109">Esses cenários DLP de Ponto de Extremidade não são os procedimentos oficiais para criar e ajustar políticas DLP. Confira os tópicos a seguir quando precisar trabalhar com as políticas DLP em situações gerais:</span><span class="sxs-lookup"><span data-stu-id="508b2-p109">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies. Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="508b2-160">Visão geral da prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="508b2-160">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
>- [<span data-ttu-id="508b2-161">Introdução à política DLP padrão</span><span class="sxs-lookup"><span data-stu-id="508b2-161">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="508b2-162">Criar uma política DLP a partir de um modelo</span><span class="sxs-lookup"><span data-stu-id="508b2-162">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="508b2-163">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="508b2-163">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="508b2-164">Cenário 1: Criar uma política a partir de um modelo, somente auditoria</span><span class="sxs-lookup"><span data-stu-id="508b2-164">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="508b2-p110">Esses cenários exigem que você já tenha dispositivos integrados e relatórios no Explorador de atividades. Se você ainda não integrou dispositivos, confira [Introdução à prevenção contra perda de dados do Ponto de Extremidade](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="508b2-p110">These scenarios require that you already have devices onboarded and reporting into Activity explorer. If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="508b2-167">Abra a página [Prevenção contra perda de dados](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="508b2-167">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="508b2-168">Escolha **Criar política**.</span><span class="sxs-lookup"><span data-stu-id="508b2-168">Choose **Create policy**.</span></span>

3. <span data-ttu-id="508b2-169">Para esse cenário, escolha **Privacidade** , em seguida, **Dados de Informações de Identificação Pessoal (PII) dos EUA** e escolha **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="508b2-169">For this scenario, choose **Privacy** , then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>

4. <span data-ttu-id="508b2-p111">Alterne o campo **Status** para desativado em todos os locais, exceto em **Dispositivos**. Escolha **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="508b2-p111">Toggle the **Status** field to off for all locations except **Devices**. Choose **Next**.</span></span>

5. <span data-ttu-id="508b2-172">Aceite a seleção padrão **Revisar e personalizar as configurações do modelo** e escolha **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="508b2-172">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>

6. <span data-ttu-id="508b2-173">Aceite os valores padrão de **Ações de proteção** e escolha **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="508b2-173">Accept the default **Protection actions** values and choose **Next**.</span></span>

7. <span data-ttu-id="508b2-p112">Selecione **Auditoria ou restringir atividades em dispositivos de Windows** e deixe as ações definidas como **Somente auditar**. Escolha **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="508b2-p112">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**. Choose **Next**.</span></span>

8. <span data-ttu-id="508b2-p113">Aceite o valor padrão **Eu quero testá-lo primeiro** e escolha **Mostrar dicas de política enquanto estiver no modo de teste**. Escolha **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="508b2-p113">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**. Choose **Next**.</span></span>

9. <span data-ttu-id="508b2-178">Examine as configurações e escolha **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="508b2-178">Review your settings and choose **Submit**.</span></span>

10. <span data-ttu-id="508b2-179">A nova política DLP será exibida na lista de políticas.</span><span class="sxs-lookup"><span data-stu-id="508b2-179">The new DLP policy will appear in the policy list.</span></span>

11. <span data-ttu-id="508b2-p114">Verifique o Explorador de atividades para dados dos pontos de extremidade monitorados. Defina o filtro de localização para dispositivos e adicione a política, em seguida, filtre por nome de política para ver o impacto desta política. Se necessário, confira, [Introdução ao explorador de atividades](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="508b2-p114">Check Activity explorer for data from the monitored endpoints. Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy. See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>

12. <span data-ttu-id="508b2-p115">Tente compartilhar um teste que contenha o conteúdo que acionará a condição de Dados de Informações de Identificação Pessoal (PII) dos EUA com alguém de fora da sua organização. Isso deve acionar a política.</span><span class="sxs-lookup"><span data-stu-id="508b2-p115">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization. This should trigger the policy.</span></span>

13. <span data-ttu-id="508b2-185">Verifique o Explorador de atividades para obter o evento.</span><span class="sxs-lookup"><span data-stu-id="508b2-185">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="508b2-186">Cenário 2: Modificar a política existente, definir um alerta</span><span class="sxs-lookup"><span data-stu-id="508b2-186">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="508b2-187">Abra a página [Prevenção de perda de dados](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="508b2-187">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="508b2-188">Escolha as políticas de **Dados de Informações de Identificação Pessoal (PII) dos EUA** criadas cenário 1.</span><span class="sxs-lookup"><span data-stu-id="508b2-188">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="508b2-189">Escolha **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="508b2-189">Choose **edit policy**.</span></span>

4. <span data-ttu-id="508b2-190">Vá para a página **Regras avançadas de DLP** e edite o **Baixo volume de conteúdo detectado nas Informações de Identificação Pessoal dos EUA**.</span><span class="sxs-lookup"><span data-stu-id="508b2-190">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="508b2-p116">Role para baixo até a seção **Relatórios de incidentes** e defina **Enviar um alerta aos administradores quando ocorrer uma correspondência de regra** como **Ativado**. Os Alertas de email serão enviados automaticamente ao administrador e a qualquer pessoa que você adicionar à lista de destinatários.</span><span class="sxs-lookup"><span data-stu-id="508b2-p116">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**. Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="508b2-193">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="508b2-193">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
   
6. <span data-ttu-id="508b2-194">Para fins deste cenário, escolha **Enviar alerta sempre que uma atividade corresponder à regra**.</span><span class="sxs-lookup"><span data-stu-id="508b2-194">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>

7. <span data-ttu-id="508b2-195">Escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="508b2-195">Choose **Save**.</span></span>

8. <span data-ttu-id="508b2-196">Mantenha todas as suas configurações anteriores escolhendo **Próximo** e **Enviar** as alterações de política.</span><span class="sxs-lookup"><span data-stu-id="508b2-196">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="508b2-p117">Tente compartilhar um teste que contenha o conteúdo que acionará a condição de Dados de Informações de Identificação Pessoal (PII) dos EUA com alguém de fora da sua organização. Isso deve acionar a política.</span><span class="sxs-lookup"><span data-stu-id="508b2-p117">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization. This should trigger the policy.</span></span>

10. <span data-ttu-id="508b2-199">Verifique o Explorador de atividades para obter o evento.</span><span class="sxs-lookup"><span data-stu-id="508b2-199">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="508b2-200">Cenário 3: Modificar a política existente, bloquear a ação com permitir substituição</span><span class="sxs-lookup"><span data-stu-id="508b2-200">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="508b2-201">Abra a página [Prevenção de perda de dados](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="508b2-201">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="508b2-202">Escolha as políticas de **Dados de Informações de Identificação Pessoal (PII) dos EUA** criadas cenário 1.</span><span class="sxs-lookup"><span data-stu-id="508b2-202">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="508b2-203">Escolha **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="508b2-203">Choose **edit policy**.</span></span>

4. <span data-ttu-id="508b2-204">Vá para a página **Regras avançadas de DLP** e edite o **Baixo volume de conteúdo detectado nas Informações de Identificação Pessoal dos EUA**.</span><span class="sxs-lookup"><span data-stu-id="508b2-204">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="508b2-205">Role a tela para baixo até a seção **Auditoria ou restringir atividades nos dispositivos do Windows** e para cada atividade defina a ação correspondente para **Bloquear com substituir**.</span><span class="sxs-lookup"><span data-stu-id="508b2-205">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="508b2-206">![definir o bloco com substituir ação](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="508b2-206">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
   
6. <span data-ttu-id="508b2-207">Escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="508b2-207">Choose **Save**.</span></span>

7. <span data-ttu-id="508b2-208">Repita as etapas 4-7 para o **Alto volume de conteúdo detectado nas Informações de Identificação Pessoal dos EUA**.</span><span class="sxs-lookup"><span data-stu-id="508b2-208">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>

8. <span data-ttu-id="508b2-209">Mantenha todas as suas configurações anteriores escolhendo **Próximo** e **Enviar** as alterações de política.</span><span class="sxs-lookup"><span data-stu-id="508b2-209">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="508b2-p118">Tente compartilhar um teste que contenha o conteúdo que acionará a condição de Dados de Informações de Identificação Pessoal (PII) dos EUA com alguém de fora da sua organização. Isso deve acionar a política.</span><span class="sxs-lookup"><span data-stu-id="508b2-p118">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization. This should trigger the policy.</span></span>

   <span data-ttu-id="508b2-212">Você verá um pop-up desse tipo no dispositivo do cliente:</span><span class="sxs-lookup"><span data-stu-id="508b2-212">You'll see a popup like this on the client device:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="508b2-213">![cliente dlp do ponto de extremidade bloqueado na notificação de substituição](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span><span class="sxs-lookup"><span data-stu-id="508b2-213">![endpoint dlp client blocked override notification](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span></span>

10. <span data-ttu-id="508b2-214">Verifique o Explorador de atividades para obter o evento.</span><span class="sxs-lookup"><span data-stu-id="508b2-214">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="508b2-215">Confira também</span><span class="sxs-lookup"><span data-stu-id="508b2-215">See also</span></span>

- [<span data-ttu-id="508b2-216">Saiba mais sobre a Prevenção contra perda de dados do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="508b2-216">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="508b2-217">Introdução à Prevenção contra perda de dados do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="508b2-217">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="508b2-218">Visão geral da prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="508b2-218">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="508b2-219">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="508b2-219">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="508b2-220">Começar a usar o Explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="508b2-220">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="508b2-221">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="508b2-221">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="508b2-222">Ferramentas e métodos de integração para computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="508b2-222">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="508b2-223">Assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="508b2-223">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="508b2-224">Associados a Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="508b2-224">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="508b2-225">Baixar o novo Microsoft Edge baseado em Chromium</span><span class="sxs-lookup"><span data-stu-id="508b2-225">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [<span data-ttu-id="508b2-226">Introdução à política DLP padrão</span><span class="sxs-lookup"><span data-stu-id="508b2-226">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="508b2-227">Criar uma política DLP a partir de um modelo</span><span class="sxs-lookup"><span data-stu-id="508b2-227">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
