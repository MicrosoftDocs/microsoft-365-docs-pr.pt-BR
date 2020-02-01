---
title: Remetente seguro e listas de remetentes bloqueados no Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: Como um administrador do Exchange Online ou do Exchange Online Protection (EOP), você pode ajudar a garantir que uma mensagem de email que viaja pelo serviço não seja marcada como spam. Uma maneira de fazer isso é criar listas de remetentes seguros e remetentes bloqueados para as pessoas da sua organização.
ms.openlocfilehash: 959af558c32e71e5a4cede2aff7bbcd1dbb092e2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598508"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a><span data-ttu-id="168c4-104">Remetente seguro e listas de remetentes bloqueados no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="168c4-104">Safe sender and blocked sender lists in Exchange Online</span></span>

<span data-ttu-id="168c4-105">Como um administrador do Exchange Online ou do Exchange Online Protection (EOP), você pode ajudar a garantir que uma mensagem de email que viaja pelo serviço não seja marcada como spam.</span><span class="sxs-lookup"><span data-stu-id="168c4-105">As an Exchange Online or Exchange Online Protection (EOP) administrator, you can help ensure that an email message traveling through the service isn't marked as spam.</span></span> <span data-ttu-id="168c4-106">Uma maneira de fazer isso é criar listas de remetentes seguros e remetentes bloqueados para as pessoas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="168c4-106">One way to do this is to create safe sender and blocked sender lists for the people in your organization.</span></span>

<span data-ttu-id="168c4-107">*Consulte a versão atualizada das dicas e procedimentos sobre como trabalhar com essas listas como um administrador em* [como impedir que bons emails sejam marcados como spam no Office 365](prevent-email-from-being-marked-as-spam.md).</span><span class="sxs-lookup"><span data-stu-id="168c4-107">*See the updated version of the tips and procedures for how to work with these lists as an admin in* [How to prevent good email from being marked as spam in Office 365](prevent-email-from-being-marked-as-spam.md).</span></span>

<span data-ttu-id="168c4-108">Se você não for um administrador e só quiser gerenciar seu próprio lixo eletrônico no Outlook usando uma lista de remetentes seguros, Confira as etapas da[visão geral do filtro de lixo eletrônico](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span><span class="sxs-lookup"><span data-stu-id="168c4-108">If you're not an admin, and you just want to manage your own junk email in Outlook by using a safe sender list, check out the steps in the[Overview of the Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a><span data-ttu-id="168c4-109">Quais são os limites de remetentes seguros e bloqueados no Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="168c4-109">What is the safe and blocked sender limits in Exchange Online?</span></span>

<span data-ttu-id="168c4-110">Os limites de remetentes seguros e bloqueados no Exchange Online diferem dos limites do Active Directory e do Outlook.</span><span class="sxs-lookup"><span data-stu-id="168c4-110">The safe and blocked sender limits in Exchange Online differ from the Active Directory and Outlook limits.</span></span> <span data-ttu-id="168c4-111">Que são:</span><span class="sxs-lookup"><span data-stu-id="168c4-111">They are:</span></span>

- <span data-ttu-id="168c4-112">Limite de remetente seguro: 1.024</span><span class="sxs-lookup"><span data-stu-id="168c4-112">Safe sender limit: 1,024</span></span>

- <span data-ttu-id="168c4-113">Limite de remetentes bloqueados: 500</span><span class="sxs-lookup"><span data-stu-id="168c4-113">Blocked sender limit: 500</span></span>

<span data-ttu-id="168c4-114">Observação:</span><span class="sxs-lookup"><span data-stu-id="168c4-114">Note:</span></span>

<span data-ttu-id="168c4-115">Você pode experimentar o erro descrito no [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span><span class="sxs-lookup"><span data-stu-id="168c4-115">You may experience the error that is described in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span></span> <span data-ttu-id="168c4-116">Para resolver esse problema, desmarque a caixa de seleção "confiar em emails de meus contatos".</span><span class="sxs-lookup"><span data-stu-id="168c4-116">To resolve this issue, clear the "Trust emails from my contacts" check box.</span></span> <span data-ttu-id="168c4-117">Como alternativa, diminua a quantidade de endereços de email que estão na sua pasta de contatos padrão para trazê-lo dentro do limite máximo permitido de 1024 no Exchange Online que está definido para o atributo "parâmetros MaxSafeSenders".</span><span class="sxs-lookup"><span data-stu-id="168c4-117">Alternatively, decrease the amount of email addresses that are in your default Contacts folder to bring it within the maximum allowed limit of 1024 in Exchange Online that is set for "MaxSafeSenders" attribute.</span></span> <span data-ttu-id="168c4-118">Para obter mais informações sobre este atributo e o cmdlet Set-Mailbox, confirao seguinte tópico:</span><span class="sxs-lookup"><span data-stu-id="168c4-118">For more information about this attribute and the Set-Mailbox cmdlet, seethe following topic:</span></span>

[<span data-ttu-id="168c4-119">Set-Mailbox</span><span class="sxs-lookup"><span data-stu-id="168c4-119">Set-Mailbox</span></span>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a><span data-ttu-id="168c4-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="168c4-120">See also</span></span>

[<span data-ttu-id="168c4-121">Filtragem de remetente no Exchange Server</span><span class="sxs-lookup"><span data-stu-id="168c4-121">Sender filtering in Exchange Server</span></span>](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
