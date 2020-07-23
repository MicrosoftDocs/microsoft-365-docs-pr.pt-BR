---
title: DKE (criptografia de chave dupla)
description: O DKE permite proteger dados altamente confidenciais, mantendo o controle total da sua chave.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 07/21/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: d9ed155576d69889e53e4e4d1ce03e4233fd08ff
ms.sourcegitcommit: 4789b261eb029d7c965421a1260acc110e6385db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "45387438"
---
# <a name="double-key-encryption-dke"></a><span data-ttu-id="eae20-103">DKE (criptografia de chave dupla)</span><span class="sxs-lookup"><span data-stu-id="eae20-103">Double Key Encryption (DKE)</span></span>

> <span data-ttu-id="eae20-104">*Aplica-se a: chave dupla de criptografia para o Microsoft 365 Public Preview, [microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [proteção de informações do Azure](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="eae20-104">*Applies to: Double Key Encryption for Microsoft 365 public preview, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="eae20-105">*Instruções para: [cliente de rotulação unificada de proteção de informações do Azure para Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="eae20-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="eae20-106">*Descrição do serviço para: conformidade com a [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="eae20-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="eae20-107">A criptografia de chave dupla (DKE) usa duas chaves juntas para acessar o conteúdo protegido.</span><span class="sxs-lookup"><span data-stu-id="eae20-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="eae20-108">Você armazena uma chave no Microsoft Azure e mantém a outra chave.</span><span class="sxs-lookup"><span data-stu-id="eae20-108">You store one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="eae20-109">O cliente de rotulação unificado de proteção de informações do Azure protege o conteúdo altamente confidencial enquanto você mantém o controle total de uma de suas chaves.</span><span class="sxs-lookup"><span data-stu-id="eae20-109">The Azure Information Protection unified labeling client protects highly sensitive content while you maintain full control of one of your keys.</span></span>

<span data-ttu-id="eae20-110">A criptografia de chave dupla oferece suporte a implantações no local e na nuvem.</span><span class="sxs-lookup"><span data-stu-id="eae20-110">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="eae20-111">Essas implantações ajudam a garantir que os dados criptografados permaneçam opaco onde quer você armazene os dados protegidos.</span><span class="sxs-lookup"><span data-stu-id="eae20-111">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="eae20-112">Para obter mais informações sobre as chaves de raiz de locatários padrão baseadas em nuvem, consulte [Planning and Implementing Your Azure Information Protection locatário Key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span><span class="sxs-lookup"><span data-stu-id="eae20-112">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

<span data-ttu-id="eae20-113">O vídeo a seguir mostra como a criptografia de chave dupla funciona para proteger o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="eae20-113">The following video shows how Double Key Encryption works to secure your content.</span></span>

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]

<span data-ttu-id="eae20-114">Se as suas organizações têm qualquer um dos seguintes requisitos, você pode usar o DKE para ajudar a proteger o conteúdo:</span><span class="sxs-lookup"><span data-stu-id="eae20-114">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="eae20-115">Você quer garantir que *apenas você* possa descriptografar o conteúdo protegido, em todas as circunstâncias.</span><span class="sxs-lookup"><span data-stu-id="eae20-115">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="eae20-116">Você não deseja que a Microsoft tenha acesso a dados protegidos por conta própria.</span><span class="sxs-lookup"><span data-stu-id="eae20-116">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="eae20-117">Você tem requisitos normativos para manter chaves dentro de um limite geográfico.</span><span class="sxs-lookup"><span data-stu-id="eae20-117">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="eae20-118">Todas as chaves que você mantém para criptografia e descriptografia de dados são mantidas em seu data center.</span><span class="sxs-lookup"><span data-stu-id="eae20-118">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="eae20-119">Requisitos de sistema e licenciamento para o DKE</span><span class="sxs-lookup"><span data-stu-id="eae20-119">System and licensing requirements for DKE</span></span>

<span data-ttu-id="eae20-120">Criptografia de chave dupla para a Microsoft 365 parte do Microsoft 365 E5 e Office 365 e5.</span><span class="sxs-lookup"><span data-stu-id="eae20-120">Double Key Encryption for Microsoft 365 part of Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="eae20-121">Se você não tem uma licença do Microsoft 365 e5, é possível inscrever-se em uma [avaliação](https://aka.ms/M365E5ComplianceTrial).</span><span class="sxs-lookup"><span data-stu-id="eae20-121">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="eae20-122">Para obter mais informações sobre essas licenças, consulte [diretrizes de licenciamento da Microsoft 365 para segurança & conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="eae20-122">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="eae20-123">**Office Insider** Para usar a visualização pública, você deve ser membro do programa Office Insider.</span><span class="sxs-lookup"><span data-stu-id="eae20-123">**Office Insider** To use the public preview, you must be a member of the Office Insider program.</span></span> <span data-ttu-id="eae20-124">Para ingressar no Office Insider, vá para [https://insider.office.com](https://insider.office.com) .</span><span class="sxs-lookup"><span data-stu-id="eae20-124">To join Office Insider, go to [https://insider.office.com](https://insider.office.com).</span></span> <span data-ttu-id="eae20-125">Quando você for membro, prepare o ambiente para implantar o Office Insider compilações escolhendo o método de implantação certo para sua organização.</span><span class="sxs-lookup"><span data-stu-id="eae20-125">Once you're a member, prepare your environment to deploy Office Insider builds by choosing the right deployment method for your organization.</span></span> <span data-ttu-id="eae20-126">Para obter instruções, consulte [introdução à implantação de compilações do Office Insider](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="eae20-126">For instructions, see [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="eae20-127">**Proteção de informações do Azure**.</span><span class="sxs-lookup"><span data-stu-id="eae20-127">**Azure Information Protection**.</span></span> <span data-ttu-id="eae20-128">O DKE funciona com rótulos de sensibilidade e requer a proteção de informações do Azure.</span><span class="sxs-lookup"><span data-stu-id="eae20-128">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="eae20-129">Ambientes suportados para armazenar e exibir o conteúdo protegido por DKE</span><span class="sxs-lookup"><span data-stu-id="eae20-129">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="eae20-130">**Aplicativos com suporte**.</span><span class="sxs-lookup"><span data-stu-id="eae20-130">**Supported applications**.</span></span> <span data-ttu-id="eae20-131">[Microsoft 365 aplicativos para clientes corporativos](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) no Windows, incluindo Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="eae20-131">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="eae20-132">**Suporte a conteúdo online**.</span><span class="sxs-lookup"><span data-stu-id="eae20-132">**Online content support**.</span></span> <span data-ttu-id="eae20-133">Há suporte para documentos e arquivos armazenados online no Microsoft SharePoint e no OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="eae20-133">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="eae20-134">Você pode compartilhar conteúdo criptografado por email, mas não pode exibir documentos e arquivos criptografados online.</span><span class="sxs-lookup"><span data-stu-id="eae20-134">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="eae20-135">Em vez disso, você deve exibir o conteúdo protegido usando os aplicativos de área de trabalho no computador local.</span><span class="sxs-lookup"><span data-stu-id="eae20-135">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="about-this-public-preview-article"></a><span data-ttu-id="eae20-136">Sobre este artigo de demonstração pública</span><span class="sxs-lookup"><span data-stu-id="eae20-136">About this public preview article</span></span>

<span data-ttu-id="eae20-137">Há várias maneiras de realizar algumas das etapas para implantar a criptografia de chave dupla.</span><span class="sxs-lookup"><span data-stu-id="eae20-137">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="eae20-138">Este artigo fornece instruções detalhadas para que administradores menos experientes implantem o serviço com êxito.</span><span class="sxs-lookup"><span data-stu-id="eae20-138">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="eae20-139">Se você estiver confortável para fazer isso, você pode optar por usar seus próprios métodos.</span><span class="sxs-lookup"><span data-stu-id="eae20-139">If you're comfortable doing so, you can choose to use your own methods.</span></span>

<span data-ttu-id="eae20-140">Este artigo inclui instruções passo a passo sobre como implantar o serviço de criptografia de chave dupla no Azure.</span><span class="sxs-lookup"><span data-stu-id="eae20-140">This article includes step-by-step instructions on how to deploy the Double Key Encryption service to Azure.</span></span> <span data-ttu-id="eae20-141">Esse cenário não é algo que você provavelmente faria em produção.</span><span class="sxs-lookup"><span data-stu-id="eae20-141">This scenario isn't something you'd likely do in production.</span></span> <span data-ttu-id="eae20-142">Para visualização pública, usar o Azure é uma maneira rápida de implantar o DKE.</span><span class="sxs-lookup"><span data-stu-id="eae20-142">For public preview, using Azure is a quick way to deploy DKE.</span></span> <span data-ttu-id="eae20-143">A implantação do Azure permite que você comece a usar a criptografia de chave dupla imediatamente.</span><span class="sxs-lookup"><span data-stu-id="eae20-143">Deploying to Azure lets you get started using Double Key Encryption right away.</span></span>

<span data-ttu-id="eae20-144">Você pode implantar o serviço localmente em sua rede ou com outro provedor.</span><span class="sxs-lookup"><span data-stu-id="eae20-144">You can deploy the service locally on your network or with another provider.</span></span> <span data-ttu-id="eae20-145">Você precisará publicar o repositório de chaves usando métodos apropriados para esse local.</span><span class="sxs-lookup"><span data-stu-id="eae20-145">You'll need to publish the key store using methods that are appropriate for that location.</span></span>

## <a name="deploy-double-key-encryption"></a><span data-ttu-id="eae20-146">Implantar a criptografia de chave dupla</span><span class="sxs-lookup"><span data-stu-id="eae20-146">Deploy Double Key Encryption</span></span>

<span data-ttu-id="eae20-147">Este artigo e o vídeo de implantação usam o Azure como o destino de implantação para o serviço DKE.</span><span class="sxs-lookup"><span data-stu-id="eae20-147">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="eae20-148">Se você estiver implantando em outro local, precisará fornecer seus próprios valores.</span><span class="sxs-lookup"><span data-stu-id="eae20-148">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="eae20-149">Assista ao [vídeo de implantação de criptografia de duas chaves](https://msit.microsoftstream.com/video/cfdda3ff-0400-a521-1579-f1eacc37fc7e) para ver a visão geral passo a passo dos conceitos no artigo.</span><span class="sxs-lookup"><span data-stu-id="eae20-149">Watch the [Double Key Encryption deployment video](https://msit.microsoftstream.com/video/cfdda3ff-0400-a521-1579-f1eacc37fc7e) to see step-by-step overview of concepts in the article.</span></span> <span data-ttu-id="eae20-150">O vídeo leva cerca de 18 minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="eae20-150">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="eae20-151">Siga estas etapas gerais para configurar a criptografia de chave dupla para sua organização.</span><span class="sxs-lookup"><span data-stu-id="eae20-151">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="eae20-152">Instalar pré-requisitos de software</span><span class="sxs-lookup"><span data-stu-id="eae20-152">Install software prerequisites</span></span>](#install-software-prerequisites)
1. [<span data-ttu-id="eae20-153">Clone o repositório do GitHub de criptografia de chave dupla</span><span class="sxs-lookup"><span data-stu-id="eae20-153">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="eae20-154">Modificar configurações do aplicativo</span><span class="sxs-lookup"><span data-stu-id="eae20-154">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="eae20-155">Gerar chaves de teste</span><span class="sxs-lookup"><span data-stu-id="eae20-155">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="eae20-156">Compilar o projeto</span><span class="sxs-lookup"><span data-stu-id="eae20-156">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="eae20-157">Publicar o repositório de chaves</span><span class="sxs-lookup"><span data-stu-id="eae20-157">Publish the key store</span></span>](#publish-the-key-store)
1. [<span data-ttu-id="eae20-158">Validar sua implantação</span><span class="sxs-lookup"><span data-stu-id="eae20-158">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="eae20-159">Registrar seu repositório de chaves</span><span class="sxs-lookup"><span data-stu-id="eae20-159">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="eae20-160">Criar rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="eae20-160">Create sensitivity labels</span></span>](#create-labels-using-dke)

<span data-ttu-id="eae20-161">Quando tiver concluído, você poderá criptografar documentos e arquivos usando o DKE.</span><span class="sxs-lookup"><span data-stu-id="eae20-161">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="eae20-162">Para saber mais, confira [aplicar rótulos de confidencialidade aos seus arquivos e emails no Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span><span class="sxs-lookup"><span data-stu-id="eae20-162">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites"></a><span data-ttu-id="eae20-163">Instalar pré-requisitos de software</span><span class="sxs-lookup"><span data-stu-id="eae20-163">Install software prerequisites</span></span>

<span data-ttu-id="eae20-164">Há dois tipos de pré-requisitos de software para a criptografia de chave dupla</span><span class="sxs-lookup"><span data-stu-id="eae20-164">There are two types of software prerequisites for Double Key Encryption</span></span>

- [<span data-ttu-id="eae20-165">Pré-requisitos do serviço de criptografia de chave dupla</span><span class="sxs-lookup"><span data-stu-id="eae20-165">Double Key Encryption service prerequisites</span></span>](#double-key-encryption-service-prerequisites)
- [<span data-ttu-id="eae20-166">Pré-requisitos de criptografia de chave dupla para computadores clientes</span><span class="sxs-lookup"><span data-stu-id="eae20-166">Double Key Encryption prerequisites for client computers</span></span>](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a><span data-ttu-id="eae20-167">Pré-requisitos do serviço de criptografia de chave dupla</span><span class="sxs-lookup"><span data-stu-id="eae20-167">Double Key Encryption service prerequisites</span></span>

<span data-ttu-id="eae20-168">Instale esses pré-requisitos no computador onde você deseja instalar o serviço DKE.</span><span class="sxs-lookup"><span data-stu-id="eae20-168">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="eae20-169">**SDK do .NET Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="eae20-169">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="eae20-170">Baixe e instale o SDK do [download do .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="eae20-170">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="eae20-171">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="eae20-171">**Visual Studio Code**.</span></span> <span data-ttu-id="eae20-172">Baixe o Visual Studio Code de [https://code.visualstudio.com/](https://code.visualstudio.com) .</span><span class="sxs-lookup"><span data-stu-id="eae20-172">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="eae20-173">Depois de instalado, execute o Visual Studio Code e selecione **View** \> **Extensions**.</span><span class="sxs-lookup"><span data-stu-id="eae20-173">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="eae20-174">Instale essas extensões.</span><span class="sxs-lookup"><span data-stu-id="eae20-174">Install these extensions.</span></span>

- <span data-ttu-id="eae20-175">C# para o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="eae20-175">C# for Visual Studio Code</span></span>

- <span data-ttu-id="eae20-176">Gerenciador de pacotes do NuGet</span><span class="sxs-lookup"><span data-stu-id="eae20-176">NuGet Package Manager</span></span>

<span data-ttu-id="eae20-177">**Microsoft Office Insider**.</span><span class="sxs-lookup"><span data-stu-id="eae20-177">**Microsoft Office Insider**.</span></span> <span data-ttu-id="eae20-178">Configure pelo menos um [método de implantação](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="eae20-178">Set up at least one [deployment method](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="eae20-179">**Recursos git**.</span><span class="sxs-lookup"><span data-stu-id="eae20-179">**Git resources**.</span></span> <span data-ttu-id="eae20-180">Baixe e instale um dos seguintes.</span><span class="sxs-lookup"><span data-stu-id="eae20-180">Download and install one of the following.</span></span>

- [<span data-ttu-id="eae20-181">Git</span><span class="sxs-lookup"><span data-stu-id="eae20-181">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="eae20-182">Área de trabalho do GitHub</span><span class="sxs-lookup"><span data-stu-id="eae20-182">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="eae20-183">GitHub corporativo</span><span class="sxs-lookup"><span data-stu-id="eae20-183">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="eae20-184">**OpenSSL** Você deve ter o [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) instalado para [gerar chaves de teste](#generate-test-keys) depois de implantar o DKE.</span><span class="sxs-lookup"><span data-stu-id="eae20-184">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="eae20-185">Certifique-se de que você está invocando-o corretamente de seu caminho de variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="eae20-185">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="eae20-186">Por exemplo, consulte "Adicionar o diretório de instalação ao caminho" https://www.osradar.com/install-openssl-windows/ para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="eae20-186">For example, see "Add the installation directory to PATH" at https://www.osradar.com/install-openssl-windows/ for details.</span></span>

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a><span data-ttu-id="eae20-187">Pré-requisitos de criptografia de chave dupla para computadores clientes</span><span class="sxs-lookup"><span data-stu-id="eae20-187">Double Key Encryption prerequisites for client computers</span></span>

<span data-ttu-id="eae20-188">Instale esses pré-requisitos em cada computador cliente onde você deseja proteger e consumir documentos protegidos.</span><span class="sxs-lookup"><span data-stu-id="eae20-188">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="eae20-189">**Microsoft Office** versão \*. 12711 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="eae20-189">**Microsoft Office** version \*.12711 or later.</span></span>

<span data-ttu-id="eae20-190">Versões **unificadas de rótulo do cliente de proteção de informações do Azure** 2.7.93.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="eae20-190">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="eae20-191">Baixe e instale o cliente de rotulação unificada da [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="eae20-191">Download and install the Unified Labeling client from [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="eae20-192">Clonar o repositório do GitHub DKE</span><span class="sxs-lookup"><span data-stu-id="eae20-192">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="eae20-193">A Microsoft fornece os arquivos de origem do DKE em um repositório do GitHub.</span><span class="sxs-lookup"><span data-stu-id="eae20-193">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="eae20-194">Você clona o repositório para compilar o projeto localmente para uso da sua organização.</span><span class="sxs-lookup"><span data-stu-id="eae20-194">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="eae20-195">O repositório do GitHub do DKE está localizado em [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="eae20-195">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="eae20-196">As instruções a seguir se destinam a usuários do git ou do Visual Studio Code inexperientes:</span><span class="sxs-lookup"><span data-stu-id="eae20-196">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="eae20-197">No navegador, acesse:[https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span><span class="sxs-lookup"><span data-stu-id="eae20-197">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span></span>

1. <span data-ttu-id="eae20-198">No lado direito da tela, selecione **código**.</span><span class="sxs-lookup"><span data-stu-id="eae20-198">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="eae20-199">Sua versão da interface do usuário pode mostrar um botão **clone ou download** .</span><span class="sxs-lookup"><span data-stu-id="eae20-199">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="eae20-200">Em seguida, na lista suspensa exibida, selecione o ícone Copiar para copiar a URL para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="eae20-200">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="eae20-201">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="eae20-201">For example:</span></span>

    :::image type="content" source="../media/dke-clone.png" alt-text="Clonar o repositório de serviço de criptografia de chave dupla do GitHub":::

3. <span data-ttu-id="eae20-203">No Visual Studio Code, selecione **Exibir** \> **paleta de comandos** e selecione **git: clonar**.</span><span class="sxs-lookup"><span data-stu-id="eae20-203">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="eae20-204">Para ir para a opção na lista, comece a digitar `git: clone` para filtrar as entradas e, em seguida, selecione-a no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="eae20-204">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="eae20-205">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="eae20-205">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-clone.png" alt-text="Visual Studio Code GIT: opção clone":::

4. <span data-ttu-id="eae20-207">Na caixa de texto, Cole a URL que você copiou do git e selecione **clonar do GitHub**.</span><span class="sxs-lookup"><span data-stu-id="eae20-207">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="eae20-208">Na caixa de diálogo **Selecionar pasta** exibida, procure e selecione um local para armazenar o repositório.</span><span class="sxs-lookup"><span data-stu-id="eae20-208">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="eae20-209">No prompt, selecione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="eae20-209">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="eae20-210">O repositório é aberto no Visual Studio Code e exibe a ramificação atual do git no canto inferior esquerdo.</span><span class="sxs-lookup"><span data-stu-id="eae20-210">The repository is opened in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="eae20-211">A ramificação deve ser **mestra**.</span><span class="sxs-lookup"><span data-stu-id="eae20-211">The branch should be **master**.</span></span>

    <span data-ttu-id="eae20-212">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="eae20-212">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-master.png" alt-text="Ramificação do Visual Studio Code Master":::

6. <span data-ttu-id="eae20-214">Selecione o Word **Master** e, em seguida, selecione **public_preview** na lista de ramificações.</span><span class="sxs-lookup"><span data-stu-id="eae20-214">Select the word **master,** and then select **public_preview** from the list of branches.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="eae20-215">Selecionar a ramificação public_preview garante que você tenha os arquivos corretos para compilar o projeto.</span><span class="sxs-lookup"><span data-stu-id="eae20-215">Selecting the public_preview branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="eae20-216">Se você não escolher a ramificação correta, sua implantação falhará.</span><span class="sxs-lookup"><span data-stu-id="eae20-216">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="eae20-217">Agora, o seu repositório de origem do DKE está configurado localmente.</span><span class="sxs-lookup"><span data-stu-id="eae20-217">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="eae20-218">Em seguida, [modifique as configurações de aplicativo](#modify-application-settings) para sua organização.</span><span class="sxs-lookup"><span data-stu-id="eae20-218">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="eae20-219">Modificar configurações do aplicativo</span><span class="sxs-lookup"><span data-stu-id="eae20-219">Modify application settings</span></span>

<span data-ttu-id="eae20-220">Para implantar o serviço DKE, você deve modificar os seguintes tipos de configurações de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="eae20-220">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="eae20-221">Configurações de acesso de chave</span><span class="sxs-lookup"><span data-stu-id="eae20-221">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="eae20-222">Definições de locatário e chave</span><span class="sxs-lookup"><span data-stu-id="eae20-222">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="eae20-223">Você modifica as configurações de aplicativo no appsettings.jsem arquivo.</span><span class="sxs-lookup"><span data-stu-id="eae20-223">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="eae20-224">Esse arquivo está localizado no repositório do DoubleKeyEncryptionService que você clonou localmente em DoubleKeyEncryptionService\src\customer-key-store.</span><span class="sxs-lookup"><span data-stu-id="eae20-224">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="eae20-225">Por exemplo, no Visual Studio Code, você pode navegar até o arquivo, conforme mostrado na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="eae20-225">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

:::image type="content" source="../media/dke-appsettingsjson.png" alt-text="Localizar o appsettings.jsno arquivo do DKE.":::

#### <a name="key-access-settings"></a><span data-ttu-id="eae20-227">Configurações de acesso de chave</span><span class="sxs-lookup"><span data-stu-id="eae20-227">Key access settings</span></span>

<span data-ttu-id="eae20-228">Escolha se deseja usar o email ou a autorização de função.</span><span class="sxs-lookup"><span data-stu-id="eae20-228">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="eae20-229">O DKE oferece suporte a apenas um desses métodos de autenticação por vez.</span><span class="sxs-lookup"><span data-stu-id="eae20-229">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="eae20-230">**Autorização de email**.</span><span class="sxs-lookup"><span data-stu-id="eae20-230">**Email authorization**.</span></span> <span data-ttu-id="eae20-231">Permite que sua organização autorize o acesso a chaves com base apenas em endereços de email.</span><span class="sxs-lookup"><span data-stu-id="eae20-231">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="eae20-232">**Autorização de função**.</span><span class="sxs-lookup"><span data-stu-id="eae20-232">**Role authorization**.</span></span> <span data-ttu-id="eae20-233">Permite que sua organização autorize o acesso às chaves com base nos grupos do Active Directory e exige que o serviço Web possa consultar o LDAP.</span><span class="sxs-lookup"><span data-stu-id="eae20-233">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="eae20-234">**Para definir as configurações de acesso de chave do DKE usando autorização de email**</span><span class="sxs-lookup"><span data-stu-id="eae20-234">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="eae20-235">Abra o **appsettings.jsem** arquivo e localize a `AuthorizedEmailAddress` configuração.</span><span class="sxs-lookup"><span data-stu-id="eae20-235">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="eae20-236">Adicione o endereço de email ou endereços que você deseja autorizar.</span><span class="sxs-lookup"><span data-stu-id="eae20-236">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="eae20-237">Separe vários endereços de email com aspas duplas e vírgulas.</span><span class="sxs-lookup"><span data-stu-id="eae20-237">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="eae20-238">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="eae20-238">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="eae20-239">Localize a `LDAPPath` configuração e remova o texto `If role authorization is used then this is the LDAP path` entre aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="eae20-239">Locate the `LDAPPath` setting and remove the text `If role authorization is used then this is the LDAP path` between the double quotes.</span></span> <span data-ttu-id="eae20-240">Deixe as aspas duplas em vigor.</span><span class="sxs-lookup"><span data-stu-id="eae20-240">Leave the double quotes in place.</span></span> <span data-ttu-id="eae20-241">Quando você tiver terminado, a configuração deverá ter a seguinte aparência.</span><span class="sxs-lookup"><span data-stu-id="eae20-241">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="eae20-242">Localize a `AuthorizedRoles` configuração e exclua a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="eae20-242">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="eae20-243">Esta imagem mostra o **appsettings.jsem** arquivo formatado corretamente para autorização de email.</span><span class="sxs-lookup"><span data-stu-id="eae20-243">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   :::image type="content" source="../media/dke-email-accesssetting.png" alt-text="O appsettings.jsem arquivo mostrando o método de autorização de email":::

<span data-ttu-id="eae20-245">**Para definir as configurações de acesso de chave para DKE usando autorização de função**</span><span class="sxs-lookup"><span data-stu-id="eae20-245">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="eae20-246">Abra o **appsettings.jsem** arquivo e localize a `AuthorizedRoles` configuração.</span><span class="sxs-lookup"><span data-stu-id="eae20-246">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="eae20-247">Adicione os nomes de grupo do Active Directory que você deseja autorizar.</span><span class="sxs-lookup"><span data-stu-id="eae20-247">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="eae20-248">Separe vários nomes de grupo com aspas duplas e vírgulas.</span><span class="sxs-lookup"><span data-stu-id="eae20-248">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="eae20-249">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="eae20-249">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="eae20-250">Localize a `LDAPPath` configuração e adicione o domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="eae20-250">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="eae20-251">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="eae20-251">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="eae20-252">Localize a `AuthorizedEmailAddress` configuração e exclua a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="eae20-252">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="eae20-253">Esta imagem mostra o **appsettings.jsem** arquivo formatado corretamente para autorização de função.</span><span class="sxs-lookup"><span data-stu-id="eae20-253">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   :::image type="content" source="../media/dke-role-accesssetting.png" alt-text="appsettings.jsem arquivo mostrando o método de autorização de função":::

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="eae20-255">Definições de locatário e chave</span><span class="sxs-lookup"><span data-stu-id="eae20-255">Tenant and key settings</span></span>

<span data-ttu-id="eae20-256">As configurações de locatário e chave do DKE estão localizadas na **appsettings.jsem** arquivo.</span><span class="sxs-lookup"><span data-stu-id="eae20-256">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="eae20-257">**Para definir as configurações de locatário e chave do DKE**</span><span class="sxs-lookup"><span data-stu-id="eae20-257">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="eae20-258">Abra o **appsettings.jsem** arquivo.</span><span class="sxs-lookup"><span data-stu-id="eae20-258">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="eae20-259">Localize a `ValidIssuers` configuração e substitua `<tenantid>` pela ID do locatário.</span><span class="sxs-lookup"><span data-stu-id="eae20-259">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="eae20-260">Você pode localizar sua ID de locatário indo para o portal do Azure e exibindo as [Propriedades do locatário](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="eae20-260">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="eae20-261">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="eae20-261">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="eae20-262">Localize o `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="eae20-262">Locate the `JwtAudience`.</span></span> <span data-ttu-id="eae20-263">Substitua `<yourhostname>` pelo nome do host do computador em que o serviço DKE será executado.</span><span class="sxs-lookup"><span data-stu-id="eae20-263">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="eae20-264">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="eae20-264">For example:</span></span>



  > [!IMPORTANT]
  > <span data-ttu-id="eae20-265">O valor de `JwtAudience` deve corresponder *exatamente*ao nome do host.</span><span class="sxs-lookup"><span data-stu-id="eae20-265">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="eae20-266">Você pode usar **localhost: 5001** durante a depuração.</span><span class="sxs-lookup"><span data-stu-id="eae20-266">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="eae20-267">No entanto, quando você terminar de depurar, certifique-se de atualizar esse valor para o nome de host do servidor.</span><span class="sxs-lookup"><span data-stu-id="eae20-267">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="eae20-268">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="eae20-268">`TestKeys:Name`.</span></span> <span data-ttu-id="eae20-269">Insira um nome para a chave.</span><span class="sxs-lookup"><span data-stu-id="eae20-269">Enter a name for your key.</span></span> <span data-ttu-id="eae20-270">Por exemplo: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="eae20-270">For example: `TestKey1`</span></span>
- <span data-ttu-id="eae20-271">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="eae20-271">`TestKeys:Id`.</span></span> <span data-ttu-id="eae20-272">Crie um GUID e insira-o como o `TestKeys:ID` valor.</span><span class="sxs-lookup"><span data-stu-id="eae20-272">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="eae20-273">Por exemplo, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span><span class="sxs-lookup"><span data-stu-id="eae20-273">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="eae20-274">Você pode usar um site como [gerador de GUID online](https://guidgenerator.com/) para gerar aleatoriamente um GUID.</span><span class="sxs-lookup"><span data-stu-id="eae20-274">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="eae20-275">Esta imagem mostra o formato correto das configurações de locatário e chaves em **appsettings.js**.</span><span class="sxs-lookup"><span data-stu-id="eae20-275">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="eae20-276">`LDAPPath`é configurada para autorização de função.</span><span class="sxs-lookup"><span data-stu-id="eae20-276">`LDAPPath` is configured for role authorization.</span></span>

:::image type="content" source="../media/dke-appsettingsjson-tenantkeysettings.png" alt-text="Mostra as configurações de locatário e chave corretas para o DKE no arquivo appsettings.js.":::

### <a name="generate-test-keys"></a><span data-ttu-id="eae20-278">Gerar chaves de teste</span><span class="sxs-lookup"><span data-stu-id="eae20-278">Generate test keys</span></span>

<span data-ttu-id="eae20-279">Depois de definir as configurações do aplicativo, você estará pronto para gerar chaves de teste públicas e privadas.</span><span class="sxs-lookup"><span data-stu-id="eae20-279">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="eae20-280">Para gerar chaves:</span><span class="sxs-lookup"><span data-stu-id="eae20-280">To generate keys:</span></span>

1. <span data-ttu-id="eae20-281">No menu Iniciar do Windows, execute o prompt de comando OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="eae20-281">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

1. <span data-ttu-id="eae20-282">Vá para a pasta onde você deseja salvar as teclas de teste.</span><span class="sxs-lookup"><span data-stu-id="eae20-282">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="eae20-283">Os arquivos que você cria ao concluir as etapas dessa tarefa são armazenados na mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="eae20-283">The files you create by completing the steps in this task are stored in the same folder.</span></span>

1. <span data-ttu-id="eae20-284">Gere a nova chave de teste.</span><span class="sxs-lookup"><span data-stu-id="eae20-284">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. <span data-ttu-id="eae20-285">Gerar a chave privada.</span><span class="sxs-lookup"><span data-stu-id="eae20-285">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. <span data-ttu-id="eae20-286">Gere a chave pública.</span><span class="sxs-lookup"><span data-stu-id="eae20-286">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. <span data-ttu-id="eae20-287">Em um editor de texto, abra **pubkeyonly. pem**.</span><span class="sxs-lookup"><span data-stu-id="eae20-287">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="eae20-288">Copie todo o conteúdo do arquivo **pubkeyonly. pem** , exceto a primeira e a última linha, na `PublicPem` seção do **appsettings.jsem** arquivo.</span><span class="sxs-lookup"><span data-stu-id="eae20-288">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="eae20-289">Em um editor de texto, abra **privkeynopass. pem**.</span><span class="sxs-lookup"><span data-stu-id="eae20-289">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="eae20-290">Copie todo o conteúdo do arquivo **privkeynopass. pem** , exceto a primeira e a última linha, na `PrivatePem` seção do **appsettings.jsem** arquivo.</span><span class="sxs-lookup"><span data-stu-id="eae20-290">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="eae20-291">Remova todos os espaços em branco e novas linhas em ambas as `PublicPem` `PrivatePem` seções e.</span><span class="sxs-lookup"><span data-stu-id="eae20-291">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="eae20-292">Ao copiar esse conteúdo, não exclua nenhum dos dados de PEM.</span><span class="sxs-lookup"><span data-stu-id="eae20-292">When you copy this content, do not delete any of the PEM data.</span></span>

1. <span data-ttu-id="eae20-293">No Visual Studio Code, navegue até o arquivo **Startup.cs** .</span><span class="sxs-lookup"><span data-stu-id="eae20-293">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="eae20-294">Esse arquivo está localizado no repositório do DoubleKeyEncryptionService que você clonou localmente em DoubleKeyEncryptionService\src\customer-key-store\.</span><span class="sxs-lookup"><span data-stu-id="eae20-294">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

2. <span data-ttu-id="eae20-295">Localize as seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="eae20-295">Locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

3. <span data-ttu-id="eae20-296">Substitua essas linhas pelo seguinte texto:</span><span class="sxs-lookup"><span data-stu-id="eae20-296">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="eae20-297">Os resultados finais devem ser semelhantes aos seguintes.</span><span class="sxs-lookup"><span data-stu-id="eae20-297">The end results should look similar to the following.</span></span>

   :::image type="content" source="../media/dke-startupcs-usetestkeys.png" alt-text="arquivo startup.cs para visualização pública":::

<span data-ttu-id="eae20-299">Agora você está pronto para [criar seu projeto do DKE](#build-the-project).</span><span class="sxs-lookup"><span data-stu-id="eae20-299">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="eae20-300">Compilar o projeto</span><span class="sxs-lookup"><span data-stu-id="eae20-300">Build the project</span></span>

<span data-ttu-id="eae20-301">Use as instruções a seguir para criar o projeto do DKE localmente:</span><span class="sxs-lookup"><span data-stu-id="eae20-301">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="eae20-302">No Visual Studio Code, no repositório de serviços do DKE, selecione **Exibir** \> **paleta de comandos** e digite **Compilar** no prompt.</span><span class="sxs-lookup"><span data-stu-id="eae20-302">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

1. <span data-ttu-id="eae20-303">Na lista, escolha **tarefas: executar tarefa de compilação**.</span><span class="sxs-lookup"><span data-stu-id="eae20-303">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="eae20-304">Se não houver tarefas de compilação encontradas, selecione **Configurar tarefa de compilação** e criar uma para o .NET Core da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="eae20-304">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   :::image type="content" source="../media/dke-configurebuildtask.png" alt-text="Configurar a tarefa de compilação ausente para o .NET":::

   1. <span data-ttu-id="eae20-306">Escolha **criar tasks.jsno modelo**.</span><span class="sxs-lookup"><span data-stu-id="eae20-306">Choose **Create tasks.json from template**.</span></span>

   :::image type="content" source="../media/dke-createtasksjsonfromtemplate.png" alt-text="Criar tasks.jsno arquivo do modelo do DKE":::

   2. <span data-ttu-id="eae20-308">Na lista de tipos de modelo, selecione **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="eae20-308">From the list of template types, select **.NET Core**.</span></span>

   :::image type="content" source="../media/dke-tasksjsontemplate.png" alt-text="Criar tasks.jsno arquivo do modelo do DKE":::

   3. <span data-ttu-id="eae20-310">Na seção criar, localize o caminho para o arquivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="eae20-310">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="eae20-311">Se ele não estiver lá, adicione a seguinte linha:</span><span class="sxs-lookup"><span data-stu-id="eae20-311">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. <span data-ttu-id="eae20-312">Execute novamente a compilação.</span><span class="sxs-lookup"><span data-stu-id="eae20-312">Run the build again.</span></span>

1. <span data-ttu-id="eae20-313">Verifique se não há nenhum erro vermelho na janela de saída.</span><span class="sxs-lookup"><span data-stu-id="eae20-313">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="eae20-314">Se houver erros vermelhos, verifique a saída do console.</span><span class="sxs-lookup"><span data-stu-id="eae20-314">If there are red errors, check the console output.</span></span> <span data-ttu-id="eae20-315">Verifique se você concluiu todas as etapas anteriores corretamente e se as versões de compilação corretas estão presentes.</span><span class="sxs-lookup"><span data-stu-id="eae20-315">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

2. <span data-ttu-id="eae20-316">Selecione **executar** \> **Iniciar Depuração** para depurar o processo.</span><span class="sxs-lookup"><span data-stu-id="eae20-316">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="eae20-317">Se for solicitado a selecionar um ambiente, selecione **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="eae20-317">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="eae20-318">O depurador do .NET Core normalmente é iniciado em ' ' https://localhost:5001 `. To view your test key, go to ` https://localhost:5001 ' e acrescenta uma barra (/) e o nome da sua chave.</span><span class="sxs-lookup"><span data-stu-id="eae20-318">The .NET core debugger typically launches to \`\`https://localhost:5001`. To view your test key, go to `https://localhost:5001\` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="eae20-319">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="eae20-319">For example:</span></span>

```https
https://localhost:5001/TestKey1
```

<span data-ttu-id="eae20-320">A chave deve ser exibida no formato JSON.</span><span class="sxs-lookup"><span data-stu-id="eae20-320">The key should display in JSON format.</span></span>

<span data-ttu-id="eae20-321">A configuração já está concluída.</span><span class="sxs-lookup"><span data-stu-id="eae20-321">Your setup is now complete.</span></span> <span data-ttu-id="eae20-322">Antes de publicar o repositório de chaves, em appsettings.js, para a configuração do JwtAudience, verifique se o valor do nome do host corresponde exatamente ao nome de host do serviço de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="eae20-322">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="eae20-323">Você pode ter alterado para localhost para solucionar problemas de compilação.</span><span class="sxs-lookup"><span data-stu-id="eae20-323">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="publish-the-key-store"></a><span data-ttu-id="eae20-324">Publicar o repositório de chaves</span><span class="sxs-lookup"><span data-stu-id="eae20-324">Publish the key store</span></span>

<span data-ttu-id="eae20-325">Para publicar o repositório de chaves, você criará uma instância do serviço de aplicativo do Azure para hospedar sua implantação do DKE.</span><span class="sxs-lookup"><span data-stu-id="eae20-325">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="eae20-326">Em seguida, você publicará as chaves geradas no Azure.</span><span class="sxs-lookup"><span data-stu-id="eae20-326">Next, you'll publish your generated keys to Azure.</span></span>

<span data-ttu-id="eae20-327">**Para criar uma instância do Azure Web App para hospedar sua implantação do DKE**</span><span class="sxs-lookup"><span data-stu-id="eae20-327">**To create an Azure Web App instance to host your DKE deployment**</span></span>

1. <span data-ttu-id="eae20-328">No navegador, entre no [portal do Microsoft Azure](https://ms.portal.azure.com)e vá para a adição de **serviços de aplicativo**  >  **Add**.</span><span class="sxs-lookup"><span data-stu-id="eae20-328">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

1. <span data-ttu-id="eae20-329">Selecione sua assinatura e o grupo de recursos e defina os detalhes da instância.</span><span class="sxs-lookup"><span data-stu-id="eae20-329">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="eae20-330">Insira o nome de host do computador onde você deseja instalar o serviço DKE.</span><span class="sxs-lookup"><span data-stu-id="eae20-330">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="eae20-331">Certifique-se de que é o mesmo nome que o definido para a configuração JwtAudience no arquivo de [**appsettings.js**](#tenant-and-key-settings) .</span><span class="sxs-lookup"><span data-stu-id="eae20-331">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="eae20-332">O valor que você fornece para o nome também é o WebAppInstanceName.</span><span class="sxs-lookup"><span data-stu-id="eae20-332">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="eae20-333">Para **publicar**, selecione **código**e para **pilha de tempo de execução**, selecione **.NET Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="eae20-333">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="eae20-334">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="eae20-334">For example:</span></span>

    :::image type="content" source="../media/dke-azure-add-app-service.png" alt-text="Adicionar seu serviço de aplicativo":::

1. <span data-ttu-id="eae20-336">Na parte inferior da página, selecione **revisar + criar**e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="eae20-336">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

1. <span data-ttu-id="eae20-337">Siga um destes procedimentos para publicar suas chaves geradas no Azure:</span><span class="sxs-lookup"><span data-stu-id="eae20-337">Do one of the following to publish your generated keys to Azure:</span></span>

    - [<span data-ttu-id="eae20-338">Publicar via ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="eae20-338">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="eae20-339">Publicar via FTP</span><span class="sxs-lookup"><span data-stu-id="eae20-339">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="eae20-340">Publicar via Visual Studio 2019 ou posterior</span><span class="sxs-lookup"><span data-stu-id="eae20-340">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [<span data-ttu-id="eae20-341">Publicar em um sistema local</span><span class="sxs-lookup"><span data-stu-id="eae20-341">Publish to an on-premises system</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > <span data-ttu-id="eae20-342">Você pode preferir outros métodos para implantar suas chaves.</span><span class="sxs-lookup"><span data-stu-id="eae20-342">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="eae20-343">Selecione o método que funciona melhor para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="eae20-343">Select the method that works best for your organization.</span></span>

    > [!TIP]
    > <span data-ttu-id="eae20-344">A [publicação via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) e para um [sistema local](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) é descrita na documentação do [ASP .net](https://docs.microsoft.com/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="eae20-344">[Publishing via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) and to an [on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) is described in the [ASP .NET documentation](https://docs.microsoft.com/aspnet/core/).</span></span> <span data-ttu-id="eae20-345">Se você usar um desses métodos, abra as instruções em uma guia separada para que você possa retornar aqui facilmente quando tiver concluído.</span><span class="sxs-lookup"><span data-stu-id="eae20-345">If you use one of these methods, open the instructions in a separate tab so that you can return here easily when you're done.</span></span>

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="eae20-346">Publicar via ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="eae20-346">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="eae20-347">Acesse `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span><span class="sxs-lookup"><span data-stu-id="eae20-347">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="eae20-348">Por exemplo: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="eae20-348">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

1. <span data-ttu-id="eae20-349">Na base de código do armazenamento de chaves, vá para a pasta **Customer-Key-store\src\customer-Key-Store** e verifique se essa pasta contém o arquivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="eae20-349">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="eae20-350">Executar: **publicação de dotnet**</span><span class="sxs-lookup"><span data-stu-id="eae20-350">Run: **dotnet publish**</span></span>

     <span data-ttu-id="eae20-351">A janela saída exibe o diretório onde a publicação foi implantada.</span><span class="sxs-lookup"><span data-stu-id="eae20-351">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="eae20-352">Por exemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="eae20-352">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="eae20-353">Envie todos os arquivos no diretório de publicação para um arquivo. zip.</span><span class="sxs-lookup"><span data-stu-id="eae20-353">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="eae20-354">Ao criar o arquivo. zip, verifique se todos os arquivos no diretório estão no nível raiz do arquivo. zip.</span><span class="sxs-lookup"><span data-stu-id="eae20-354">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="eae20-355">Arraste e solte o arquivo. zip criado no site do ZipDeployUI que você abriu acima.</span><span class="sxs-lookup"><span data-stu-id="eae20-355">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="eae20-356">Por exemplo: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="eae20-356">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="eae20-357">O DKE é implantado e você pode navegar até as chaves de teste que você criou.</span><span class="sxs-lookup"><span data-stu-id="eae20-357">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="eae20-358">Continue para [validar sua implantação](#validate-your-deployment) abaixo.</span><span class="sxs-lookup"><span data-stu-id="eae20-358">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="eae20-359">Publicar via FTP</span><span class="sxs-lookup"><span data-stu-id="eae20-359">Publish via FTP</span></span>

1. <span data-ttu-id="eae20-360">Conecte-se ao serviço de aplicativo que você criou [acima](#publish-the-key-store).</span><span class="sxs-lookup"><span data-stu-id="eae20-360">Connect to the App Service you created [above](#publish-the-key-store).</span></span>

    <span data-ttu-id="eae20-361">Em seu navegador, vá para: centro de implantação do serviço de aplicativo **do portal do Azure**  >  **App Service**  >  **Deployment Center**  >  painel de FTP de**implantação manual**  >  **FTP**  >  **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="eae20-361">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

1. <span data-ttu-id="eae20-362">Copie as cadeias de conexão exibidas para um arquivo local.</span><span class="sxs-lookup"><span data-stu-id="eae20-362">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="eae20-363">Você usará essas cadeias de caracteres para se conectar ao serviço do aplicativo Web e carregar arquivos via FTP.</span><span class="sxs-lookup"><span data-stu-id="eae20-363">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="eae20-364">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="eae20-364">For example:</span></span>

    :::image type="content" source="../media/dke-ftp-dashboard.png" alt-text="Copiar cadeias de conexão do painel de FTP":::

1. <span data-ttu-id="eae20-366">Na base de código do armazenamento principal, vá para o **diretório Customer-Key-store\src\customer-Key-Store**</span><span class="sxs-lookup"><span data-stu-id="eae20-366">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

1. <span data-ttu-id="eae20-367">Verifique se esse diretório contém o arquivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="eae20-367">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="eae20-368">Executar: **publicação de dotnet**</span><span class="sxs-lookup"><span data-stu-id="eae20-368">Run: **dotnet publish**</span></span>

    <span data-ttu-id="eae20-369">A saída contém o diretório onde a publicação foi implantada.</span><span class="sxs-lookup"><span data-stu-id="eae20-369">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="eae20-370">Por exemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="eae20-370">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="eae20-371">Envie todos os arquivos no diretório de publicação para um arquivo zip.</span><span class="sxs-lookup"><span data-stu-id="eae20-371">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="eae20-372">Ao criar o arquivo. zip, verifique se todos os arquivos no diretório estão no nível raiz do arquivo. zip.</span><span class="sxs-lookup"><span data-stu-id="eae20-372">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="eae20-373">No cliente FTP, use as informações de conexão que você copiou para se conectar ao serviço de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="eae20-373">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="eae20-374">Carregue o arquivo. zip que você criou na etapa anterior para o diretório raiz do seu aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="eae20-374">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="eae20-375">DKE é implantado e você pode navegar para as teclas de teste que você criou.</span><span class="sxs-lookup"><span data-stu-id="eae20-375">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="eae20-376">Em seguida, [valide sua implantação](#validate-your-deployment).</span><span class="sxs-lookup"><span data-stu-id="eae20-376">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="eae20-377">Validar sua implantação</span><span class="sxs-lookup"><span data-stu-id="eae20-377">Validate your deployment</span></span>

<span data-ttu-id="eae20-378">Depois de implantar o DKE usando um dos métodos descritos acima, valide a implantação e as configurações do armazenamento de chaves.</span><span class="sxs-lookup"><span data-stu-id="eae20-378">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="eae20-379">Sejam</span><span class="sxs-lookup"><span data-stu-id="eae20-379">Run:</span></span>

<span data-ttu-id="eae20-380">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/MyKey</span><span class="sxs-lookup"><span data-stu-id="eae20-380">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span></span>

<span data-ttu-id="eae20-381">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="eae20-381">For example:</span></span>

<span data-ttu-id="eae20-382">key_store_tester.ps1https://mycustomerkeystore.com/mykey</span><span class="sxs-lookup"><span data-stu-id="eae20-382">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span></span>

<span data-ttu-id="eae20-383">Certifique-se de que nenhum erro apareça na saída.</span><span class="sxs-lookup"><span data-stu-id="eae20-383">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="eae20-384">Quando estiver pronto, [Registre o repositório de chaves](#register-your-key-store).</span><span class="sxs-lookup"><span data-stu-id="eae20-384">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="eae20-385">Registrar seu repositório de chaves</span><span class="sxs-lookup"><span data-stu-id="eae20-385">Register your key store</span></span>

<span data-ttu-id="eae20-386">As etapas a seguir permitem que você registre seu repositório de chaves.</span><span class="sxs-lookup"><span data-stu-id="eae20-386">The following steps enable you to register your key store.</span></span> <span data-ttu-id="eae20-387">O registro do armazenamento de chaves é a última etapa na implantação do DKE antes que você possa começar a criar rótulos.</span><span class="sxs-lookup"><span data-stu-id="eae20-387">Registering your key store is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="eae20-388">Para registrar seu repositório de chave:</span><span class="sxs-lookup"><span data-stu-id="eae20-388">To register your key store:</span></span>

1. <span data-ttu-id="eae20-389">No navegador, abra o [portal do Microsoft Azure](https://ms.portal.azure.com/)e vá para **todos os** \> registros de aplicativos de **identidade** de serviços \> **App Registrations**.</span><span class="sxs-lookup"><span data-stu-id="eae20-389">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="eae20-390">Selecione **novo registro**e insira um nome significativo.</span><span class="sxs-lookup"><span data-stu-id="eae20-390">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="eae20-391">Selecione um tipo de conta nas opções exibidas.</span><span class="sxs-lookup"><span data-stu-id="eae20-391">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="eae20-392">Se você estiver usando o Microsoft Azure com um domínio não personalizado, como **onmicrosoft.com**, selecione **contas nesse diretório organizacional apenas (somente para o Microsoft locatário).**</span><span class="sxs-lookup"><span data-stu-id="eae20-392">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="eae20-393">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="eae20-393">For example:</span></span>

    :::image type="content" source="../media/dke-app-registration.png" alt-text="Novo registro de aplicativo":::

4. <span data-ttu-id="eae20-395">Na parte inferior da página, selecione **registrar** para criar o novo registro de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="eae20-395">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="eae20-396">No novo registro de aplicativo, no painel esquerdo, em **gerenciar**, selecione **autenticação**.</span><span class="sxs-lookup"><span data-stu-id="eae20-396">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="eae20-397">Selecione **Adicionar uma plataforma**.</span><span class="sxs-lookup"><span data-stu-id="eae20-397">Select **Add a platform**.</span></span>
 
7. <span data-ttu-id="eae20-398">No pop-up **Configurar plataformas** , selecione **Web**.</span><span class="sxs-lookup"><span data-stu-id="eae20-398">On the **Configure platforms** popup, select **Web**.</span></span>
 
8. <span data-ttu-id="eae20-399">Em **URIs de redirecionamento**, insira o URI do serviço de criptografia de chave dupla.</span><span class="sxs-lookup"><span data-stu-id="eae20-399">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="eae20-400">Insira a URL do serviço de aplicativo, incluindo o nome do host e o domínio.</span><span class="sxs-lookup"><span data-stu-id="eae20-400">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="eae20-401">Por exemplo: https://mycustomerkeystoretest.com</span><span class="sxs-lookup"><span data-stu-id="eae20-401">For example: https://mycustomerkeystoretest.com</span></span>

    - <span data-ttu-id="eae20-402">A URL inserida deve corresponder ao nome de host onde o repositório de chave está implantado.</span><span class="sxs-lookup"><span data-stu-id="eae20-402">The URL you enter must match the hostname where your key store is deployed.</span></span>
    - <span data-ttu-id="eae20-403">Se você estiver testando localmente com o Visual Studio, use **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="eae20-403">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="eae20-404">Em todos os casos, o esquema deve ser **https**.</span><span class="sxs-lookup"><span data-stu-id="eae20-404">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="eae20-405">Certifique-se de que o nome do host corresponde exatamente ao nome de host do serviço de aplicativo</span><span class="sxs-lookup"><span data-stu-id="eae20-405">Ensure the hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="eae20-406">Você pode ter alterado para `localhost` solucionar problemas de compilação.</span><span class="sxs-lookup"><span data-stu-id="eae20-406">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="eae20-407">Em **appsettings.js**, esse valor é o nome de host definido para `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="eae20-407">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

6. <span data-ttu-id="eae20-408">Em **concessão implícita**, selecione a caixa de seleção **tokens de ID** .</span><span class="sxs-lookup"><span data-stu-id="eae20-408">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

1. <span data-ttu-id="eae20-409">Clique em **Salvar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="eae20-409">Select **Save** to save your changes.</span></span>

7. <span data-ttu-id="eae20-410">No painel esquerdo, selecione **expor uma API**e, em seguida, ao lado de URI da ID do aplicativo, selecione **definir**.</span><span class="sxs-lookup"><span data-stu-id="eae20-410">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

9. <span data-ttu-id="eae20-411">Ainda na página de **exibir uma API** , na área **escopos definidos por esta API** , selecione **Adicionar um escopo**.</span><span class="sxs-lookup"><span data-stu-id="eae20-411">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="eae20-412">No novo escopo:</span><span class="sxs-lookup"><span data-stu-id="eae20-412">In the new scope:</span></span>

    1. <span data-ttu-id="eae20-413">Defina o nome do escopo como **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="eae20-413">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="eae20-414">Selecione os administradores e usuários que podem autorizar.</span><span class="sxs-lookup"><span data-stu-id="eae20-414">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="eae20-415">Defina os valores restantes necessários.</span><span class="sxs-lookup"><span data-stu-id="eae20-415">Define any remaining values required.</span></span>

    4. <span data-ttu-id="eae20-416">Selecione **Adicionar escopo.**</span><span class="sxs-lookup"><span data-stu-id="eae20-416">Select **Add scope.**</span></span>

    <span data-ttu-id="eae20-417">Selecione **salvar** na parte superior para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="eae20-417">Select **Save** at the top to save your changes.</span></span>

10. <span data-ttu-id="eae20-418">Ainda na página **expor uma API** , na área **aplicativos cliente autorizados** , selecione **Adicionar um aplicativo cliente**.</span><span class="sxs-lookup"><span data-stu-id="eae20-418">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="eae20-419">No novo aplicativo cliente:</span><span class="sxs-lookup"><span data-stu-id="eae20-419">In the new client application:</span></span>

    1. <span data-ttu-id="eae20-420">Defina a ID do cliente como **d3590ed6-52B3-4102-AEFF-aad2292ab01c**.</span><span class="sxs-lookup"><span data-stu-id="eae20-420">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="eae20-421">Esse valor é a ID de cliente do Microsoft Office e permite que o Office obtenha um token de acesso para o armazenamento de chaves.</span><span class="sxs-lookup"><span data-stu-id="eae20-421">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="eae20-422">Em **escopos autorizados**, selecione o escopo de **user_impersonation** .</span><span class="sxs-lookup"><span data-stu-id="eae20-422">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="eae20-423">Selecione **Adicionar aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="eae20-423">Select **Add application**.</span></span>

    4. <span data-ttu-id="eae20-424">Selecione **salvar** na parte superior para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="eae20-424">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="eae20-425">O armazenamento de chave do DKE agora está registrado.</span><span class="sxs-lookup"><span data-stu-id="eae20-425">Your DKE key store is now registered.</span></span> <span data-ttu-id="eae20-426">Continue [criando rótulos usando o DKE](#create-labels-using-dke).</span><span class="sxs-lookup"><span data-stu-id="eae20-426">Continue by [creating labels using DKE](#create-labels-using-dke).</span></span>

## <a name="create-labels-using-dke"></a><span data-ttu-id="eae20-427">Criar rótulos usando DKE</span><span class="sxs-lookup"><span data-stu-id="eae20-427">Create labels using DKE</span></span>

<span data-ttu-id="eae20-428">No centro de conformidade da Microsoft 365, crie um novo rótulo de confidencialidade e aplique a criptografia como faria de outra forma.</span><span class="sxs-lookup"><span data-stu-id="eae20-428">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="eae20-429">Selecione **usar criptografia de chave dupla** e digite a URL do ponto de extremidade da sua chave.</span><span class="sxs-lookup"><span data-stu-id="eae20-429">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="eae20-430">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="eae20-430">For example:</span></span>

:::image type="content" source="../media/dke-use-dke.png" alt-text="Selecione usar criptografia de chave dupla no centro de conformidade do Microsoft 365":::

<span data-ttu-id="eae20-432">Quaisquer rótulos do DKE que você adicionar serão iniciados para os usuários nas versões mais recentes dos aplicativos do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="eae20-432">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="eae20-433">Pode levar até 24 horas para que os clientes sejam atualizados com os novos rótulos.</span><span class="sxs-lookup"><span data-stu-id="eae20-433">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="eae20-434">Habilitar o DKE no cliente</span><span class="sxs-lookup"><span data-stu-id="eae20-434">Enable DKE in your client</span></span>

<span data-ttu-id="eae20-435">Se os rótulos do DKE não aparecerem na faixa de opções de confidencialidade no Microsoft Office, o cliente pode não ter o DKE habilitado.</span><span class="sxs-lookup"><span data-stu-id="eae20-435">If your DKE labels don't appear under the Sensitivity ribbon in Microsoft Office, your client may not have DKE enabled.</span></span>

<span data-ttu-id="eae20-436">Habilite o DKE para o cliente adicionando as seguintes chaves do registro:</span><span class="sxs-lookup"><span data-stu-id="eae20-436">Enable DKE for your client by adding the following registry keys:</span></span>

```ini
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
