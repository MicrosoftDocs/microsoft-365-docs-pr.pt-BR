---
title: Criar indicadores com base em certificados
ms.reviewer: ''
description: Crie indicadores com base em certificados que definem a detecção, a prevenção e a exclusão de entidades.
keywords: ioc, certificado, certificados, gerenciar, permitido, bloqueado, bloquear, limpar, mal-intencionado, hash de arquivo, endereço ip, urls, domínio
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
ms.openlocfilehash: b75a8cf1d2681281555a3b7bb80deadfc11ee44c
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845445"
---
# <a name="create-indicators-based-on-certificates"></a><span data-ttu-id="3fedf-104">Criar indicadores com base em certificados</span><span class="sxs-lookup"><span data-stu-id="3fedf-104">Create indicators based on certificates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3fedf-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="3fedf-105">**Applies to:**</span></span>
- [<span data-ttu-id="3fedf-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="3fedf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3fedf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3fedf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="3fedf-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="3fedf-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3fedf-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="3fedf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="3fedf-110">Você pode criar indicadores para certificados.</span><span class="sxs-lookup"><span data-stu-id="3fedf-110">You can create indicators for certificates.</span></span> <span data-ttu-id="3fedf-111">Alguns casos de uso comuns incluem:</span><span class="sxs-lookup"><span data-stu-id="3fedf-111">Some common use cases include:</span></span>

- <span data-ttu-id="3fedf-112">Cenários quando você precisa implantar tecnologias de bloqueio, como regras de redução de superfície de ataque e acesso controlado a pastas, mas precisa permitir comportamentos de aplicativos assinados adicionando o certificado na lista de autorizações. [](attack-surface-reduction.md) [](controlled-folders.md)</span><span class="sxs-lookup"><span data-stu-id="3fedf-112">Scenarios when you need to deploy blocking technologies, such as [attack surface reduction rules](attack-surface-reduction.md) and [controlled folder access](controlled-folders.md) but need to allow behaviors from signed applications by adding the certificate in the allow list.</span></span>
- <span data-ttu-id="3fedf-113">Bloqueando o uso de um aplicativo assinado específico em toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="3fedf-113">Blocking the use of a specific signed application across your organization.</span></span> <span data-ttu-id="3fedf-114">Ao criar um indicador para bloquear o certificado do aplicativo, Windows Defender AV impedirá execuções de arquivo (bloquear e remediar) e a Investigação Automatizada e Correção se comportará da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="3fedf-114">By creating an indicator to block the certificate of the application, Windows Defender AV will prevent file executions (block and remediate) and the Automated Investigation and Remediation behave the same.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="3fedf-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="3fedf-115">Before you begin</span></span>

<span data-ttu-id="3fedf-116">É importante entender os seguintes requisitos antes da criação de indicadores para certificados:</span><span class="sxs-lookup"><span data-stu-id="3fedf-116">It's important to understand the following requirements prior to creating indicators for certificates:</span></span>

- <span data-ttu-id="3fedf-117">Esse recurso estará disponível se sua organização usar Windows Defender Antivírus e a proteção baseada em nuvem estiver habilitada.</span><span class="sxs-lookup"><span data-stu-id="3fedf-117">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="3fedf-118">Para obter mais informações, consulte [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="3fedf-118">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="3fedf-119">A versão do cliente Antimalware deve ser 4.18.1901.x ou posterior.</span><span class="sxs-lookup"><span data-stu-id="3fedf-119">The Antimalware client version must be  4.18.1901.x or later.</span></span>
- <span data-ttu-id="3fedf-120">Com suporte em máquinas Windows 10, versão 1703 ou posterior, Windows 2016 e 2019.</span><span class="sxs-lookup"><span data-stu-id="3fedf-120">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="3fedf-121">As definições de proteção contra vírus e ameaças devem estar atualizadas.</span><span class="sxs-lookup"><span data-stu-id="3fedf-121">The virus and threat protection definitions must be up to date.</span></span>
- <span data-ttu-id="3fedf-122">No momento, esse recurso dá suporte à inserção de . CER ou . Extensões de arquivo PEM.</span><span class="sxs-lookup"><span data-stu-id="3fedf-122">This feature currently supports entering .CER or .PEM file extensions.</span></span>

>[!IMPORTANT]
> - <span data-ttu-id="3fedf-123">Um certificado folha válido é um certificado de assinatura que tem um caminho de certificação válido e deve ser encadeado à Autoridade de Certificação Raiz (CA) confiável pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3fedf-123">A valid leaf certificate is a signing certificate that has a valid certification path and must be chained to the Root Certificate Authority (CA) trusted by Microsoft.</span></span>  <span data-ttu-id="3fedf-124">Como alternativa, um certificado personalizado (auto-assinado) pode ser usado desde que ele seja confiável pelo cliente (o certificado de AC raiz é instalado sob a Máquina Local 'Autoridades de Certificação Raiz Confiáveis').</span><span class="sxs-lookup"><span data-stu-id="3fedf-124">Alternatively, a custom (self-signed) certificate can be used as long as it's trusted by the client (Root CA certificate is installed under the Local Machine 'Trusted Root Certification Authorities').</span></span>
>- <span data-ttu-id="3fedf-125">Os filhos ou pai dos IOCs de certificado de permitir/bloquear não estão incluídos na funcionalidade IoC de permitir/bloquear, apenas certificados folha são suportados.</span><span class="sxs-lookup"><span data-stu-id="3fedf-125">The children or parent of the allow/block certificate IOCs are not included in the allow/block IoC functionality, only leaf certificates are supported.</span></span>
>- <span data-ttu-id="3fedf-126">Os certificados assinados pela Microsoft não podem ser bloqueados.</span><span class="sxs-lookup"><span data-stu-id="3fedf-126">Microsoft signed certificates cannot be blocked.</span></span>

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a><span data-ttu-id="3fedf-127">Crie um indicador para certificados na página de configurações:</span><span class="sxs-lookup"><span data-stu-id="3fedf-127">Create an indicator for certificates from the settings page:</span></span>

>[!IMPORTANT]
> <span data-ttu-id="3fedf-128">Pode levar até 3 horas para criar e remover um IoC de certificado.</span><span class="sxs-lookup"><span data-stu-id="3fedf-128">It can take up to 3 hours to create and remove a certificate IoC.</span></span>

1. <span data-ttu-id="3fedf-129">No painel de navegação, selecione **Configurações**  >  **Indicadores**.</span><span class="sxs-lookup"><span data-stu-id="3fedf-129">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="3fedf-130">Selecione a **guia Certificado.**</span><span class="sxs-lookup"><span data-stu-id="3fedf-130">Select the **Certificate** tab.</span></span>

3. <span data-ttu-id="3fedf-131">Selecione **Adicionar indicador**.</span><span class="sxs-lookup"><span data-stu-id="3fedf-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="3fedf-132">Especifique os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="3fedf-132">Specify the following details:</span></span>
   - <span data-ttu-id="3fedf-133">Indicador - Especifique os detalhes da entidade e defina a expiração do indicador.</span><span class="sxs-lookup"><span data-stu-id="3fedf-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="3fedf-134">Ação - Especifique a ação a ser tomada e forneça uma descrição.</span><span class="sxs-lookup"><span data-stu-id="3fedf-134">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="3fedf-135">Escopo - Definir o escopo do grupo de máquinas.</span><span class="sxs-lookup"><span data-stu-id="3fedf-135">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="3fedf-136">Revise os detalhes na guia Resumo e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3fedf-136">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3fedf-137">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3fedf-137">Related topics</span></span>
- [<span data-ttu-id="3fedf-138">Criar indicadores</span><span class="sxs-lookup"><span data-stu-id="3fedf-138">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="3fedf-139">Criar indicadores para arquivos</span><span class="sxs-lookup"><span data-stu-id="3fedf-139">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="3fedf-140">Criar indicadores para IPs e URLs/domínios</span><span class="sxs-lookup"><span data-stu-id="3fedf-140">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="3fedf-141">Gerenciar indicadores</span><span class="sxs-lookup"><span data-stu-id="3fedf-141">Manage indicators</span></span>](indicator-manage.md)
