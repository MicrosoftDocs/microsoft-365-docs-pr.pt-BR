---
title: Definir idioma e fuso horário em Microsoft bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 94af3e22-aca6-4e91-8b91-1cd5a02a9ea8
description: Alterar suas configurações de idioma e fuso horário em Microsoft bookings. Se as reservas forem criadas na hora errada, as reservas poderão ser definidas para o fuso horário errado.
ms.openlocfilehash: 07e5dde2a896610ee079063943aff24ec69ba721
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419180"
---
# <a name="set-language-and-time-zones-in-microsoft-bookings"></a><span data-ttu-id="3d8d5-104">Definir idioma e fuso horário em Microsoft bookings</span><span class="sxs-lookup"><span data-stu-id="3d8d5-104">Set language and time zones in Microsoft Bookings</span></span>

<span data-ttu-id="3d8d5-105">Se você estiver usando o Microsoft bookings e as reservas são criados no momento errado, as configurações de fuso horário podem precisar ser alteradas.</span><span class="sxs-lookup"><span data-stu-id="3d8d5-105">If you are using Microsoft Bookings and bookings are created at the wrong time, then your time zone settings might need to be changed.</span></span> <span data-ttu-id="3d8d5-106">Da mesma forma, se algumas reservas estiverem no idioma errado, talvez seja necessário alterar as configurações de idioma.</span><span class="sxs-lookup"><span data-stu-id="3d8d5-106">Likewise, if some bookings are in the wrong language, you might need to change your language settings.</span></span>

<span data-ttu-id="3d8d5-107">Há duas configurações de idioma e fuso horário separados para reservas.</span><span class="sxs-lookup"><span data-stu-id="3d8d5-107">There are two separate language and time zone settings for Bookings.</span></span> <span data-ttu-id="3d8d5-108">A primeira configuração controla o idioma e o fuso horário do calendário de reserva e é definida usando as configurações do Outlook na Web para o calendário pessoal do usuário conectado.</span><span class="sxs-lookup"><span data-stu-id="3d8d5-108">The first setting controls the language and time zone of the booking calendar and is set using the Outlook on the web settings for the personal calendar of the logged-in user.</span></span> <span data-ttu-id="3d8d5-109">A segunda configuração afeta a página de reserva de autoatendimento usada pelos seus clientes e é definida usando uma página "configurações regionais" que controla o idioma e o fuso horário somente para essa página.</span><span class="sxs-lookup"><span data-stu-id="3d8d5-109">The second setting affects the self-service booking page that your customers use and is set using a "regional settings" page that controls language and time zone only for that page.</span></span>

> [!NOTE]
> <span data-ttu-id="3d8d5-110">As reservas são ativadas por padrão para clientes que têm as assinaturas do Microsoft 365 Business Standard, da Microsoft 365 a3 ou do Microsoft 365 a5.</span><span class="sxs-lookup"><span data-stu-id="3d8d5-110">Bookings is turned on by default for customers who have the Microsoft 365 Business Standard, Microsoft 365 A3, or Microsoft 365 A5 subscriptions.</span></span> <span data-ttu-id="3d8d5-111">As reservas também estão disponíveis para clientes que têm o Office 365 Enterprise E3 e o Office 365 Enterprise e5, mas estão desativados por padrão.</span><span class="sxs-lookup"><span data-stu-id="3d8d5-111">Bookings is also available to customers who have Office 365 Enterprise E3 and Office 365 Enterprise E5, but it is turned off by default.</span></span> <span data-ttu-id="3d8d5-112">Para começar, confira [obter acesso aos Microsoft bookings](get-access.md).</span><span class="sxs-lookup"><span data-stu-id="3d8d5-112">To get started, see [Get access to Microsoft Bookings](get-access.md).</span></span> <span data-ttu-id="3d8d5-113">Para ativar ou desativar reservas, consulte [Ativar ou desativar reservas para sua organização](turn-bookings-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="3d8d5-113">To turn Bookings on or off, see [Turn Bookings on or off for your organization](turn-bookings-on-or-off.md).</span></span>

## <a name="setting-language-and-time-zone-for-a-booking-calendar"></a><span data-ttu-id="3d8d5-114">Definindo o idioma e o fuso horário de um calendário de reserva</span><span class="sxs-lookup"><span data-stu-id="3d8d5-114">Setting language and time zone for a booking calendar</span></span>

<span data-ttu-id="3d8d5-115">O calendário de reserva usa as configurações de idioma e fuso horário do usuário conectado.</span><span class="sxs-lookup"><span data-stu-id="3d8d5-115">The booking calendar uses the logged-in user’s language and time zone settings.</span></span> <span data-ttu-id="3d8d5-116">Por exemplo, se o fuso horário do usuário conectado estiver definido como hora padrão do leste (EST), o calendário de reserva mostrará as horas de início e término do compromisso existente na EST.</span><span class="sxs-lookup"><span data-stu-id="3d8d5-116">For example, If the logged-in user’s time zone is set to Eastern Standard Time (EST), then the booking calendar will show existing appointment start and end times in EST.</span></span> <span data-ttu-id="3d8d5-117">Este fuso horário foi originalmente definido quando as contas do usuário da Web do Microsoft 365 e do Outlook foram criadas.</span><span class="sxs-lookup"><span data-stu-id="3d8d5-117">This time zone was originally set when the user’s Microsoft 365 and Outlook on the web accounts were created.</span></span>

<span data-ttu-id="3d8d5-118">Para definir o idioma e o fuso horário do calendário de reserva:</span><span class="sxs-lookup"><span data-stu-id="3d8d5-118">To set the language and time zone for the booking calendar:</span></span>

1. <span data-ttu-id="3d8d5-119">Faça logon no Microsoft 365 e selecione o bloco do Outlook na página de aterrissagem (conforme mostrado na captura de tela abaixo) ou no inicializador de aplicativos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d8d5-119">Log into Microsoft 365 and select the Outlook tile on the landing page (as shown in the screenshot below) or in the Microsoft 365 App Launcher.</span></span>

   ![Imagem do bloco do Outlook na página de aterrissagem do Microsoft 365](../media/bookings-outlook-tile.png)

1. <span data-ttu-id="3d8d5-121">Após a abertura do Outlook, selecione o **ícone de engrenagem** no canto superior direito da tela para abrir suas configurações pessoais e de conta e procure "fuso horário" na caixa de pesquisa painel de **configurações** .</span><span class="sxs-lookup"><span data-stu-id="3d8d5-121">After Outlook opens, select the **gear icon** in the upper, right-hand corner of the screen to open your personal and account settings, then search for “time zone” in the **Settings** panel search box.</span></span> <span data-ttu-id="3d8d5-122">O painel será atualizado para mostrar suas configurações de idioma pessoal e fuso horário atuais para esta conta.</span><span class="sxs-lookup"><span data-stu-id="3d8d5-122">The panel will update to show your current personal language and time zone settings for this account.</span></span> <span data-ttu-id="3d8d5-123">Conforme observado acima, essa configuração também controla o idioma e o fuso horário do calendário de reserva.</span><span class="sxs-lookup"><span data-stu-id="3d8d5-123">As noted above, this setting also controls the language and time zone of the booking calendar.</span></span>

1. <span data-ttu-id="3d8d5-124">Altere o idioma ou o fuso horário selecionando a seta suspensa na caixa **idioma ou fuso horário atual** e escolhendo a configuração desejada.</span><span class="sxs-lookup"><span data-stu-id="3d8d5-124">Change the language or time zone by selecting the drop-down arrow in the **Language or Current time zone** box and choosing the desired setting.</span></span>

1. <span data-ttu-id="3d8d5-125">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3d8d5-125">Click **Save**.</span></span> <span data-ttu-id="3d8d5-126">O painel configurações é fechado, o Outlook na Web é reiniciado e as novas configurações de idioma e fuso horário são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="3d8d5-126">The Settings panel closes, Outlook on the web restarts, and the new language and time zone settings are applied.</span></span>

## <a name="setting-the-language-and-time-zone-for-the-booking-page"></a><span data-ttu-id="3d8d5-127">Configurando o idioma e o fuso horário da página de reserva</span><span class="sxs-lookup"><span data-stu-id="3d8d5-127">Setting the language and time zone for the booking page</span></span>

1. <span data-ttu-id="3d8d5-128">No Microsoft 365, selecione o inicializador de aplicativos e, em seguida, selecione **reservas**.</span><span class="sxs-lookup"><span data-stu-id="3d8d5-128">In Microsoft 365, select the app launcher, and then select **Bookings**.</span></span>

1. <span data-ttu-id="3d8d5-129">No painel de navegação, selecione **página de reserva** e selecione **alterar as configurações de idioma e fuso horário**.</span><span class="sxs-lookup"><span data-stu-id="3d8d5-129">In the navigation pane, select **Booking page** and select **Change language and time zone settings**.</span></span>

   ![Captura de tela: link de configurações de idioma e fuso horário](../media/bookings-region-language-timezone-settings.png)

1. <span data-ttu-id="3d8d5-131">Selecione seu idioma e fuso horário atual e escolha OK.</span><span class="sxs-lookup"><span data-stu-id="3d8d5-131">Select your language and current time zone and choose OK.</span></span>

   ![Captura de tela: configurações de idioma e fuso horário](../media/bookings-region-timezone-settings.png)
