---
title: Desabilitando o TLS 1.0 e 1.1 no Microsoft 365 GCC High e DoD
description: Discute como a Microsoft está desabilitando o suporte para TLS 1.1 e 1.0 em ambientes GCC High e DoD no Microsoft 365.
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: 16a02985107c5f578d6d6c21bf2efc6e80297951
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919337"
---
# <a name="disabling-tls-10-and-11-in-microsoft-365-gcc-high-and-dod"></a><span data-ttu-id="8097f-103">Desabilitando o TLS 1.0 e 1.1 no Microsoft 365 GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="8097f-103">Disabling TLS 1.0 and 1.1 in Microsoft 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="8097f-104">Resumo</span><span class="sxs-lookup"><span data-stu-id="8097f-104">Summary</span></span>

<span data-ttu-id="8097f-105">Para cumprir os padrões de conformidade mais recentes do Programa Federal de Gerenciamento de Riscos e Autorizações (FedRAMP), estamos desabilitando as versões 1.1 e 1.0 do TLS no Microsoft 365 para ambientes GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="8097f-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are disabling Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="8097f-106">Essa alteração foi anunciada anteriormente por meio do Suporte da Microsoft em Preparação para o uso obrigatório do [TLS 1.2 no Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="8097f-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="8097f-107">A segurança de seus dados é importante e estamos comprometidos com a transparência sobre as alterações que podem afetar seu uso do serviço.</span><span class="sxs-lookup"><span data-stu-id="8097f-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="8097f-108">Embora a implementação do [Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) não tenha vulnerabilidades de segurança conhecidas, permanecemos comprometidos com os padrões de conformidade fedRAMP.</span><span class="sxs-lookup"><span data-stu-id="8097f-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="8097f-109">Portanto, desabilitamos o TLS 1.1 e 1.0 no Microsoft 365 em ambientes GCC High e DoD em 15 de janeiro de 2020.</span><span class="sxs-lookup"><span data-stu-id="8097f-109">Therefore, we disabled TLS 1.1 and 1.0 in Microsoft 365 in GCC High and DoD environments on January 15, 2020.</span></span> <span data-ttu-id="8097f-110">Para obter informações sobre como remover as dependências do TLS 1.1 e 1.0, consulte o seguinte white paper:</span><span class="sxs-lookup"><span data-stu-id="8097f-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="8097f-111">Solução do problema TLS 1.0</span><span class="sxs-lookup"><span data-stu-id="8097f-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a><span data-ttu-id="8097f-112">Mais informações</span><span class="sxs-lookup"><span data-stu-id="8097f-112">More information</span></span>

<span data-ttu-id="8097f-113">A partir de 15 de janeiro de 2020, o Microsoft 365 nos ambientes GCC High e DoD desabilitará o TLS 1.1 e 1.0.</span><span class="sxs-lookup"><span data-stu-id="8097f-113">Starting on January 15, 2020, Microsoft 365 in the GCC High and DoD environments will disable TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="8097f-114">Até 15 de janeiro de 2020, todas as combinações de servidores cliente e servidores de navegador devem usar o TLS versão 1.2 (ou uma versão posterior) para garantir que todas as conexões possam ser feitas sem problemas com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8097f-114">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Microsoft 365.</span></span> <span data-ttu-id="8097f-115">Isso pode exigir atualizações para determinadas combinações de servidores cliente e servidores de navegador.</span><span class="sxs-lookup"><span data-stu-id="8097f-115">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="8097f-116">Para o SharePoint e o OneDrive, você precisará atualizar e configurar o .NET para dar suporte ao TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="8097f-116">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="8097f-117">Para obter informações, [consulte Como habilitar o TLS 1.2 em clientes](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span><span class="sxs-lookup"><span data-stu-id="8097f-117">For information, see [How to enable TLS 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

<span data-ttu-id="8097f-118">Você deve atualizar seus computadores clientes para garantir que você mantenha o acesso ininterrupto ao Office 365 GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="8097f-118">You must update your client computers to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="8097f-119">Você precisará atualizar aplicativos que chamam APIs do Microsoft 365 por TLS 1.0 ou TLS 1.1 para usar o TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="8097f-119">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="8097f-120">O .NET 4.5 é padrão para TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="8097f-120">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="8097f-121">Para atualizar sua configuração .NET, consulte [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span><span class="sxs-lookup"><span data-stu-id="8097f-121">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span> <span data-ttu-id="8097f-122">Para obter mais informações, consulte Preparando-se para o uso obrigatório [do TLS 1.2 no Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="8097f-122">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="8097f-123">Sabemos que os seguintes aplicativos cliente não podem usar o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="8097f-123">We know that the following client applications cannot use TLS 1.2:</span></span>

- <span data-ttu-id="8097f-124">Android 4.3 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="8097f-124">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="8097f-125">Firefox versão 5.0 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="8097f-125">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="8097f-126">Internet Explorer 8–10 no Windows 7 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="8097f-126">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="8097f-127">Internet Explorer 10 no Windows Phone 8.0</span><span class="sxs-lookup"><span data-stu-id="8097f-127">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="8097f-128">Safari 6.0.4/OS X 10.8.4 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="8097f-128">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="8097f-129">Embora a análise atual das conexões com os serviços do Microsoft Online mostre que a maioria dos serviços e pontos de extremidade vê muito pouco uso do TLS 1.1 e 1.0, estamos notificação dessa alteração para que você possa atualizar todos os clientes ou servidores afetados conforme necessário antes do suporte para o TLS 1.1 e 1.0 terminar.</span><span class="sxs-lookup"><span data-stu-id="8097f-129">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we're providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="8097f-130">Se você estiver usando qualquer infraestrutura local para cenários híbridos ou Serviços de Federação do Active Directory (AD FS), certifique-se de que a infraestrutura possa dar suporte a conexões de entrada e de saída que usam TLS 1.2 (ou uma versão posterior).</span><span class="sxs-lookup"><span data-stu-id="8097f-130">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="8097f-131">Além das paralisações que você pode experimentar se você usar os clientes listados que não podem usar o TLS 1.2, remover o TLS 1.1 e 1.0 impedirá que você possa usar o seguinte produto da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="8097f-131">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="8097f-132">Telefone do Lync</span><span class="sxs-lookup"><span data-stu-id="8097f-132">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="8097f-133">Referências</span><span class="sxs-lookup"><span data-stu-id="8097f-133">References</span></span>

<span data-ttu-id="8097f-134">Para obter orientações e referências para ajudar a garantir que seus clientes estão usando o TLS 1.2, consulte Preparando-se para o uso obrigatório do [TLS 1.2 no Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="8097f-134">For guidance and references to help make sure that your clients are using TLS 1.2, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>