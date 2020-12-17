---
title: Gerenciar as políticas de dispositivos do Windows 10 pro com o Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como gerenciar as políticas de dispositivos do Windows 10 pro com o Microsoft 365 Business Premium.
ms.openlocfilehash: 9052859f03035a76bf69b7c8c23c75ae00353846
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701654"
---
# <a name="manage-windows-10-pro-device-policies"></a><span data-ttu-id="a0e9f-103">Gerenciar políticas de dispositivos do Windows 10 pro</span><span class="sxs-lookup"><span data-stu-id="a0e9f-103">Manage Windows 10 Pro device policies</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

<span data-ttu-id="a0e9f-104">Você pode usar o Microsoft 365 Business para garantir que o Windows Defender Antivirus seja ativado em dispositivos Windows 10 e as atualizações da Microsoft são baixadas automaticamente para os dispositivos dos usuários.</span><span class="sxs-lookup"><span data-stu-id="a0e9f-104">You can use Microsoft 365 Business to ensure that Windows Defender Antivirus is activated on Windows 10 devices and Microsoft updates are automatically downloaded to users' devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="a0e9f-105">Experimente!</span><span class="sxs-lookup"><span data-stu-id="a0e9f-105">Try it!</span></span>

1. <span data-ttu-id="a0e9f-106">Acesse o centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a0e9f-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="a0e9f-107">Em **políticas**, escolha Adicionar política.</span><span class="sxs-lookup"><span data-stu-id="a0e9f-107">Under **Policies**, choose Add policy.</span></span>
1. <span data-ttu-id="a0e9f-108">No painel **Adicionar política** , digite um nome em **nome da política** e selecione configuração de **dispositivo do Windows 10** em **tipo de política**.</span><span class="sxs-lookup"><span data-stu-id="a0e9f-108">In the **Add policy** pane, enter a name under **Policy name**, and then select **Windows 10 Device Configuration** under **Policy type**.</span></span>
1. <span data-ttu-id="a0e9f-109">Escolha **proteger dispositivos Windows 10** para ver as subconfiguraçãos.</span><span class="sxs-lookup"><span data-stu-id="a0e9f-109">Choose **Secure Windows 10 devices** to see the sub-settings.</span></span>
1. <span data-ttu-id="a0e9f-110">Certifique-se de **ajudar a proteger os computadores contra vírus e outras ameaças usando o Windows Defender Antivirus** e **manter os dispositivos Windows 10 atualizados automaticamente** .</span><span class="sxs-lookup"><span data-stu-id="a0e9f-110">Make sure that **Help protect PCs from viruses and other threats using Windows Defender Antivirus** and **Keep Windows 10 devices up to date automatically** are turned on.</span></span>
1. <span data-ttu-id="a0e9f-111">Em **quem receberá essas configurações?**, todos os usuários são selecionados por padrão, mas você pode escolher **alterar** para selecionar qualquer grupo de segurança que você tenha criado.</span><span class="sxs-lookup"><span data-stu-id="a0e9f-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="a0e9f-112">Para concluir a criação da política, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a0e9f-112">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="a0e9f-113">Na página **Adicionar política** , escolha **fechar**.</span><span class="sxs-lookup"><span data-stu-id="a0e9f-113">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="a0e9f-114">Na home page do centro de administração, confirme se a nova política foi adicionada escolhendo **políticas** e revisando sua política na página **políticas** .</span><span class="sxs-lookup"><span data-stu-id="a0e9f-114">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>
1. <span data-ttu-id="a0e9f-115">Para verificar se a política levou em vigor, no dispositivo Windows 10 de um usuário, vá para Windows Update, escolha **Opções avançadas** e confirme se as configurações estão acinzentadas.</span><span class="sxs-lookup"><span data-stu-id="a0e9f-115">To verify that the policy has taken effect, on a user's Windows 10 device, go to Windows Update, choose **Advanced options**, and confirm that settings are grayed out.</span></span>

    <span data-ttu-id="a0e9f-116">Em seguida, clique em **escolher como as atualizações são entregues** e confirme se as configurações estão esmaecidas e se a seguinte mensagem aparece: **algumas configurações são ocultas ou gerenciadas pela sua organização**.</span><span class="sxs-lookup"><span data-stu-id="a0e9f-116">Then, click **Choose how updates are delivered**, and confirm that settings are grayed out and the following message appears: **Some settings are hidden or managed by your organization**.</span></span>

