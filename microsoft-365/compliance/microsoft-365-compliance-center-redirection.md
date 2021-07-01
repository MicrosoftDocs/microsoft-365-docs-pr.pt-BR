---
title: Redirecionar usuários do centro Office 365 Segurança e Conformidade para o Centro de conformidade do Microsoft 365
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Saiba mais sobre redirecionar automaticamente Office 365 usuários do Centro de Conformidade e Segurança para o Centro de conformidade do Microsoft 365..
ms.collection: M365-security-compliance
ms.openlocfilehash: 83d6a08d5c189c08c8f7d25daa3af39f28cbf8f1
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226270"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="554b5-103">Redirecionar usuários do centro Office 365 Segurança e Conformidade para o Centro de conformidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="554b5-103">Redirect users from the Office 365 Security and Compliance center to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="554b5-104">Este artigo explica como funciona o redirecionamento automático para usuários que acessam soluções de conformidade do Centro de Conformidade e Segurança Office 365 (protection.office.com) para o Centro de conformidade do Microsoft 365 (compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="554b5-104">This article explains how automatic redirection works for users accessing compliance solutions from the Office 365 Security and Compliance Center (protection.office.com) to the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="554b5-105">O que esperar</span><span class="sxs-lookup"><span data-stu-id="554b5-105">What to expect</span></span>

<span data-ttu-id="554b5-106">O redirecionamento automático é habilitado por padrão para todos os usuários que acessam as seguintes soluções relacionadas Office 365 Segurança e Conformidade (protection.office.com):</span><span class="sxs-lookup"><span data-stu-id="554b5-106">Automatic redirection is enabled by default for all users accessing the following compliance-related solutions in Office 365 Security and Compliance (protection.office.com):</span></span>

- <span data-ttu-id="554b5-107">Prevenção de perda de dados (DLP)</span><span class="sxs-lookup"><span data-stu-id="554b5-107">Data loss prevention (DLP)</span></span>
- <span data-ttu-id="554b5-108">Classificação</span><span class="sxs-lookup"><span data-stu-id="554b5-108">Classification</span></span>
- <span data-ttu-id="554b5-109">Governança de informações</span><span class="sxs-lookup"><span data-stu-id="554b5-109">Information governance</span></span>
- <span data-ttu-id="554b5-110">Gerenciamento de registros</span><span class="sxs-lookup"><span data-stu-id="554b5-110">Records management</span></span>
- <span data-ttu-id="554b5-111">Conformidade de comunicação (anteriormente 'Supervisão')</span><span class="sxs-lookup"><span data-stu-id="554b5-111">Communication compliance (formerly 'Supervision')</span></span>

<span data-ttu-id="554b5-112">Os usuários são automaticamente roteados para as mesmas soluções de conformidade no Centro de conformidade do Microsoft 365 (compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="554b5-112">Users are automatically routed to the same compliance solutions in the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="554b5-113">Para outras soluções de conformidade incluídas no Centro de Conformidade e Segurança do Office 365, os usuários continuarão a gerenciar essas soluções no Centro de conformidade do Microsoft 365 ou no Centro de Conformidade e Segurança Office 365.</span><span class="sxs-lookup"><span data-stu-id="554b5-113">For other compliance solutions included in the Office 365 Security and Compliance Center, users will continue to manage these solutions in either the Microsoft 365 compliance center or the Office 365 Security and Compliance Center.</span></span> <span data-ttu-id="554b5-114">O redirecionamento automático para essas soluções de conformidade estará disponível em breve.\*</span><span class="sxs-lookup"><span data-stu-id="554b5-114">The automatic redirection for these compliance solutions will be available soon.\*</span></span>

<span data-ttu-id="554b5-115">Esse recurso e controles associados não habilitam o redirecionamento automático de recursos de Segurança para o Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="554b5-115">This feature and associated controls does not enable the automatic redirection of Security features for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="554b5-116">Para habilitar o redirecionamento para recursos de segurança, consulte [Redirecionando](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) contas do Microsoft Defender para Office 365 para o centro de segurança Microsoft 365 para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="554b5-116">To enable the redirection for security features, see [Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) for details.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="554b5-117">Posso voltar a usar o portal anterior?</span><span class="sxs-lookup"><span data-stu-id="554b5-117">Can I go back to using the former portal?</span></span>

<span data-ttu-id="554b5-118">Se algo não estiver funcionando para você ou se houver algo que você não consiga concluir por meio do portal Centro de conformidade do Microsoft 365, você poderá desabilitar temporariamente o redirecionamento automático para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="554b5-118">If something isn't working for you or if there's anything you're unable to complete through the Microsoft 365 compliance center portal, you can temporarily disable the automatic redirection for all users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="554b5-119">O Centro de conformidade do Microsoft 365 é o portal de gerenciamento de substituição para soluções de conformidade gerenciadas atualmente no centro Office 365 Segurança e Conformidade.</span><span class="sxs-lookup"><span data-stu-id="554b5-119">The Microsoft 365 compliance center is the replacement management portal for compliance solutions currently managed in the Office 365 Security and Compliance center.</span></span> <span data-ttu-id="554b5-120">Todas as Microsoft 365 de conformidade serão gerenciadas somente no Centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="554b5-120">All Microsoft 365 compliance solutions will be managed solely in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="554b5-121">Desabilitar o redirecionamento para o Centro de conformidade do Microsoft 365 deve ser uma solução de curto prazo.\*</span><span class="sxs-lookup"><span data-stu-id="554b5-121">Disabling redirection to the Microsoft 365 compliance center should be a short-term solution.\*</span></span>

<span data-ttu-id="554b5-122">Para alternar de volta para o centro Office 365 Segurança e Conformidade (protection.microsoft.com) para todos os usuários, conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="554b5-122">To switch back to the Office 365 Security and Compliance center (protection.microsoft.com) for all users, complete the following steps:</span></span>

1. <span data-ttu-id="554b5-123">Entre no Centro de conformidade do Microsoft 365 [como](https://compliance.microsoft.com) administrador global ou usando qualquer conta com permissões de administrador de conformidade no Azure Active directory.</span><span class="sxs-lookup"><span data-stu-id="554b5-123">Sign in to the [Microsoft 365 compliance center](https://compliance.microsoft.com) as a global administrator or using any account with compliance administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="554b5-124">Navegue **até Configurações**  >  **redirecionamento do Centro de Conformidade.**</span><span class="sxs-lookup"><span data-stu-id="554b5-124">Navigate to **Settings** > **Compliance center redirection**.</span></span>
3. <span data-ttu-id="554b5-125">Alterne a configuração de redirecionamento automático para **Off**.</span><span class="sxs-lookup"><span data-stu-id="554b5-125">Toggle the Automatic redirection setting to **Off**.</span></span>
4. <span data-ttu-id="554b5-126">Selecione **Desativar e** compartilhar comentários quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="554b5-126">Select **Turn off** and share feedback when prompted.</span></span>

<span data-ttu-id="554b5-127">Depois de desabilitados, os usuários não serão mais roteados para compliance.microsoft.com e serão direcionados para o centro Office 365 Segurança e Conformidade (protection.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="554b5-127">Once disabled, users will no longer be routed to compliance.microsoft.com and they will be directed to the Office 365 Security and Compliance center (protection.microsoft.com).</span></span> <span data-ttu-id="554b5-128">Essa configuração pode ser habilitada novamente a qualquer momento pelos administradores de Conformidade ou Global.</span><span class="sxs-lookup"><span data-stu-id="554b5-128">This setting can be enabled again at any time by Global or Compliance admins.</span></span>

## <a name="related-information"></a><span data-ttu-id="554b5-129">Informações relacionadas</span><span class="sxs-lookup"><span data-stu-id="554b5-129">Related information</span></span>

- [<span data-ttu-id="554b5-130">Centro de conformidade do Microsoft 365 visão geral</span><span class="sxs-lookup"><span data-stu-id="554b5-130">Microsoft 365 compliance center overview</span></span>](/microsoft-365/compliance/microsoft-365-compliance-center)
