---
title: Criptografia de dados em trânsito
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 'Resumo: uma breve explicação de como a Microsoft criptografa dados em trânsito.'
ms.openlocfilehash: 0775d28a96f271a24406fd68c2ccb9fe4954e66d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637327"
---
# <a name="encryption-for-data-in-transit"></a><span data-ttu-id="88f5b-103">Criptografia para dados em trânsito</span><span class="sxs-lookup"><span data-stu-id="88f5b-103">Encryption for data in transit</span></span>

<span data-ttu-id="88f5b-104">Além de proteger os dados do cliente em repouso, a Microsoft usa tecnologias de criptografia para proteger os dados do cliente em trânsito.</span><span class="sxs-lookup"><span data-stu-id="88f5b-104">In addition to protecting customer data at rest, Microsoft uses encryption technologies to protect customer data in transit.</span></span> 

<span data-ttu-id="88f5b-105">Os dados estão em trânsito:</span><span class="sxs-lookup"><span data-stu-id="88f5b-105">Data is in transit:</span></span>

- <span data-ttu-id="88f5b-106">Quando uma máquina cliente se comunica com um servidor Microsoft;</span><span class="sxs-lookup"><span data-stu-id="88f5b-106">when a client machine communicates with a Microsoft server;</span></span>
- <span data-ttu-id="88f5b-107">Quando um servidor Microsoft se comunica com outro servidor Microsoft; e</span><span class="sxs-lookup"><span data-stu-id="88f5b-107">when a Microsoft server communicates with another Microsoft server; and</span></span>
- <span data-ttu-id="88f5b-108">Quando um servidor Microsoft se comunica com um servidor não-Microsoft (por exemplo, o Exchange Online que entrega emails para um servidor de email externo).</span><span class="sxs-lookup"><span data-stu-id="88f5b-108">when a Microsoft server communicates with a non-Microsoft server (e.g., Exchange Online delivering email to a foreign email server).</span></span>

<span data-ttu-id="88f5b-109">Comunicações entre data centers entre servidores da Microsoft ocorrem sobre TLS ou IPsec, e todos os servidores voltados ao cliente negociam uma sessão segura usando TLS com máquinas clientes (por exemplo, o Exchange Online usa TLS 1,2 com intensidade de codificação de 256 bits é usado (FIPS 140-2 Level 2 validado).</span><span class="sxs-lookup"><span data-stu-id="88f5b-109">Inter-datacenter communications between Microsoft servers takes place over TLS or IPsec, and all customer-facing servers negotiate a secure session using TLS with client machines (e.g., Exchange Online uses TLS 1.2 with 256-bit cipher strength is used (FIPS 140-2 Level 2-validated).</span></span> <span data-ttu-id="88f5b-110">(Veja [detalhes técnicos de referência sobre criptografia no office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) para obter uma lista de pacotes de criptografia TLS compatíveis com o Office 365.) Isso se aplica aos protocolos usados por clientes como Outlook, Skype for Business e Outlook na Web (por exemplo, HTTP, POP3, etc.).</span><span class="sxs-lookup"><span data-stu-id="88f5b-110">(See [Technical reference details about encryption in Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) for a list of TLS cipher suites supported by Office 365.) This applies to the protocols that are used by clients such as Outlook, Skype for Business, and Outlook on the web (e.g., HTTP, POP3, etc.).</span></span>

<span data-ttu-id="88f5b-111">Os certificados públicos são emitidos pelo SSL de ti da Microsoft usando o SSLAdmin, uma ferramenta interna da Microsoft para proteger a confidencialidade das informações transmitidas.</span><span class="sxs-lookup"><span data-stu-id="88f5b-111">The public certificates are issued by Microsoft IT SSL using SSLAdmin, an internal Microsoft tool to protect confidentiality of transmitted information.</span></span> <span data-ttu-id="88f5b-112">Todos os certificados emitidos pela TI da Microsoft têm um mínimo de 2048 bits de duração, e a conformidade do WebTrust requer o SSLAdmin para garantir que os certificados sejam emitidos apenas para endereços IP públicos pertencentes à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="88f5b-112">All certificates issued by Microsoft IT have a minimum of 2048 bits in length, and Webtrust compliance requires SSLAdmin to make sure that certificates are issued only to public IP addresses owned by Microsoft.</span></span> <span data-ttu-id="88f5b-113">Qualquer endereço IP que não atenda a esse critério é roteado por meio de um processo de exceção.</span><span class="sxs-lookup"><span data-stu-id="88f5b-113">Any IP addresses that fail to meet this criterion are routed through an exception process.</span></span>

<span data-ttu-id="88f5b-114">Todos os detalhes de implementação, como a versão do TLS que está sendo usada, se o sigilo total (FS) está habilitado, a ordem de pacotes de codificação, etc., estão disponíveis publicamente.</span><span class="sxs-lookup"><span data-stu-id="88f5b-114">All implementation details such as the version of TLS being used, whether Forward Secrecy (FS) is enabled, the order of cipher suites, etc., are available publicly.</span></span> <span data-ttu-id="88f5b-115">Uma maneira de ver esses detalhes é usar um site de terceiros, como [laboratórios de Qualys SSL](https://www.ssllabs.com).</span><span class="sxs-lookup"><span data-stu-id="88f5b-115">One way to see these details is to use a third-party website, such as [Qualys SSL Labs](https://www.ssllabs.com).</span></span> <span data-ttu-id="88f5b-116">Veja a seguir os links para páginas de teste automatizadas do Qualys que exibem informações sobre os seguintes serviços:</span><span class="sxs-lookup"><span data-stu-id="88f5b-116">Below are the links to automated test pages from Qualys that display information for the following services:</span></span>

- [<span data-ttu-id="88f5b-117">Portal do Office 365</span><span class="sxs-lookup"><span data-stu-id="88f5b-117">Office 365 Portal</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [<span data-ttu-id="88f5b-118">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="88f5b-118">Exchange Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [<span data-ttu-id="88f5b-119">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="88f5b-119">SharePoint Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [<span data-ttu-id="88f5b-120">Skype for Business (SIP)</span><span class="sxs-lookup"><span data-stu-id="88f5b-120">Skype for Business (SIP)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [<span data-ttu-id="88f5b-121">Skype for Business (Web)</span><span class="sxs-lookup"><span data-stu-id="88f5b-121">Skype for Business (Web)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [<span data-ttu-id="88f5b-122">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="88f5b-122">Exchange Online Protection</span></span>](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [<span data-ttu-id="88f5b-123">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="88f5b-123">Microsoft Teams</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

<span data-ttu-id="88f5b-124">Para o Exchange Online Protection, as URLs variam de acordo com nomes de locatários; no entanto, todos os clientes podem testar o Microsoft 365 usando o **Microsoft-com.mail.Protection.Outlook.com**.</span><span class="sxs-lookup"><span data-stu-id="88f5b-124">For Exchange Online Protection, URLs vary by tenant names; however, all customers can test Microsoft 365 using **microsoft-com.mail.protection.outlook.com**.</span></span>
