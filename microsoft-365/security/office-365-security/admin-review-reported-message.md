---
title: Revisão de administrador para mensagens relatadas
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Saiba como revisar as mensagens relatadas e fazer comentários aos usuários.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 619cd35b6a60f0d50aa6c13e4cad2b8d7ae947a8
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730949"
---
# <a name="admin-review-for-reported-messages"></a><span data-ttu-id="bdd58-103">Revisão de administrador para mensagens relatadas</span><span class="sxs-lookup"><span data-stu-id="bdd58-103">Admin review for reported messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> <span data-ttu-id="bdd58-104">As informações neste artigo se relacionam a um produto de visualização que pode ser substancialmente modificado antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="bdd58-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="bdd58-105">Este documento é fornecido apenas para fins de avaliação e exploração.</span><span class="sxs-lookup"><span data-stu-id="bdd58-105">This document is provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="bdd58-106">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="bdd58-106">**Applies to**</span></span>
- [<span data-ttu-id="bdd58-107">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="bdd58-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="bdd58-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bdd58-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="bdd58-109">Em Microsoft 365 com caixas de correio Exchange Online e o Microsoft Defender para Office 365, os administradores agora podem enviar mensagens com modelos de volta aos usuários finais depois de revisarem as mensagens relatadas.</span><span class="sxs-lookup"><span data-stu-id="bdd58-109">In Microsoft 365 organizations with Exchange Online mailboxes and Microsoft Defender for Office 365, admins can now send templated messages back to end users after they review reported messages.</span></span> <span data-ttu-id="bdd58-110">Isso também pode ser personalizado para sua organização e com base no veredito do administrador.</span><span class="sxs-lookup"><span data-stu-id="bdd58-110">This can be customized for your organization and based on your admin’s verdict as well.</span></span>

<span data-ttu-id="bdd58-111">Esse recurso foi projetado para dar feedback aos usuários, mas não altera os vereditos das mensagens no sistema.</span><span class="sxs-lookup"><span data-stu-id="bdd58-111">This feature is designed to give feedback to your users but does not change the verdicts of messages in the system.</span></span> <span data-ttu-id="bdd58-112">Para ajudar a Microsoft a atualizar e melhorar seus filtros, você precisará enviar mensagens para análise usando [o envio de Administrador.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="bdd58-112">To help Microsoft update and improve its filters, you will need to submit messages for analysis using [Admin submission](admin-submission.md).</span></span>

<span data-ttu-id="bdd58-113">Você só poderá marcar e notificar os usuários dos resultados da revisão se a mensagem for relatada como falsos [positivos ou falsos negativos.](report-false-positives-and-false-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="bdd58-113">You will only be able to mark and notify users of review results if the message was reported as a [false positives or false negatives](report-false-positives-and-false-negatives.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bdd58-114">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="bdd58-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bdd58-115">Para modificar a configuração para envios do usuário, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="bdd58-115">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>
    - <span data-ttu-id="bdd58-116">Gerenciamento da Organização ou Administrador de Segurança no [Centro de Segurança.](permissions-microsoft-365-compliance-security.md)</span><span class="sxs-lookup"><span data-stu-id="bdd58-116">Organization Management or Security Administrator in the [Security center](permissions-microsoft-365-compliance-security.md).</span></span>
    - <span data-ttu-id="bdd58-117">Gerenciamento de organização em [Exchange Online](/Exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="bdd58-117">Organization Management in [Exchange Online](/Exchange/permissions-exo/permissions-exo).</span></span>

- <span data-ttu-id="bdd58-118">Você também precisará de acesso ao Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bdd58-118">You'll also need access to the Exchange Online PowerShell.</span></span> <span data-ttu-id="bdd58-119">Se a conta que você está tentando usar não tiver acesso ao Exchange Online PowerShell, você receberá um erro que diz Especificar um endereço de email em *seu domínio*.</span><span class="sxs-lookup"><span data-stu-id="bdd58-119">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that says *Specify an email address in your domain*.</span></span> <span data-ttu-id="bdd58-120">Para obter mais informações sobre a habilitação ou desabilitação do acesso ao Exchange Online PowerShell, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="bdd58-120">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>
    - [<span data-ttu-id="bdd58-121">Habilitar ou desabilitar o acesso Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="bdd58-121">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell)
    - [<span data-ttu-id="bdd58-122">Regras de Acesso para Cliente no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bdd58-122">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a><span data-ttu-id="bdd58-123">Configurar as mensagens usadas para notificar os usuários</span><span class="sxs-lookup"><span data-stu-id="bdd58-123">Configure the messages used to notify users</span></span>

1. <span data-ttu-id="bdd58-124">No centro [de Microsoft 365 de segurança](../defender/overview-security-center.md), vá para Políticas & **políticas** de ameaça As configurações de mensagem \>  \> **relatadas pelo usuário.**</span><span class="sxs-lookup"><span data-stu-id="bdd58-124">In the [Microsoft 365 security center](../defender/overview-security-center.md), go to **Policies & rules** \> **Threat policies** \> **User reported message settings**.</span></span>

2. <span data-ttu-id="bdd58-125">Se você quiser especificar o nome de exibição do remetente, marque Office 365 caixa especificar um endereço de **email** para usar como remetente na seção Notificações de **email** para resultados de revisão de administrador e insira o nome que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="bdd58-125">If you want to specify the sender display name, check the box for **Specify Office 365 email address to use as sender** under the **Email notifications for admin review results** section, and enter in the name you wish to use.</span></span> <span data-ttu-id="bdd58-126">Este é o endereço de email que ficará visível no Outlook e para onde as respostas serão.</span><span class="sxs-lookup"><span data-stu-id="bdd58-126">This is the email address that will be visible in Outlook and where replies will go to.</span></span>

3. <span data-ttu-id="bdd58-127">Se você quiser personalizar qualquer um dos modelos, clique em **Personalizar notificação de email**.</span><span class="sxs-lookup"><span data-stu-id="bdd58-127">If you want to customize any of the templates, click **Customize email notification**.</span></span> <span data-ttu-id="bdd58-128">Neste sobrevoo, você poderá personalizar apenas o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bdd58-128">In this flyout, you will be able to customize only the following:</span></span>
    - <span data-ttu-id="bdd58-129">Phishing</span><span class="sxs-lookup"><span data-stu-id="bdd58-129">Phishing</span></span>
    - <span data-ttu-id="bdd58-130">Lixo eletrônico</span><span class="sxs-lookup"><span data-stu-id="bdd58-130">Junk</span></span>
    - <span data-ttu-id="bdd58-131">Nenhuma ameaça encontrada</span><span class="sxs-lookup"><span data-stu-id="bdd58-131">No threats found</span></span>
    - <span data-ttu-id="bdd58-132">Treinamento de conscientização</span><span class="sxs-lookup"><span data-stu-id="bdd58-132">Awareness training</span></span>
    - <span data-ttu-id="bdd58-133">Rodapé</span><span class="sxs-lookup"><span data-stu-id="bdd58-133">Footer</span></span>

4. <span data-ttu-id="bdd58-134">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bdd58-134">When you're finished, click **Save**.</span></span> <span data-ttu-id="bdd58-135">Para limpar esses valores, clique **em Descartar** na página Envios do usuário.</span><span class="sxs-lookup"><span data-stu-id="bdd58-135">To clear these values, click **Discard** on the User submissions page.</span></span>
