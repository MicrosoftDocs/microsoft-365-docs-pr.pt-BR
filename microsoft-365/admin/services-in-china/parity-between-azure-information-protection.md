---
title: Paridade entre a Proteção de Informações do Azure para o Office 365 operado pela 21Vianet e ofertas comerciais
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
ms.reviewer: arthurj
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
description: Saiba mais sobre a Proteção de Informações do Azure (AIP) para o Office 365 operado pela 21Vianet e como configurá-la para clientes na China.
monikerRange: o365-21vianet
ms.openlocfilehash: 50269749b5f4e544263f790ec9c7e4474af57219
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840296"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="cfb39-103">Paridade entre a Proteção de Informações do Azure para o Office 365 operado pela 21Vianet e ofertas comerciais</span><span class="sxs-lookup"><span data-stu-id="cfb39-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="cfb39-104">Embora nosso objetivo seja fornecer todos os recursos comerciais e funcionalidades aos clientes na China com nossa AIP (Proteção de Informações do Azure) para a oferta do Office 365 operado pela 21Vianet, há algumas funcionalidades ausentes que queremos destacar.</span><span class="sxs-lookup"><span data-stu-id="cfb39-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection (AIP) for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="cfb39-105">A lista a seguir inclui as lacunas existentes entre a Proteção de Informações do Azure para o Office 365 operado pela 21Vianet e nossas ofertas comerciais a partir de janeiro de 2021:</span><span class="sxs-lookup"><span data-stu-id="cfb39-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="cfb39-106">O Gerenciamento de Direitos de Informação (IRM) tem suporte apenas para o Microsoft 365 Apps para empresas (build 11731.10000 ou superior).</span><span class="sxs-lookup"><span data-stu-id="cfb39-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="cfb39-107">Não há suporte para o Office 2010, o Office 2013 e outras versões do Office 2016.</span><span class="sxs-lookup"><span data-stu-id="cfb39-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="cfb39-108">A migração do Active Directory Rights Management Services (AD RMS) para a Proteção de Informações do Azure não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="cfb39-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="cfb39-109">Há suporte para o compartilhamento de emails protegidos com usuários na nuvem comercial.</span><span class="sxs-lookup"><span data-stu-id="cfb39-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="cfb39-110">O compartilhamento de documentos e anexos de email para usuários na nuvem comercial não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="cfb39-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="cfb39-111">Isso inclui usuários do Office 365 operados pela 21Vianet na nuvem comercial, usuários que não são operados pela 21Vianet na nuvem comercial e usuários com uma licença rmS para indivíduos.</span><span class="sxs-lookup"><span data-stu-id="cfb39-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="cfb39-112">O IRM com o SharePoint (bibliotecas e sites protegidos por IRM) não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="cfb39-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="cfb39-113">A extensão de dispositivo móvel para AD RMS não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="cfb39-113">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="cfb39-114">O [Visualizador Móvel](/azure/information-protection/rms-client/mobile-app-faq) não é suportado pelo Azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="cfb39-114">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="cfb39-115">Configurando a Proteção de Informações do Azure para clientes na China</span><span class="sxs-lookup"><span data-stu-id="cfb39-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="cfb39-116">Habilitar o Gerenciamento de Direitos para o locatário</span><span class="sxs-lookup"><span data-stu-id="cfb39-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="cfb39-117">Para que a criptografia funcione corretamente, o RMS deve estar habilitado para o locatário.</span><span class="sxs-lookup"><span data-stu-id="cfb39-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="cfb39-118">Verifique se o RMS está habilitado:</span><span class="sxs-lookup"><span data-stu-id="cfb39-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="cfb39-119">Iniciar o PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="cfb39-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="cfb39-120">Se o módulo AIPService não estiver instalado, `Install-Module AipService` execute.</span><span class="sxs-lookup"><span data-stu-id="cfb39-120">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="cfb39-121">Importe o módulo usando `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="cfb39-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="cfb39-122">Conecte-se ao serviço usando `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="cfb39-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="cfb39-123">Execute `(Get-AipServiceConfiguration).FunctionalState` e verifique se o estado é `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="cfb39-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="cfb39-124">Se o estado funcional for `Disabled` , execute `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="cfb39-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="cfb39-125">Configuração de DNS para criptografia (Windows)</span><span class="sxs-lookup"><span data-stu-id="cfb39-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="cfb39-126">Para que a criptografia funcione corretamente, os aplicativos cliente do Office devem se conectar à instância da China do serviço e inicializar a partir daí.</span><span class="sxs-lookup"><span data-stu-id="cfb39-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="cfb39-127">Para redirecionar aplicativos cliente para a instância de serviço correta, o administrador de locatários deve configurar um registro SRV dns com informações sobre a URL do Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="cfb39-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="cfb39-128">Sem o registro SRV de DNS, o aplicativo cliente tentará se conectar à instância de nuvem pública por padrão e falhará.</span><span class="sxs-lookup"><span data-stu-id="cfb39-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="cfb39-129">Além disso, a suposição é de que os usuários entrarão com um nome de usuário baseado no domínio de propriedade do locatário (por exemplo, ), e não com o nome de usuário `joe@contoso.cn` `onmschina` (por exemplo, `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="cfb39-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="cfb39-130">O nome de domínio do nome de usuário é usado para redirecionamento de DNS para a instância de serviço correta.</span><span class="sxs-lookup"><span data-stu-id="cfb39-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="cfb39-131">Obter a ID do RMS:</span><span class="sxs-lookup"><span data-stu-id="cfb39-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="cfb39-132">Iniciar o PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="cfb39-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="cfb39-133">Se o módulo AIPService não estiver instalado, `Install-Module AipService` execute.</span><span class="sxs-lookup"><span data-stu-id="cfb39-133">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="cfb39-134">Conecte-se ao serviço usando `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="cfb39-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="cfb39-135">Execute `(Get-AipServiceConfiguration).RightsManagementServiceId` para obter a ID do RMS.</span><span class="sxs-lookup"><span data-stu-id="cfb39-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="cfb39-136">Entre no provedor DNS, navegue até as configurações de DNS do domínio e adicione um novo registro SRV.</span><span class="sxs-lookup"><span data-stu-id="cfb39-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="cfb39-137">Serviço = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="cfb39-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="cfb39-138">Protocolo = `_http`</span><span class="sxs-lookup"><span data-stu-id="cfb39-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="cfb39-139">Nome = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="cfb39-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="cfb39-140">Target = `[GUID].rms.aadrm.cn` (onde GUID é a ID do RMS)</span><span class="sxs-lookup"><span data-stu-id="cfb39-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="cfb39-141">Prioridade, Peso, Segundos, TTL = valores padrão</span><span class="sxs-lookup"><span data-stu-id="cfb39-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="cfb39-142">Associe o domínio personalizado ao locatário no [portal do Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="cfb39-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="cfb39-143">Isso adicionará uma entrada no DNS, que pode levar vários minutos para ser verificada depois que você adicionar o valor às configurações de DNS.</span><span class="sxs-lookup"><span data-stu-id="cfb39-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="cfb39-144">Entre no centro de administração do Microsoft 365 com as credenciais de administrador global correspondentes e adicione o domínio (por exemplo, `contoso.cn` ) para criação do usuário.</span><span class="sxs-lookup"><span data-stu-id="cfb39-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="cfb39-145">No processo de verificação, alterações de DNS adicionais podem ser necessárias.</span><span class="sxs-lookup"><span data-stu-id="cfb39-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="cfb39-146">Quando a verificação for feita, os usuários poderão ser criados.</span><span class="sxs-lookup"><span data-stu-id="cfb39-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="cfb39-147">Configuração dns para criptografia (Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="cfb39-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

<span data-ttu-id="cfb39-148">Entre no provedor DNS, navegue até as configurações de DNS do domínio e adicione um novo registro SRV.</span><span class="sxs-lookup"><span data-stu-id="cfb39-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="cfb39-149">Serviço = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="cfb39-149">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="cfb39-150">Protocolo = `_http`</span><span class="sxs-lookup"><span data-stu-id="cfb39-150">Protocol = `_http`</span></span>
- <span data-ttu-id="cfb39-151">Nome = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="cfb39-151">Name = `_tcp`</span></span>
- <span data-ttu-id="cfb39-152">Destino = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="cfb39-152">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="cfb39-153">Porta = `80`</span><span class="sxs-lookup"><span data-stu-id="cfb39-153">Port = `80`</span></span>
- <span data-ttu-id="cfb39-154">Prioridade, Peso, Segundos, TTL = valores padrão</span><span class="sxs-lookup"><span data-stu-id="cfb39-154">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="aip-client-configuration"></a><span data-ttu-id="cfb39-155">Configuração do cliente AIP</span><span class="sxs-lookup"><span data-stu-id="cfb39-155">AIP client configuration</span></span>

<span data-ttu-id="cfb39-156">O cliente AIP unificado pode ser baixado do Centro [de Download da Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="cfb39-156">The unified AIP client can be downloaded from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="cfb39-157">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="cfb39-157">For more information, see:</span></span>

- [<span data-ttu-id="cfb39-158">Documentação da Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="cfb39-158">Azure Information Protection documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="cfb39-159">Histórico de versão do AIP e política de suporte</span><span class="sxs-lookup"><span data-stu-id="cfb39-159">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="cfb39-160">Requisitos do sistema AIP</span><span class="sxs-lookup"><span data-stu-id="cfb39-160">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="cfb39-161">Guia de início rápido do AIP: implantar o cliente AIP</span><span class="sxs-lookup"><span data-stu-id="cfb39-161">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="cfb39-162">Guia do administrador do AIP</span><span class="sxs-lookup"><span data-stu-id="cfb39-162">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="cfb39-163">Guia do usuário do AIP</span><span class="sxs-lookup"><span data-stu-id="cfb39-163">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="cfb39-164">Saiba mais sobre os rótulos de sensibilidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cfb39-164">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="aip-apps-configuration-unified-labeling-client-only"></a><span data-ttu-id="cfb39-165">Configuração de aplicativos AIP (apenas cliente de rotulagem unificada)</span><span class="sxs-lookup"><span data-stu-id="cfb39-165">AIP apps configuration (unified labeling client only)</span></span>

<span data-ttu-id="cfb39-166">Para a solução de rotulagem unificada, os aplicativos AIP no Windows precisam da seguinte chave do Registro para apontar para a nuvem soberana correta para o Azure China:</span><span class="sxs-lookup"><span data-stu-id="cfb39-166">For the unified labeling solution, AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="cfb39-167">Nó do Registro = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="cfb39-167">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="cfb39-168">Nome = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="cfb39-168">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="cfb39-169">Valor = `6` (padrão = 0)</span><span class="sxs-lookup"><span data-stu-id="cfb39-169">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="cfb39-170">Tipo = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="cfb39-170">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cfb39-171">Certifique-se de não excluir a chave do Registro após uma desinstalação.</span><span class="sxs-lookup"><span data-stu-id="cfb39-171">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="cfb39-172">Se a chave estiver vazia, incorreta ou inexistente, a funcionalidade se comportará como o valor padrão (valor padrão = 0 para a nuvem comercial).</span><span class="sxs-lookup"><span data-stu-id="cfb39-172">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="cfb39-173">Se a chave estiver vazia ou incorreta, um erro de impressão também será adicionado ao log.</span><span class="sxs-lookup"><span data-stu-id="cfb39-173">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="manage-azure-information-protection-content-scan-jobs"></a><span data-ttu-id="cfb39-174">Gerenciar trabalhos de verificação de conteúdo da Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="cfb39-174">Manage Azure Information Protection content scan jobs</span></span>

<span data-ttu-id="cfb39-175">Para gerenciar seus trabalhos de verificação de conteúdo da Proteção de Informações do Azure com um servidor de verificação do Azure China, use os seguintes cmdlets em vez do portal do Azure:</span><span class="sxs-lookup"><span data-stu-id="cfb39-175">To manage your Azure Information Protection content scan jobs with an Azure China scanner server, use the following cmdlets instead of the Azure portal:</span></span><br><br>

| <span data-ttu-id="cfb39-176">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="cfb39-176">Cmdlet</span></span> | <span data-ttu-id="cfb39-177">Descrição</span><span class="sxs-lookup"><span data-stu-id="cfb39-177">Description</span></span> |
|--|--|
| [<span data-ttu-id="cfb39-178">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="cfb39-178">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="cfb39-179">Adiciona um novo repositório ao seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="cfb39-179">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="cfb39-180">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="cfb39-180">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="cfb39-181">Obtém detalhes sobre seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="cfb39-181">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="cfb39-182">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="cfb39-182">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="cfb39-183">Obtém detalhes sobre repositórios definidos para seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="cfb39-183">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="cfb39-184">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="cfb39-184">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="cfb39-185">Exclui seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="cfb39-185">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="cfb39-186">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="cfb39-186">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="cfb39-187">Remove um repositório do trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="cfb39-187">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="cfb39-188">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="cfb39-188">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="cfb39-189">Define configurações para seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="cfb39-189">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="cfb39-190">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="cfb39-190">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="cfb39-191">Define configurações para um repositório existente em seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="cfb39-191">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="cfb39-192">Para obter mais informações, consulte [Gerenciar seus trabalhos de verificação de conteúdo usando apenas o PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="cfb39-192">For more information, see [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>