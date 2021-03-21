---
title: Exibir o status de sincronização de diretórios no Microsoft 365
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
description: Neste artigo, saiba como verificar o status da sincronização de diretórios no Office 365.
ms.openlocfilehash: cbaae8bbd31f6124c2b0f4984b9a625ffbde538f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924655"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="cf297-103">Exibir o status de sincronização de diretórios no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf297-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="cf297-104">Se você tiver integrado seus Serviços de Domínio do Active Directory (AD DS) local com o Azure Active Directory (Azure AD) sincronizando seu ambiente local com o Microsoft 365, você também poderá verificar o status da sincronização.</span><span class="sxs-lookup"><span data-stu-id="cf297-104">If you have integrated your on-premises Active Directory Domain Services (AD DS) with Azure Active Directory (Azure AD) by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="cf297-105">Visualizar o status de sincronização de diretório</span><span class="sxs-lookup"><span data-stu-id="cf297-105">View directory synchronization status</span></span>

- <span data-ttu-id="cf297-106">Entre no Centro de administração do [Microsoft 365](https://admin.microsoft.com) e escolha **Status dirSync** na home page.</span><span class="sxs-lookup"><span data-stu-id="cf297-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="cf297-107">Como alternativa, você pode ir para **Usuários** Usuários ativos e, na página Usuários ativos, \> escolha **Mais**  \> **Sincronização de Diretório.**</span><span class="sxs-lookup"><span data-stu-id="cf297-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="cf297-108">No painel **Sincronização de** Diretórios, escolha **Ir para Gerenciamento dirSync**.</span><span class="sxs-lookup"><span data-stu-id="cf297-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="cf297-109">Informações na página Gerenciar sincronização de diretórios</span><span class="sxs-lookup"><span data-stu-id="cf297-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="cf297-110">A tabela a seguir lista os recursos sobre os que você pode obter informações sobre na página.</span><span class="sxs-lookup"><span data-stu-id="cf297-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="cf297-111">Se houver um problema com a sincronização de diretórios, os erros também serão listados nesta página.</span><span class="sxs-lookup"><span data-stu-id="cf297-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="cf297-112">Para obter mais informações sobre diferentes erros que você pode encontrar, consulte Identificar erros de sincronização de diretório [no Microsoft 365](identify-directory-synchronization-errors.md).</span><span class="sxs-lookup"><span data-stu-id="cf297-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="cf297-113">Item</span><span class="sxs-lookup"><span data-stu-id="cf297-113">Item</span></span>|<span data-ttu-id="cf297-114">Para que serve</span><span class="sxs-lookup"><span data-stu-id="cf297-114">What it's for</span></span>|
|:-----|:-----|
|<span data-ttu-id="cf297-115">**Domínios verificados**</span><span class="sxs-lookup"><span data-stu-id="cf297-115">**Domains verified**</span></span> | <span data-ttu-id="cf297-116">Número de domínios em seu locatário do Microsoft 365 que você verificou que possui.</span><span class="sxs-lookup"><span data-stu-id="cf297-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="cf297-117">**Domínios não verificados**</span><span class="sxs-lookup"><span data-stu-id="cf297-117">**Domains not verified**</span></span> | <span data-ttu-id="cf297-118">Domínios adicionados, mas não verificados.</span><span class="sxs-lookup"><span data-stu-id="cf297-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="cf297-119">**Sincronização de diretório habilitada**</span><span class="sxs-lookup"><span data-stu-id="cf297-119">**Directory sync enabled**</span></span> |<span data-ttu-id="cf297-120">Verdadeiro ou Falso.</span><span class="sxs-lookup"><span data-stu-id="cf297-120">True or False.</span></span> <span data-ttu-id="cf297-121">Especifica se você habilitar a sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="cf297-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="cf297-122">**Sincronização de diretório mais recente**</span><span class="sxs-lookup"><span data-stu-id="cf297-122">**Latest directory sync**</span></span> | <span data-ttu-id="cf297-123">Última vez em que a sincronização de diretórios foi.</span><span class="sxs-lookup"><span data-stu-id="cf297-123">Last time directory sync ran.</span></span> <span data-ttu-id="cf297-124">Exibirá um aviso e um link para uma ferramenta de solução de problemas se a última sincronização foi há mais de três dias.</span><span class="sxs-lookup"><span data-stu-id="cf297-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="cf297-125">**Sincronização de senha habilitada**</span><span class="sxs-lookup"><span data-stu-id="cf297-125">**Password sync enabled**</span></span> | <span data-ttu-id="cf297-126">Verdadeiro ou Falso.</span><span class="sxs-lookup"><span data-stu-id="cf297-126">True or False.</span></span> <span data-ttu-id="cf297-127">Especifica se você tem uma sincronização de hash de senha entre nosso locatário local e seu locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf297-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="cf297-128">**Última Sincronização de Senha**</span><span class="sxs-lookup"><span data-stu-id="cf297-128">**Last Password Sync**</span></span> | <span data-ttu-id="cf297-129">Última vez em que a sincronização de hash de senha foi acoplda.</span><span class="sxs-lookup"><span data-stu-id="cf297-129">Last time password hash sync ran.</span></span> <span data-ttu-id="cf297-130">Exibirá um aviso e um link para uma ferramenta de solução de problemas se a última sincronização foi há mais de três dias.</span><span class="sxs-lookup"><span data-stu-id="cf297-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="cf297-131">**Versão do cliente de sincronização de diretório**</span><span class="sxs-lookup"><span data-stu-id="cf297-131">**Directory sync client version**</span></span> | <span data-ttu-id="cf297-132">Contém um link de download se uma nova versão do Azure AD Connect tiver sido lançada.</span><span class="sxs-lookup"><span data-stu-id="cf297-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="cf297-133">**Conta do serviço de sincronização de diretório**</span><span class="sxs-lookup"><span data-stu-id="cf297-133">**Directory sync service account**</span></span> | <span data-ttu-id="cf297-134">Exibe o nome da sua conta de serviço de sincronização de diretório do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf297-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |
|||

## <a name="monitor-synchronization-health"></a><span data-ttu-id="cf297-135">Monitorar a integridade da sincronização</span><span class="sxs-lookup"><span data-stu-id="cf297-135">Monitor synchronization health</span></span>

<span data-ttu-id="cf297-136">Nesta seção, você instalará um agente do Azure AD Connect Health em cada um dos seus controladores de domínio AD DS locais para monitorar sua infraestrutura de identidade e os serviços de sincronização fornecidos pelo Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="cf297-136">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="cf297-137">As informações de monitoramento são disponibilizadas em um portal do Azure AD Connect Health, onde você pode ver alertas, monitoramento de desempenho, análise de uso e outras informações.</span><span class="sxs-lookup"><span data-stu-id="cf297-137">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

<span data-ttu-id="cf297-138">A decisão da estrutura principal de como usar o Azure AD Connect Health baseia-se em como o Azure AD Connect está sendo usado:</span><span class="sxs-lookup"><span data-stu-id="cf297-138">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="cf297-139">Se você estiver usando a opção de **autenticação gerenciada**, comece [usando o Azure AD Connect Health com a sincronização](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) para entender e configurar o Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="cf297-139">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="cf297-140">Se você estiver sincronizando apenas os nomes das contas e dos grupos usando a **autenticação federada** com os Serviços de Federação do Active Directory (AD FS), comece [usando o Azure AD Connect Health com os AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) para entender e configurar o Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="cf297-140">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="cf297-141">Quando estiver concluído, você terá:</span><span class="sxs-lookup"><span data-stu-id="cf297-141">When complete, you’ll have:</span></span>

- <span data-ttu-id="cf297-142">Terá instalado o agente do Azure AD Connect Health nos servidores do provedor de identidade local.</span><span class="sxs-lookup"><span data-stu-id="cf297-142">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="cf297-143">Poderá ver, no portal do Azure AD Connect Health, o estado atual de sua infraestrutura local e das atividades de sincronização com o locatário do Azure AD para suas assinaturas do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf297-143">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>