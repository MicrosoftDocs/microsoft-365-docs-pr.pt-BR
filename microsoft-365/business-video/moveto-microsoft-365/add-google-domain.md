---
title: Adicionar seu domínio do Espaço de Trabalho do Google
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Saiba como mover seu domínio do Google Workspace para o Microsoft 365 para empresas.
ms.openlocfilehash: 23ca451cfdcb67898a10935101efedcdf360ef91
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49924997"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="ffd12-103">Adicionar seu domínio do Espaço de Trabalho do Google ao Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ffd12-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="ffd12-104">Adicione seu domínio do Espaço de Trabalho do Google ao Microsoft 365 para empresas para que você possa continuar usando seu endereço de email comercial.</span><span class="sxs-lookup"><span data-stu-id="ffd12-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="ffd12-105">Experimente!</span><span class="sxs-lookup"><span data-stu-id="ffd12-105">Try it!</span></span>

1. <span data-ttu-id="ffd12-106">Vá para o [Centro de administração do Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ffd12-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="ffd12-107">No Centro de Administração do Microsoft 365, no painel de administração esquerdo, selecione **Mostrar tudo** **,** Configurações e **domínios.**</span><span class="sxs-lookup"><span data-stu-id="ffd12-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="ffd12-108">Choose **Add domain**, enter your domain name then select Use this **domain**.</span><span class="sxs-lookup"><span data-stu-id="ffd12-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="ffd12-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span><span class="sxs-lookup"><span data-stu-id="ffd12-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="ffd12-110">Volte para o [Google Admin Console](https://admin.google.com), escolha **Domínios**, **Gerenciar domínios** **,** Exibir Detalhes **,** Gerenciar domínio , **DNS** e role para baixo até Registros de **recurso personalizados**.</span><span class="sxs-lookup"><span data-stu-id="ffd12-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="ffd12-111">Abra o drop-down de tipo de registro, escolha **TXT**, colar o valor TXT que você copiou e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ffd12-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="ffd12-112">A atualização geralmente leva um fato dentro de alguns minutos, mas pode levar até 48 horas.</span><span class="sxs-lookup"><span data-stu-id="ffd12-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="ffd12-113">Retorne ao Centro de Administração do Microsoft 365, selecione **Verificar** e **Feche.**</span><span class="sxs-lookup"><span data-stu-id="ffd12-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="ffd12-114">Para definir seu domínio como o email principal para seus usuários, na nav esquerda, selecione **Usuários**  >  **ativos.**</span><span class="sxs-lookup"><span data-stu-id="ffd12-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="ffd12-115">Escolha um usuário, selecione Gerenciar nome de usuário e **email,** **Editar**, selecione seu domínio na lista suspenso e selecione **Alterações** Feitas **e Salvar.**</span><span class="sxs-lookup"><span data-stu-id="ffd12-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="ffd12-116">Repita esse processo para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="ffd12-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="ffd12-117">Quando terminar, você estará pronto para instalar os aplicativos do Office e migrar seus itens de email e calendário para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ffd12-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 