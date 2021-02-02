---
title: Criptografia de Chave Dupla (DKE)
description: O DKE permite que você proteja dados altamente confidenciais enquanto mantém o controle total de sua chave.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 01/29/2021
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: c10a10a5922755db2c901137c3dff8acee5b8445
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066854"
---
# <a name="double-key-encryption-for-microsoft-365"></a><span data-ttu-id="c4a42-103">Criptografia de Chave Dupla para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c4a42-103">Double Key Encryption for Microsoft 365</span></span>

> <span data-ttu-id="c4a42-104">*Aplica-se a: Criptografia de Chave Dupla para Microsoft 365, Conformidade do [Microsoft 365,](https://www.microsoft.com/microsoft-365/business/compliance-management)Proteção de Informações do [Azure](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="c4a42-104">*Applies to: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="c4a42-105">*Instruções para: cliente [de rotulagem unificada da Proteção](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients) de Informações do Azure para Windows*</span><span class="sxs-lookup"><span data-stu-id="c4a42-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="c4a42-106">*Descrição do serviço para: [Conformidade do Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="c4a42-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="c4a42-107">A Criptografia de Chave Dupla (DKE) usa duas chaves juntas para acessar o conteúdo protegido.</span><span class="sxs-lookup"><span data-stu-id="c4a42-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="c4a42-108">A Microsoft armazena uma chave no Microsoft Azure e você mantém a outra chave.</span><span class="sxs-lookup"><span data-stu-id="c4a42-108">Microsoft stores one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="c4a42-109">Você mantém o controle total de uma de suas chaves usando o serviço de Criptografia de Chave Dupla.</span><span class="sxs-lookup"><span data-stu-id="c4a42-109">You maintain full control of one of your keys using the Double Key Encryption service.</span></span> <span data-ttu-id="c4a42-110">Você aplica proteção usando o cliente de rotulagem unificada da Proteção de Informações do Azure ao seu conteúdo altamente sensível.</span><span class="sxs-lookup"><span data-stu-id="c4a42-110">You apply protection using The Azure Information Protection unified labeling client to your highly sensitive content.</span></span>

<span data-ttu-id="c4a42-111">A Criptografia de Chave Dupla dá suporte a implantações na nuvem e locais.</span><span class="sxs-lookup"><span data-stu-id="c4a42-111">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="c4a42-112">Essas implantações ajudam a garantir que os dados criptografados permaneçam opacos onde quer que você armazene os dados protegidos.</span><span class="sxs-lookup"><span data-stu-id="c4a42-112">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="c4a42-113">Para obter mais informações sobre as chaves raiz de locatário padrão baseadas em nuvem, consulte Planejamento e implementação da chave de locatário da Proteção de Informações do [Azure.](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)</span><span class="sxs-lookup"><span data-stu-id="c4a42-113">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

## <a name="when-your-organization-should-adopt-dke"></a><span data-ttu-id="c4a42-114">Quando sua organização deve adotar dKE</span><span class="sxs-lookup"><span data-stu-id="c4a42-114">When your organization should adopt DKE</span></span>

<span data-ttu-id="c4a42-115">A Criptografia de Chave Dupla destina-se aos seus dados mais confidenciais sujeitos aos requisitos de proteção mais rígidos.</span><span class="sxs-lookup"><span data-stu-id="c4a42-115">Double Key Encryption is intended for your most sensitive data that is subject to the strictest protection requirements.</span></span> <span data-ttu-id="c4a42-116">O DKE não se destina a todos os dados.</span><span class="sxs-lookup"><span data-stu-id="c4a42-116">DKE is not intended for all data.</span></span> <span data-ttu-id="c4a42-117">Em geral, você estará usando a Criptografia de Chave Dupla para proteger apenas uma pequena parte de seus dados gerais.</span><span class="sxs-lookup"><span data-stu-id="c4a42-117">In general, you'll be using Double Key Encryption to protect only a small part of your overall data.</span></span> <span data-ttu-id="c4a42-118">Você deve fazer a devida auditoria na identificação dos dados corretos a abranger com essa solução antes de implantar.</span><span class="sxs-lookup"><span data-stu-id="c4a42-118">You should do due diligence in identifying the right data to cover with this solution before you deploy.</span></span> <span data-ttu-id="c4a42-119">Em alguns casos, talvez seja necessário restringir seu escopo e usar outras soluções para a maioria dos seus dados, como a Proteção de Informações da Microsoft com chaves gerenciadas pela Microsoft ou BYOK.</span><span class="sxs-lookup"><span data-stu-id="c4a42-119">In some cases, you might need to narrow your scope and make use of other solutions for most your data such as Microsoft Information Protection with Microsoft-managed keys or BYOK.</span></span> <span data-ttu-id="c4a42-120">Essas soluções são suficientes para documentos que não estão sujeitos a proteções e requisitos regulatórios aprimorados.</span><span class="sxs-lookup"><span data-stu-id="c4a42-120">These solutions are sufficient for documents that aren't subject to enhanced protections and regulatory requirements.</span></span> <span data-ttu-id="c4a42-121">Além disso, essas soluções permitem que você use os serviços mais poderosos do Office 365; serviços que você não pode usar com conteúdo criptografado DKE.</span><span class="sxs-lookup"><span data-stu-id="c4a42-121">Also, these solutions enable you to use the most powerful Office 365 services; services that you can't use with DKE encrypted content.</span></span> <span data-ttu-id="c4a42-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c4a42-122">For example:</span></span>

- <span data-ttu-id="c4a42-123">Regras de transporte, incluindo anti-malware e spam que exigem visibilidade do anexo</span><span class="sxs-lookup"><span data-stu-id="c4a42-123">Transport rules including anti-malware and spam that require visibility into the attachment</span></span>
- <span data-ttu-id="c4a42-124">Microsoft Delve</span><span class="sxs-lookup"><span data-stu-id="c4a42-124">Microsoft Delve</span></span>
- <span data-ttu-id="c4a42-125">Descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="c4a42-125">eDiscovery</span></span>
- <span data-ttu-id="c4a42-126">Pesquisa e indexação de conteúdo</span><span class="sxs-lookup"><span data-stu-id="c4a42-126">Content search and indexing</span></span>
- <span data-ttu-id="c4a42-127">Office Web Apps incluindo a funcionalidade de coautoria</span><span class="sxs-lookup"><span data-stu-id="c4a42-127">Office Web Apps including coauthoring functionality</span></span>

<span data-ttu-id="c4a42-128">Quaisquer aplicativos ou serviços externos que não estão integrados ao DKE por meio do SDK MIP não poderão executar ações nos dados criptografados.</span><span class="sxs-lookup"><span data-stu-id="c4a42-128">Any external applications or services that are not integrated with DKE through the MIP SDK will be unable to perform actions on the encrypted data.</span></span>

<span data-ttu-id="c4a42-129">O SDK 1.7+ da Proteção de Informações da Microsoft dá suporte à Criptografia de Chave Dupla; os aplicativos que se integram ao nosso SDK serão capazes de levar em conta esses dados com permissões e integrações suficientes no local.</span><span class="sxs-lookup"><span data-stu-id="c4a42-129">The Microsoft Information Protection SDK 1.7+ supports Double Key Encryption; applications that integrate with our SDK will be able to reason over this data with sufficient permissions and integrations in place.</span></span>

<span data-ttu-id="c4a42-130">Recomendamos que as organizações usem os recursos de proteção de informações da Microsoft (classificação e rotulagem) para proteger a maioria de seus dados confidenciais e usar somente o DKE para seus dados críticos.</span><span class="sxs-lookup"><span data-stu-id="c4a42-130">We recommend organizations use Microsoft Information protection capabilities (classification and labeling) to protect most of their sensitive data and only use DKE for their mission-critical data.</span></span> <span data-ttu-id="c4a42-131">A Criptografia de Chave Dupla é relevante para dados confidenciais em setores altamente regulamentados, como serviços financeiros e assistência médica.</span><span class="sxs-lookup"><span data-stu-id="c4a42-131">Double Key Encryption is relevant for sensitive data in highly regulated industries such as Financial services and Healthcare.</span></span>

<span data-ttu-id="c4a42-132">Se suas organizações têm qualquer um dos seguintes requisitos, você pode usar o DKE para ajudar a proteger seu conteúdo:</span><span class="sxs-lookup"><span data-stu-id="c4a42-132">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="c4a42-133">Você deseja garantir que *somente você* possa descriptografar o conteúdo protegido, sob todas as circunstâncias.</span><span class="sxs-lookup"><span data-stu-id="c4a42-133">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="c4a42-134">Você não quer que a Microsoft tenha acesso a dados protegidos por conta própria.</span><span class="sxs-lookup"><span data-stu-id="c4a42-134">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="c4a42-135">Você tem requisitos regulatórios para manter chaves dentro de um limite geográfico.</span><span class="sxs-lookup"><span data-stu-id="c4a42-135">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="c4a42-136">Todas as chaves mantidas para criptografia e descriptografia de dados são mantidas em seu data center.</span><span class="sxs-lookup"><span data-stu-id="c4a42-136">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="c4a42-137">Requisitos de sistema e licenciamento para DKE</span><span class="sxs-lookup"><span data-stu-id="c4a42-137">System and licensing requirements for DKE</span></span>

<span data-ttu-id="c4a42-138">**A Criptografia de Chave Dupla do Microsoft 365** vem com o Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c4a42-138">**Double Key Encryption for Microsoft 365** comes with Microsoft 365 E5.</span></span> <span data-ttu-id="c4a42-139">Se você não tiver uma licença do Microsoft 365 E5, inscreva-se para uma [avaliação.](https://aka.ms/M365E5ComplianceTrial)</span><span class="sxs-lookup"><span data-stu-id="c4a42-139">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="c4a42-140">Para saber mais sobre essas licenças, confira as diretrizes de licenciamento do [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)para segurança e & conformidade.</span><span class="sxs-lookup"><span data-stu-id="c4a42-140">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="c4a42-141">**Proteção de Informações do Azure.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-141">**Azure Information Protection**.</span></span> <span data-ttu-id="c4a42-142">O DKE funciona com rótulos de sensibilidade e requer a Proteção de Informações do Azure.</span><span class="sxs-lookup"><span data-stu-id="c4a42-142">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

<span data-ttu-id="c4a42-143">Os rótulos de sensibilidade DKE são disponibilizados para os usuários finais por meio da faixa de opções de sensibilidade nos Aplicativos da Área de Trabalho do Office.</span><span class="sxs-lookup"><span data-stu-id="c4a42-143">DKE sensitivity labels are made available to end users through the sensitivity ribbon in Office Desktop Apps.</span></span> <span data-ttu-id="c4a42-144">Instale esses pré-requisitos em cada computador cliente onde você deseja proteger e consumir documentos protegidos.</span><span class="sxs-lookup"><span data-stu-id="c4a42-144">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="c4a42-145">**Microsoft Office Apps para empresas** versão \*.12711 ou posterior (versões da área de trabalho do Word, PowerPoint e Excel) no Windows.</span><span class="sxs-lookup"><span data-stu-id="c4a42-145">**Microsoft Office Apps for enterprise** version \*.12711 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

<span data-ttu-id="c4a42-146">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span><span class="sxs-lookup"><span data-stu-id="c4a42-146">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="c4a42-147">Baixe e instale o cliente de Rotulagem Unificada no centro [de download da Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="c4a42-147">Download and install the Unified Labeling client from the [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="c4a42-148">Ambientes com suporte para armazenar e exibir conteúdo protegido por DKE</span><span class="sxs-lookup"><span data-stu-id="c4a42-148">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="c4a42-149">**Aplicativos com suporte.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-149">**Supported applications**.</span></span> <span data-ttu-id="c4a42-150">[Aplicativos do Microsoft 365 para clientes](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) corporativos no Windows, incluindo Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="c4a42-150">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="c4a42-151">**Suporte a conteúdo online.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-151">**Online content support**.</span></span> <span data-ttu-id="c4a42-152">Documentos e arquivos armazenados online no Microsoft SharePoint e no OneDrive for Business são suportados.</span><span class="sxs-lookup"><span data-stu-id="c4a42-152">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="c4a42-153">Você pode compartilhar conteúdo criptografado por email, mas não pode exibir documentos e arquivos criptografados online.</span><span class="sxs-lookup"><span data-stu-id="c4a42-153">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="c4a42-154">Em vez disso, você deve exibir o conteúdo protegido usando os aplicativos da área de trabalho no computador local.</span><span class="sxs-lookup"><span data-stu-id="c4a42-154">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="overview-of-deploying-dke"></a><span data-ttu-id="c4a42-155">Visão geral da implantação do DKE</span><span class="sxs-lookup"><span data-stu-id="c4a42-155">Overview of deploying DKE</span></span>

<span data-ttu-id="c4a42-156">Você seguirá estas etapas gerais para configurar o DKE.</span><span class="sxs-lookup"><span data-stu-id="c4a42-156">You'll follow these general steps to set up DKE.</span></span> <span data-ttu-id="c4a42-157">Depois de concluir essas etapas, os usuários finais poderão proteger seus dados altamente confidenciais com a Criptografia de Chave Dupla.</span><span class="sxs-lookup"><span data-stu-id="c4a42-157">Once you've completed these steps, your end users will can protect your highly sensitive data with Double Key Encryption.</span></span>

1. <span data-ttu-id="c4a42-158">Implante o serviço DKE conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c4a42-158">Deploy the DKE service as described in this article.</span></span>

2. <span data-ttu-id="c4a42-159">Crie um rótulo com Criptografia de Chave Dupla.</span><span class="sxs-lookup"><span data-stu-id="c4a42-159">Create a label with Double Key Encryption.</span></span> <span data-ttu-id="c4a42-160">Navegue até Proteção de Informações no centro [de conformidade do Microsoft 365](https://compliance.microsoft.com) e crie um novo rótulo com Criptografia de Chave Dupla.</span><span class="sxs-lookup"><span data-stu-id="c4a42-160">Navigate to Information protection under the [Microsoft 365 compliance center](https://compliance.microsoft.com) and create a new label with Double Key Encryption.</span></span> <span data-ttu-id="c4a42-161">Confira [Restringir o acesso ao conteúdo usando rótulos de sensibilidade para aplicar criptografia.](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)</span><span class="sxs-lookup"><span data-stu-id="c4a42-161">See [Restrict access to content by using sensitivity labels to apply encryption](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels).</span></span>

3. <span data-ttu-id="c4a42-162">Use rótulos de Criptografia de Chave Dupla.</span><span class="sxs-lookup"><span data-stu-id="c4a42-162">Use Double Key Encryption labels.</span></span> <span data-ttu-id="c4a42-163">Proteja os dados selecionando o rótulo de Chave Dupla Criptografada na faixa de opções Sensibilidade do Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="c4a42-163">Protect data by selecting the Double Key Encrypted label from the Sensitivity ribbon in Microsoft Office.</span></span>

<span data-ttu-id="c4a42-164">Há várias maneiras de concluir algumas das etapas para implantar a Criptografia de Chave Dupla.</span><span class="sxs-lookup"><span data-stu-id="c4a42-164">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="c4a42-165">Este artigo fornece instruções detalhadas para que administradores menos experientes implantem o serviço com êxito.</span><span class="sxs-lookup"><span data-stu-id="c4a42-165">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="c4a42-166">Se você estiver confortável em fazer isso, pode optar por usar seus próprios métodos.</span><span class="sxs-lookup"><span data-stu-id="c4a42-166">If you're comfortable doing so, you can choose to use your own methods.</span></span>

## <a name="deploy-dke"></a><span data-ttu-id="c4a42-167">Implantar DKE</span><span class="sxs-lookup"><span data-stu-id="c4a42-167">Deploy DKE</span></span>

<span data-ttu-id="c4a42-168">Este artigo e o vídeo de implantação usam o Azure como o destino de implantação para o serviço DKE.</span><span class="sxs-lookup"><span data-stu-id="c4a42-168">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="c4a42-169">Se estiver implantando em outro local, você precisará fornecer seus próprios valores.</span><span class="sxs-lookup"><span data-stu-id="c4a42-169">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="c4a42-170">Assista ao [vídeo de implantação](https://youtu.be/vDWfHN_kygg) da Criptografia de Chave Dupla para ver uma visão geral passo a passo dos conceitos deste artigo.</span><span class="sxs-lookup"><span data-stu-id="c4a42-170">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see a step-by-step overview of the concepts in this article.</span></span> <span data-ttu-id="c4a42-171">O vídeo leva cerca de 18 minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="c4a42-171">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="c4a42-172">Você seguirá estas etapas gerais para configurar a Criptografia de Chave Dupla para sua organização.</span><span class="sxs-lookup"><span data-stu-id="c4a42-172">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="c4a42-173">Instalar pré-requisitos de software para o serviço DKE</span><span class="sxs-lookup"><span data-stu-id="c4a42-173">Install software prerequisites for the DKE service</span></span>](#install-software-prerequisites-for-the-dke-service)
1. [<span data-ttu-id="c4a42-174">Clonar o repositório gitHub de criptografia de chave dupla</span><span class="sxs-lookup"><span data-stu-id="c4a42-174">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="c4a42-175">Modificar configurações do aplicativo</span><span class="sxs-lookup"><span data-stu-id="c4a42-175">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="c4a42-176">Gerar chaves de teste</span><span class="sxs-lookup"><span data-stu-id="c4a42-176">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="c4a42-177">Criar o projeto</span><span class="sxs-lookup"><span data-stu-id="c4a42-177">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="c4a42-178">Implantar o serviço DKE e publicar o armazenamento de chaves</span><span class="sxs-lookup"><span data-stu-id="c4a42-178">Deploy the DKE service and publish the key store</span></span>](#deploy-the-dke-service-and-publish-the-key-store)
1. [<span data-ttu-id="c4a42-179">Validar sua implantação</span><span class="sxs-lookup"><span data-stu-id="c4a42-179">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="c4a42-180">Registrar seu armazenamento de chaves</span><span class="sxs-lookup"><span data-stu-id="c4a42-180">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="c4a42-181">Criar rótulos de sensibilidade usando DKE</span><span class="sxs-lookup"><span data-stu-id="c4a42-181">Create sensitivity labels using DKE</span></span>](#create-sensitivity-labels-using-dke)
1. [<span data-ttu-id="c4a42-182">Habilitar dKE em seu cliente</span><span class="sxs-lookup"><span data-stu-id="c4a42-182">Enable DKE in your client</span></span>](#enable-dke-in-your-client)
1. [<span data-ttu-id="c4a42-183">Migrar arquivos protegidos de rótulos HYOK para rótulos DKE</span><span class="sxs-lookup"><span data-stu-id="c4a42-183">Migrate protected files from HYOK labels to DKE labels</span></span>](#migrate-protected-files-from-hyok-labels-to-dke-labels)

<span data-ttu-id="c4a42-184">Quando terminar, você poderá criptografar documentos e arquivos usando ODKE.</span><span class="sxs-lookup"><span data-stu-id="c4a42-184">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="c4a42-185">Para saber mais, confira [Aplicar rótulos de sensibilidade aos seus arquivos e emails no Office.](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)</span><span class="sxs-lookup"><span data-stu-id="c4a42-185">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites-for-the-dke-service"></a><span data-ttu-id="c4a42-186">Instalar pré-requisitos de software para o serviço DKE</span><span class="sxs-lookup"><span data-stu-id="c4a42-186">Install software prerequisites for the DKE service</span></span>

<span data-ttu-id="c4a42-187">Instale esses pré-requisitos no computador em que você deseja instalar o serviço DKE.</span><span class="sxs-lookup"><span data-stu-id="c4a42-187">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="c4a42-188">**.NET Core 3.1 SDK**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-188">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="c4a42-189">Baixe e instale o SDK do [Download .NET Core 3.1.](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="c4a42-189">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="c4a42-190">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-190">**Visual Studio Code**.</span></span> <span data-ttu-id="c4a42-191">Baixe o Visual Studio Code de [https://code.visualstudio.com/](https://code.visualstudio.com) .</span><span class="sxs-lookup"><span data-stu-id="c4a42-191">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="c4a42-192">Depois de instalado, execute o Visual Studio Code e selecione **Exibir** \> **Extensões.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-192">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="c4a42-193">Instale essas extensões.</span><span class="sxs-lookup"><span data-stu-id="c4a42-193">Install these extensions.</span></span>

- <span data-ttu-id="c4a42-194">C# para Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c4a42-194">C# for Visual Studio Code</span></span>

- <span data-ttu-id="c4a42-195">NuGet Package Manager</span><span class="sxs-lookup"><span data-stu-id="c4a42-195">NuGet Package Manager</span></span>

<span data-ttu-id="c4a42-196">**Recursos do Git.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-196">**Git resources**.</span></span> <span data-ttu-id="c4a42-197">Baixe e instale um dos seguintes.</span><span class="sxs-lookup"><span data-stu-id="c4a42-197">Download and install one of the following.</span></span>

- [<span data-ttu-id="c4a42-198">Git</span><span class="sxs-lookup"><span data-stu-id="c4a42-198">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="c4a42-199">GitHub Desktop</span><span class="sxs-lookup"><span data-stu-id="c4a42-199">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="c4a42-200">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="c4a42-200">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="c4a42-201">**OpenSSL** Você deve ter [o OpenSSL instalado](https://slproweb.com/products/Win32OpenSSL.html) para [gerar chaves de teste depois](#generate-test-keys) de implantar o DKE.</span><span class="sxs-lookup"><span data-stu-id="c4a42-201">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="c4a42-202">Certifique-se de invocá-la corretamente no caminho das variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="c4a42-202">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="c4a42-203">Por exemplo, consulte "Adicionar o diretório de instalação ao PATH" [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="c4a42-203">For example, see "Add the installation directory to PATH" at [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) for details.</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="c4a42-204">Clonar o repositório DKE do GitHub</span><span class="sxs-lookup"><span data-stu-id="c4a42-204">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="c4a42-205">A Microsoft fornece os arquivos de origem DKE em um repositório do GitHub.</span><span class="sxs-lookup"><span data-stu-id="c4a42-205">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="c4a42-206">Clone o repositório para criar o projeto localmente para uso da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c4a42-206">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="c4a42-207">O repositório GitHub DKE está localizado em [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="c4a42-207">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="c4a42-208">As instruções a seguir destinam-se a usuários não qualificados do Git ou do Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="c4a42-208">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="c4a42-209">No navegador, vá para: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="c4a42-209">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

2. <span data-ttu-id="c4a42-210">No lado direito da tela, selecione **Código.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-210">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="c4a42-211">Sua versão da interface do usuário pode mostrar um **clone ou botão de download.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-211">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="c4a42-212">Em seguida, no menu suspenso exibido, selecione o ícone de cópia para copiar a URL para sua área de transferência.</span><span class="sxs-lookup"><span data-stu-id="c4a42-212">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="c4a42-213">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c4a42-213">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c4a42-214">![Clonar o repositório do serviço de Criptografia de Chave Dupla do GitHub](../media/dke-clone.png)</span><span class="sxs-lookup"><span data-stu-id="c4a42-214">![Clone the Double Key Encryption service repository from GitHub](../media/dke-clone.png)</span></span>

3. <span data-ttu-id="c4a42-215">No Visual Studio Code, selecione **Exibir** \> **Paleta de Comandos** e selecione **Git: Clone**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-215">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="c4a42-216">Para ir para a opção na lista, comece a digitar para filtrar as entradas e, em seguida, `git: clone` selecione-a no drop-down.</span><span class="sxs-lookup"><span data-stu-id="c4a42-216">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="c4a42-217">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c4a42-217">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c4a42-218">![Opção GIT:Clone do Visual Studio Code](../media/dke-vscode-clone.png)</span><span class="sxs-lookup"><span data-stu-id="c4a42-218">![Visual Studio Code GIT:Clone option](../media/dke-vscode-clone.png)</span></span>

4. <span data-ttu-id="c4a42-219">Na caixa de texto, copie a URL que você copiou do Git e selecione **Clone no GitHub.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-219">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="c4a42-220">Na caixa **de diálogo Selecionar** Pasta exibida, procure e selecione um local para armazenar o repositório.</span><span class="sxs-lookup"><span data-stu-id="c4a42-220">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="c4a42-221">No prompt, selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-221">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="c4a42-222">O repositório é aberto no Visual Studio Code e exibe a ramificação atual do Git no canto inferior esquerdo.</span><span class="sxs-lookup"><span data-stu-id="c4a42-222">The repository opens in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="c4a42-223">Por exemplo, a ramificação deve ser **principal.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-223">For example,  The branch should be **main**.</span></span> <span data-ttu-id="c4a42-224">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c4a42-224">For example:</span></span>

   ![Captura de tela do repo DKE no Visual Studio Code exibindo a ramificação principal](../media/dke-vscode-main-branch.jpg)

6. <span data-ttu-id="c4a42-226">Se você não estiver no branch principal, será necessário selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="c4a42-226">If you're not on the main branch, you'll need to select it.</span></span> <span data-ttu-id="c4a42-227">No Visual Studio Code, selecione a ramificação e escolha **principal** na lista de ramificações exibida.</span><span class="sxs-lookup"><span data-stu-id="c4a42-227">In Visual Studio Code, select the branch and choose **main** from the list of branches that displays.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="c4a42-228">Selecionar a ramificação principal garante que você tenha os arquivos corretos para criar o projeto.</span><span class="sxs-lookup"><span data-stu-id="c4a42-228">Selecting the main branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="c4a42-229">Se você não escolher a ramificação correta, sua implantação falhará.</span><span class="sxs-lookup"><span data-stu-id="c4a42-229">If you don't choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="c4a42-230">Agora você tem seu repositório de origem DKE definido localmente.</span><span class="sxs-lookup"><span data-stu-id="c4a42-230">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="c4a42-231">Em seguida, [modifique as configurações do](#modify-application-settings) aplicativo para sua organização.</span><span class="sxs-lookup"><span data-stu-id="c4a42-231">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="c4a42-232">Modificar configurações do aplicativo</span><span class="sxs-lookup"><span data-stu-id="c4a42-232">Modify application settings</span></span>

<span data-ttu-id="c4a42-233">Para implantar o serviço DKE, você deve modificar os seguintes tipos de configurações de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="c4a42-233">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="c4a42-234">Configurações de acesso de teclas</span><span class="sxs-lookup"><span data-stu-id="c4a42-234">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="c4a42-235">Configurações de locatário e chave</span><span class="sxs-lookup"><span data-stu-id="c4a42-235">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="c4a42-236">Modifique as configurações do aplicativo appsettings.jsarquivo on.</span><span class="sxs-lookup"><span data-stu-id="c4a42-236">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="c4a42-237">Esse arquivo está localizado no repo DoubleKeyEncryptionService clonado localmente em DoubleKeyEncryptionService\src\customer-key-store.</span><span class="sxs-lookup"><span data-stu-id="c4a42-237">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="c4a42-238">Por exemplo, no Visual Studio Code, você pode navegar até o arquivo conforme mostrado na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="c4a42-238">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![Localizar o appsettings.jsarquivo on para DKE.](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="c4a42-240">Configurações de acesso de teclas</span><span class="sxs-lookup"><span data-stu-id="c4a42-240">Key access settings</span></span>

<span data-ttu-id="c4a42-241">Escolha se quer usar a autorização de email ou função.</span><span class="sxs-lookup"><span data-stu-id="c4a42-241">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="c4a42-242">O DKE dá suporte a apenas um desses métodos de autenticação de cada vez.</span><span class="sxs-lookup"><span data-stu-id="c4a42-242">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="c4a42-243">**Autorização de email.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-243">**Email authorization**.</span></span> <span data-ttu-id="c4a42-244">Permite que sua organização autorize o acesso a chaves somente com base em endereços de email.</span><span class="sxs-lookup"><span data-stu-id="c4a42-244">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="c4a42-245">**Autorização de função**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-245">**Role authorization**.</span></span> <span data-ttu-id="c4a42-246">Permite que sua organização autorize o acesso a chaves com base em grupos do Active Directory e exige que o serviço Web possa consultar o LDAP.</span><span class="sxs-lookup"><span data-stu-id="c4a42-246">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="c4a42-247">**Para definir as configurações de acesso de chave para DKE usando autorização de email**</span><span class="sxs-lookup"><span data-stu-id="c4a42-247">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="c4a42-248">Abra o **appsettings.jsno arquivo** e localize a `AuthorizedEmailAddress` configuração.</span><span class="sxs-lookup"><span data-stu-id="c4a42-248">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="c4a42-249">Adicione o endereço de email ou endereços que você deseja autorizar.</span><span class="sxs-lookup"><span data-stu-id="c4a42-249">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="c4a42-250">Separe vários endereços de email com aspas duplas e vírgulas.</span><span class="sxs-lookup"><span data-stu-id="c4a42-250">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="c4a42-251">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c4a42-251">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="c4a42-252">Localize `LDAPPath` a configuração e remova o texto `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` entre aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="c4a42-252">Locate the `LDAPPath` setting and remove the text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` between the double quotes.</span></span> <span data-ttu-id="c4a42-253">Deixe as aspas duplas no lugar.</span><span class="sxs-lookup"><span data-stu-id="c4a42-253">Leave the double quotes in place.</span></span> <span data-ttu-id="c4a42-254">Quando você terminar, a configuração deve ter esta aparência.</span><span class="sxs-lookup"><span data-stu-id="c4a42-254">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="c4a42-255">Localize `AuthorizedRoles` a configuração e exclua a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="c4a42-255">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="c4a42-256">Esta imagem mostra o **appsettings.jsarquivo corretamente** formatado para autorização de email.</span><span class="sxs-lookup"><span data-stu-id="c4a42-256">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![O appsettings.json mostrando o método de autorização de email](../media/dke-email-accesssetting.png)

<span data-ttu-id="c4a42-258">**Para definir as configurações de acesso de teclas para DKE usando a autorização de função**</span><span class="sxs-lookup"><span data-stu-id="c4a42-258">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="c4a42-259">Abra o **appsettings.jsno arquivo** e localize a `AuthorizedRoles` configuração.</span><span class="sxs-lookup"><span data-stu-id="c4a42-259">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="c4a42-260">Adicione os nomes de grupo do Active Directory que você deseja autorizar.</span><span class="sxs-lookup"><span data-stu-id="c4a42-260">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="c4a42-261">Separe vários nomes de grupo com aspas duplas e vírgulas.</span><span class="sxs-lookup"><span data-stu-id="c4a42-261">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="c4a42-262">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c4a42-262">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="c4a42-263">Localize `LDAPPath` a configuração e adicione o domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c4a42-263">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="c4a42-264">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c4a42-264">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="c4a42-265">Localize `AuthorizedEmailAddress` a configuração e exclua a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="c4a42-265">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="c4a42-266">Esta imagem mostra o **appsettings.jsno arquivo** formatado corretamente para autorização de função.</span><span class="sxs-lookup"><span data-stu-id="c4a42-266">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![appsettings.jsarquivo mostrando o método de autorização de função](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="c4a42-268">Configurações de locatário e chave</span><span class="sxs-lookup"><span data-stu-id="c4a42-268">Tenant and key settings</span></span>

<span data-ttu-id="c4a42-269">As configurações de locatário e chave do DKE estão localizadas **appsettings.jsarquivo** on.</span><span class="sxs-lookup"><span data-stu-id="c4a42-269">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="c4a42-270">**Para definir configurações de locatário e chave para DKE**</span><span class="sxs-lookup"><span data-stu-id="c4a42-270">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="c4a42-271">Abra o **appsettings.jsno** arquivo.</span><span class="sxs-lookup"><span data-stu-id="c4a42-271">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="c4a42-272">Localize a `ValidIssuers` configuração e substitua `<tenantid>` pela ID de locatário.</span><span class="sxs-lookup"><span data-stu-id="c4a42-272">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="c4a42-273">Você pode localizar sua ID de locatário indo para o portal do Azure e exibindo as propriedades [de locatário.](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)</span><span class="sxs-lookup"><span data-stu-id="c4a42-273">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="c4a42-274">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c4a42-274">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="c4a42-275">Localize o `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="c4a42-275">Locate the `JwtAudience`.</span></span> <span data-ttu-id="c4a42-276">Substitua `<yourhostname>` pelo nome de host do computador onde o serviço DKE será executado.</span><span class="sxs-lookup"><span data-stu-id="c4a42-276">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="c4a42-277">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c4a42-277">For example:</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="c4a42-278">O valor para `JwtAudience` deve corresponder exatamente ao nome do seu host.</span><span class="sxs-lookup"><span data-stu-id="c4a42-278">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="c4a42-279">Você pode usar **localhost:5001** durante a depuração.</span><span class="sxs-lookup"><span data-stu-id="c4a42-279">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="c4a42-280">No entanto, quando terminar a depuração, certifique-se de atualizar esse valor para o nome de host do servidor.</span><span class="sxs-lookup"><span data-stu-id="c4a42-280">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="c4a42-281">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="c4a42-281">`TestKeys:Name`.</span></span> <span data-ttu-id="c4a42-282">Insira um nome para sua chave.</span><span class="sxs-lookup"><span data-stu-id="c4a42-282">Enter a name for your key.</span></span> <span data-ttu-id="c4a42-283">Por exemplo: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="c4a42-283">For example: `TestKey1`</span></span>
- <span data-ttu-id="c4a42-284">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="c4a42-284">`TestKeys:Id`.</span></span> <span data-ttu-id="c4a42-285">Crie um GUID e insira-o como o `TestKeys:ID` valor.</span><span class="sxs-lookup"><span data-stu-id="c4a42-285">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="c4a42-286">Por exemplo, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span><span class="sxs-lookup"><span data-stu-id="c4a42-286">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="c4a42-287">Você pode usar um site como [o Gerador de GUID Online](https://guidgenerator.com/) para gerar aleatoriamente um GUID.</span><span class="sxs-lookup"><span data-stu-id="c4a42-287">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="c4a42-288">Esta imagem mostra o formato correto para as configurações de locatário e chaves **appsettings.jsem**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-288">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="c4a42-289">`LDAPPath` está configurada para autorização de função.</span><span class="sxs-lookup"><span data-stu-id="c4a42-289">`LDAPPath` is configured for role authorization.</span></span>

![Mostra as configurações corretas de locatário e chave para DKE no appsettings.jsarquivo on.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="c4a42-291">Gerar chaves de teste</span><span class="sxs-lookup"><span data-stu-id="c4a42-291">Generate test keys</span></span>

<span data-ttu-id="c4a42-292">Depois de definir as configurações do aplicativo, você estará pronto para gerar chaves de teste públicas e privadas.</span><span class="sxs-lookup"><span data-stu-id="c4a42-292">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="c4a42-293">Para gerar chaves:</span><span class="sxs-lookup"><span data-stu-id="c4a42-293">To generate keys:</span></span>

1. <span data-ttu-id="c4a42-294">No menu Iniciar do Windows, execute o Prompt de Comando do OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="c4a42-294">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

2. <span data-ttu-id="c4a42-295">Altere para a pasta onde você deseja salvar as chaves de teste.</span><span class="sxs-lookup"><span data-stu-id="c4a42-295">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="c4a42-296">Os arquivos que você cria concluindo as etapas dessa tarefa são armazenados na mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="c4a42-296">The files you create by completing the steps in this task are stored in the same folder.</span></span>

3. <span data-ttu-id="c4a42-297">Gere a nova chave de teste.</span><span class="sxs-lookup"><span data-stu-id="c4a42-297">Generate the new test key.</span></span>

   ```console
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. <span data-ttu-id="c4a42-298">Gere a chave privada.</span><span class="sxs-lookup"><span data-stu-id="c4a42-298">Generate the private key.</span></span>

   ```console
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. <span data-ttu-id="c4a42-299">Gere a chave pública.</span><span class="sxs-lookup"><span data-stu-id="c4a42-299">Generate the public key.</span></span>

   ```console
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. <span data-ttu-id="c4a42-300">Em um editor de texto, **abra pubkeyonly.pem**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-300">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="c4a42-301">Copie todo o conteúdo no **arquivo pubkeyonly.pem,** exceto a primeira e a última linhas, na seção do arquivo `PublicPem`appsettings.js **on.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-301">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

7. <span data-ttu-id="c4a42-302">Em um editor de texto, **abra privkeynopass.pem**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-302">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="c4a42-303">Copie todo o conteúdo no arquivo **privkeynopass.pem,** exceto a primeira e a última linhas, na seção do arquivo `PrivatePem` **appsettings.json.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-303">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

8. <span data-ttu-id="c4a42-304">Remova todos os espaços em branco e linhas novas nas `PublicPem` `PrivatePem` seções e nas seções.</span><span class="sxs-lookup"><span data-stu-id="c4a42-304">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c4a42-305">Ao copiar esse conteúdo, não exclua nenhum dos dados PEM.</span><span class="sxs-lookup"><span data-stu-id="c4a42-305">When you copy this content, do not delete any of the PEM data.</span></span>

9. <span data-ttu-id="c4a42-306">No Visual Studio Code, navegue até o **Startup.cs** arquivo.</span><span class="sxs-lookup"><span data-stu-id="c4a42-306">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="c4a42-307">Esse arquivo está localizado no repo DoubleKeyEncryptionService clonado localmente em DoubleKeyEncryptionService\src\customer-key-store\.</span><span class="sxs-lookup"><span data-stu-id="c4a42-307">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

10. <span data-ttu-id="c4a42-308">Localize as seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="c4a42-308">Locate the following lines:</span></span>

    ```csharp
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
    ```

11. <span data-ttu-id="c4a42-309">Substitua essas linhas pelo seguinte texto:</span><span class="sxs-lookup"><span data-stu-id="c4a42-309">Replace these lines with the following text:</span></span>

    ```csharp
    services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
    ```

    <span data-ttu-id="c4a42-310">Os resultados finais devem ser semelhantes aos seguintes.</span><span class="sxs-lookup"><span data-stu-id="c4a42-310">The end results should look similar to the following.</span></span>

    ![startup.cs para visualização pública](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="c4a42-312">Agora você está pronto para [criar seu projeto DKE.](#build-the-project)</span><span class="sxs-lookup"><span data-stu-id="c4a42-312">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="c4a42-313">Compilar o projeto</span><span class="sxs-lookup"><span data-stu-id="c4a42-313">Build the project</span></span>

<span data-ttu-id="c4a42-314">Use as instruções a seguir para criar o projeto DKE localmente:</span><span class="sxs-lookup"><span data-stu-id="c4a42-314">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="c4a42-315">No Visual Studio Code, no repositório de serviço DKE, selecione **Exibir** Paleta de Comandos e \>  digite **build** no prompt.</span><span class="sxs-lookup"><span data-stu-id="c4a42-315">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

2. <span data-ttu-id="c4a42-316">Na lista, escolha **Tarefas: Executar tarefa de com build.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-316">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="c4a42-317">Se não houver nenhuma tarefa de com build encontrada, selecione Configurar Tarefa **de** Com build e crie uma para o .NET Core da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="c4a42-317">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![Configurar tarefa de com build ausente para .NET](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="c4a42-319">Escolha **Criar tasks.jsa partir do modelo.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-319">Choose **Create tasks.json from template**.</span></span>

      ![Criar tasks.jsno arquivo do modelo para DKE](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="c4a42-321">Na lista de tipos de modelo, selecione **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-321">From the list of template types, select **.NET Core**.</span></span>

      ![Selecione o modelo correto para DKE](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="c4a42-323">Na seção build, localize o caminho para o **arquivo customerkeystore.csproj.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-323">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="c4a42-324">Se não estiver lá, adicione a seguinte linha:</span><span class="sxs-lookup"><span data-stu-id="c4a42-324">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. <span data-ttu-id="c4a42-325">Execute a com build novamente.</span><span class="sxs-lookup"><span data-stu-id="c4a42-325">Run the build again.</span></span>

3. <span data-ttu-id="c4a42-326">Verifique se não há erros em vermelho na janela de saída.</span><span class="sxs-lookup"><span data-stu-id="c4a42-326">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="c4a42-327">Se houver erros em vermelho, verifique a saída do console.</span><span class="sxs-lookup"><span data-stu-id="c4a42-327">If there are red errors, check the console output.</span></span> <span data-ttu-id="c4a42-328">Verifique se você concluiu todas as etapas anteriores corretamente e se as versões de com build corretas estão presentes.</span><span class="sxs-lookup"><span data-stu-id="c4a42-328">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

4. <span data-ttu-id="c4a42-329">Selecione **Executar** \> **Iniciar Depuração** para depurar o processo.</span><span class="sxs-lookup"><span data-stu-id="c4a42-329">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="c4a42-330">Se você for solicitado a selecionar um ambiente, selecione **.NET core**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-330">If you're prompted to select an environment, select **.NET core**.</span></span>

   <span data-ttu-id="c4a42-331">O depurador de núcleo do .NET normalmente inicia para `https://localhost:5001` .</span><span class="sxs-lookup"><span data-stu-id="c4a42-331">The .NET core debugger typically launches to `https://localhost:5001`.</span></span> <span data-ttu-id="c4a42-332">Para exibir sua chave de teste, vá `https://localhost:5001` para e aende uma barra (/) e o nome da chave.</span><span class="sxs-lookup"><span data-stu-id="c4a42-332">To view your test key, go to `https://localhost:5001` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="c4a42-333">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c4a42-333">For example:</span></span>

   ```https
   https://localhost:5001/TestKey1
   ```

   <span data-ttu-id="c4a42-334">A chave deve ser exibida no formato JSON.</span><span class="sxs-lookup"><span data-stu-id="c4a42-334">The key should display in JSON format.</span></span>

<span data-ttu-id="c4a42-335">Sua configuração agora está concluída.</span><span class="sxs-lookup"><span data-stu-id="c4a42-335">Your setup is now complete.</span></span> <span data-ttu-id="c4a42-336">Antes de publicar o repositório de chaves, em appsettings.js, para a configuração JwtAudience, certifique-se de que o valor do nome do host corresponde exatamente ao nome do host do Serviço de Aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c4a42-336">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="c4a42-337">Você pode ter alterado para localhost para solucionar problemas de com build.</span><span class="sxs-lookup"><span data-stu-id="c4a42-337">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a><span data-ttu-id="c4a42-338">Implantar o serviço DKE e publicar o armazenamento de chaves</span><span class="sxs-lookup"><span data-stu-id="c4a42-338">Deploy the DKE service and publish the key store</span></span>

<span data-ttu-id="c4a42-339">Para implantações de produção, implante o serviço em uma nuvem de terceiros ou [publique em um sistema local.](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli)</span><span class="sxs-lookup"><span data-stu-id="c4a42-339">For production deployments, deploy the service either in a third-party cloud or [publish to an on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli).</span></span>

<span data-ttu-id="c4a42-340">Você pode preferir outros métodos para implantar suas chaves.</span><span class="sxs-lookup"><span data-stu-id="c4a42-340">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="c4a42-341">Selecione o método que funciona melhor para sua organização.</span><span class="sxs-lookup"><span data-stu-id="c4a42-341">Select the method that works best for your organization.</span></span>

<span data-ttu-id="c4a42-342">Para implantações piloto, você pode implantar no Azure e começar imediatamente.</span><span class="sxs-lookup"><span data-stu-id="c4a42-342">For pilot deployments, you can deploy in Azure and get started right away.</span></span>

<span data-ttu-id="c4a42-343">**Para criar uma instância do Azure Web App para hospedar sua implantação de DKE**</span><span class="sxs-lookup"><span data-stu-id="c4a42-343">**To create an Azure Web App instance to host your DKE deployment**</span></span>

<span data-ttu-id="c4a42-344">Para publicar o armazenamento de chaves, você criará uma instância do Serviço de Aplicativo do Azure para hospedar sua implantação de DKE.</span><span class="sxs-lookup"><span data-stu-id="c4a42-344">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="c4a42-345">Em seguida, você publicará suas chaves geradas no Azure.</span><span class="sxs-lookup"><span data-stu-id="c4a42-345">Next, you'll publish your generated keys to Azure.</span></span>

1. <span data-ttu-id="c4a42-346">No navegador, entre no [portal do Microsoft Azure e](https://ms.portal.azure.com)vá para Adicionar serviços **de**  >  **aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-346">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

2. <span data-ttu-id="c4a42-347">Selecione sua assinatura e grupo de recursos e defina seus detalhes de instância.</span><span class="sxs-lookup"><span data-stu-id="c4a42-347">Select your subscription and resource group and define your instance details.</span></span>

   - <span data-ttu-id="c4a42-348">Insira o nome do host do computador em que você deseja instalar o serviço DKE.</span><span class="sxs-lookup"><span data-stu-id="c4a42-348">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="c4a42-349">Certifique-se de que seja o mesmo nome definido para a configuração JwtAudience noappsettings.js [**no**](#tenant-and-key-settings) arquivo.</span><span class="sxs-lookup"><span data-stu-id="c4a42-349">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="c4a42-350">O valor que você fornece para o nome também é WebAppInstanceName.</span><span class="sxs-lookup"><span data-stu-id="c4a42-350">The value you provide for the name is also the WebAppInstanceName.</span></span>

   - <span data-ttu-id="c4a42-351">For **Publish**, select **code,** and for **Runtime stack**, select **.NET Core 3.1**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-351">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

   <span data-ttu-id="c4a42-352">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c4a42-352">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c4a42-353">![Adicionar seu Serviço de Aplicativo](../media/dke-azure-add-app-service.png)</span><span class="sxs-lookup"><span data-stu-id="c4a42-353">![Add your App Service](../media/dke-azure-add-app-service.png)</span></span>

3. <span data-ttu-id="c4a42-354">Na parte inferior da página, selecione **Revisar + criar** e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-354">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

4. <span data-ttu-id="c4a42-355">Faça um dos seguintes para publicar suas chaves geradas:</span><span class="sxs-lookup"><span data-stu-id="c4a42-355">Do one of the following to publish your generated keys:</span></span>

   - [<span data-ttu-id="c4a42-356">Publicar via ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="c4a42-356">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
   - [<span data-ttu-id="c4a42-357">Publicar via FTP</span><span class="sxs-lookup"><span data-stu-id="c4a42-357">Publish via FTP</span></span>](#publish-via-ftp)
   - [<span data-ttu-id="c4a42-358">Publicar por meio do Visual Studio 2019 ou posterior</span><span class="sxs-lookup"><span data-stu-id="c4a42-358">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="c4a42-359">Publicar via ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="c4a42-359">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="c4a42-360">Vá para `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span><span class="sxs-lookup"><span data-stu-id="c4a42-360">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

   <span data-ttu-id="c4a42-361">Por exemplo: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="c4a42-361">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

2. <span data-ttu-id="c4a42-362">Na base de código do repositório de chaves, vá para a pasta **customer-key-store\src\customer-key-store** e verifique se essa pasta contém o arquivo **customerkeystore.csproj.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-362">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

3. <span data-ttu-id="c4a42-363">Executar: **publicação de dotnet**</span><span class="sxs-lookup"><span data-stu-id="c4a42-363">Run: **dotnet publish**</span></span>

   <span data-ttu-id="c4a42-364">A janela de saída exibe o diretório onde a publicação foi implantada.</span><span class="sxs-lookup"><span data-stu-id="c4a42-364">The output window displays the directory where the publish was deployed.</span></span>

   <span data-ttu-id="c4a42-365">Por exemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="c4a42-365">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

4. <span data-ttu-id="c4a42-366">Envie todos os arquivos no diretório de publicação para um arquivo .zip.</span><span class="sxs-lookup"><span data-stu-id="c4a42-366">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="c4a42-367">Ao criar o arquivo .zip, certifique-se de que todos os arquivos no diretório estão no nível raiz do arquivo .zip.</span><span class="sxs-lookup"><span data-stu-id="c4a42-367">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

5. <span data-ttu-id="c4a42-368">Arraste e solte o arquivo .zip criado para o site ZipDeployUI aberto acima.</span><span class="sxs-lookup"><span data-stu-id="c4a42-368">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="c4a42-369">Por exemplo: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="c4a42-369">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="c4a42-370">O DKE é implantado e você pode navegar até as chaves de teste criadas.</span><span class="sxs-lookup"><span data-stu-id="c4a42-370">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="c4a42-371">Continue [validando sua implantação](#validate-your-deployment) abaixo.</span><span class="sxs-lookup"><span data-stu-id="c4a42-371">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="c4a42-372">Publicar via FTP</span><span class="sxs-lookup"><span data-stu-id="c4a42-372">Publish via FTP</span></span>

1. <span data-ttu-id="c4a42-373">Conecte-se ao Serviço de Aplicativo que você criou [acima.](#deploy-the-dke-service-and-publish-the-key-store)</span><span class="sxs-lookup"><span data-stu-id="c4a42-373">Connect to the App Service you created [above](#deploy-the-dke-service-and-publish-the-key-store).</span></span>

   <span data-ttu-id="c4a42-374">No navegador, vá para: Painel FTP de Implantação Manual do Centro de Implantação do Serviço de Aplicativo do portal do **Azure.**  >    >    >    >    >  </span><span class="sxs-lookup"><span data-stu-id="c4a42-374">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

2. <span data-ttu-id="c4a42-375">Copie as cadeias de conexão exibidas para um arquivo local.</span><span class="sxs-lookup"><span data-stu-id="c4a42-375">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="c4a42-376">Você usará essas cadeias de caracteres para se conectar ao Serviço de Aplicativo Web e carregar arquivos via FTP.</span><span class="sxs-lookup"><span data-stu-id="c4a42-376">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

   <span data-ttu-id="c4a42-377">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c4a42-377">For example:</span></span>

   ![Copiar cadeias de conexão do painel FTP](../media/dke-ftp-dashboard.png)

3. <span data-ttu-id="c4a42-379">Na base de código do armazenamento de chaves, vá para **o diretório customer-key-store\src\customer-key-store.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-379">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

4. <span data-ttu-id="c4a42-380">Verifique se esse diretório contém o **arquivo customerkeystore.csproj.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-380">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

5. <span data-ttu-id="c4a42-381">Executar: **publicação de dotnet**</span><span class="sxs-lookup"><span data-stu-id="c4a42-381">Run: **dotnet publish**</span></span>

   <span data-ttu-id="c4a42-382">A saída contém o diretório onde a publicação foi implantada.</span><span class="sxs-lookup"><span data-stu-id="c4a42-382">The output contains the directory where the publish was deployed.</span></span>

   <span data-ttu-id="c4a42-383">Por exemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="c4a42-383">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

6. <span data-ttu-id="c4a42-384">Envie todos os arquivos no diretório de publicação para um arquivo zip.</span><span class="sxs-lookup"><span data-stu-id="c4a42-384">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="c4a42-385">Ao criar o arquivo .zip, certifique-se de que todos os arquivos no diretório estão no nível raiz do arquivo .zip.</span><span class="sxs-lookup"><span data-stu-id="c4a42-385">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

7. <span data-ttu-id="c4a42-386">No cliente FTP, use as informações de conexão que você copiou para se conectar ao Serviço de Aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c4a42-386">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="c4a42-387">Carregue o arquivo .zip que você criou na etapa anterior para o diretório raiz do seu Web App.</span><span class="sxs-lookup"><span data-stu-id="c4a42-387">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="c4a42-388">O DKE é implantado e você pode navegar até as chaves de teste que criou.</span><span class="sxs-lookup"><span data-stu-id="c4a42-388">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="c4a42-389">Em seguida, [valide sua implantação.](#validate-your-deployment)</span><span class="sxs-lookup"><span data-stu-id="c4a42-389">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="c4a42-390">Validar sua implantação</span><span class="sxs-lookup"><span data-stu-id="c4a42-390">Validate your deployment</span></span>

<span data-ttu-id="c4a42-391">Depois de implantar o DKE usando um dos métodos descritos acima, valide a implantação e as configurações do armazenamento de chaves.</span><span class="sxs-lookup"><span data-stu-id="c4a42-391">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="c4a42-392">Execute:</span><span class="sxs-lookup"><span data-stu-id="c4a42-392">Run:</span></span>

```powershell
src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey
```

<span data-ttu-id="c4a42-393">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c4a42-393">For example:</span></span>

```powershell
key_store_tester.ps1 https://mydkeservice.com/mykey
```

<span data-ttu-id="c4a42-394">Certifique-se de que nenhum erro apareça na saída.</span><span class="sxs-lookup"><span data-stu-id="c4a42-394">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="c4a42-395">Quando você estiver pronto, [registre seu armazenamento de chaves.](#register-your-key-store)</span><span class="sxs-lookup"><span data-stu-id="c4a42-395">When you're ready, [register your key store](#register-your-key-store).</span></span>

<span data-ttu-id="c4a42-396">O nome da chave faz a resição entre as minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c4a42-396">The key name is case sensitive.</span></span> <span data-ttu-id="c4a42-397">Insira o nome da chave como ele aparece no appsettings.jsno arquivo.</span><span class="sxs-lookup"><span data-stu-id="c4a42-397">Enter the key name as it appears in the appsettings.json file.</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="c4a42-398">Registrar seu armazenamento de chaves</span><span class="sxs-lookup"><span data-stu-id="c4a42-398">Register your key store</span></span>

<span data-ttu-id="c4a42-399">As etapas a seguir permitem que você registre seu serviço DKE.</span><span class="sxs-lookup"><span data-stu-id="c4a42-399">The following steps enable you to register your DKE service.</span></span> <span data-ttu-id="c4a42-400">Registrar seu serviço DKE é a última etapa na implantação do DKE antes de começar a criar rótulos.</span><span class="sxs-lookup"><span data-stu-id="c4a42-400">Registering your DKE service is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="c4a42-401">Para registrar o serviço DKE:</span><span class="sxs-lookup"><span data-stu-id="c4a42-401">To register the DKE service:</span></span>

1. <span data-ttu-id="c4a42-402">No navegador, abra o [portal do Microsoft Azure e](https://ms.portal.azure.com/)vá para Todos os Registros de Aplicativo de  \> **Identidade** \> **de Serviços.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-402">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="c4a42-403">Selecione **Novo registro** e insira um nome significativo.</span><span class="sxs-lookup"><span data-stu-id="c4a42-403">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="c4a42-404">Selecione um tipo de conta nas opções exibidas.</span><span class="sxs-lookup"><span data-stu-id="c4a42-404">Select an account type from the options displayed.</span></span>

   <span data-ttu-id="c4a42-405">Se você estiver usando o Microsoft Azure com um domínio não personalizado, como o **onmicrosoft.com**, selecione Contas somente neste diretório organizacional **(somente Microsoft – locatário único).**</span><span class="sxs-lookup"><span data-stu-id="c4a42-405">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

   <span data-ttu-id="c4a42-406">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c4a42-406">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c4a42-407">![Novo Registro de Aplicativo](../media/dke-app-registration.png)</span><span class="sxs-lookup"><span data-stu-id="c4a42-407">![New App Registration](../media/dke-app-registration.png)</span></span>

4. <span data-ttu-id="c4a42-408">Na parte inferior da página, selecione **Registrar** para criar o novo Registro de Aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c4a42-408">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="c4a42-409">No novo Registro de Aplicativo, no painel esquerdo, em **Gerenciar,** selecione **Autenticação.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-409">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="c4a42-410">Selecione **Adicionar uma plataforma.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-410">Select **Add a platform**.</span></span>

7. <span data-ttu-id="c4a42-411">No **pop-up Configurar plataformas,** selecione **Web**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-411">On the **Configure platforms** popup, select **Web**.</span></span>

8. <span data-ttu-id="c4a42-412">Em **URIs de redirecionamento,** insira o URI do seu serviço de criptografia de chave dupla.</span><span class="sxs-lookup"><span data-stu-id="c4a42-412">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="c4a42-413">Insira a URL do Serviço de Aplicativo, incluindo o nome do host e o domínio.</span><span class="sxs-lookup"><span data-stu-id="c4a42-413">Enter the App Service URL, including both the hostname and domain.</span></span>

   <span data-ttu-id="c4a42-414">Por exemplo: https://mydkeservicetest.com</span><span class="sxs-lookup"><span data-stu-id="c4a42-414">For example: https://mydkeservicetest.com</span></span>

   - <span data-ttu-id="c4a42-415">A URL que você inserir deve corresponder ao nome do host onde seu serviço DKE está implantado.</span><span class="sxs-lookup"><span data-stu-id="c4a42-415">The URL you enter must match the hostname where your DKE service is deployed.</span></span>
   - <span data-ttu-id="c4a42-416">Se você estiver testando localmente com o Visual Studio, use **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="c4a42-416">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
   - <span data-ttu-id="c4a42-417">Em todos os casos, o esquema deve ser **https**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-417">In all cases, the scheme must be **https**.</span></span>

   <span data-ttu-id="c4a42-418">Verifique se o nome do host corresponde exatamente ao nome de host do Serviço de Aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c4a42-418">Ensure the hostname exactly matches your App Service hostname.</span></span> <span data-ttu-id="c4a42-419">Você pode ter alterado para solucionar `localhost` problemas de com build.</span><span class="sxs-lookup"><span data-stu-id="c4a42-419">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="c4a42-420">In **appsettings.json**, this value is the hostname you set for `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="c4a42-420">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

9. <span data-ttu-id="c4a42-421">Em **Concessão implícita,** marque a caixa de seleção de tokens de **ID.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-421">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

10. <span data-ttu-id="c4a42-422">Clique em **Salvar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="c4a42-422">Select **Save** to save your changes.</span></span>

11. <span data-ttu-id="c4a42-423">No painel esquerdo, selecione Expor **uma API** e, em seguida, ao lado do URI da ID do Aplicativo, selecione **Definir.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-423">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

12. <span data-ttu-id="c4a42-424">Ainda na página **Expor uma API,** nos **Escopos definidos por essa** área de API, selecione Adicionar um **escopo.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-424">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="c4a42-425">No novo escopo:</span><span class="sxs-lookup"><span data-stu-id="c4a42-425">In the new scope:</span></span>

    1. <span data-ttu-id="c4a42-426">Defina o nome do escopo **como user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-426">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="c4a42-427">Selecione os administradores e usuários que podem consentir.</span><span class="sxs-lookup"><span data-stu-id="c4a42-427">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="c4a42-428">Defina os valores restantes necessários.</span><span class="sxs-lookup"><span data-stu-id="c4a42-428">Define any remaining values required.</span></span>

    4. <span data-ttu-id="c4a42-429">Selecione **Adicionar escopo**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-429">Select **Add scope**.</span></span>

    5. <span data-ttu-id="c4a42-430">Selecione **Salvar** na parte superior para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="c4a42-430">Select **Save** at the top to save your changes.</span></span>

13. <span data-ttu-id="c4a42-431">Ainda na página **Expor uma API,** na **área** Aplicativos cliente Autorizados, selecione Adicionar um **aplicativo cliente.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-431">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="c4a42-432">No novo aplicativo cliente:</span><span class="sxs-lookup"><span data-stu-id="c4a42-432">In the new client application:</span></span>

    1. <span data-ttu-id="c4a42-433">Defina a ID do Cliente como **d3590ed6-52b3-4102-aeff-aad2292ab01c.**</span><span class="sxs-lookup"><span data-stu-id="c4a42-433">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="c4a42-434">Esse valor é a ID de cliente do Microsoft Office e permite que o Office obtenha um token de acesso para seu armazenamento de chaves.</span><span class="sxs-lookup"><span data-stu-id="c4a42-434">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="c4a42-435">Em **Escopos Autorizados,** selecione o **user_impersonation** escopo.</span><span class="sxs-lookup"><span data-stu-id="c4a42-435">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="c4a42-436">Selecione **Adicionar aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="c4a42-436">Select **Add application**.</span></span>

    4. <span data-ttu-id="c4a42-437">Selecione **Salvar** na parte superior para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="c4a42-437">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="c4a42-438">Seu serviço DKE agora está registrado.</span><span class="sxs-lookup"><span data-stu-id="c4a42-438">Your DKE service is now registered.</span></span> <span data-ttu-id="c4a42-439">Continue criando [rótulos usando DKE](#create-sensitivity-labels-using-dke).</span><span class="sxs-lookup"><span data-stu-id="c4a42-439">Continue by [creating labels using DKE](#create-sensitivity-labels-using-dke).</span></span>

## <a name="create-sensitivity-labels-using-dke"></a><span data-ttu-id="c4a42-440">Criar rótulos de sensibilidade usando DKE</span><span class="sxs-lookup"><span data-stu-id="c4a42-440">Create sensitivity labels using DKE</span></span>

<span data-ttu-id="c4a42-441">No centro de conformidade do Microsoft 365, crie um novo rótulo de sensibilidade e aplique criptografia como faria de outra forma.</span><span class="sxs-lookup"><span data-stu-id="c4a42-441">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="c4a42-442">Selecione **Usar Criptografia de Chave** Dupla e insira a URL do ponto de extremidade da chave.</span><span class="sxs-lookup"><span data-stu-id="c4a42-442">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="c4a42-443">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c4a42-443">For example:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4a42-444">![Selecione Usar Criptografia de Chave Dupla no centro de conformidade do Microsoft 365](../media/dke-use-dke.png)</span><span class="sxs-lookup"><span data-stu-id="c4a42-444">![Select Use Double Key Encryption in the Microsoft 365 compliance center](../media/dke-use-dke.png)</span></span>

<span data-ttu-id="c4a42-445">Qualquer rótulo DKE que você adicionar começará a aparecer para os usuários nas versões mais recentes do Microsoft 365 Apps para empresas.</span><span class="sxs-lookup"><span data-stu-id="c4a42-445">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="c4a42-446">Pode levar até 24 horas para que os clientes se atualizem com os novos rótulos.</span><span class="sxs-lookup"><span data-stu-id="c4a42-446">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="c4a42-447">Habilitar dKE em seu cliente</span><span class="sxs-lookup"><span data-stu-id="c4a42-447">Enable DKE in your client</span></span>

<span data-ttu-id="c4a42-448">Se você for um Office Insider, o DKE será habilitado para você.</span><span class="sxs-lookup"><span data-stu-id="c4a42-448">If you're an Office Insider, DKE is enabled for you.</span></span> <span data-ttu-id="c4a42-449">Caso contrário, habilita o DKE para seu cliente adicionando as seguintes chaves do Registro:</span><span class="sxs-lookup"><span data-stu-id="c4a42-449">Otherwise, enable DKE for your client by adding the following registry keys:</span></span>

```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a><span data-ttu-id="c4a42-450">Migrar arquivos protegidos de rótulos HYOK para rótulos DKE</span><span class="sxs-lookup"><span data-stu-id="c4a42-450">Migrate protected files from HYOK labels to DKE labels</span></span>

<span data-ttu-id="c4a42-451">Se você quiser, depois de terminar de configurar o DKE, poderá migrar o conteúdo que protegeu usando rótulos HYOK para rótulos DKE.</span><span class="sxs-lookup"><span data-stu-id="c4a42-451">If you want, once you're finished setting up DKE, you can migrate content that you've protected using HYOK labels to DKE labels.</span></span> <span data-ttu-id="c4a42-452">Para migrar, você usará o scanner AIP.</span><span class="sxs-lookup"><span data-stu-id="c4a42-452">To migrate, you'll use the AIP scanner.</span></span> <span data-ttu-id="c4a42-453">Para começar a usar o scanner, consulte O que é o scanner de rotulagem unificado da Proteção de Informações do [Azure?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner).</span><span class="sxs-lookup"><span data-stu-id="c4a42-453">To get started using the scanner, see [What is the Azure Information Protection unified labeling scanner?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner).</span></span>

<span data-ttu-id="c4a42-454">Se você não migrar o conteúdo, seu conteúdo protegido HYOK permanecerá não afetado.</span><span class="sxs-lookup"><span data-stu-id="c4a42-454">If you don't migrate content, your HYOK protected content will remain unaffected.</span></span>
