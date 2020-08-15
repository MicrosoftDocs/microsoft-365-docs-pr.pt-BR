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
description: Saiba como configurar um servidor Exchange local para usar a protocolo de autenticação moderna (HMA), oferecendo uma autenticação e autorização de usuário mais segura.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 291c7c220fb4ee56db2a42409d5b81724de5da32
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686883"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="a88e9-103">Como configurar o Exchange Server no local para usar a autenticação moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="a88e9-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="a88e9-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a88e9-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a88e9-105">A HMA moderna (autenticação moderna híbrida) é um método de gerenciamento de identidades que oferece autenticação e autorização de usuário mais seguras e está disponível para implantações híbridas locais do Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="a88e9-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>
  
## <a name="fyi"></a><span data-ttu-id="a88e9-106">CONHECIMENTO</span><span class="sxs-lookup"><span data-stu-id="a88e9-106">FYI</span></span>

<span data-ttu-id="a88e9-107">Antes de começar, chamo:</span><span class="sxs-lookup"><span data-stu-id="a88e9-107">Before we begin, I call:</span></span>
  
- <span data-ttu-id="a88e9-108">HMA de autenticação moderna híbrida \></span><span class="sxs-lookup"><span data-stu-id="a88e9-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="a88e9-109">\>Exchange local</span><span class="sxs-lookup"><span data-stu-id="a88e9-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="a88e9-110">EXO do Exchange Online \></span><span class="sxs-lookup"><span data-stu-id="a88e9-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="a88e9-111">Além disso, *se um gráfico neste artigo tiver um objeto que é ' esmaecido ' ou ' esmaecido ' que significa que o elemento mostrado em cinza não está incluído na configuração específica da HMA* .</span><span class="sxs-lookup"><span data-stu-id="a88e9-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration* .</span></span>
  
## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="a88e9-112">Habilitar a autenticação moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="a88e9-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="a88e9-113">Virar a HMA em significa:</span><span class="sxs-lookup"><span data-stu-id="a88e9-113">Turning HMA on means:</span></span>
  
1. <span data-ttu-id="a88e9-114">Ter certeza de que você atende ao pré antes de começar.</span><span class="sxs-lookup"><span data-stu-id="a88e9-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="a88e9-115">Como muitos **pré-requisitos** são comuns para o Skype for Business e o Exchange, a [visão geral da autenticação moderna híbrida e os pré-requisitos para usá-lo com o Skype for Business e servidores do Exchange locais](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a88e9-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="a88e9-116">Faça isso antes de começar qualquer uma das etapas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="a88e9-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="a88e9-117">Adicionar URLs do serviço Web local como **nomes de entidade de serviço (SPNs)** no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a88e9-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span>

1. <span data-ttu-id="a88e9-118">Garantir que todos os diretórios virtuais estejam habilitados para a HMA</span><span class="sxs-lookup"><span data-stu-id="a88e9-118">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="a88e9-119">Verificando o objeto do servidor de autenticação EvoSTS</span><span class="sxs-lookup"><span data-stu-id="a88e9-119">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="a88e9-120">Habilitando HMA no EXCH.</span><span class="sxs-lookup"><span data-stu-id="a88e9-120">Enabling HMA in EXCH.</span></span>

 <span data-ttu-id="a88e9-121">**Observação** Sua versão do Office oferece suporte ao MA?</span><span class="sxs-lookup"><span data-stu-id="a88e9-121">**Note** Does your version of Office support MA?</span></span> <span data-ttu-id="a88e9-122">Veja [como a autenticação moderna funciona para aplicativos cliente do office 2013 e office 2016](modern-auth-for-office-2013-and-2016.md).</span><span class="sxs-lookup"><span data-stu-id="a88e9-122">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>
  
## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="a88e9-123">Verifique se você atende a todos os pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a88e9-123">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="a88e9-124">Como muitos pré-requisitos são comuns para o Skype for Business e o Exchange, revise a [visão geral da autenticação moderna híbrida e os pré-requisitos para usá-lo com o Skype for Business e os servidores do Exchange locais](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a88e9-124">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="a88e9-125">Faça isso  *antes*  de começar qualquer uma das etapas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="a88e9-125">Do this  *before*  you begin any of the steps in this article.</span></span>
  
## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="a88e9-126">Adicionar URLs do serviço Web local como SPNs no Azure AD</span><span class="sxs-lookup"><span data-stu-id="a88e9-126">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="a88e9-127">Execute os comandos que atribuem as URLs do serviço Web local como SPNs do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a88e9-127">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="a88e9-128">Os SPNs são usados por máquinas clientes e dispositivos durante a autenticação e autorização.</span><span class="sxs-lookup"><span data-stu-id="a88e9-128">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="a88e9-129">Todas as URLs que podem ser usadas para se conectar a partir do local para o Azure Active Directory (Azure AD) devem ser registradas no Azure AD (isso inclui namespaces internos e externos).</span><span class="sxs-lookup"><span data-stu-id="a88e9-129">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>
  
<span data-ttu-id="a88e9-130">Primeiro, reúna todas as URLs que você precisa adicionar no AAD.</span><span class="sxs-lookup"><span data-stu-id="a88e9-130">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="a88e9-131">Execute estes comandos no local:</span><span class="sxs-lookup"><span data-stu-id="a88e9-131">Run these commands on-premises:</span></span>
  
```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```
    
<span data-ttu-id="a88e9-132">Verifique se os clientes URLs que podem se conectar estão listados como nomes de entidade de serviço HTTPS no AAD.</span><span class="sxs-lookup"><span data-stu-id="a88e9-132">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span>
  
1. <span data-ttu-id="a88e9-133">Primeiro, conecte-se ao AAD com [estas instruções](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a88e9-133">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

 <span data-ttu-id="a88e9-134">**Observação** Você precisa usar a opção _Connect-MsolService_ desta página para poder usar o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="a88e9-134">**Note** You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="a88e9-135">Para suas URLs relacionadas ao Exchange, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a88e9-135">For your Exchange related URLs, type the following command:</span></span>

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
```

<span data-ttu-id="a88e9-136">Anote (e captura de tela para comparação posterior) a saída desse comando, que deve incluir uma URL https://  *autodiscover.yourdomain.com*  e https://  *mail.yourdomain.com* , mas que basicamente consiste em SPNs que começam com 00000002-0000-0ff1-ce00-000000000000/.</span><span class="sxs-lookup"><span data-stu-id="a88e9-136">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="a88e9-137">Se houver https://URLs de seu local que estão ausentes, precisaremos adicionar esses registros específicos a essa lista.</span><span class="sxs-lookup"><span data-stu-id="a88e9-137">If there are https:// URLs from your on-premises that are missing we will need to add those specific records to this list.</span></span>
  
3. <span data-ttu-id="a88e9-138">Se você não vir seus registros internos e externos de MAPI/HTTP, EWS, ActiveSync, OAB e descoberta automática nesta lista, você deve adicioná-los usando o comando a seguir (as URLs de exemplo são ' `mail.corp.contoso.com` ' e ' `owa.contoso.com` ', mas você **substituirá as URLs de exemplo por suas próprias** ):</span><span class="sxs-lookup"><span data-stu-id="a88e9-138">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own** ):</span></span> <br/>
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
$x.ServicePrincipalnames.Add("https://owa.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```

4. <span data-ttu-id="a88e9-139">Verifique se os novos registros foram adicionados executando o comando Get-MsolServicePrincipal da etapa 2 novamente e examinando a saída.</span><span class="sxs-lookup"><span data-stu-id="a88e9-139">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="a88e9-140">Compare a lista/captura de tela antes da nova lista de SPNs (você também pode capturar a nova lista para seus registros).</span><span class="sxs-lookup"><span data-stu-id="a88e9-140">Compare the list / screenshot from before to the new list of SPNs (you may also screenshot the new list for your records).</span></span> <span data-ttu-id="a88e9-141">Se você tiver êxito, verá as duas novas URLs na lista.</span><span class="sxs-lookup"><span data-stu-id="a88e9-141">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="a88e9-142">Indo em nosso exemplo, a lista de SPNs agora incluirá as URLs específicas  `https://mail.corp.contoso.com`  e  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="a88e9-142">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span> 
  
## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="a88e9-143">Verificar se os diretórios virtuais estão configurados corretamente</span><span class="sxs-lookup"><span data-stu-id="a88e9-143">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="a88e9-144">Agora, verifique se o OAuth está habilitado corretamente no Exchange em todos os diretórios virtuais que o Outlook pode usar executando os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="a88e9-144">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth* 
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="a88e9-145">Verifique a saída para certificar-se de que o **OAuth** está habilitado em cada um desses VDirss, ele terá a seguinte aparência (e o principal aspecto a ser examinado é ' OAuth '):</span><span class="sxs-lookup"><span data-stu-id="a88e9-145">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```
  
<span data-ttu-id="a88e9-146">Se o OAuth estiver ausente de qualquer servidor e de qualquer um dos quatro diretórios virtuais, você precisará adicioná-lo usando os comandos relevantes antes de proceder ([set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-mapivirtualdirectory?view=exchange-ps), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-webservicesvirtualdirectory?view=exchange-ps), [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/email-addresses-and-address-books/set-oabvirtualdirectory?view=exchange-ps)e [Set-AutoDiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-autodiscovervirtualdirectory?view=exchange-ps)).</span><span class="sxs-lookup"><span data-stu-id="a88e9-146">If OAuth is missing from any server and any of the four virtual directories then you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-mapivirtualdirectory?view=exchange-ps), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-webservicesvirtualdirectory?view=exchange-ps), [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/email-addresses-and-address-books/set-oabvirtualdirectory?view=exchange-ps), and [Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-autodiscovervirtualdirectory?view=exchange-ps)).</span></span>
  
## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="a88e9-147">Confirmar se o objeto de servidor de autenticação EvoSTS está presente</span><span class="sxs-lookup"><span data-stu-id="a88e9-147">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="a88e9-148">Retorne ao Shell de gerenciamento do Exchange local para este último comando.</span><span class="sxs-lookup"><span data-stu-id="a88e9-148">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="a88e9-149">Agora você pode validar que seu local tem uma entrada para o provedor de autenticação do evoSTS:</span><span class="sxs-lookup"><span data-stu-id="a88e9-149">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>
  
```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="a88e9-150">A saída deve mostrar um AuthServer do nome EvoSts e o estado ' Enabled ' deve ser true.</span><span class="sxs-lookup"><span data-stu-id="a88e9-150">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="a88e9-151">Se você não vir isso, baixe e execute a versão mais recente do assistente de configuração híbrida.</span><span class="sxs-lookup"><span data-stu-id="a88e9-151">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>
  
 <span data-ttu-id="a88e9-152">**Importante** Se você estiver executando o Exchange 2010 em seu ambiente, o provedor de autenticação do EvoSTS não será criado.</span><span class="sxs-lookup"><span data-stu-id="a88e9-152">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span> 
  
## <a name="enable-hma"></a><span data-ttu-id="a88e9-153">Habilitar HMA</span><span class="sxs-lookup"><span data-stu-id="a88e9-153">Enable HMA</span></span>

<span data-ttu-id="a88e9-154">Execute o seguinte comando no Shell de gerenciamento do Exchange, no local:</span><span class="sxs-lookup"><span data-stu-id="a88e9-154">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true  
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a><span data-ttu-id="a88e9-155">Verify</span><span class="sxs-lookup"><span data-stu-id="a88e9-155">Verify</span></span>

<span data-ttu-id="a88e9-156">Depois de habilitar a HMA, o próximo login de um cliente usará o novo fluxo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="a88e9-156">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="a88e9-157">Observe que apenas a ativação da HMA não acionará uma nova autenticação para qualquer cliente.</span><span class="sxs-lookup"><span data-stu-id="a88e9-157">Note that just turning on HMA won't trigger a re-authentication for any client.</span></span> <span data-ttu-id="a88e9-158">Os clientes são autenticados novamente com base no tempo de vida dos tokens de autenticação e/ou certs que possuem.</span><span class="sxs-lookup"><span data-stu-id="a88e9-158">The clients re-authenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>
  
<span data-ttu-id="a88e9-159">Você também deve manter pressionada a tecla CTRL enquanto clica com o botão direito do mouse no ícone do cliente Outlook (também na bandeja de notificações do Windows) e clique em "status da conexão".</span><span class="sxs-lookup"><span data-stu-id="a88e9-159">You should also hold down the CTRL key at the same time you right click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="a88e9-160">Procure o endereço SMTP do cliente em relação a um tipo "Authn" de "portador \* ", que representa o token de portador usado no OAuth.</span><span class="sxs-lookup"><span data-stu-id="a88e9-160">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>
  
 <span data-ttu-id="a88e9-161">**Observação** Precisa configurar o Skype for Business com a HMA?</span><span class="sxs-lookup"><span data-stu-id="a88e9-161">**Note** Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="a88e9-162">Você precisará de dois artigos: um que lista as [topologias suportadas](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)e uma que mostra [como fazer a configuração](configure-skype-for-business-for-hybrid-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="a88e9-162">You'll need two articles: One that lists [supported topologies](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>
 
## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="a88e9-163">Usar autenticação moderna híbrida com o Outlook para iOS e Android</span><span class="sxs-lookup"><span data-stu-id="a88e9-163">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="a88e9-164">Se você for um cliente local usando o Exchange Server no TCP 443, leia os seguintes intervalos IP:  </span><span class="sxs-lookup"><span data-stu-id="a88e9-164">If you are an on-premises customer using Exchange server on TCP 443, please whitelist the following IP ranges:  </span></span><BR> ```52.125.128.0/20``` <BR> ```52.127.96.0/23``` <BR>

## <a name="related-topics"></a><span data-ttu-id="a88e9-165">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a88e9-165">Related topics</span></span>

[<span data-ttu-id="a88e9-166">Requisitos de configuração de autenticação moderna para transição do Office 365 dedicada/ITAR para o vNext</span><span class="sxs-lookup"><span data-stu-id="a88e9-166">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
