---
title: insight de correção de domínio do remetente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Os administradores podem saber mais sobre a correção do domínio do remetente no painel de fluxo de emails no centro de conformidade do & de segurança.
ms.openlocfilehash: 1b154f4aecd5ada711b9177380d936cd888df425
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598818"
---
# <a name="fix-sender-domain-insight"></a><span data-ttu-id="7291a-103">insight de correção de domínio do remetente</span><span class="sxs-lookup"><span data-stu-id="7291a-103">Fix sender domain insight</span></span>

<span data-ttu-id="7291a-104">O Office 365 requer mensagens de envio de ambientes de email locais internos para o Office 365 para atender a determinados critérios de segurança:</span><span class="sxs-lookup"><span data-stu-id="7291a-104">Office 365 requires messages sending from internal on-premises email environments to Office 365 to meet certain security criteria:</span></span>

- <span data-ttu-id="7291a-105">Você criou um conector de entrada no Office 365 para autenticar conexões SMTP do seu servidor de email local usando o endereço IP de origem ou um certificado.</span><span class="sxs-lookup"><span data-stu-id="7291a-105">You've created an inbound connector in Office 365 to authenticate SMTP connections from your on-premises email server by using the source IP address or a certificate.</span></span>

- <span data-ttu-id="7291a-106">Você configurou seu servidor de email local para retransmitir emails por meio do Office 365 para o mundo externo.</span><span class="sxs-lookup"><span data-stu-id="7291a-106">You've configured your on-premises email server to relay email via Office 365 to external world.</span></span>

- <span data-ttu-id="7291a-107">Na configuração, uma das seguintes instruções é verdadeira:</span><span class="sxs-lookup"><span data-stu-id="7291a-107">In your configuration, one of the following statements is true:</span></span>

  - <span data-ttu-id="7291a-108">O domínio de email do remetente está registrado na sua organização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="7291a-108">The sender's email domain is registered in your Office 365 organization.</span></span> <span data-ttu-id="7291a-109">Para obter mais informações, consulte adicionar domínios no Office 365.</span><span class="sxs-lookup"><span data-stu-id="7291a-109">For more information, see Add Domains in Office 365.</span></span>

  - <span data-ttu-id="7291a-110">Seu servidor de email local está configurado para usar um certificado para enviar emails para o Office 365, o certificado contém ou corresponde exatamente a um nome de domínio que você registrou no Office 365 e criou um conector baseado em certificado no Office 365 com esse Domain.</span><span class="sxs-lookup"><span data-stu-id="7291a-110">Your on-premises email server is configured to use a certificate to send email to Office 365, the certificate contains or exactly matches a domain name that you've registered in Office 365, and you've created a certificate based connector in Office 365 with that domain.</span></span> 

<span data-ttu-id="7291a-111">As mensagens que não atenderem aos critérios não serão atribuídas à organização e poderão ser rejeitadas.</span><span class="sxs-lookup"><span data-stu-id="7291a-111">Messages that don't meet the criteria will not be attributed to the organization and could be rejected.</span></span>

<span data-ttu-id="7291a-112">A **solução corrigir domínio do remetente** mostra emails do seu ambiente local que não atendem aos critérios, ajuda você a identificar máquinas potencialmente comprometidas e contas de usuário em seu ambiente de email local e ajuda a realizar ações de correção.</span><span class="sxs-lookup"><span data-stu-id="7291a-112">The **Fix sender domain** insight shows you email from your on-premises environment that doesn't meet the criteria, helps you to identify potentially compromised machines and user accounts in your on-premises email environment, and helps you to take remediation actions.</span></span>

![A correção do domínio do remetente se aprofunda no painel de fluxo de emails no centro de conformidade de & de segurança](../media/sender-domain-insight-selected.png)

<span data-ttu-id="7291a-114">Ao clicar em **Exibir detalhes**, você será levado para outro widget com mais detalhes, conforme mostrado no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="7291a-114">When you click **View details**, you are taken to another widget with more details as shown in the following diagram:</span></span>

![O widget detalhes na visão corrigir domínio do remetente](../media/sender-domain-view-details.png)

<span data-ttu-id="7291a-116">Você verá o conector de entrada usado para entregar as mensagens ao Office 365.</span><span class="sxs-lookup"><span data-stu-id="7291a-116">You'll see the inbound connector that was used to deliver the messages to Office 365.</span></span> <span data-ttu-id="7291a-117">Você também pode clicar em **Exibir IDs de mensagem de amostra** para ver os detalhes das mensagens que foram enviadas de seu ambiente de email local.</span><span class="sxs-lookup"><span data-stu-id="7291a-117">You can also click **view sample message IDs** to see details for the messages that were sent from your on-premises email environment.</span></span> <span data-ttu-id="7291a-118">Como essas mensagens foram rejeitadas pelo Office 365, não é possível usar o rastreamento de mensagens, mas você pode usar as IDs de mensagem de exemplo para rastrear as mensagens no seu ambiente de email local.</span><span class="sxs-lookup"><span data-stu-id="7291a-118">Because these messages were rejected by Office 365, you can't use message trace, but you can use the sample message ids to track the messages in your on-premises email environment.</span></span>

![Exibir IDs de mensagem de exemplo na solução corrigir domínio do remetente](../media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a><span data-ttu-id="7291a-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="7291a-120">See also</span></span>

<span data-ttu-id="7291a-121">Para obter mais informações sobre outros insights de fluxo de email no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="7291a-121">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
