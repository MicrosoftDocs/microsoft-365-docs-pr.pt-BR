---
title: Suporte à Proteção de Informações do Azure para o Office 365 operado pela 21Vianet
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
description: Saiba mais sobre a Proteção de Informações do Azure (AIP) para o Office 365 operado pela 21Vianet e como configurá-la para clientes na China.
monikerRange: o365-21vianet
ms.openlocfilehash: cee50384587ffc3e1e43eb9c6bb07d2e0ced7e13
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988039"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="e14a4-103">Suporte à Proteção de Informações do Azure para o Office 365 operado pela 21Vianet</span><span class="sxs-lookup"><span data-stu-id="e14a4-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="e14a4-104">Este artigo aborda as diferenças entre o suporte à Proteção de Informações do Azure (AIP) para o Office 365 operado pela 21Vianet e ofertas comerciais, bem como instruções específicas para configurar o AIP para clientes na China, incluindo como instalar o scanner local do AIP e gerenciar trabalhos de verificação de &mdash; conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e14a4-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="e14a4-105">Diferenças entre o AIP para o Office 365 operado pela 21Vianet e as ofertas comerciais</span><span class="sxs-lookup"><span data-stu-id="e14a4-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="e14a4-106">Embora nosso objetivo seja fornecer todos os recursos comerciais e funcionalidades aos clientes na China com nosso AIP para o Office 365 operado pela 21Vianet, há algumas funcionalidades ausentes que queremos destacar.</span><span class="sxs-lookup"><span data-stu-id="e14a4-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="e14a4-107">A lista a seguir inclui as lacunas existentes entre o AIP para o Office 365 operado pela 21Vianet e nossas ofertas comerciais a partir de janeiro de 2021:</span><span class="sxs-lookup"><span data-stu-id="e14a4-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="e14a4-108">O Gerenciamento de Direitos de Informação (IRM) tem suporte apenas para o Microsoft 365 Apps para empresas (build 11731.10000 ou superior).</span><span class="sxs-lookup"><span data-stu-id="e14a4-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="e14a4-109">Não há suporte para o Office 2010, o Office 2013 e outras versões do Office 2016.</span><span class="sxs-lookup"><span data-stu-id="e14a4-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="e14a4-110">A migração do Active Directory Rights Management Services (AD RMS) para o AIP não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="e14a4-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="e14a4-111">Há suporte para o compartilhamento de emails protegidos com usuários na nuvem comercial.</span><span class="sxs-lookup"><span data-stu-id="e14a4-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="e14a4-112">O compartilhamento de documentos e anexos de email com usuários na nuvem comercial não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="e14a4-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="e14a4-113">Isso inclui usuários do Office 365 operados pela 21Vianet na nuvem comercial, usuários que não são operados pela 21Vianet na nuvem comercial e usuários com uma licença rmS para indivíduos.</span><span class="sxs-lookup"><span data-stu-id="e14a4-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="e14a4-114">O IRM com o SharePoint (bibliotecas e sites protegidos por IRM) não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="e14a4-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="e14a4-115">A Extensão de Dispositivo Móvel para AD RMS não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="e14a4-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="e14a4-116">O [Visualizador Móvel](/azure/information-protection/rms-client/mobile-app-faq) não é suportado pelo Azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="e14a4-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="e14a4-117">Configurar o AIP para clientes na China</span><span class="sxs-lookup"><span data-stu-id="e14a4-117">Configure AIP for customers in China</span></span>

<span data-ttu-id="e14a4-118">Para configurar o AIP para clientes na China:</span><span class="sxs-lookup"><span data-stu-id="e14a4-118">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="e14a4-119">[Habilitar o Gerenciamento de Direitos para o locatário.](#step-1-enable-rights-management-for-the-tenant)</span><span class="sxs-lookup"><span data-stu-id="e14a4-119">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="e14a4-120">[Configurar criptografia DNS.](#step-2-configure-dns-encryption)</span><span class="sxs-lookup"><span data-stu-id="e14a4-120">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="e14a4-121">[Instale e configure o cliente de rotulagem unificada do AIP.](#step-3-install-and-configure-the-aip-unified-labeling-client)</span><span class="sxs-lookup"><span data-stu-id="e14a4-121">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="e14a4-122">[Configurar aplicativos AIP no Windows.](#step-4-configure-aip-apps-on-windows)</span><span class="sxs-lookup"><span data-stu-id="e14a4-122">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="e14a4-123">[Instale o scanner local do AIP e gerencie trabalhos de verificação de conteúdo.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="e14a4-123">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="e14a4-124">Etapa 1: Habilitar o Gerenciamento de Direitos para o locatário</span><span class="sxs-lookup"><span data-stu-id="e14a4-124">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="e14a4-125">Para que a criptografia funcione corretamente, o RMS deve estar habilitado para o locatário.</span><span class="sxs-lookup"><span data-stu-id="e14a4-125">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="e14a4-126">Verifique se o RMS está habilitado:</span><span class="sxs-lookup"><span data-stu-id="e14a4-126">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="e14a4-127">Iniciar o PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="e14a4-127">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="e14a4-128">Se o módulo AIPService não estiver instalado, `Install-Module AipService` execute.</span><span class="sxs-lookup"><span data-stu-id="e14a4-128">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="e14a4-129">Importe o módulo usando `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="e14a4-129">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="e14a4-130">Conecte-se ao serviço usando `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="e14a4-130">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="e14a4-131">Execute `(Get-AipServiceConfiguration).FunctionalState` e verifique se o estado é `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="e14a4-131">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="e14a4-132">Se o estado funcional for `Disabled` , execute `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="e14a4-132">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="e14a4-133">Etapa 2: Configurar a criptografia DNS</span><span class="sxs-lookup"><span data-stu-id="e14a4-133">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="e14a4-134">Para que a criptografia funcione corretamente, os aplicativos cliente do Office devem se conectar à instância da China do serviço e inicializar a partir daí.</span><span class="sxs-lookup"><span data-stu-id="e14a4-134">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="e14a4-135">Para redirecionar aplicativos cliente para a instância de serviço correta, o administrador de locatários deve configurar um registro SRV dns com informações sobre a URL do Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="e14a4-135">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="e14a4-136">Sem o registro SRV de DNS, o aplicativo cliente tentará se conectar à instância de nuvem pública por padrão e falhará.</span><span class="sxs-lookup"><span data-stu-id="e14a4-136">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="e14a4-137">Além disso, a suposição é de que os usuários entrarão com um nome de usuário baseado no domínio de propriedade do locatário (por exemplo, ), e não com o nome de usuário `joe@contoso.cn` `onmschina` (por exemplo, `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="e14a4-137">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="e14a4-138">O nome de domínio do nome de usuário é usado para redirecionamento de DNS para a instância de serviço correta.</span><span class="sxs-lookup"><span data-stu-id="e14a4-138">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="e14a4-139">Configurar criptografia DNS - Windows</span><span class="sxs-lookup"><span data-stu-id="e14a4-139">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="e14a4-140">Obter a ID do RMS:</span><span class="sxs-lookup"><span data-stu-id="e14a4-140">Get the RMS ID:</span></span>

    1. <span data-ttu-id="e14a4-141">Iniciar o PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="e14a4-141">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="e14a4-142">Se o módulo AIPService não estiver instalado, `Install-Module AipService` execute.</span><span class="sxs-lookup"><span data-stu-id="e14a4-142">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="e14a4-143">Conecte-se ao serviço usando `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="e14a4-143">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="e14a4-144">Execute `(Get-AipServiceConfiguration).RightsManagementServiceId` para obter a ID do RMS.</span><span class="sxs-lookup"><span data-stu-id="e14a4-144">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="e14a4-145">Entre no provedor DNS, navegue até as configurações de DNS do domínio e adicione um novo registro SRV.</span><span class="sxs-lookup"><span data-stu-id="e14a4-145">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="e14a4-146">Serviço = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="e14a4-146">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="e14a4-147">Protocolo = `_http`</span><span class="sxs-lookup"><span data-stu-id="e14a4-147">Protocol = `_http`</span></span>
    - <span data-ttu-id="e14a4-148">Nome = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="e14a4-148">Name = `_tcp`</span></span>
    - <span data-ttu-id="e14a4-149">Target = `[GUID].rms.aadrm.cn` (onde GUID é a ID do RMS)</span><span class="sxs-lookup"><span data-stu-id="e14a4-149">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="e14a4-150">Prioridade, Peso, Segundos, TTL = valores padrão</span><span class="sxs-lookup"><span data-stu-id="e14a4-150">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="e14a4-151">Associe o domínio personalizado ao locatário no [portal do Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="e14a4-151">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="e14a4-152">Isso adicionará uma entrada no DNS, que pode levar vários minutos para ser verificada depois que você adicionar o valor às configurações de DNS.</span><span class="sxs-lookup"><span data-stu-id="e14a4-152">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="e14a4-153">Entre no centro de administração do Microsoft 365 com as credenciais de administrador global correspondentes e adicione o domínio (por exemplo, `contoso.cn` ) para criação do usuário.</span><span class="sxs-lookup"><span data-stu-id="e14a4-153">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="e14a4-154">No processo de verificação, alterações de DNS adicionais podem ser necessárias.</span><span class="sxs-lookup"><span data-stu-id="e14a4-154">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="e14a4-155">Depois que a verificação é feita, os usuários podem ser criados.</span><span class="sxs-lookup"><span data-stu-id="e14a4-155">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="e14a4-156">Configurar criptografia DNS - Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="e14a4-156">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="e14a4-157">Entre no provedor DNS, navegue até as configurações de DNS do domínio e adicione um novo registro SRV.</span><span class="sxs-lookup"><span data-stu-id="e14a4-157">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="e14a4-158">Serviço = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="e14a4-158">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="e14a4-159">Protocolo = `_http`</span><span class="sxs-lookup"><span data-stu-id="e14a4-159">Protocol = `_http`</span></span>
- <span data-ttu-id="e14a4-160">Nome = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="e14a4-160">Name = `_tcp`</span></span>
- <span data-ttu-id="e14a4-161">Destino = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="e14a4-161">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="e14a4-162">Porta = `80`</span><span class="sxs-lookup"><span data-stu-id="e14a4-162">Port = `80`</span></span>
- <span data-ttu-id="e14a4-163">Prioridade, Peso, Segundos, TTL = valores padrão</span><span class="sxs-lookup"><span data-stu-id="e14a4-163">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="e14a4-164">Etapa 3: Instalar e configurar o cliente de rotulagem unificada do AIP</span><span class="sxs-lookup"><span data-stu-id="e14a4-164">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="e14a4-165">Baixe o cliente de rotulagem unificada do AIP do Centro [de Download da Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="e14a4-165">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="e14a4-166">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="e14a4-166">For more information, see:</span></span>

- [<span data-ttu-id="e14a4-167">Documentação do AIP</span><span class="sxs-lookup"><span data-stu-id="e14a4-167">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="e14a4-168">Histórico de versão do AIP e política de suporte</span><span class="sxs-lookup"><span data-stu-id="e14a4-168">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="e14a4-169">Requisitos do sistema AIP</span><span class="sxs-lookup"><span data-stu-id="e14a4-169">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="e14a4-170">Guia de início rápido do AIP: implantar o cliente AIP</span><span class="sxs-lookup"><span data-stu-id="e14a4-170">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="e14a4-171">Guia do administrador do AIP</span><span class="sxs-lookup"><span data-stu-id="e14a4-171">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="e14a4-172">Guia do usuário do AIP</span><span class="sxs-lookup"><span data-stu-id="e14a4-172">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="e14a4-173">Saiba mais sobre os rótulos de sensibilidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e14a4-173">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="e14a4-174">Etapa 4: Configurar aplicativos AIP no Windows</span><span class="sxs-lookup"><span data-stu-id="e14a4-174">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="e14a4-175">Os aplicativos AIP no Windows precisam da seguinte chave do Registro para apontar para a nuvem soberana correta para o Azure China:</span><span class="sxs-lookup"><span data-stu-id="e14a4-175">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="e14a4-176">Nó do Registro = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="e14a4-176">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="e14a4-177">Nome = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="e14a4-177">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="e14a4-178">Valor = `6` (padrão = 0)</span><span class="sxs-lookup"><span data-stu-id="e14a4-178">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="e14a4-179">Tipo = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="e14a4-179">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e14a4-180">Certifique-se de não excluir a chave do Registro após uma desinstalação.</span><span class="sxs-lookup"><span data-stu-id="e14a4-180">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="e14a4-181">Se a chave estiver vazia, incorreta ou inexistente, a funcionalidade se comportará como o valor padrão (valor padrão = 0 para a nuvem comercial).</span><span class="sxs-lookup"><span data-stu-id="e14a4-181">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="e14a4-182">Se a chave estiver vazia ou incorreta, um erro de impressão também será adicionado ao log.</span><span class="sxs-lookup"><span data-stu-id="e14a4-182">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="e14a4-183">Etapa 5: instalar o scanner local do AIP e gerenciar trabalhos de verificação de conteúdo</span><span class="sxs-lookup"><span data-stu-id="e14a4-183">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="e14a4-184">Instale o scanner local do AIP para verificar se há dados confidenciais nos compartilhamentos de rede e conteúdo e aplique rótulos de classificação e proteção conforme configurado na política da sua organização.</span><span class="sxs-lookup"><span data-stu-id="e14a4-184">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="e14a4-185">Ao instalar o scanner e gerenciar seus trabalhos de verificação de conteúdo, use os seguintes cmdlets em vez da interface do portal do Azure usada pelas ofertas comerciais:</span><span class="sxs-lookup"><span data-stu-id="e14a4-185">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

| <span data-ttu-id="e14a4-186">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e14a4-186">Cmdlet</span></span> | <span data-ttu-id="e14a4-187">Descrição</span><span class="sxs-lookup"><span data-stu-id="e14a4-187">Description</span></span> |
|--|--|
| [<span data-ttu-id="e14a4-188">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="e14a4-188">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="e14a4-189">Adiciona um novo repositório ao trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e14a4-189">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="e14a4-190">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="e14a4-190">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="e14a4-191">Obtém detalhes sobre seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e14a4-191">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="e14a4-192">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="e14a4-192">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="e14a4-193">Obtém detalhes sobre repositórios definidos para seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e14a4-193">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="e14a4-194">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="e14a4-194">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="e14a4-195">Exclui seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e14a4-195">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="e14a4-196">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="e14a4-196">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="e14a4-197">Remove um repositório do trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e14a4-197">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="e14a4-198">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="e14a4-198">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="e14a4-199">Define configurações para seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e14a4-199">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="e14a4-200">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="e14a4-200">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="e14a4-201">Define configurações para um repositório existente em seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e14a4-201">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="e14a4-202">Para saber mais, confira O que é o scanner de rotulagem unificado da Proteção de Informações do [Azure?](/azure/information-protection/deploy-aip-scanner) e Gerencie seus trabalhos de verificação de conteúdo usando apenas [o PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="e14a4-202">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>