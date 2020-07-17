---
title: Substituição de TLS 1,0 e 1,1 no Office 365 GCC High e DoD
description: Discute como a Microsoft está movendo a data para a qual o suporte do TLS 1,1 e 1,0 nos ambientes GCC High e DoD no Office 365 e se prepara para usar o TLS 1,2.
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
ms.openlocfilehash: 76e9b203e58ba7fa23942ea42810456e3bee377d
ms.sourcegitcommit: 42b618231e9f608f3ae7226a313b0366601d0ea2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158876"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="d9f16-103">Substituição de TLS 1,0 e 1,1 no Office 365 GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="d9f16-103">Deprecating TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="d9f16-104">Resumo</span><span class="sxs-lookup"><span data-stu-id="d9f16-104">Summary</span></span>

<span data-ttu-id="d9f16-105">Para estar em conformidade com os padrões de conformidade mais recentes para o programa de gerenciamento de riscos e autorização (FedRAMP), estamos reprovando as versões 1,1 e 1,0 do protocolo de segurança da camada de transporte (TLS) do Microsoft Office 365 para os ambientes GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="d9f16-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are deprecating Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft Office 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="d9f16-106">Essa alteração foi anunciada anteriormente pelo suporte da Microsoft em [preparação para o uso obrigatório do TLS 1,2 no Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="d9f16-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="d9f16-107">A segurança de seus dados é importante, e temos o compromisso de transparência das alterações que podem afetar o uso do serviço.</span><span class="sxs-lookup"><span data-stu-id="d9f16-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="d9f16-108">Embora a [implementação do Microsoft TLS 1,0](https://support.microsoft.com/help/3117336) não tenha vulnerabilidades de segurança conhecidas, continuamos a confirmar os padrões de conformidade do FedRAMP.</span><span class="sxs-lookup"><span data-stu-id="d9f16-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="d9f16-109">Portanto, preteriremos o TLS 1,1 e 1,0 no Office 365 em ambientes GCC High e DoD, a partir de 15 de janeiro de 2020.</span><span class="sxs-lookup"><span data-stu-id="d9f16-109">Therefore, we will deprecate TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments starting on January 15, 2020.</span></span> <span data-ttu-id="d9f16-110">Para obter informações sobre como remover as dependências de TLS 1,1 e 1,0, consulte o White Paper a seguir:</span><span class="sxs-lookup"><span data-stu-id="d9f16-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="d9f16-111">Resolvendo o problema de TLS 1,0</span><span class="sxs-lookup"><span data-stu-id="d9f16-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

<span data-ttu-id="d9f16-112">Ao se preparar para esta alteração para TLS 1,1 e 1,0, recomendamos que você use a versão 1,2 de TLS.</span><span class="sxs-lookup"><span data-stu-id="d9f16-112">In preparing for this change for TLS 1.1 and 1.0, we recommend that you use TLS version 1.2 instead.</span></span> <span data-ttu-id="d9f16-113">Para obter mais informações, consulte [preparação para o uso obrigatório do TLS 1,2 no Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="d9f16-113">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

## <a name="more-information"></a><span data-ttu-id="d9f16-114">Mais informações</span><span class="sxs-lookup"><span data-stu-id="d9f16-114">More information</span></span>

<span data-ttu-id="d9f16-115">A partir de 15 de janeiro de 2020, o Office 365 nos ambientes GCC High e DoD substituirá o TLS 1,1 e 1,0.</span><span class="sxs-lookup"><span data-stu-id="d9f16-115">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="d9f16-116">Em 15 de janeiro de 2020, todas as combinações de servidores cliente e servidores de navegador devem usar a versão 1,2 do TLS (ou uma versão posterior) para garantir que todas as conexões possam ser feitas sem problemas para os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d9f16-116">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="d9f16-117">Isso pode exigir atualizações para determinadas combinações de servidores cliente e servidores de navegador.</span><span class="sxs-lookup"><span data-stu-id="d9f16-117">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="d9f16-118">Se você não atualizar para TLS versão 1,2 (ou uma versão posterior) em 15 de janeiro de 2020, você terá problemas ao tentar se conectar ao Office 365.</span><span class="sxs-lookup"><span data-stu-id="d9f16-118">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="d9f16-119">Além disso, será necessário atualizar para o TLS 1,2 (ou uma versão posterior) como parte da resolução.</span><span class="sxs-lookup"><span data-stu-id="d9f16-119">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="d9f16-120">Sabemos que os seguintes clientes não podem usar o TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="d9f16-120">We know that the following clients cannot use TLS 1.2:</span></span>

- <span data-ttu-id="d9f16-121">Android 4.3 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="d9f16-121">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="d9f16-122">Firefox versão 5.0 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="d9f16-122">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="d9f16-123">Internet Explorer 8 – 10 no Windows 7 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="d9f16-123">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="d9f16-124">Internet Explorer 10 no Windows Phone 8,0</span><span class="sxs-lookup"><span data-stu-id="d9f16-124">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="d9f16-125">Safari 6.0.4/OS X 10.8.4 e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="d9f16-125">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="d9f16-126">Recomendamos que você atualize seus clientes para garantir que você mantenha o acesso ininterrupto ao Office 365 GCC High e o DoD.</span><span class="sxs-lookup"><span data-stu-id="d9f16-126">We recommend that you update your clients to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="d9f16-127">Embora a análise atual de conexões com o Microsoft Online Services mostre que a maioria dos serviços e pontos de extremidade Confira muito pouco uso de TLS 1,1 e 1,0, estamos fornecendo notificações sobre essa alteração para que você possa atualizar quaisquer clientes ou servidores afetados, conforme o necessário, antes que o suporte para TLS 1,1 e 1,0 seja encerrado.</span><span class="sxs-lookup"><span data-stu-id="d9f16-127">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="d9f16-128">Se você estiver usando uma infraestrutura local para cenários híbridos ou serviços de Federação do Active Directory (AD FS), verifique se a infraestrutura pode dar suporte a conexões de entrada e de saída que usam TLS 1,2 (ou uma versão posterior).</span><span class="sxs-lookup"><span data-stu-id="d9f16-128">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="d9f16-129">Além das interrupções que podem ocorrer se você usar os clientes listados que não podem usar o TLS 1,2, remover o TLS 1,1 e o 1,0 impedirá que você use o seguinte produto da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="d9f16-129">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="d9f16-130">Telefone Lync</span><span class="sxs-lookup"><span data-stu-id="d9f16-130">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="d9f16-131">Referências</span><span class="sxs-lookup"><span data-stu-id="d9f16-131">References</span></span>

<span data-ttu-id="d9f16-132">O artigo de suporte a seguir descreve orientações e referências para ajudar a garantir que seus clientes estejam usando o TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="d9f16-132">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="d9f16-133">Preparando o uso obrigatório do TLS 1,2 no Office 365</span><span class="sxs-lookup"><span data-stu-id="d9f16-133">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
