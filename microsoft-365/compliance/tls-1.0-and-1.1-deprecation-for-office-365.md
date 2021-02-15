---
title: Desabilitando o TLS 1.0 e 1.1 para o Microsoft 365
description: Descreve a preteração e desabilitação do TLS 1.0 e 1.1 para o Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 669ab53739bfd108bdbe9077762272e6a4901865
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233093"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a><span data-ttu-id="2f0e0-103">Desabilitando o TLS 1.0 e 1.1 para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2f0e0-103">Disabling TLS 1.0 and 1.1 for Microsoft 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f0e0-104">Interrompemos temporariamente a desabilitação do TLS 1.0 e 1.1 para clientes comerciais devido ao COVID-19.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-104">We temporarily halted disablement of TLS 1.0 and 1.1 for commercial customers due to COVID-19.</span></span> <span data-ttu-id="2f0e0-105">Como as cadeias de fornecimento foram ajustadas e determinados países abriram o back up, reiniciamos a rollout de imposição do TLS 1.2 em 15 de outubro de 2020.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-105">As supply chains have adjusted and certain countries open back up, we restarted the TLS 1.2 enforcement rollout on October 15, 2020.</span></span> <span data-ttu-id="2f0e0-106">A rollout continuará nas seguintes semanas e meses.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-106">Rollout will continue over the following weeks and months.</span></span>

<span data-ttu-id="2f0e0-107">A partir de 31 de outubro de 2018, os protocolos TLS 1.0 e 1.1 foram preterido para o serviço do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-107">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Microsoft 365 service.</span></span> <span data-ttu-id="2f0e0-108">O efeito para os usuários finais é mínimo.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-108">The effect for end-users is minimal.</span></span> <span data-ttu-id="2f0e0-109">Essa alteração foi divulgada há mais de dois anos, com o primeiro comunicado público feito em dezembro de 2017.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-109">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="2f0e0-110">Este artigo destina-se apenas a abranger o cliente local do Office 365 em relação ao serviço do Office 365, mas também pode se aplicar a problemas de TLS locais com o Office e o Servidor do Office Online/Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-110">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

<span data-ttu-id="2f0e0-111">Para o SharePoint e o OneDrive, você precisará atualizar e configurar o .NET para dar suporte ao TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-111">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="2f0e0-112">Para obter informações, [consulte Como habilitar o TLS 1.2 em clientes.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="2f0e0-112">For information, see [How to enable TLS 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="office-365-and-tls-overview"></a><span data-ttu-id="2f0e0-113">Visão geral do Office 365 e do TLS</span><span class="sxs-lookup"><span data-stu-id="2f0e0-113">Office 365 and TLS overview</span></span>

<span data-ttu-id="2f0e0-114">O cliente do Office depende do winHTTP (serviço Web do Windows) para enviar e receber tráfego por protocolos TLS.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-114">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="2f0e0-115">O cliente do Office poderá usar o TLS 1.2 se o serviço Web do computador local puder usar o TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-115">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="2f0e0-116">Todos os clientes do Office podem usar protocolos TLS, pois os protocolos TLS e SSL fazem parte do sistema operacional e não são específicos do cliente do Office.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-116">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="2f0e0-117">No Windows 8 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="2f0e0-117">On Windows 8 and later versions</span></span>

<span data-ttu-id="2f0e0-118">Por padrão, os protocolos TLS 1.2 e 1.1 estão disponíveis se nenhum dispositivo de rede estiver configurado para rejeitar o tráfego TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-118">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="2f0e0-119">No Windows 7</span><span class="sxs-lookup"><span data-stu-id="2f0e0-119">On Windows 7</span></span>

<span data-ttu-id="2f0e0-120">Os protocolos TLS 1.1 e 1.2 não estão disponíveis sem a atualização [KB 3140245.](https://support.microsoft.com/help/3140245)</span><span class="sxs-lookup"><span data-stu-id="2f0e0-120">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="2f0e0-121">A atualização resolve esse problema e adiciona a seguinte sub-chave do Registro:</span><span class="sxs-lookup"><span data-stu-id="2f0e0-121">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="2f0e0-122">Os usuários do Windows 7 que não têm essa atualização são afetados a partir de 31 de outubro de 2018.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-122">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="2f0e0-123">[O KB 3140245](https://support.microsoft.com/help/3140245) tem detalhes sobre como alterar as configurações WINHTTP para habilitar protocolos TLS.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-123">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="2f0e0-124">Mais informações</span><span class="sxs-lookup"><span data-stu-id="2f0e0-124">More information</span></span>

<span data-ttu-id="2f0e0-125">O valor da chave do Registro **DefaultSecureProtocols** que o artigo da KB descreve determina quais protocolos de rede podem ser usados:</span><span class="sxs-lookup"><span data-stu-id="2f0e0-125">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="2f0e0-126">Valor de DefaultSecureProtocols</span><span class="sxs-lookup"><span data-stu-id="2f0e0-126">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="2f0e0-127">Protocolo habilitado</span><span class="sxs-lookup"><span data-stu-id="2f0e0-127">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="2f0e0-128">0x00000008</span><span class="sxs-lookup"><span data-stu-id="2f0e0-128">0x00000008</span></span>|<span data-ttu-id="2f0e0-129">Habilitar SSL 2.0 por padrão</span><span class="sxs-lookup"><span data-stu-id="2f0e0-129">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="2f0e0-130">0x00000020</span><span class="sxs-lookup"><span data-stu-id="2f0e0-130">0x00000020</span></span>|<span data-ttu-id="2f0e0-131">Habilitar SSL 3.0 por padrão</span><span class="sxs-lookup"><span data-stu-id="2f0e0-131">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="2f0e0-132">0x00000080</span><span class="sxs-lookup"><span data-stu-id="2f0e0-132">0x00000080</span></span>|<span data-ttu-id="2f0e0-133">Habilitar TLS 1.0 por padrão</span><span class="sxs-lookup"><span data-stu-id="2f0e0-133">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="2f0e0-134">0x00000200</span><span class="sxs-lookup"><span data-stu-id="2f0e0-134">0x00000200</span></span>|<span data-ttu-id="2f0e0-135">Habilitar TLS 1.1 por padrão</span><span class="sxs-lookup"><span data-stu-id="2f0e0-135">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="2f0e0-136">0x00000800</span><span class="sxs-lookup"><span data-stu-id="2f0e0-136">0x00000800</span></span>|<span data-ttu-id="2f0e0-137">Habilitar TLS 1.2 por padrão</span><span class="sxs-lookup"><span data-stu-id="2f0e0-137">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="2f0e0-138">Clientes do Office e chaves do Registro TLS</span><span class="sxs-lookup"><span data-stu-id="2f0e0-138">Office clients and TLS registry keys</span></span>

<span data-ttu-id="2f0e0-139">Você pode consultar a KB 4057306 Preparando-se para o uso obrigatório do [TLS 1.2 no Office 365.](https://support.microsoft.com/help/4057306)</span><span class="sxs-lookup"><span data-stu-id="2f0e0-139">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="2f0e0-140">Este é um artigo geral para administradores de IT e sua documentação oficial sobre a alteração do TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-140">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="2f0e0-141">A tabela a seguir mostra os valores de chave do Registro apropriados nos clientes do Office 365 após 31 de outubro de 2018.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-141">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="2f0e0-142">Protocolos habilitados para o serviço do Office 365 após 31 de outubro de 2018</span><span class="sxs-lookup"><span data-stu-id="2f0e0-142">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="2f0e0-143">Valor hexadecimal</span><span class="sxs-lookup"><span data-stu-id="2f0e0-143">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="2f0e0-144">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="2f0e0-144">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="2f0e0-145">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="2f0e0-145">0x00000A80</span></span>|
|<span data-ttu-id="2f0e0-146">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="2f0e0-146">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="2f0e0-147">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="2f0e0-147">0x00000A00</span></span>|
|<span data-ttu-id="2f0e0-148">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="2f0e0-148">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="2f0e0-149">0x00000880</span><span class="sxs-lookup"><span data-stu-id="2f0e0-149">0x00000880</span></span>|
|<span data-ttu-id="2f0e0-150">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="2f0e0-150">TLS 1.2</span></span>|<span data-ttu-id="2f0e0-151">0x00000800</span><span class="sxs-lookup"><span data-stu-id="2f0e0-151">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="2f0e0-152">Não use os protocolos SSL 2.0 e 3.0, que também podem ser definidos usando a **chave DefaultSecureProtocols.**</span><span class="sxs-lookup"><span data-stu-id="2f0e0-152">Don't use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="2f0e0-153">O SSL 2.0 e 3.0 são considerados protocolos desatualizados e inseguros.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-153">SSL 2.0 and 3.0 are considered outdated and insecure protocols.</span></span> <span data-ttu-id="2f0e0-154">A prática ideal é encerrar o uso de SSL 2.0 e SSL 3.0, embora a decisão de fazer isso em última análise dependa do que melhor atende às necessidades do seu produto.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-154">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="2f0e0-155">Para obter mais informações sobre vulnerabilidades do SSL 3.0, consulte [kb 3009008](https://support.microsoft.com/help/3009008).</span><span class="sxs-lookup"><span data-stu-id="2f0e0-155">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="2f0e0-156">Você pode usar a Calculadora do Windows padrão no modo Programador para configurar os mesmos valores de chave de registro de referência.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-156">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="2f0e0-157">Para obter mais informações, consulte a Atualização [KB 3140245 para habilitar o TLS 1.1 e o TLS 1.2](https://support.microsoft.com/help/3140245)como protocolos seguros padrão no WinHTTP no Windows.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-157">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="2f0e0-158">Independentemente de a atualização do Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)) estar instalada ou não, a sub-chave do Registro DefaultSecureProtocols não está presente e deve ser adicionada manualmente ou por meio de um OBJETO de política de grupo (GPO).</span><span class="sxs-lookup"><span data-stu-id="2f0e0-158">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="2f0e0-159">Ou seja, a menos que você tenha que personalizar quais protocolos seguros estão habilitados ou restritos, essa chave não é necessária.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-159">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="2f0e0-160">Você só precisa da atualização do Windows 7 SP1 ([KB 3140245).](https://support.microsoft.com/help/3140245)</span><span class="sxs-lookup"><span data-stu-id="2f0e0-160">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a><span data-ttu-id="2f0e0-161">Atualizar e configurar o .NET Framework para dar suporte a TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="2f0e0-161">Update and configure the .NET Framework to support TLS 1.2</span></span>

<span data-ttu-id="2f0e0-162">Você precisará atualizar aplicativos que chamam as APIs do Microsoft 365 sobre TLS 1.0 ou TLS 1.1 para usar o TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-162">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="2f0e0-163">O .NET 4.5 assume como padrão o TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="2f0e0-163">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="2f0e0-164">Para atualizar sua configuração do .NET, consulte Como habilitar o [TLS (Transport Layer Security) 1.2 em clientes.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="2f0e0-164">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="2f0e0-165">Mais informações</span><span class="sxs-lookup"><span data-stu-id="2f0e0-165">More information</span></span>

<span data-ttu-id="2f0e0-166">Para obter mais informações, consulte Preparando-se para o uso obrigatório [do TLS 1.2 no Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="2f0e0-166">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>
