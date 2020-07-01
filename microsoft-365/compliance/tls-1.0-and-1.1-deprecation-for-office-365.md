---
title: TLS 1,0 e 1,1 de substituição para o Office 365
description: Descreve o TLS 1,0 e o 1,1 de substituição para o Office 365.
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 611b6970c3ecb95f4cdf046b96a5e3aa9155391d
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937314"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a><span data-ttu-id="5dd0f-103">TLS 1,0 e 1,1 de substituição para o Office 365</span><span class="sxs-lookup"><span data-stu-id="5dd0f-103">TLS 1.0 and 1.1 deprecation for Office 365</span></span>

<span data-ttu-id="5dd0f-104">A partir de 31 de outubro de 2018, os protocolos TLS (Transport Layer Security) 1,0 e 1,1 são preteridos para o serviço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5dd0f-104">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Office 365 service.</span></span> <span data-ttu-id="5dd0f-105">O efeito para os usuários finais deve ser mínimo.</span><span class="sxs-lookup"><span data-stu-id="5dd0f-105">The effect for end-users is expected to be minimal.</span></span> <span data-ttu-id="5dd0f-106">Essa alteração foi publicada por quase dois anos, com o primeiro lançamento publicado em dezembro de 2017.</span><span class="sxs-lookup"><span data-stu-id="5dd0f-106">This change was publicized for almost two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="5dd0f-107">Este artigo destina-se apenas a abranger o cliente local do Office 365 em relação ao serviço do Office 365, mas também pode ser aplicado a problemas de TLS no local com o Office Web Apps e o servidor do Office Online.</span><span class="sxs-lookup"><span data-stu-id="5dd0f-107">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

## <a name="office-and-tls-overview"></a><span data-ttu-id="5dd0f-108">Visão geral do Office e do TLS</span><span class="sxs-lookup"><span data-stu-id="5dd0f-108">Office and TLS overview</span></span>

<span data-ttu-id="5dd0f-109">O cliente do Office depende do serviço Web do Windows (WINHTTP) para enviar e receber tráfego sobre protocolos TLS.</span><span class="sxs-lookup"><span data-stu-id="5dd0f-109">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="5dd0f-110">O cliente do Office pode usar TLS 1,2 se o serviço Web do computador local puder usar TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="5dd0f-110">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="5dd0f-111">Todos os clientes do Office podem usar protocolos TLS, já que os protocolos TLS e SSL fazem parte do sistema operacional e não são específicos para o cliente do Office.</span><span class="sxs-lookup"><span data-stu-id="5dd0f-111">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="5dd0f-112">No Windows 8 e nas versões posteriores</span><span class="sxs-lookup"><span data-stu-id="5dd0f-112">On Windows 8 and later versions</span></span>

<span data-ttu-id="5dd0f-113">Por padrão, os protocolos TLS 1,2 e 1,1 estão disponíveis se nenhum dispositivo de rede estiver configurado para rejeitar o tráfego TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="5dd0f-113">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="5dd0f-114">No Windows 7</span><span class="sxs-lookup"><span data-stu-id="5dd0f-114">On Windows 7</span></span>

<span data-ttu-id="5dd0f-115">Os protocolos TLS 1,1 e 1,2 não estão disponíveis sem a atualização [KB 3140245](https://support.microsoft.com/help/3140245) .</span><span class="sxs-lookup"><span data-stu-id="5dd0f-115">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="5dd0f-116">A atualização aborda esse problema e adiciona a seguinte subchave do registro:</span><span class="sxs-lookup"><span data-stu-id="5dd0f-116">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="5dd0f-117">Os usuários do Windows 7 que não têm essa atualização são afetados em 31 de outubro de 2018.</span><span class="sxs-lookup"><span data-stu-id="5dd0f-117">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="5dd0f-118">O [KB 3140245](https://support.microsoft.com/help/3140245) tem detalhes sobre como alterar as configurações de WinHTTP para habilitar os protocolos TLS.</span><span class="sxs-lookup"><span data-stu-id="5dd0f-118">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="5dd0f-119">Mais informações</span><span class="sxs-lookup"><span data-stu-id="5dd0f-119">More information</span></span>

<span data-ttu-id="5dd0f-120">O valor da chave de registro **DefaultSecureProtocols** que o artigo da base de conhecimento descreve determina quais protocolos de rede podem ser usados:</span><span class="sxs-lookup"><span data-stu-id="5dd0f-120">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="5dd0f-121">Valor DefaultSecureProtocols</span><span class="sxs-lookup"><span data-stu-id="5dd0f-121">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="5dd0f-122">Protocolo habilitado</span><span class="sxs-lookup"><span data-stu-id="5dd0f-122">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="5dd0f-123">0x00000008</span><span class="sxs-lookup"><span data-stu-id="5dd0f-123">0x00000008</span></span>|<span data-ttu-id="5dd0f-124">Habilitar SSL 2.0 por padrão</span><span class="sxs-lookup"><span data-stu-id="5dd0f-124">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="5dd0f-125">0x00000020</span><span class="sxs-lookup"><span data-stu-id="5dd0f-125">0x00000020</span></span>|<span data-ttu-id="5dd0f-126">Habilitar SSL 3.0 por padrão</span><span class="sxs-lookup"><span data-stu-id="5dd0f-126">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="5dd0f-127">0x00000080</span><span class="sxs-lookup"><span data-stu-id="5dd0f-127">0x00000080</span></span>|<span data-ttu-id="5dd0f-128">Habilitar TLS 1.0 por padrão</span><span class="sxs-lookup"><span data-stu-id="5dd0f-128">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="5dd0f-129">0x00000200</span><span class="sxs-lookup"><span data-stu-id="5dd0f-129">0x00000200</span></span>|<span data-ttu-id="5dd0f-130">Habilitar TLS 1.1 por padrão</span><span class="sxs-lookup"><span data-stu-id="5dd0f-130">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="5dd0f-131">0x00000800</span><span class="sxs-lookup"><span data-stu-id="5dd0f-131">0x00000800</span></span>|<span data-ttu-id="5dd0f-132">Habilitar TLS 1.2 por padrão</span><span class="sxs-lookup"><span data-stu-id="5dd0f-132">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="5dd0f-133">Clientes do Office e chaves do registro TLS</span><span class="sxs-lookup"><span data-stu-id="5dd0f-133">Office clients and TLS registry keys</span></span>

<span data-ttu-id="5dd0f-134">Você pode consultar [o KB 4057306 preparando para o uso obrigatório de TLS 1,2 no Office 365](https://support.microsoft.com/help/4057306).</span><span class="sxs-lookup"><span data-stu-id="5dd0f-134">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="5dd0f-135">Este é um artigo geral para administradores de ti e é uma documentação oficial sobre a alteração de TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="5dd0f-135">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="5dd0f-136">A tabela a seguir mostra os valores de chave do registro apropriados nos clientes do Office 365 após 31 de outubro de 2018.</span><span class="sxs-lookup"><span data-stu-id="5dd0f-136">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="5dd0f-137">Protocolos habilitados para o serviço do Office 365 após 31 de outubro de 2018</span><span class="sxs-lookup"><span data-stu-id="5dd0f-137">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="5dd0f-138">Valor hexadecimal</span><span class="sxs-lookup"><span data-stu-id="5dd0f-138">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="5dd0f-139">TLS 1,0 + 1,1 + 1,2</span><span class="sxs-lookup"><span data-stu-id="5dd0f-139">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="5dd0f-140">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="5dd0f-140">0x00000A80</span></span>|
|<span data-ttu-id="5dd0f-141">TLS 1,1 + 1,2</span><span class="sxs-lookup"><span data-stu-id="5dd0f-141">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="5dd0f-142">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="5dd0f-142">0x00000A00</span></span>|
|<span data-ttu-id="5dd0f-143">TLS 1,0 + 1,2</span><span class="sxs-lookup"><span data-stu-id="5dd0f-143">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="5dd0f-144">0x00000880</span><span class="sxs-lookup"><span data-stu-id="5dd0f-144">0x00000880</span></span>|
|<span data-ttu-id="5dd0f-145">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="5dd0f-145">TLS 1.2</span></span>|<span data-ttu-id="5dd0f-146">0x00000800</span><span class="sxs-lookup"><span data-stu-id="5dd0f-146">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="5dd0f-147">Não é recomendável usar os protocolos SSL 2,0 e 3,0, que também podem ser definidos usando a chave **DefaultSecureProtocols** .</span><span class="sxs-lookup"><span data-stu-id="5dd0f-147">We don't recommend that you use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="5dd0f-148">SSL 2,0 e 3,0 são considerados protocolos preteridos.</span><span class="sxs-lookup"><span data-stu-id="5dd0f-148">SSL 2.0 and 3.0 are considered deprecated protocols.</span></span> <span data-ttu-id="5dd0f-149">A prática recomendada é encerrar o uso do SSL 2,0 e do SSL 3,0, embora a decisão de fazer isso por fim dependa do que melhor atende às necessidades do seu produto.</span><span class="sxs-lookup"><span data-stu-id="5dd0f-149">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="5dd0f-150">Para obter mais informações sobre as vulnerabilidades de SSL 3,0, consulte [KB 3009008](https://support.microsoft.com/help/3009008).</span><span class="sxs-lookup"><span data-stu-id="5dd0f-150">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="5dd0f-151">Você pode usar a calculadora padrão do Windows no modo Programador para configurar os mesmos valores de chave de registro de referência.</span><span class="sxs-lookup"><span data-stu-id="5dd0f-151">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="5dd0f-152">Para obter mais informações, consulte [a atualização do KB 3140245 para habilitar o tls 1,1 e o tls 1,2 como protocolos de segurança padrão no WinHTTP no Windows](https://support.microsoft.com/help/3140245).</span><span class="sxs-lookup"><span data-stu-id="5dd0f-152">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="5dd0f-153">Independentemente de a atualização do Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)) ser instalada ou não, a subchave do registro DefaultSecureProtocols não está presente e deve ser adicionada manualmente ou por meio de um objeto de política de grupo (GPO).</span><span class="sxs-lookup"><span data-stu-id="5dd0f-153">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="5dd0f-154">Ou seja, a menos que você precise Personalizar que protocolos seguros estão habilitados ou restritos, essa chave não é necessária.</span><span class="sxs-lookup"><span data-stu-id="5dd0f-154">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="5dd0f-155">Você precisa apenas da atualização do Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)).</span><span class="sxs-lookup"><span data-stu-id="5dd0f-155">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>
