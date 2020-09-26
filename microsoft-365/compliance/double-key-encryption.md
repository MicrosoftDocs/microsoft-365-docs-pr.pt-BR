---
title: DKE (criptografia de chave dupla)
description: O DKE permite proteger dados altamente confidenciais, mantendo o controle total da sua chave.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 09/22/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 39d7933014f1dc71f8c94e467954d36ede4fb451
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277534"
---
# <a name="double-key-encryption-for-microsoft-365"></a><span data-ttu-id="59c17-103">Criptografia de chave dupla para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="59c17-103">Double Key Encryption for Microsoft 365</span></span>

> <span data-ttu-id="59c17-104">*Aplica-se a: chave de criptografia dupla para o Microsoft 365, [microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [proteção de informações do Azure](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="59c17-104">*Applies to: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="59c17-105">*Instruções para: [cliente de rotulação unificada de proteção de informações do Azure para Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="59c17-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="59c17-106">*Descrição do serviço para: conformidade com a [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="59c17-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="59c17-107">A criptografia de chave dupla (DKE) usa duas chaves juntas para acessar o conteúdo protegido.</span><span class="sxs-lookup"><span data-stu-id="59c17-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="59c17-108">A Microsoft armazena uma chave no Microsoft Azure e você mantém a outra chave.</span><span class="sxs-lookup"><span data-stu-id="59c17-108">Microsoft stores one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="59c17-109">Você mantém o controle total de uma de suas chaves usando o serviço de criptografia de chave dupla.</span><span class="sxs-lookup"><span data-stu-id="59c17-109">You maintain full control of one of your keys using the Double Key Encryption service.</span></span> <span data-ttu-id="59c17-110">Você aplica proteção usando o cliente de rotulação unificado de proteção de informações do Azure para seu conteúdo altamente confidencial.</span><span class="sxs-lookup"><span data-stu-id="59c17-110">You apply protection using The Azure Information Protection unified labeling client to your highly sensitive content.</span></span>

<span data-ttu-id="59c17-111">A criptografia de chave dupla oferece suporte a implantações no local e na nuvem.</span><span class="sxs-lookup"><span data-stu-id="59c17-111">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="59c17-112">Essas implantações ajudam a garantir que os dados criptografados permaneçam opaco onde quer você armazene os dados protegidos.</span><span class="sxs-lookup"><span data-stu-id="59c17-112">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="59c17-113">Para obter mais informações sobre as chaves de raiz de locatários padrão baseadas em nuvem, consulte [Planning and Implementing Your Azure Information Protection locatário Key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span><span class="sxs-lookup"><span data-stu-id="59c17-113">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

## <a name="when-your-organization-should-adopt-dke"></a><span data-ttu-id="59c17-114">Quando sua organização deve adotar o DKE</span><span class="sxs-lookup"><span data-stu-id="59c17-114">When your organization should adopt DKE</span></span>

<span data-ttu-id="59c17-115">A criptografia de chave dupla é destinada a seus dados confidenciais que estão sujeitos aos requisitos de proteção mais rígidos.</span><span class="sxs-lookup"><span data-stu-id="59c17-115">Double Key Encryption is intended for your most sensitive data that is subject to the strictest protection requirements.</span></span> <span data-ttu-id="59c17-116">DKE não se destina a todos os dados.</span><span class="sxs-lookup"><span data-stu-id="59c17-116">DKE is not intended for all data.</span></span> <span data-ttu-id="59c17-117">Em geral, você usará a criptografia de chave dupla para proteger apenas uma parte muito pequena de seus dados gerais.</span><span class="sxs-lookup"><span data-stu-id="59c17-117">In general, you'll be using Double Key Encryption to protect only a very small part of your overall data.</span></span> <span data-ttu-id="59c17-118">Você deve fazer uma auditoria detalhada para identificar os dados certos para abranger essa solução antes de implantar o.</span><span class="sxs-lookup"><span data-stu-id="59c17-118">You should do due diligence in identifying the right data to cover with this solution before you deploy.</span></span> <span data-ttu-id="59c17-119">Em alguns casos, talvez seja necessário restringir o escopo e usar outras soluções para a maioria dos seus dados, como a proteção de informações da Microsoft com chaves gerenciadas pela Microsoft ou BYOK.</span><span class="sxs-lookup"><span data-stu-id="59c17-119">In some cases, you might need to narrow your scope and make use of other solutions for the majority of your data such as Microsoft Information Protection with Microsoft-managed keys or BYOK.</span></span> <span data-ttu-id="59c17-120">Essas soluções são suficientes para documentos que não estão sujeitos a proteções aprimoradas e requisitos normativos.</span><span class="sxs-lookup"><span data-stu-id="59c17-120">These solutions are sufficient for documents that aren't subject to enhanced protections and regulatory requirements.</span></span> <span data-ttu-id="59c17-121">Além disso, essas soluções permitem que você use os serviços mais avançados do Office 365; serviços que você não pode usar com o conteúdo criptografado do DKE.</span><span class="sxs-lookup"><span data-stu-id="59c17-121">Also, these solutions enable you to use the most powerful Office 365 services; services that you can't use with DKE encrypted content.</span></span> <span data-ttu-id="59c17-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="59c17-122">For example:</span></span>

- <span data-ttu-id="59c17-123">Regras de transporte, incluindo antimalware e spam que exigem visibilidade no anexo</span><span class="sxs-lookup"><span data-stu-id="59c17-123">Transport rules including anti-malware and spam that require visibility into the attachment</span></span>
- <span data-ttu-id="59c17-124">Microsoft Delve</span><span class="sxs-lookup"><span data-stu-id="59c17-124">Microsoft Delve</span></span>
- <span data-ttu-id="59c17-125">Descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="59c17-125">eDiscovery</span></span>
- <span data-ttu-id="59c17-126">Pesquisa e indexação de conteúdo</span><span class="sxs-lookup"><span data-stu-id="59c17-126">Content search and indexing</span></span>
- <span data-ttu-id="59c17-127">Office Web Apps incluindo funcionalidade de coautoria</span><span class="sxs-lookup"><span data-stu-id="59c17-127">Office Web Apps including co-authoring functionality</span></span>

<span data-ttu-id="59c17-128">Quaisquer aplicativos ou serviços externos que não estejam integrados ao DKE por meio do SDK MIP não poderão executar ações nos dados criptografados.</span><span class="sxs-lookup"><span data-stu-id="59c17-128">Any external applications or services that are not integrated with DKE through the MIP SDK will be unable to perform actions on the encrypted data.</span></span>

<span data-ttu-id="59c17-129">O Microsoft Information Protection SDK 1.7 + suporta a criptografia de chave dupla; os aplicativos que se integram ao nosso SDK poderão fazer o motivo desses dados com permissões e integrações suficientes no local.</span><span class="sxs-lookup"><span data-stu-id="59c17-129">The Microsoft Information Protection SDK 1.7+ supports Double Key Encryption; applications that integrate with our SDK will be able to reason over this data with sufficient permissions and integrations in place.</span></span>

<span data-ttu-id="59c17-130">Recomendamos que as organizações usem os recursos de proteção de informações da Microsoft (classificação e rotulamento) para proteger a maioria dos seus dados confidenciais e usar somente o DKE para seus dados essenciais.</span><span class="sxs-lookup"><span data-stu-id="59c17-130">We recommend organizations use Microsoft Information protection capabilities (classification and labeling) to protect most of their sensitive data and only use DKE for their mission-critical data.</span></span> <span data-ttu-id="59c17-131">A criptografia de chave dupla é particularmente relevante para dados extremamente confidenciais em setores altamente regulamentados, como serviços financeiros e assistência médica.</span><span class="sxs-lookup"><span data-stu-id="59c17-131">Double Key Encryption is particularly relevant for extremely sensitive data in highly regulated industries such as Financial services and Healthcare.</span></span>

<span data-ttu-id="59c17-132">Se as suas organizações têm qualquer um dos seguintes requisitos, você pode usar o DKE para ajudar a proteger o conteúdo:</span><span class="sxs-lookup"><span data-stu-id="59c17-132">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="59c17-133">Você quer garantir que *apenas você* possa descriptografar o conteúdo protegido, em todas as circunstâncias.</span><span class="sxs-lookup"><span data-stu-id="59c17-133">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="59c17-134">Você não deseja que a Microsoft tenha acesso a dados protegidos por conta própria.</span><span class="sxs-lookup"><span data-stu-id="59c17-134">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="59c17-135">Você tem requisitos normativos para manter chaves dentro de um limite geográfico.</span><span class="sxs-lookup"><span data-stu-id="59c17-135">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="59c17-136">Todas as chaves que você mantém para criptografia e descriptografia de dados são mantidas em seu data center.</span><span class="sxs-lookup"><span data-stu-id="59c17-136">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="59c17-137">Requisitos de sistema e licenciamento para o DKE</span><span class="sxs-lookup"><span data-stu-id="59c17-137">System and licensing requirements for DKE</span></span>

<span data-ttu-id="59c17-138">A **chave dupla de criptografia para o microsoft 365** vem com o Microsoft 365 E5 e o Office 365 e5.</span><span class="sxs-lookup"><span data-stu-id="59c17-138">**Double Key Encryption for Microsoft 365** comes with Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="59c17-139">Se você não tem uma licença do Microsoft 365 e5, é possível inscrever-se em uma [avaliação](https://aka.ms/M365E5ComplianceTrial).</span><span class="sxs-lookup"><span data-stu-id="59c17-139">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="59c17-140">Para obter mais informações sobre essas licenças, consulte [diretrizes de licenciamento da Microsoft 365 para segurança & conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="59c17-140">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="59c17-141">**Proteção de informações do Azure**.</span><span class="sxs-lookup"><span data-stu-id="59c17-141">**Azure Information Protection**.</span></span> <span data-ttu-id="59c17-142">O DKE funciona com rótulos de sensibilidade e requer a proteção de informações do Azure.</span><span class="sxs-lookup"><span data-stu-id="59c17-142">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

<span data-ttu-id="59c17-143">Os rótulos de sensibilidade DKE são disponibilizados para os usuários finais por meio da faixa de opções de confidencialidade em aplicativos de área de trabalho do Office.</span><span class="sxs-lookup"><span data-stu-id="59c17-143">DKE sensitivity labels are made available to end-users through the sensitivity ribbon in Office Desktop Apps.</span></span> <span data-ttu-id="59c17-144">Instale esses pré-requisitos em cada computador cliente onde você deseja proteger e consumir documentos protegidos.</span><span class="sxs-lookup"><span data-stu-id="59c17-144">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="59c17-145">**Aplicativos do Microsoft Office para Enterprise** versão \*. 12711 ou posterior (versões da área de trabalho do Word, PowerPoint e Excel) no Windows.</span><span class="sxs-lookup"><span data-stu-id="59c17-145">**Microsoft Office Apps for enterprise** version \*.12711 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

<span data-ttu-id="59c17-146">Versões **unificadas de rótulo do cliente de proteção de informações do Azure** 2.7.93.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="59c17-146">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="59c17-147">Baixe e instale o cliente de rotulação unificada no [centro de download da Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="59c17-147">Download and install the Unified Labeling client from the [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="59c17-148">Ambientes suportados para armazenar e exibir o conteúdo protegido por DKE</span><span class="sxs-lookup"><span data-stu-id="59c17-148">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="59c17-149">**Aplicativos com suporte**.</span><span class="sxs-lookup"><span data-stu-id="59c17-149">**Supported applications**.</span></span> <span data-ttu-id="59c17-150">[Microsoft 365 aplicativos para clientes corporativos](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) no Windows, incluindo Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="59c17-150">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="59c17-151">**Suporte a conteúdo online**.</span><span class="sxs-lookup"><span data-stu-id="59c17-151">**Online content support**.</span></span> <span data-ttu-id="59c17-152">Há suporte para documentos e arquivos armazenados online no Microsoft SharePoint e no OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="59c17-152">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="59c17-153">Você pode compartilhar conteúdo criptografado por email, mas não pode exibir documentos e arquivos criptografados online.</span><span class="sxs-lookup"><span data-stu-id="59c17-153">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="59c17-154">Em vez disso, você deve exibir o conteúdo protegido usando os aplicativos de área de trabalho no computador local.</span><span class="sxs-lookup"><span data-stu-id="59c17-154">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="overview-of-deploying-dke"></a><span data-ttu-id="59c17-155">Visão geral da implantação do DKE</span><span class="sxs-lookup"><span data-stu-id="59c17-155">Overview of deploying DKE</span></span>

<span data-ttu-id="59c17-156">Siga estas etapas gerais para configurar o DKE.</span><span class="sxs-lookup"><span data-stu-id="59c17-156">You'll follow these general steps to set up DKE.</span></span> <span data-ttu-id="59c17-157">Depois de concluir essas etapas, os usuários finais poderão proteger seus dados altamente confidenciais com a criptografia de chave dupla.</span><span class="sxs-lookup"><span data-stu-id="59c17-157">Once you've completed these steps, your end users will be able to protect your highly sensitive data with Double Key Encryption.</span></span>

1. <span data-ttu-id="59c17-158">Implante o serviço DKE conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="59c17-158">Deploy the DKE service as described in this article.</span></span>

2. <span data-ttu-id="59c17-159">Criar um rótulo com criptografia de chave dupla.</span><span class="sxs-lookup"><span data-stu-id="59c17-159">Create a label with Double Key Encryption.</span></span> <span data-ttu-id="59c17-160">Navegue até proteção de informações no [centro de conformidade da Microsoft 365](https://compliance.microsoft.com) e crie um novo rótulo com criptografia de chave dupla.</span><span class="sxs-lookup"><span data-stu-id="59c17-160">Navigate to Information protection under the [Microsoft 365 compliance center](https://compliance.microsoft.com) and create a new label with Double Key Encryption.</span></span> <span data-ttu-id="59c17-161">Consulte [restringir o acesso ao conteúdo usando rótulos de confidencialidade para aplicar criptografia](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="59c17-161">See [Restrict access to content by using sensitivity labels to apply encryption](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels).</span></span>

3. <span data-ttu-id="59c17-162">Use rótulos de criptografia de chave dupla.</span><span class="sxs-lookup"><span data-stu-id="59c17-162">Use Double Key Encryption labels.</span></span> <span data-ttu-id="59c17-163">Proteja os dados selecionando o rótulo de chave dupla e criptografado na faixa de opções de confidencialidade no Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="59c17-163">Protect data by selecting the Double Key Encrypted label from the Sensitivity ribbon in Microsoft Office.</span></span>

<span data-ttu-id="59c17-164">Há várias maneiras de realizar algumas das etapas para implantar a criptografia de chave dupla.</span><span class="sxs-lookup"><span data-stu-id="59c17-164">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="59c17-165">Este artigo fornece instruções detalhadas para que administradores menos experientes implantem o serviço com êxito.</span><span class="sxs-lookup"><span data-stu-id="59c17-165">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="59c17-166">Se você estiver confortável para fazer isso, você pode optar por usar seus próprios métodos.</span><span class="sxs-lookup"><span data-stu-id="59c17-166">If you're comfortable doing so, you can choose to use your own methods.</span></span>

## <a name="deploy-dke"></a><span data-ttu-id="59c17-167">Implantar DKE</span><span class="sxs-lookup"><span data-stu-id="59c17-167">Deploy DKE</span></span>

<span data-ttu-id="59c17-168">Este artigo e o vídeo de implantação usam o Azure como o destino de implantação para o serviço DKE.</span><span class="sxs-lookup"><span data-stu-id="59c17-168">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="59c17-169">Se você estiver implantando em outro local, precisará fornecer seus próprios valores.</span><span class="sxs-lookup"><span data-stu-id="59c17-169">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="59c17-170">Assista ao [vídeo de implantação de criptografia de chave dupla](https://youtu.be/vDWfHN_kygg) para ver uma visão geral passo a passo dos conceitos deste artigo.</span><span class="sxs-lookup"><span data-stu-id="59c17-170">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see a step-by-step overview of the concepts in this article.</span></span> <span data-ttu-id="59c17-171">O vídeo leva cerca de 18 minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="59c17-171">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="59c17-172">Siga estas etapas gerais para configurar a criptografia de chave dupla para sua organização.</span><span class="sxs-lookup"><span data-stu-id="59c17-172">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="59c17-173">Instalar pré-requisitos de software para o serviço DKE</span><span class="sxs-lookup"><span data-stu-id="59c17-173">Install software prerequisites for the DKE service</span></span>](#install-software-prerequisites-for-the-dke-service)
1. [<span data-ttu-id="59c17-174">Clone o repositório do GitHub de criptografia de chave dupla</span><span class="sxs-lookup"><span data-stu-id="59c17-174">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="59c17-175">Modificar configurações do aplicativo</span><span class="sxs-lookup"><span data-stu-id="59c17-175">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="59c17-176">Gerar chaves de teste</span><span class="sxs-lookup"><span data-stu-id="59c17-176">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="59c17-177">Compilar o projeto</span><span class="sxs-lookup"><span data-stu-id="59c17-177">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="59c17-178">Implantar o serviço DKE e publicar o repositório de chaves</span><span class="sxs-lookup"><span data-stu-id="59c17-178">Deploy the DKE service and publish the key store</span></span>](#deploy-the-dke-service-and-publish-the-key-store)
1. [<span data-ttu-id="59c17-179">Validar sua implantação</span><span class="sxs-lookup"><span data-stu-id="59c17-179">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="59c17-180">Registrar seu repositório de chaves</span><span class="sxs-lookup"><span data-stu-id="59c17-180">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="59c17-181">Criar rótulos de confidencialidade usando DKE</span><span class="sxs-lookup"><span data-stu-id="59c17-181">Create sensitivity labels using DKE</span></span>](#create-sensitivity-labels-using-dke)
1. [<span data-ttu-id="59c17-182">Habilitar o DKE no cliente</span><span class="sxs-lookup"><span data-stu-id="59c17-182">Enable DKE in your client</span></span>](#enable-dke-in-your-client)
1. [<span data-ttu-id="59c17-183">Migrar arquivos protegidos de rótulos do HYOK para rótulos do DKE</span><span class="sxs-lookup"><span data-stu-id="59c17-183">Migrate protected files from HYOK labels to DKE labels</span></span>](#migrate-protected-files-from-hyok-labels-to-dke-labels)

<span data-ttu-id="59c17-184">Quando tiver concluído, você poderá criptografar documentos e arquivos usando o DKE.</span><span class="sxs-lookup"><span data-stu-id="59c17-184">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="59c17-185">Para saber mais, confira [aplicar rótulos de confidencialidade aos seus arquivos e emails no Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span><span class="sxs-lookup"><span data-stu-id="59c17-185">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites-for-the-dke-service"></a><span data-ttu-id="59c17-186">Instalar pré-requisitos de software para o serviço DKE</span><span class="sxs-lookup"><span data-stu-id="59c17-186">Install software prerequisites for the DKE service</span></span>

<span data-ttu-id="59c17-187">Instale esses pré-requisitos no computador onde você deseja instalar o serviço DKE.</span><span class="sxs-lookup"><span data-stu-id="59c17-187">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="59c17-188">**SDK do .NET Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="59c17-188">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="59c17-189">Baixe e instale o SDK do [download do .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="59c17-189">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="59c17-190">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="59c17-190">**Visual Studio Code**.</span></span> <span data-ttu-id="59c17-191">Baixe o Visual Studio Code de [https://code.visualstudio.com/](https://code.visualstudio.com) .</span><span class="sxs-lookup"><span data-stu-id="59c17-191">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="59c17-192">Depois de instalado, execute o Visual Studio Code e selecione **View** \> **Extensions**.</span><span class="sxs-lookup"><span data-stu-id="59c17-192">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="59c17-193">Instale essas extensões.</span><span class="sxs-lookup"><span data-stu-id="59c17-193">Install these extensions.</span></span>

- <span data-ttu-id="59c17-194">C# para o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="59c17-194">C# for Visual Studio Code</span></span>

- <span data-ttu-id="59c17-195">Gerenciador de pacotes do NuGet</span><span class="sxs-lookup"><span data-stu-id="59c17-195">NuGet Package Manager</span></span>

<span data-ttu-id="59c17-196">**Recursos git**.</span><span class="sxs-lookup"><span data-stu-id="59c17-196">**Git resources**.</span></span> <span data-ttu-id="59c17-197">Baixe e instale um dos seguintes.</span><span class="sxs-lookup"><span data-stu-id="59c17-197">Download and install one of the following.</span></span>

- [<span data-ttu-id="59c17-198">Git</span><span class="sxs-lookup"><span data-stu-id="59c17-198">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="59c17-199">Área de trabalho do GitHub</span><span class="sxs-lookup"><span data-stu-id="59c17-199">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="59c17-200">GitHub corporativo</span><span class="sxs-lookup"><span data-stu-id="59c17-200">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="59c17-201">**OpenSSL** Você deve ter o [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) instalado para [gerar chaves de teste](#generate-test-keys) depois de implantar o DKE.</span><span class="sxs-lookup"><span data-stu-id="59c17-201">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="59c17-202">Certifique-se de que você está invocando-o corretamente de seu caminho de variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="59c17-202">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="59c17-203">Por exemplo, consulte "Adicionar o diretório de instalação ao caminho" [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="59c17-203">For example, see "Add the installation directory to PATH" at [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) for details.</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="59c17-204">Clonar o repositório do GitHub DKE</span><span class="sxs-lookup"><span data-stu-id="59c17-204">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="59c17-205">A Microsoft fornece os arquivos de origem do DKE em um repositório do GitHub.</span><span class="sxs-lookup"><span data-stu-id="59c17-205">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="59c17-206">Você clona o repositório para compilar o projeto localmente para uso da sua organização.</span><span class="sxs-lookup"><span data-stu-id="59c17-206">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="59c17-207">O repositório do GitHub do DKE está localizado em [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="59c17-207">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="59c17-208">As instruções a seguir se destinam a usuários do git ou do Visual Studio Code inexperientes:</span><span class="sxs-lookup"><span data-stu-id="59c17-208">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="59c17-209">No navegador, vá para: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="59c17-209">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

2. <span data-ttu-id="59c17-210">No lado direito da tela, selecione **código**.</span><span class="sxs-lookup"><span data-stu-id="59c17-210">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="59c17-211">Sua versão da interface do usuário pode mostrar um botão **clone ou download** .</span><span class="sxs-lookup"><span data-stu-id="59c17-211">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="59c17-212">Em seguida, na lista suspensa exibida, selecione o ícone Copiar para copiar a URL para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="59c17-212">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="59c17-213">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="59c17-213">For example:</span></span>

   ![Clonar o repositório de serviço de criptografia de chave dupla do GitHub](../media/dke-clone.png)

3. <span data-ttu-id="59c17-215">No Visual Studio Code, selecione **Exibir** \> **paleta de comandos** e selecione **git: clonar**.</span><span class="sxs-lookup"><span data-stu-id="59c17-215">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="59c17-216">Para ir para a opção na lista, comece a digitar `git: clone` para filtrar as entradas e, em seguida, selecione-a no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="59c17-216">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="59c17-217">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="59c17-217">For example:</span></span>

   ![Visual Studio Code GIT: opção clone](../media/dke-vscode-clone.png)

4. <span data-ttu-id="59c17-219">Na caixa de texto, Cole a URL que você copiou do git e selecione **clonar do GitHub**.</span><span class="sxs-lookup"><span data-stu-id="59c17-219">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="59c17-220">Na caixa de diálogo **Selecionar pasta** exibida, procure e selecione um local para armazenar o repositório.</span><span class="sxs-lookup"><span data-stu-id="59c17-220">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="59c17-221">No prompt, selecione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="59c17-221">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="59c17-222">O repositório é aberto no Visual Studio Code e exibe a ramificação atual do git no canto inferior esquerdo.</span><span class="sxs-lookup"><span data-stu-id="59c17-222">The repository opens in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="59c17-223">A ramificação deve ser **mestra**.</span><span class="sxs-lookup"><span data-stu-id="59c17-223">The branch should be **master**.</span></span>

    <span data-ttu-id="59c17-224">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="59c17-224">For example:</span></span>

   ![Ramificação do Visual Studio Code Master](../media/dke-vscode-master.png)

6. <span data-ttu-id="59c17-226">Selecione o Word **Master** na lista de ramificações.</span><span class="sxs-lookup"><span data-stu-id="59c17-226">Select the word **master** from the list of branches.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="59c17-227">Selecionar a ramificação principal garante que você tenha os arquivos corretos para compilar o projeto.</span><span class="sxs-lookup"><span data-stu-id="59c17-227">Selecting the master branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="59c17-228">Se você não escolher a ramificação correta, sua implantação falhará.</span><span class="sxs-lookup"><span data-stu-id="59c17-228">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="59c17-229">Agora, o seu repositório de origem do DKE está configurado localmente.</span><span class="sxs-lookup"><span data-stu-id="59c17-229">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="59c17-230">Em seguida, [modifique as configurações de aplicativo](#modify-application-settings) para sua organização.</span><span class="sxs-lookup"><span data-stu-id="59c17-230">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="59c17-231">Modificar configurações do aplicativo</span><span class="sxs-lookup"><span data-stu-id="59c17-231">Modify application settings</span></span>

<span data-ttu-id="59c17-232">Para implantar o serviço DKE, você deve modificar os seguintes tipos de configurações de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="59c17-232">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="59c17-233">Configurações de acesso de chave</span><span class="sxs-lookup"><span data-stu-id="59c17-233">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="59c17-234">Definições de locatário e chave</span><span class="sxs-lookup"><span data-stu-id="59c17-234">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="59c17-235">Você modifica as configurações de aplicativo no appsettings.jsem arquivo.</span><span class="sxs-lookup"><span data-stu-id="59c17-235">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="59c17-236">Esse arquivo está localizado no repositório do DoubleKeyEncryptionService que você clonou localmente em DoubleKeyEncryptionService\src\customer-key-store.</span><span class="sxs-lookup"><span data-stu-id="59c17-236">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="59c17-237">Por exemplo, no Visual Studio Code, você pode navegar até o arquivo, conforme mostrado na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="59c17-237">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![Localizar o appsettings.jsno arquivo do DKE.](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="59c17-239">Configurações de acesso de chave</span><span class="sxs-lookup"><span data-stu-id="59c17-239">Key access settings</span></span>

<span data-ttu-id="59c17-240">Escolha se deseja usar o email ou a autorização de função.</span><span class="sxs-lookup"><span data-stu-id="59c17-240">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="59c17-241">O DKE oferece suporte a apenas um desses métodos de autenticação por vez.</span><span class="sxs-lookup"><span data-stu-id="59c17-241">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="59c17-242">**Autorização de email**.</span><span class="sxs-lookup"><span data-stu-id="59c17-242">**Email authorization**.</span></span> <span data-ttu-id="59c17-243">Permite que sua organização autorize o acesso a chaves com base apenas em endereços de email.</span><span class="sxs-lookup"><span data-stu-id="59c17-243">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="59c17-244">**Autorização de função**.</span><span class="sxs-lookup"><span data-stu-id="59c17-244">**Role authorization**.</span></span> <span data-ttu-id="59c17-245">Permite que sua organização autorize o acesso às chaves com base nos grupos do Active Directory e exige que o serviço Web possa consultar o LDAP.</span><span class="sxs-lookup"><span data-stu-id="59c17-245">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="59c17-246">**Para definir as configurações de acesso de chave do DKE usando autorização de email**</span><span class="sxs-lookup"><span data-stu-id="59c17-246">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="59c17-247">Abra o **appsettings.jsem** arquivo e localize a `AuthorizedEmailAddress` configuração.</span><span class="sxs-lookup"><span data-stu-id="59c17-247">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="59c17-248">Adicione o endereço de email ou endereços que você deseja autorizar.</span><span class="sxs-lookup"><span data-stu-id="59c17-248">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="59c17-249">Separe vários endereços de email com aspas duplas e vírgulas.</span><span class="sxs-lookup"><span data-stu-id="59c17-249">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="59c17-250">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="59c17-250">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="59c17-251">Localize a `LDAPPath` configuração e remova o texto `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` entre aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="59c17-251">Locate the `LDAPPath` setting and remove the text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` between the double quotes.</span></span> <span data-ttu-id="59c17-252">Deixe as aspas duplas em vigor.</span><span class="sxs-lookup"><span data-stu-id="59c17-252">Leave the double quotes in place.</span></span> <span data-ttu-id="59c17-253">Quando você tiver terminado, a configuração deverá ter a seguinte aparência.</span><span class="sxs-lookup"><span data-stu-id="59c17-253">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="59c17-254">Localize a `AuthorizedRoles` configuração e exclua a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="59c17-254">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="59c17-255">Esta imagem mostra o **appsettings.jsem** arquivo formatado corretamente para autorização de email.</span><span class="sxs-lookup"><span data-stu-id="59c17-255">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![O appsettings.jsem arquivo mostrando o método de autorização de email](../media/dke-email-accesssetting.png)

<span data-ttu-id="59c17-257">**Para definir as configurações de acesso de chave para DKE usando autorização de função**</span><span class="sxs-lookup"><span data-stu-id="59c17-257">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="59c17-258">Abra o **appsettings.jsem** arquivo e localize a `AuthorizedRoles` configuração.</span><span class="sxs-lookup"><span data-stu-id="59c17-258">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="59c17-259">Adicione os nomes de grupo do Active Directory que você deseja autorizar.</span><span class="sxs-lookup"><span data-stu-id="59c17-259">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="59c17-260">Separe vários nomes de grupo com aspas duplas e vírgulas.</span><span class="sxs-lookup"><span data-stu-id="59c17-260">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="59c17-261">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="59c17-261">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="59c17-262">Localize a `LDAPPath` configuração e adicione o domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="59c17-262">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="59c17-263">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="59c17-263">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="59c17-264">Localize a `AuthorizedEmailAddress` configuração e exclua a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="59c17-264">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="59c17-265">Esta imagem mostra o **appsettings.jsem** arquivo formatado corretamente para autorização de função.</span><span class="sxs-lookup"><span data-stu-id="59c17-265">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![appsettings.jsem arquivo mostrando o método de autorização de função](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="59c17-267">Definições de locatário e chave</span><span class="sxs-lookup"><span data-stu-id="59c17-267">Tenant and key settings</span></span>

<span data-ttu-id="59c17-268">As configurações de locatário e chave do DKE estão localizadas na **appsettings.jsem** arquivo.</span><span class="sxs-lookup"><span data-stu-id="59c17-268">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="59c17-269">**Para definir as configurações de locatário e chave do DKE**</span><span class="sxs-lookup"><span data-stu-id="59c17-269">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="59c17-270">Abra o **appsettings.jsem** arquivo.</span><span class="sxs-lookup"><span data-stu-id="59c17-270">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="59c17-271">Localize a `ValidIssuers` configuração e substitua `<tenantid>` pela ID do locatário.</span><span class="sxs-lookup"><span data-stu-id="59c17-271">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="59c17-272">Você pode localizar sua ID de locatário indo para o portal do Azure e exibindo as [Propriedades do locatário](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="59c17-272">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="59c17-273">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="59c17-273">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="59c17-274">Localize o `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="59c17-274">Locate the `JwtAudience`.</span></span> <span data-ttu-id="59c17-275">Substitua `<yourhostname>` pelo nome do host do computador em que o serviço DKE será executado.</span><span class="sxs-lookup"><span data-stu-id="59c17-275">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="59c17-276">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="59c17-276">For example:</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="59c17-277">O valor de `JwtAudience` deve corresponder *exatamente*ao nome do host.</span><span class="sxs-lookup"><span data-stu-id="59c17-277">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="59c17-278">Você pode usar **localhost: 5001** durante a depuração.</span><span class="sxs-lookup"><span data-stu-id="59c17-278">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="59c17-279">No entanto, quando você terminar de depurar, certifique-se de atualizar esse valor para o nome de host do servidor.</span><span class="sxs-lookup"><span data-stu-id="59c17-279">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="59c17-280">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="59c17-280">`TestKeys:Name`.</span></span> <span data-ttu-id="59c17-281">Insira um nome para a chave.</span><span class="sxs-lookup"><span data-stu-id="59c17-281">Enter a name for your key.</span></span> <span data-ttu-id="59c17-282">Por exemplo: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="59c17-282">For example: `TestKey1`</span></span>
- <span data-ttu-id="59c17-283">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="59c17-283">`TestKeys:Id`.</span></span> <span data-ttu-id="59c17-284">Crie um GUID e insira-o como o `TestKeys:ID` valor.</span><span class="sxs-lookup"><span data-stu-id="59c17-284">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="59c17-285">Por exemplo, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span><span class="sxs-lookup"><span data-stu-id="59c17-285">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="59c17-286">Você pode usar um site como [gerador de GUID online](https://guidgenerator.com/) para gerar aleatoriamente um GUID.</span><span class="sxs-lookup"><span data-stu-id="59c17-286">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="59c17-287">Esta imagem mostra o formato correto das configurações de locatário e chaves em **appsettings.js**.</span><span class="sxs-lookup"><span data-stu-id="59c17-287">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="59c17-288">`LDAPPath` é configurada para autorização de função.</span><span class="sxs-lookup"><span data-stu-id="59c17-288">`LDAPPath` is configured for role authorization.</span></span>

![Mostra as configurações de locatário e chave corretas para o DKE no arquivo appsettings.js.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="59c17-290">Gerar chaves de teste</span><span class="sxs-lookup"><span data-stu-id="59c17-290">Generate test keys</span></span>

<span data-ttu-id="59c17-291">Depois de definir as configurações do aplicativo, você estará pronto para gerar chaves de teste públicas e privadas.</span><span class="sxs-lookup"><span data-stu-id="59c17-291">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="59c17-292">Para gerar chaves:</span><span class="sxs-lookup"><span data-stu-id="59c17-292">To generate keys:</span></span>

1. <span data-ttu-id="59c17-293">No menu Iniciar do Windows, execute o prompt de comando OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="59c17-293">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

2. <span data-ttu-id="59c17-294">Vá para a pasta onde você deseja salvar as teclas de teste.</span><span class="sxs-lookup"><span data-stu-id="59c17-294">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="59c17-295">Os arquivos que você cria ao concluir as etapas dessa tarefa são armazenados na mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="59c17-295">The files you create by completing the steps in this task are stored in the same folder.</span></span>

3. <span data-ttu-id="59c17-296">Gere a nova chave de teste.</span><span class="sxs-lookup"><span data-stu-id="59c17-296">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. <span data-ttu-id="59c17-297">Gerar a chave privada.</span><span class="sxs-lookup"><span data-stu-id="59c17-297">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. <span data-ttu-id="59c17-298">Gere a chave pública.</span><span class="sxs-lookup"><span data-stu-id="59c17-298">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. <span data-ttu-id="59c17-299">Em um editor de texto, abra **pubkeyonly. pem**.</span><span class="sxs-lookup"><span data-stu-id="59c17-299">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="59c17-300">Copie todo o conteúdo do arquivo **pubkeyonly. pem** , exceto a primeira e a última linha, na `PublicPem` seção do **appsettings.jsem** arquivo.</span><span class="sxs-lookup"><span data-stu-id="59c17-300">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

7. <span data-ttu-id="59c17-301">Em um editor de texto, abra **privkeynopass. pem**.</span><span class="sxs-lookup"><span data-stu-id="59c17-301">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="59c17-302">Copie todo o conteúdo do arquivo **privkeynopass. pem** , exceto a primeira e a última linha, na `PrivatePem` seção do **appsettings.jsem** arquivo.</span><span class="sxs-lookup"><span data-stu-id="59c17-302">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

8. <span data-ttu-id="59c17-303">Remova todos os espaços em branco e novas linhas em ambas as `PublicPem` `PrivatePem` seções e.</span><span class="sxs-lookup"><span data-stu-id="59c17-303">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="59c17-304">Ao copiar esse conteúdo, não exclua nenhum dos dados de PEM.</span><span class="sxs-lookup"><span data-stu-id="59c17-304">When you copy this content, do not delete any of the PEM data.</span></span>

9. <span data-ttu-id="59c17-305">No Visual Studio Code, navegue até o arquivo **Startup.cs** .</span><span class="sxs-lookup"><span data-stu-id="59c17-305">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="59c17-306">Esse arquivo está localizado no repositório do DoubleKeyEncryptionService que você clonou localmente em DoubleKeyEncryptionService\src\customer-key-store\.</span><span class="sxs-lookup"><span data-stu-id="59c17-306">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

10. <span data-ttu-id="59c17-307">Localize as seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="59c17-307">Locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

11. <span data-ttu-id="59c17-308">Substitua essas linhas pelo seguinte texto:</span><span class="sxs-lookup"><span data-stu-id="59c17-308">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="59c17-309">Os resultados finais devem ser semelhantes aos seguintes.</span><span class="sxs-lookup"><span data-stu-id="59c17-309">The end results should look similar to the following.</span></span>

   ![arquivo startup.cs para visualização pública](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="59c17-311">Agora você está pronto para [criar seu projeto do DKE](#build-the-project).</span><span class="sxs-lookup"><span data-stu-id="59c17-311">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="59c17-312">Compilar o projeto</span><span class="sxs-lookup"><span data-stu-id="59c17-312">Build the project</span></span>

<span data-ttu-id="59c17-313">Use as instruções a seguir para criar o projeto do DKE localmente:</span><span class="sxs-lookup"><span data-stu-id="59c17-313">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="59c17-314">No Visual Studio Code, no repositório de serviços do DKE, selecione **Exibir** \> **paleta de comandos** e digite **Compilar** no prompt.</span><span class="sxs-lookup"><span data-stu-id="59c17-314">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

2. <span data-ttu-id="59c17-315">Na lista, escolha **tarefas: executar tarefa de compilação**.</span><span class="sxs-lookup"><span data-stu-id="59c17-315">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="59c17-316">Se não houver tarefas de compilação encontradas, selecione **Configurar tarefa de compilação** e criar uma para o .NET Core da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="59c17-316">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![Configurar a tarefa de compilação ausente para o .NET](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="59c17-318">Escolha **criar tasks.jsno modelo**.</span><span class="sxs-lookup"><span data-stu-id="59c17-318">Choose **Create tasks.json from template**.</span></span>

      ![Criar tasks.jsno arquivo do modelo do DKE](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="59c17-320">Na lista de tipos de modelo, selecione **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="59c17-320">From the list of template types, select **.NET Core**.</span></span>

      ![Selecione o modelo correto para o DKE](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="59c17-322">Na seção criar, localize o caminho para o arquivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="59c17-322">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="59c17-323">Se ele não estiver lá, adicione a seguinte linha:</span><span class="sxs-lookup"><span data-stu-id="59c17-323">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. <span data-ttu-id="59c17-324">Execute novamente a compilação.</span><span class="sxs-lookup"><span data-stu-id="59c17-324">Run the build again.</span></span>

3. <span data-ttu-id="59c17-325">Verifique se não há nenhum erro vermelho na janela de saída.</span><span class="sxs-lookup"><span data-stu-id="59c17-325">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="59c17-326">Se houver erros vermelhos, verifique a saída do console.</span><span class="sxs-lookup"><span data-stu-id="59c17-326">If there are red errors, check the console output.</span></span> <span data-ttu-id="59c17-327">Verifique se você concluiu todas as etapas anteriores corretamente e se as versões de compilação corretas estão presentes.</span><span class="sxs-lookup"><span data-stu-id="59c17-327">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

4. <span data-ttu-id="59c17-328">Selecione **executar** \> **Iniciar Depuração** para depurar o processo.</span><span class="sxs-lookup"><span data-stu-id="59c17-328">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="59c17-329">Se for solicitado a selecionar um ambiente, selecione **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="59c17-329">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="59c17-330">O depurador do .NET Core normalmente é iniciado no `https://localhost:5001` .</span><span class="sxs-lookup"><span data-stu-id="59c17-330">The .NET core debugger typically launches to `https://localhost:5001`.</span></span> <span data-ttu-id="59c17-331">Para exibir sua chave de teste, vá para `https://localhost:5001` e acrescente uma barra (/) e o nome da sua chave.</span><span class="sxs-lookup"><span data-stu-id="59c17-331">To view your test key, go to `https://localhost:5001` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="59c17-332">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="59c17-332">For example:</span></span>

```https
https://localhost:5001/TestKey1
```

<span data-ttu-id="59c17-333">A chave deve ser exibida no formato JSON.</span><span class="sxs-lookup"><span data-stu-id="59c17-333">The key should display in JSON format.</span></span>

<span data-ttu-id="59c17-334">A configuração já está concluída.</span><span class="sxs-lookup"><span data-stu-id="59c17-334">Your setup is now complete.</span></span> <span data-ttu-id="59c17-335">Antes de publicar o repositório de chaves, em appsettings.js, para a configuração do JwtAudience, verifique se o valor do nome do host corresponde exatamente ao nome de host do serviço de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59c17-335">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="59c17-336">Você pode ter alterado para localhost para solucionar problemas de compilação.</span><span class="sxs-lookup"><span data-stu-id="59c17-336">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a><span data-ttu-id="59c17-337">Implantar o serviço DKE e publicar o repositório de chaves</span><span class="sxs-lookup"><span data-stu-id="59c17-337">Deploy the DKE service and publish the key store</span></span>

<span data-ttu-id="59c17-338">Para implantações de produção, implante o serviço em uma nuvem de terceiros ou [publique em um sistema local](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli).</span><span class="sxs-lookup"><span data-stu-id="59c17-338">For production deployments, deploy the service either in a third-party cloud or [publish to an on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli).</span></span>

<span data-ttu-id="59c17-339">Você pode preferir outros métodos para implantar suas chaves.</span><span class="sxs-lookup"><span data-stu-id="59c17-339">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="59c17-340">Selecione o método que funciona melhor para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="59c17-340">Select the method that works best for your organization.</span></span>

<span data-ttu-id="59c17-341">Para implantações piloto, você pode implantar no Azure e começar imediatamente.</span><span class="sxs-lookup"><span data-stu-id="59c17-341">For pilot deployments, you can deploy in Azure and get started right away.</span></span>

<span data-ttu-id="59c17-342">**Para criar uma instância do Azure Web App para hospedar sua implantação do DKE**</span><span class="sxs-lookup"><span data-stu-id="59c17-342">**To create an Azure Web App instance to host your DKE deployment**</span></span>

<span data-ttu-id="59c17-343">Para publicar o repositório de chaves, você criará uma instância do serviço de aplicativo do Azure para hospedar sua implantação do DKE.</span><span class="sxs-lookup"><span data-stu-id="59c17-343">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="59c17-344">Em seguida, você publicará as chaves geradas no Azure.</span><span class="sxs-lookup"><span data-stu-id="59c17-344">Next, you'll publish your generated keys to Azure.</span></span>

1. <span data-ttu-id="59c17-345">No navegador, entre no [portal do Microsoft Azure](https://ms.portal.azure.com)e vá para a adição de **serviços de aplicativo**  >  **Add**.</span><span class="sxs-lookup"><span data-stu-id="59c17-345">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

2. <span data-ttu-id="59c17-346">Selecione sua assinatura e o grupo de recursos e defina os detalhes da instância.</span><span class="sxs-lookup"><span data-stu-id="59c17-346">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="59c17-347">Insira o nome de host do computador onde você deseja instalar o serviço DKE.</span><span class="sxs-lookup"><span data-stu-id="59c17-347">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="59c17-348">Certifique-se de que é o mesmo nome que o definido para a configuração JwtAudience no arquivo de [**appsettings.js**](#tenant-and-key-settings) .</span><span class="sxs-lookup"><span data-stu-id="59c17-348">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="59c17-349">O valor que você fornece para o nome também é o WebAppInstanceName.</span><span class="sxs-lookup"><span data-stu-id="59c17-349">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="59c17-350">Para **publicar**, selecione **código**e para **pilha de tempo de execução**, selecione **.NET Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="59c17-350">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="59c17-351">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="59c17-351">For example:</span></span>

   ![Adicionar seu serviço de aplicativo](../media/dke-azure-add-app-service.png)

3. <span data-ttu-id="59c17-353">Na parte inferior da página, selecione **revisar + criar**e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="59c17-353">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

4. <span data-ttu-id="59c17-354">Siga um destes procedimentos para publicar suas chaves geradas:</span><span class="sxs-lookup"><span data-stu-id="59c17-354">Do one of the following to publish your generated keys:</span></span>

    - [<span data-ttu-id="59c17-355">Publicar via ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="59c17-355">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="59c17-356">Publicar via FTP</span><span class="sxs-lookup"><span data-stu-id="59c17-356">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="59c17-357">Publicar via Visual Studio 2019 ou posterior</span><span class="sxs-lookup"><span data-stu-id="59c17-357">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="59c17-358">Publicar via ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="59c17-358">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="59c17-359">Vá para `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span><span class="sxs-lookup"><span data-stu-id="59c17-359">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="59c17-360">Por exemplo: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="59c17-360">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

2. <span data-ttu-id="59c17-361">Na base de código do armazenamento de chaves, vá para a pasta **Customer-Key-store\src\customer-Key-Store** e verifique se essa pasta contém o arquivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="59c17-361">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

3. <span data-ttu-id="59c17-362">Executar: **publicação de dotnet**</span><span class="sxs-lookup"><span data-stu-id="59c17-362">Run: **dotnet publish**</span></span>

     <span data-ttu-id="59c17-363">A janela saída exibe o diretório onde a publicação foi implantada.</span><span class="sxs-lookup"><span data-stu-id="59c17-363">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="59c17-364">Por exemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="59c17-364">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

4. <span data-ttu-id="59c17-365">Envie todos os arquivos no diretório de publicação para um arquivo. zip.</span><span class="sxs-lookup"><span data-stu-id="59c17-365">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="59c17-366">Ao criar o arquivo. zip, verifique se todos os arquivos no diretório estão no nível raiz do arquivo. zip.</span><span class="sxs-lookup"><span data-stu-id="59c17-366">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

5. <span data-ttu-id="59c17-367">Arraste e solte o arquivo. zip criado no site do ZipDeployUI que você abriu acima.</span><span class="sxs-lookup"><span data-stu-id="59c17-367">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="59c17-368">Por exemplo: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="59c17-368">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="59c17-369">O DKE é implantado e você pode navegar até as chaves de teste que você criou.</span><span class="sxs-lookup"><span data-stu-id="59c17-369">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="59c17-370">Continue para [validar sua implantação](#validate-your-deployment) abaixo.</span><span class="sxs-lookup"><span data-stu-id="59c17-370">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="59c17-371">Publicar via FTP</span><span class="sxs-lookup"><span data-stu-id="59c17-371">Publish via FTP</span></span>

1. <span data-ttu-id="59c17-372">Conecte-se ao serviço de aplicativo que você criou [acima](#deploy-the-dke-service-and-publish-the-key-store).</span><span class="sxs-lookup"><span data-stu-id="59c17-372">Connect to the App Service you created [above](#deploy-the-dke-service-and-publish-the-key-store).</span></span>

    <span data-ttu-id="59c17-373">Em seu navegador, vá para: centro de implantação do serviço de aplicativo **do portal do Azure**  >  **App Service**  >  **Deployment Center**  >  painel de FTP de**implantação manual**  >  **FTP**  >  **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="59c17-373">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

2. <span data-ttu-id="59c17-374">Copie as cadeias de conexão exibidas para um arquivo local.</span><span class="sxs-lookup"><span data-stu-id="59c17-374">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="59c17-375">Você usará essas cadeias de caracteres para se conectar ao serviço do aplicativo Web e carregar arquivos via FTP.</span><span class="sxs-lookup"><span data-stu-id="59c17-375">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="59c17-376">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="59c17-376">For example:</span></span>

   ![Copiar cadeias de conexão do painel de FTP](../media/dke-ftp-dashboard.png)

3. <span data-ttu-id="59c17-378">Na base de código do armazenamento principal, vá para o **diretório Customer-Key-store\src\customer-Key-Store**</span><span class="sxs-lookup"><span data-stu-id="59c17-378">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

4. <span data-ttu-id="59c17-379">Verifique se esse diretório contém o arquivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="59c17-379">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

5. <span data-ttu-id="59c17-380">Executar: **publicação de dotnet**</span><span class="sxs-lookup"><span data-stu-id="59c17-380">Run: **dotnet publish**</span></span>

    <span data-ttu-id="59c17-381">A saída contém o diretório onde a publicação foi implantada.</span><span class="sxs-lookup"><span data-stu-id="59c17-381">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="59c17-382">Por exemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="59c17-382">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

6. <span data-ttu-id="59c17-383">Envie todos os arquivos no diretório de publicação para um arquivo zip.</span><span class="sxs-lookup"><span data-stu-id="59c17-383">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="59c17-384">Ao criar o arquivo. zip, verifique se todos os arquivos no diretório estão no nível raiz do arquivo. zip.</span><span class="sxs-lookup"><span data-stu-id="59c17-384">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

7. <span data-ttu-id="59c17-385">No cliente FTP, use as informações de conexão que você copiou para se conectar ao serviço de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59c17-385">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="59c17-386">Carregue o arquivo. zip que você criou na etapa anterior para o diretório raiz do seu aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="59c17-386">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="59c17-387">DKE é implantado e você pode navegar para as teclas de teste que você criou.</span><span class="sxs-lookup"><span data-stu-id="59c17-387">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="59c17-388">Em seguida, [valide sua implantação](#validate-your-deployment).</span><span class="sxs-lookup"><span data-stu-id="59c17-388">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="59c17-389">Validar sua implantação</span><span class="sxs-lookup"><span data-stu-id="59c17-389">Validate your deployment</span></span>

<span data-ttu-id="59c17-390">Depois de implantar o DKE usando um dos métodos descritos acima, valide a implantação e as configurações do armazenamento de chaves.</span><span class="sxs-lookup"><span data-stu-id="59c17-390">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="59c17-391">Sejam</span><span class="sxs-lookup"><span data-stu-id="59c17-391">Run:</span></span>

<span data-ttu-id="59c17-392">src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/MyKey</span><span class="sxs-lookup"><span data-stu-id="59c17-392">src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey</span></span>

<span data-ttu-id="59c17-393">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="59c17-393">For example:</span></span>

<span data-ttu-id="59c17-394">key_store_tester.ps1 https://mydkeservice.com/mykey</span><span class="sxs-lookup"><span data-stu-id="59c17-394">key_store_tester.ps1 https://mydkeservice.com/mykey</span></span>

<span data-ttu-id="59c17-395">Certifique-se de que nenhum erro apareça na saída.</span><span class="sxs-lookup"><span data-stu-id="59c17-395">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="59c17-396">Quando estiver pronto, [Registre o repositório de chaves](#register-your-key-store).</span><span class="sxs-lookup"><span data-stu-id="59c17-396">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="59c17-397">Registrar seu repositório de chaves</span><span class="sxs-lookup"><span data-stu-id="59c17-397">Register your key store</span></span>

<span data-ttu-id="59c17-398">As etapas a seguir permitem que você registre o serviço DKE.</span><span class="sxs-lookup"><span data-stu-id="59c17-398">The following steps enable you to register your DKE service.</span></span> <span data-ttu-id="59c17-399">O registro do seu serviço DKE é a última etapa na implantação do DKE antes que você possa começar a criar rótulos.</span><span class="sxs-lookup"><span data-stu-id="59c17-399">Registering your DKE service is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="59c17-400">Para registrar o serviço DKE:</span><span class="sxs-lookup"><span data-stu-id="59c17-400">To register the DKE service:</span></span>

1. <span data-ttu-id="59c17-401">No navegador, abra o [portal do Microsoft Azure](https://ms.portal.azure.com/)e vá para **todos os** \> registros de aplicativos de **identidade** de serviços \> **App Registrations**.</span><span class="sxs-lookup"><span data-stu-id="59c17-401">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="59c17-402">Selecione **novo registro**e insira um nome significativo.</span><span class="sxs-lookup"><span data-stu-id="59c17-402">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="59c17-403">Selecione um tipo de conta nas opções exibidas.</span><span class="sxs-lookup"><span data-stu-id="59c17-403">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="59c17-404">Se você estiver usando o Microsoft Azure com um domínio não personalizado, como **onmicrosoft.com**, selecione **contas nesse diretório organizacional apenas (somente para o Microsoft locatário).**</span><span class="sxs-lookup"><span data-stu-id="59c17-404">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="59c17-405">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="59c17-405">For example:</span></span>

   ![Novo registro de aplicativo](../media/dke-app-registration.png)

4. <span data-ttu-id="59c17-407">Na parte inferior da página, selecione **registrar** para criar o novo registro de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59c17-407">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="59c17-408">No novo registro de aplicativo, no painel esquerdo, em **gerenciar**, selecione **autenticação**.</span><span class="sxs-lookup"><span data-stu-id="59c17-408">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="59c17-409">Selecione **Adicionar uma plataforma**.</span><span class="sxs-lookup"><span data-stu-id="59c17-409">Select **Add a platform**.</span></span>

7. <span data-ttu-id="59c17-410">No pop-up **Configurar plataformas** , selecione **Web**.</span><span class="sxs-lookup"><span data-stu-id="59c17-410">On the **Configure platforms** popup, select **Web**.</span></span>

8. <span data-ttu-id="59c17-411">Em **URIs de redirecionamento**, insira o URI do serviço de criptografia de chave dupla.</span><span class="sxs-lookup"><span data-stu-id="59c17-411">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="59c17-412">Insira a URL do serviço de aplicativo, incluindo o nome do host e o domínio.</span><span class="sxs-lookup"><span data-stu-id="59c17-412">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="59c17-413">Por exemplo: https://mydkeservicetest.com</span><span class="sxs-lookup"><span data-stu-id="59c17-413">For example: https://mydkeservicetest.com</span></span>

    - <span data-ttu-id="59c17-414">A URL inserida deve corresponder ao nome de host onde o serviço DKE está implantado.</span><span class="sxs-lookup"><span data-stu-id="59c17-414">The URL you enter must match the hostname where your DKE service is deployed.</span></span>
    - <span data-ttu-id="59c17-415">Se você estiver testando localmente com o Visual Studio, use **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="59c17-415">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="59c17-416">Em todos os casos, o esquema deve ser **https**.</span><span class="sxs-lookup"><span data-stu-id="59c17-416">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="59c17-417">Verifique se o nome do host corresponde exatamente ao nome de host do serviço de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59c17-417">Ensure the hostname exactly matches your App Service hostname.</span></span> <span data-ttu-id="59c17-418">Você pode ter alterado para `localhost` solucionar problemas de compilação.</span><span class="sxs-lookup"><span data-stu-id="59c17-418">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="59c17-419">Em **appsettings.js**, esse valor é o nome de host definido para `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="59c17-419">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

9. <span data-ttu-id="59c17-420">Em **concessão implícita**, selecione a caixa de seleção **tokens de ID** .</span><span class="sxs-lookup"><span data-stu-id="59c17-420">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

10. <span data-ttu-id="59c17-421">Clique em **Salvar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="59c17-421">Select **Save** to save your changes.</span></span>

11. <span data-ttu-id="59c17-422">No painel esquerdo, selecione **expor uma API**e, em seguida, ao lado de URI da ID do aplicativo, selecione **definir**.</span><span class="sxs-lookup"><span data-stu-id="59c17-422">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

12. <span data-ttu-id="59c17-423">Ainda na página de **exibir uma API** , na área **escopos definidos por esta API** , selecione **Adicionar um escopo**.</span><span class="sxs-lookup"><span data-stu-id="59c17-423">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="59c17-424">No novo escopo:</span><span class="sxs-lookup"><span data-stu-id="59c17-424">In the new scope:</span></span>

    1. <span data-ttu-id="59c17-425">Defina o nome do escopo como **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="59c17-425">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="59c17-426">Selecione os administradores e usuários que podem autorizar.</span><span class="sxs-lookup"><span data-stu-id="59c17-426">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="59c17-427">Defina os valores restantes necessários.</span><span class="sxs-lookup"><span data-stu-id="59c17-427">Define any remaining values required.</span></span>

    4. <span data-ttu-id="59c17-428">Selecione **Adicionar escopo**.</span><span class="sxs-lookup"><span data-stu-id="59c17-428">Select **Add scope**.</span></span>

    5. <span data-ttu-id="59c17-429">Selecione **salvar** na parte superior para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="59c17-429">Select **Save** at the top to save your changes.</span></span>

13. <span data-ttu-id="59c17-430">Ainda na página **expor uma API** , na área **aplicativos cliente autorizados** , selecione **Adicionar um aplicativo cliente**.</span><span class="sxs-lookup"><span data-stu-id="59c17-430">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="59c17-431">No novo aplicativo cliente:</span><span class="sxs-lookup"><span data-stu-id="59c17-431">In the new client application:</span></span>

    1. <span data-ttu-id="59c17-432">Defina a ID do cliente como **d3590ed6-52B3-4102-AEFF-aad2292ab01c**.</span><span class="sxs-lookup"><span data-stu-id="59c17-432">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="59c17-433">Esse valor é a ID de cliente do Microsoft Office e permite que o Office obtenha um token de acesso para o armazenamento de chaves.</span><span class="sxs-lookup"><span data-stu-id="59c17-433">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="59c17-434">Em **escopos autorizados**, selecione o escopo de **user_impersonation** .</span><span class="sxs-lookup"><span data-stu-id="59c17-434">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="59c17-435">Selecione **Adicionar aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="59c17-435">Select **Add application**.</span></span>

    4. <span data-ttu-id="59c17-436">Selecione **salvar** na parte superior para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="59c17-436">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="59c17-437">Seu serviço do DKE agora está registrado.</span><span class="sxs-lookup"><span data-stu-id="59c17-437">Your DKE service is now registered.</span></span> <span data-ttu-id="59c17-438">Continue [criando rótulos usando o DKE](#create-sensitivity-labels-using-dke).</span><span class="sxs-lookup"><span data-stu-id="59c17-438">Continue by [creating labels using DKE](#create-sensitivity-labels-using-dke).</span></span>

## <a name="create-sensitivity-labels-using-dke"></a><span data-ttu-id="59c17-439">Criar rótulos de confidencialidade usando DKE</span><span class="sxs-lookup"><span data-stu-id="59c17-439">Create sensitivity labels using DKE</span></span>

<span data-ttu-id="59c17-440">No centro de conformidade da Microsoft 365, crie um novo rótulo de confidencialidade e aplique a criptografia como faria de outra forma.</span><span class="sxs-lookup"><span data-stu-id="59c17-440">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="59c17-441">Selecione **usar criptografia de chave dupla** e digite a URL do ponto de extremidade da sua chave.</span><span class="sxs-lookup"><span data-stu-id="59c17-441">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="59c17-442">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="59c17-442">For example:</span></span>

![Selecione usar criptografia de chave dupla no centro de conformidade do Microsoft 365](../media/dke-use-dke.png)

<span data-ttu-id="59c17-444">Quaisquer rótulos do DKE que você adicionar serão iniciados para os usuários nas versões mais recentes dos aplicativos do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="59c17-444">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="59c17-445">Pode levar até 24 horas para que os clientes sejam atualizados com os novos rótulos.</span><span class="sxs-lookup"><span data-stu-id="59c17-445">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="59c17-446">Habilitar o DKE no cliente</span><span class="sxs-lookup"><span data-stu-id="59c17-446">Enable DKE in your client</span></span>

<span data-ttu-id="59c17-447">Se você for um Office Insider, o DKE está habilitado para você.</span><span class="sxs-lookup"><span data-stu-id="59c17-447">If you're an Office Insider, DKE is enabled for you.</span></span> <span data-ttu-id="59c17-448">Caso contrário, habilite o DKE para o cliente adicionando as seguintes chaves do registro:</span><span class="sxs-lookup"><span data-stu-id="59c17-448">Otherwise, enable DKE for your client by adding the following registry keys:</span></span>

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a><span data-ttu-id="59c17-449">Migrar arquivos protegidos de rótulos do HYOK para rótulos do DKE</span><span class="sxs-lookup"><span data-stu-id="59c17-449">Migrate protected files from HYOK labels to DKE labels</span></span>

<span data-ttu-id="59c17-450">Se quiser, depois de concluir a configuração do DKE, você poderá migrar o conteúdo protegido por você usando os rótulos do HYOK para os rótulos do DKE.</span><span class="sxs-lookup"><span data-stu-id="59c17-450">If you want, once you're finished setting up DKE, you can migrate content that you've protected using HYOK labels to DKE labels.</span></span> <span data-ttu-id="59c17-451">Para migrar, você usará o verificador de AIP.</span><span class="sxs-lookup"><span data-stu-id="59c17-451">To migrate, you'll use the AIP scanner.</span></span> <span data-ttu-id="59c17-452">Para começar a usar o verificador, confira o [que é o verificador de rótulo unificado de proteção de informações do Azure?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner).</span><span class="sxs-lookup"><span data-stu-id="59c17-452">To get started using the scanner, see [What is the Azure Information Protection unified labeling scanner?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner).</span></span>

<span data-ttu-id="59c17-453">Se você não migrar conteúdo, seu conteúdo protegido do HYOK permanecerá inalterado.</span><span class="sxs-lookup"><span data-stu-id="59c17-453">If you don't migrate content, your HYOK protected content will remain unaffected.</span></span>
