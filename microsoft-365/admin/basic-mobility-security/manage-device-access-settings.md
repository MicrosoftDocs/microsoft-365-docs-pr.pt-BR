---
title: Gerenciar configurações de acesso de dispositivos em Mobilidade Básica e Segurança
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
description: A Mobilidade Básica e Segurança pode ajudá-lo a proteger e gerenciar dispositivos móveis.
ms.openlocfilehash: dd9d777798c2c96776a8f9b40a3c4dfe0b95702a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876943"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="00f6b-103">Gerenciar configurações de acesso de dispositivos em Mobilidade Básica e Segurança</span><span class="sxs-lookup"><span data-stu-id="00f6b-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="00f6b-104">Se você estiver usando Mobilidade Básica e Segurança, pode haver dispositivos que você não pode gerenciar com Mobilidade e Segurança Básica.</span><span class="sxs-lookup"><span data-stu-id="00f6b-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="00f6b-105">Nesse caso, você deve bloquear o acesso do aplicativo Exchange ActiveSync ao email do Microsoft 365 para dispositivos móveis que não são suportados pelo Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="00f6b-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="00f6b-106">Isso ajuda a proteger as informações da sua organização em mais dispositivos.</span><span class="sxs-lookup"><span data-stu-id="00f6b-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="00f6b-107">Use estas etapas:</span><span class="sxs-lookup"><span data-stu-id="00f6b-107">Use these steps:</span></span>

1. <span data-ttu-id="00f6b-108">Entre no Microsoft 365 com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="00f6b-108">Sign in to  Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="00f6b-109">No navegador, digite:  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="00f6b-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>    

    >[!IMPORTANT]
    ><span data-ttu-id="00f6b-110">Se esta for a primeira vez que você estiver usando o Basic Mobility and Security para o Microsoft 365 Business Standard, ative-a aqui: Ativar Segurança Básica [e Mobilidade.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)</span><span class="sxs-lookup"><span data-stu-id="00f6b-110">If this is the first time you're using Basic Mobility and Security for Microsoft 365 Business Standard, activate it here: [Activate Basic Security and Mobility](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="00f6b-111">Depois de ativação, gerencie seus dispositivos com o [Office 365 Security & Compliance.](https://protection.office.com/)</span><span class="sxs-lookup"><span data-stu-id="00f6b-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="00f6b-112">Vá para Prevenção contra perda de dados > **Políticas** de dispositivo de gerenciamento de dispositivo e selecione Gerenciar configurações de acesso a   >  \*\*\*\* **dispositivos em toda a organização.**</span><span class="sxs-lookup"><span data-stu-id="00f6b-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>

4. <span data-ttu-id="00f6b-113">Selecione **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="00f6b-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Caixa de seleção mobilidade básica e segurança bloquear acesso":::

5. <span data-ttu-id="00f6b-115">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="00f6b-115">Select **Save**.</span></span>

<span data-ttu-id="00f6b-116">Para saber quais dispositivos o Basic Mobility and Security oferece suporte, consulte [Recursos de Mobilidade Básica e Segurança.](capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="00f6b-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>