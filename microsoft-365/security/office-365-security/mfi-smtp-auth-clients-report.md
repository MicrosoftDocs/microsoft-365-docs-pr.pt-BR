---
title: Informações e relatório dos clientes do Auth SMTP no painel de fluxo de emails
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
description: Os administradores podem aprender a usar o insight e o relatório do SMTP Auth no painel de fluxo de emails no Centro de Conformidade do & de Segurança para monitorar os envios de email em sua organização que usam SMTP (SMTP AUTH) autenticados para enviar mensagens de email.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a979f0e80fc303868bf2572974563323035fc4bc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51202975"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="db2c8-103">Informações e relatório dos clientes do Auth SMTP no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="db2c8-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="db2c8-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="db2c8-104">**Applies to**</span></span>
- [<span data-ttu-id="db2c8-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="db2c8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="db2c8-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="db2c8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="db2c8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db2c8-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="db2c8-108">A visão dos clientes **do Auth SMTP** no painel de fluxo de email e o relatório de clientes [Auth SMTP](#smtp-auth-clients-report) associados no Centro de Conformidade do & de Segurança realçam [o](https://protection.office.com) uso do protocolo de envio de cliente AUTH SMTP por usuários ou contas do sistema em sua organização. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="db2c8-108">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="db2c8-109">Esse protocolo herdado (que usa o ponto de extremidade smtp.office365.com) só oferece autenticação básica e é suscetível a ser usado por contas comprometidas para enviar emails.</span><span class="sxs-lookup"><span data-stu-id="db2c8-109">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="db2c8-110">O insight e o relatório permitem que você verifique se há atividades incomuns para envios de email SMTP AUTH.</span><span class="sxs-lookup"><span data-stu-id="db2c8-110">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="db2c8-111">Ele também mostra os dados de uso TLS para clientes ou dispositivos que usam AUTH SMTP.</span><span class="sxs-lookup"><span data-stu-id="db2c8-111">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="db2c8-112">O widget indica o número de usuários ou contas de serviço que usaram o protocolo Auth SMTP nos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="db2c8-112">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![Widget de clientes do Auth SMTP no painel de fluxo de email no Centro de Conformidade & Segurança](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="db2c8-114">Se você clicar no número de mensagens no widget, será exibido um flyout de clientes **Auth SMTP.**</span><span class="sxs-lookup"><span data-stu-id="db2c8-114">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="db2c8-115">O flyout fornece uma exibição agregada do uso e volumes TLS da última semana.</span><span class="sxs-lookup"><span data-stu-id="db2c8-115">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Detalhes do sobrevoo depois de clicar no widget de clientes do Auth SMTP no painel fluxo de emails](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="db2c8-117">Você pode clicar no link de relatório de clientes **SMTP Auth** para ir para o relatório de clientes Auth SMTP, conforme descrito na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="db2c8-117">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="db2c8-118">Relatório de clientes de autenticação SMTP</span><span class="sxs-lookup"><span data-stu-id="db2c8-118">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="db2c8-119">Exibição de relatório para o relatório de clientes Auth SMTP</span><span class="sxs-lookup"><span data-stu-id="db2c8-119">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="db2c8-120">Por padrão, o relatório mostra dados dos últimos 7 dias, mas os dados estão disponíveis nos últimos 90 dias.</span><span class="sxs-lookup"><span data-stu-id="db2c8-120">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="db2c8-121">A seção visão geral contém os seguintes gráficos:</span><span class="sxs-lookup"><span data-stu-id="db2c8-121">The overview section contains the following charts:</span></span>

- <span data-ttu-id="db2c8-122">Exibir dados **por:** Volume de envio : Por padrão, o gráfico mostra o número de mensagens de cliente SMTP Auth enviadas de todos os domínios ( Mostrar dados para: Todos os domínios de remetente **são selecionados** por padrão).</span><span class="sxs-lookup"><span data-stu-id="db2c8-122">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="db2c8-123">Você pode filtrar os resultados para um domínio de remetente específico clicando em **Mostrar dados** e selecionando o domínio do remetente na lista de menus suspensos.</span><span class="sxs-lookup"><span data-stu-id="db2c8-123">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="db2c8-124">Se você passar o mouse em um ponto de dados específico (dia), o número de mensagens será mostrado.</span><span class="sxs-lookup"><span data-stu-id="db2c8-124">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![Enviar exibição de volume no relatório de clientes do Auth SMTP no Centro de Conformidade & Segurança](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="db2c8-126">**Exibir dados por: Uso do TLS**: O gráfico mostra a porcentagem de uso do TLS para todas as mensagens de cliente SMTP Auth durante o período de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="db2c8-126">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="db2c8-127">Este gráfico permite identificar e tomar medidas em usuários e contas do sistema que ainda estão usando versões mais antigas do TLS.</span><span class="sxs-lookup"><span data-stu-id="db2c8-127">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![Exibição de uso do TLS no relatório de clientes do Auth SMTP no Centro de Conformidade & Segurança](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="db2c8-129">Se você clicar **em Filtros** em um exibição de relatório, poderá especificar um intervalo de datas com **Data de** Início e Data **de Término.**</span><span class="sxs-lookup"><span data-stu-id="db2c8-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="db2c8-130">Clique **em Solicitar relatório** para receber uma versão mais detalhada do relatório em uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="db2c8-130">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="db2c8-131">Você pode especificar o intervalo de datas e os destinatários para receber o relatório.</span><span class="sxs-lookup"><span data-stu-id="db2c8-131">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="db2c8-132">Exibição de tabela de detalhes para o relatório de clientes SMTP Auth</span><span class="sxs-lookup"><span data-stu-id="db2c8-132">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="db2c8-133">Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:</span><span class="sxs-lookup"><span data-stu-id="db2c8-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="db2c8-134">**Exibir dados por: Volume de envio**: As seguintes informações são mostradas em uma tabela:</span><span class="sxs-lookup"><span data-stu-id="db2c8-134">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="db2c8-135">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="db2c8-135">**Sender address**</span></span>
  - <span data-ttu-id="db2c8-136">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="db2c8-136">**Message count**</span></span>

  <span data-ttu-id="db2c8-137">Se você selecionar uma linha, os mesmos detalhes serão mostrados em um sobremenu.</span><span class="sxs-lookup"><span data-stu-id="db2c8-137">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="db2c8-138">**Exibir dados por: Uso do TLS**: As informações a seguir são mostradas em uma tabela:</span><span class="sxs-lookup"><span data-stu-id="db2c8-138">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="db2c8-139">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="db2c8-139">**Sender address**</span></span>
  - <span data-ttu-id="db2c8-140">**TLS1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db2c8-140">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="db2c8-141">**TLS1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db2c8-141">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="db2c8-142">**TLS1,2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db2c8-142">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="db2c8-143">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="db2c8-143">**Message count**</span></span>

  <span data-ttu-id="db2c8-144"><sup>\*</sup> Esta coluna mostra a porcentagem e o número de mensagens do remetente.</span><span class="sxs-lookup"><span data-stu-id="db2c8-144"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="db2c8-145">Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá especificar um intervalo de datas com **Data de** início e data **de término.**</span><span class="sxs-lookup"><span data-stu-id="db2c8-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="db2c8-146">Se você selecionar uma linha, detalhes semelhantes serão mostrados em um sobremenu:</span><span class="sxs-lookup"><span data-stu-id="db2c8-146">If you select a row, similar details are shown in a flyout:</span></span>

![Detalhes do flyout da tabela de detalhes do exibição de uso TLS no relatório de clientes do Auth SMTP](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="db2c8-148">Clique **em Solicitar relatório** para receber uma versão mais detalhada do relatório em uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="db2c8-148">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="db2c8-149">Você pode especificar o intervalo de datas e os destinatários para receber o relatório.</span><span class="sxs-lookup"><span data-stu-id="db2c8-149">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="db2c8-150">Para voltar à exibição de relatórios, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="db2c8-150">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="db2c8-151">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="db2c8-151">Related topics</span></span>

<span data-ttu-id="db2c8-152">Para obter informações sobre outras informações no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de Conformidade & [Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="db2c8-152">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
