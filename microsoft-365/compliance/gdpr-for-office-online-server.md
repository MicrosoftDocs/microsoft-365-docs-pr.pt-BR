---
title: RGPD para Servidor do Office Online e para o Servidor do Office Web Apps
description: Neste artigo, você aprenderá sobre como resolver os requisitos do RGPD para o servidor do Office Online e para o Office Web Apps.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 84ea370f513ade134df75b2ee4e0912d6a623227
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547337"
---
# <a name="gdpr-for-office-web-apps-server-and-office-online-server"></a><span data-ttu-id="d67d5-103">RGPD para Servidor do Office Web Apps e Servidor do Office Online</span><span class="sxs-lookup"><span data-stu-id="d67d5-103">GDPR for Office Web Apps Server and Office Online Server</span></span>

<span data-ttu-id="d67d5-p101">Dados de telemetria do Servidor do Office Web Apps e do Servidor do Office Online são armazenados em forma de logs ULS. Você pode usar [ULSViewer](https://www.microsoft.com/download/details.aspx?id=44020) para exibir os logs ULS do seu locatário local.</span><span class="sxs-lookup"><span data-stu-id="d67d5-p101">Office Online Server and Office Web Apps Server telemetry data is stored in the form of ULS logs. You can use [ULS Viewer](https://www.microsoft.com/download/details.aspx?id=44020) to view ULS logs from your on-premises tenant.</span></span>

<span data-ttu-id="d67d5-p102">Todas as linhas de log contêm uma CorrelationID. Linhas de log relacionadas compartilham a mesma CorrelationID. Cada CorrelationID está vinculada a uma SessionID e uma SessionID pode estar relacionada a muitas CorrelationIDs. Cada SessionID pode estar relacionada a uma única UserID, embora algumas sessões possam ser anônimas e, portanto, não estarem associadas a uma UserID. Para determinar quais dados estão associados a um usuário específico, é possível mapear de uma única UserID para as SessionIDs associadas ao usuário, das SessionIDs para as CorrelationIDs associadas, e dessas CorrelationIDs para todos os logs nessas correlações. Confira o diagrama abaixo para verificar a relação entre as diferentes IDs.</span><span class="sxs-lookup"><span data-stu-id="d67d5-p102">Every log line contains a CorrelationID. Related log lines share the same CorrelationID. Each CorrelationID is tied to a single SessionID, and one SessionID may be related to many CorrelationIDs. Each SessionID may be related to a single UserID, although some sessions can be anonymous and therefore not have an associated UserID. In order to determine what data is associated with a particular user, it is therefore possible to map from a single UserID to the SessionIDs associated with that user, from those SessionIDs to the associated CorrelationIDs, and from those CorrelationIDs to all the logs in those correlations. See the below diagram for the relationship between the different IDs.</span></span>

![Fluxograma mostrando a relação entre SessionIDs e CorrelationIds](../media/gdpr-for-office-online-server-image1.jpg)

## <a name="gathering-logs"></a><span data-ttu-id="d67d5-113">Coletar logs</span><span class="sxs-lookup"><span data-stu-id="d67d5-113">Gathering Logs</span></span>

<span data-ttu-id="d67d5-p103">Para reunir todos os logs associados com a UserID 1, por exemplo, a primeira etapa é reunir todas as sessões associadas à UserID 1 (ou seja, SessionID 1 e SessionID2). A próxima etapa será reunir todas as correlações associadas com a SessionID 1 (ou seja, CorrelationIDs 1, 2 e 3) e com a SessionID 2 (ou seja, CorrelationID 4). Por fim, reúna todos os logs associados a cada correlação na lista.</span><span class="sxs-lookup"><span data-stu-id="d67d5-p103">In order to gather all logs associated with UserID 1, for example, the first step would be to gather all sessions associated with UserID 1 (i.e. SessionID 1 and SessionID2). The next step would be to gather all correlations associated with SessionID 1 (i.e. CorrelationIDs 1, 2, and 3) and with SessionID 2 (i.e. CorrelationID 4). Finally, gather all logs associated with each of the correlations in the list.</span></span>

1. <span data-ttu-id="d67d5-117">Iniciar o ULSViewer</span><span class="sxs-lookup"><span data-stu-id="d67d5-117">Launch UlsViewer</span></span>

2. <span data-ttu-id="d67d5-118">Abra o log ULS correspondente ao período de tempo pretendido; logs ULS são armazenados em %PROGRAMDATA%\\Microsoft\\OfficeWebApps\\Data\\Logs\\ULS</span><span class="sxs-lookup"><span data-stu-id="d67d5-118">Open up the uls log corresponding to the intended timeframe; ULS logs are stored in %PROGRAMDATA%\\Microsoft\\OfficeWebApps\\Data\\Logs\\ULS</span></span>

3. <span data-ttu-id="d67d5-119">Editar | Modificar Filtro</span><span class="sxs-lookup"><span data-stu-id="d67d5-119">Edit | Modify Filter</span></span>

4. <span data-ttu-id="d67d5-120">Aplique um filtro que seja:</span><span class="sxs-lookup"><span data-stu-id="d67d5-120">Apply a filter that is:</span></span>

    - <span data-ttu-id="d67d5-121">EventID igual a apr3y</span><span class="sxs-lookup"><span data-stu-id="d67d5-121">EventID equals apr3y</span></span>

      <span data-ttu-id="d67d5-122">Ou</span><span class="sxs-lookup"><span data-stu-id="d67d5-122">Or</span></span>

    - <span data-ttu-id="d67d5-123">EventID igual a bp2d6</span><span class="sxs-lookup"><span data-stu-id="d67d5-123">EventID equals bp2d6</span></span>

5. <span data-ttu-id="d67d5-124">UserIDs com hash estarão na mensagem de qualquer um desses dois eventos</span><span class="sxs-lookup"><span data-stu-id="d67d5-124">Hashed UserIds will be in the Message of either one of these two events</span></span>

6. <span data-ttu-id="d67d5-125">Para apr3y, a mensagem conterá um valor de UserID e um valor de PUID</span><span class="sxs-lookup"><span data-stu-id="d67d5-125">For apr3y, the Message will contain a UserID value and a PUID value</span></span>

7. <span data-ttu-id="d67d5-p104">Para bp2d6, a mensagem conterá uma grande quantidade de informações. O campo de valor LoggableUserId é a UserID com hash.</span><span class="sxs-lookup"><span data-stu-id="d67d5-p104">For bp2d6, the Message will contain quite a bit of information. The LoggableUserId Value field is the hashed UserID.</span></span>

8. <span data-ttu-id="d67d5-128">Depois de obter a UserID com hash dessas duas marcas, o valor de WacSessionId dessa linha no ULSViewer conterá a WacSessionId associada ao usuário</span><span class="sxs-lookup"><span data-stu-id="d67d5-128">Once the hashed UserId is obtained from either of these two tags, the WacSessionId value of that row in ULSViewer will contain the WacSessionId associated with that user</span></span>

9. <span data-ttu-id="d67d5-129">Colete todos os valores de WacSessionId associados com usuários em questão</span><span class="sxs-lookup"><span data-stu-id="d67d5-129">Collect all of the WacSessionId values associated with the user in question</span></span>

10. <span data-ttu-id="d67d5-130">Filtre todos EventId iguais a "xmnv", Message igual a "UserSessionId =\<WacSessionId\>WacSessionId" para a primeira WacSessionId na lista (substituindo a parte \<WacSessionId\> do filtro com sua WacSessionId)</span><span class="sxs-lookup"><span data-stu-id="d67d5-130">Filter for all EventId equals "xmnv", Message equals "UserSessionId=\<WacSessionId\>" for the first WacSessionId in the list (replacing the \<WacSessionId\> part of the filter with your WacSessionId)</span></span>

11. <span data-ttu-id="d67d5-131">Colete todos os valores de correlação que correspondam a essa WacSessionId</span><span class="sxs-lookup"><span data-stu-id="d67d5-131">Collect all values of Correlation that match that WacSessionId</span></span>

12. <span data-ttu-id="d67d5-132">Repita as etapas 10 e 11 para todos os valores de WacSessionId em sua lista de usuários em questão</span><span class="sxs-lookup"><span data-stu-id="d67d5-132">Repeat steps 10-11 for all values of WacSessionId in your list for the user in question</span></span>

13. <span data-ttu-id="d67d5-133">Filtrar para todos os valores de correlação iguais à primeira correlação da sua lista</span><span class="sxs-lookup"><span data-stu-id="d67d5-133">Filter for all Correlation equals the first Correlation in your list</span></span>

14. <span data-ttu-id="d67d5-134">Colete todos os logs correspondentes a essa correlação</span><span class="sxs-lookup"><span data-stu-id="d67d5-134">Collect all logs matching that Correlation</span></span>

15. <span data-ttu-id="d67d5-135">Repita as etapas 13 e 14 para todos os valores de correlação em sua lista de usuários em questão</span><span class="sxs-lookup"><span data-stu-id="d67d5-135">Repeat steps 13-14 for all values of Correlation in your list for the user in question</span></span>

## <a name="types-of-data"></a><span data-ttu-id="d67d5-136">Tipos de dados</span><span class="sxs-lookup"><span data-stu-id="d67d5-136">Types of Data</span></span>

<span data-ttu-id="d67d5-p105">Os logs do Office contêm diversos tipos de dados. A seguir são apresentados exemplos de dados que podem conter logs ULS:</span><span class="sxs-lookup"><span data-stu-id="d67d5-p105">Office logs contain a variety of different types of data. The following are examples of the data that ULS logs may contain:</span></span>

- <span data-ttu-id="d67d5-139">Códigos de erro para problemas encontrados durante o uso do produto</span><span class="sxs-lookup"><span data-stu-id="d67d5-139">Error codes for issues encountered during use of the product</span></span>

- <span data-ttu-id="d67d5-140">Cliques de botão e outros dados sobre o uso do aplicativo</span><span class="sxs-lookup"><span data-stu-id="d67d5-140">Button clicks and other pieces of data about app usage</span></span>

- <span data-ttu-id="d67d5-141">Dados de desempenho do aplicativo e/ou recursos específicos do aplicativo</span><span class="sxs-lookup"><span data-stu-id="d67d5-141">Performance data about the app and/or particular features within the app</span></span>

- <span data-ttu-id="d67d5-142">Informações gerais de localização sobre onde está o computador do usuário (por exemplo, país/região, estado e cidade, derivadas do endereço IP), mas não uma geolocalização precisa.</span><span class="sxs-lookup"><span data-stu-id="d67d5-142">General location information about where the user’s computer is (e.g. country / region, state, and city, derived from the IP address), but not precise geo location.</span></span>

- <span data-ttu-id="d67d5-143">Metadados básicos sobre o navegador, por exemplo, o nome e a versão do navegador e informações sobre o computador, como o tipo e a versão do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="d67d5-143">Basic metadata about the browser, e.g. browser name and version, and the computer, e.g. OS type and version</span></span>

- <span data-ttu-id="d67d5-144">Mensagens de erro do host do documento (por exemplo, OneDrive, SharePoint, Exchange)</span><span class="sxs-lookup"><span data-stu-id="d67d5-144">Error messages from the document host (e.g. OneDrive, SharePoint, Exchange)</span></span>

- <span data-ttu-id="d67d5-145">Informações sobre processos internos do aplicativo não relacionados a ações do usuário</span><span class="sxs-lookup"><span data-stu-id="d67d5-145">Information about processes internal to the app, unrelated to any action the user has taken</span></span>
