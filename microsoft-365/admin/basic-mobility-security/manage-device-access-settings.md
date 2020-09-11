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
ms.openlocfilehash: e66465d312c4268aca82677fa4e517aaeb822ce3
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430056"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="33438-103">Gerenciar as configurações de acesso de dispositivo na mobilidade básica e segurança</span><span class="sxs-lookup"><span data-stu-id="33438-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="33438-104">Se você estiver usando mobilidade básica e segurança, pode haver dispositivos que você não pode gerenciar com mobilidade básica e segurança.</span><span class="sxs-lookup"><span data-stu-id="33438-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="33438-105">Em caso afirmativo, você deve bloquear o acesso do aplicativo Exchange ActiveSync ao email do Microsoft 365 para dispositivos móveis que não são suportados pela mobilidade básica e segurança.</span><span class="sxs-lookup"><span data-stu-id="33438-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="33438-106">Isso ajuda a proteger as informações da sua organização em mais dispositivos.</span><span class="sxs-lookup"><span data-stu-id="33438-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="33438-107">Siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="33438-107">Use these steps:</span></span>

1. <span data-ttu-id="33438-108">Entre no Microsoft 365 com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="33438-108">Sign in to  Microsoft 365 with your global admin account.</span></span>
    
2. <span data-ttu-id="33438-109">No navegador, digite:  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="33438-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>    

    >[!IMPORTANT]
    ><span data-ttu-id="33438-110">Se esta é a primeira vez que você está usando o MDM para o Microsoft 365 Business Standard, ative-o aqui: [ativar o gerenciamento de dispositivos móveis](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span><span class="sxs-lookup"><span data-stu-id="33438-110">If this is the first time you're using MDM for Microsoft 365 Business Standard, activate it here: [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="33438-111">Após ativá-la, gerencie seus dispositivos com o [Office 365 Security & Compliance](https://protection.office.com/).</span><span class="sxs-lookup"><span data-stu-id="33438-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="33438-112">Vá para prevenção de perda de  **Device management**dados >  >  **políticas de dispositivos**de gerenciamento de dispositivos e selecione **gerenciar configurações de acesso de dispositivo para toda a organização**.</span><span class="sxs-lookup"><span data-stu-id="33438-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>
    
4. <span data-ttu-id="33438-113">Selecione **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="33438-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Caixa de seleção mobilidade básica e acesso de bloqueio de segurança":::

5. <span data-ttu-id="33438-115">Selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="33438-115">Select **Save**.</span></span> 

<span data-ttu-id="33438-116">Para saber quais dispositivos são compatíveis com mobilidade e segurança básica, confira [recursos de mobilidade básica e segurança](capabilities.md).</span><span class="sxs-lookup"><span data-stu-id="33438-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>