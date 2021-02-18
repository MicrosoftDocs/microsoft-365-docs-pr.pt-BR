---
title: Insight e relatório de clientes de Auth SMTP no painel de fluxo de emails
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o insight e o relatório de autenticação SMTP no painel de fluxo de emails no Centro de Conformidade & e Segurança para monitorar os envios de email em sua organização que usam SMTP autenticado (SMTP AUTH) para enviar mensagens de email.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9050fd2c1bc3863a3bd78190cd5b27fda018479e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287792"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="83c45-103">Insight e relatório de clientes de Auth SMTP no Centro de Conformidade e & Segurança</span><span class="sxs-lookup"><span data-stu-id="83c45-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="83c45-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="83c45-104">**Applies to**</span></span>
- [<span data-ttu-id="83c45-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="83c45-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="83c45-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="83c45-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="83c45-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83c45-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="83c45-108">Os insights dos clientes de **Auth SMTP** no painel de fluxo de emails e no relatório de clientes de [Auth SMTP](#smtp-auth-clients-report) associados no Centro de Conformidade [do &](https://protection.office.com) de Segurança destacam o uso do protocolo de envio de cliente SMTP AUTH por usuários ou contas do sistema em sua organização. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="83c45-108">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="83c45-109">Esse protocolo herdado (que usa o ponto de extremidade smtp.office365.com) só oferece autenticação Básica e é suscetível a ser usado por contas comprometidas para enviar emails.</span><span class="sxs-lookup"><span data-stu-id="83c45-109">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="83c45-110">O insight e o relatório permitem que você verifique se há atividades incomuns para envios de email SMTP AUTH.</span><span class="sxs-lookup"><span data-stu-id="83c45-110">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="83c45-111">Ele também mostra os dados de uso do TLS para clientes ou dispositivos que usam SMTP AUTH.</span><span class="sxs-lookup"><span data-stu-id="83c45-111">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="83c45-112">O widget indica o número de usuários ou contas de serviço que usaram o protocolo de Auth SMTP nos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="83c45-112">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![Widget de clientes de Auth SMTP no painel Fluxo de emails no Centro de Conformidade e Segurança & Segurança](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="83c45-114">Se você clicar no número de mensagens no widget, um flyout de clientes **de Auth SMTP** será exibido.</span><span class="sxs-lookup"><span data-stu-id="83c45-114">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="83c45-115">O flyout fornece uma exibição agregada do uso e volumes do TLS da última semana.</span><span class="sxs-lookup"><span data-stu-id="83c45-115">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Detalhes do flyout depois de clicar no widget de clientes de Auth SMTP no painel de fluxo de emails](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="83c45-117">Você pode clicar no link de relatório de clientes de **Auth SMTP** para ir para o relatório de clientes de Auth SMTP, conforme descrito na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="83c45-117">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="83c45-118">Relatório de clientes de autenticação SMTP</span><span class="sxs-lookup"><span data-stu-id="83c45-118">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="83c45-119">Exibição de relatório para o relatório de clientes de Auth SMTP</span><span class="sxs-lookup"><span data-stu-id="83c45-119">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="83c45-120">Por padrão, o relatório mostra dados dos últimos 7 dias, mas os dados estão disponíveis para os últimos 90 dias.</span><span class="sxs-lookup"><span data-stu-id="83c45-120">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="83c45-121">A seção visão geral contém os seguintes gráficos:</span><span class="sxs-lookup"><span data-stu-id="83c45-121">The overview section contains the following charts:</span></span>

- <span data-ttu-id="83c45-122">Exibir dados por: Volume de **envio:** Por padrão, o gráfico mostra o número de mensagens de cliente de Auth SMTP que foram enviadas de todos os domínios ( Mostrar dados para: Todos os domínios de remetentes são **selecionados** por padrão).</span><span class="sxs-lookup"><span data-stu-id="83c45-122">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="83c45-123">Você pode filtrar os resultados para um  domínio de remetente específico clicando em Mostrar dados e selecionando o domínio do remetente na lista suspenso.</span><span class="sxs-lookup"><span data-stu-id="83c45-123">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="83c45-124">Se você passar o mouse sobre um ponto de dados específico (dia), o número de mensagens será mostrado.</span><span class="sxs-lookup"><span data-stu-id="83c45-124">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![Exibição de volume de envio no relatório de clientes de Auth SMTP no Centro de Conformidade & Segurança](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="83c45-126">**Exibir dados por: Uso de TLS:** o gráfico mostra a porcentagem de uso de TLS para todas as mensagens de cliente de Auth SMTP durante o período de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="83c45-126">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="83c45-127">Este gráfico permite identificar e tomar medidas em usuários e contas do sistema que ainda usam versões mais antigas do TLS.</span><span class="sxs-lookup"><span data-stu-id="83c45-127">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![Exibição de uso do TLS no relatório de clientes de Auth SMTP no Centro de Conformidade & Segurança](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="83c45-129">Se você clicar em **Filtros** em uma exibição de relatório, poderá especificar um intervalo de datas com data **de** início **e data de término.**</span><span class="sxs-lookup"><span data-stu-id="83c45-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="83c45-130">Clique **em Solicitar relatório** para receber uma versão mais detalhada do relatório em uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="83c45-130">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="83c45-131">Você pode especificar o intervalo de datas e os destinatários para receber o relatório.</span><span class="sxs-lookup"><span data-stu-id="83c45-131">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="83c45-132">Visão de tabela de detalhes do relatório de clientes de Auth SMTP</span><span class="sxs-lookup"><span data-stu-id="83c45-132">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="83c45-133">Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:</span><span class="sxs-lookup"><span data-stu-id="83c45-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="83c45-134">**Exibir dados por: Volume de envio:** as seguintes informações são mostradas em uma tabela:</span><span class="sxs-lookup"><span data-stu-id="83c45-134">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="83c45-135">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="83c45-135">**Sender address**</span></span>
  - <span data-ttu-id="83c45-136">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="83c45-136">**Message count**</span></span>

  <span data-ttu-id="83c45-137">Se você selecionar uma linha, os mesmos detalhes serão mostrados em um flyout.</span><span class="sxs-lookup"><span data-stu-id="83c45-137">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="83c45-138">**Exibir dados por: Uso do TLS:** as seguintes informações são mostradas em uma tabela:</span><span class="sxs-lookup"><span data-stu-id="83c45-138">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="83c45-139">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="83c45-139">**Sender address**</span></span>
  - <span data-ttu-id="83c45-140">**TLS1,0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="83c45-140">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="83c45-141">**TLS1,1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="83c45-141">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="83c45-142">**TLS1,2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="83c45-142">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="83c45-143">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="83c45-143">**Message count**</span></span>

  <span data-ttu-id="83c45-144"><sup>\*</sup> Esta coluna mostra a porcentagem e o número de mensagens do remetente.</span><span class="sxs-lookup"><span data-stu-id="83c45-144"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="83c45-145">Se você clicar em **Filtros** em uma exibição de tabela de detalhes, poderá especificar um intervalo de datas com data de **início** **e data de término.**</span><span class="sxs-lookup"><span data-stu-id="83c45-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="83c45-146">Se você selecionar uma linha, detalhes semelhantes serão mostrados em um flyout:</span><span class="sxs-lookup"><span data-stu-id="83c45-146">If you select a row, similar details are shown in a flyout:</span></span>

![Detalhes do flyout da tabela de detalhes do ponto de vista de uso do TLS no relatório de clientes de Auth SMTP](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="83c45-148">Clique **em Solicitar relatório** para receber uma versão mais detalhada do relatório em uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="83c45-148">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="83c45-149">Você pode especificar o intervalo de datas e os destinatários para receber o relatório.</span><span class="sxs-lookup"><span data-stu-id="83c45-149">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="83c45-150">Para voltar para a exibição de relatórios, clique em **Exibir relatório.**</span><span class="sxs-lookup"><span data-stu-id="83c45-150">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="83c45-151">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="83c45-151">Related topics</span></span>

<span data-ttu-id="83c45-152">Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações sobre o fluxo de emails no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="83c45-152">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
