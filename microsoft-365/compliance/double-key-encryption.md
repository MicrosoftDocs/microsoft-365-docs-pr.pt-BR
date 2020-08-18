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
ms.openlocfilehash: f36eeeb1f228bff48088cbbf3241d6866d0b3a21
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794160"
---
# <a name="double-key-encryption-dke"></a><span data-ttu-id="9ec2d-103">DKE (criptografia de chave dupla)</span><span class="sxs-lookup"><span data-stu-id="9ec2d-103">Double Key Encryption (DKE)</span></span>

> <span data-ttu-id="9ec2d-104">*Aplica-se a: chave dupla de criptografia para o Microsoft 365 Public Preview, [microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [proteção de informações do Azure](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="9ec2d-104">*Applies to: Double Key Encryption for Microsoft 365 public preview, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="9ec2d-105">*Instruções para: [cliente de rotulação unificada de proteção de informações do Azure para Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="9ec2d-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="9ec2d-106">*Descrição do serviço para: conformidade com a [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="9ec2d-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="9ec2d-107">A criptografia de chave dupla (DKE) usa duas chaves juntas para acessar o conteúdo protegido.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="9ec2d-108">Você armazena uma chave no Microsoft Azure e mantém a outra chave.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-108">You store one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="9ec2d-109">O cliente de rotulação unificado de proteção de informações do Azure protege o conteúdo altamente confidencial enquanto você mantém o controle total de uma de suas chaves.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-109">The Azure Information Protection unified labeling client protects highly sensitive content while you maintain full control of one of your keys.</span></span>

<span data-ttu-id="9ec2d-110">A criptografia de chave dupla oferece suporte a implantações no local e na nuvem.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-110">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="9ec2d-111">Essas implantações ajudam a garantir que os dados criptografados permaneçam opaco onde quer você armazene os dados protegidos.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-111">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="9ec2d-112">Para obter mais informações sobre as chaves de raiz de locatários padrão baseadas em nuvem, consulte [Planning and Implementing Your Azure Information Protection locatário Key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span><span class="sxs-lookup"><span data-stu-id="9ec2d-112">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

<!--
The following video shows how Double Key Encryption works to secure your content.

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]
-->

<span data-ttu-id="9ec2d-113">Se as suas organizações têm qualquer um dos seguintes requisitos, você pode usar o DKE para ajudar a proteger o conteúdo:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-113">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="9ec2d-114">Você quer garantir que *apenas você* possa descriptografar o conteúdo protegido, em todas as circunstâncias.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-114">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="9ec2d-115">Você não deseja que a Microsoft tenha acesso a dados protegidos por conta própria.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-115">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="9ec2d-116">Você tem requisitos normativos para manter chaves dentro de um limite geográfico.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-116">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="9ec2d-117">Todas as chaves que você mantém para criptografia e descriptografia de dados são mantidas em seu data center.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-117">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="9ec2d-118">Requisitos de sistema e licenciamento para o DKE</span><span class="sxs-lookup"><span data-stu-id="9ec2d-118">System and licensing requirements for DKE</span></span>

<span data-ttu-id="9ec2d-119">A chave dupla de criptografia para o Microsoft 365 vem com o Microsoft 365 E5 e o Office 365 e5.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-119">Double Key Encryption for Microsoft 365 comes with Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="9ec2d-120">Se você não tem uma licença do Microsoft 365 e5, é possível inscrever-se em uma [avaliação](https://aka.ms/M365E5ComplianceTrial).</span><span class="sxs-lookup"><span data-stu-id="9ec2d-120">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="9ec2d-121">Para obter mais informações sobre essas licenças, consulte [diretrizes de licenciamento da Microsoft 365 para segurança & conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="9ec2d-121">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="9ec2d-122">**Office Insider** Para usar a visualização pública, você deve ser membro do programa Office Insider.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-122">**Office Insider** To use the public preview, you must be a member of the Office Insider program.</span></span> <span data-ttu-id="9ec2d-123">Para ingressar no Office Insider, vá para [https://insider.office.com](https://insider.office.com) .</span><span class="sxs-lookup"><span data-stu-id="9ec2d-123">To join Office Insider, go to [https://insider.office.com](https://insider.office.com).</span></span> <span data-ttu-id="9ec2d-124">Quando você for membro, prepare o ambiente para implantar o Office Insider compilações escolhendo o método de implantação certo para sua organização.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-124">Once you're a member, prepare your environment to deploy Office Insider builds by choosing the right deployment method for your organization.</span></span> <span data-ttu-id="9ec2d-125">Para obter instruções, consulte [introdução à implantação de compilações do Office Insider](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="9ec2d-125">For instructions, see [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="9ec2d-126">**Proteção de informações do Azure**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-126">**Azure Information Protection**.</span></span> <span data-ttu-id="9ec2d-127">O DKE funciona com rótulos de sensibilidade e requer a proteção de informações do Azure.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-127">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="9ec2d-128">Ambientes suportados para armazenar e exibir o conteúdo protegido por DKE</span><span class="sxs-lookup"><span data-stu-id="9ec2d-128">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="9ec2d-129">**Aplicativos com suporte**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-129">**Supported applications**.</span></span> <span data-ttu-id="9ec2d-130">[Microsoft 365 aplicativos para clientes corporativos](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) no Windows, incluindo Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-130">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="9ec2d-131">**Suporte a conteúdo online**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-131">**Online content support**.</span></span> <span data-ttu-id="9ec2d-132">Há suporte para documentos e arquivos armazenados online no Microsoft SharePoint e no OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-132">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="9ec2d-133">Você pode compartilhar conteúdo criptografado por email, mas não pode exibir documentos e arquivos criptografados online.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-133">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="9ec2d-134">Em vez disso, você deve exibir o conteúdo protegido usando os aplicativos de área de trabalho no computador local.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-134">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="about-this-public-preview-article"></a><span data-ttu-id="9ec2d-135">Sobre este artigo de demonstração pública</span><span class="sxs-lookup"><span data-stu-id="9ec2d-135">About this public preview article</span></span>

<span data-ttu-id="9ec2d-136">Há várias maneiras de realizar algumas das etapas para implantar a criptografia de chave dupla.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-136">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="9ec2d-137">Este artigo fornece instruções detalhadas para que administradores menos experientes implantem o serviço com êxito.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-137">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="9ec2d-138">Se você estiver confortável para fazer isso, você pode optar por usar seus próprios métodos.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-138">If you're comfortable doing so, you can choose to use your own methods.</span></span>

<span data-ttu-id="9ec2d-139">Este artigo inclui instruções passo a passo sobre como implantar o serviço de criptografia de chave dupla no Azure.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-139">This article includes step-by-step instructions on how to deploy the Double Key Encryption service to Azure.</span></span> <span data-ttu-id="9ec2d-140">Esse cenário não é algo que você provavelmente faria em produção.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-140">This scenario isn't something you'd likely do in production.</span></span> <span data-ttu-id="9ec2d-141">Para visualização pública, usar o Azure é uma maneira rápida de implantar o DKE.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-141">For public preview, using Azure is a quick way to deploy DKE.</span></span> <span data-ttu-id="9ec2d-142">A implantação do Azure permite que você comece a usar a criptografia de chave dupla imediatamente.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-142">Deploying to Azure lets you get started using Double Key Encryption right away.</span></span>

<span data-ttu-id="9ec2d-143">Você pode implantar o serviço localmente em sua rede ou com outro provedor.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-143">You can deploy the service locally on your network or with another provider.</span></span> <span data-ttu-id="9ec2d-144">Você precisará publicar o repositório de chaves usando métodos apropriados para esse local.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-144">You'll need to publish the key store using methods that are appropriate for that location.</span></span>

## <a name="deploy-double-key-encryption"></a><span data-ttu-id="9ec2d-145">Implantar a criptografia de chave dupla</span><span class="sxs-lookup"><span data-stu-id="9ec2d-145">Deploy Double Key Encryption</span></span>

<span data-ttu-id="9ec2d-146">Este artigo e o vídeo de implantação usam o Azure como o destino de implantação para o serviço DKE.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-146">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="9ec2d-147">Se você estiver implantando em outro local, precisará fornecer seus próprios valores.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-147">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="9ec2d-148">Assista ao [vídeo de implantação de criptografia de duas chaves](https://youtu.be/vDWfHN_kygg) para ver a visão geral passo a passo dos conceitos no artigo.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-148">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see step-by-step overview of concepts in the article.</span></span> <span data-ttu-id="9ec2d-149">O vídeo leva cerca de 18 minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-149">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="9ec2d-150">Siga estas etapas gerais para configurar a criptografia de chave dupla para sua organização.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-150">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="9ec2d-151">Instalar pré-requisitos de software</span><span class="sxs-lookup"><span data-stu-id="9ec2d-151">Install software prerequisites</span></span>](#install-software-prerequisites)
1. [<span data-ttu-id="9ec2d-152">Clone o repositório do GitHub de criptografia de chave dupla</span><span class="sxs-lookup"><span data-stu-id="9ec2d-152">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="9ec2d-153">Modificar configurações do aplicativo</span><span class="sxs-lookup"><span data-stu-id="9ec2d-153">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="9ec2d-154">Gerar chaves de teste</span><span class="sxs-lookup"><span data-stu-id="9ec2d-154">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="9ec2d-155">Compilar o projeto</span><span class="sxs-lookup"><span data-stu-id="9ec2d-155">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="9ec2d-156">Publicar o repositório de chaves</span><span class="sxs-lookup"><span data-stu-id="9ec2d-156">Publish the key store</span></span>](#publish-the-key-store)
1. [<span data-ttu-id="9ec2d-157">Validar sua implantação</span><span class="sxs-lookup"><span data-stu-id="9ec2d-157">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="9ec2d-158">Registrar seu repositório de chaves</span><span class="sxs-lookup"><span data-stu-id="9ec2d-158">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="9ec2d-159">Criar rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="9ec2d-159">Create sensitivity labels</span></span>](#create-labels-using-dke)

<span data-ttu-id="9ec2d-160">Quando tiver concluído, você poderá criptografar documentos e arquivos usando o DKE.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-160">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="9ec2d-161">Para saber mais, confira [aplicar rótulos de confidencialidade aos seus arquivos e emails no Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span><span class="sxs-lookup"><span data-stu-id="9ec2d-161">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites"></a><span data-ttu-id="9ec2d-162">Instalar pré-requisitos de software</span><span class="sxs-lookup"><span data-stu-id="9ec2d-162">Install software prerequisites</span></span>

<span data-ttu-id="9ec2d-163">Há dois tipos de pré-requisitos de software para a criptografia de chave dupla</span><span class="sxs-lookup"><span data-stu-id="9ec2d-163">There are two types of software prerequisites for Double Key Encryption</span></span>

- [<span data-ttu-id="9ec2d-164">Pré-requisitos do serviço de criptografia de chave dupla</span><span class="sxs-lookup"><span data-stu-id="9ec2d-164">Double Key Encryption service prerequisites</span></span>](#double-key-encryption-service-prerequisites)
- [<span data-ttu-id="9ec2d-165">Pré-requisitos de criptografia de chave dupla para computadores clientes</span><span class="sxs-lookup"><span data-stu-id="9ec2d-165">Double Key Encryption prerequisites for client computers</span></span>](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a><span data-ttu-id="9ec2d-166">Pré-requisitos do serviço de criptografia de chave dupla</span><span class="sxs-lookup"><span data-stu-id="9ec2d-166">Double Key Encryption service prerequisites</span></span>

<span data-ttu-id="9ec2d-167">Instale esses pré-requisitos no computador onde você deseja instalar o serviço DKE.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-167">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="9ec2d-168">**SDK do .NET Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-168">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="9ec2d-169">Baixe e instale o SDK do [download do .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="9ec2d-169">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="9ec2d-170">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-170">**Visual Studio Code**.</span></span> <span data-ttu-id="9ec2d-171">Baixe o Visual Studio Code de [https://code.visualstudio.com/](https://code.visualstudio.com) .</span><span class="sxs-lookup"><span data-stu-id="9ec2d-171">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="9ec2d-172">Depois de instalado, execute o Visual Studio Code e selecione **View** \> **Extensions**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-172">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="9ec2d-173">Instale essas extensões.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-173">Install these extensions.</span></span>

- <span data-ttu-id="9ec2d-174">C# para o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="9ec2d-174">C# for Visual Studio Code</span></span>

- <span data-ttu-id="9ec2d-175">Gerenciador de pacotes do NuGet</span><span class="sxs-lookup"><span data-stu-id="9ec2d-175">NuGet Package Manager</span></span>

<span data-ttu-id="9ec2d-176">**Microsoft Office Insider**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-176">**Microsoft Office Insider**.</span></span> <span data-ttu-id="9ec2d-177">Configure pelo menos um [método de implantação](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="9ec2d-177">Set up at least one [deployment method](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="9ec2d-178">**Recursos git**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-178">**Git resources**.</span></span> <span data-ttu-id="9ec2d-179">Baixe e instale um dos seguintes.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-179">Download and install one of the following.</span></span>

- [<span data-ttu-id="9ec2d-180">Git</span><span class="sxs-lookup"><span data-stu-id="9ec2d-180">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="9ec2d-181">Área de trabalho do GitHub</span><span class="sxs-lookup"><span data-stu-id="9ec2d-181">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="9ec2d-182">GitHub corporativo</span><span class="sxs-lookup"><span data-stu-id="9ec2d-182">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="9ec2d-183">**OpenSSL** Você deve ter o [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) instalado para [gerar chaves de teste](#generate-test-keys) depois de implantar o DKE.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-183">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="9ec2d-184">Certifique-se de que você está invocando-o corretamente de seu caminho de variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-184">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="9ec2d-185">Por exemplo, consulte "Adicionar o diretório de instalação ao caminho" https://www.osradar.com/install-openssl-windows/ para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-185">For example, see "Add the installation directory to PATH" at https://www.osradar.com/install-openssl-windows/ for details.</span></span>

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a><span data-ttu-id="9ec2d-186">Pré-requisitos de criptografia de chave dupla para computadores clientes</span><span class="sxs-lookup"><span data-stu-id="9ec2d-186">Double Key Encryption prerequisites for client computers</span></span>

<span data-ttu-id="9ec2d-187">Instale esses pré-requisitos em cada computador cliente onde você deseja proteger e consumir documentos protegidos.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-187">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="9ec2d-188">**Microsoft Office** versão \*. 12711 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-188">**Microsoft Office** version \*.12711 or later.</span></span>

<span data-ttu-id="9ec2d-189">Versões **unificadas de rótulo do cliente de proteção de informações do Azure** 2.7.93.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-189">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="9ec2d-190">Baixe e instale o cliente de rotulação unificada da [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="9ec2d-190">Download and install the Unified Labeling client from [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="9ec2d-191">Clonar o repositório do GitHub DKE</span><span class="sxs-lookup"><span data-stu-id="9ec2d-191">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="9ec2d-192">A Microsoft fornece os arquivos de origem do DKE em um repositório do GitHub.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-192">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="9ec2d-193">Você clona o repositório para compilar o projeto localmente para uso da sua organização.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-193">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="9ec2d-194">O repositório do GitHub do DKE está localizado em [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="9ec2d-194">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="9ec2d-195">As instruções a seguir se destinam a usuários do git ou do Visual Studio Code inexperientes:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-195">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="9ec2d-196">No navegador, acesse: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span><span class="sxs-lookup"><span data-stu-id="9ec2d-196">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span></span>

1. <span data-ttu-id="9ec2d-197">No lado direito da tela, selecione **código**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-197">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="9ec2d-198">Sua versão da interface do usuário pode mostrar um botão **clone ou download** .</span><span class="sxs-lookup"><span data-stu-id="9ec2d-198">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="9ec2d-199">Em seguida, na lista suspensa exibida, selecione o ícone Copiar para copiar a URL para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-199">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="9ec2d-200">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-200">For example:</span></span>

   ![Clonar o repositório de serviço de criptografia de chave dupla do GitHub](../media/dke-clone.png)

3. <span data-ttu-id="9ec2d-202">No Visual Studio Code, selecione **Exibir** \> **paleta de comandos** e selecione **git: clonar**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-202">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="9ec2d-203">Para ir para a opção na lista, comece a digitar `git: clone` para filtrar as entradas e, em seguida, selecione-a no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-203">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="9ec2d-204">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-204">For example:</span></span>

   ![Visual Studio Code GIT: opção clone](../media/dke-vscode-clone.png)

4. <span data-ttu-id="9ec2d-206">Na caixa de texto, Cole a URL que você copiou do git e selecione **clonar do GitHub**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-206">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="9ec2d-207">Na caixa de diálogo **Selecionar pasta** exibida, procure e selecione um local para armazenar o repositório.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-207">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="9ec2d-208">No prompt, selecione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-208">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="9ec2d-209">O repositório é aberto no Visual Studio Code e exibe a ramificação atual do git no canto inferior esquerdo.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-209">The repository is opened in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="9ec2d-210">A ramificação deve ser **mestra**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-210">The branch should be **master**.</span></span>

    <span data-ttu-id="9ec2d-211">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-211">For example:</span></span>

   ![Ramificação do Visual Studio Code Master](../media/dke-vscode-master.png)

6. <span data-ttu-id="9ec2d-213">Selecione o Word **Master** e, em seguida, selecione **public_preview** na lista de ramificações.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-213">Select the word **master,** and then select **public_preview** from the list of branches.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="9ec2d-214">Selecionar a ramificação public_preview garante que você tenha os arquivos corretos para compilar o projeto.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-214">Selecting the public_preview branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="9ec2d-215">Se você não escolher a ramificação correta, sua implantação falhará.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-215">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="9ec2d-216">Agora, o seu repositório de origem do DKE está configurado localmente.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-216">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="9ec2d-217">Em seguida, [modifique as configurações de aplicativo](#modify-application-settings) para sua organização.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-217">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="9ec2d-218">Modificar configurações do aplicativo</span><span class="sxs-lookup"><span data-stu-id="9ec2d-218">Modify application settings</span></span>

<span data-ttu-id="9ec2d-219">Para implantar o serviço DKE, você deve modificar os seguintes tipos de configurações de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-219">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="9ec2d-220">Configurações de acesso de chave</span><span class="sxs-lookup"><span data-stu-id="9ec2d-220">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="9ec2d-221">Definições de locatário e chave</span><span class="sxs-lookup"><span data-stu-id="9ec2d-221">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="9ec2d-222">Você modifica as configurações de aplicativo no appsettings.jsem arquivo.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-222">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="9ec2d-223">Esse arquivo está localizado no repositório do DoubleKeyEncryptionService que você clonou localmente em DoubleKeyEncryptionService\src\customer-key-store.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-223">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="9ec2d-224">Por exemplo, no Visual Studio Code, você pode navegar até o arquivo, conforme mostrado na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-224">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![Localizar o appsettings.jsno arquivo do DKE.](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="9ec2d-226">Configurações de acesso de chave</span><span class="sxs-lookup"><span data-stu-id="9ec2d-226">Key access settings</span></span>

<span data-ttu-id="9ec2d-227">Escolha se deseja usar o email ou a autorização de função.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-227">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="9ec2d-228">O DKE oferece suporte a apenas um desses métodos de autenticação por vez.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-228">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="9ec2d-229">**Autorização de email**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-229">**Email authorization**.</span></span> <span data-ttu-id="9ec2d-230">Permite que sua organização autorize o acesso a chaves com base apenas em endereços de email.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-230">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="9ec2d-231">**Autorização de função**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-231">**Role authorization**.</span></span> <span data-ttu-id="9ec2d-232">Permite que sua organização autorize o acesso às chaves com base nos grupos do Active Directory e exige que o serviço Web possa consultar o LDAP.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-232">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="9ec2d-233">**Para definir as configurações de acesso de chave do DKE usando autorização de email**</span><span class="sxs-lookup"><span data-stu-id="9ec2d-233">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="9ec2d-234">Abra o **appsettings.jsem** arquivo e localize a `AuthorizedEmailAddress` configuração.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-234">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="9ec2d-235">Adicione o endereço de email ou endereços que você deseja autorizar.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-235">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="9ec2d-236">Separe vários endereços de email com aspas duplas e vírgulas.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-236">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="9ec2d-237">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-237">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="9ec2d-238">Localize a `LDAPPath` configuração e remova o texto `If role authorization is used then this is the LDAP path` entre aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-238">Locate the `LDAPPath` setting and remove the text `If role authorization is used then this is the LDAP path` between the double quotes.</span></span> <span data-ttu-id="9ec2d-239">Deixe as aspas duplas em vigor.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-239">Leave the double quotes in place.</span></span> <span data-ttu-id="9ec2d-240">Quando você tiver terminado, a configuração deverá ter a seguinte aparência.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-240">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="9ec2d-241">Localize a `AuthorizedRoles` configuração e exclua a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-241">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="9ec2d-242">Esta imagem mostra o **appsettings.jsem** arquivo formatado corretamente para autorização de email.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-242">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![O appsettings.jsem arquivo mostrando o método de autorização de email](../media/dke-email-accesssetting.png)

<span data-ttu-id="9ec2d-244">**Para definir as configurações de acesso de chave para DKE usando autorização de função**</span><span class="sxs-lookup"><span data-stu-id="9ec2d-244">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="9ec2d-245">Abra o **appsettings.jsem** arquivo e localize a `AuthorizedRoles` configuração.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-245">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="9ec2d-246">Adicione os nomes de grupo do Active Directory que você deseja autorizar.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-246">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="9ec2d-247">Separe vários nomes de grupo com aspas duplas e vírgulas.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-247">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="9ec2d-248">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-248">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="9ec2d-249">Localize a `LDAPPath` configuração e adicione o domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-249">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="9ec2d-250">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-250">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="9ec2d-251">Localize a `AuthorizedEmailAddress` configuração e exclua a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-251">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="9ec2d-252">Esta imagem mostra o **appsettings.jsem** arquivo formatado corretamente para autorização de função.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-252">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![appsettings.jsem arquivo mostrando o método de autorização de função](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="9ec2d-254">Definições de locatário e chave</span><span class="sxs-lookup"><span data-stu-id="9ec2d-254">Tenant and key settings</span></span>

<span data-ttu-id="9ec2d-255">As configurações de locatário e chave do DKE estão localizadas na **appsettings.jsem** arquivo.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-255">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="9ec2d-256">**Para definir as configurações de locatário e chave do DKE**</span><span class="sxs-lookup"><span data-stu-id="9ec2d-256">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="9ec2d-257">Abra o **appsettings.jsem** arquivo.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-257">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="9ec2d-258">Localize a `ValidIssuers` configuração e substitua `<tenantid>` pela ID do locatário.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-258">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="9ec2d-259">Você pode localizar sua ID de locatário indo para o portal do Azure e exibindo as [Propriedades do locatário](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="9ec2d-259">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="9ec2d-260">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-260">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="9ec2d-261">Localize o `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="9ec2d-261">Locate the `JwtAudience`.</span></span> <span data-ttu-id="9ec2d-262">Substitua `<yourhostname>` pelo nome do host do computador em que o serviço DKE será executado.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-262">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="9ec2d-263">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-263">For example:</span></span>



  > [!IMPORTANT]
  > <span data-ttu-id="9ec2d-264">O valor de `JwtAudience` deve corresponder *exatamente*ao nome do host.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-264">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="9ec2d-265">Você pode usar **localhost: 5001** durante a depuração.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-265">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="9ec2d-266">No entanto, quando você terminar de depurar, certifique-se de atualizar esse valor para o nome de host do servidor.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-266">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="9ec2d-267">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-267">`TestKeys:Name`.</span></span> <span data-ttu-id="9ec2d-268">Insira um nome para a chave.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-268">Enter a name for your key.</span></span> <span data-ttu-id="9ec2d-269">Por exemplo: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="9ec2d-269">For example: `TestKey1`</span></span>
- <span data-ttu-id="9ec2d-270">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-270">`TestKeys:Id`.</span></span> <span data-ttu-id="9ec2d-271">Crie um GUID e insira-o como o `TestKeys:ID` valor.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-271">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="9ec2d-272">Por exemplo, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-272">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="9ec2d-273">Você pode usar um site como [gerador de GUID online](https://guidgenerator.com/) para gerar aleatoriamente um GUID.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-273">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="9ec2d-274">Esta imagem mostra o formato correto das configurações de locatário e chaves em **appsettings.js**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-274">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="9ec2d-275">`LDAPPath` é configurada para autorização de função.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-275">`LDAPPath` is configured for role authorization.</span></span>

![Mostra as configurações de locatário e chave corretas para o DKE no arquivo appsettings.js.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="9ec2d-277">Gerar chaves de teste</span><span class="sxs-lookup"><span data-stu-id="9ec2d-277">Generate test keys</span></span>

<span data-ttu-id="9ec2d-278">Depois de definir as configurações do aplicativo, você estará pronto para gerar chaves de teste públicas e privadas.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-278">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="9ec2d-279">Para gerar chaves:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-279">To generate keys:</span></span>

1. <span data-ttu-id="9ec2d-280">No menu Iniciar do Windows, execute o prompt de comando OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-280">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

1. <span data-ttu-id="9ec2d-281">Vá para a pasta onde você deseja salvar as teclas de teste.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-281">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="9ec2d-282">Os arquivos que você cria ao concluir as etapas dessa tarefa são armazenados na mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-282">The files you create by completing the steps in this task are stored in the same folder.</span></span>

1. <span data-ttu-id="9ec2d-283">Gere a nova chave de teste.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-283">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. <span data-ttu-id="9ec2d-284">Gerar a chave privada.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-284">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. <span data-ttu-id="9ec2d-285">Gere a chave pública.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-285">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. <span data-ttu-id="9ec2d-286">Em um editor de texto, abra **pubkeyonly. pem**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-286">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="9ec2d-287">Copie todo o conteúdo do arquivo **pubkeyonly. pem** , exceto a primeira e a última linha, na `PublicPem` seção do **appsettings.jsem** arquivo.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-287">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="9ec2d-288">Em um editor de texto, abra **privkeynopass. pem**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-288">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="9ec2d-289">Copie todo o conteúdo do arquivo **privkeynopass. pem** , exceto a primeira e a última linha, na `PrivatePem` seção do **appsettings.jsem** arquivo.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-289">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="9ec2d-290">Remova todos os espaços em branco e novas linhas em ambas as `PublicPem` `PrivatePem` seções e.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-290">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9ec2d-291">Ao copiar esse conteúdo, não exclua nenhum dos dados de PEM.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-291">When you copy this content, do not delete any of the PEM data.</span></span>

1. <span data-ttu-id="9ec2d-292">No Visual Studio Code, navegue até o arquivo **Startup.cs** .</span><span class="sxs-lookup"><span data-stu-id="9ec2d-292">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="9ec2d-293">Esse arquivo está localizado no repositório do DoubleKeyEncryptionService que você clonou localmente em DoubleKeyEncryptionService\src\customer-key-store\.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-293">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

2. <span data-ttu-id="9ec2d-294">Localize as seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-294">Locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

3. <span data-ttu-id="9ec2d-295">Substitua essas linhas pelo seguinte texto:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-295">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="9ec2d-296">Os resultados finais devem ser semelhantes aos seguintes.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-296">The end results should look similar to the following.</span></span>

   ![arquivo startup.cs para visualização pública](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="9ec2d-298">Agora você está pronto para [criar seu projeto do DKE](#build-the-project).</span><span class="sxs-lookup"><span data-stu-id="9ec2d-298">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="9ec2d-299">Compilar o projeto</span><span class="sxs-lookup"><span data-stu-id="9ec2d-299">Build the project</span></span>

<span data-ttu-id="9ec2d-300">Use as instruções a seguir para criar o projeto do DKE localmente:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-300">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="9ec2d-301">No Visual Studio Code, no repositório de serviços do DKE, selecione **Exibir** \> **paleta de comandos** e digite **Compilar** no prompt.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-301">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

1. <span data-ttu-id="9ec2d-302">Na lista, escolha **tarefas: executar tarefa de compilação**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-302">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="9ec2d-303">Se não houver tarefas de compilação encontradas, selecione **Configurar tarefa de compilação** e criar uma para o .NET Core da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-303">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![Configurar a tarefa de compilação ausente para o .NET](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="9ec2d-305">Escolha **criar tasks.jsno modelo**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-305">Choose **Create tasks.json from template**.</span></span>

   ![Criar tasks.jsno arquivo do modelo do DKE](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="9ec2d-307">Na lista de tipos de modelo, selecione **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-307">From the list of template types, select **.NET Core**.</span></span>

   ![Criar tasks.jsno arquivo do modelo do DKE](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="9ec2d-309">Na seção criar, localize o caminho para o arquivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="9ec2d-309">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="9ec2d-310">Se ele não estiver lá, adicione a seguinte linha:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-310">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. <span data-ttu-id="9ec2d-311">Execute novamente a compilação.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-311">Run the build again.</span></span>

1. <span data-ttu-id="9ec2d-312">Verifique se não há nenhum erro vermelho na janela de saída.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-312">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="9ec2d-313">Se houver erros vermelhos, verifique a saída do console.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-313">If there are red errors, check the console output.</span></span> <span data-ttu-id="9ec2d-314">Verifique se você concluiu todas as etapas anteriores corretamente e se as versões de compilação corretas estão presentes.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-314">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

2. <span data-ttu-id="9ec2d-315">Selecione **executar** \> **Iniciar Depuração** para depurar o processo.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-315">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="9ec2d-316">Se for solicitado a selecionar um ambiente, selecione **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-316">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="9ec2d-317">O depurador do .NET Core normalmente é iniciado em ' ' https://localhost:5001 `. To view your test key, go to ` https://localhost:5001 ' e acrescenta uma barra (/) e o nome da sua chave.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-317">The .NET core debugger typically launches to \`\`https://localhost:5001`. To view your test key, go to `https://localhost:5001\` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="9ec2d-318">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-318">For example:</span></span>

```https
https://localhost:5001/TestKey1
```

<span data-ttu-id="9ec2d-319">A chave deve ser exibida no formato JSON.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-319">The key should display in JSON format.</span></span>

<span data-ttu-id="9ec2d-320">A configuração já está concluída.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-320">Your setup is now complete.</span></span> <span data-ttu-id="9ec2d-321">Antes de publicar o repositório de chaves, em appsettings.js, para a configuração do JwtAudience, verifique se o valor do nome do host corresponde exatamente ao nome de host do serviço de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-321">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="9ec2d-322">Você pode ter alterado para localhost para solucionar problemas de compilação.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-322">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="publish-the-key-store"></a><span data-ttu-id="9ec2d-323">Publicar o repositório de chaves</span><span class="sxs-lookup"><span data-stu-id="9ec2d-323">Publish the key store</span></span>

<span data-ttu-id="9ec2d-324">Para publicar o repositório de chaves, você criará uma instância do serviço de aplicativo do Azure para hospedar sua implantação do DKE.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-324">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="9ec2d-325">Em seguida, você publicará as chaves geradas no Azure.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-325">Next, you'll publish your generated keys to Azure.</span></span>

<span data-ttu-id="9ec2d-326">**Para criar uma instância do Azure Web App para hospedar sua implantação do DKE**</span><span class="sxs-lookup"><span data-stu-id="9ec2d-326">**To create an Azure Web App instance to host your DKE deployment**</span></span>

1. <span data-ttu-id="9ec2d-327">No navegador, entre no [portal do Microsoft Azure](https://ms.portal.azure.com)e vá para a adição de **serviços de aplicativo**  >  **Add**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-327">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

1. <span data-ttu-id="9ec2d-328">Selecione sua assinatura e o grupo de recursos e defina os detalhes da instância.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-328">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="9ec2d-329">Insira o nome de host do computador onde você deseja instalar o serviço DKE.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-329">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="9ec2d-330">Certifique-se de que é o mesmo nome que o definido para a configuração JwtAudience no arquivo de [**appsettings.js**](#tenant-and-key-settings) .</span><span class="sxs-lookup"><span data-stu-id="9ec2d-330">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="9ec2d-331">O valor que você fornece para o nome também é o WebAppInstanceName.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-331">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="9ec2d-332">Para **publicar**, selecione **código**e para **pilha de tempo de execução**, selecione **.NET Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-332">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="9ec2d-333">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-333">For example:</span></span>

   ![Adicionar seu serviço de aplicativo](../media/dke-azure-add-app-service.png)

1. <span data-ttu-id="9ec2d-335">Na parte inferior da página, selecione **revisar + criar**e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-335">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

1. <span data-ttu-id="9ec2d-336">Siga um destes procedimentos para publicar suas chaves geradas no Azure:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-336">Do one of the following to publish your generated keys to Azure:</span></span>

    - [<span data-ttu-id="9ec2d-337">Publicar via ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="9ec2d-337">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="9ec2d-338">Publicar via FTP</span><span class="sxs-lookup"><span data-stu-id="9ec2d-338">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="9ec2d-339">Publicar via Visual Studio 2019 ou posterior</span><span class="sxs-lookup"><span data-stu-id="9ec2d-339">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [<span data-ttu-id="9ec2d-340">Publicar em um sistema local</span><span class="sxs-lookup"><span data-stu-id="9ec2d-340">Publish to an on-premises system</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > <span data-ttu-id="9ec2d-341">Você pode preferir outros métodos para implantar suas chaves.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-341">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="9ec2d-342">Selecione o método que funciona melhor para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-342">Select the method that works best for your organization.</span></span>

    > [!TIP]
    > <span data-ttu-id="9ec2d-343">A [publicação via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) e para um [sistema local](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) é descrita na documentação do [ASP .net](https://docs.microsoft.com/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="9ec2d-343">[Publishing via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) and to an [on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) is described in the [ASP .NET documentation](https://docs.microsoft.com/aspnet/core/).</span></span> <span data-ttu-id="9ec2d-344">Se você usar um desses métodos, abra as instruções em uma guia separada para que você possa retornar aqui facilmente quando tiver concluído.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-344">If you use one of these methods, open the instructions in a separate tab so that you can return here easily when you're done.</span></span>

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="9ec2d-345">Publicar via ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="9ec2d-345">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="9ec2d-346">Acesse `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-346">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="9ec2d-347">Por exemplo: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="9ec2d-347">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

1. <span data-ttu-id="9ec2d-348">Na base de código do armazenamento de chaves, vá para a pasta **Customer-Key-store\src\customer-Key-Store** e verifique se essa pasta contém o arquivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="9ec2d-348">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="9ec2d-349">Executar: **publicação de dotnet**</span><span class="sxs-lookup"><span data-stu-id="9ec2d-349">Run: **dotnet publish**</span></span>

     <span data-ttu-id="9ec2d-350">A janela saída exibe o diretório onde a publicação foi implantada.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-350">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="9ec2d-351">Por exemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="9ec2d-351">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="9ec2d-352">Envie todos os arquivos no diretório de publicação para um arquivo. zip.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-352">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="9ec2d-353">Ao criar o arquivo. zip, verifique se todos os arquivos no diretório estão no nível raiz do arquivo. zip.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-353">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="9ec2d-354">Arraste e solte o arquivo. zip criado no site do ZipDeployUI que você abriu acima.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-354">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="9ec2d-355">Por exemplo: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="9ec2d-355">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="9ec2d-356">O DKE é implantado e você pode navegar até as chaves de teste que você criou.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-356">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="9ec2d-357">Continue para [validar sua implantação](#validate-your-deployment) abaixo.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-357">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="9ec2d-358">Publicar via FTP</span><span class="sxs-lookup"><span data-stu-id="9ec2d-358">Publish via FTP</span></span>

1. <span data-ttu-id="9ec2d-359">Conecte-se ao serviço de aplicativo que você criou [acima](#publish-the-key-store).</span><span class="sxs-lookup"><span data-stu-id="9ec2d-359">Connect to the App Service you created [above](#publish-the-key-store).</span></span>

    <span data-ttu-id="9ec2d-360">Em seu navegador, vá para: centro de implantação do serviço de aplicativo **do portal do Azure**  >  **App Service**  >  **Deployment Center**  >  painel de FTP de**implantação manual**  >  **FTP**  >  **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-360">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

1. <span data-ttu-id="9ec2d-361">Copie as cadeias de conexão exibidas para um arquivo local.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-361">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="9ec2d-362">Você usará essas cadeias de caracteres para se conectar ao serviço do aplicativo Web e carregar arquivos via FTP.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-362">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="9ec2d-363">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-363">For example:</span></span>

   ![Copiar cadeias de conexão do painel de FTP](../media/dke-ftp-dashboard.png)

1. <span data-ttu-id="9ec2d-365">Na base de código do armazenamento principal, vá para o **diretório Customer-Key-store\src\customer-Key-Store**</span><span class="sxs-lookup"><span data-stu-id="9ec2d-365">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

1. <span data-ttu-id="9ec2d-366">Verifique se esse diretório contém o arquivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="9ec2d-366">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="9ec2d-367">Executar: **publicação de dotnet**</span><span class="sxs-lookup"><span data-stu-id="9ec2d-367">Run: **dotnet publish**</span></span>

    <span data-ttu-id="9ec2d-368">A saída contém o diretório onde a publicação foi implantada.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-368">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="9ec2d-369">Por exemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="9ec2d-369">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="9ec2d-370">Envie todos os arquivos no diretório de publicação para um arquivo zip.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-370">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="9ec2d-371">Ao criar o arquivo. zip, verifique se todos os arquivos no diretório estão no nível raiz do arquivo. zip.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-371">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="9ec2d-372">No cliente FTP, use as informações de conexão que você copiou para se conectar ao serviço de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-372">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="9ec2d-373">Carregue o arquivo. zip que você criou na etapa anterior para o diretório raiz do seu aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-373">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="9ec2d-374">DKE é implantado e você pode navegar para as teclas de teste que você criou.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-374">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="9ec2d-375">Em seguida, [valide sua implantação](#validate-your-deployment).</span><span class="sxs-lookup"><span data-stu-id="9ec2d-375">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="9ec2d-376">Validar sua implantação</span><span class="sxs-lookup"><span data-stu-id="9ec2d-376">Validate your deployment</span></span>

<span data-ttu-id="9ec2d-377">Depois de implantar o DKE usando um dos métodos descritos acima, valide a implantação e as configurações do armazenamento de chaves.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-377">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="9ec2d-378">Execute:  </span><span class="sxs-lookup"><span data-stu-id="9ec2d-378">Run:</span></span>

<span data-ttu-id="9ec2d-379">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/MyKey</span><span class="sxs-lookup"><span data-stu-id="9ec2d-379">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span></span>

<span data-ttu-id="9ec2d-380">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-380">For example:</span></span>

<span data-ttu-id="9ec2d-381">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span><span class="sxs-lookup"><span data-stu-id="9ec2d-381">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span></span>

<span data-ttu-id="9ec2d-382">Certifique-se de que nenhum erro apareça na saída.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-382">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="9ec2d-383">Quando estiver pronto, [Registre o repositório de chaves](#register-your-key-store).</span><span class="sxs-lookup"><span data-stu-id="9ec2d-383">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="9ec2d-384">Registrar seu repositório de chaves</span><span class="sxs-lookup"><span data-stu-id="9ec2d-384">Register your key store</span></span>

<span data-ttu-id="9ec2d-385">As etapas a seguir permitem que você registre seu repositório de chaves.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-385">The following steps enable you to register your key store.</span></span> <span data-ttu-id="9ec2d-386">O registro do armazenamento de chaves é a última etapa na implantação do DKE antes que você possa começar a criar rótulos.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-386">Registering your key store is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="9ec2d-387">Para registrar seu repositório de chave:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-387">To register your key store:</span></span>

1. <span data-ttu-id="9ec2d-388">No navegador, abra o [portal do Microsoft Azure](https://ms.portal.azure.com/)e vá para **todos os** \> registros de aplicativos de **identidade** de serviços \> **App Registrations**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-388">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="9ec2d-389">Selecione **novo registro**e insira um nome significativo.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-389">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="9ec2d-390">Selecione um tipo de conta nas opções exibidas.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-390">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="9ec2d-391">Se você estiver usando o Microsoft Azure com um domínio não personalizado, como **onmicrosoft.com**, selecione **contas nesse diretório organizacional apenas (somente para o Microsoft locatário).**</span><span class="sxs-lookup"><span data-stu-id="9ec2d-391">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="9ec2d-392">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-392">For example:</span></span>

   ![Novo registro de aplicativo](../media/dke-app-registration.png)

4. <span data-ttu-id="9ec2d-394">Na parte inferior da página, selecione **registrar** para criar o novo registro de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-394">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="9ec2d-395">No novo registro de aplicativo, no painel esquerdo, em **gerenciar**, selecione **autenticação**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-395">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="9ec2d-396">Selecione **Adicionar uma plataforma**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-396">Select **Add a platform**.</span></span>
 
7. <span data-ttu-id="9ec2d-397">No pop-up **Configurar plataformas** , selecione **Web**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-397">On the **Configure platforms** popup, select **Web**.</span></span>
 
8. <span data-ttu-id="9ec2d-398">Em **URIs de redirecionamento**, insira o URI do serviço de criptografia de chave dupla.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-398">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="9ec2d-399">Insira a URL do serviço de aplicativo, incluindo o nome do host e o domínio.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-399">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="9ec2d-400">Por exemplo: https://mycustomerkeystoretest.com</span><span class="sxs-lookup"><span data-stu-id="9ec2d-400">For example: https://mycustomerkeystoretest.com</span></span>

    - <span data-ttu-id="9ec2d-401">A URL inserida deve corresponder ao nome de host onde o repositório de chave está implantado.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-401">The URL you enter must match the hostname where your key store is deployed.</span></span>
    - <span data-ttu-id="9ec2d-402">Se você estiver testando localmente com o Visual Studio, use **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="9ec2d-402">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="9ec2d-403">Em todos os casos, o esquema deve ser **https**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-403">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="9ec2d-404">Certifique-se de que o nome do host corresponde exatamente ao nome de host do serviço de aplicativo</span><span class="sxs-lookup"><span data-stu-id="9ec2d-404">Ensure the hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="9ec2d-405">Você pode ter alterado para `localhost` solucionar problemas de compilação.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-405">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="9ec2d-406">Em **appsettings.js**, esse valor é o nome de host definido para `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="9ec2d-406">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

6. <span data-ttu-id="9ec2d-407">Em **concessão implícita**, selecione a caixa de seleção **tokens de ID** .</span><span class="sxs-lookup"><span data-stu-id="9ec2d-407">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

1. <span data-ttu-id="9ec2d-408">Clique em **Salvar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-408">Select **Save** to save your changes.</span></span>

7. <span data-ttu-id="9ec2d-409">No painel esquerdo, selecione **expor uma API**e, em seguida, ao lado de URI da ID do aplicativo, selecione **definir**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-409">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

9. <span data-ttu-id="9ec2d-410">Ainda na página de **exibir uma API** , na área **escopos definidos por esta API** , selecione **Adicionar um escopo**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-410">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="9ec2d-411">No novo escopo:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-411">In the new scope:</span></span>

    1. <span data-ttu-id="9ec2d-412">Defina o nome do escopo como **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-412">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="9ec2d-413">Selecione os administradores e usuários que podem autorizar.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-413">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="9ec2d-414">Defina os valores restantes necessários.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-414">Define any remaining values required.</span></span>

    4. <span data-ttu-id="9ec2d-415">Selecione **Adicionar escopo.**</span><span class="sxs-lookup"><span data-stu-id="9ec2d-415">Select **Add scope.**</span></span>

    <span data-ttu-id="9ec2d-416">Selecione **salvar** na parte superior para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-416">Select **Save** at the top to save your changes.</span></span>

10. <span data-ttu-id="9ec2d-417">Ainda na página **expor uma API** , na área **aplicativos cliente autorizados** , selecione **Adicionar um aplicativo cliente**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-417">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="9ec2d-418">No novo aplicativo cliente:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-418">In the new client application:</span></span>

    1. <span data-ttu-id="9ec2d-419">Defina a ID do cliente como **d3590ed6-52B3-4102-AEFF-aad2292ab01c**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-419">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="9ec2d-420">Esse valor é a ID de cliente do Microsoft Office e permite que o Office obtenha um token de acesso para o armazenamento de chaves.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-420">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="9ec2d-421">Em **escopos autorizados**, selecione o escopo de **user_impersonation** .</span><span class="sxs-lookup"><span data-stu-id="9ec2d-421">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="9ec2d-422">Selecione **Adicionar aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-422">Select **Add application**.</span></span>

    4. <span data-ttu-id="9ec2d-423">Selecione **salvar** na parte superior para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-423">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="9ec2d-424">O armazenamento de chave do DKE agora está registrado.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-424">Your DKE key store is now registered.</span></span> <span data-ttu-id="9ec2d-425">Continue [criando rótulos usando o DKE](#create-labels-using-dke).</span><span class="sxs-lookup"><span data-stu-id="9ec2d-425">Continue by [creating labels using DKE](#create-labels-using-dke).</span></span>

## <a name="create-labels-using-dke"></a><span data-ttu-id="9ec2d-426">Criar rótulos usando DKE</span><span class="sxs-lookup"><span data-stu-id="9ec2d-426">Create labels using DKE</span></span>

<span data-ttu-id="9ec2d-427">No centro de conformidade da Microsoft 365, crie um novo rótulo de confidencialidade e aplique a criptografia como faria de outra forma.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-427">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="9ec2d-428">Selecione **usar criptografia de chave dupla** e digite a URL do ponto de extremidade da sua chave.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-428">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="9ec2d-429">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-429">For example:</span></span>

![Selecione usar criptografia de chave dupla no centro de conformidade do Microsoft 365](../media/dke-use-dke.png)

<span data-ttu-id="9ec2d-431">Quaisquer rótulos do DKE que você adicionar serão iniciados para os usuários nas versões mais recentes dos aplicativos do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-431">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="9ec2d-432">Pode levar até 24 horas para que os clientes sejam atualizados com os novos rótulos.</span><span class="sxs-lookup"><span data-stu-id="9ec2d-432">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="9ec2d-433">Habilitar o DKE no cliente</span><span class="sxs-lookup"><span data-stu-id="9ec2d-433">Enable DKE in your client</span></span>

<span data-ttu-id="9ec2d-434">Habilite o DKE para o cliente adicionando as seguintes chaves do registro:</span><span class="sxs-lookup"><span data-stu-id="9ec2d-434">Enable DKE for your client by adding the following registry keys:</span></span>

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
