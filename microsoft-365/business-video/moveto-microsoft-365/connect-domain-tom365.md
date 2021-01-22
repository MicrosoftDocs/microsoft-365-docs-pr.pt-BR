---
title: Conectar seu domínio ao Microsoft 365
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como conectar seu domínio ao Microsoft 365.
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925105"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a><span data-ttu-id="b979b-103">Conectar seu domínio ao Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="b979b-103">Connect your domain to Microsoft 365 for business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

<span data-ttu-id="b979b-104">Depois de configurar o Microsoft 365 e mudar seus dados de email do Google Workspace, você poderá conectar seu domínio ao Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b979b-104">Once you’ve set up Microsoft 365 and moved your email data from Google Workspace, you can connect your domain to Microsoft 365.</span></span> 

<span data-ttu-id="b979b-105">Primeiro, você precisará excluir registros DNS existentes do Google e, em seguida, podemos adicionar novos registros DNS do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b979b-105">First you will need to delete existing DNS records from Google, then we can add new DNS records from Microsoft 365.</span></span>

## <a name="try-it"></a><span data-ttu-id="b979b-106">Experimente!</span><span class="sxs-lookup"><span data-stu-id="b979b-106">Try it!</span></span>

1. <span data-ttu-id="b979b-107">Entre no console de administração do Espaço de Trabalho do Google [admin.google.com.](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="b979b-107">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>
1. <span data-ttu-id="b979b-108">Select **Domains**, **Manage domains**, **View details**, Manage **domain**, then **DNS** in the left nav.</span><span class="sxs-lookup"><span data-stu-id="b979b-108">Select **Domains**, **Manage domains**, **View details**, **Manage domain**, then **DNS** in the left nav.</span></span>
1. <span data-ttu-id="b979b-109">Role para baixo **até registros sintéticos,** abra **Google Workspace**, selecione **Excluir** e **Excluir** novamente.</span><span class="sxs-lookup"><span data-stu-id="b979b-109">Scroll down to **Synthetic records**, open **Google Workspace**, select **Delete**, then **Delete** again.</span></span>
1. <span data-ttu-id="b979b-110">Role para baixo **até registros** de recursos personalizados e exclua quaisquer registros DNS existentes que apareçam, incluindo qualquer um que você possa ter criado anteriormente para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b979b-110">Scroll down to **Custom resource records** and delete any existing DNS records that appear, including any you may have created previously for Microsoft 365.</span></span>
1. <span data-ttu-id="b979b-111">Vá para o [Centro de administração do Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b979b-111">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="b979b-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span><span class="sxs-lookup"><span data-stu-id="b979b-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span></span>
1. <span data-ttu-id="b979b-113">Em seguida, escolha seu domínio padrão.</span><span class="sxs-lookup"><span data-stu-id="b979b-113">Then choose your default domain.</span></span>
1. <span data-ttu-id="b979b-114">Selecione **Continuar configuração,** em seguida, para conectar seu domínio, escolha  **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="b979b-114">Select **Continue setup**, then, to connect your domain, choose  **Continue**.</span></span>
1. <span data-ttu-id="b979b-115">Role para baixo para exibir os registros DNS que precisam ser copiados para o Google.</span><span class="sxs-lookup"><span data-stu-id="b979b-115">Scroll down to view the DNS records that need to be copied to Google.</span></span>
1. <span data-ttu-id="b979b-116">Abra **registros MX** e, em **Pontos de endereço ou valor,** copie o registro.</span><span class="sxs-lookup"><span data-stu-id="b979b-116">Open **MX Records**, and under **Points to address or value**, copy the record.</span></span>
1. <span data-ttu-id="b979b-117">Retorne ao Google e, na seção **Registros** de recursos personalizados, abra o menu suspenso de tipo de registro e selecione **MX**.</span><span class="sxs-lookup"><span data-stu-id="b979b-117">Return to Google, and in the **Custom resource records** section, open the record type dropdown and select **MX**.</span></span>
1. <span data-ttu-id="b979b-118">No campo **Dados,** copie o registro copiado.</span><span class="sxs-lookup"><span data-stu-id="b979b-118">In the **Data** field, paste the record you copied.</span></span>
1. <span data-ttu-id="b979b-119">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b979b-119">Then select **Add**.</span></span>
1. <span data-ttu-id="b979b-120">Repita o processo para registros CNAME e TXT e adicione os valores na página de gerenciamento de DNS do Google.</span><span class="sxs-lookup"><span data-stu-id="b979b-120">Repeat the process for CNAME and TXT records and add the values in the Google DNS management page.</span></span>
1. <span data-ttu-id="b979b-121">Retorne ao Centro de administração do Microsoft 365 e selecione **Continuar.**</span><span class="sxs-lookup"><span data-stu-id="b979b-121">Return to the Microsoft 365 Admin center and select **Continue**.</span></span>

    <span data-ttu-id="b979b-122">Sua configuração de domínio foi concluída.</span><span class="sxs-lookup"><span data-stu-id="b979b-122">Your domain setup is complete.</span></span>