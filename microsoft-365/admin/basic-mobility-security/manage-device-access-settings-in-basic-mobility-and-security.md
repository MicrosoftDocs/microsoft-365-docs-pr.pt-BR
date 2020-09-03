---
title: Gerenciar as configurações de acesso de dispositivo na mobilidade básica e segurança
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
description: Mobilidade e segurança básica podem ajudá-lo a proteger e gerenciar dispositivos móveis.
ms.openlocfilehash: 0d8f4293c45bcc1dc2a71dbc749641cf3791337e
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336697"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="29410-103">Gerenciar as configurações de acesso de dispositivo na mobilidade básica e segurança</span><span class="sxs-lookup"><span data-stu-id="29410-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="29410-104">Se você estiver usando mobilidade básica e segurança, pode haver dispositivos que você não pode gerenciar com mobilidade básica e segurança.</span><span class="sxs-lookup"><span data-stu-id="29410-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="29410-105">Em caso afirmativo, você deve bloquear o acesso do aplicativo Exchange ActiveSync ao email do Microsoft 365 para dispositivos móveis que não são suportados pela mobilidade básica e segurança.</span><span class="sxs-lookup"><span data-stu-id="29410-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="29410-106">Isso ajuda a proteger as informações da sua organização em mais dispositivos.</span><span class="sxs-lookup"><span data-stu-id="29410-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="29410-107">Siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="29410-107">Use these steps:</span></span>

1. <span data-ttu-id="29410-108">Entre no Microsoft 365 com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="29410-108">Sign in to  Microsoft 365 with your global admin account.</span></span>
    
2. <span data-ttu-id="29410-109">No navegador, digite:  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="29410-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>    

    >[!IMPORTANT]
    ><span data-ttu-id="29410-110">Se esta é a primeira vez que você está usando o MDM para o Microsoft 365 Business Standard, ative-o aqui: [ativar o gerenciamento de dispositivos móveis](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span><span class="sxs-lookup"><span data-stu-id="29410-110">If this is the first time you're using MDM for Microsoft 365 Business Standard, activate it here: [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="29410-111">Após ativá-la, gerencie seus dispositivos com o [Office 365 Security & Compliance](https://protection.office.com/).</span><span class="sxs-lookup"><span data-stu-id="29410-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="29410-112">Vá para prevenção de perda de  **Device management**dados >  >  **políticas de dispositivos**de gerenciamento de dispositivos e selecione **gerenciar configurações de acesso de dispositivo para toda a organização**.</span><span class="sxs-lookup"><span data-stu-id="29410-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>
    
4. <span data-ttu-id="29410-113">Selecione **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="29410-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Caixa de seleção mobilidade básica e acesso de bloqueio de segurança":::

5. <span data-ttu-id="29410-115">Selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="29410-115">Select **Save**.</span></span> 

<span data-ttu-id="29410-116">Para saber quais dispositivos são compatíveis com mobilidade e segurança básica, confira [recursos de mobilidade básica e segurança](capabilities-of-basic-mobility-and-secruity.md).</span><span class="sxs-lookup"><span data-stu-id="29410-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities-of-basic-mobility-and-secruity.md).</span></span>