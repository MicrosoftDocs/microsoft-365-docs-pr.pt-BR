---
title: Desativar a mobilidade básica e segurança
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
description: Remover grupos ou políticas para desativar a mobilidade básica e a segurança.
ms.openlocfilehash: 54f78cc30e5259ad5244ce3a8fc6d0f46a395d7c
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430054"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="77cd9-103">Desativar a mobilidade básica e segurança</span><span class="sxs-lookup"><span data-stu-id="77cd9-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="77cd9-104">Para desativar efetivamente a mobilidade e a segurança básica, remova grupos de pessoas definidos por grupos de segurança das políticas de gerenciamento de dispositivos ou remova as próprias políticas.</span><span class="sxs-lookup"><span data-stu-id="77cd9-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="77cd9-105">Remover grupos de usuários, removendo grupos de segurança do usuário das políticas de dispositivos que você criou.</span><span class="sxs-lookup"><span data-stu-id="77cd9-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>
    
- <span data-ttu-id="77cd9-106">Desabilite a mobilidade básica e a segurança para todos removendo todas as políticas básicas de mobilidade e dispositivo de segurança.</span><span class="sxs-lookup"><span data-stu-id="77cd9-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>
    
<span data-ttu-id="77cd9-107">Essas opções removem a mobilidade básica e a imposição de segurança para dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="77cd9-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="77cd9-108">Infelizmente, não é possível simplesmente "desconfigurar" a mobilidade básica e a segurança após configurá-la.</span><span class="sxs-lookup"><span data-stu-id="77cd9-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="77cd9-109">Lembre-se do impacto nos dispositivos dos usuários ao remover grupos de segurança do usuário das políticas ou remover as próprias diretivas.</span><span class="sxs-lookup"><span data-stu-id="77cd9-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="77cd9-110">Por exemplo, perfis de email e emails em cache podem ser removidos, dependendo do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="77cd9-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="77cd9-111">Para obter mais informações, consulte  [o que acontece quando você exclui uma política ou remove um usuário da política?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span><span class="sxs-lookup"><span data-stu-id="77cd9-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="77cd9-112">Remover grupos de segurança de usuário das políticas de mobilidade básica e dispositivo de segurança</span><span class="sxs-lookup"><span data-stu-id="77cd9-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="77cd9-113">No seu navegador, digite:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="77cd9-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="77cd9-114">Selecione uma política de dispositivo e selecione **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="77cd9-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="77cd9-115">Na página  **implantação**   , selecione **remover**.</span><span class="sxs-lookup"><span data-stu-id="77cd9-115">On the  **Deployment**  page, select **Remove**.</span></span>
    
4. <span data-ttu-id="77cd9-116">Em  **grupos**, selecione um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="77cd9-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="77cd9-117">Selecione  **remover**e selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="77cd9-117">Select  **Remove**, and select **Save**.</span></span>
    

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="77cd9-118">Remover as políticas de mobilidade básica e dispositivo de segurança</span><span class="sxs-lookup"><span data-stu-id="77cd9-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="77cd9-119">No seu navegador, digite:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="77cd9-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="77cd9-120">Selecione uma política de dispositivo e, em seguida, selecione  **excluir política**.</span><span class="sxs-lookup"><span data-stu-id="77cd9-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="77cd9-121">Na caixa de diálogo de aviso, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="77cd9-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE] 
><span data-ttu-id="77cd9-122">Para obter mais etapas para desbloquear dispositivos se os dispositivos de sua organização ainda estiverem em um estado bloqueado, consulte o blog post [removendo o controle de acesso do gerenciamento de dispositivos móveis para o Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span><span class="sxs-lookup"><span data-stu-id="77cd9-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
