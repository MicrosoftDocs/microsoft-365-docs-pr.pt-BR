---
title: O que está acontecendo na pontuação segura da Microsoft?
description: Descreve a pontuação segura da Microsoft na central de segurança do Microsoft 365, como os detalhes são calculados e quais administradores de segurança podem esperar.
keywords: segurança, malware, Microsoft 365, M365, Pontuação segura, central de segurança, ações de melhoria
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 61f066b2fff2798e78e6379bbca46e48e93ff017
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895436"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="e61d4-104">O que está acontecendo na pontuação segura da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="e61d4-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="e61d4-105">Para tornar a pontuação segura da Microsoft um melhor representante da postura de segurança e melhorar a usabilidade, estamos fazendo algumas alterações em um futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="e61d4-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="e61d4-106">Sua pontuação e a pontuação máxima possível mudarão.</span><span class="sxs-lookup"><span data-stu-id="e61d4-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="e61d4-107">No entanto, isso não implica uma alteração na postura de segurança.</span><span class="sxs-lookup"><span data-stu-id="e61d4-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="e61d4-108">Para saber mais sobre as alterações recentes, confira [o que há de novo na pontuação segura da Microsoft?](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="e61d4-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="e61d4-109">21 de abril de 2020</span><span class="sxs-lookup"><span data-stu-id="e61d4-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="e61d4-110">Removendo ações de melhoria que não atendem às expectativas para uma medição confiável ou não oferecem uma representação útil de postura de segurança</span><span class="sxs-lookup"><span data-stu-id="e61d4-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="e61d4-111">Para garantir que a pontuação segura da Microsoft seja significativa e que cada ação de melhoria seja mensurável e confiável, estamos removendo as seguintes ações de aprimoramento.</span><span class="sxs-lookup"><span data-stu-id="e61d4-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="e61d4-112">Excluir/bloquear contas não usadas nos últimos 30 dias</span><span class="sxs-lookup"><span data-stu-id="e61d4-112">Delete/block accounts not used in last 30 days</span></span>
- <span data-ttu-id="e61d4-113">Designar menos de 5 administradores globais</span><span class="sxs-lookup"><span data-stu-id="e61d4-113">Designate fewer than 5 global admins</span></span>
- <span data-ttu-id="e61d4-114">Aplicar proteções de IRM a documentos</span><span class="sxs-lookup"><span data-stu-id="e61d4-114">Apply IRM protections to documents</span></span>
- <span data-ttu-id="e61d4-115">Aplicar políticas de prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="e61d4-115">Apply Data Loss Prevention policies</span></span>

### <a name="adding-additional-control-support-in-the-preview-version"></a><span data-ttu-id="e61d4-116">Adição de suporte de controle adicional na versão de visualização</span><span class="sxs-lookup"><span data-stu-id="e61d4-116">Adding additional control support in the preview version</span></span>
- <span data-ttu-id="e61d4-117">Não permitir que os usuários conceda consentimento a aplicativos não gerenciados (atualmente disponível na versão lançada)</span><span class="sxs-lookup"><span data-stu-id="e61d4-117">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

#### <a name="support-for-additional-microsoft-cloud-app-security-improvement-actions"></a><span data-ttu-id="e61d4-118">Suporte para ações adicionais de melhoria de segurança do aplicativo do Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="e61d4-118">Support for additional Microsoft Cloud App Security improvement actions</span></span>
- <span data-ttu-id="e61d4-119">Desabilitar o serviço spooler de impressão em controladores de domínio</span><span class="sxs-lookup"><span data-stu-id="e61d4-119">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="e61d4-120">Modificar as delegações Kerberos não seguras para impedir a representação</span><span class="sxs-lookup"><span data-stu-id="e61d4-120">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="e61d4-121">Proteger e gerenciar senhas de administrador local com o Microsoft LAPS</span><span class="sxs-lookup"><span data-stu-id="e61d4-121">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="e61d4-122">Reduzir o risco de caminho de movimento lateral para entidades confidenciais</span><span class="sxs-lookup"><span data-stu-id="e61d4-122">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="e61d4-123">Remover contas inativas de grupos confidenciais</span><span class="sxs-lookup"><span data-stu-id="e61d4-123">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="e61d4-124">Remover atributos de histórico de SID não seguros das entidades</span><span class="sxs-lookup"><span data-stu-id="e61d4-124">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="e61d4-125">Resolver atributos de conta não seguros</span><span class="sxs-lookup"><span data-stu-id="e61d4-125">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="e61d4-126">Parar exposição de credenciais de texto não criptografado</span><span class="sxs-lookup"><span data-stu-id="e61d4-126">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="e61d4-127">Parar comunicação de protocolos herdados</span><span class="sxs-lookup"><span data-stu-id="e61d4-127">Stop legacy protocols communication</span></span>
- <span data-ttu-id="e61d4-128">Interromper o uso de codificação fraca</span><span class="sxs-lookup"><span data-stu-id="e61d4-128">Stop weak cipher usage</span></span>

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a><span data-ttu-id="e61d4-129">Suporte para recomendações de segurança do TVM (gerenciamento de vulnerabilidades) do Microsoft defender & ATP</span><span class="sxs-lookup"><span data-stu-id="e61d4-129">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations</span></span>
- <span data-ttu-id="e61d4-130">Todas as recomendações de segurança lançadas pelo TVM também estarão disponíveis na pontuação segura da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e61d4-130">All released security recommendations supplied by TVM will now also be available in Microsoft Secure Score</span></span>
