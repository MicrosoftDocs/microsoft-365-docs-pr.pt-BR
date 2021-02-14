---
title: Como configurar o Skype for Business no local para usar a autenticação moderna híbrida
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Saiba como configurar o Skype for Business local para usar a Autenticação Moderna Híbrida (HMA), oferecendo autenticação e autorização de usuário mais seguras.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74c8e3e0514fbfd8779c2f65e9c541c33b281c59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694999"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="c5587-103">Como configurar o Skype for Business no local para usar a autenticação moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="c5587-103">How to configure Skype for Business on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="c5587-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c5587-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c5587-105">A Autenticação Moderna é um método de gerenciamento de identidade que oferece autenticação e autorização de usuário mais seguras, está disponível para o skype for Business server local e o servidor exchange local e para híbridos de domínio dividido do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c5587-105">Modern Authentication, is a method of identity management that offers more secure user authentication and authorization, is available for Skype for Business server on-premises and Exchange server on-premises, and split-domain Skype for Business hybrids.</span></span>
  
 <span data-ttu-id="c5587-106">**Importante** Gostaria de saber mais sobre a Autenticação Moderna (MA) e por que você pode preferir usá-la em sua empresa ou organização?</span><span class="sxs-lookup"><span data-stu-id="c5587-106">**Important** Would you like to know more about Modern Authentication (MA) and why you might prefer to use it in your company or organization?</span></span> <span data-ttu-id="c5587-107">Verifique [este documento para](hybrid-modern-auth-overview.md) ter uma visão geral.</span><span class="sxs-lookup"><span data-stu-id="c5587-107">Check [this document](hybrid-modern-auth-overview.md) for an overview.</span></span> <span data-ttu-id="c5587-108">Se você precisar saber quais topologias do Skype for Business têm suporte com a ma, isso está documentado aqui!</span><span class="sxs-lookup"><span data-stu-id="c5587-108">If you need to know what Skype for Business topologies are supported with MA, that's documented here!</span></span>
  
 <span data-ttu-id="c5587-109">**Antes de começar,** eu uso estes termos:</span><span class="sxs-lookup"><span data-stu-id="c5587-109">**Before we begin**, I use these terms:</span></span>
  
- <span data-ttu-id="c5587-110">Autenticação Moderna (MA)</span><span class="sxs-lookup"><span data-stu-id="c5587-110">Modern Authentication (MA)</span></span>

- <span data-ttu-id="c5587-111">HMA (Autenticação Moderna Híbrida)</span><span class="sxs-lookup"><span data-stu-id="c5587-111">Hybrid Modern Authentication (HMA)</span></span>

- <span data-ttu-id="c5587-112">Exchange local (EXCH)</span><span class="sxs-lookup"><span data-stu-id="c5587-112">Exchange on-premises (EXCH)</span></span>

- <span data-ttu-id="c5587-113">Exchange Online (EXO)</span><span class="sxs-lookup"><span data-stu-id="c5587-113">Exchange Online (EXO)</span></span>

- <span data-ttu-id="c5587-114">Skype for Business local (SFB)</span><span class="sxs-lookup"><span data-stu-id="c5587-114">Skype for Business on-premises (SFB)</span></span>

- <span data-ttu-id="c5587-115">Skype for Business Online (SFBO)</span><span class="sxs-lookup"><span data-stu-id="c5587-115">Skype for Business Online (SFBO)</span></span>

<span data-ttu-id="c5587-116">Além disso, se um gráfico neste artigo tiver um objeto esmaecida ou  esmaecida ou esmaecida, isso significa que o elemento mostrado em cinza não está incluído na configuração específica do MA.</span><span class="sxs-lookup"><span data-stu-id="c5587-116">Also, if a graphic in this article has an object that's grayed-out or dimmed that means the element shown in gray **isn't** included in MA-specific configuration.</span></span>
  
## <a name="read-the-summary"></a><span data-ttu-id="c5587-117">Ler o resumo</span><span class="sxs-lookup"><span data-stu-id="c5587-117">Read the summary</span></span>

<span data-ttu-id="c5587-118">Este resumo divide o processo em etapas que, de outra forma, podem se perder durante a execução e é bom que uma lista de verificação geral acompanhe onde você está no processo.</span><span class="sxs-lookup"><span data-stu-id="c5587-118">This summary breaks down the process into steps that might otherwise get lost during the execution, and is good for an overall checklist to keep track of where you are in the process.</span></span>
  
1. <span data-ttu-id="c5587-119">Primeiro, certifique-se de atender a todos os pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="c5587-119">First, make sure you meet all the prerequisites.</span></span>

1. <span data-ttu-id="c5587-120">Como muitos **pré-requisitos são** comuns para o Skype for Business e o Exchange, consulte o artigo de visão geral da lista de verificação [pré-requisitos.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c5587-120">Since many **prerequisites** are common for both Skype for Business and Exchange, [see the overview article for your pre-req checklist](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="c5587-121">Faça isso  *antes*  de começar qualquer uma das etapas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c5587-121">Do this  *before*  you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="c5587-122">Colete as informações específicas de HMA de que você precisará em um arquivo ou no OneNote.</span><span class="sxs-lookup"><span data-stu-id="c5587-122">Collect the HMA-specific info you'll need in a file, or OneNote.</span></span>

1. <span data-ttu-id="c5587-123">Ativar a autenticação moderna para EXO (caso ainda não tenha sido turned on).</span><span class="sxs-lookup"><span data-stu-id="c5587-123">Turn ON Modern Authentication for EXO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="c5587-124">Ativar a autenticação moderna para SFBO (se ainda não estiver ligado).</span><span class="sxs-lookup"><span data-stu-id="c5587-124">Turn ON Modern Authentication for SFBO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="c5587-125">Ativar a autenticação moderna híbrida para o Exchange no local.</span><span class="sxs-lookup"><span data-stu-id="c5587-125">Turn ON Hybrid Modern Authentication for Exchange on-premises.</span></span>

1. <span data-ttu-id="c5587-126">Ativar a autenticação moderna híbrida para o Skype for Business no local.</span><span class="sxs-lookup"><span data-stu-id="c5587-126">Turn ON Hybrid Modern Authentication for Skype for Business on-premises.</span></span>

<span data-ttu-id="c5587-127">Essas etapas ativarão o MA para SFB, SFBO, EXCH e EXO, ou seja, todos os produtos que podem participar de uma configuração HMA de SFB e SFBO (incluindo dependências de EXCH/EXO).</span><span class="sxs-lookup"><span data-stu-id="c5587-127">These steps turn on MA for SFB, SFBO, EXCH, and EXO - that is, all the products that can participate in an HMA configuration of SFB and SFBO (including dependencies on EXCH/EXO).</span></span> <span data-ttu-id="c5587-128">Em outras palavras, se os usuários estão em/ter caixas de correio criadas em qualquer parte do Híbrido (EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB), seu produto concluído terá esta aparência:</span><span class="sxs-lookup"><span data-stu-id="c5587-128">In other words, if your users are homed in/have mailboxes created in any part of the Hybrid (EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB), your finished product will look like this:</span></span>
  
![Uma topologia HMA Mista 6 do Skype for Business tem MA em todos os quatro locais possíveis.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)
  
<span data-ttu-id="c5587-130">Como você pode ver, há quatro lugares diferentes para ativar o ma!</span><span class="sxs-lookup"><span data-stu-id="c5587-130">As you can see there are four different places to turn on MA!</span></span> <span data-ttu-id="c5587-131">Para a melhor experiência do usuário, recomendamos ativar a ma em todos os quatro locais.</span><span class="sxs-lookup"><span data-stu-id="c5587-131">For the best user experience, we recommend you turn on MA in all four of these locations.</span></span> <span data-ttu-id="c5587-132">Se não for possível ativar o ma em todos esses locais, ajuste as etapas para ativar o ma somente nos locais necessários para seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="c5587-132">If you can't turn MA on in all these locations, adjust the steps so that you turn on MA only in the locations that are necessary for your environment.</span></span>
  
<span data-ttu-id="c5587-133">Consulte o [tópico Suporte do Skype for Business com MA](https://technet.microsoft.com/library/mt803262.aspx) para ver as topologias com suporte.</span><span class="sxs-lookup"><span data-stu-id="c5587-133">See the [Supportability topic for Skype for Business with MA](https://technet.microsoft.com/library/mt803262.aspx) for supported topologies.</span></span>
  
 <span data-ttu-id="c5587-134">**Importante** Verifique se você atendeu a todos os pré-requisitos antes de começar.</span><span class="sxs-lookup"><span data-stu-id="c5587-134">**Important** Double-check that you've met all the prerequisites before you begin.</span></span> <span data-ttu-id="c5587-135">Você encontrará essas informações na visão geral e pré-requisitos da autenticação moderna [híbrida.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c5587-135">You'll find that information in [Hybrid modern authentication overview and prerequisites](hybrid-modern-auth-overview.md).</span></span>
  
## <a name="collect-all-hma-specific-info-youll-need"></a><span data-ttu-id="c5587-136">Coletar todas as informações específicas de HMA de que você precisará</span><span class="sxs-lookup"><span data-stu-id="c5587-136">Collect all HMA-specific info you'll need</span></span>

<span data-ttu-id="c5587-137">Depois de verificar se você está [](hybrid-modern-auth-overview.md) de acordo com os pré-requisitos para usar a Autenticação Moderna (veja a observação acima), crie um arquivo para manter as informações necessárias para configurar o HMA nas etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="c5587-137">After you've double-checked that you meet the [prerequisites](hybrid-modern-auth-overview.md) to use Modern Authentication (see the note above), you should create a file to hold the info you'll need for configuring HMA in the steps ahead.</span></span> <span data-ttu-id="c5587-138">Exemplos usados neste artigo:</span><span class="sxs-lookup"><span data-stu-id="c5587-138">Examples used in this article:</span></span>
  
- <span data-ttu-id="c5587-139">**Domínio SIP/SMTP**</span><span class="sxs-lookup"><span data-stu-id="c5587-139">**SIP/SMTP domain**</span></span>

  - <span data-ttu-id="c5587-140">Por ex.</span><span class="sxs-lookup"><span data-stu-id="c5587-140">Ex.</span></span> <span data-ttu-id="c5587-141">contoso.com (é federado com o Office 365)</span><span class="sxs-lookup"><span data-stu-id="c5587-141">contoso.com (is federated with Office 365)</span></span>

- <span data-ttu-id="c5587-142">**ID do locatário**</span><span class="sxs-lookup"><span data-stu-id="c5587-142">**Tenant ID**</span></span>

  - <span data-ttu-id="c5587-143">O GUID que representa seu locatário do Office 365 (no logon do contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="c5587-143">The GUID that represents your Office 365 tenant (at the login of contoso.onmicrosoft.com).</span></span>

- <span data-ttu-id="c5587-144">**URLs de serviço Web do SFB 2015 CU5**</span><span class="sxs-lookup"><span data-stu-id="c5587-144">**SFB 2015 CU5 Web Service URLs**</span></span>

<span data-ttu-id="c5587-145">você precisará de URLs de serviço Web internos e externos para todos os pools do SfB 2015 implantados.</span><span class="sxs-lookup"><span data-stu-id="c5587-145">you'll need internal and external web service URLs for all SfB 2015 pools deployed.</span></span> <span data-ttu-id="c5587-146">Para obter essas informações, execute o seguinte a partir do Shell de Gerenciamento do Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="c5587-146">To obtain these, run the following from Skype for Business Management Shell:</span></span>
  
```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- <span data-ttu-id="c5587-147">Por ex.</span><span class="sxs-lookup"><span data-stu-id="c5587-147">Ex.</span></span> <span data-ttu-id="c5587-148">Interno: https://lyncwebint01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5587-148">Internal: https://lyncwebint01.contoso.com</span></span>

- <span data-ttu-id="c5587-149">Por ex.</span><span class="sxs-lookup"><span data-stu-id="c5587-149">Ex.</span></span> <span data-ttu-id="c5587-150">Externo: https://lyncwebext01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5587-150">External: https://lyncwebext01.contoso.com</span></span>

<span data-ttu-id="c5587-151">Se você estiver usando um servidor Standard Edition, a URL interna ficará em branco.</span><span class="sxs-lookup"><span data-stu-id="c5587-151">If you're using a Standard Edition server, the internal URL will be blank.</span></span> <span data-ttu-id="c5587-152">Nesse caso, use o fqdn do pool para a URL interna.</span><span class="sxs-lookup"><span data-stu-id="c5587-152">In this case, use the pool fqdn for the internal URL.</span></span>
  
## <a name="turn-on-modern-authentication-for-exo"></a><span data-ttu-id="c5587-153">Ativar a autenticação moderna para EXO</span><span class="sxs-lookup"><span data-stu-id="c5587-153">Turn on Modern Authentication for EXO</span></span>

<span data-ttu-id="c5587-154">Siga as instruções aqui: [Exchange Online: como habilitar seu locatário para autenticação moderna.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span><span class="sxs-lookup"><span data-stu-id="c5587-154">Follow the instructions here: [Exchange Online: How to enable your tenant for modern authentication.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span></span>
  
## <a name="turn-on-modern-authentication-for-sfbo"></a><span data-ttu-id="c5587-155">Ativar a autenticação moderna para SFBO</span><span class="sxs-lookup"><span data-stu-id="c5587-155">Turn on Modern Authentication for SFBO</span></span>

<span data-ttu-id="c5587-156">Siga as instruções aqui: [Skype for Business Online: habilitar seu locatário para autenticação moderna.](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</span><span class="sxs-lookup"><span data-stu-id="c5587-156">Follow the instructions here: [Skype for Business Online: Enable your tenant for modern authentication](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span>
  
## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a><span data-ttu-id="c5587-157">Ativar a autenticação moderna híbrida para o Exchange local</span><span class="sxs-lookup"><span data-stu-id="c5587-157">Turn on Hybrid Modern Authentication for Exchange on-premises</span></span>

<span data-ttu-id="c5587-158">Siga as instruções aqui: Como configurar o Exchange Server local para [usar a Autenticação Moderna Híbrida.](configure-exchange-server-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="c5587-158">Follow the instructions here: [How to configure Exchange Server on-premises to use Hybrid Modern Authentication](configure-exchange-server-for-hybrid-modern-authentication.md).</span></span>
  
## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a><span data-ttu-id="c5587-159">Ativar a autenticação moderna híbrida para o Skype for Business local</span><span class="sxs-lookup"><span data-stu-id="c5587-159">Turn on Hybrid Modern Authentication for Skype for Business on-premises</span></span>

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a><span data-ttu-id="c5587-160">Adicionar URLs de serviço Web local como SPNs no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c5587-160">Add on-premises web service URLs as SPNs in Azure Active Directory</span></span>

<span data-ttu-id="c5587-161">Agora você precisará executar comandos para adicionar as URLs (coletadas anteriormente) como Entidades de Serviço no SFBO.</span><span class="sxs-lookup"><span data-stu-id="c5587-161">Now you'll need to run commands to add the URLs (collected earlier) as Service Principals in SFBO.</span></span>
  
 <span data-ttu-id="c5587-162">**Observação** Os nomes de entidades de serviço (SPNs) identificam serviços Web e os associam a uma entidade de segurança (como um nome de conta ou grupo) para que o serviço possa agir em nome de um usuário autorizado.</span><span class="sxs-lookup"><span data-stu-id="c5587-162">**Note** Service principal names (SPNs) identify web services and associate them with a security principal (such as an account name or group) so that the service can act on the behalf of an authorized user.</span></span> <span data-ttu-id="c5587-163">Os clientes que fazem a autenticação em um servidor usam as informações contidas nos SPNs.</span><span class="sxs-lookup"><span data-stu-id="c5587-163">Clients authenticating to a server make use of information that's contained in SPNs.</span></span>
  
1. <span data-ttu-id="c5587-164">Primeiro, conecte-se ao Azure Active Directory (Azure AD) com [estas instruções.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="c5587-164">First, connect to Azure Active Directory (Azure AD) with [these instructions](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

2. <span data-ttu-id="c5587-165">Execute este comando, no local, para obter uma lista de URLs de serviço Web SFB.</span><span class="sxs-lookup"><span data-stu-id="c5587-165">Run this command, on-premises, to get a list of SFB web service URLs.</span></span>

   <span data-ttu-id="c5587-166">Observe que AppPrincipalId começa com `00000004` .</span><span class="sxs-lookup"><span data-stu-id="c5587-166">Note that the AppPrincipalId begins with `00000004`.</span></span> <span data-ttu-id="c5587-167">Isso corresponde ao Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="c5587-167">This corresponds to Skype for Business Online.</span></span>

   <span data-ttu-id="c5587-168">Anote (e captura de tela para comparação posterior) a saída desse comando, que incluirá uma URL de SE e WS, mas, principalmente, consiste em SPNs que começam com `00000004-0000-0ff1-ce00-000000000000/` .</span><span class="sxs-lookup"><span data-stu-id="c5587-168">Take note of (and screenshot for later comparison) the output of this command, which will include an SE and WS URL, but mostly consist of SPNs that begin with `00000004-0000-0ff1-ce00-000000000000/`.</span></span>

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. <span data-ttu-id="c5587-169">Se as  URLs SFB internas ou externas do local não tiverem (por exemplo, e precisaremos adicionar esses registros específicos https://lyncwebint01.contoso.com a essa https://lyncwebext01.contoso.com) lista).</span><span class="sxs-lookup"><span data-stu-id="c5587-169">If the internal **or** external SFB URLs from on-premises are missing (for example, https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com) we will need to add those specific records to this list.</span></span>

    <span data-ttu-id="c5587-170">Certifique-se de  *substituir as URLs de* exemplo abaixo por suas URLs reais nos comandos Adicionar!</span><span class="sxs-lookup"><span data-stu-id="c5587-170">Be sure to replace  *the example URLs* below with your actual URLs in the Add commands!</span></span>
  
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```
  
4. <span data-ttu-id="c5587-171">Verifique se os novos registros foram adicionados executando o comando **Get-MsolServicePrincipal** da etapa 2 novamente e verificando a saída.</span><span class="sxs-lookup"><span data-stu-id="c5587-171">Verify your new records were added by running the **Get-MsolServicePrincipal** command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="c5587-172">Compare a lista ou a captura de tela de antes com a nova lista de SPNs.</span><span class="sxs-lookup"><span data-stu-id="c5587-172">Compare the list or screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="c5587-173">Você também pode fazer uma captura de tela da nova lista para seus registros.</span><span class="sxs-lookup"><span data-stu-id="c5587-173">You might also screenshot the new list for your records.</span></span> <span data-ttu-id="c5587-174">Se você foi bem-sucedido, verá as duas novas URLs na lista.</span><span class="sxs-lookup"><span data-stu-id="c5587-174">If you were successful, you'll see the two new URLs in the list.</span></span> <span data-ttu-id="c5587-175">No nosso exemplo, a lista de SPNs agora incluirá as URLs específicas https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com/ e.</span><span class="sxs-lookup"><span data-stu-id="c5587-175">Going by our example, the list of SPNs will now include the specific URLs https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com/.</span></span>

### <a name="create-the-evosts-auth-server-object"></a><span data-ttu-id="c5587-176">Criar o objeto de servidor de auth do EvoSTS</span><span class="sxs-lookup"><span data-stu-id="c5587-176">Create the EvoSTS Auth Server Object</span></span>

<span data-ttu-id="c5587-177">Execute o seguinte comando no Shell de Gerenciamento do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c5587-177">Run the following command in the Skype for Business Management Shell.</span></span>
  
```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a><span data-ttu-id="c5587-178">Habilitar a autenticação moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="c5587-178">Enable Hybrid Modern Authentication</span></span>

<span data-ttu-id="c5587-179">Esta é a etapa que realmente liga a ma.</span><span class="sxs-lookup"><span data-stu-id="c5587-179">This is the step that actually turns on MA.</span></span> <span data-ttu-id="c5587-180">Todas as etapas anteriores podem ser executados com antecedência sem alterar o fluxo de autenticação do cliente.</span><span class="sxs-lookup"><span data-stu-id="c5587-180">All the previous steps can be run ahead of time without changing the client authentication flow.</span></span> <span data-ttu-id="c5587-181">Quando estiver pronto para alterar o fluxo de autenticação, execute este comando no Shell de Gerenciamento do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c5587-181">When you're ready to change the authentication flow, run this command in the Skype for Business Management Shell.</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a><span data-ttu-id="c5587-182">Verify</span><span class="sxs-lookup"><span data-stu-id="c5587-182">Verify</span></span>

<span data-ttu-id="c5587-183">Depois de habilitar o HMA, o próximo logon do cliente usará o novo fluxo de auth.</span><span class="sxs-lookup"><span data-stu-id="c5587-183">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="c5587-184">Observe que apenas ativar o HMA não disparará uma nova autenticação para qualquer cliente.</span><span class="sxs-lookup"><span data-stu-id="c5587-184">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="c5587-185">Os clientes são autenticados com base no tempo de vida dos tokens de autenticação e/ou certificados que eles têm.</span><span class="sxs-lookup"><span data-stu-id="c5587-185">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>
  
<span data-ttu-id="c5587-186">Para testar se o HMA está funcionando depois que você o habilitar, saia de um cliente SFB do Windows de teste e clique em 'excluir minhas credenciais'.</span><span class="sxs-lookup"><span data-stu-id="c5587-186">To test that HMA is working after you've enabled it, sign out of a test SFB Windows client and be sure to click 'delete my credentials'.</span></span> <span data-ttu-id="c5587-187">Entre novamente.</span><span class="sxs-lookup"><span data-stu-id="c5587-187">Sign in again.</span></span> <span data-ttu-id="c5587-188">Agora, o cliente deve usar o fluxo de Auth Moderno e seu logon incluirá um prompt do **Office 365** para uma conta "Trabalho ou escola", visto logo antes de o cliente entrar em contato com o servidor e fazer logon.</span><span class="sxs-lookup"><span data-stu-id="c5587-188">The client should now use the Modern Auth flow and your login will now include an **Office 365** prompt for a 'Work or school' account, seen right before the client contacts the server and logs you in.</span></span>
  
<span data-ttu-id="c5587-189">Você também deve verificar as "Informações de Configuração" para clientes do Skype for Business em busca de uma "Autoridade OAuth".</span><span class="sxs-lookup"><span data-stu-id="c5587-189">You should also check the 'Configuration Information' for Skype for Business Clients for an 'OAuth Authority'.</span></span> <span data-ttu-id="c5587-190">Para fazer isso no computador cliente, mantenha a tecla CTRL no mesmo momento em que clicar com o botão direito do mouse no ícone do Skype for Business na bandeja de notificação do Windows.</span><span class="sxs-lookup"><span data-stu-id="c5587-190">To do this on your client computer, hold down the CTRL key at the same time you right-click the Skype for Business Icon in the Windows Notification tray.</span></span> <span data-ttu-id="c5587-191">Clique **em Informações de** Configuração no menu exibido.</span><span class="sxs-lookup"><span data-stu-id="c5587-191">Click **Configuration Information** in the menu that appears.</span></span> <span data-ttu-id="c5587-192">Na janela "Informações de Configuração do Skype for Business" que aparecerá na área de trabalho, procure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c5587-192">In the 'Skype for Business Configuration Information' window that will appear on the desktop, look for the following:</span></span>
  
![As informações de configuração de um cliente Skype for Business usando a Autenticação Moderna mostram uma URL de autoridade OAUTH do Lync e do EWS de https://login.windows.net/common/oauth2/authorize .](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)
  
<span data-ttu-id="c5587-194">Você também deve segurar a tecla CTRL ao mesmo tempo em que clica com o botão direito do mouse no ícone do cliente do Outlook (também na bandeja Notificações do Windows) e clique em 'Status da Conexão'.</span><span class="sxs-lookup"><span data-stu-id="c5587-194">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="c5587-195">Procure o endereço SMTP do cliente em relação a um tipo de AuthN de "Portador", que representa o token de portador usado \* no OAuth.</span><span class="sxs-lookup"><span data-stu-id="c5587-195">Look for the client's SMTP address against an AuthN type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="c5587-196">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="c5587-196">Related articles</span></span>

<span data-ttu-id="c5587-197">[Link de volta para a visão geral da Autenticação Moderna.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c5587-197">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md).</span></span>
  
<span data-ttu-id="c5587-198">Você precisa saber como usar a Autenticação Moderna (ADAL) para seus clientes do Skype for Business?</span><span class="sxs-lookup"><span data-stu-id="c5587-198">Do you need to know how to use Modern Authentication (ADAL) for your Skype for Business clients?</span></span> <span data-ttu-id="c5587-199">Temos etapas [aqui.](https://technet.microsoft.com/library/mt710548.aspx)</span><span class="sxs-lookup"><span data-stu-id="c5587-199">We've got steps [here](https://technet.microsoft.com/library/mt710548.aspx).</span></span>
