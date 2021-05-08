---
title: Como configurar o Exchange Server no local para usar a autenticação moderna híbrida
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Saiba como configurar um Exchange Server local para usar a Autenticação Moderna HÍbrida (HMA), oferecendo a você uma autenticação e autorização de usuário mais seguras.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9cb6d25a346ac48c9875a26f385cb733f1ff051f
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259446"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="fc994-103">Como configurar o Exchange Server no local para usar a autenticação moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="fc994-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="fc994-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="fc994-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fc994-105">A Autenticação Moderna HÍbrida (HMA) é um método de gerenciamento de identidade que oferece autenticação e autorização de usuário mais seguras e está disponível para implantações híbridas Exchange servidor local.</span><span class="sxs-lookup"><span data-stu-id="fc994-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="fc994-106">FYI</span><span class="sxs-lookup"><span data-stu-id="fc994-106">FYI</span></span>

<span data-ttu-id="fc994-107">Antes de começar, eu chamarei:</span><span class="sxs-lookup"><span data-stu-id="fc994-107">Before we begin, I call:</span></span>

- <span data-ttu-id="fc994-108">HMA de autenticação \> moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="fc994-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="fc994-109">Exchange \> EXCH local</span><span class="sxs-lookup"><span data-stu-id="fc994-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="fc994-110">\>Exchange Online EXO</span><span class="sxs-lookup"><span data-stu-id="fc994-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="fc994-111">Além disso, se um gráfico neste artigo tiver um objeto que seja "esmaecida" ou "esmaecida", isso significa que o elemento mostrado em cinza não está incluído na configuração específica do *HMA.*</span><span class="sxs-lookup"><span data-stu-id="fc994-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="fc994-112">Habilitando a autenticação moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="fc994-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="fc994-113">A ação do HMA significa:</span><span class="sxs-lookup"><span data-stu-id="fc994-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="fc994-114">Certifique-se de atender aos pré-requisitos antes de começar.</span><span class="sxs-lookup"><span data-stu-id="fc994-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="fc994-115">Como muitos **pré-requisitos** são comuns para Skype for Business e Exchange, a visão geral da Autenticação Moderna Híbrida e os pré-requisitos para [usá-lo](hybrid-modern-auth-overview.md)com servidores Skype for Business e Exchange locais.</span><span class="sxs-lookup"><span data-stu-id="fc994-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="fc994-116">Faça isso antes de começar qualquer uma das etapas deste artigo.</span><span class="sxs-lookup"><span data-stu-id="fc994-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="fc994-117">Adicionando URLs do serviço Web local como **SPNs (Service Principal Names)** no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fc994-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span> <span data-ttu-id="fc994-118">Caso o EXCH seja híbrido com vários **locatários,** essas URLs do serviço Web local devem ser adicionadas como SPNs no Azure AD de todos os locatários que estão híbridos com o EXCH.</span><span class="sxs-lookup"><span data-stu-id="fc994-118">In case EXCH is in hybrid with **multiple tenants**, these on-premises web service URLs must be added as SPNs in the Azure AD of all the tenants which are in hybrid with EXCH.</span></span>

1. <span data-ttu-id="fc994-119">Garantir que todos os Diretórios Virtuais sejam habilitados para HMA</span><span class="sxs-lookup"><span data-stu-id="fc994-119">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="fc994-120">Verificando o objeto EvoSTS Auth Server</span><span class="sxs-lookup"><span data-stu-id="fc994-120">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="fc994-121">Habilitando o HMA no EXCH.</span><span class="sxs-lookup"><span data-stu-id="fc994-121">Enabling HMA in EXCH.</span></span>

> [!NOTE]
> <span data-ttu-id="fc994-122">Sua versão do Office suporta MA?</span><span class="sxs-lookup"><span data-stu-id="fc994-122">Does your version of Office support MA?</span></span> <span data-ttu-id="fc994-123">Consulte [Como a autenticação moderna funciona para Office 2013 e Office aplicativos cliente 2016.](modern-auth-for-office-2013-and-2016.md)</span><span class="sxs-lookup"><span data-stu-id="fc994-123">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>


## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="fc994-124">Certifique-se de atender a todos os pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="fc994-124">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="fc994-125">Como muitos pré-requisitos são comuns para o Skype for Business e o Exchange, revise a visão geral da Autenticação Moderna Híbrida e os [pré-requisitos para usá-lo](hybrid-modern-auth-overview.md)com servidores Skype for Business e Exchange locais.</span><span class="sxs-lookup"><span data-stu-id="fc994-125">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="fc994-126">Faça isso  *antes*  de começar qualquer uma das etapas deste artigo.</span><span class="sxs-lookup"><span data-stu-id="fc994-126">Do this  *before*  you begin any of the steps in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="fc994-127">Outlook Web App e Exchange painel de controle não funciona com autenticação moderna híbrida.</span><span class="sxs-lookup"><span data-stu-id="fc994-127">Outlook Web App and Exchange Control Panel does not work with hybrid Modern Authentication.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="fc994-128">Adicionar URLs de serviço Web locais como SPNs no Azure AD</span><span class="sxs-lookup"><span data-stu-id="fc994-128">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="fc994-129">Execute os comandos que atribuem as URLs do serviço Web local como SPNs do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fc994-129">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="fc994-130">Os SPNs são usados por máquinas e dispositivos cliente durante a autenticação e a autorização.</span><span class="sxs-lookup"><span data-stu-id="fc994-130">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="fc994-131">Todas as URLs que podem ser usadas para se conectar do local ao Azure Active Directory (Azure AD) devem ser registradas no Azure AD (isso inclui namespaces internos e externos).</span><span class="sxs-lookup"><span data-stu-id="fc994-131">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="fc994-132">Primeiro, reúna todas as URLs que você precisa adicionar no AAD.</span><span class="sxs-lookup"><span data-stu-id="fc994-132">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="fc994-133">Execute estes comandos no local:</span><span class="sxs-lookup"><span data-stu-id="fc994-133">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
```

<span data-ttu-id="fc994-134">Verifique se os clientes URLs aos que podem se conectar estão listados como nomes principais do serviço HTTPS no AAD.</span><span class="sxs-lookup"><span data-stu-id="fc994-134">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span> <span data-ttu-id="fc994-135">Caso o EXCH seja híbrido com vários **locatários,** esses SPNs HTTPS devem ser adicionados ao AAD de todos os locatários híbridos com o EXCH.</span><span class="sxs-lookup"><span data-stu-id="fc994-135">In case EXCH is in hybrid with **multiple tenants**, these HTTPS SPNs should be added in the AAD of all the tenants in hybrid with EXCH.</span></span>

1. <span data-ttu-id="fc994-136">Primeiro, conecte-se ao AAD com [estas instruções](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="fc994-136">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="fc994-137">Você precisa usar a _opção Conexão-MsolService_ nesta página para poder usar o comando abaixo.</span><span class="sxs-lookup"><span data-stu-id="fc994-137">You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="fc994-138">Para as URLs Exchange relacionadas ao Exchange, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="fc994-138">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="fc994-139">Observe (e captura de tela para comparação posterior) a saída deste comando, que deve incluir uma URL https://  *autodiscover.yourdomain.com*  e https://  *mail.yourdomain.com,* mas consiste principalmente em SPNs que começam com 00000002-0000-0ff1-ce00-000000000000/.</span><span class="sxs-lookup"><span data-stu-id="fc994-139">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="fc994-140">Se houver https:// URLs do seu local ausentes, será necessário adicionar esses registros específicos a essa lista.</span><span class="sxs-lookup"><span data-stu-id="fc994-140">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="fc994-141">Se você não vir seus registros internos e externos MAPI/HTTP, EWS, ActiveSync, OAB e Descoberta Automática nesta lista, você deverá adicioná-los usando o comando abaixo (as URLs de exemplo são ' e ' ', mas você substituiria as `mail.corp.contoso.com` `owa.contoso.com` **URLs** de exemplo por suas próprias ):</span><span class="sxs-lookup"><span data-stu-id="fc994-141">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="fc994-142">Verifique se os novos registros foram adicionados executando o comando Get-MsolServicePrincipal da etapa 2 novamente e verificando a saída.</span><span class="sxs-lookup"><span data-stu-id="fc994-142">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="fc994-143">Compare a lista/captura de tela de antes com a nova lista de SPNs.</span><span class="sxs-lookup"><span data-stu-id="fc994-143">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="fc994-144">Você também pode fazer uma captura de tela da nova lista para seus registros.</span><span class="sxs-lookup"><span data-stu-id="fc994-144">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="fc994-145">Se você tiver êxito, verá as duas novas URLs na lista.</span><span class="sxs-lookup"><span data-stu-id="fc994-145">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="fc994-146">Em nosso exemplo, a lista de SPNs agora incluirá as URLs específicas  `https://mail.corp.contoso.com`  e  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="fc994-146">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="fc994-147">Verificar se os Diretórios Virtuais estão configurados corretamente</span><span class="sxs-lookup"><span data-stu-id="fc994-147">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="fc994-148">Agora verifique se o OAuth está habilitado corretamente no Exchange em todos os Diretórios Virtuais Outlook podem ser utilizados executando os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="fc994-148">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="fc994-149">Verifique a saída para verificar se **o OAuth** está habilitado em cada um desses VDirs, ele será parecido com isso (e a chave a ser olhada é 'OAuth'):</span><span class="sxs-lookup"><span data-stu-id="fc994-149">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="fc994-150">Se o OAuth estiver ausente de qualquer servidor e de qualquer um dos quatro diretórios virtuais, você precisará adicioná-lo usando os comandos relevantes antes de prosseguir ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory,](/powershell/module/exchange/set-webservicesvirtualdirectory) [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)e [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span><span class="sxs-lookup"><span data-stu-id="fc994-150">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="fc994-151">Confirme se o objeto EvoSTS Auth Server está presente</span><span class="sxs-lookup"><span data-stu-id="fc994-151">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="fc994-152">Retorne ao Shell de Gerenciamento local Exchange para este último comando.</span><span class="sxs-lookup"><span data-stu-id="fc994-152">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="fc994-153">Agora você pode validar que seu local tem uma entrada para o provedor de autenticação evoSTS:</span><span class="sxs-lookup"><span data-stu-id="fc994-153">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -like "EvoSts"}
```

<span data-ttu-id="fc994-154">Sua saída deve mostrar um AuthServer do nome EvoSts e o estado 'Habilitado' deve ser True.</span><span class="sxs-lookup"><span data-stu-id="fc994-154">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="fc994-155">Se você não vir isso, baixe e execute a versão mais recente do Assistente de Configuração Híbrida.</span><span class="sxs-lookup"><span data-stu-id="fc994-155">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="fc994-156">Caso o EXCH seja híbrido com vários **locatários,** sua saída deverá mostrar um AuthServer do Name EvoSts - {GUID} para cada locatário em híbrido com EXCH e o estado 'Habilitado' deve ser True para todos esses objetos AuthServer.</span><span class="sxs-lookup"><span data-stu-id="fc994-156">In case EXCH is in hybrid with **multiple tenants**, your output should show one AuthServer of the Name EvoSts - {GUID} for each tenant in hybrid with EXCH and the 'Enabled' state should be True for all of these AuthServer objects.</span></span>

 <span data-ttu-id="fc994-157">**Importante** Se você estiver executando Exchange 2010 em seu ambiente, o provedor de autenticação EvoSTS não será criado.</span><span class="sxs-lookup"><span data-stu-id="fc994-157">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="fc994-158">Habilitar HMA</span><span class="sxs-lookup"><span data-stu-id="fc994-158">Enable HMA</span></span>

<span data-ttu-id="fc994-159">Execute o seguinte comando no Shell de Gerenciamento Exchange, local:</span><span class="sxs-lookup"><span data-stu-id="fc994-159">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

<span data-ttu-id="fc994-160">Se a versão EXCH for Exchange 2016 (CU18 ou superior) ou Exchange 2019 (CU7 ou superior) e híbrida tiver sido configurada com HCW baixada após setembro de 2020, execute o seguinte comando no Shell de Gerenciamento do Exchange, local:</span><span class="sxs-lookup"><span data-stu-id="fc994-160">If the EXCH version is Exchange 2016 (CU18 or higher) or Exchange 2019 (CU7 or higher) and hybrid was configured with HCW downloaded after September 2020, run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -Domain "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> <span data-ttu-id="fc994-161">Caso o EXCH seja híbrido com vários **locatários,** há vários objetos AuthServer presentes no EXCH com domínios correspondentes a cada locatário.</span><span class="sxs-lookup"><span data-stu-id="fc994-161">In case EXCH is in hybrid with **multiple tenants**, there are multiple AuthServer objects present in EXCH with domains corresponding to each tenant.</span></span>  <span data-ttu-id="fc994-162">O **sinalizador IsDefaultAuthorizationEndpoint** deve ser definido como true (usando o cmdlet **IsDefaultAuthorizationEndpoint)** para qualquer um desses objetos AuthServer.</span><span class="sxs-lookup"><span data-stu-id="fc994-162">The **IsDefaultAuthorizationEndpoint** flag should be set to true (using the **IsDefaultAuthorizationEndpoint** cmdlet) for any one of these AuthServer objects.</span></span> <span data-ttu-id="fc994-163">Esse sinalizador não pode ser definido como true para todos os objetos Authserver e o HMA estaria habilitado, mesmo se um desses sinalizadores do objeto AuthServer **IsDefaultAuthorizationEndpoint** estivesse definido como true.</span><span class="sxs-lookup"><span data-stu-id="fc994-163">This flag can't be set to true for all the Authserver objects and HMA would be enabled even if one of these AuthServer object's **IsDefaultAuthorizationEndpoint** flag is set to true.</span></span>

## <a name="verify"></a><span data-ttu-id="fc994-164">Verify</span><span class="sxs-lookup"><span data-stu-id="fc994-164">Verify</span></span>

<span data-ttu-id="fc994-165">Depois de habilitar o HMA, o próximo logon de um cliente usará o novo fluxo de auth.</span><span class="sxs-lookup"><span data-stu-id="fc994-165">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="fc994-166">Observe que apenas ativar o HMA não disparará uma reauthentication para qualquer cliente.</span><span class="sxs-lookup"><span data-stu-id="fc994-166">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="fc994-167">Os clientes reauthenticam com base no tempo de vida dos tokens de autenticação e/ou certificados que eles têm.</span><span class="sxs-lookup"><span data-stu-id="fc994-167">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="fc994-168">Você também deve segurar a tecla CTRL ao mesmo tempo em que clica com o botão direito do mouse no ícone do cliente Outlook (também na bandeja Windows Notificações) e clique em "Status da Conexão".</span><span class="sxs-lookup"><span data-stu-id="fc994-168">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="fc994-169">Procure o endereço SMTP do cliente em relação a um tipo "Authn" de "Portador", que representa o token de portador usado \* no OAuth.</span><span class="sxs-lookup"><span data-stu-id="fc994-169">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

> [!NOTE]
> <span data-ttu-id="fc994-170">Precisa configurar Skype for Business HMA?</span><span class="sxs-lookup"><span data-stu-id="fc994-170">Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="fc994-171">Você precisará de dois artigos: um que lista [topologias](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)com suporte e um que mostra como [fazer a configuração](configure-skype-for-business-for-hybrid-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="fc994-171">You'll need two articles: One that lists [supported topologies](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="fc994-172">Usar autenticação moderna híbrida com o Outlook para iOS e Android</span><span class="sxs-lookup"><span data-stu-id="fc994-172">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="fc994-173">Se você for um cliente local usando um servidor Exchange TCP 443, ignore o processamento de tráfego para os seguintes intervalos de endereços IP:</span><span class="sxs-lookup"><span data-stu-id="fc994-173">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP address ranges:</span></span>

```
52.125.128.0/20
52.127.96.0/23
```

<span data-ttu-id="fc994-174">O aplicativo Outlook para iOS e Android foi projetado como a melhor maneira de experimentar Microsoft 365 ou Office 365 em seu dispositivo móvel usando o serviços Microsoft para ajudar a encontrar, planejar e priorizar sua vida diária e trabalho.</span><span class="sxs-lookup"><span data-stu-id="fc994-174">The Outlook app for iOS and Android is designed as the best way to experience Microsoft 365 or Office 365 on your mobile device by using Microsoft services to help find, plan, and prioritize your daily life and work.</span></span> <span data-ttu-id="fc994-175">Para obter mais informações, consulte [Using hybrid Modern Authentication with Outlook for iOS and Android](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth?view=exchserver-2019).</span><span class="sxs-lookup"><span data-stu-id="fc994-175">For more information, please refer to [Using hybrid Modern Authentication with Outlook for iOS and Android](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth?view=exchserver-2019).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fc994-176">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fc994-176">Related topics</span></span>

[<span data-ttu-id="fc994-177">Requisitos de configuração de autenticação moderna para a transição de Office 365/ITAR dedicado para vNext</span><span class="sxs-lookup"><span data-stu-id="fc994-177">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
