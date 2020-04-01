---
title: Adicionar suporte para emails de entrada anônimos por IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: O administrador pode saber como configurar o suporte para emails de entrada anônimos de fontes IPv6 no Exchange Online e no Exchange Online Protection.
ms.openlocfilehash: 67e839249d41381be22bbccf6b09d1616c387c66
ms.sourcegitcommit: 748bc3484b7ccbd65b558f495b6fa42196c3c571
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2020
ms.locfileid: "43083636"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-office-365"></a><span data-ttu-id="f5838-103">Adicionar suporte para email de entrada anônimo por IPv6 no Office 365</span><span class="sxs-lookup"><span data-stu-id="f5838-103">Add support for anonymous inbound email over IPv6 in Office 365</span></span>

<span data-ttu-id="f5838-104">As organizações do Office 365 com caixas de correio do Exchange Online e do proteção autônoma do Exchange Online (EOP) sem caixas de correio do Exchange Online dão suporte a emails de entrada anônimos por IPv6.</span><span class="sxs-lookup"><span data-stu-id="f5838-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="f5838-105">O servidor de email IPv6 de origem deve cumprir os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="f5838-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="f5838-106">O endereço IPv6 de origem deve ter um registro de pesquisa de DNS reverso válido que permite que o destino encontre o nome de domínio do endereço IPv6.</span><span class="sxs-lookup"><span data-stu-id="f5838-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="f5838-107">O remetente deve passar por verificação SPF (definida na [RFC 7208](https://tools.ietf.org/html/rfc7208)) ou [verificação DKIM](https://dkim.org/) (definida na [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="f5838-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="f5838-108">Antes que sua organização possa receber emails de entrada anônimos por IPv6, um administrador precisa entrar em contato com o suporte da Microsoft e solicitá-lo:</span><span class="sxs-lookup"><span data-stu-id="f5838-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it:</span></span>

1. <span data-ttu-id="f5838-109">Abra o centro de administração do Microsoft <https://admin.microsoft.com/adminportal/home> 365 em e clique em **ajuda** (?).</span><span class="sxs-lookup"><span data-stu-id="f5838-109">Open the Microsoft 365 admin center at <https://admin.microsoft.com/adminportal/home> and click **Help** (?).</span></span>

2. <span data-ttu-id="f5838-110">No submenu **precisa de ajuda?** que aparece, digite algo descritivo na caixa de pesquisa (por exemplo, "solicitar email IPv6 de entrada anônimo") e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="f5838-110">In the **Need help?** flyout that appears, type something descriptive in the search box (for example, "request anonymous inbound IPv6 email"), and then press ENTER.</span></span>

3. <span data-ttu-id="f5838-111">Na parte inferior da página, clique em **entrar em contato com o suporte**.</span><span class="sxs-lookup"><span data-stu-id="f5838-111">At the bottom of the page, click **Contact support**.</span></span>

4. <span data-ttu-id="f5838-112">Na página de **suporte de contato** que aparece, preencha e verifique as informações (role para baixo conforme necessário) e clique em **entrar em contato comigo**.</span><span class="sxs-lookup"><span data-stu-id="f5838-112">In the **Contact support** page that appears, fill out and verify the information (scroll down as necessary), and then click **Contact me**.</span></span>

<span data-ttu-id="f5838-113">Depois que o suporte à mensagem IPv6 de entrada anônima estiver habilitado em sua organização, a mensagem passará pela filtragem de mensagens normal fornecida pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="f5838-113">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f5838-114">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="f5838-114">Troubleshooting</span></span>

- <span data-ttu-id="f5838-115">Se o servidor de email de origem não tiver um registro de pesquisa de DNS reverso IPv6, as mensagens serão rejeitadas com o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="f5838-115">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="f5838-116">450 o serviço 4.7.25 não está disponível, enviando endereço IPv6 [2a01:111: F200: de 2004:: 240] deve ter um registro DNS reverso.</span><span class="sxs-lookup"><span data-stu-id="f5838-116">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="f5838-117">Se o remetente não passar pela validação SPF ou DKIM, as mensagens serão rejeitadas com o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="f5838-117">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="f5838-118">450 4.7.26 serviço não disponível, a mensagem enviada por IPv6 [2a01:111: F200:2004:: 240] deve passar pela validação SPF ou DKIM.</span><span class="sxs-lookup"><span data-stu-id="f5838-118">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="f5838-119">Se você tentar receber mensagens IPv6 anônimas antes de optar por você, a mensagem será rejeitada com o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="f5838-119">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="f5838-120">550 o serviço 5.2.1 não está disponível, [contoso.com] não aceita emails sobre IPv6.</span><span class="sxs-lookup"><span data-stu-id="f5838-120">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="f5838-121">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="f5838-121">For more information</span></span>

[<span data-ttu-id="f5838-122">Suporte para validação de mensagens assinadas por DKIM</span><span class="sxs-lookup"><span data-stu-id="f5838-122">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
