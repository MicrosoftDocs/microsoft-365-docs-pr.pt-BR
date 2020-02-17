---
title: 'Etapa 5: Otimizar o desempenho do serviço do Office 365 com o cliente'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Definir as configurações de TCP e os serviços do Office 365 para melhorar o desempenho.
ms.openlocfilehash: e3aefb417330ab791a3dd217e2e34591eba3e1d1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066537"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a><span data-ttu-id="7d454-103">Etapa 5: Otimizar o desempenho do serviço do Office 365 com o cliente</span><span class="sxs-lookup"><span data-stu-id="7d454-103">Step 5: Optimize client and Office 365 service performance</span></span>

<span data-ttu-id="7d454-104">*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="7d454-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 1 – Rede](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="7d454-106">Você pode aumentar o desempenho ao ajustar a forma como o Protocolo de Controle de Transmissão (TCP) funciona entre dispositivos-cliente e os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d454-106">You can increase performance by fine tuning the way that the Transmission Control Protocol (TCP) works between client devices and Office 365 services.</span></span>

<span data-ttu-id="7d454-107">Para dispositivos-cliente, você pode alterar as seguintes configurações do TCP em dispositivos-cliente para otimizar o desempenho do TCP:</span><span class="sxs-lookup"><span data-stu-id="7d454-107">For client devices, you can change the following TCP settings on client devices to optimize TCP performance:</span></span>

- <span data-ttu-id="7d454-108">[Dimensionamento de janelas TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), para que seu dispositivo-cliente possa enviar mais dados antes de solicitar uma confirmação.</span><span class="sxs-lookup"><span data-stu-id="7d454-108">[TCP window scaling](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), so your client device can send more data before requiring an acknowledgement</span></span>
- <span data-ttu-id="7d454-109">[Tempo ocioso do TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), para que seu dispositivo-cliente possa lidar com conexões abertas com mais eficiência.</span><span class="sxs-lookup"><span data-stu-id="7d454-109">[TCP idle time](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), so your client device can handle open connections more efficiently</span></span>
- <span data-ttu-id="7d454-110">[Tamanho máximo de segmento TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), para que seu dispositivo-cliente possa enviar os maiores blocos de dados em um pacote.</span><span class="sxs-lookup"><span data-stu-id="7d454-110">[TCP maximum segment size](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), so your client device can send the largest blocks of data in a packet</span></span>
- <span data-ttu-id="7d454-111">[Confirmações seletivas do TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), para que seu dispositivo-cliente possa confirmar os dados recebidos com mais eficiência.</span><span class="sxs-lookup"><span data-stu-id="7d454-111">[TCP selective acknowledgements](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), so your client device can acknowledge received data more efficiently</span></span>

<span data-ttu-id="7d454-112">Com relação aos serviços do Office 365, consulte estes recursos adicionais para otimizar o desempenho:</span><span class="sxs-lookup"><span data-stu-id="7d454-112">For Office 365 services, see these additional resources to optimize performance:</span></span>

- [<span data-ttu-id="7d454-113">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7d454-113">Exchange Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [<span data-ttu-id="7d454-114">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7d454-114">Skype for Business Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [<span data-ttu-id="7d454-115">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7d454-115">SharePoint Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [<span data-ttu-id="7d454-116">Project Web App no Project Online</span><span class="sxs-lookup"><span data-stu-id="7d454-116">Project Web App in Project Online</span></span>](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

<span data-ttu-id="7d454-117">Como um ponto de verificação provisório, é possível ver os [critérios de saída](networking-exit-criteria.md#crit-networking-step5) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="7d454-117">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step5) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="7d454-118">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="7d454-118">Next step</span></span>

[<span data-ttu-id="7d454-119">Critérios de saída da infraestrutura de rede</span><span class="sxs-lookup"><span data-stu-id="7d454-119">Networking infrastructure exit criteria</span></span>](networking-exit-criteria.md)
