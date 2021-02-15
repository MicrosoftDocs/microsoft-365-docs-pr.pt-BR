---
title: Desativar a Mobilidade e Segurança Básica
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
description: Remova grupos ou políticas para desativar a Mobilidade Básica e Segurança.
ms.openlocfilehash: 0786ac8ebd190b9af3211c211cc6db2ea9e0ea48
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876835"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="d3781-103">Desativar a Mobilidade e Segurança Básica</span><span class="sxs-lookup"><span data-stu-id="d3781-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="d3781-104">Para desativar efetivamente a Mobilidade Básica e a Segurança, remova grupos de pessoas definidos por grupos de segurança das políticas de gerenciamento de dispositivos ou remova as próprias políticas.</span><span class="sxs-lookup"><span data-stu-id="d3781-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="d3781-105">Remova grupos de usuários removendo grupos de segurança de usuários das políticas de dispositivo que você criou.</span><span class="sxs-lookup"><span data-stu-id="d3781-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>

- <span data-ttu-id="d3781-106">Desabilite a Mobilidade Básica e a Segurança para todos removendo todas as políticas básicas de dispositivos de Mobilidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="d3781-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>

<span data-ttu-id="d3781-107">Essas opções removem a imposição básica de mobilidade e segurança para dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d3781-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="d3781-108">Infelizmente, você não pode simplesmente "desprovisionar" a Mobilidade e a Segurança Básica após a configuração.</span><span class="sxs-lookup"><span data-stu-id="d3781-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="d3781-109">Esteja ciente do impacto nos dispositivos dos usuários ao remover grupos de segurança de usuários das políticas ou remover as próprias políticas.</span><span class="sxs-lookup"><span data-stu-id="d3781-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="d3781-110">Por exemplo, perfis de email e emails armazenados em cache podem ser removidos, dependendo do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d3781-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="d3781-111">Para obter mais informações,  [consulte O que acontece quando você exclui uma política ou remove um usuário da política?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span><span class="sxs-lookup"><span data-stu-id="d3781-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="d3781-112">Remover grupos de segurança do usuário das políticas básicas de dispositivos de mobilidade e segurança</span><span class="sxs-lookup"><span data-stu-id="d3781-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="d3781-113">No seu tipo de navegador:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="d3781-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="d3781-114">Selecione uma política de dispositivo e selecione **Editar política.**</span><span class="sxs-lookup"><span data-stu-id="d3781-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="d3781-115">Na  \*\*\*\* página   Implantação, selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="d3781-115">On the  **Deployment**  page, select **Remove**.</span></span>

4. <span data-ttu-id="d3781-116">Em  **Grupos,** selecione um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="d3781-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="d3781-117">Selecione  **Remover** e **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="d3781-117">Select  **Remove**, and select **Save**.</span></span>

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="d3781-118">Remover políticas básicas de dispositivos de mobilidade e segurança</span><span class="sxs-lookup"><span data-stu-id="d3781-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="d3781-119">No seu tipo de navegador:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="d3781-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="d3781-120">Selecione uma política de dispositivo e, em seguida,  **selecione Excluir política.**</span><span class="sxs-lookup"><span data-stu-id="d3781-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="d3781-121">Na caixa de diálogo Aviso, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="d3781-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE]
><span data-ttu-id="d3781-122">Para obter mais etapas para desbloquear dispositivos se os dispositivos da sua organização ainda estão em um estado bloqueado, consulte a postagem do blog Removendo o Controle de Acesso do Gerenciamento de Dispositivo Móvel para [o Office 365.](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)</span><span class="sxs-lookup"><span data-stu-id="d3781-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
