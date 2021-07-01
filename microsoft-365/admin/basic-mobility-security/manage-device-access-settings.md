---
title: Gerenciar configurações de acesso a dispositivos em Mobilidade Básica e Segurança
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: A Mobilidade Básica e a Segurança podem ajudá-lo a proteger e gerenciar dispositivos móveis.
ms.openlocfilehash: 24eeb1dfccef3d30e577b15ecb9d2fda4d902cdc
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228154"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="60212-103">Gerenciar configurações de acesso a dispositivos em Mobilidade Básica e Segurança</span><span class="sxs-lookup"><span data-stu-id="60212-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="60212-104">Se você estiver usando o Basic Mobility and Security, pode haver dispositivos que você não pode gerenciar com o Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="60212-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="60212-105">Nesse caso, você deve bloquear o Exchange ActiveSync de aplicativos Microsoft 365 email para dispositivos móveis que não têm suporte da Mobilidade Básica e Segurança.</span><span class="sxs-lookup"><span data-stu-id="60212-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="60212-106">Isso ajuda a proteger as informações da sua organização em mais dispositivos.</span><span class="sxs-lookup"><span data-stu-id="60212-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="60212-107">Use estas etapas:</span><span class="sxs-lookup"><span data-stu-id="60212-107">Use these steps:</span></span>

1. <span data-ttu-id="60212-108">Entre no Microsoft 365 com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="60212-108">Sign in to  Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="60212-109">No navegador, digite:  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="60212-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="60212-110">Se essa for a primeira vez que você estiver usando o Basic Mobility and Security para Microsoft 365 Business Standard, ative-o aqui: Ativar Segurança Básica [e Mobilidade](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span><span class="sxs-lookup"><span data-stu-id="60212-110">If this is the first time you're using Basic Mobility and Security for Microsoft 365 Business Standard, activate it here: [Activate Basic Security and Mobility](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="60212-111">Depois de ativação, gerencie seus dispositivos com Office 365 [Segurança & Conformidade.](https://protection.office.com/)</span><span class="sxs-lookup"><span data-stu-id="60212-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="60212-112">Vá para Prevenção contra perda de dados >Políticas de dispositivo  **de** gerenciamento de dispositivo e selecione Gerenciar configurações de acesso a dispositivos em toda a   >  \*\*\*\* **organização.**</span><span class="sxs-lookup"><span data-stu-id="60212-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>

4. <span data-ttu-id="60212-113">Selecione **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="60212-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Caixa de seleção de acesso de bloqueio básico de mobilidade e segurança":::

5. <span data-ttu-id="60212-115">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="60212-115">Select **Save**.</span></span>

<span data-ttu-id="60212-116">Para saber quais dispositivos o Basic Mobility and Security oferece suporte, consulte [Capabilities of Basic Mobility and Security](capabilities.md).</span><span class="sxs-lookup"><span data-stu-id="60212-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>
