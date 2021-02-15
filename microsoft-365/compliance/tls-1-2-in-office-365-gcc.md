---
title: Desabilitando o TLS 1.0 e 1.1 no Office 365 GCC High e DoD
description: Discute como a Microsoft está desabilitando o suporte para TLS 1.1 e 1.0 em ambientes GCC High e DoD no Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: shmehta
appliesto:
- Office 365 Business
ms.openlocfilehash: a0b1fecc9991cd7ba4ac915d3d684d43714014af
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233747"
---
# <a name="disabling-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="ef422-103">Desabilitando o TLS 1.0 e 1.1 no Office 365 GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="ef422-103">Disabling TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="ef422-104">Resumo</span><span class="sxs-lookup"><span data-stu-id="ef422-104">Summary</span></span>

<span data-ttu-id="ef422-105">Para atender aos padrões de conformidade mais recentes do FedRAMP (Federal Risk and Authorization Management Program), estamos desabilitando as versões 1.1 e 1.0 do Transport Layer Security (TLS) no Microsoft 365 para ambientes GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="ef422-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are disabling Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="ef422-106">Essa alteração foi anunciada anteriormente por meio do Suporte da Microsoft na preparação para o uso obrigatório do [TLS 1.2 no Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="ef422-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="ef422-107">A segurança de seus dados é importante, e estamos comprometidos com a transparência sobre as alterações que podem afetar o uso do serviço.</span><span class="sxs-lookup"><span data-stu-id="ef422-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="ef422-108">Embora a [implementação do Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) não tenha vulnerabilidades de segurança conhecidas, permanecemos comprometidos com os padrões de conformidade do FedRAMP.</span><span class="sxs-lookup"><span data-stu-id="ef422-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="ef422-109">Portanto, desabilitamos o TLS 1.1 e 1.0 nos ambientes GCC High e DoD do Office 365 em 15 de janeiro de 2020.</span><span class="sxs-lookup"><span data-stu-id="ef422-109">Therefore, we disabled TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments on January 15, 2020.</span></span> <span data-ttu-id="ef422-110">Para obter informações sobre como remover as dependências do TLS 1.1 e 1.0, consulte o seguinte white paper:</span><span class="sxs-lookup"><span data-stu-id="ef422-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="ef422-111">Resolvendo o problema do TLS 1.0</span><span class="sxs-lookup"><span data-stu-id="ef422-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a><span data-ttu-id="ef422-112">Mais informações</span><span class="sxs-lookup"><span data-stu-id="ef422-112">More information</span></span>

<span data-ttu-id="ef422-113">A partir de 15 de janeiro de 2020, o Office 365 nos ambientes GCC High e DoD preterirá os TLS 1.1 e 1.0.</span><span class="sxs-lookup"><span data-stu-id="ef422-113">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="ef422-114">Até 15 de janeiro de 2020, todas as combinações de servidores cliente e servidores de navegador devem usar o TLS versão 1.2 (ou uma versão posterior) para garantir que todas as conexões possam ser feitas sem problemas com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ef422-114">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="ef422-115">Isso pode exigir atualizações para determinadas combinações de servidores cliente e servidores do navegador.</span><span class="sxs-lookup"><span data-stu-id="ef422-115">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="ef422-116">Se você não atualizar para o TLS versão 1.2 (ou uma versão posterior) até 15 de janeiro de 2020, terá problemas ao tentar se conectar ao Office 365.</span><span class="sxs-lookup"><span data-stu-id="ef422-116">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="ef422-117">Além disso, será necessário atualizar para o TLS 1.2 (ou uma versão posterior) como parte da resolução.</span><span class="sxs-lookup"><span data-stu-id="ef422-117">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="ef422-118">Você deve atualizar seus computadores clientes para garantir que mantenha acesso ininterrupto ao Office 365 GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="ef422-118">You must update your client computers to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="ef422-119">Você precisará atualizar aplicativos que chamam as APIs do Microsoft 365 sobre TLS 1.0 ou TLS 1.1 para usar o TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="ef422-119">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="ef422-120">O .NET 4.5 assume como padrão o TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="ef422-120">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="ef422-121">Para atualizar sua configuração do .NET, consulte Como habilitar o [TLS (Transport Layer Security) 1.2 em clientes.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="ef422-121">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span> <span data-ttu-id="ef422-122">Para obter mais informações, consulte Preparando-se para o uso obrigatório [do TLS 1.2 no Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="ef422-122">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="ef422-123">Sabemos que os seguintes aplicativos cliente não podem usar o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="ef422-123">We know that the following client applications cannot use TLS 1.2:</span></span>

- <span data-ttu-id="ef422-124">Android 4.3 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="ef422-124">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="ef422-125">Firefox versão 5.0 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="ef422-125">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="ef422-126">Internet Explorer 8–10 no Windows 7 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="ef422-126">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="ef422-127">Internet Explorer 10 no Windows Phone 8.0</span><span class="sxs-lookup"><span data-stu-id="ef422-127">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="ef422-128">Safari 6.0.4/OS X 10.8.4 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="ef422-128">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="ef422-129">Embora a análise atual das conexões com os serviços Do Microsoft Online mostre que a maioria dos serviços e pontos de extremidade vê muito pouco uso do TLS 1.1 e 1.0, estamos fornecendo um aviso dessa alteração para que você possa atualizar todos os clientes ou servidores afetados conforme necessário antes que o suporte para TLS 1.1 e 1.0 termine.</span><span class="sxs-lookup"><span data-stu-id="ef422-129">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we're providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="ef422-130">Se você estiver usando qualquer infraestrutura local para cenários híbridos ou Serviços de Federação do Active Directory (AD FS), certifique-se de que a infraestrutura possa suportar conexões de entrada e saída que usam TLS 1.2 (ou uma versão posterior).</span><span class="sxs-lookup"><span data-stu-id="ef422-130">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="ef422-131">Além das paralisações que podem ocorrer se você usar os clientes listados que não podem usar o TLS 1.2, remover o TLS 1.1 e 1.0 impedirá que você possa usar o seguinte produto da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="ef422-131">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="ef422-132">Telefone do Lync</span><span class="sxs-lookup"><span data-stu-id="ef422-132">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="ef422-133">Referências</span><span class="sxs-lookup"><span data-stu-id="ef422-133">References</span></span>

<span data-ttu-id="ef422-134">O artigo de suporte a seguir descreve orientações e referências para ajudar a garantir que seus clientes estão usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="ef422-134">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="ef422-135">Preparando-se para o uso obrigatório do TLS 1.2 no Office 365</span><span class="sxs-lookup"><span data-stu-id="ef422-135">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
