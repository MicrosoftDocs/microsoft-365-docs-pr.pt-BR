---
title: Relatório de clientes de autenticação SMTP
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Os administradores podem saber mais sobre o relatório de clientes de autenticação SMTP no painel de fluxo de emails no centro de conformidade do & de segurança.
ms.openlocfilehash: 7d3977293b0456b9ab3d383c1a41be9858a66028
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073648"
---
# <a name="smtp-auth-clients-report"></a><span data-ttu-id="403f9-103">Relatório de clientes de autenticação SMTP</span><span class="sxs-lookup"><span data-stu-id="403f9-103">SMTP Auth clients report</span></span>

<span data-ttu-id="403f9-104">O relatório de **clientes de autenticação SMTP** realça o uso do protocolo de envio de cliente de autenticação SMTP por usuários ou contas de sistema em sua organização.</span><span class="sxs-lookup"><span data-stu-id="403f9-104">The **SMTP Auth clients** report highlights the use of the SMTP Auth client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="403f9-105">Este protocolo herdado (que usa o ponto de extremidade smtp.office365.com) só oferece autenticação básica e é suscetível a uso por contas comprometidas para enviar emails.</span><span class="sxs-lookup"><span data-stu-id="403f9-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span>  <span data-ttu-id="403f9-106">Este relatório permite verificar atividades incomuns.</span><span class="sxs-lookup"><span data-stu-id="403f9-106">This report allows you to check for unusual activity.</span></span> <span data-ttu-id="403f9-107">Ele também mostra os dados de uso de TLS para clientes ou dispositivos que usam a autenticação SMTP.</span><span class="sxs-lookup"><span data-stu-id="403f9-107">It also shows the TLS usage data for clients or devices using SMTP Auth.</span></span>

<span data-ttu-id="403f9-108">O widget que é mostrado no painel de fluxo de emails indica o número de usuários ou contas de serviço que usaram o protocolo de autenticação SMTP nos últimos sete dias.</span><span class="sxs-lookup"><span data-stu-id="403f9-108">The widget that's shown in the Mail Flow dashboard indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![O relatório de clientes de autenticação SMTP no painel de fluxo de emails no centro de conformidade & segurança](../media/smtp-auth-clients-report-selected.png)

<span data-ttu-id="403f9-110">Clicar no widget abre um submenu que fornece uma exibição agregada do uso e dos volumes de TLS para a última semana.</span><span class="sxs-lookup"><span data-stu-id="403f9-110">Clicking on the widget opens a flyout that provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![O submenu no relatório de clientes de autenticação SMTP](../media/smtp-auth-clients-flyout.png)

<span data-ttu-id="403f9-112">Ao clicar no link de **relatório de clientes de autenticação SMTP** , você verá dois dados dinâmicos principais e dois modos de exibição de dados.</span><span class="sxs-lookup"><span data-stu-id="403f9-112">When you click on the **SMTP Auth Clients Report** link, you'll see two main data pivots and two data views.</span></span> <span data-ttu-id="403f9-113">Os dados dinâmicos são o **volume de envio** e o **uso de TLS**.</span><span class="sxs-lookup"><span data-stu-id="403f9-113">The data pivots are the **Sending Volume** and **TLS Usage**.</span></span> <span data-ttu-id="403f9-114">Os modos de exibição de dados são o gráfico e a tabela de detalhes.</span><span class="sxs-lookup"><span data-stu-id="403f9-114">The data views are the chart and the details table.</span></span>

<span data-ttu-id="403f9-115">O modo de exibição de **volume de envio** mostra o número de mensagens que foram enviadas usando a autenticação SMTP no intervalo de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="403f9-115">The **Sending Volume** view shows the number of messages that were sent using SMTP Auth for the specified time range.</span></span> <span data-ttu-id="403f9-116">Você pode ajustar o intervalo clicando em **filtros**.</span><span class="sxs-lookup"><span data-stu-id="403f9-116">You can adjust the range by clicking **Filters**.</span></span> <span data-ttu-id="403f9-117">O gráfico é organizado por domínio de remetente.</span><span class="sxs-lookup"><span data-stu-id="403f9-117">The chart is organized by sender domain.</span></span> <span data-ttu-id="403f9-118">Você pode ver dados separados para cada domínio selecionando o domínio na lista suspensa **Mostrar dados para** .</span><span class="sxs-lookup"><span data-stu-id="403f9-118">You can see separate data for each domain by selecting the domain in the **Show data for** drop down.</span></span>

![Enviando o volume no relatório de clientes de autenticação SMTP](../media/smtp-auth-clients-report-sending-volume.png)

<span data-ttu-id="403f9-120">Você pode exibir informações detalhadas sobre os remetentes e suas contagens de mensagens clicando em **Exibir detalhes tabela**.</span><span class="sxs-lookup"><span data-stu-id="403f9-120">You can view detailed information about the senders and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="403f9-121">Para retornar ao gráfico, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="403f9-121">To return to the chart, click **View report**.</span></span>

![Tabela de detalhes para o envio de volume no relatório de clientes de autenticação SMTP](../media/smtp-auth-clients-report-details-sending-volume.png)

<span data-ttu-id="403f9-123">A tabela dinâmica de **uso de TLS** é importante devido à futura substituição de TLS 1.0 e TLS 1.1 no Office 365.</span><span class="sxs-lookup"><span data-stu-id="403f9-123">The **TLS Usage** pivot is important due to the upcoming deprecation of TLS1.0 and TLS1.1 in Office 365.</span></span> <span data-ttu-id="403f9-124">Muitos dispositivos e aplicativos herdados não poderão enviar emails se eles só forem capazes de usar o TLS 1.0 com autenticação SMTP. Essa tabela dinâmica permite que você identifique e execute ações sobre usuários e contas de sistema que ainda estão usando versões mais antigas do TLS.</span><span class="sxs-lookup"><span data-stu-id="403f9-124">Many legacy devices and applications will be unable to send email if they are only capable of using TLS1.0 with SMTP Auth. This pivot allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

![Uso de TLS no relatório de clientes de autenticação SMTP](../media/smtp-auth-clients-report-tls-usage.png)

<span data-ttu-id="403f9-126">Você pode exibir informações detalhadas sobre os remetentes, as versões do TLS que estão usando a autenticação SMTP e suas contagens de mensagens clicando em **Exibir detalhes tabela**.</span><span class="sxs-lookup"><span data-stu-id="403f9-126">You can view detailed information about the senders, the versions of TLS they are using with SMTP Auth, and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="403f9-127">Para retornar ao gráfico, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="403f9-127">To return to the chart, click **View report**.</span></span>

<span data-ttu-id="403f9-128">Você também pode baixar uma versão mais detalhada do relatório clicando em solicitação de relatório.</span><span class="sxs-lookup"><span data-stu-id="403f9-128">You can also download a more detailed version of the report by clicking Request report.</span></span>

![Tabela de detalhes para uso de TLS no relatório de clientes de autenticação SMTP](../media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="see-also"></a><span data-ttu-id="403f9-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="403f9-130">See also</span></span>

<span data-ttu-id="403f9-131">Para obter mais informações sobre outros insights de fluxo de email no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="403f9-131">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
