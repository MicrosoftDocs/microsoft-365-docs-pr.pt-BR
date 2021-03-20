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
ms.openlocfilehash: 77790249cbd544b2f11e9a16dd77bab297cac509
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914313"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="a4e26-103">Suporte à Proteção de Informações do Azure para o Office 365 operado pela 21Vianet</span><span class="sxs-lookup"><span data-stu-id="a4e26-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="a4e26-104">Este artigo aborda as diferenças entre o suporte à Proteção de Informações do Azure (AIP) para o Office 365 operado pela 21Vianet e ofertas comerciais, bem como instruções específicas para configurar a AIP para clientes na China, incluindo como instalar o scanner local do AIP e gerenciar trabalhos de verificação de &mdash; conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a4e26-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="a4e26-105">Diferenças entre a AIP para o Office 365 operado pela 21Vianet e ofertas comerciais</span><span class="sxs-lookup"><span data-stu-id="a4e26-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="a4e26-106">Embora nosso objetivo seja fornecer todos os recursos comerciais e funcionalidades aos clientes na China com nossa oferta AIP para Office 365 operado pela 21Vianet, há algumas funcionalidades ausentes que gostaria de destacar.</span><span class="sxs-lookup"><span data-stu-id="a4e26-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="a4e26-107">A lista a seguir inclui as lacunas existentes entre a AIP para o Office 365 operado pela 21Vianet e nossas ofertas comerciais a partir de janeiro de 2021:</span><span class="sxs-lookup"><span data-stu-id="a4e26-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="a4e26-108">O IRM (Gerenciamento de Direitos de Informação) só tem suporte para Aplicativos do Microsoft 365 para empresas (build 11731.10000 ou superior).</span><span class="sxs-lookup"><span data-stu-id="a4e26-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="a4e26-109">Não há suporte para Office 2010, Office 2013 e outras versões do Office 2016.</span><span class="sxs-lookup"><span data-stu-id="a4e26-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="a4e26-110">A migração Active Directory Rights Management Services (AD RMS) para a AIP não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="a4e26-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="a4e26-111">Há suporte para o compartilhamento de emails protegidos com usuários na nuvem comercial.</span><span class="sxs-lookup"><span data-stu-id="a4e26-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="a4e26-112">O compartilhamento de documentos e anexos de email com usuários na nuvem comercial não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="a4e26-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="a4e26-113">Isso inclui o Office 365 operado por usuários da 21Vianet na nuvem comercial, não o Office 365 operado por usuários da 21Vianet na nuvem comercial e usuários com uma licença RMS para Indivíduos.</span><span class="sxs-lookup"><span data-stu-id="a4e26-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="a4e26-114">O IRM com o SharePoint (sites e bibliotecas protegidos por IRM) não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="a4e26-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="a4e26-115">No momento, a Extensão de Dispositivo Móvel do AD RMS não está disponível.</span><span class="sxs-lookup"><span data-stu-id="a4e26-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="a4e26-116">O [Visualizador Móvel](/azure/information-protection/rms-client/mobile-app-faq) não é suportado pelo Azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="a4e26-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="a4e26-117">A área AIP do portal do Azure não está disponível para os clientes na China.</span><span class="sxs-lookup"><span data-stu-id="a4e26-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="a4e26-118">Use [comandos do PowerShell](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) em vez de executar ações no portal, como instalar o scanner local e gerenciar seus trabalhos de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a4e26-118">Use [PowerShell commands](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as installing the on-premises scanner and managing your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="a4e26-119">Configurar a AIP para clientes na China</span><span class="sxs-lookup"><span data-stu-id="a4e26-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="a4e26-120">Para configurar a AIP para clientes na China:</span><span class="sxs-lookup"><span data-stu-id="a4e26-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="a4e26-121">[Habilitar o Gerenciamento de Direitos para o locatário](#step-1-enable-rights-management-for-the-tenant).</span><span class="sxs-lookup"><span data-stu-id="a4e26-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="a4e26-122">[Configurar criptografia DNS](#step-2-configure-dns-encryption).</span><span class="sxs-lookup"><span data-stu-id="a4e26-122">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="a4e26-123">[Instale e configure o cliente de rotulagem unificada do AIP.](#step-3-install-and-configure-the-aip-unified-labeling-client)</span><span class="sxs-lookup"><span data-stu-id="a4e26-123">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="a4e26-124">[Configurar aplicativos AIP no Windows](#step-4-configure-aip-apps-on-windows).</span><span class="sxs-lookup"><span data-stu-id="a4e26-124">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="a4e26-125">[Instale o scanner local do AIP e gerencie trabalhos de verificação de conteúdo.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="a4e26-125">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="a4e26-126">Etapa 1: Habilitar o Gerenciamento de Direitos para o locatário</span><span class="sxs-lookup"><span data-stu-id="a4e26-126">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="a4e26-127">Para que a criptografia funcione corretamente, o RMS deve estar habilitado para o locatário.</span><span class="sxs-lookup"><span data-stu-id="a4e26-127">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="a4e26-128">Verifique se o RMS está habilitado:</span><span class="sxs-lookup"><span data-stu-id="a4e26-128">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="a4e26-129">Iniciar o PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="a4e26-129">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="a4e26-130">Se o módulo AIPService não estiver instalado, execute `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="a4e26-130">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="a4e26-131">Importar o módulo usando `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="a4e26-131">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="a4e26-132">Conecte-se ao serviço usando `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="a4e26-132">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="a4e26-133">Execute `(Get-AipServiceConfiguration).FunctionalState` e verifique se o estado é `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="a4e26-133">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="a4e26-134">Se o estado funcional for `Disabled` , execute `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="a4e26-134">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="a4e26-135">Etapa 2: Configurar criptografia DNS</span><span class="sxs-lookup"><span data-stu-id="a4e26-135">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="a4e26-136">Para que a criptografia funcione corretamente, os aplicativos cliente do Office devem se conectar à instância da China do serviço e inicializar a partir daí.</span><span class="sxs-lookup"><span data-stu-id="a4e26-136">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="a4e26-137">Para redirecionar aplicativos cliente para a instância de serviço correta, o administrador do locatário deve configurar um registro SRV DNS com informações sobre a URL do Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="a4e26-137">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="a4e26-138">Sem o registro SRV DNS, o aplicativo cliente tentará se conectar à instância de nuvem pública por padrão e falhará.</span><span class="sxs-lookup"><span data-stu-id="a4e26-138">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="a4e26-139">Além disso, a suposição é de que os usuários entrarão com um nome de usuário com base no domínio de propriedade do locatário (por exemplo), e não o nome de usuário `joe@contoso.cn` `onmschina` (por exemplo, `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="a4e26-139">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="a4e26-140">O nome de domínio do nome de usuário é usado para redirecionamento DNS para a instância de serviço correta.</span><span class="sxs-lookup"><span data-stu-id="a4e26-140">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="a4e26-141">Configurar criptografia DNS - Windows</span><span class="sxs-lookup"><span data-stu-id="a4e26-141">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="a4e26-142">Obter a ID do RMS:</span><span class="sxs-lookup"><span data-stu-id="a4e26-142">Get the RMS ID:</span></span>

    1. <span data-ttu-id="a4e26-143">Iniciar o PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="a4e26-143">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="a4e26-144">Se o módulo AIPService não estiver instalado, execute `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="a4e26-144">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="a4e26-145">Conecte-se ao serviço usando `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="a4e26-145">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="a4e26-146">Execute `(Get-AipServiceConfiguration).RightsManagementServiceId` para obter a ID do RMS.</span><span class="sxs-lookup"><span data-stu-id="a4e26-146">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="a4e26-147">Faça logoff no provedor DNS, navegue até as configurações DNS do domínio e adicione um novo registro SRV.</span><span class="sxs-lookup"><span data-stu-id="a4e26-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="a4e26-148">Serviço = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="a4e26-148">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="a4e26-149">Protocolo = `_http`</span><span class="sxs-lookup"><span data-stu-id="a4e26-149">Protocol = `_http`</span></span>
    - <span data-ttu-id="a4e26-150">Nome = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="a4e26-150">Name = `_tcp`</span></span>
    - <span data-ttu-id="a4e26-151">Target = `[GUID].rms.aadrm.cn` (onde GUID é a ID RMS)</span><span class="sxs-lookup"><span data-stu-id="a4e26-151">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="a4e26-152">Prioridade, Peso, Segundos, TTL = valores padrão</span><span class="sxs-lookup"><span data-stu-id="a4e26-152">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="a4e26-153">Associe o domínio personalizado ao locatário no [portal do Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="a4e26-153">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="a4e26-154">Isso adicionará uma entrada no DNS, que pode levar vários minutos para ser verificada depois que você adicionar o valor às configurações dns.</span><span class="sxs-lookup"><span data-stu-id="a4e26-154">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="a4e26-155">Faça logoff no Centro de administração do Microsoft 365 com as credenciais de administrador global correspondentes e adicione o domínio (por exemplo, `contoso.cn` ) para criação do usuário.</span><span class="sxs-lookup"><span data-stu-id="a4e26-155">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="a4e26-156">No processo de verificação, alterações de DNS adicionais podem ser necessárias.</span><span class="sxs-lookup"><span data-stu-id="a4e26-156">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="a4e26-157">Depois que a verificação for feita, os usuários poderão ser criados.</span><span class="sxs-lookup"><span data-stu-id="a4e26-157">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="a4e26-158">Configurar criptografia DNS - Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="a4e26-158">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="a4e26-159">Faça logoff no provedor DNS, navegue até as configurações DNS do domínio e adicione um novo registro SRV.</span><span class="sxs-lookup"><span data-stu-id="a4e26-159">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="a4e26-160">Serviço = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="a4e26-160">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="a4e26-161">Protocolo = `_http`</span><span class="sxs-lookup"><span data-stu-id="a4e26-161">Protocol = `_http`</span></span>
- <span data-ttu-id="a4e26-162">Nome = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="a4e26-162">Name = `_tcp`</span></span>
- <span data-ttu-id="a4e26-163">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="a4e26-163">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="a4e26-164">Porta = `80`</span><span class="sxs-lookup"><span data-stu-id="a4e26-164">Port = `80`</span></span>
- <span data-ttu-id="a4e26-165">Prioridade, Peso, Segundos, TTL = valores padrão</span><span class="sxs-lookup"><span data-stu-id="a4e26-165">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="a4e26-166">Etapa 3: Instalar e configurar o cliente de rotulagem unificada do AIP</span><span class="sxs-lookup"><span data-stu-id="a4e26-166">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="a4e26-167">Baixe o cliente de rotulagem unificada do AIP no [Centro de Download da Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="a4e26-167">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="a4e26-168">Para mais informações, confira:</span><span class="sxs-lookup"><span data-stu-id="a4e26-168">For more information, see:</span></span>

- [<span data-ttu-id="a4e26-169">Documentação do AIP</span><span class="sxs-lookup"><span data-stu-id="a4e26-169">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="a4e26-170">Política de suporte e histórico de versão do AIP</span><span class="sxs-lookup"><span data-stu-id="a4e26-170">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="a4e26-171">Requisitos do sistema AIP</span><span class="sxs-lookup"><span data-stu-id="a4e26-171">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="a4e26-172">Início rápido da AIP: Implantar o cliente AIP</span><span class="sxs-lookup"><span data-stu-id="a4e26-172">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="a4e26-173">Guia de administrador do AIP</span><span class="sxs-lookup"><span data-stu-id="a4e26-173">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="a4e26-174">Guia do usuário AIP</span><span class="sxs-lookup"><span data-stu-id="a4e26-174">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="a4e26-175">Saiba mais sobre rótulos de sensibilidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a4e26-175">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="a4e26-176">Etapa 4: Configurar aplicativos AIP no Windows</span><span class="sxs-lookup"><span data-stu-id="a4e26-176">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="a4e26-177">Os aplicativos AIP no Windows precisam da seguinte chave do Registro para apontar para a nuvem soberana correta para o Azure China:</span><span class="sxs-lookup"><span data-stu-id="a4e26-177">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="a4e26-178">Nó do Registro = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="a4e26-178">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="a4e26-179">Nome = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="a4e26-179">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="a4e26-180">Valor = `6` (padrão = 0)</span><span class="sxs-lookup"><span data-stu-id="a4e26-180">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="a4e26-181">Tipo = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="a4e26-181">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4e26-182">Certifique-se de não excluir a chave do Registro após uma desinstalação.</span><span class="sxs-lookup"><span data-stu-id="a4e26-182">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="a4e26-183">Se a chave estiver vazia, incorreta ou não existente, a funcionalidade se comportará como o valor padrão (valor padrão = 0 para a nuvem comercial).</span><span class="sxs-lookup"><span data-stu-id="a4e26-183">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="a4e26-184">Se a chave estiver vazia ou incorreta, um erro de impressão também será adicionado ao log.</span><span class="sxs-lookup"><span data-stu-id="a4e26-184">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="a4e26-185">Etapa 5: instalar o scanner local do AIP e gerenciar trabalhos de verificação de conteúdo</span><span class="sxs-lookup"><span data-stu-id="a4e26-185">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="a4e26-186">Instale o scanner local do AIP para verificar seus compartilhamentos de rede e conteúdo para dados confidenciais e aplicar rótulos de classificação e proteção conforme configurado na política da sua organização.</span><span class="sxs-lookup"><span data-stu-id="a4e26-186">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="a4e26-187">Ao instalar o scanner e gerenciar seus trabalhos de verificação de conteúdo, use os seguintes cmdlets em vez da interface do portal do Azure usada pelas ofertas comerciais:</span><span class="sxs-lookup"><span data-stu-id="a4e26-187">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

| <span data-ttu-id="a4e26-188">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a4e26-188">Cmdlet</span></span> | <span data-ttu-id="a4e26-189">Descrição</span><span class="sxs-lookup"><span data-stu-id="a4e26-189">Description</span></span> |
|--|--|
| [<span data-ttu-id="a4e26-190">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="a4e26-190">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="a4e26-191">Adiciona um novo repositório ao trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a4e26-191">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="a4e26-192">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="a4e26-192">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="a4e26-193">Obtém detalhes sobre seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a4e26-193">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="a4e26-194">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="a4e26-194">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="a4e26-195">Obtém detalhes sobre repositórios definidos para seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a4e26-195">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="a4e26-196">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="a4e26-196">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="a4e26-197">Exclui seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a4e26-197">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="a4e26-198">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="a4e26-198">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="a4e26-199">Remove um repositório do trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a4e26-199">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="a4e26-200">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="a4e26-200">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="a4e26-201">Define configurações para seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a4e26-201">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="a4e26-202">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="a4e26-202">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="a4e26-203">Define configurações para um repositório existente em seu trabalho de verificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a4e26-203">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="a4e26-204">Para obter mais informações, consulte O que é o scanner unificado de rotulagem da Proteção de Informações do [Azure?](/azure/information-protection/deploy-aip-scanner) e Gerenciar seus trabalhos de verificação de conteúdo usando apenas [o PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span><span class="sxs-lookup"><span data-stu-id="a4e26-204">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>