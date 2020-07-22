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
ms.openlocfilehash: 47fc4bc47831970ef7a7f2087cf6c86b6fefb8c2
ms.sourcegitcommit: fe20f5ed07f38786c63df0f73659ca472e69e478
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201643"
---
# <a name="double-key-encryption-dke"></a><span data-ttu-id="3fc97-103">DKE (criptografia de chave dupla)</span><span class="sxs-lookup"><span data-stu-id="3fc97-103">Double Key Encryption (DKE)</span></span>

> <span data-ttu-id="3fc97-104">*Aplica-se a: conformidade com a [Microsoft 365](https://www.microsoft.com/microsoft-365/business/compliance-management), [proteção de informações do Azure](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="3fc97-104">*Applies to: [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="3fc97-105">*Instruções para: [cliente de rotulação unificada de proteção de informações do Azure para Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="3fc97-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="3fc97-106">*Descrição do serviço para: conformidade com a [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="3fc97-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="3fc97-107">Esta versão prévia pública da DKE (criptografia de chave dupla) permite que você use o cliente de rotulação unificado de proteção de informações do Azure para proteger o conteúdo altamente confidencial e, ao mesmo tempo, manter controle total da sua chave.</span><span class="sxs-lookup"><span data-stu-id="3fc97-107">This public preview version of Double Key Encryption (DKE) enables you to use the Azure Information Protection Unified Labeling Client to protect highly sensitive content while maintaining full control of your key.</span></span>

<span data-ttu-id="3fc97-108">A criptografia de chave dupla requer duas chaves, usadas juntas, para acessar o conteúdo protegido.</span><span class="sxs-lookup"><span data-stu-id="3fc97-108">Double Key Encryption requires two keys, used together, to access protected content.</span></span> <span data-ttu-id="3fc97-109">Você armazena uma chave no Microsoft Azure e mantém a outra chave.</span><span class="sxs-lookup"><span data-stu-id="3fc97-109">You store one key in Microsoft Azure, and you hold the other key.</span></span>

<span data-ttu-id="3fc97-110">A criptografia de chave dupla oferece suporte a implantações no local e na nuvem.</span><span class="sxs-lookup"><span data-stu-id="3fc97-110">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="3fc97-111">Essas implantações ajudam a garantir que os dados criptografados permaneçam opaco onde quer você armazene os dados protegidos.</span><span class="sxs-lookup"><span data-stu-id="3fc97-111">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="3fc97-112">Para obter mais informações sobre as chaves de raiz de locatários padrão baseadas em nuvem, consulte [Planning and Implementing Your Azure Information Protection locatário Key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span><span class="sxs-lookup"><span data-stu-id="3fc97-112">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

<span data-ttu-id="3fc97-113">A criptografia de chave dupla é semelhante a uma caixa de depósito de segurança que exige uma chave de banco e uma chave de cliente para obter acesso.</span><span class="sxs-lookup"><span data-stu-id="3fc97-113">Double Key Encryption is similar to a safety deposit box that requires both a bank key and a customer key to gain access.</span></span> <span data-ttu-id="3fc97-114">Para descriptografar o conteúdo protegido, você deve usar a chave gerenciada da Microsoft e a chave do cliente.</span><span class="sxs-lookup"><span data-stu-id="3fc97-114">To decrypt protected content, you must use both the Microsoft managed key and the customer-held key.</span></span>

<span data-ttu-id="3fc97-115">O vídeo a seguir mostra como a criptografia de chave dupla funciona para proteger o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="3fc97-115">The following video shows how Double Key Encryption works to secure your content.</span></span>

<span data-ttu-id="3fc97-116">Se as suas organizações têm qualquer um dos seguintes requisitos, você pode usar o DKE para ajudar a proteger o conteúdo:</span><span class="sxs-lookup"><span data-stu-id="3fc97-116">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="3fc97-117">Você quer garantir que *apenas você* possa descriptografar o conteúdo protegido, em todas as circunstâncias.</span><span class="sxs-lookup"><span data-stu-id="3fc97-117">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="3fc97-118">Você não deseja que a Microsoft tenha acesso a dados protegidos por conta própria.</span><span class="sxs-lookup"><span data-stu-id="3fc97-118">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="3fc97-119">Você tem requisitos normativos para manter chaves dentro de um limite geográfico.</span><span class="sxs-lookup"><span data-stu-id="3fc97-119">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="3fc97-120">Todas as chaves de retenção de dados e descriptografia são mantidas em seu data center.</span><span class="sxs-lookup"><span data-stu-id="3fc97-120">All customer-held keys for data encryption and decryption are maintained in your data center.</span></span>

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="3fc97-121">Requisitos de sistema e licenciamento para o DKE</span><span class="sxs-lookup"><span data-stu-id="3fc97-121">System and licensing requirements for DKE</span></span>

<span data-ttu-id="3fc97-122">Esta versão prévia pública da criptografia de chave dupla para o Microsoft 365 está disponível como parte do Microsoft 365 E5 e do Office 365 e5.</span><span class="sxs-lookup"><span data-stu-id="3fc97-122">This public preview release of Double Key Encryption for Microsoft 365 is available as part of Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="3fc97-123">Se você não tem uma licença do Microsoft 365 e5, é possível inscrever-se em uma [avaliação](https://aka.ms/M365E5ComplianceTrial).</span><span class="sxs-lookup"><span data-stu-id="3fc97-123">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="3fc97-124">Para obter mais informações sobre essas licenças, consulte [diretrizes de licenciamento da Microsoft 365 para segurança & conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="3fc97-124">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="3fc97-125">**Office Insider** Para usar a visualização pública, você deve ser membro do programa Office Insider.</span><span class="sxs-lookup"><span data-stu-id="3fc97-125">**Office Insider** To use the public preview, you must be a member of the Office Insider program.</span></span> <span data-ttu-id="3fc97-126">Para ingressar no Office Insider, vá para [https://insider.office.com](https://insider.office.com) .</span><span class="sxs-lookup"><span data-stu-id="3fc97-126">To join Office Insider, go to [https://insider.office.com](https://insider.office.com).</span></span> <span data-ttu-id="3fc97-127">Quando você for membro, prepare o ambiente para implantar o Office Insider compilações escolhendo o método de implantação certo para sua organização.</span><span class="sxs-lookup"><span data-stu-id="3fc97-127">Once you're a member, prepare your environment to deploy Office Insider builds by choosing the right deployment method for your organization.</span></span> <span data-ttu-id="3fc97-128">Para obter instruções, consulte [introdução à implantação de compilações do Office Insider](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="3fc97-128">For instructions, see [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="3fc97-129">**Proteção de informações do Azure**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-129">**Azure Information Protection**.</span></span> <span data-ttu-id="3fc97-130">O DKE funciona com rótulos de sensibilidade e requer a proteção de informações do Azure.</span><span class="sxs-lookup"><span data-stu-id="3fc97-130">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="3fc97-131">Ambientes suportados para armazenar e exibir o conteúdo protegido por DKE</span><span class="sxs-lookup"><span data-stu-id="3fc97-131">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="3fc97-132">**Aplicativos com suporte**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-132">**Supported applications**.</span></span> <span data-ttu-id="3fc97-133">[Microsoft 365 aplicativos para clientes corporativos](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) no Windows, incluindo Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="3fc97-133">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="3fc97-134">**Suporte a conteúdo online**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-134">**Online content support**.</span></span> <span data-ttu-id="3fc97-135">Há suporte para documentos e arquivos armazenados online no Microsoft SharePoint e no OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="3fc97-135">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="3fc97-136">Você pode compartilhar conteúdo criptografado por email, mas não pode exibir documentos e arquivos criptografados online.</span><span class="sxs-lookup"><span data-stu-id="3fc97-136">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="3fc97-137">Em vez disso, você deve exibir o conteúdo protegido usando os aplicativos de área de trabalho no computador local.</span><span class="sxs-lookup"><span data-stu-id="3fc97-137">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="about-this-public-preview-article"></a><span data-ttu-id="3fc97-138">Sobre este artigo de demonstração pública</span><span class="sxs-lookup"><span data-stu-id="3fc97-138">About this public preview article</span></span>

<span data-ttu-id="3fc97-139">Há várias maneiras de realizar algumas das etapas para implantar a criptografia de chave dupla.</span><span class="sxs-lookup"><span data-stu-id="3fc97-139">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="3fc97-140">Este artigo fornece instruções detalhadas para que administradores menos experientes implantem o serviço com êxito.</span><span class="sxs-lookup"><span data-stu-id="3fc97-140">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="3fc97-141">Se você tiver experiência com as tecnologias comuns, como o Git, compartilhado pelos métodos de implantação descritos neste artigo, você pode optar por usar seus próprios métodos.</span><span class="sxs-lookup"><span data-stu-id="3fc97-141">If you're experienced with the common technologies, such as git, shared by the deployment methods described in this article, you can choose to use your own methods.</span></span>

<span data-ttu-id="3fc97-142">Para visualização pública, incluímos instruções passo a passo sobre como implantar o serviço de criptografia de chave dupla no Azure.</span><span class="sxs-lookup"><span data-stu-id="3fc97-142">For public preview, we've included step-by-step instructions on how to deploy the Double Key Encryption service to Azure.</span></span> <span data-ttu-id="3fc97-143">Esse cenário não é algo que você provavelmente faria em produção.</span><span class="sxs-lookup"><span data-stu-id="3fc97-143">This scenario isn't something you'd likely do in production.</span></span> <span data-ttu-id="3fc97-144">Para visualização pública usando o Azure é uma maneira rápida de implantar que permite começar a usar imediatamente a criptografia de chave dupla.</span><span class="sxs-lookup"><span data-stu-id="3fc97-144">For public preview using Azure is a quick way to deploy that lets you get started using Double Key Encryption right away.</span></span>

<span data-ttu-id="3fc97-145">Você pode optar por implantar o serviço onde quiser, seja localmente em sua rede ou com outro provedor.</span><span class="sxs-lookup"><span data-stu-id="3fc97-145">You can choose to deploy the service wherever you want, whether it's locally on your network or with another provider.</span></span> <span data-ttu-id="3fc97-146">Você precisará publicar o repositório de chaves usando métodos apropriados para esse local.</span><span class="sxs-lookup"><span data-stu-id="3fc97-146">You'll need to publish the key store using methods appropriate for that location.</span></span>

## <a name="deploy-double-key-encryption"></a><span data-ttu-id="3fc97-147">Implantar a criptografia de chave dupla</span><span class="sxs-lookup"><span data-stu-id="3fc97-147">Deploy Double Key Encryption</span></span>

<span data-ttu-id="3fc97-148">Siga estas etapas gerais para configurar a criptografia de chave dupla para sua organização.</span><span class="sxs-lookup"><span data-stu-id="3fc97-148">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span> <span data-ttu-id="3fc97-149">O exemplo neste artigo usa o Azure como o destino de implantação para o serviço DKE.</span><span class="sxs-lookup"><span data-stu-id="3fc97-149">The example in this article uses Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="3fc97-150">Se você estiver implantando em outro local, precisará fornecer seus próprios valores.</span><span class="sxs-lookup"><span data-stu-id="3fc97-150">If you're deploying to another location, you'll need to provide your own values.</span></span>

1. [<span data-ttu-id="3fc97-151">Instalar pré-requisitos de software</span><span class="sxs-lookup"><span data-stu-id="3fc97-151">Install software prerequisites</span></span>](#install-software-prerequisites)
1. [<span data-ttu-id="3fc97-152">Clone o repositório do GitHub de criptografia de chave dupla</span><span class="sxs-lookup"><span data-stu-id="3fc97-152">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="3fc97-153">Modificar configurações do aplicativo</span><span class="sxs-lookup"><span data-stu-id="3fc97-153">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="3fc97-154">Gerar chaves de teste</span><span class="sxs-lookup"><span data-stu-id="3fc97-154">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="3fc97-155">Compilar o projeto</span><span class="sxs-lookup"><span data-stu-id="3fc97-155">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="3fc97-156">Publicar o repositório de chaves</span><span class="sxs-lookup"><span data-stu-id="3fc97-156">Publish the key store</span></span>](#publish-the-key-store)
1. [<span data-ttu-id="3fc97-157">Validar sua implantação</span><span class="sxs-lookup"><span data-stu-id="3fc97-157">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="3fc97-158">Registrar seu repositório de chaves</span><span class="sxs-lookup"><span data-stu-id="3fc97-158">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="3fc97-159">Criar rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="3fc97-159">Create sensitivity labels</span></span>](#create-labels-using-dke)

<span data-ttu-id="3fc97-160">Quando tiver concluído, você poderá criptografar documentos e arquivos usando o DKE.</span><span class="sxs-lookup"><span data-stu-id="3fc97-160">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="3fc97-161">Para saber mais, confira [aplicar rótulos de confidencialidade aos seus arquivos e emails no Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span><span class="sxs-lookup"><span data-stu-id="3fc97-161">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites"></a><span data-ttu-id="3fc97-162">Instalar pré-requisitos de software</span><span class="sxs-lookup"><span data-stu-id="3fc97-162">Install software prerequisites</span></span>

<span data-ttu-id="3fc97-163">Há dois tipos de pré-requisitos de software para a criptografia de chave dupla</span><span class="sxs-lookup"><span data-stu-id="3fc97-163">There are two types of software prerequisites for Double Key Encryption</span></span>

- [<span data-ttu-id="3fc97-164">Pré-requisitos do serviço de criptografia de chave dupla</span><span class="sxs-lookup"><span data-stu-id="3fc97-164">Double Key Encryption service prerequisites</span></span>](#double-key-encryption-service-prerequisites)
- [<span data-ttu-id="3fc97-165">Pré-requisitos de criptografia de chave dupla para computadores clientes</span><span class="sxs-lookup"><span data-stu-id="3fc97-165">Double Key Encryption prerequisites for client computers</span></span>](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a><span data-ttu-id="3fc97-166">Pré-requisitos do serviço de criptografia de chave dupla</span><span class="sxs-lookup"><span data-stu-id="3fc97-166">Double Key Encryption service prerequisites</span></span>

<span data-ttu-id="3fc97-167">Instale esses pré-requisitos no computador onde você deseja instalar o serviço DKE.</span><span class="sxs-lookup"><span data-stu-id="3fc97-167">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="3fc97-168">**SDK do .NET Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-168">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="3fc97-169">Baixe e instale o SDK do [download do .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="3fc97-169">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="3fc97-170">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-170">**Visual Studio Code**.</span></span> <span data-ttu-id="3fc97-171">Baixe o Visual Studio Code de [https://code.visualstudio.com/](https://code.visualstudio.com) .</span><span class="sxs-lookup"><span data-stu-id="3fc97-171">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="3fc97-172">Depois de instalado, execute o Visual Studio Code e selecione **View** \> **Extensions**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-172">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="3fc97-173">Instale essas extensões.</span><span class="sxs-lookup"><span data-stu-id="3fc97-173">Install these extensions.</span></span>

- <span data-ttu-id="3fc97-174">C# para o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3fc97-174">C# for Visual Studio Code</span></span>

- <span data-ttu-id="3fc97-175">Gerenciador de pacotes do NuGet</span><span class="sxs-lookup"><span data-stu-id="3fc97-175">NuGet Package Manager</span></span>

<span data-ttu-id="3fc97-176">**Microsoft Office Insider**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-176">**Microsoft Office Insider**.</span></span> <span data-ttu-id="3fc97-177">Configure pelo menos um [método de implantação](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="3fc97-177">Set up at least one [deployment method](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="3fc97-178">**Recursos git**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-178">**Git resources**.</span></span> <span data-ttu-id="3fc97-179">Baixe e instale um dos seguintes.</span><span class="sxs-lookup"><span data-stu-id="3fc97-179">Download and install one of the following.</span></span>

- [<span data-ttu-id="3fc97-180">Git</span><span class="sxs-lookup"><span data-stu-id="3fc97-180">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="3fc97-181">Área de trabalho do GitHub</span><span class="sxs-lookup"><span data-stu-id="3fc97-181">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="3fc97-182">GitHub corporativo</span><span class="sxs-lookup"><span data-stu-id="3fc97-182">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="3fc97-183">**OpenSSL** Você deve ter o [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) instalado para [gerar chaves de teste](#generate-test-keys) depois de implantar o DKE.</span><span class="sxs-lookup"><span data-stu-id="3fc97-183">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="3fc97-184">Certifique-se de que você está invocando-o corretamente de seu caminho de variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="3fc97-184">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="3fc97-185">Por exemplo, consulte "Adicionar o diretório de instalação ao caminho" https://www.osradar.com/install-openssl-windows/ para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="3fc97-185">For example, see "Add the installation directory to PATH" at https://www.osradar.com/install-openssl-windows/ for details.</span></span>

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a><span data-ttu-id="3fc97-186">Pré-requisitos de criptografia de chave dupla para computadores clientes</span><span class="sxs-lookup"><span data-stu-id="3fc97-186">Double Key Encryption prerequisites for client computers</span></span>

<span data-ttu-id="3fc97-187">Instale esses pré-requisitos em cada computador cliente onde você deseja proteger e consumir documentos protegidos.</span><span class="sxs-lookup"><span data-stu-id="3fc97-187">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="3fc97-188">**Microsoft Office** versão \*. 12711 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="3fc97-188">**Microsoft Office** version \*.12711 or later.</span></span>

<span data-ttu-id="3fc97-189">Versões **unificadas de rótulo do cliente de proteção de informações do Azure** 2.7.93.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="3fc97-189">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="3fc97-190">Baixe e instale o cliente de rotulação unificada da [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="3fc97-190">Download and install the Unified Labeling client from [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="3fc97-191">Clonar o repositório do GitHub DKE</span><span class="sxs-lookup"><span data-stu-id="3fc97-191">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="3fc97-192">A Microsoft fornece os arquivos de origem do DKE em um repositório do GitHub.</span><span class="sxs-lookup"><span data-stu-id="3fc97-192">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="3fc97-193">Você clona o repositório para compilar o projeto localmente para uso da sua organização.</span><span class="sxs-lookup"><span data-stu-id="3fc97-193">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="3fc97-194">O repositório do GitHub do DKE está localizado em [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="3fc97-194">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="3fc97-195">As instruções a seguir se destinam a usuários do git ou do Visual Studio Code inexperientes:</span><span class="sxs-lookup"><span data-stu-id="3fc97-195">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="3fc97-196">No navegador, acesse:[https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span><span class="sxs-lookup"><span data-stu-id="3fc97-196">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span></span>

1. <span data-ttu-id="3fc97-197">No lado direito da tela, selecione **código**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-197">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="3fc97-198">Sua versão da interface do usuário pode mostrar um botão **clone ou download** .</span><span class="sxs-lookup"><span data-stu-id="3fc97-198">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="3fc97-199">Em seguida, na lista suspensa exibida, selecione o ícone Copiar para copiar a URL para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="3fc97-199">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="3fc97-200">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3fc97-200">For example:</span></span>

    :::image type="content" source="../media/dke-clone.png" alt-text="Clonar o repositório de serviço de criptografia de chave dupla do GitHub":::

3. <span data-ttu-id="3fc97-202">No Visual Studio Code, selecione **Exibir** \> **paleta de comandos** e selecione **git: clonar**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-202">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="3fc97-203">Para ir para a opção na lista, comece a digitar `git: clone` para filtrar as entradas e, em seguida, selecione-a no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="3fc97-203">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="3fc97-204">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3fc97-204">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-clone.png" alt-text="Visual Studio Code GIT: opção clone":::

4. <span data-ttu-id="3fc97-206">Na caixa de texto, Cole a URL que você copiou do git e selecione **clonar do GitHub**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-206">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="3fc97-207">Na caixa de diálogo **Selecionar pasta** exibida, procure e selecione um local para armazenar o repositório.</span><span class="sxs-lookup"><span data-stu-id="3fc97-207">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="3fc97-208">No prompt, selecione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-208">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="3fc97-209">O repositório é aberto no Visual Studio Code e exibe a ramificação atual do git no canto inferior esquerdo.</span><span class="sxs-lookup"><span data-stu-id="3fc97-209">The repository is opened in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="3fc97-210">Sua ramificação atual deve ser **mestra**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-210">Your current branch should be **master**.</span></span>

    <span data-ttu-id="3fc97-211">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3fc97-211">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-master.png" alt-text="Ramificação do Visual Studio Code Master":::

6. <span data-ttu-id="3fc97-213">Selecione o Word **Master** e, em seguida, selecione **public_preview** na lista de ramificações.</span><span class="sxs-lookup"><span data-stu-id="3fc97-213">Select the word **master,** and then select **public_preview** from the list of branches.</span></span> 

   > [!IMPORTANT]
   > <span data-ttu-id="3fc97-214">Selecionar a ramificação public_preview garante que você tenha os arquivos corretos para compilar o projeto.</span><span class="sxs-lookup"><span data-stu-id="3fc97-214">Selecting the public_preview branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="3fc97-215">Se você não escolher a ramificação correta, sua implantação falhará.</span><span class="sxs-lookup"><span data-stu-id="3fc97-215">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="3fc97-216">Agora, o seu repositório de origem do DKE está configurado localmente.</span><span class="sxs-lookup"><span data-stu-id="3fc97-216">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="3fc97-217">Em seguida, [modifique as configurações de aplicativo](#modify-application-settings) para sua organização.</span><span class="sxs-lookup"><span data-stu-id="3fc97-217">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="3fc97-218">Modificar configurações do aplicativo</span><span class="sxs-lookup"><span data-stu-id="3fc97-218">Modify application settings</span></span>

<span data-ttu-id="3fc97-219">Para implantar o serviço DKE, você deve modificar os seguintes tipos de configurações de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="3fc97-219">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="3fc97-220">Configurações de acesso de chave</span><span class="sxs-lookup"><span data-stu-id="3fc97-220">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="3fc97-221">Definições de locatário e chave</span><span class="sxs-lookup"><span data-stu-id="3fc97-221">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="3fc97-222">Você modifica as configurações de aplicativo no appsettings.jsem arquivo.</span><span class="sxs-lookup"><span data-stu-id="3fc97-222">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="3fc97-223">Esse arquivo está localizado no repositório do DoubleKeyEncryptionService que você clonou localmente em DoubleKeyEncryptionService\src\customer-key-store.</span><span class="sxs-lookup"><span data-stu-id="3fc97-223">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="3fc97-224">Por exemplo, no Visual Studio Code, você pode navegar até o arquivo, conforme mostrado na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="3fc97-224">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

:::image type="content" source="../media/dke-appsettingsjson.png" alt-text="Localizar o appsettings.jsno arquivo do DKE.":::

#### <a name="key-access-settings"></a><span data-ttu-id="3fc97-226">Configurações de acesso de chave</span><span class="sxs-lookup"><span data-stu-id="3fc97-226">Key access settings</span></span>

<span data-ttu-id="3fc97-227">Escolha se deseja usar o email ou a autorização de função.</span><span class="sxs-lookup"><span data-stu-id="3fc97-227">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="3fc97-228">O DKE oferece suporte a apenas um desses métodos de autenticação por vez.</span><span class="sxs-lookup"><span data-stu-id="3fc97-228">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="3fc97-229">**Autorização de email**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-229">**Email authorization**.</span></span> <span data-ttu-id="3fc97-230">Permite que sua organização autorize o acesso a chaves com base apenas em endereços de email.</span><span class="sxs-lookup"><span data-stu-id="3fc97-230">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="3fc97-231">**Autorização de função**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-231">**Role authorization**.</span></span> <span data-ttu-id="3fc97-232">Permite que sua organização autorize o acesso às chaves com base nos grupos do Active Directory e exige que o serviço Web possa consultar o LDAP.</span><span class="sxs-lookup"><span data-stu-id="3fc97-232">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="3fc97-233">Para definir as configurações de acesso de chave para DKE:</span><span class="sxs-lookup"><span data-stu-id="3fc97-233">To set key access settings for DKE:</span></span>

1. <span data-ttu-id="3fc97-234">Na **appsettings.jsem** arquivo, defina apenas uma destas configurações:</span><span class="sxs-lookup"><span data-stu-id="3fc97-234">In the **appsettings.json** file, define only one of these settings:</span></span>

   - <span data-ttu-id="3fc97-235">Para autorização de email, localize a configuração **AuthorizedEmailAddresses** .</span><span class="sxs-lookup"><span data-stu-id="3fc97-235">For email authorization, locate the **AuthorizedEmailAddresses** setting.</span></span> <span data-ttu-id="3fc97-236">Adicione o endereço de email que você deseja autorizar.</span><span class="sxs-lookup"><span data-stu-id="3fc97-236">Add the email address that you want to authorize.</span></span> <span data-ttu-id="3fc97-237">Separe vários endereços de email com aspas duplas e vírgulas.</span><span class="sxs-lookup"><span data-stu-id="3fc97-237">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="3fc97-238">Por exemplo: **"' AuthorizedEmailAddresses '": ["email1@company.com", "EMAIL2@company.com", email3@company.com]**</span><span class="sxs-lookup"><span data-stu-id="3fc97-238">For example: **" ‘AuthorizedEmailAddresses’ ": ["email1@company.com", "email2@company.com ", email3@company.com]**</span></span>

   :::image type="content" source="../media/dke-email-accesssetting.png" alt-text="appsettings.jsem arquivo mostrando o método de autorização de email":::

   - <span data-ttu-id="3fc97-240">Para autorização de função, localize a configuração **AuthorizedRoles** .</span><span class="sxs-lookup"><span data-stu-id="3fc97-240">For role authorization, locate the **AuthorizedRoles** setting.</span></span> <span data-ttu-id="3fc97-241">Defina com os nomes de grupo do ActiveDirectory que você deseja autorizar.</span><span class="sxs-lookup"><span data-stu-id="3fc97-241">Define with the ActiveDirectory group names you want to authorize.</span></span> <span data-ttu-id="3fc97-242">Por exemplo: **"AuthorizedRoles": ["grupo1", "group2", "Group3"]**</span><span class="sxs-lookup"><span data-stu-id="3fc97-242">For example: **"AuthorizedRoles": ["group1", "group2", "group3"]**</span></span>

   :::image type="content" source="../media/dke-role-accesssetting.png" alt-text="appsettings.jsem arquivo mostrando o método de autorização de função":::

2. <span data-ttu-id="3fc97-244">Remova a configuração que não seja relevante para o método de autorização escolhido.</span><span class="sxs-lookup"><span data-stu-id="3fc97-244">Remove the setting that isn't relevant for your chosen authorization method.</span></span>

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="3fc97-245">Definições de locatário e chave</span><span class="sxs-lookup"><span data-stu-id="3fc97-245">Tenant and key settings</span></span>

<span data-ttu-id="3fc97-246">As configurações de locatário e chave do DKE estão localizadas na **appsettings.jsde** arquivo e no arquivo **Startup.cs** .</span><span class="sxs-lookup"><span data-stu-id="3fc97-246">DKE tenant and key settings are located in the **appsettings.json** file and the **startup.cs** file.</span></span>

<span data-ttu-id="3fc97-247">Na **appsettings.jsem** arquivo, modifique os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="3fc97-247">In the **appsettings.json** file, modify the following values:</span></span>

- <span data-ttu-id="3fc97-248">**ValidIssuers**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-248">**ValidIssuers**.</span></span> <span data-ttu-id="3fc97-249">Substitua `<tenantid>` pelo seu GUID de locatário.</span><span class="sxs-lookup"><span data-stu-id="3fc97-249">Replace `<tenantid>` with your tenant GUID.</span></span>
- <span data-ttu-id="3fc97-250">**JwtAudience**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-250">**JwtAudience**.</span></span> <span data-ttu-id="3fc97-251">Substitua `<yourhostname>` pelo nome do host do computador em que o serviço DKE será executado.</span><span class="sxs-lookup"><span data-stu-id="3fc97-251">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="3fc97-252">O valor de JwtAudience deve corresponder *exatamente*ao nome do host.</span><span class="sxs-lookup"><span data-stu-id="3fc97-252">The value for JwtAudience must match the name of your host *exactly*.</span></span> <span data-ttu-id="3fc97-253">Você pode usar **localhost: 5000** durante a depuração.</span><span class="sxs-lookup"><span data-stu-id="3fc97-253">You may use **localhost:5000** while debugging.</span></span> <span data-ttu-id="3fc97-254">No entanto, quando você terminar de depurar, certifique-se de atualizar esse valor para o nome de host do servidor.</span><span class="sxs-lookup"><span data-stu-id="3fc97-254">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="3fc97-255">**LDAPPath**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-255">**LDAPPath**.</span></span> <span data-ttu-id="3fc97-256">Defina o valor da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="3fc97-256">Set the value as follows:</span></span>

  - <span data-ttu-id="3fc97-257">Se você estiver usando autorização de função, insira o domínio LDAP.</span><span class="sxs-lookup"><span data-stu-id="3fc97-257">If you're using role authorization, enter the LDAP domain.</span></span>
  - <span data-ttu-id="3fc97-258">Se você estiver usando autorização de email, deixe esse valor vazio.</span><span class="sxs-lookup"><span data-stu-id="3fc97-258">If you're using email authorization, leave this value empty.</span></span>

   <span data-ttu-id="3fc97-259">Para obter mais informações, consulte [configurações de acesso de chave](#key-access-settings).</span><span class="sxs-lookup"><span data-stu-id="3fc97-259">For more information, see [Key access settings](#key-access-settings).</span></span>

- <span data-ttu-id="3fc97-260">**TestKeys: Name**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-260">**TestKeys:Name**.</span></span> <span data-ttu-id="3fc97-261">Insira um nome para a chave.</span><span class="sxs-lookup"><span data-stu-id="3fc97-261">Enter a name for your key.</span></span> <span data-ttu-id="3fc97-262">Exemplo: **TestKey1**</span><span class="sxs-lookup"><span data-stu-id="3fc97-262">Example: **TestKey1**</span></span>
- <span data-ttu-id="3fc97-263">**TestKeys: ID**. Crie um GUID e insira-o como o valor de **ID TestKeys:** .</span><span class="sxs-lookup"><span data-stu-id="3fc97-263">**TestKeys:Id**. Create a GUID and enter it as the **TestKeys:ID** value.</span></span> <span data-ttu-id="3fc97-264">Por exemplo, **DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-264">For example, **DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE**.</span></span> <span data-ttu-id="3fc97-265">Você pode usar um site como [gerador de GUID online](https://guidgenerator.com/) para gerar aleatoriamente um GUID.</span><span class="sxs-lookup"><span data-stu-id="3fc97-265">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

### <a name="generate-test-keys"></a><span data-ttu-id="3fc97-266">Gerar chaves de teste</span><span class="sxs-lookup"><span data-stu-id="3fc97-266">Generate test keys</span></span>

<span data-ttu-id="3fc97-267">Depois de definir as configurações do aplicativo, você estará pronto para gerar chaves de teste públicas e privadas.</span><span class="sxs-lookup"><span data-stu-id="3fc97-267">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="3fc97-268">Para gerar chaves:</span><span class="sxs-lookup"><span data-stu-id="3fc97-268">To generate keys:</span></span>

1. <span data-ttu-id="3fc97-269">No menu Iniciar do Windows, execute o prompt de comando OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="3fc97-269">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

1. <span data-ttu-id="3fc97-270">Vá para a pasta onde você deseja salvar as teclas de teste.</span><span class="sxs-lookup"><span data-stu-id="3fc97-270">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="3fc97-271">Os arquivos que você cria ao concluir as etapas dessa tarefa são armazenados na mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="3fc97-271">The files you create by completing the steps in this task are stored in the same folder.</span></span>

1. <span data-ttu-id="3fc97-272">Gere a nova chave de teste.</span><span class="sxs-lookup"><span data-stu-id="3fc97-272">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. <span data-ttu-id="3fc97-273">Gerar a chave privada.</span><span class="sxs-lookup"><span data-stu-id="3fc97-273">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. <span data-ttu-id="3fc97-274">Gere a chave pública.</span><span class="sxs-lookup"><span data-stu-id="3fc97-274">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. <span data-ttu-id="3fc97-275">Em um editor de texto, abra **pubkeyonly. pem**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-275">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="3fc97-276">Copie todo o conteúdo do arquivo **pubkeyonly. pem** , exceto a primeira e a última linha, na seção **PublicPem** do **appsettings.jsem** arquivo.</span><span class="sxs-lookup"><span data-stu-id="3fc97-276">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the **PublicPem** section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="3fc97-277">Em um editor de texto, abra **privkeynopass. pem**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-277">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="3fc97-278">Copie todo o conteúdo do arquivo **privkeynopass. pem** , exceto a primeira e a última linha, na seção **PrivatePem** do **appsettings.jsem** arquivo.</span><span class="sxs-lookup"><span data-stu-id="3fc97-278">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the **PrivatePem** section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="3fc97-279">Remova todos os espaços em branco e novas linhas nas seções **PublicPem** e **PrivatePem** .</span><span class="sxs-lookup"><span data-stu-id="3fc97-279">Remove all blank spaces and newlines in both the **PublicPem** and **PrivatePem** sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3fc97-280">Ao copiar esse conteúdo, não exclua nenhum dos dados de PEM.</span><span class="sxs-lookup"><span data-stu-id="3fc97-280">When you copy this content, do not delete any of the PEM data.</span></span>

1. <span data-ttu-id="3fc97-281">Abra o arquivo **Startup.cs** e localize as seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="3fc97-281">Open the **Startup.cs** file, and locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

1. <span data-ttu-id="3fc97-282">Substitua essas linhas pelo seguinte texto:</span><span class="sxs-lookup"><span data-stu-id="3fc97-282">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="3fc97-283">Os resultados finais devem ser semelhantes à imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="3fc97-283">The end results should look similar to the following picture.</span></span>

   :::image type="content" source="../media/dke-startupcs-usetestkeys.png" alt-text="arquivo startup.cs para visualização pública":::

<span data-ttu-id="3fc97-285">Agora você está pronto para [criar seu projeto do DKE](#build-the-project).</span><span class="sxs-lookup"><span data-stu-id="3fc97-285">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="3fc97-286">Compilar o projeto</span><span class="sxs-lookup"><span data-stu-id="3fc97-286">Build the project</span></span>

<span data-ttu-id="3fc97-287">Use as instruções a seguir para criar o projeto do DKE localmente:</span><span class="sxs-lookup"><span data-stu-id="3fc97-287">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="3fc97-288">No Visual Studio Code, no repositório de serviços do DKE, selecione **Exibir** \> **paleta de comandos** e digite **Compilar** no prompt.</span><span class="sxs-lookup"><span data-stu-id="3fc97-288">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

1. <span data-ttu-id="3fc97-289">Na lista, escolha **tarefas: executar tarefa de compilação**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-289">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="3fc97-290">Se não houver tarefas de compilação encontradas, selecione **Configurar tarefa de compilação** e criar uma para o .NET Core da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="3fc97-290">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   :::image type="content" source="../media/dke-configurebuildtask.png" alt-text="Configurar a tarefa de compilação ausente para o .NET":::

   1. <span data-ttu-id="3fc97-292">Escolha **criar tasks.jsno modelo**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-292">Choose **Create tasks.json from template**.</span></span>

   :::image type="content" source="../media/dke-createtasksjsonfromtemplate.png" alt-text="Criar tasks.jsno arquivo do modelo do DKE":::

   2. <span data-ttu-id="3fc97-294">Na lista de tipos de modelo, selecione **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-294">From the list of template types, select **.NET Core**.</span></span>

   :::image type="content" source="../media/dke-tasksjsontemplate.png" alt-text="Criar tasks.jsno arquivo do modelo do DKE":::

   3. <span data-ttu-id="3fc97-296">Na seção criar, localize o caminho para o arquivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="3fc97-296">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="3fc97-297">Se ele não estiver lá, adicione a seguinte linha:</span><span class="sxs-lookup"><span data-stu-id="3fc97-297">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. <span data-ttu-id="3fc97-298">Execute novamente a compilação.</span><span class="sxs-lookup"><span data-stu-id="3fc97-298">Run the build again.</span></span>

1. <span data-ttu-id="3fc97-299">Verifique se não há nenhum erro vermelho na janela de saída.</span><span class="sxs-lookup"><span data-stu-id="3fc97-299">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="3fc97-300">Se houver erros vermelhos, verifique a saída do console.</span><span class="sxs-lookup"><span data-stu-id="3fc97-300">If there are red errors, check the console output.</span></span> <span data-ttu-id="3fc97-301">Verifique se você concluiu todas as etapas anteriores corretamente e se as versões de compilação corretas estão presentes.</span><span class="sxs-lookup"><span data-stu-id="3fc97-301">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

1. <span data-ttu-id="3fc97-302">**Executar** \> **Inicie a depuração** para depurar o processo.</span><span class="sxs-lookup"><span data-stu-id="3fc97-302">**Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="3fc97-303">Se for solicitado a selecionar um ambiente, selecione **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-303">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="3fc97-304">O depurador do .NET Core normalmente é iniciado no **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="3fc97-304">The .NET core debugger typically launches to **https://localhost:5001**.</span></span> <span data-ttu-id="3fc97-305">Para exibir sua chave de teste, vá para **https://localhost:5001** e acrescente uma barra (/) e o nome da sua chave.</span><span class="sxs-lookup"><span data-stu-id="3fc97-305">To view your test key, go to **https://localhost:5001**, and append a forward slash (/) and the name of your key.</span></span>

<span data-ttu-id="3fc97-306">Por exemplo:**https://localhost:5001/TestKey1**</span><span class="sxs-lookup"><span data-stu-id="3fc97-306">For example: **https://localhost:5001/TestKey1**</span></span>

<span data-ttu-id="3fc97-307">A chave deve ser exibida no formato JSON.</span><span class="sxs-lookup"><span data-stu-id="3fc97-307">The key should display in JSON format.</span></span>

<span data-ttu-id="3fc97-308">A configuração já está concluída.</span><span class="sxs-lookup"><span data-stu-id="3fc97-308">Your setup is now complete.</span></span> <span data-ttu-id="3fc97-309">Antes de publicar o repositório de chaves, em appsettings.js, para a configuração do JwtAudience, verifique se o valor do nome do host corresponde exatamente ao nome de host do serviço de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3fc97-309">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="3fc97-310">Você pode ter alterado para localhost para solucionar problemas de compilação.</span><span class="sxs-lookup"><span data-stu-id="3fc97-310">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="publish-the-key-store"></a><span data-ttu-id="3fc97-311">Publicar o repositório de chaves</span><span class="sxs-lookup"><span data-stu-id="3fc97-311">Publish the key store</span></span>

<span data-ttu-id="3fc97-312">As etapas a seguir descrevem como criar uma instância do serviço de aplicativo do Azure para hospedar sua implantação do DKE e como publicar as chaves geradas no Azure.</span><span class="sxs-lookup"><span data-stu-id="3fc97-312">The following steps describe how to create an Azure App Service instance to host your DKE deployment, and how to publish your generated keys to Azure.</span></span>

<span data-ttu-id="3fc97-313">Para criar uma instância do Azure Web App para hospedar sua implantação do DKE:</span><span class="sxs-lookup"><span data-stu-id="3fc97-313">To create an Azure Web App instance to host your DKE deployment:</span></span>

1. <span data-ttu-id="3fc97-314">No navegador, entre no [portal do Microsoft Azure](https://ms.portal.azure.com)e vá para a adição de **serviços de aplicativo**  >  **Add**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-314">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

1. <span data-ttu-id="3fc97-315">Selecione sua assinatura e o grupo de recursos e defina os detalhes da instância.</span><span class="sxs-lookup"><span data-stu-id="3fc97-315">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="3fc97-316">Insira o nome de host do computador onde você deseja instalar o serviço DKE.</span><span class="sxs-lookup"><span data-stu-id="3fc97-316">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="3fc97-317">Certifique-se de que é o mesmo nome que o definido para a configuração JwtAudience no arquivo de [**appsettings.js**](#tenant-and-key-settings) .</span><span class="sxs-lookup"><span data-stu-id="3fc97-317">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="3fc97-318">O valor que você fornece para o nome também é o WebAppInstanceName.</span><span class="sxs-lookup"><span data-stu-id="3fc97-318">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="3fc97-319">Para **publicar**, selecione **código**e para **pilha de tempo de execução**, selecione **.NET Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-319">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="3fc97-320">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3fc97-320">For example:</span></span>

    :::image type="content" source="../media/dke-azure-add-app-service.png" alt-text="Adicionar seu serviço de aplicativo":::

1. <span data-ttu-id="3fc97-322">Na parte inferior da página, selecione **revisar + criar**e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-322">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

1. <span data-ttu-id="3fc97-323">Siga um destes procedimentos para publicar suas chaves geradas no Azure:</span><span class="sxs-lookup"><span data-stu-id="3fc97-323">Do one of the following to publish your generated keys to Azure:</span></span>

    - [<span data-ttu-id="3fc97-324">Publicar via ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="3fc97-324">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="3fc97-325">Publicar via FTP</span><span class="sxs-lookup"><span data-stu-id="3fc97-325">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="3fc97-326">Publicar via Visual Studio 2019 ou posterior</span><span class="sxs-lookup"><span data-stu-id="3fc97-326">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [<span data-ttu-id="3fc97-327">Publicar em um sistema local</span><span class="sxs-lookup"><span data-stu-id="3fc97-327">Publish to an on-premises system</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > <span data-ttu-id="3fc97-328">Você pode preferir outros métodos para implantar suas chaves.</span><span class="sxs-lookup"><span data-stu-id="3fc97-328">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="3fc97-329">Selecione o método que funciona melhor para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="3fc97-329">Select the method that works best for your organization.</span></span>

    > [!TIP]
    > <span data-ttu-id="3fc97-330">A [publicação via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) e para um [sistema local](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) é descrita na documentação do [ASP .net](https://docs.microsoft.com/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="3fc97-330">[Publishing via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) and to an [on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) is described in the [ASP .NET documentation](https://docs.microsoft.com/aspnet/core/).</span></span> <span data-ttu-id="3fc97-331">Se você usar um desses métodos, abra as instruções em uma guia separada para que você possa retornar aqui facilmente quando tiver concluído.</span><span class="sxs-lookup"><span data-stu-id="3fc97-331">If you use one of these methods, open the instructions in a separate tab so that you can return here easily when you're done.</span></span>

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="3fc97-332">Publicar via ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="3fc97-332">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="3fc97-333">Acesse `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span><span class="sxs-lookup"><span data-stu-id="3fc97-333">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="3fc97-334">Por exemplo: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="3fc97-334">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

1. <span data-ttu-id="3fc97-335">Na base de código do armazenamento de chaves, vá para a pasta **Customer-Key-store\src\customer-Key-Store** e verifique se essa pasta contém o arquivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="3fc97-335">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="3fc97-336">Executar: **publicação de dotnet**</span><span class="sxs-lookup"><span data-stu-id="3fc97-336">Run: **dotnet publish**</span></span>

     <span data-ttu-id="3fc97-337">A janela saída exibe o diretório onde a publicação foi implantada.</span><span class="sxs-lookup"><span data-stu-id="3fc97-337">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="3fc97-338">Por exemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="3fc97-338">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="3fc97-339">Envie todos os arquivos no diretório de publicação para um arquivo. zip.</span><span class="sxs-lookup"><span data-stu-id="3fc97-339">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="3fc97-340">Ao criar o arquivo. zip, verifique se todos os arquivos no diretório estão no nível raiz do arquivo. zip.</span><span class="sxs-lookup"><span data-stu-id="3fc97-340">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="3fc97-341">Arraste e solte o arquivo. zip criado no site do ZipDeployUI que você abriu acima.</span><span class="sxs-lookup"><span data-stu-id="3fc97-341">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="3fc97-342">Por exemplo: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="3fc97-342">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="3fc97-343">O DKE é implantado e você pode navegar até as chaves de teste que você criou.</span><span class="sxs-lookup"><span data-stu-id="3fc97-343">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="3fc97-344">Continue para [validar sua implantação](#validate-your-deployment) abaixo.</span><span class="sxs-lookup"><span data-stu-id="3fc97-344">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="3fc97-345">Publicar via FTP</span><span class="sxs-lookup"><span data-stu-id="3fc97-345">Publish via FTP</span></span>

1. <span data-ttu-id="3fc97-346">Conecte-se ao serviço de aplicativo que você criou [acima](#publish-the-key-store).</span><span class="sxs-lookup"><span data-stu-id="3fc97-346">Connect to the App Service you created [above](#publish-the-key-store).</span></span>

    <span data-ttu-id="3fc97-347">Em seu navegador, vá para: centro de implantação do serviço de aplicativo **do portal do Azure**  >  **App Service**  >  **Deployment Center**  >  painel de FTP de**implantação manual**  >  **FTP**  >  **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-347">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

1. <span data-ttu-id="3fc97-348">Copie as cadeias de conexão exibidas para um arquivo local.</span><span class="sxs-lookup"><span data-stu-id="3fc97-348">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="3fc97-349">Você usará essas cadeias de caracteres para se conectar ao serviço do aplicativo Web e carregar arquivos via FTP.</span><span class="sxs-lookup"><span data-stu-id="3fc97-349">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="3fc97-350">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3fc97-350">For example:</span></span>

    :::image type="content" source="../media/dke-ftp-dashboard.png" alt-text="Copiar cadeias de conexão do painel de FTP":::

1. <span data-ttu-id="3fc97-352">Na base de código do armazenamento principal, vá para o **diretório Customer-Key-store\src\customer-Key-Store**</span><span class="sxs-lookup"><span data-stu-id="3fc97-352">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

1. <span data-ttu-id="3fc97-353">Verifique se esse diretório contém o arquivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="3fc97-353">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="3fc97-354">Executar: **publicação de dotnet**</span><span class="sxs-lookup"><span data-stu-id="3fc97-354">Run: **dotnet publish**</span></span>

    <span data-ttu-id="3fc97-355">A saída contém o diretório onde a publicação foi implantada.</span><span class="sxs-lookup"><span data-stu-id="3fc97-355">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="3fc97-356">Por exemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="3fc97-356">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="3fc97-357">Envie todos os arquivos no diretório de publicação para um arquivo zip.</span><span class="sxs-lookup"><span data-stu-id="3fc97-357">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="3fc97-358">Ao criar o arquivo. zip, verifique se todos os arquivos no diretório estão no nível raiz do arquivo. zip.</span><span class="sxs-lookup"><span data-stu-id="3fc97-358">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="3fc97-359">No cliente FTP, use as informações de conexão que você copiou para se conectar ao serviço de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3fc97-359">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="3fc97-360">Carregue o arquivo. zip que você criou na etapa anterior para o diretório raiz do seu aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="3fc97-360">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="3fc97-361">DKE é implantado e você pode navegar para as teclas de teste que você criou.</span><span class="sxs-lookup"><span data-stu-id="3fc97-361">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="3fc97-362">Em seguida, [valide sua implantação](#validate-your-deployment).</span><span class="sxs-lookup"><span data-stu-id="3fc97-362">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="3fc97-363">Validar sua implantação</span><span class="sxs-lookup"><span data-stu-id="3fc97-363">Validate your deployment</span></span>

<span data-ttu-id="3fc97-364">Depois de implantar o DKE usando um dos métodos descritos acima, valide a implantação e as configurações do armazenamento de chaves.</span><span class="sxs-lookup"><span data-stu-id="3fc97-364">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="3fc97-365">Sejam</span><span class="sxs-lookup"><span data-stu-id="3fc97-365">Run:</span></span>

<span data-ttu-id="3fc97-366">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/MyKey</span><span class="sxs-lookup"><span data-stu-id="3fc97-366">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span></span>

<span data-ttu-id="3fc97-367">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3fc97-367">For example:</span></span>

<span data-ttu-id="3fc97-368">key_store_tester.ps1https://mycustomerkeystore.com/mykey</span><span class="sxs-lookup"><span data-stu-id="3fc97-368">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span></span>

<span data-ttu-id="3fc97-369">Certifique-se de que nenhum erro apareça na saída.</span><span class="sxs-lookup"><span data-stu-id="3fc97-369">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="3fc97-370">Quando estiver pronto, [Registre o repositório de chaves](#register-your-key-store).</span><span class="sxs-lookup"><span data-stu-id="3fc97-370">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="3fc97-371">Registrar seu repositório de chaves</span><span class="sxs-lookup"><span data-stu-id="3fc97-371">Register your key store</span></span>

<span data-ttu-id="3fc97-372">As etapas a seguir permitem que você registre seu repositório de chaves.</span><span class="sxs-lookup"><span data-stu-id="3fc97-372">The following steps enable you to register your key store.</span></span> <span data-ttu-id="3fc97-373">O registro do armazenamento de chaves é a última etapa na implantação do DKE antes que você possa começar a criar rótulos.</span><span class="sxs-lookup"><span data-stu-id="3fc97-373">Registering your key store is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="3fc97-374">Para registrar seu repositório de chave:</span><span class="sxs-lookup"><span data-stu-id="3fc97-374">To register your key store:</span></span>

1. <span data-ttu-id="3fc97-375">No navegador, abra o [portal do Microsoft Azure](https://ms.portal.azure.com/)e vá para **todos os** \> registros de aplicativos de **identidade** de serviços \> **App Registrations**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-375">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="3fc97-376">Selecione **novo registro**e insira um nome significativo.</span><span class="sxs-lookup"><span data-stu-id="3fc97-376">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="3fc97-377">Selecione um tipo de conta nas opções exibidas.</span><span class="sxs-lookup"><span data-stu-id="3fc97-377">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="3fc97-378">Se você estiver usando o Microsoft Azure com um domínio não personalizado, como **onmicrosoft.com**, selecione **contas nesse diretório organizacional apenas (somente para o Microsoft locatário).**</span><span class="sxs-lookup"><span data-stu-id="3fc97-378">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="3fc97-379">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3fc97-379">For example:</span></span>

    :::image type="content" source="../media/dke-app-registration.png" alt-text="Novo registro de aplicativo":::

4. <span data-ttu-id="3fc97-381">Na parte inferior da página, selecione **registrar** para criar o novo registro de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3fc97-381">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="3fc97-382">No novo registro de aplicativo, no painel esquerdo, em **gerenciar**, selecione **autenticação**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-382">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="3fc97-383">Selecione **Adicionar uma plataforma**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-383">Select **Add a platform**.</span></span>
 
7. <span data-ttu-id="3fc97-384">No pop-up **Configurar plataformas** , selecione **Web**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-384">On the **Configure platforms** popup select **Web**.</span></span>
 
8. <span data-ttu-id="3fc97-385">Em **URIs de redirecionamento** , insira o URI do serviço de criptografia de chave dupla.</span><span class="sxs-lookup"><span data-stu-id="3fc97-385">Under **Redirect URIs** enter the URI of your double key encryption service.</span></span> <span data-ttu-id="3fc97-386">Insira a URL do serviço de aplicativo, incluindo o nome do host e o domínio.</span><span class="sxs-lookup"><span data-stu-id="3fc97-386">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="3fc97-387">Por exemplo: https://mycustomerkeystoretest.com</span><span class="sxs-lookup"><span data-stu-id="3fc97-387">For example: https://mycustomerkeystoretest.com</span></span>

    - <span data-ttu-id="3fc97-388">A URL inserida deve corresponder ao nome de host onde o repositório de chave está implantado.</span><span class="sxs-lookup"><span data-stu-id="3fc97-388">The URL you enter must match the hostname where your key store is deployed.</span></span>
    - <span data-ttu-id="3fc97-389">Se você estiver testando localmente com o Visual Studio, use **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="3fc97-389">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="3fc97-390">Em todos os casos, o esquema deve ser **https**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-390">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="3fc97-391">Certifique-se de que o nome do host corresponde exatamente ao nome de host do serviço de aplicativo</span><span class="sxs-lookup"><span data-stu-id="3fc97-391">Ensure the hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="3fc97-392">Você pode ter alterado para localhost para solucionar problemas de compilação.</span><span class="sxs-lookup"><span data-stu-id="3fc97-392">You may have changed it to localhost to troubleshoot the build.</span></span> <span data-ttu-id="3fc97-393">Em appsettings.js, este é o nome de host que você identificou como o valor da configuração JwtAudience.</span><span class="sxs-lookup"><span data-stu-id="3fc97-393">In appsettings.json, this is the hostname you identified as the value for the JwtAudience setting.</span></span>

6. <span data-ttu-id="3fc97-394">Em **concessão implícita**, selecione a caixa de seleção **tokens de ID** .</span><span class="sxs-lookup"><span data-stu-id="3fc97-394">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

1. <span data-ttu-id="3fc97-395">Clique em **Salvar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="3fc97-395">Select **Save** to save your changes.</span></span>

7. <span data-ttu-id="3fc97-396">No painel esquerdo, selecione **expor uma API**e, em seguida, ao lado de URI da ID do aplicativo, selecione **definir**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-396">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

9. <span data-ttu-id="3fc97-397">Ainda na página de **exibir uma API** , na área **escopos definidos por esta API** , selecione **Adicionar um escopo**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-397">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="3fc97-398">No novo escopo:</span><span class="sxs-lookup"><span data-stu-id="3fc97-398">In the new scope:</span></span>

    1. <span data-ttu-id="3fc97-399">Defina o nome do escopo como **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-399">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="3fc97-400">Selecione os administradores e usuários que podem autorizar.</span><span class="sxs-lookup"><span data-stu-id="3fc97-400">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="3fc97-401">Defina os valores restantes necessários.</span><span class="sxs-lookup"><span data-stu-id="3fc97-401">Define any remaining values required.</span></span>

    4. <span data-ttu-id="3fc97-402">Selecione **Adicionar escopo.**</span><span class="sxs-lookup"><span data-stu-id="3fc97-402">Select **Add scope.**</span></span>

    <span data-ttu-id="3fc97-403">Selecione **salvar** na parte superior para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="3fc97-403">Select **Save** at the top to save your changes.</span></span>

10. <span data-ttu-id="3fc97-404">Ainda na página **expor uma API** , na área **aplicativos cliente autorizados** , selecione **Adicionar um aplicativo cliente**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-404">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="3fc97-405">No novo aplicativo cliente:</span><span class="sxs-lookup"><span data-stu-id="3fc97-405">In the new client application:</span></span>

    1. <span data-ttu-id="3fc97-406">Defina a ID do cliente como **d3590ed6-52B3-4102-AEFF-aad2292ab01c**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-406">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="3fc97-407">Esse valor é a ID de cliente do Microsoft Office e permite que o Office obtenha um token de acesso para o armazenamento de chaves.</span><span class="sxs-lookup"><span data-stu-id="3fc97-407">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="3fc97-408">Em **escopos autorizados**, selecione o escopo de **user_impersonation** .</span><span class="sxs-lookup"><span data-stu-id="3fc97-408">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="3fc97-409">Selecione **Adicionar aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="3fc97-409">Select **Add application**.</span></span>

    4. <span data-ttu-id="3fc97-410">Selecione **salvar** na parte superior para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="3fc97-410">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="3fc97-411">O armazenamento de chave do DKE agora está registrado.</span><span class="sxs-lookup"><span data-stu-id="3fc97-411">Your DKE key store is now registered.</span></span> <span data-ttu-id="3fc97-412">Continue [criando rótulos usando o DKE](#create-labels-using-dke).</span><span class="sxs-lookup"><span data-stu-id="3fc97-412">Continue  by [creating labels using DKE](#create-labels-using-dke).</span></span>

## <a name="create-labels-using-dke"></a><span data-ttu-id="3fc97-413">Criar rótulos usando DKE</span><span class="sxs-lookup"><span data-stu-id="3fc97-413">Create labels using DKE</span></span>

<span data-ttu-id="3fc97-414">Depois de registrar seu repositório de chaves, configure os rótulos de confidencialidade no centro de conformidade da Microsoft 365 e aplique a criptografia de chave dupla a esses rótulos.</span><span class="sxs-lookup"><span data-stu-id="3fc97-414">Once you've registered your key store, set up sensitivity labels in the Microsoft 365 compliance center and apply double key encryption to those labels.</span></span>

<span data-ttu-id="3fc97-415">Na interface de usuário de criação de rótulo, selecione a opção **usar criptografia de chave dupla** e digite a URL do ponto de extremidade da sua chave.</span><span class="sxs-lookup"><span data-stu-id="3fc97-415">In the label creation UI, select the **Use Double Key Encryption** option and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="3fc97-416">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3fc97-416">For example:</span></span>

:::image type="content" source="../media/dke-use-dke.png" alt-text="Selecione usar criptografia de chave dupla no centro de conformidade do Microsoft 365":::

<span data-ttu-id="3fc97-418">Quaisquer rótulos do DKE que você adicionar serão iniciados para os usuários nas versões mais recentes dos aplicativos do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="3fc97-418">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="3fc97-419">Pode levar até 24 horas para que os clientes sejam atualizados com os novos rótulos.</span><span class="sxs-lookup"><span data-stu-id="3fc97-419">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="3fc97-420">Habilitar o DKE no cliente</span><span class="sxs-lookup"><span data-stu-id="3fc97-420">Enable DKE in your client</span></span>

<span data-ttu-id="3fc97-421">Se os rótulos do DKE não aparecerem na faixa de opções de confidencialidade no Microsoft Office, o cliente pode não ter o DKE habilitado.</span><span class="sxs-lookup"><span data-stu-id="3fc97-421">If your DKE labels don't appear under the Sensitivity ribbon in Microsoft Office, your client may not have DKE enabled.</span></span>

<span data-ttu-id="3fc97-422">Habilite o DKE para o cliente adicionando as seguintes chaves do registro:</span><span class="sxs-lookup"><span data-stu-id="3fc97-422">Enable DKE for your client by adding the following registry keys:</span></span>

```ini
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
