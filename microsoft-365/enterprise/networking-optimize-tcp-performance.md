---
title: 'Etapa 5: Otimizar o desempenho do serviço do Office 365 com o cliente'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Definir as configurações de TCP e os serviços do Office 365 para melhorar o desempenho.
ms.openlocfilehash: 9e786b36d7a2afccc3b9112b815cd42a40317c15
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073181"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a><span data-ttu-id="2f7f7-103">Etapa 5: Otimizar o desempenho do serviço do Office 365 com o cliente</span><span class="sxs-lookup"><span data-stu-id="2f7f7-103">Step 5: Optimize client and Office 365 service performance</span></span>

<span data-ttu-id="2f7f7-104">*Esta etapa é opcional e aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="2f7f7-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="2f7f7-105">Você pode aumentar o desempenho ao ajustar a forma como o Protocolo de Controle de Transmissão (TCP) funciona entre dispositivos-cliente e os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="2f7f7-105">You can increase performance by fine tuning the way that the Transmission Control Protocol (TCP) works between client devices and Office 365 services.</span></span>

<span data-ttu-id="2f7f7-106">Para dispositivos-cliente, você pode alterar as seguintes configurações do TCP em dispositivos-cliente para otimizar o desempenho do TCP:</span><span class="sxs-lookup"><span data-stu-id="2f7f7-106">For client devices, you can change the following TCP settings on client devices to optimize TCP performance:</span></span>

- <span data-ttu-id="2f7f7-107">[Dimensionamento de janelas TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), para que seu dispositivo-cliente possa enviar mais dados antes de solicitar uma confirmação.</span><span class="sxs-lookup"><span data-stu-id="2f7f7-107">[TCP window scaling](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), so your client device can send more data before requiring an acknowledgement</span></span>
- <span data-ttu-id="2f7f7-108">[Tempo ocioso do TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), para que seu dispositivo-cliente possa lidar com conexões abertas com mais eficiência.</span><span class="sxs-lookup"><span data-stu-id="2f7f7-108">[TCP idle time](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), so your client device can handle open connections more efficiently</span></span>
- <span data-ttu-id="2f7f7-109">[Tamanho máximo de segmento TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), para que seu dispositivo-cliente possa enviar os maiores blocos de dados em um pacote.</span><span class="sxs-lookup"><span data-stu-id="2f7f7-109">[TCP maximum segment size](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), so your client device can send the largest blocks of data in a packet</span></span>
- <span data-ttu-id="2f7f7-110">[Confirmações seletivas do TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), para que seu dispositivo-cliente possa confirmar os dados recebidos com mais eficiência.</span><span class="sxs-lookup"><span data-stu-id="2f7f7-110">[TCP selective acknowledgements](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), so your client device can acknowledge received data more efficiently</span></span>

<span data-ttu-id="2f7f7-111">Com relação aos serviços do Office 365, consulte estes recursos adicionais para otimizar o desempenho:</span><span class="sxs-lookup"><span data-stu-id="2f7f7-111">For Office 365 services, see these additional resources to optimize performance:</span></span>

- [<span data-ttu-id="2f7f7-112">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2f7f7-112">Exchange Online</span></span>](https://support.office.com/article/Tune-Exchange-Online-performance-026e83cb-a945-4543-97b0-a8af6e80ac61)
- [<span data-ttu-id="2f7f7-113">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2f7f7-113">Skype for Business Online</span></span>](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802)
- [<span data-ttu-id="2f7f7-114">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2f7f7-114">SharePoint Online</span></span>](https://support.office.com/article/Tune-SharePoint-Online-performance-f0522d4a-fbf4-41f9-854e-c9b59555091d)
- [<span data-ttu-id="2f7f7-115">Project Online</span><span class="sxs-lookup"><span data-stu-id="2f7f7-115">Project Online</span></span>](https://support.office.com/article/Tune-Project-Online-performance-12ba0ebd-c616-42e5-b9b6-cad570e8409c)

<span data-ttu-id="2f7f7-116">Como ponto de verificação provisório, você pode consultar os [critérios de saída](networking-exit-criteria.md#crit-networking-step5) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="2f7f7-116">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step5) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="2f7f7-117">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="2f7f7-117">Next step</span></span>

[<span data-ttu-id="2f7f7-118">Critérios de saída da infraestrutura de rede</span><span class="sxs-lookup"><span data-stu-id="2f7f7-118">Networking infrastructure exit criteria</span></span>](networking-exit-criteria.md)
