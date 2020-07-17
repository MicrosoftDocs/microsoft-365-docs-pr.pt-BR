---
title: Substituição de TLS 1,0 e 1,1 no Office 365 GCC High e DoD
description: Discute como a Microsoft está movendo a data para a qual o suporte do TLS 1,1 e 1,0 nos ambientes GCC High e DoD no Office 365 e se prepara para usar o TLS 1,2.
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
ms.reviewer: lobrion
appliesto:
- Office 365 Business
ms.openlocfilehash: f61c0a809c4666981ee0f2d67eea21474b83a675
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024811"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="0626b-103">Substituição de TLS 1,0 e 1,1 no Office 365 GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="0626b-103">Deprecating TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0626b-104">O mundo está no meio de uma pandemia, e nós da Microsoft estamos cientes do impacto para nossos clientes e parceiros.</span><span class="sxs-lookup"><span data-stu-id="0626b-104">The world is in the middle of a pandemic, and we at Microsoft are aware of the impact on our customers and partners.</span></span> <span data-ttu-id="0626b-105">Para aliviar a carga de nossos clientes comerciais, suspendemos temporariamente qualquer imposição de preterimento do TLS 1.0 e 1.1.</span><span class="sxs-lookup"><span data-stu-id="0626b-105">To lighten the burden on our commercial customers, we have temporarily halted any deprecation enforcement of TLS 1.0 and 1.1.</span></span> <span data-ttu-id="0626b-106">Uma atualização será enviada em uma linha do tempo revisada após a crise atual se estabilizar.</span><span class="sxs-lookup"><span data-stu-id="0626b-106">An update will be sent on a revised timeline after the current crisis stabilizes.</span></span> <span data-ttu-id="0626b-107">(Este artigo é revisado para refletir a mudança.)</span><span class="sxs-lookup"><span data-stu-id="0626b-107">(This article is revised to reflect the change.)</span></span>

## <a name="summary"></a><span data-ttu-id="0626b-108">Resumo</span><span class="sxs-lookup"><span data-stu-id="0626b-108">Summary</span></span>

<span data-ttu-id="0626b-109">Para estar em conformidade com os padrões de conformidade mais recentes para o programa de gerenciamento de riscos e autorização (FedRAMP), estamos migrando para substituir as versões 1,1 e 1,0 do protocolo de segurança de camada de transporte (TLS) do Microsoft Office 365 para ambientes GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="0626b-109">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are moving to deprecate Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft Office 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="0626b-110">Essa alteração foi anunciada anteriormente pelo suporte da Microsoft em [preparação para o uso obrigatório do TLS 1,2 no Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="0626b-110">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="0626b-111">Entendemos que a segurança de seus dados é importante, e estamos comprometidos com a transparência das alterações que podem afetar o uso do serviço.</span><span class="sxs-lookup"><span data-stu-id="0626b-111">We understand that the security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="0626b-112">Embora a [implementação do Microsoft TLS 1,0](https://support.microsoft.com/help/3117336) não tenha vulnerabilidades de segurança conhecidas, continuamos a confirmar os padrões de conformidade do FedRAMP.</span><span class="sxs-lookup"><span data-stu-id="0626b-112">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="0626b-113">Portanto, preteriremos o TLS 1,1 e 1,0 no Office 365 em ambientes GCC High e DoD, a partir de 15 de janeiro de 2020.</span><span class="sxs-lookup"><span data-stu-id="0626b-113">Therefore, we will deprecate TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments starting on January 15, 2020.</span></span> <span data-ttu-id="0626b-114">Para obter informações sobre como remover as dependências de TLS 1,1 e 1,0, consulte o White Paper a seguir:</span><span class="sxs-lookup"><span data-stu-id="0626b-114">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="0626b-115">Resolvendo o problema de TLS 1,0</span><span class="sxs-lookup"><span data-stu-id="0626b-115">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

<span data-ttu-id="0626b-116">Ao se preparar para esta alteração para TLS 1,1 e 1,0, recomendamos que você use a versão 1,2 de TLS.</span><span class="sxs-lookup"><span data-stu-id="0626b-116">In preparing for this change for TLS 1.1 and 1.0, we recommend that you use TLS version 1.2 instead.</span></span> <span data-ttu-id="0626b-117">Para obter mais informações, consulte [preparação para o uso obrigatório do TLS 1,2 no Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="0626b-117">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

## <a name="more-information"></a><span data-ttu-id="0626b-118">Mais informações</span><span class="sxs-lookup"><span data-stu-id="0626b-118">More information</span></span>

<span data-ttu-id="0626b-119">A partir de 15 de janeiro de 2020, o Office 365 nos ambientes GCC High e DoD substituirá o TLS 1,1 e 1,0.</span><span class="sxs-lookup"><span data-stu-id="0626b-119">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="0626b-120">Em 15 de janeiro de 2020, todas as combinações de servidores cliente e servidores de navegador devem usar a versão 1,2 do TLS (ou uma versão posterior) para garantir que todas as conexões possam ser feitas sem problemas para os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="0626b-120">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="0626b-121">Isso pode exigir atualizações para determinadas combinações de servidores cliente e servidores de navegador.</span><span class="sxs-lookup"><span data-stu-id="0626b-121">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="0626b-122">Se você não atualizar para TLS versão 1,2 (ou uma versão posterior) em 15 de janeiro de 2020, você terá problemas ao tentar se conectar ao Office 365.</span><span class="sxs-lookup"><span data-stu-id="0626b-122">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="0626b-123">Além disso, será necessário atualizar para o TLS 1,2 (ou uma versão posterior) como parte da resolução.</span><span class="sxs-lookup"><span data-stu-id="0626b-123">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="0626b-124">Sabemos que os seguintes clientes não podem usar o TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="0626b-124">We know that the following clients cannot use TLS 1.2:</span></span>

- <span data-ttu-id="0626b-125">Android 4.3 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="0626b-125">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="0626b-126">Firefox versão 5.0 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="0626b-126">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="0626b-127">Internet Explorer 8 – 10 no Windows 7 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="0626b-127">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="0626b-128">Internet Explorer 10 no Windows Phone 8,0</span><span class="sxs-lookup"><span data-stu-id="0626b-128">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="0626b-129">Safari 6.0.4/OS X 10.8.4 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="0626b-129">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="0626b-130">Recomendamos que você atualize seus clientes para garantir que você mantenha o acesso ininterrupto ao Office 365 GCC High e o DoD.</span><span class="sxs-lookup"><span data-stu-id="0626b-130">We recommend that you update your clients to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="0626b-131">Embora a análise atual de conexões com o Microsoft Online Services mostre que a maioria dos serviços e pontos de extremidade Confira muito pouco uso de TLS 1,1 e 1,0, estamos fornecendo notificações sobre essa alteração para que você possa atualizar quaisquer clientes ou servidores afetados, conforme o necessário, antes que o suporte para TLS 1,1 e 1,0 seja encerrado.</span><span class="sxs-lookup"><span data-stu-id="0626b-131">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="0626b-132">Se você estiver usando uma infraestrutura local para cenários híbridos ou serviços de Federação do Active Directory (AD FS), verifique se a infraestrutura pode dar suporte a conexões de entrada e de saída que usam TLS 1,2 (ou uma versão posterior).</span><span class="sxs-lookup"><span data-stu-id="0626b-132">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="0626b-133">Além das interrupções que podem ocorrer se você usar os clientes listados que não podem usar o TLS 1,2, remover o TLS 1,1 e o 1,0 impedirá que você use o seguinte produto da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="0626b-133">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="0626b-134">Telefone Lync</span><span class="sxs-lookup"><span data-stu-id="0626b-134">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="0626b-135">Referências</span><span class="sxs-lookup"><span data-stu-id="0626b-135">References</span></span>

<span data-ttu-id="0626b-136">O artigo de suporte a seguir descreve orientações e referências para ajudar a garantir que seus clientes estejam usando o TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="0626b-136">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="0626b-137">Preparando o uso obrigatório do TLS 1,2 no Office 365</span><span class="sxs-lookup"><span data-stu-id="0626b-137">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
