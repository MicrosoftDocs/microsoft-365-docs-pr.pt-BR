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
description: Saiba como configurar um Exchange Server local para usar a Autenticação Moderna Híbrida (HMA), oferecendo autenticação e autorização de usuário mais seguras.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3841f429399500cfc24ebadc89c74d478d2290d9
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780279"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="f38e1-103">Como configurar o Exchange Server no local para usar a autenticação moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="f38e1-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="f38e1-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f38e1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f38e1-105">A Autenticação Moderna Híbrida (HMA) é um método de gerenciamento de identidade que oferece autenticação e autorização de usuário mais seguras e está disponível para implantações híbridas locais do Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="f38e1-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="f38e1-106">FYI</span><span class="sxs-lookup"><span data-stu-id="f38e1-106">FYI</span></span>

<span data-ttu-id="f38e1-107">Antes de começar, eu faço a chamada:</span><span class="sxs-lookup"><span data-stu-id="f38e1-107">Before we begin, I call:</span></span>

- <span data-ttu-id="f38e1-108">HMA de autenticação \> moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="f38e1-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="f38e1-109">EXCH local \> do Exchange</span><span class="sxs-lookup"><span data-stu-id="f38e1-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="f38e1-110">Exchange Online \> EXO</span><span class="sxs-lookup"><span data-stu-id="f38e1-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="f38e1-111">Além disso, se um gráfico neste artigo tiver um objeto que está "esmaecida" ou "esmaecida", isso significa que o elemento mostrado em cinza não está incluído na configuração específica de *HMA.*</span><span class="sxs-lookup"><span data-stu-id="f38e1-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="f38e1-112">Habilitando a autenticação moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="f38e1-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="f38e1-113">A adoção do HMA significa:</span><span class="sxs-lookup"><span data-stu-id="f38e1-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="f38e1-114">Certifique-se de atender aos pré-requisitos antes de começar.</span><span class="sxs-lookup"><span data-stu-id="f38e1-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="f38e1-115">Como  muitos pré-requisitos são comuns para o Skype for Business e o Exchange, a visão geral da Autenticação Moderna Híbrida e os [pré-requisitos para usá-lo](hybrid-modern-auth-overview.md)com os servidores locais do Skype for Business e do Exchange.</span><span class="sxs-lookup"><span data-stu-id="f38e1-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="f38e1-116">Faça isso antes de começar qualquer uma das etapas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="f38e1-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="f38e1-117">Adição de URLs de serviço Web locais como **SPNs (Nomes** de Entidades de Serviço) no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f38e1-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span>

1. <span data-ttu-id="f38e1-118">Garantir que todos os Diretórios Virtuais sejam habilitados para HMA</span><span class="sxs-lookup"><span data-stu-id="f38e1-118">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="f38e1-119">Verificando o objeto EvoSTS Auth Server</span><span class="sxs-lookup"><span data-stu-id="f38e1-119">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="f38e1-120">Habilitando o HMA no EXCH.</span><span class="sxs-lookup"><span data-stu-id="f38e1-120">Enabling HMA in EXCH.</span></span>

 <span data-ttu-id="f38e1-121">**Observação** Sua versão do Office dá suporte à MA?</span><span class="sxs-lookup"><span data-stu-id="f38e1-121">**Note** Does your version of Office support MA?</span></span> <span data-ttu-id="f38e1-122">Veja [como funciona a autenticação moderna para aplicativos clientes do Office 2013 e do Office 2016.](modern-auth-for-office-2013-and-2016.md)</span><span class="sxs-lookup"><span data-stu-id="f38e1-122">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>

## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="f38e1-123">Certifique-se de atender a todos os pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f38e1-123">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="f38e1-124">Como muitos pré-requisitos são comuns para o Skype for Business e o Exchange, revise a visão geral da Autenticação Moderna Híbrida e os [pré-requisitos para usá-la](hybrid-modern-auth-overview.md)com os servidores locais do Skype for Business e do Exchange.</span><span class="sxs-lookup"><span data-stu-id="f38e1-124">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="f38e1-125">Faça isso  *antes*  de começar qualquer uma das etapas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="f38e1-125">Do this  *before*  you begin any of the steps in this article.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="f38e1-126">Adicionar URLs de serviço Web local como SPNs no Azure AD</span><span class="sxs-lookup"><span data-stu-id="f38e1-126">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="f38e1-127">Execute os comandos que atribuem suas URLs de serviço Web locais como SPNs do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f38e1-127">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="f38e1-128">Os SPNs são usados por máquinas e dispositivos cliente durante a autenticação e autorização.</span><span class="sxs-lookup"><span data-stu-id="f38e1-128">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="f38e1-129">Todas as URLs que podem ser usadas para se conectar do Azure Active Directory (Azure AD) local devem ser registradas no Azure AD (isso inclui namespaces internos e externos).</span><span class="sxs-lookup"><span data-stu-id="f38e1-129">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="f38e1-130">Primeiro, reúna todas as URLs que você precisa adicionar no AAD.</span><span class="sxs-lookup"><span data-stu-id="f38e1-130">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="f38e1-131">Execute estes comandos no local:</span><span class="sxs-lookup"><span data-stu-id="f38e1-131">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

<span data-ttu-id="f38e1-132">Verifique se os clientes urLs aos que podem se conectar estão listados como nomes de entidade de serviço HTTPS no AAD.</span><span class="sxs-lookup"><span data-stu-id="f38e1-132">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span>

1. <span data-ttu-id="f38e1-133">Primeiro, conecte-se ao AAD com [estas instruções.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="f38e1-133">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

   <span data-ttu-id="f38e1-134">**Observação** Você precisa usar a _opção Connect-MsolService_ desta página para poder usar o comando abaixo.</span><span class="sxs-lookup"><span data-stu-id="f38e1-134">**Note** You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="f38e1-135">Para suas URLs relacionadas ao Exchange, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f38e1-135">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="f38e1-136">Anote (e captura de tela para comparação posterior) a saída desse comando, que deve incluir uma URL de https://  *autodiscover.yourdomain.com*  e  *https:// mail.yourdomain.com,* mas, principalmente, consiste em SPNs que começam com 00000002-0000-0ff1-ce00-0000000000000/.</span><span class="sxs-lookup"><span data-stu-id="f38e1-136">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="f38e1-137">Se houver https:// URLs de seu local ausentes, será necessário adicionar esses registros específicos a essa lista.</span><span class="sxs-lookup"><span data-stu-id="f38e1-137">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="f38e1-138">Se você não vir seus registros MAPI/HTTP, EWS, ActiveSync, OAB e Descoberta Automática internos e externos nesta lista, adicione-os usando o comando abaixo (as URLs de exemplo são ' e ' ', mas você substituiria as `mail.corp.contoso.com` `owa.contoso.com` **URLs** de exemplo por suas próprias ):</span><span class="sxs-lookup"><span data-stu-id="f38e1-138">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="f38e1-139">Verifique se os novos registros foram adicionados executando o Get-MsolServicePrincipal comando da etapa 2 novamente e observando a saída.</span><span class="sxs-lookup"><span data-stu-id="f38e1-139">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="f38e1-140">Compare a lista/captura de tela de antes com a nova lista de SPNs.</span><span class="sxs-lookup"><span data-stu-id="f38e1-140">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="f38e1-141">Você também pode fazer uma captura de tela da nova lista para seus registros.</span><span class="sxs-lookup"><span data-stu-id="f38e1-141">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="f38e1-142">Se você foi bem-sucedido, verá as duas novas URLs na lista.</span><span class="sxs-lookup"><span data-stu-id="f38e1-142">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="f38e1-143">No nosso exemplo, a lista de SPNs agora incluirá as URLs específicas  `https://mail.corp.contoso.com`  `https://owa.contoso.com` e.</span><span class="sxs-lookup"><span data-stu-id="f38e1-143">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="f38e1-144">Verificar se os diretórios virtuais estão configurados corretamente</span><span class="sxs-lookup"><span data-stu-id="f38e1-144">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="f38e1-145">Agora verifique se o OAuth está habilitado corretamente no Exchange em todos os Diretórios Virtuais que o Outlook pode usar executando os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="f38e1-145">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="f38e1-146">Verifique a saída para garantir que **o OAuth** está habilitado em cada um desses VDirs, ele será parecido com isso (e o mais importante a ser analisado é 'OAuth'):</span><span class="sxs-lookup"><span data-stu-id="f38e1-146">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="f38e1-147">Se o OAuth estiver ausente de qualquer servidor e de qualquer um dos quatro diretórios virtuais, você precisará adicioná-lo usando os comandos relevantes antes de prosseguir ([Set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory)e [Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span><span class="sxs-lookup"><span data-stu-id="f38e1-147">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="f38e1-148">Confirmar se o objeto de servidor de auth do EvoSTS está presente</span><span class="sxs-lookup"><span data-stu-id="f38e1-148">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="f38e1-149">Retorne ao Shell de Gerenciamento do Exchange local para este último comando.</span><span class="sxs-lookup"><span data-stu-id="f38e1-149">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="f38e1-150">Agora você pode validar se o local tem uma entrada para o provedor de autenticação evoSTS:</span><span class="sxs-lookup"><span data-stu-id="f38e1-150">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="f38e1-151">Sua saída deve mostrar um AuthServer do nome EvoSts e o estado "Habilitado" deve ser True.</span><span class="sxs-lookup"><span data-stu-id="f38e1-151">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="f38e1-152">Se você não vir isso, baixe e execute a versão mais recente do Assistente de Configuração Híbrida.</span><span class="sxs-lookup"><span data-stu-id="f38e1-152">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

 <span data-ttu-id="f38e1-153">**Importante** Se você estiver executando o Exchange 2010 em seu ambiente, o provedor de autenticação EvoSTS não será criado.</span><span class="sxs-lookup"><span data-stu-id="f38e1-153">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="f38e1-154">Habilitar HMA</span><span class="sxs-lookup"><span data-stu-id="f38e1-154">Enable HMA</span></span>

<span data-ttu-id="f38e1-155">Execute o seguinte comando no Shell de Gerenciamento do Exchange, local:</span><span class="sxs-lookup"><span data-stu-id="f38e1-155">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a><span data-ttu-id="f38e1-156">Verify</span><span class="sxs-lookup"><span data-stu-id="f38e1-156">Verify</span></span>

<span data-ttu-id="f38e1-157">Depois de habilitar o HMA, o próximo logon do cliente usará o novo fluxo de auth.</span><span class="sxs-lookup"><span data-stu-id="f38e1-157">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="f38e1-158">Observe que apenas ativar o HMA não disparará uma nova autenticação para qualquer cliente.</span><span class="sxs-lookup"><span data-stu-id="f38e1-158">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="f38e1-159">Os clientes são autenticados com base no tempo de vida dos tokens de autenticação e/ou certificados que eles têm.</span><span class="sxs-lookup"><span data-stu-id="f38e1-159">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="f38e1-160">Você também deve segurar a tecla CTRL ao mesmo tempo em que clica com o botão direito do mouse no ícone do cliente do Outlook (também na bandeja notificações do Windows) e clicar em 'Status da Conexão'.</span><span class="sxs-lookup"><span data-stu-id="f38e1-160">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="f38e1-161">Procure o endereço SMTP do cliente em relação a um tipo 'Authn' de "Portador", que representa o token de portador usado \* no OAuth.</span><span class="sxs-lookup"><span data-stu-id="f38e1-161">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

 <span data-ttu-id="f38e1-162">**Observação** Precisa configurar o Skype for Business com HMA?</span><span class="sxs-lookup"><span data-stu-id="f38e1-162">**Note** Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="f38e1-163">Você precisará de dois artigos: um que lista as [topologias](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)com suporte e um que mostra [como fazer a configuração.](configure-skype-for-business-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="f38e1-163">You'll need two articles: One that lists [supported topologies](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="f38e1-164">Usar autenticação moderna híbrida com o Outlook para iOS e Android</span><span class="sxs-lookup"><span data-stu-id="f38e1-164">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="f38e1-165">Se você for um cliente local usando o servidor Exchange no TCP 443, ignore o processamento de tráfego para os seguintes intervalos de IP:</span><span class="sxs-lookup"><span data-stu-id="f38e1-165">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP ranges:</span></span>

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a><span data-ttu-id="f38e1-166">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f38e1-166">Related topics</span></span>

[<span data-ttu-id="f38e1-167">Requisitos de configuração de Autenticação Moderna para transição do Office 365 dedicado/ITAR para vNext</span><span class="sxs-lookup"><span data-stu-id="f38e1-167">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
