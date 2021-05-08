---
title: Etapa 5 - Apagar e bloquear o dispositivo móvel de um ex-funcionário
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Siga estas etapas para bloquear o acesso ao dispositivo móvel de um ex-funcionário.
ms.openlocfilehash: 1ce12b06b6a0a74615ff8ac43b8f333456a469bb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244154"
---
# <a name="step-5---wipe-and-block-a-former-employees-mobile-device"></a><span data-ttu-id="12eb2-103">Etapa 5 - Apagar e bloquear o dispositivo móvel de um ex-funcionário</span><span class="sxs-lookup"><span data-stu-id="12eb2-103">Step 5 - Wipe and block a former employee's mobile device</span></span>

<span data-ttu-id="12eb2-104">Se seu ex-funcionário tinha um telefone de organização, você pode usar o centro de administração do Exchange para apagar e bloquear esse dispositivo para que todos os dados da organização seja removidos do dispositivo e ele não possa mais se conectar ao Office 365.</span><span class="sxs-lookup"><span data-stu-id="12eb2-104">If your former employee had an organization phone, you can use the Exchange admin center to wipe and block that device so that all organization data is removed from the device and it can no longer connect to Office 365.</span></span> <span data-ttu-id="12eb2-105">Se a sua organização usar a Mobilidade Básica e a Segurança para gerenciar dispositivos móveis, você poderá apagar e bloquear esses dispositivos usando a Mobilidade Básica e a Segurança.</span><span class="sxs-lookup"><span data-stu-id="12eb2-105">If your organization uses Basic Mobility and Security to manage mobile devices, you can wipe and block those devices using Basic Mobility and Security.</span></span>

## <a name="wipe-mobile-device-using-the-exchange-admin-center"></a><span data-ttu-id="12eb2-106">Apagar dispositivo móvel usando o Exchange de administração</span><span class="sxs-lookup"><span data-stu-id="12eb2-106">Wipe mobile device using the Exchange admin center</span></span>

1. <span data-ttu-id="12eb2-107">Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="12eb2-107">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="12eb2-108">No Centro de administração do Exchange, navegue até **Destinatários** \> **Caixas de Correio**.</span><span class="sxs-lookup"><span data-stu-id="12eb2-108">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="12eb2-109">Selecione o usuário e, em **Dispositivos Móveis,** selecione **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="12eb2-109">Select the user, and under **Mobile Devices**, select **View details**.</span></span>
4. <span data-ttu-id="12eb2-110">Na página **Detalhes do Dispositivo** Móvel, em **Dispositivos** Móveis, selecione o dispositivo móvel, selecione **Apagar Dispositivo** de Apagar Dados e selecione ![ ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="12eb2-110">On the **Mobile Device Details** page, under **Mobile devices**, select the mobile device, select **Wipe Data**![Wipe Device](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png), and then select **Block**.</span></span>
5. <span data-ttu-id="12eb2-111">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="12eb2-111">Select **Save**.</span></span>
   > [!TIP]
   > <span data-ttu-id="12eb2-112">Certifique-se de remover ou desabilitar o usuário do serviço de Enterprise Blackberry local.</span><span class="sxs-lookup"><span data-stu-id="12eb2-112">Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service.</span></span> <span data-ttu-id="12eb2-113">Você também deve desabilitar todos os dispositivos Blackberry desse usuário.</span><span class="sxs-lookup"><span data-stu-id="12eb2-113">You should also disable any Blackberry devices for the user.</span></span> <span data-ttu-id="12eb2-114">Veja o Guia de Administração do Blackberry Business Cloud Services se precisar de etapas específicas para desabilitar o usuário.</span><span class="sxs-lookup"><span data-stu-id="12eb2-114">Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user.</span></span>
