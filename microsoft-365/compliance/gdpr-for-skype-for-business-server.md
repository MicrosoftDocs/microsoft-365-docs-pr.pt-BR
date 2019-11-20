---
title: RGPD para Skype for Business Server
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: Saiba mais sobre como atender aos requisitos de RGPD no Skype for Business Server e no Lync Server.
ms.openlocfilehash: fb3789a6835a367d415e5c32eeec043add150724
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "38749591"
---
# <a name="gdpr-for-skype-for-business-server-and-lync-server"></a><span data-ttu-id="be959-103">RGPD para Skype for Business Server e Lync Server</span><span class="sxs-lookup"><span data-stu-id="be959-103">GDPR for Skype for Business Server and Lync Server</span></span>

<span data-ttu-id="be959-p101">A maioria dos dados do Skype for Business Server e do Lync Server é armazenada no Exchange Server. Isso inclui:</span><span class="sxs-lookup"><span data-stu-id="be959-p101">Most Skype for Business Server and Lync Server data is stored in Exchange Server. This includes:</span></span>

-   <span data-ttu-id="be959-106">Histórico de conversas</span><span class="sxs-lookup"><span data-stu-id="be959-106">Conversation history</span></span>

-   <span data-ttu-id="be959-107">Transcrições e notificações da caixa postal</span><span class="sxs-lookup"><span data-stu-id="be959-107">Voicemail notifications and transcriptions</span></span>

-   <span data-ttu-id="be959-108">Convites de reuniões</span><span class="sxs-lookup"><span data-stu-id="be959-108">Meeting invites</span></span>

<span data-ttu-id="be959-109">Use os procedimentos descritos para [RGPD para Exchange Server](gdpr-for-exchange-server.md) para localizar, exportar ou excluir esses tipos de dados para solicitações de RGPD.</span><span class="sxs-lookup"><span data-stu-id="be959-109">Use the procedures outlined for [GDPR for Exchange Server](gdpr-for-exchange-server.md) to find, export, or delete these types of data for GDPR requests.</span></span>

<span data-ttu-id="be959-p102">Listas de contatos são armazenadas no banco de dados do SQL Server. Elas podem ser exportadas das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="be959-p102">Contact lists are stored in the SQL Server database. They can be exported in the following ways:</span></span>

-   <span data-ttu-id="be959-p103">Os usuários finais podem exportar os contatos por conta própria clicando no cabeçalho do grupo com o botão direito do mouse e selecionando Copiar. Isso copiará os contatos para a área de transferência, e eles poderão ser colados em qualquer aplicativo.</span><span class="sxs-lookup"><span data-stu-id="be959-p103">End users themselves can export the contacts by right clicking the group header and selecting Copy. This will copy all the contacts in that group into the clipboard, which can then be pasted into any app.</span></span>

-   <span data-ttu-id="be959-114">Você pode usar o cmdlet [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) para exportar esses dados.</span><span class="sxs-lookup"><span data-stu-id="be959-114">You can use the [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) cmdlet to export this data.</span></span>

<span data-ttu-id="be959-p104">Conteúdo carregado em reuniões (como arquivos do PowerPoint ou folhetos) ou conteúdo gerado em uma reunião (como quadro de comunicações, votações ou sessões de perguntas e respostas) armazenado no servidor de dados. Também é possível exportar esse conteúdo se os usuários finais entrarem novamente em qualquer reunião que não tenha expirado e baixarem o conteúdo carregado ou fizerem capturas de tela no caso do conteúdo gerado.</span><span class="sxs-lookup"><span data-stu-id="be959-p104">Content uploaded into meetings (such as PowerPoint files or handouts) or content generated in a meeting (such as whiteboard, polls, or Q/A) is stored in the filer. This can also be exported if end users log back into any meeting that has not expired and download any uploaded content or take screenshots in the case of generated content.</span></span>

<span data-ttu-id="be959-p105">Reuniões do MeetNow que não estão no Calendário do Exchange e na Lista de Contatos e os direitos de contado (familiares, colegas de trabalho etc.) se encontram no banco de dados do usuário. No Lync Server 2013 e em versões posteriores, você poderá usar o cmdlet [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) para exportar esses dados.</span><span class="sxs-lookup"><span data-stu-id="be959-p105">MeetNow meetings that are not in the Exchange Calendar and Contact List and contact rights (family, co-worker, etc.) are in the User Database. In Lync Server 2013 and later, you can use the [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) cmdlet to export this data.</span></span>
