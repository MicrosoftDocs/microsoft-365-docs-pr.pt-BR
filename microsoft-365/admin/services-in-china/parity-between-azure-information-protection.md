---
title: Office 365 operado pela 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: mnirkhe
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- MET150
- GEU150
- GEA150
description: Saiba mais sobre o Azure Information Protection para Office 365 operado pela 21Vianet e como configurá-lo para os clientes da China.
monikerRange: o365-21vianet
ms.openlocfilehash: 3d24b450cc9ba9a6427732d408e35af1394b4a34
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627649"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="05f60-103">Paridade entre a proteção de informações do Azure para Office 365 operado pela 21Vianet e ofertas comerciais</span><span class="sxs-lookup"><span data-stu-id="05f60-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="05f60-104">Enquanto o nosso objetivo é fornecer todos os recursos e funcionalidades comerciais aos clientes da China com nossa proteção de informações do Azure para Office 365 operado pela 21Vianet, há algumas funcionalidades que gostaríamos de destacar.</span><span class="sxs-lookup"><span data-stu-id="05f60-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="05f60-105">Essas são as lacunas existentes entre a proteção de informações do Azure para Office 365 operado pela 21Vianet e nossas ofertas comerciais a partir de julho de 2019:</span><span class="sxs-lookup"><span data-stu-id="05f60-105">These are the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="05f60-106">O gerenciamento de direitos de informação (IRM) é suportado somente para o Microsoft 365 aplicativos para empresas (Build 11731,10000 ou posterior).</span><span class="sxs-lookup"><span data-stu-id="05f60-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="05f60-107">O Office 2010, o Office 2013 e outras versões do Office 2016 não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="05f60-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="05f60-108">A migração do Active Directory Rights Management Services (AD RMS) para a proteção de informações do Azure não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="05f60-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="05f60-109">Há suporte para o compartilhamento de emails protegidos para os usuários na nuvem comercial.</span><span class="sxs-lookup"><span data-stu-id="05f60-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="05f60-110">O compartilhamento de documentos e anexos de email para usuários na nuvem comercial não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="05f60-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="05f60-111">Isso inclui o Office 365 operado pela 21Vianet Users na nuvem comercial, não-Office 365 operado pela 21Vianet Users na nuvem comercial e usuários com um RMS para licença de pessoas.</span><span class="sxs-lookup"><span data-stu-id="05f60-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="05f60-112">O IRM com o SharePoint (sites e bibliotecas protegidas por IRM) não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="05f60-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="05f60-113">O conector de gerenciamento de direitos não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="05f60-113">The Rights Management Connector is currently not available.</span></span>
  
- <span data-ttu-id="05f60-114">A extensão do dispositivo móvel para AD RMS não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="05f60-114">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="05f60-115">Configurando a proteção de informações do Azure para clientes na China</span><span class="sxs-lookup"><span data-stu-id="05f60-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="05f60-116">Habilitar o gerenciamento de direitos para o locatário</span><span class="sxs-lookup"><span data-stu-id="05f60-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="05f60-117">Para que a criptografia funcione corretamente, o RMS deve estar habilitado para o locatário.</span><span class="sxs-lookup"><span data-stu-id="05f60-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="05f60-118">Verifique se o RMS está habilitado:</span><span class="sxs-lookup"><span data-stu-id="05f60-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="05f60-119">Inicie o PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="05f60-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="05f60-120">Se o módulo AIPService não estiver instalado, execute `Install-Module AipService`.</span><span class="sxs-lookup"><span data-stu-id="05f60-120">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="05f60-121">Importe o módulo usando `Import-Module AipService`o.</span><span class="sxs-lookup"><span data-stu-id="05f60-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="05f60-122">Conecte-se ao serviço `Connect-AipService -environmentname azurechinacloud`usando.</span><span class="sxs-lookup"><span data-stu-id="05f60-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="05f60-123">Executar `(Get-AipServiceConfiguration).FunctionalState` e verificar se o estado é `Enabled`.</span><span class="sxs-lookup"><span data-stu-id="05f60-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="05f60-124">Se o estado funcional for `Disabled`, execute `Enable-AipService`.</span><span class="sxs-lookup"><span data-stu-id="05f60-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="05f60-125">Configuração de DNS para criptografia (Windows)</span><span class="sxs-lookup"><span data-stu-id="05f60-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="05f60-126">Para que a criptografia funcione corretamente, os aplicativos clientes do Office devem se conectar à instância da China do serviço e inicializar a partir daí.</span><span class="sxs-lookup"><span data-stu-id="05f60-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="05f60-127">Para redirecionar aplicativos cliente para a instância de serviço correta, o administrador de locatários deve configurar um registro SRV de DNS com informações sobre a URL do Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="05f60-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="05f60-128">Sem o registro SRV do DNS, o aplicativo cliente tentará se conectar à instância da nuvem pública por padrão e falhará.</span><span class="sxs-lookup"><span data-stu-id="05f60-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="05f60-129">Além disso, a pressuposição é que os usuários farão logon com um nome de usuário com base no domínio de Propriedade do `joe@contoso.cn`locatário (por exemplo, `onmschina` ) e não no nome `joe@contoso.onmschina.cn`de usuário (por exemplo,).</span><span class="sxs-lookup"><span data-stu-id="05f60-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="05f60-130">O nome de domínio do nome de usuário é usado para o redirecionamento de DNS para a instância de serviço correta.</span><span class="sxs-lookup"><span data-stu-id="05f60-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="05f60-131">Obter a ID do RMS:</span><span class="sxs-lookup"><span data-stu-id="05f60-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="05f60-132">Inicie o PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="05f60-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="05f60-133">Se o módulo AIPService não estiver instalado, execute `Install-Module AipService`.</span><span class="sxs-lookup"><span data-stu-id="05f60-133">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="05f60-134">Conecte-se ao serviço `Connect-AipService -environmentname azurechinacloud`usando.</span><span class="sxs-lookup"><span data-stu-id="05f60-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="05f60-135">Execute `(Get-AipServiceConfiguration).RightsManagementServiceId` para obter a ID do RMS.</span><span class="sxs-lookup"><span data-stu-id="05f60-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="05f60-136">Faça logon no seu provedor de DNS, navegue até as configurações de DNS para o domínio e, em seguida, adicione um novo registro SRV.</span><span class="sxs-lookup"><span data-stu-id="05f60-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="05f60-137">Serviço = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="05f60-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="05f60-138">Protocolo = `_http`</span><span class="sxs-lookup"><span data-stu-id="05f60-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="05f60-139">Nome = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="05f60-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="05f60-140">Target = `[GUID].rms.aadrm.cn` (onde GUID é a ID do RMS)</span><span class="sxs-lookup"><span data-stu-id="05f60-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="05f60-141">Prioridade, peso, segundos, TTL = valores padrão</span><span class="sxs-lookup"><span data-stu-id="05f60-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="05f60-142">Associe o domínio personalizado ao locatário no [portal do Azure](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span><span class="sxs-lookup"><span data-stu-id="05f60-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="05f60-143">Isso adicionará uma entrada no DNS, que pode levar alguns minutos para ser verificada depois que você adicionar o valor às configurações de DNS.</span><span class="sxs-lookup"><span data-stu-id="05f60-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="05f60-144">Faça logon no centro de administração do Microsoft 365 com as credenciais de administrador global correspondentes e adicione o domínio (por `contoso.cn`exemplo,) para a criação de usuários.</span><span class="sxs-lookup"><span data-stu-id="05f60-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="05f60-145">No processo de verificação, alterações adicionais de DNS podem ser necessárias.</span><span class="sxs-lookup"><span data-stu-id="05f60-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="05f60-146">Após a verificação ser concluída, os usuários podem ser criados.</span><span class="sxs-lookup"><span data-stu-id="05f60-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="05f60-147">Configuração de DNS para criptografia (Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="05f60-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="05f60-148">Faça logon no seu provedor de DNS, navegue até as configurações de DNS para o domínio e, em seguida, adicione um novo registro SRV.</span><span class="sxs-lookup"><span data-stu-id="05f60-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="05f60-149">Serviço = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="05f60-149">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="05f60-150">Protocolo = `_http`</span><span class="sxs-lookup"><span data-stu-id="05f60-150">Protocol = `_http`</span></span>
  - <span data-ttu-id="05f60-151">Nome = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="05f60-151">Name = `_tcp`</span></span>
  - <span data-ttu-id="05f60-152">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="05f60-152">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="05f60-153">Porta = `80`</span><span class="sxs-lookup"><span data-stu-id="05f60-153">Port = `80`</span></span>
  - <span data-ttu-id="05f60-154">Prioridade, peso, segundos, TTL = valores padrão</span><span class="sxs-lookup"><span data-stu-id="05f60-154">Priority, Weight, Seconds, TTL = default values</span></span>
