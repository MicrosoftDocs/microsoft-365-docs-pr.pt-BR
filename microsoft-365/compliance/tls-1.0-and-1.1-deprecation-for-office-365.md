---
title: TLS 1.0 e 1.1 substituição para o Office 365
description: Descreve o TLS 1,0 e o 1,1 de substituição para o Office 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 270d04974cec9c36fa31a77bda401375fdac0471
ms.sourcegitcommit: 94f2f8e3e6bc3946d8b3cf798b3eb77a49ffd12a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/16/2020
ms.locfileid: "45148143"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a><span data-ttu-id="1d10a-103">TLS 1.0 e 1.1 substituição para o Office 365</span><span class="sxs-lookup"><span data-stu-id="1d10a-103">TLS 1.0 and 1.1 deprecation for Office 365</span></span>
> [!IMPORTANT]
> <span data-ttu-id="1d10a-104">Suspendemos temporariamente a imposição de substituição de TLS 1,0 e 1,1 para clientes comerciais devido ao covid-19, mas à medida que as cadeias de fornecimento foram ajustadas e determinados países são abertos novamente, redefinindo a imposição de TLS para iniciar 15 de outubro de 2020.</span><span class="sxs-lookup"><span data-stu-id="1d10a-104">We temporarily halted deprecation enforcement of TLS 1.0 and 1.1 for commercial customers due to covid-19, but as supply chains have adjusted and certain countries open back up, we are resetting the TLS enforcement to start Oct 15, 2020.</span></span> 

<span data-ttu-id="1d10a-105">A partir de 31 de outubro de 2018, os protocolos TLS (Transport Layer Security) 1,0 e 1,1 são preteridos para o serviço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="1d10a-105">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Office 365 service.</span></span> <span data-ttu-id="1d10a-106">O efeito para os usuários finais deve ser mínimo.</span><span class="sxs-lookup"><span data-stu-id="1d10a-106">The effect for end-users is expected to be minimal.</span></span> <span data-ttu-id="1d10a-107">Essa alteração foi divulgada por mais de dois anos, com o primeiro lançamento publicado em dezembro de 2017.</span><span class="sxs-lookup"><span data-stu-id="1d10a-107">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="1d10a-108">Este artigo destina-se apenas a abranger o cliente local do Office 365 em relação ao serviço do Office 365, mas também pode ser aplicado a problemas de TLS no local com o Office Web Apps e o servidor do Office Online.</span><span class="sxs-lookup"><span data-stu-id="1d10a-108">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

## <a name="office-and-tls-overview"></a><span data-ttu-id="1d10a-109">Visão geral do Office e do TLS</span><span class="sxs-lookup"><span data-stu-id="1d10a-109">Office and TLS overview</span></span>

<span data-ttu-id="1d10a-110">O cliente do Office depende do serviço Web do Windows (WINHTTP) para enviar e receber tráfego sobre protocolos TLS.</span><span class="sxs-lookup"><span data-stu-id="1d10a-110">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="1d10a-111">O cliente do Office pode usar TLS 1,2 se o serviço Web do computador local puder usar TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="1d10a-111">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="1d10a-112">Todos os clientes do Office podem usar protocolos TLS, já que os protocolos TLS e SSL fazem parte do sistema operacional e não são específicos para o cliente do Office.</span><span class="sxs-lookup"><span data-stu-id="1d10a-112">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="1d10a-113">No Windows 8 e nas versões posteriores</span><span class="sxs-lookup"><span data-stu-id="1d10a-113">On Windows 8 and later versions</span></span>

<span data-ttu-id="1d10a-114">Por padrão, os protocolos TLS 1,2 e 1,1 estão disponíveis se nenhum dispositivo de rede estiver configurado para rejeitar o tráfego TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="1d10a-114">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="1d10a-115">No Windows 7</span><span class="sxs-lookup"><span data-stu-id="1d10a-115">On Windows 7</span></span>

<span data-ttu-id="1d10a-116">Os protocolos TLS 1,1 e 1,2 não estão disponíveis sem a atualização [KB 3140245](https://support.microsoft.com/help/3140245) .</span><span class="sxs-lookup"><span data-stu-id="1d10a-116">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="1d10a-117">A atualização aborda esse problema e adiciona a seguinte subchave do registro:</span><span class="sxs-lookup"><span data-stu-id="1d10a-117">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="1d10a-118">Os usuários do Windows 7 que não têm essa atualização são afetados em 31 de outubro de 2018.</span><span class="sxs-lookup"><span data-stu-id="1d10a-118">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="1d10a-119">O [KB 3140245](https://support.microsoft.com/help/3140245) tem detalhes sobre como alterar as configurações de WinHTTP para habilitar os protocolos TLS.</span><span class="sxs-lookup"><span data-stu-id="1d10a-119">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="1d10a-120">Mais informações</span><span class="sxs-lookup"><span data-stu-id="1d10a-120">More information</span></span>

<span data-ttu-id="1d10a-121">O valor da chave de registro **DefaultSecureProtocols** que o artigo da base de conhecimento descreve determina quais protocolos de rede podem ser usados:</span><span class="sxs-lookup"><span data-stu-id="1d10a-121">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="1d10a-122">Valor DefaultSecureProtocols</span><span class="sxs-lookup"><span data-stu-id="1d10a-122">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="1d10a-123">Protocolo habilitado</span><span class="sxs-lookup"><span data-stu-id="1d10a-123">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="1d10a-124">0x00000008</span><span class="sxs-lookup"><span data-stu-id="1d10a-124">0x00000008</span></span>|<span data-ttu-id="1d10a-125">Habilitar SSL 2.0 por padrão</span><span class="sxs-lookup"><span data-stu-id="1d10a-125">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="1d10a-126">0x00000020</span><span class="sxs-lookup"><span data-stu-id="1d10a-126">0x00000020</span></span>|<span data-ttu-id="1d10a-127">Habilitar SSL 3.0 por padrão</span><span class="sxs-lookup"><span data-stu-id="1d10a-127">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="1d10a-128">0x00000080</span><span class="sxs-lookup"><span data-stu-id="1d10a-128">0x00000080</span></span>|<span data-ttu-id="1d10a-129">Habilitar TLS 1.0 por padrão</span><span class="sxs-lookup"><span data-stu-id="1d10a-129">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="1d10a-130">0x00000200</span><span class="sxs-lookup"><span data-stu-id="1d10a-130">0x00000200</span></span>|<span data-ttu-id="1d10a-131">Habilitar TLS 1.1 por padrão</span><span class="sxs-lookup"><span data-stu-id="1d10a-131">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="1d10a-132">0x00000800</span><span class="sxs-lookup"><span data-stu-id="1d10a-132">0x00000800</span></span>|<span data-ttu-id="1d10a-133">Habilitar TLS 1.2 por padrão</span><span class="sxs-lookup"><span data-stu-id="1d10a-133">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="1d10a-134">Clientes do Office e chaves do registro TLS</span><span class="sxs-lookup"><span data-stu-id="1d10a-134">Office clients and TLS registry keys</span></span>

<span data-ttu-id="1d10a-135">Você pode consultar [o KB 4057306 preparando para o uso obrigatório de TLS 1,2 no Office 365](https://support.microsoft.com/help/4057306).</span><span class="sxs-lookup"><span data-stu-id="1d10a-135">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="1d10a-136">Este é um artigo geral para administradores de ti e é uma documentação oficial sobre a alteração de TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="1d10a-136">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="1d10a-137">A tabela a seguir mostra os valores de chave do registro apropriados nos clientes do Office 365 após 31 de outubro de 2018.</span><span class="sxs-lookup"><span data-stu-id="1d10a-137">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="1d10a-138">Protocolos habilitados para o serviço do Office 365 após 31 de outubro de 2018</span><span class="sxs-lookup"><span data-stu-id="1d10a-138">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="1d10a-139">Valor hexadecimal</span><span class="sxs-lookup"><span data-stu-id="1d10a-139">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="1d10a-140">TLS 1,0 + 1,1 + 1,2</span><span class="sxs-lookup"><span data-stu-id="1d10a-140">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="1d10a-141">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="1d10a-141">0x00000A80</span></span>|
|<span data-ttu-id="1d10a-142">TLS 1,1 + 1,2</span><span class="sxs-lookup"><span data-stu-id="1d10a-142">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="1d10a-143">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="1d10a-143">0x00000A00</span></span>|
|<span data-ttu-id="1d10a-144">TLS 1,0 + 1,2</span><span class="sxs-lookup"><span data-stu-id="1d10a-144">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="1d10a-145">0x00000880</span><span class="sxs-lookup"><span data-stu-id="1d10a-145">0x00000880</span></span>|
|<span data-ttu-id="1d10a-146">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="1d10a-146">TLS 1.2</span></span>|<span data-ttu-id="1d10a-147">0x00000800</span><span class="sxs-lookup"><span data-stu-id="1d10a-147">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="1d10a-148">Não é recomendável usar os protocolos SSL 2,0 e 3,0, que também podem ser definidos usando a chave **DefaultSecureProtocols** .</span><span class="sxs-lookup"><span data-stu-id="1d10a-148">We don't recommend that you use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="1d10a-149">SSL 2,0 e 3,0 são considerados protocolos preteridos.</span><span class="sxs-lookup"><span data-stu-id="1d10a-149">SSL 2.0 and 3.0 are considered deprecated protocols.</span></span> <span data-ttu-id="1d10a-150">A prática recomendada é encerrar o uso do SSL 2,0 e do SSL 3,0, embora a decisão de fazer isso por fim dependa do que melhor atende às necessidades do seu produto.</span><span class="sxs-lookup"><span data-stu-id="1d10a-150">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="1d10a-151">Para obter mais informações sobre as vulnerabilidades de SSL 3,0, consulte [KB 3009008](https://support.microsoft.com/help/3009008).</span><span class="sxs-lookup"><span data-stu-id="1d10a-151">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="1d10a-152">Você pode usar a calculadora padrão do Windows no modo Programador para configurar os mesmos valores de chave de registro de referência.</span><span class="sxs-lookup"><span data-stu-id="1d10a-152">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="1d10a-153">Para obter mais informações, consulte [a atualização do KB 3140245 para habilitar o tls 1,1 e o tls 1,2 como protocolos de segurança padrão no WinHTTP no Windows](https://support.microsoft.com/help/3140245).</span><span class="sxs-lookup"><span data-stu-id="1d10a-153">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="1d10a-154">Independentemente de a atualização do Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)) ser instalada ou não, a subchave do registro DefaultSecureProtocols não está presente e deve ser adicionada manualmente ou por meio de um objeto de política de grupo (GPO).</span><span class="sxs-lookup"><span data-stu-id="1d10a-154">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="1d10a-155">Ou seja, a menos que você precise Personalizar que protocolos seguros estão habilitados ou restritos, essa chave não é necessária.</span><span class="sxs-lookup"><span data-stu-id="1d10a-155">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="1d10a-156">Você precisa apenas da atualização do Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)).</span><span class="sxs-lookup"><span data-stu-id="1d10a-156">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>
