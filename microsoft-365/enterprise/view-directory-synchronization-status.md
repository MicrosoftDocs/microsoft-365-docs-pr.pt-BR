---
title: Exibir o status de sincronização do diretório no Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: Neste artigo, saiba como você pode verificar o status da sua sincronização de diretórios no Office 365.
ms.openlocfilehash: c77898b58b58c6ae91492debd7ad66f395d80d52
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687260"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="9632c-103">Exibir o status de sincronização do diretório no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9632c-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="9632c-104">Se você integrou o Active Directory local ao Azure AD sincronizando seu ambiente local com o Microsoft 365, você também pode verificar o status da sua sincronização.</span><span class="sxs-lookup"><span data-stu-id="9632c-104">If you have integrated your on-premises Active Directory with Azure AD by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="9632c-105">Exibir o status da sincronização de diretórios</span><span class="sxs-lookup"><span data-stu-id="9632c-105">View directory synchronization status</span></span>

- <span data-ttu-id="9632c-106">Entre no centro de [Administração do Microsoft 365](https://admin.microsoft.com) e escolha **status DirSync** na página inicial.</span><span class="sxs-lookup"><span data-stu-id="9632c-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="9632c-107">Como alternativa, você pode ir para **Users** \> **usuários ativos**do usuário e, na página **usuários ativos** , escolha **mais** \> **sincronização de diretórios**.</span><span class="sxs-lookup"><span data-stu-id="9632c-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="9632c-108">No painel de **sincronização de diretórios** , escolha **ir para gerenciamento DirSync**.</span><span class="sxs-lookup"><span data-stu-id="9632c-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="9632c-109">Informações na página Gerenciar sincronização de diretório</span><span class="sxs-lookup"><span data-stu-id="9632c-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="9632c-110">A tabela a seguir lista os recursos para os quais você pode obter informações na página.</span><span class="sxs-lookup"><span data-stu-id="9632c-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="9632c-111">Se houver um problema com a sincronização de diretório, os erros também serão listados nessa página.</span><span class="sxs-lookup"><span data-stu-id="9632c-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="9632c-112">Para obter mais informações sobre diferentes erros que você pode encontrar, consulte [identificar erros de sincronização de diretório no Microsoft 365](identify-directory-synchronization-errors.md).</span><span class="sxs-lookup"><span data-stu-id="9632c-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="9632c-113">**Item**</span><span class="sxs-lookup"><span data-stu-id="9632c-113">**Item**</span></span>|<span data-ttu-id="9632c-114">**Para que serve**</span><span class="sxs-lookup"><span data-stu-id="9632c-114">**What it's for**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9632c-115">**Domínios verificados**</span><span class="sxs-lookup"><span data-stu-id="9632c-115">**Domains verified**</span></span> | <span data-ttu-id="9632c-116">Número de domínios em seu locatário do Microsoft 365 que você verificou você possui.</span><span class="sxs-lookup"><span data-stu-id="9632c-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="9632c-117">**Domínios não verificados**</span><span class="sxs-lookup"><span data-stu-id="9632c-117">**Domains not verified**</span></span> | <span data-ttu-id="9632c-118">Domínios que você adicionou, mas não verificados.</span><span class="sxs-lookup"><span data-stu-id="9632c-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="9632c-119">**Sincronização de diretório habilitada**</span><span class="sxs-lookup"><span data-stu-id="9632c-119">**Directory sync enabled**</span></span> |<span data-ttu-id="9632c-120">True ou false.</span><span class="sxs-lookup"><span data-stu-id="9632c-120">True or False.</span></span> <span data-ttu-id="9632c-121">Especifica se você habilitou a sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="9632c-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="9632c-122">**Sincronização de diretório mais recente**</span><span class="sxs-lookup"><span data-stu-id="9632c-122">**Latest directory sync**</span></span> | <span data-ttu-id="9632c-123">Última vez em que a sincronização de diretório foi executada.</span><span class="sxs-lookup"><span data-stu-id="9632c-123">Last time directory sync ran.</span></span> <span data-ttu-id="9632c-124">Exibirá um aviso e um link para uma ferramenta de solução de problemas se a última sincronização tiver mais de três dias.</span><span class="sxs-lookup"><span data-stu-id="9632c-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="9632c-125">**Sincronização de senha habilitada**</span><span class="sxs-lookup"><span data-stu-id="9632c-125">**Password sync enabled**</span></span> | <span data-ttu-id="9632c-126">True ou false.</span><span class="sxs-lookup"><span data-stu-id="9632c-126">True or False.</span></span> <span data-ttu-id="9632c-127">Especifica se a sincronização de hash de senha deve ser sincronizada entre o seu locatário do Microsoft 365 e no local.</span><span class="sxs-lookup"><span data-stu-id="9632c-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="9632c-128">**Última sincronização de senha**</span><span class="sxs-lookup"><span data-stu-id="9632c-128">**Last Password Sync**</span></span> | <span data-ttu-id="9632c-129">Última vez em que a sincronização de hash de senha foi executada.</span><span class="sxs-lookup"><span data-stu-id="9632c-129">Last time password hash sync ran.</span></span> <span data-ttu-id="9632c-130">Exibirá um aviso e um link para uma ferramenta de solução de problemas se a última sincronização tiver mais de três dias.</span><span class="sxs-lookup"><span data-stu-id="9632c-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="9632c-131">**Versão do cliente de sincronização de diretório**</span><span class="sxs-lookup"><span data-stu-id="9632c-131">**Directory sync client version**</span></span> | <span data-ttu-id="9632c-132">Contém um link de download se uma nova versão do Azure AD Connect foi liberada.</span><span class="sxs-lookup"><span data-stu-id="9632c-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="9632c-133">**Conta de serviço de sincronização de diretório**</span><span class="sxs-lookup"><span data-stu-id="9632c-133">**Directory sync service account**</span></span> | <span data-ttu-id="9632c-134">Exibe o nome da sua conta de serviço de sincronização de diretório do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9632c-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |