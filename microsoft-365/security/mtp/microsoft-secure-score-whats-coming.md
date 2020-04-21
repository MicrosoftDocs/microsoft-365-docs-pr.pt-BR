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
ms.openlocfilehash: 234ae17ab31d56d1bbd65f1aa8ed29475e9cd155
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583710"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="10250-104">O que está acontecendo na pontuação segura da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="10250-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="10250-105">Para tornar a [Pontuação segura da Microsoft](microsoft-secure-score.md) um melhor representante da postura de segurança e melhorar a usabilidade, estamos fazendo algumas alterações em um futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="10250-105">To make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="10250-106">Sua pontuação e a pontuação máxima possível mudarão.</span><span class="sxs-lookup"><span data-stu-id="10250-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="10250-107">No entanto, isso não implica uma alteração na postura de segurança.</span><span class="sxs-lookup"><span data-stu-id="10250-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="10250-108">Para saber mais sobre as alterações recentes, confira [o que há de novo na pontuação segura da Microsoft?](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="10250-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="10250-109">21 de abril de 2020</span><span class="sxs-lookup"><span data-stu-id="10250-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="10250-110">Removendo ações de melhoria que não atendem às expectativas para uma medição confiável ou não oferecem uma representação útil de postura de segurança</span><span class="sxs-lookup"><span data-stu-id="10250-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="10250-111">Para garantir que a pontuação segura da Microsoft seja significativa e que cada ação de melhoria seja mensurável e confiável, estamos removendo as seguintes ações de aprimoramento.</span><span class="sxs-lookup"><span data-stu-id="10250-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="10250-112">Aplicar proteções de IRM a documentos</span><span class="sxs-lookup"><span data-stu-id="10250-112">Apply IRM protections to documents</span></span>
- <span data-ttu-id="10250-113">Aplicar políticas de prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="10250-113">Apply Data Loss Prevention policies</span></span>

### <a name="adding-azure-ad-improvement-action-to-preview"></a><span data-ttu-id="10250-114">Adicionando a ação de melhoria do Azure AD para visualização</span><span class="sxs-lookup"><span data-stu-id="10250-114">Adding Azure AD improvement action to preview</span></span>

<span data-ttu-id="10250-115">Adição da seguinte ação de melhoria do Azure Active Directory para a [versão prévia da Pontuação segura da Microsoft](microsoft-secure-score-preview.md):</span><span class="sxs-lookup"><span data-stu-id="10250-115">Adding the following Azure Active Directory improvement action to the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md):</span></span>

- <span data-ttu-id="10250-116">Não permitir que os usuários conceda consentimento a aplicativos não gerenciados (atualmente disponível na versão lançada)</span><span class="sxs-lookup"><span data-stu-id="10250-116">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

### <a name="adding-azure-atp-improvement-actions-to-preview"></a><span data-ttu-id="10250-117">Adicionando ações de melhoria da ATP do Azure para visualização</span><span class="sxs-lookup"><span data-stu-id="10250-117">Adding Azure ATP improvement actions to preview</span></span>

<span data-ttu-id="10250-118">Adicionar as seguintes ações de melhoria avançada de proteção contra ameaças do Azure à [versão prévia da Pontuação segura da Microsoft](microsoft-secure-score-preview.md):</span><span class="sxs-lookup"><span data-stu-id="10250-118">Adding the following Azure Advanced Threat Protection improvement actions to the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md):</span></span>

- <span data-ttu-id="10250-119">Desabilitar o serviço spooler de impressão em controladores de domínio</span><span class="sxs-lookup"><span data-stu-id="10250-119">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="10250-120">Modificar as delegações Kerberos não seguras para impedir a representação</span><span class="sxs-lookup"><span data-stu-id="10250-120">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="10250-121">Proteger e gerenciar senhas de administrador local com o Microsoft LAPS</span><span class="sxs-lookup"><span data-stu-id="10250-121">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="10250-122">Reduzir o risco de caminho de movimento lateral para entidades confidenciais</span><span class="sxs-lookup"><span data-stu-id="10250-122">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="10250-123">Remover contas inativas de grupos confidenciais</span><span class="sxs-lookup"><span data-stu-id="10250-123">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="10250-124">Remover atributos de histórico de SID não seguros das entidades</span><span class="sxs-lookup"><span data-stu-id="10250-124">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="10250-125">Resolver atributos de conta não seguros</span><span class="sxs-lookup"><span data-stu-id="10250-125">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="10250-126">Parar exposição de credenciais de texto não criptografado</span><span class="sxs-lookup"><span data-stu-id="10250-126">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="10250-127">Parar comunicação de protocolos herdados</span><span class="sxs-lookup"><span data-stu-id="10250-127">Stop legacy protocols communication</span></span>
- <span data-ttu-id="10250-128">Interromper o uso de codificação fraca</span><span class="sxs-lookup"><span data-stu-id="10250-128">Stop weak cipher usage</span></span>

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-preview"></a><span data-ttu-id="10250-129">Suporte para recomendações de segurança do TVM (gerenciamento de vulnerabilidades) do Microsoft defender & ATP em versão prévia</span><span class="sxs-lookup"><span data-stu-id="10250-129">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations in preview</span></span>

<span data-ttu-id="10250-130">Todas as recomendações de segurança lançadas pelo TVM agora também estarão disponíveis na [versão prévia da Pontuação segura da Microsoft](microsoft-secure-score-preview.md).</span><span class="sxs-lookup"><span data-stu-id="10250-130">All released security recommendations supplied by TVM will now also be available the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md).</span></span>
