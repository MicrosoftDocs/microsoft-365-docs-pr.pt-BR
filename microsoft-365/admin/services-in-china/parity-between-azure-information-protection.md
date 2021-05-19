---
title: Suporte à Proteção de Informações do Azure para Office 365 operado pela 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: Saiba mais sobre a Proteção de Informações do Azure (AIP) para Office 365 operado pela 21Vianet e como configurá-la para clientes na China.
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535837"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="ab411-103">Suporte à Proteção de Informações do Azure para Office 365 operado pela 21Vianet</span><span class="sxs-lookup"><span data-stu-id="ab411-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="ab411-104">Este artigo aborda as diferenças entre o suporte à Proteção de Informações do Azure (AIP) para o Office 365 operado pela 21Vianet e ofertas comerciais, bem como instruções específicas para configurar o AIP para clientes na China, incluindo como instalar o scanner local do AIP e gerenciar trabalhos de verificação de &mdash; conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ab411-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="ab411-105">Diferenças entre a AIP para Office 365 operado pela 21Vianet e ofertas comerciais</span><span class="sxs-lookup"><span data-stu-id="ab411-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="ab411-106">Embora nosso objetivo seja fornecer todos os recursos comerciais e funcionalidades aos clientes na China com nosso AIP para Office 365 operado pela oferta da 21Vianet, há algumas funcionalidades ausentes que gostaria de destacar.</span><span class="sxs-lookup"><span data-stu-id="ab411-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="ab411-107">A lista a seguir inclui as lacunas existentes entre a AIP para Office 365 operado pela 21Vianet e nossas ofertas comerciais a partir de janeiro de 2021:</span><span class="sxs-lookup"><span data-stu-id="ab411-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="ab411-108">O IRM (Gerenciamento de Direitos de Informação) só tem suporte para Microsoft 365 Apps para Grandes Empresas (build 11731.10000 ou superior).</span><span class="sxs-lookup"><span data-stu-id="ab411-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="ab411-109">Office 2010, Office 2013 e outras versões Office 2016 não são suportadas.</span><span class="sxs-lookup"><span data-stu-id="ab411-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="ab411-110">A migração Active Directory Rights Management Services (AD RMS) para a AIP não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="ab411-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="ab411-111">Há suporte para o compartilhamento de emails protegidos com usuários na nuvem comercial.</span><span class="sxs-lookup"><span data-stu-id="ab411-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="ab411-112">O compartilhamento de documentos e anexos de email com usuários na nuvem comercial não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="ab411-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="ab411-113">Isso inclui Office 365 operado por usuários da 21Vianet na nuvem comercial Office 365, não operados por usuários da 21Vianet na nuvem comercial e usuários com uma licença RMS para Indivíduos.</span><span class="sxs-lookup"><span data-stu-id="ab411-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="ab411-114">O IRM com SharePoint (bibliotecas e sites protegidos por IRM) não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="ab411-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="ab411-115">No momento, a Extensão de Dispositivo Móvel do AD RMS não está disponível.</span><span class="sxs-lookup"><span data-stu-id="ab411-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="ab411-116">O [Visualizador Móvel](/azure/information-protection/rms-client/mobile-app-faq) não é suportado pelo Azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="ab411-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="ab411-117">A área AIP do portal do Azure não está disponível para os clientes na China.</span><span class="sxs-lookup"><span data-stu-id="ab411-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="ab411-118">Use [comandos do PowerShell em](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) vez de executar ações no portal, como gerenciar e executar trabalhos de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ab411-118">Use [PowerShell commands](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as managing and running your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="ab411-119">Configurar a AIP para clientes na China</span><span class="sxs-lookup"><span data-stu-id="ab411-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="ab411-120">Para configurar a AIP para clientes na China:</span><span class="sxs-lookup"><span data-stu-id="ab411-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="ab411-121">[Habilitar o Gerenciamento de Direitos para o locatário](#step-1-enable-rights-management-for-the-tenant).</span><span class="sxs-lookup"><span data-stu-id="ab411-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

1. <span data-ttu-id="ab411-122">Adicione a entidade de serviço do Serviço de [Sincronização de Proteção de Informações da Microsoft.](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)</span><span class="sxs-lookup"><span data-stu-id="ab411-122">[Add the Microsoft Information Protection Sync Service service principal](#step-2-add-the-microsoft-information-protection-sync-service-service-principal).</span></span>

1. <span data-ttu-id="ab411-123">[Configurar criptografia DNS](#step-3-configure-dns-encryption).</span><span class="sxs-lookup"><span data-stu-id="ab411-123">[Configure DNS encryption](#step-3-configure-dns-encryption).</span></span>

1. <span data-ttu-id="ab411-124">[Instale e configure o cliente de rotulagem unificada do AIP.](#step-4-install-and-configure-the-aip-unified-labeling-client)</span><span class="sxs-lookup"><span data-stu-id="ab411-124">[Install and configure the AIP unified labeling client](#step-4-install-and-configure-the-aip-unified-labeling-client).</span></span>

1. <span data-ttu-id="ab411-125">[Configurar aplicativos AIP em Windows](#step-5-configure-aip-apps-on-windows).</span><span class="sxs-lookup"><span data-stu-id="ab411-125">[Configure AIP apps on Windows](#step-5-configure-aip-apps-on-windows).</span></span>

1. <span data-ttu-id="ab411-126">[Instale o scanner local do AIP e gerencie trabalhos de verificação de conteúdo.](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="ab411-126">[Install the AIP on-premises scanner and manage content scan jobs](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="ab411-127">Etapa 1: Habilitar o Gerenciamento de Direitos para o locatário</span><span class="sxs-lookup"><span data-stu-id="ab411-127">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="ab411-128">Para que a criptografia funcione corretamente, o RMS deve estar habilitado para o locatário.</span><span class="sxs-lookup"><span data-stu-id="ab411-128">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="ab411-129">Verifique se o RMS está habilitado:</span><span class="sxs-lookup"><span data-stu-id="ab411-129">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="ab411-130">Iniciar o PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="ab411-130">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="ab411-131">Se o módulo AIPService não estiver instalado, execute `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="ab411-131">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="ab411-132">Importar o módulo usando `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="ab411-132">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="ab411-133">Conexão ao serviço usando `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="ab411-133">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="ab411-134">Execute `(Get-AipServiceConfiguration).FunctionalState` e verifique se o estado é `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="ab411-134">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="ab411-135">Se o estado funcional for `Disabled` , execute `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="ab411-135">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a><span data-ttu-id="ab411-136">Etapa 2: Adicionar a entidade de serviço do Serviço de Sincronização de Proteção de Informações da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ab411-136">Step 2: Add the Microsoft Information Protection Sync Service service principal</span></span>

<span data-ttu-id="ab411-137">A **entidade de** serviço do Serviço de Sincronização de Proteção de Informações da Microsoft não está disponível nos locatários do Azure China por padrão e é necessária para a Proteção de Informações do Azure.</span><span class="sxs-lookup"><span data-stu-id="ab411-137">The **Microsoft Information Protection Sync Service** service principal is not available in Azure China tenants by default, and is required for Azure Information Protection.</span></span>

1. <span data-ttu-id="ab411-138">Crie essa entidade de serviço manualmente usando o cmdlet [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) e a ID do aplicativo para o Serviço de Sincronização de Proteção de Informações `870c4f2e-85b6-4d43-bdda-6ed9a579b725` da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ab411-138">Create this service principal manually using the [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) cmdlet and the `870c4f2e-85b6-4d43-bdda-6ed9a579b725` application ID for the Microsoft Information Protection Sync Service.</span></span> 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. <span data-ttu-id="ab411-139">Depois de adicionar a entidade de serviço, adicione as permissões relevantes necessárias ao serviço.</span><span class="sxs-lookup"><span data-stu-id="ab411-139">After adding the service principal, add the relevant permissions required to the service.</span></span>

### <a name="step-3-configure-dns-encryption"></a><span data-ttu-id="ab411-140">Etapa 3: Configurar criptografia DNS</span><span class="sxs-lookup"><span data-stu-id="ab411-140">Step 3: Configure DNS encryption</span></span>

<span data-ttu-id="ab411-141">Para que a criptografia funcione corretamente, Office aplicativos cliente devem se conectar à instância da China do serviço e inicializar a partir daí.</span><span class="sxs-lookup"><span data-stu-id="ab411-141">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="ab411-142">Para redirecionar aplicativos cliente para a instância de serviço correta, o administrador do locatário deve configurar um registro SRV DNS com informações sobre a URL do Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="ab411-142">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="ab411-143">Sem o registro SRV DNS, o aplicativo cliente tentará se conectar à instância de nuvem pública por padrão e falhará.</span><span class="sxs-lookup"><span data-stu-id="ab411-143">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="ab411-144">Além disso, a suposição é de que os usuários entrarão com um nome de usuário com base no domínio de propriedade do locatário (por exemplo), e não o nome de usuário `joe@contoso.cn` `onmschina` (por exemplo, `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="ab411-144">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="ab411-145">O nome de domínio do nome de usuário é usado para redirecionamento DNS para a instância de serviço correta.</span><span class="sxs-lookup"><span data-stu-id="ab411-145">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="ab411-146">Configurar criptografia DNS - Windows</span><span class="sxs-lookup"><span data-stu-id="ab411-146">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="ab411-147">Obter a ID do RMS:</span><span class="sxs-lookup"><span data-stu-id="ab411-147">Get the RMS ID:</span></span>

    1. <span data-ttu-id="ab411-148">Iniciar o PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="ab411-148">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="ab411-149">Se o módulo AIPService não estiver instalado, execute `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="ab411-149">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="ab411-150">Conexão ao serviço usando `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="ab411-150">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="ab411-151">Execute `(Get-AipServiceConfiguration).RightsManagementServiceId` para obter a ID do RMS.</span><span class="sxs-lookup"><span data-stu-id="ab411-151">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="ab411-152">Faça logoff no provedor DNS, navegue até as configurações DNS do domínio e adicione um novo registro SRV.</span><span class="sxs-lookup"><span data-stu-id="ab411-152">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="ab411-153">Serviço = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="ab411-153">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="ab411-154">Protocolo = `_http`</span><span class="sxs-lookup"><span data-stu-id="ab411-154">Protocol = `_http`</span></span>
    - <span data-ttu-id="ab411-155">Nome = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="ab411-155">Name = `_tcp`</span></span>
    - <span data-ttu-id="ab411-156">Target = `[GUID].rms.aadrm.cn` (onde GUID é a ID RMS)</span><span class="sxs-lookup"><span data-stu-id="ab411-156">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="ab411-157">Prioridade, Peso, Segundos, TTL = valores padrão</span><span class="sxs-lookup"><span data-stu-id="ab411-157">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="ab411-158">Associe o domínio personalizado ao locatário no [portal do Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="ab411-158">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="ab411-159">Isso adicionará uma entrada no DNS, que pode levar vários minutos para ser verificada depois que você adicionar o valor às configurações dns.</span><span class="sxs-lookup"><span data-stu-id="ab411-159">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="ab411-160">Entre no centro de administração Microsoft 365 com as credenciais de administrador global correspondentes e adicione o domínio (por exemplo, `contoso.cn` ) para criação do usuário.</span><span class="sxs-lookup"><span data-stu-id="ab411-160">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="ab411-161">No processo de verificação, alterações de DNS adicionais podem ser necessárias.</span><span class="sxs-lookup"><span data-stu-id="ab411-161">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="ab411-162">Depois que a verificação for feita, os usuários poderão ser criados.</span><span class="sxs-lookup"><span data-stu-id="ab411-162">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="ab411-163">Configurar criptografia DNS - Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="ab411-163">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="ab411-164">Faça logoff no provedor DNS, navegue até as configurações DNS do domínio e adicione um novo registro SRV.</span><span class="sxs-lookup"><span data-stu-id="ab411-164">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="ab411-165">Serviço = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="ab411-165">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="ab411-166">Protocolo = `_http`</span><span class="sxs-lookup"><span data-stu-id="ab411-166">Protocol = `_http`</span></span>
- <span data-ttu-id="ab411-167">Nome = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="ab411-167">Name = `_tcp`</span></span>
- <span data-ttu-id="ab411-168">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="ab411-168">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="ab411-169">Porta = `80`</span><span class="sxs-lookup"><span data-stu-id="ab411-169">Port = `80`</span></span>
- <span data-ttu-id="ab411-170">Prioridade, Peso, Segundos, TTL = valores padrão</span><span class="sxs-lookup"><span data-stu-id="ab411-170">Priority, Weight, Seconds, TTL = default values</span></span>


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="ab411-171">Etapa 4: Instalar e configurar o cliente de rotulagem unificada do AIP</span><span class="sxs-lookup"><span data-stu-id="ab411-171">Step 4: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="ab411-172">Baixe e instale o cliente de rotulagem unificada do AIP no [Centro de Download da Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="ab411-172">Download and install the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="ab411-173">Para mais informações, confira:</span><span class="sxs-lookup"><span data-stu-id="ab411-173">For more information, see:</span></span>

- [<span data-ttu-id="ab411-174">Documentação do AIP</span><span class="sxs-lookup"><span data-stu-id="ab411-174">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="ab411-175">Política de suporte e histórico de versão do AIP</span><span class="sxs-lookup"><span data-stu-id="ab411-175">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="ab411-176">Requisitos do sistema AIP</span><span class="sxs-lookup"><span data-stu-id="ab411-176">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="ab411-177">Início rápido da AIP: Implantar o cliente AIP</span><span class="sxs-lookup"><span data-stu-id="ab411-177">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="ab411-178">Guia de administrador do AIP</span><span class="sxs-lookup"><span data-stu-id="ab411-178">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="ab411-179">Guia do usuário AIP</span><span class="sxs-lookup"><span data-stu-id="ab411-179">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="ab411-180">Saiba mais sobre Microsoft 365 rótulos de sensibilidade</span><span class="sxs-lookup"><span data-stu-id="ab411-180">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a><span data-ttu-id="ab411-181">Etapa 5: Configurar aplicativos AIP em Windows</span><span class="sxs-lookup"><span data-stu-id="ab411-181">Step 5: Configure AIP apps on Windows</span></span>

<span data-ttu-id="ab411-182">Os aplicativos AIP Windows a chave do Registro a seguir para apontar para a nuvem soberana correta para o Azure China:</span><span class="sxs-lookup"><span data-stu-id="ab411-182">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="ab411-183">Nó do Registro = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="ab411-183">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="ab411-184">Nome = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="ab411-184">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="ab411-185">Valor = `6` (padrão = 0)</span><span class="sxs-lookup"><span data-stu-id="ab411-185">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="ab411-186">Tipo = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="ab411-186">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab411-187">Certifique-se de não excluir a chave do Registro após uma desinstalação.</span><span class="sxs-lookup"><span data-stu-id="ab411-187">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="ab411-188">Se a chave estiver vazia, incorreta ou não existente, a funcionalidade se comportará como o valor padrão (valor padrão = 0 para a nuvem comercial).</span><span class="sxs-lookup"><span data-stu-id="ab411-188">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="ab411-189">Se a chave estiver vazia ou incorreta, um erro de impressão também será adicionado ao log.</span><span class="sxs-lookup"><span data-stu-id="ab411-189">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="ab411-190">Etapa 6: instalar o scanner local do AIP e gerenciar trabalhos de verificação de conteúdo</span><span class="sxs-lookup"><span data-stu-id="ab411-190">Step 6: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="ab411-191">Instale o scanner local do AIP para verificar seus compartilhamentos de rede e conteúdo para dados confidenciais e aplicar rótulos de classificação e proteção conforme configurado na política da sua organização.</span><span class="sxs-lookup"><span data-stu-id="ab411-191">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="ab411-192">Ao configurar e gerenciar seus trabalhos de verificação de conteúdo, use o procedimento a seguir, em vez da interface do portal do [Azure](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) usada pelas ofertas comerciais.</span><span class="sxs-lookup"><span data-stu-id="ab411-192">When configuring and managing your content scan jobs, use the following procedure instead of the [Azure portal interface](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) that's used by the commercial offerings.</span></span>

<span data-ttu-id="ab411-193">Para obter mais informações, consulte O que é o scanner unificado de rotulagem da Proteção de Informações do [Azure?](/azure/information-protection/deploy-aip-scanner) e Gerenciar seus trabalhos de verificação de conteúdo usando apenas [o PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span><span class="sxs-lookup"><span data-stu-id="ab411-193">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>

<span data-ttu-id="ab411-194">**Para instalar e configurar o scanner**:</span><span class="sxs-lookup"><span data-stu-id="ab411-194">**To install and configure your scanner**:</span></span>

1. <span data-ttu-id="ab411-195">Entre no computador do Windows Server que executará o scanner.</span><span class="sxs-lookup"><span data-stu-id="ab411-195">Sign in to the Windows Server computer that will run the scanner.</span></span> <span data-ttu-id="ab411-196">Use uma conta que tenha direitos de administrador local e que tenha permissões para gravar no banco de dados SQL Server mestre.</span><span class="sxs-lookup"><span data-stu-id="ab411-196">Use an account that has local administrator rights and that has permissions to write to the SQL Server master database.</span></span>

1. <span data-ttu-id="ab411-197">Comece com o PowerShell fechado.</span><span class="sxs-lookup"><span data-stu-id="ab411-197">Start with PowerShell closed.</span></span> <span data-ttu-id="ab411-198">Se você instalou o cliente e o scanner AIP anteriormente, certifique-se de que o **serviço AIPScanner** foi interrompido.</span><span class="sxs-lookup"><span data-stu-id="ab411-198">If you've previously installed the AIP client and scanner, make sure that the **AIPScanner** service is stopped.</span></span>

1. <span data-ttu-id="ab411-199">Abra uma Windows PowerShell com a opção **Executar como** administrador.</span><span class="sxs-lookup"><span data-stu-id="ab411-199">Open a Windows PowerShell session with the **Run as an administrator** option.</span></span>

1. <span data-ttu-id="ab411-200">Execute o cmdlet [Install-AIPScanner,](/powershell/module/azureinformationprotection/Install-AIPScanner) especificando sua instância de SQL Server na qual criar um banco de dados para o scanner da Proteção de Informações do Azure e um nome significativo para o cluster do scanner.</span><span class="sxs-lookup"><span data-stu-id="ab411-200">Run the [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) cmdlet, specifying your SQL Server instance on which to create a database for the Azure Information Protection scanner, and a meaningful name for your scanner cluster.</span></span>

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > <span data-ttu-id="ab411-201">Você pode usar o mesmo nome de cluster no [comando Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) para associar vários nós de scanner ao mesmo cluster.</span><span class="sxs-lookup"><span data-stu-id="ab411-201">You can use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="ab411-202">Usar o mesmo cluster para vários nós de scanner permite que vários scanners trabalhem juntos para executar suas verificações.</span><span class="sxs-lookup"><span data-stu-id="ab411-202">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
    > 

1. <span data-ttu-id="ab411-203">Verifique se o serviço agora está instalado usando o **Administrative Tools**  >  **Services**.</span><span class="sxs-lookup"><span data-stu-id="ab411-203">Verify that the service is now installed by using **Administrative Tools** > **Services**.</span></span>

    <span data-ttu-id="ab411-204">O serviço instalado chama-se Scanner de Proteção de Informações do **Azure** e é configurado para ser executado usando a conta de serviço de scanner que você criou.</span><span class="sxs-lookup"><span data-stu-id="ab411-204">The installed service is named **Azure Information Protection Scanner** and is configured to run by using the scanner service account that you created.</span></span>

1. <span data-ttu-id="ab411-205">Obter um token do Azure a ser usado com o scanner.</span><span class="sxs-lookup"><span data-stu-id="ab411-205">Get an Azure token to use with your scanner.</span></span> <span data-ttu-id="ab411-206">Um token do Azure AD permite que o scanner se autenture no serviço de Proteção de Informações do Azure, permitindo que o scanner seja executado de forma não interativa.</span><span class="sxs-lookup"><span data-stu-id="ab411-206">An Azure AD token allows the scanner to authenticate to the Azure Information Protection service, enabling the scanner to run non-interactively.</span></span> 

    1. <span data-ttu-id="ab411-207">Abra o portal do Azure e crie um aplicativo do Azure AD para especificar um token de acesso para autenticação.</span><span class="sxs-lookup"><span data-stu-id="ab411-207">Open the Azure portal and create an Azure AD application to specify an access token for authentication.</span></span> <span data-ttu-id="ab411-208">Para obter mais informações, [consulte How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span><span class="sxs-lookup"><span data-stu-id="ab411-208">For more information, see [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>
    
        > [!TIP]
        > <span data-ttu-id="ab411-209">Ao criar e configurar **aplicativos** do Azure AD para o comando [Set-AIPAuthentication,](/powershell/module/azureinformationprotection/set-aipauthentication) o painel Permissões de API de Solicitação mostra as **APIs** que minha organização usa guia em vez da guia **APIs** da Microsoft. Selecione as **APIs que minha organização usa** para selecionar os Serviços de Gerenciamento de Direitos do **Azure.**</span><span class="sxs-lookup"><span data-stu-id="ab411-209">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span> 
        >

    1. <span data-ttu-id="ab411-210">No computador Windows Server, se sua conta de serviço de scanner tiver sido concedida o **Logon** localmente à direita para a instalação, entre com essa conta e inicie uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab411-210">From the Windows Server computer, if your scanner service account has been granted the **Log on locally** right for the installation, sign in with this account and start a PowerShell session.</span></span> 
    
        <span data-ttu-id="ab411-211">Se sua conta de serviço de scanner não puder ser concedida ao **Log** localmente correto para a instalação, use o parâmetro *OnBehalfOf* com [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), conforme descrito em Como rotular arquivos de forma não interativa para a Proteção de Informações do [Azure.](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)</span><span class="sxs-lookup"><span data-stu-id="ab411-211">If your scanner service account cannot be granted the **Log on locally** right for the installation, use the *OnBehalfOf* parameter with [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), as described in [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>

    1. <span data-ttu-id="ab411-212">Execute [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), especificando valores copiados do seu aplicativo do Azure AD:</span><span class="sxs-lookup"><span data-stu-id="ab411-212">Run [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), specifying values copied from your Azure AD application:</span></span>

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      <span data-ttu-id="ab411-213">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ab411-213">For example:</span></span>

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    <span data-ttu-id="ab411-214">O scanner agora tem um token para autenticar no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ab411-214">The scanner now has a token to authenticate to Azure AD.</span></span> <span data-ttu-id="ab411-215">Esse token é válido por um ano, dois anos ou nunca, de acordo com a configuração do segredo do cliente do **aplicativo Web /API** no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ab411-215">This token is valid for one year, two years, or never, according to your configuration of the **Web app /API** client secret in Azure AD.</span></span> <span data-ttu-id="ab411-216">Quando o token expirar, você deverá repetir este procedimento.</span><span class="sxs-lookup"><span data-stu-id="ab411-216">When the token expires, you must repeat this procedure.</span></span>

1. <span data-ttu-id="ab411-217">Execute o cmdlet [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) para definir o scanner para funcionar no modo offline.</span><span class="sxs-lookup"><span data-stu-id="ab411-217">Run the [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) cmdlet to set the scanner to function in offline mode.</span></span> <span data-ttu-id="ab411-218">Executar:</span><span class="sxs-lookup"><span data-stu-id="ab411-218">Run:</span></span>

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. <span data-ttu-id="ab411-219">Execute o cmdlet [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) para criar um trabalho de verificação de conteúdo padrão.</span><span class="sxs-lookup"><span data-stu-id="ab411-219">Run the [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) cmdlet to create a default content scan job.</span></span>

    <span data-ttu-id="ab411-220">O único parâmetro necessário no cmdlet **Set-AIPScannerContentScanJob** é **Enforce**.</span><span class="sxs-lookup"><span data-stu-id="ab411-220">The only required parameter in the **Set-AIPScannerContentScanJob** cmdlet is **Enforce**.</span></span> <span data-ttu-id="ab411-221">No entanto, talvez você queira definir outras configurações para seu trabalho de verificação de conteúdo no momento.</span><span class="sxs-lookup"><span data-stu-id="ab411-221">However, you may want to define other settings for your content scan job at this time.</span></span> <span data-ttu-id="ab411-222">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ab411-222">For example:</span></span>

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    <span data-ttu-id="ab411-223">A sintaxe acima configura as seguintes configurações enquanto você continua a configuração:</span><span class="sxs-lookup"><span data-stu-id="ab411-223">The syntax above configures the following settings while you continue the configuration:</span></span>

    - <span data-ttu-id="ab411-224">Mantém o agendamento de executar o scanner para *manual*</span><span class="sxs-lookup"><span data-stu-id="ab411-224">Keeps the scanner run scheduling to *manual*</span></span>
    - <span data-ttu-id="ab411-225">Define os tipos de informações a serem descobertos com base na política de rotulagem de sensibilidade</span><span class="sxs-lookup"><span data-stu-id="ab411-225">Sets the information types to be discovered based on the sensitivity labeling policy</span></span>
    - <span data-ttu-id="ab411-226">Não *impõe* uma política de rotulagem de sensibilidade</span><span class="sxs-lookup"><span data-stu-id="ab411-226">Does *not* enforce a sensitivity labeling policy</span></span>
    - <span data-ttu-id="ab411-227">Rotula automaticamente arquivos com base no conteúdo, usando o rótulo padrão definido para a política de rotulagem de sensibilidade</span><span class="sxs-lookup"><span data-stu-id="ab411-227">Automatically labels files based on content, using the default label defined for the sensitivity labeling policy</span></span>
    - <span data-ttu-id="ab411-228">Não *permite* o relabeleamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="ab411-228">Does *not* allow for relabeling files</span></span>
    - <span data-ttu-id="ab411-229">Preserva os detalhes do arquivo durante a verificação e rotulagem automática, incluindo a data *modificada*, *a última* modificação e *a modificação por* valores</span><span class="sxs-lookup"><span data-stu-id="ab411-229">Preserves file details while scanning and auto-labeling, including *date modified*, *last modified*, and *modified by* values</span></span>
    - <span data-ttu-id="ab411-230">Define o scanner para excluir arquivos .msg e .tmp ao executar</span><span class="sxs-lookup"><span data-stu-id="ab411-230">Sets the scanner to exclude .msg and .tmp files when running</span></span>
    - <span data-ttu-id="ab411-231">Define o proprietário padrão como a conta que você deseja usar ao executar o scanner</span><span class="sxs-lookup"><span data-stu-id="ab411-231">Sets the default owner to the account you want to use when running the scanner</span></span>

1. <span data-ttu-id="ab411-232">Use o cmdlet [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) para definir os repositórios que você deseja examinar no trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ab411-232">Use the [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) cmdlet to define the repositories you want to scan in your content scan job.</span></span> <span data-ttu-id="ab411-233">Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="ab411-233">For example, run:</span></span>

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    <span data-ttu-id="ab411-234">Use uma das seguintes sintaxes, dependendo do tipo de repositório que você está adicionando:</span><span class="sxs-lookup"><span data-stu-id="ab411-234">Use one of the following syntaxes, depending on the type of repository you're adding:</span></span>

    - <span data-ttu-id="ab411-235">Para um compartilhamento de rede, use `\\Server\Folder` .</span><span class="sxs-lookup"><span data-stu-id="ab411-235">For a network share, use `\\Server\Folder`.</span></span>
    - <span data-ttu-id="ab411-236">Para uma SharePoint, use `http://sharepoint.contoso.com/Shared%20Documents/Folder` .</span><span class="sxs-lookup"><span data-stu-id="ab411-236">For a SharePoint library, use `http://sharepoint.contoso.com/Shared%20Documents/Folder`.</span></span>
    - <span data-ttu-id="ab411-237">Para um caminho local: `C:\Folder`</span><span class="sxs-lookup"><span data-stu-id="ab411-237">For a local path: `C:\Folder`</span></span>
    - <span data-ttu-id="ab411-238">Para um caminho UNC: `\\Server\Folder`</span><span class="sxs-lookup"><span data-stu-id="ab411-238">For a UNC path: `\\Server\Folder`</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab411-239">Não há suporte para caracteres curinga e locais WebDav não são suportados.</span><span class="sxs-lookup"><span data-stu-id="ab411-239">Wildcards are not supported and WebDav locations are not supported.</span></span>
    >
    > <span data-ttu-id="ab411-240">Para modificar o repositório posteriormente, use o cmdlet [Set-AIPScannerRepository.](/powershell/module/azureinformationprotection/set-aipscannerrepository)</span><span class="sxs-lookup"><span data-stu-id="ab411-240">To modify the repository later on, use the [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) cmdlet instead.</span></span> 


<span data-ttu-id="ab411-241">Continue com as seguintes etapas conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="ab411-241">Continue with the following steps as needed:</span></span>

- [<span data-ttu-id="ab411-242">Executar um ciclo de descoberta e exibir relatórios do scanner</span><span class="sxs-lookup"><span data-stu-id="ab411-242">Run a discovery cycle and view reports for the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [<span data-ttu-id="ab411-243">Usar o PowerShell para configurar o scanner para aplicar classificação e proteção</span><span class="sxs-lookup"><span data-stu-id="ab411-243">Use PowerShell to configure the scanner to apply classification and protection</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [<span data-ttu-id="ab411-244">Usar o PowerShell para configurar uma política de DLP com o scanner</span><span class="sxs-lookup"><span data-stu-id="ab411-244">Use PowerShell to configure a DLP policy with the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

<span data-ttu-id="ab411-245">A tabela a seguir lista os cmdlets do PowerShell relevantes para instalar o scanner e gerenciar seus trabalhos de verificação de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="ab411-245">The following table lists PowerShell cmdlets that are relevant for installing the scanner and managing your content scan jobs:</span></span>

| <span data-ttu-id="ab411-246">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ab411-246">Cmdlet</span></span> | <span data-ttu-id="ab411-247">Descrição</span><span class="sxs-lookup"><span data-stu-id="ab411-247">Description</span></span> |
|--|--|
| [<span data-ttu-id="ab411-248">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="ab411-248">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="ab411-249">Adiciona um novo repositório ao trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ab411-249">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="ab411-250">Get-AIPScannerConfiguration</span><span class="sxs-lookup"><span data-stu-id="ab411-250">Get-AIPScannerConfiguration</span></span>](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|<span data-ttu-id="ab411-251">Retorna detalhes sobre seu cluster.</span><span class="sxs-lookup"><span data-stu-id="ab411-251">Returns details about your cluster.</span></span> |
| [<span data-ttu-id="ab411-252">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="ab411-252">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="ab411-253">Obtém detalhes sobre seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ab411-253">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="ab411-254">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="ab411-254">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="ab411-255">Obtém detalhes sobre repositórios definidos para seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ab411-255">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="ab411-256">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="ab411-256">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="ab411-257">Exclui seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ab411-257">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="ab411-258">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="ab411-258">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="ab411-259">Remove um repositório do trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ab411-259">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="ab411-260">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="ab411-260">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="ab411-261">Define configurações para seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ab411-261">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="ab411-262">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="ab411-262">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="ab411-263">Define configurações para um repositório existente em seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ab411-263">Defines settings for an existing repository in your content scan job.</span></span> |
| | |

<span data-ttu-id="ab411-264">Para mais informações, confira:</span><span class="sxs-lookup"><span data-stu-id="ab411-264">For more information, see:</span></span>

- [<span data-ttu-id="ab411-265">O que é o scanner unificado de rotulagem da Proteção de Informações do Azure?</span><span class="sxs-lookup"><span data-stu-id="ab411-265">What is the Azure Information Protection unified labeling scanner?</span></span>](/azure/information-protection/deploy-aip-scanner)
- [<span data-ttu-id="ab411-266">Configurando e instalando o scanner unificado de rotulagem da Proteção de Informações do Azure (AIP)</span><span class="sxs-lookup"><span data-stu-id="ab411-266">Configuring and installing the Azure Information Protection (AIP) unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- <span data-ttu-id="ab411-267">[Gerencie seus trabalhos de verificação de conteúdo usando apenas o PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span><span class="sxs-lookup"><span data-stu-id="ab411-267">[Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>
