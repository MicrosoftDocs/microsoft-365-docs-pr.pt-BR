---
title: Relatórios de clientes de autenticação SMTP percepção e relatório no painel de fluxo de emails
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar a percepção e o relatório de autenticação SMTP no painel de fluxo de emails no centro de conformidade de & de segurança para monitorar remetentes de email em sua organização que usam SMTP autenticado (autenticação SMTP) para enviar mensagens de email.
ms.openlocfilehash: 4123edcfa08e31217dcd6a29186492bc036fa7a0
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357429"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="e63fb-103">Clientes de autenticação SMTP percepção e relatório no centro de conformidade e segurança &</span><span class="sxs-lookup"><span data-stu-id="e63fb-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

<span data-ttu-id="e63fb-104">Os **clientes de autenticação SMTP** se aprofundam no [painel de fluxo de emails](mail-flow-insights-v2.md) e no [relatório de clientes de autenticação SMTP](#smtp-auth-clients-report) associado no [centro de conformidade & de segurança](https://protection.office.com) realçar o uso do protocolo de envio de cliente de autenticação SMTP por usuários ou contas de sistema em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e63fb-104">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="e63fb-105">Este protocolo herdado (que usa o ponto de extremidade smtp.office365.com) só oferece autenticação básica e é suscetível a uso por contas comprometidas para enviar emails.</span><span class="sxs-lookup"><span data-stu-id="e63fb-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="e63fb-106">A percepção e o relatório permitem verificar se há atividades incomuns para envios de email de autenticação SMTP.</span><span class="sxs-lookup"><span data-stu-id="e63fb-106">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="e63fb-107">Ele também mostra os dados de uso de TLS para clientes ou dispositivos que usam a autenticação SMTP.</span><span class="sxs-lookup"><span data-stu-id="e63fb-107">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="e63fb-108">O widget indica o número de usuários ou contas de serviço que usaram o protocolo de autenticação SMTP nos últimos sete dias.</span><span class="sxs-lookup"><span data-stu-id="e63fb-108">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![Widget clientes de autenticação SMTP no painel de fluxo de emails no centro de conformidade & segurança](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="e63fb-110">Se você clicar no número de mensagens no widget, um submenu de **clientes de autenticação SMTP** será exibido.</span><span class="sxs-lookup"><span data-stu-id="e63fb-110">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="e63fb-111">O submenu fornece uma exibição agregada do uso e dos volumes de TLS para a última semana.</span><span class="sxs-lookup"><span data-stu-id="e63fb-111">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Submenu de detalhes após clicar no widget clientes de autenticação SMTP no painel de fluxo de emails](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="e63fb-113">Você pode clicar no link **relatório de clientes de autenticação SMTP** para acessar o relatório de clientes de autenticação SMTP, conforme descrito na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="e63fb-113">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="e63fb-114">Relatório de clientes de autenticação SMTP</span><span class="sxs-lookup"><span data-stu-id="e63fb-114">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="e63fb-115">Exibição de relatório para o relatório de clientes de autenticação SMTP</span><span class="sxs-lookup"><span data-stu-id="e63fb-115">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="e63fb-116">Por padrão, o relatório mostra os dados dos últimos 7 dias, mas os dados estão disponíveis nos últimos 90 dias.</span><span class="sxs-lookup"><span data-stu-id="e63fb-116">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="e63fb-117">A seção visão geral contém os seguintes gráficos:</span><span class="sxs-lookup"><span data-stu-id="e63fb-117">The overview section contains the following charts:</span></span>

- <span data-ttu-id="e63fb-118">**Exibir dados por: enviando o volume**: por padrão, o gráfico mostra o número de mensagens de cliente de autenticação SMTP que foram enviadas de todos os domínios (**Mostrar dados de: todos os domínios do remetente** estão selecionados por padrão).</span><span class="sxs-lookup"><span data-stu-id="e63fb-118">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="e63fb-119">Você pode filtrar os resultados em um domínio de remetente específico clicando em **Mostrar dados para** e selecionando o domínio do remetente na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="e63fb-119">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="e63fb-120">Se você focalizar um ponto de dados específico (dia), o número de mensagens será exibido.</span><span class="sxs-lookup"><span data-stu-id="e63fb-120">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![Enviando o modo de exibição de volume no relatório de clientes de autenticação SMTP no centro de conformidade & segurança](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="e63fb-122">**Exibir dados por: uso de TLS**: o gráfico mostra a porcentagem de uso de TLS para todas as mensagens de cliente de autenticação SMTP durante o período de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="e63fb-122">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="e63fb-123">Este gráfico permite identificar e executar ações sobre usuários e contas de sistema que ainda estão usando versões mais antigas do TLS.</span><span class="sxs-lookup"><span data-stu-id="e63fb-123">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![Modo de exibição de uso de TLS no relatório de clientes de autenticação SMTP no centro de conformidade & segurança](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="e63fb-125">Se você clicar em **filtros** em um modo de exibição de relatório, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="e63fb-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e63fb-126">Clique em **solicitar relatório** para receber uma versão mais detalhada do relatório em uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="e63fb-126">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="e63fb-127">Você pode especificar o intervalo de datas e os destinatários que receberão o relatório.</span><span class="sxs-lookup"><span data-stu-id="e63fb-127">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="e63fb-128">Exibição da tabela de detalhes para o relatório de clientes de autenticação SMTP</span><span class="sxs-lookup"><span data-stu-id="e63fb-128">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="e63fb-129">Se você clicar em **Exibir tabela de detalhes**, as informações mostradas dependem do gráfico que você estava observando:</span><span class="sxs-lookup"><span data-stu-id="e63fb-129">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="e63fb-130">**Exibir dados por: enviando volume**: as informações a seguir são mostradas em uma tabela:</span><span class="sxs-lookup"><span data-stu-id="e63fb-130">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="e63fb-131">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="e63fb-131">**Sender address**</span></span>
  - <span data-ttu-id="e63fb-132">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="e63fb-132">**Message count**</span></span>

  <span data-ttu-id="e63fb-133">Se você selecionar uma linha, os mesmos detalhes serão mostrados em um submenu.</span><span class="sxs-lookup"><span data-stu-id="e63fb-133">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="e63fb-134">**Exibir dados por: uso de TLS**: as seguintes informações são mostradas em uma tabela:</span><span class="sxs-lookup"><span data-stu-id="e63fb-134">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="e63fb-135">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="e63fb-135">**Sender address**</span></span>
  - <span data-ttu-id="e63fb-136">**TLS 1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e63fb-136">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="e63fb-137">**TLS 1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e63fb-137">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="e63fb-138">**TLS 1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e63fb-138">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="e63fb-139">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="e63fb-139">**Message count**</span></span>

  <span data-ttu-id="e63fb-140"><sup>\*</sup> Esta coluna mostra a porcentagem e o número de mensagens do remetente.</span><span class="sxs-lookup"><span data-stu-id="e63fb-140"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="e63fb-141">Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="e63fb-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e63fb-142">Se você selecionar uma linha, os detalhes semelhantes serão mostrados em um submenu:</span><span class="sxs-lookup"><span data-stu-id="e63fb-142">If you select a row, similar details are shown in a flyout:</span></span>

![Submenu de detalhes da tabela detalhes do modo de exibição uso de TLS no relatório de clientes de autenticação SMTP](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="e63fb-144">Clique em **solicitar relatório** para receber uma versão mais detalhada do relatório em uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="e63fb-144">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="e63fb-145">Você pode especificar o intervalo de datas e os destinatários que receberão o relatório.</span><span class="sxs-lookup"><span data-stu-id="e63fb-145">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="e63fb-146">Para voltar para o modo de exibição relatórios, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="e63fb-146">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e63fb-147">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e63fb-147">Related topics</span></span>

<span data-ttu-id="e63fb-148">Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="e63fb-148">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
