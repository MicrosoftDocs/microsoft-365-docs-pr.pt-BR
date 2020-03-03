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
ms.openlocfilehash: efb75f26d66258880c9defa94869f27e18685052
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42371999"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="63598-104">O que está acontecendo na pontuação segura da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="63598-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="63598-105">Para tornar a pontuação segura da Microsoft um melhor representante da postura de segurança e melhorar a usabilidade, estamos fazendo algumas alterações em um futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="63598-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="63598-106">Sua pontuação e a pontuação máxima possível mudarão.</span><span class="sxs-lookup"><span data-stu-id="63598-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="63598-107">No entanto, isso não implica uma alteração na postura de segurança.</span><span class="sxs-lookup"><span data-stu-id="63598-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="63598-108">Para saber mais sobre as alterações recentes, confira [o que há de novo na pontuação segura da Microsoft?](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="63598-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="63598-109">16 de março de 2020</span><span class="sxs-lookup"><span data-stu-id="63598-109">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="63598-110">Removendo ações de melhoria que não atendem às expectativas para uma medição confiável ou não oferecem uma representação útil de postura de segurança</span><span class="sxs-lookup"><span data-stu-id="63598-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="63598-111">Para garantir que a pontuação segura da Microsoft seja significativa e que cada ação de melhoria seja mensurável e confiável, estamos removendo as seguintes ações de aprimoramento.</span><span class="sxs-lookup"><span data-stu-id="63598-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="63598-112">Armazenar documentos de usuário no OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="63598-112">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="63598-113">Configurar as políticas de anexo seguro do Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="63598-113">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="63598-114">Configurar links seguros do Office 365 para verificar URLs</span><span class="sxs-lookup"><span data-stu-id="63598-114">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="63598-115">Não permitir a delegação de caixa de correio</span><span class="sxs-lookup"><span data-stu-id="63598-115">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="63598-116">Permitir links de compartilhamento de convidados anônimos para sites e documentos</span><span class="sxs-lookup"><span data-stu-id="63598-116">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="63598-117">Ativar console do Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="63598-117">Turn on Cloud App Security Console</span></span>
- <span data-ttu-id="63598-118">Configurar tempo de expiração para links de compartilhamento externos</span><span class="sxs-lookup"><span data-stu-id="63598-118">Configure expiration time for external sharing links</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="63598-119">Padrões de segurança de suporte para ações de melhoria do Azure AD</span><span class="sxs-lookup"><span data-stu-id="63598-119">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="63598-120">A pontuação segura da Microsoft atualizará as ações de aperfeiçoamento para suportar os [padrões de segurança no Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), o que facilita a proteção da sua organização com configurações de segurança pré-configuradas para ataques comuns.</span><span class="sxs-lookup"><span data-stu-id="63598-120">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="63598-121">Isso afetará as seguintes ações de melhoria:</span><span class="sxs-lookup"><span data-stu-id="63598-121">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="63598-122">Garantir que todos os usuários possam concluir a autenticação multifator para acesso seguro</span><span class="sxs-lookup"><span data-stu-id="63598-122">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="63598-123">Exigir MFA para funções administrativas</span><span class="sxs-lookup"><span data-stu-id="63598-123">Require MFA for administrative roles</span></span>
- <span data-ttu-id="63598-124">Habilitar política para bloquear autenticação herdada</span><span class="sxs-lookup"><span data-stu-id="63598-124">Enable policy to block legacy authentication</span></span>
