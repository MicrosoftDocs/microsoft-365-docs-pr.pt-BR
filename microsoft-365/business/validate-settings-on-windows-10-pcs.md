---
title: Validar as configurações de proteção de aplicativo em computadores Windows 10
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
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Saiba como verificar se as configurações de proteção de aplicativos do Microsoft 365 para empresas entrou em vigor nos dispositivos Windows 10 dos usuários.
ms.openlocfilehash: 39aee3bc811cb0090d58f9a282de7a8162c097b3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403581"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="837cb-103">Validar configurações de proteção de dispositivo em computadores com Windows 10</span><span class="sxs-lookup"><span data-stu-id="837cb-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="837cb-104">Verificar se as políticas de dispositivo Windows 10 estão definidas</span><span class="sxs-lookup"><span data-stu-id="837cb-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="837cb-105">Depois de [configurar as políticas de](protection-settings-for-windows-10-pcs.md)dispositivos, pode levar algumas horas para que a política entre em vigor nos dispositivos dos usuários.</span><span class="sxs-lookup"><span data-stu-id="837cb-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="837cb-106">Você pode confirmar se as políticas entrou em vigor analisando várias telas de Configurações do Windows nos dispositivos dos usuários.</span><span class="sxs-lookup"><span data-stu-id="837cb-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="837cb-107">Como os usuários não poderão modificar as configurações do Windows Update e do Windows Defender Antivírus em seus dispositivos Windows 10, muitas opções estarão es cinza.</span><span class="sxs-lookup"><span data-stu-id="837cb-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="837cb-108">Vá para **as opções de Reinicialização** do Windows Update de segurança de Atualização de Configurações e confirme se todas as \> **&amp;** \>  \>  configurações estão es cinzas.</span><span class="sxs-lookup"><span data-stu-id="837cb-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![Todas as opções de reinicialização estão es cinza.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="837cb-110">Vá para **as opções de** segurança atualização de configurações do Windows Update Advanced e \> **&amp;** \>  \>  confirme se todas as configurações estão es cinza.</span><span class="sxs-lookup"><span data-stu-id="837cb-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![As opções de atualizações avançadas do Windows estão es cinza.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="837cb-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** Advanced \> **options** Choose \> **how updates are delivered**.</span><span class="sxs-lookup"><span data-stu-id="837cb-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="837cb-113">Confirme se você pode ver a mensagem (em vermelho) de que algumas configurações estão ocultas ou gerenciadas por sua organização e se todas as opções estão es cinza.</span><span class="sxs-lookup"><span data-stu-id="837cb-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![Escolha como as atualizações são entregues na página indica que as configurações estão ocultas ou gerenciadas pela sua organização.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="837cb-115">Para abrir a Central de  Segurança do Windows Defender, vá até Segurança de Atualização de Configurações do \> **&amp;** \> **Windows Defender,** clique em Abrir Proteção contra \>  \> **&amp; vírus** \> **&amp;** da Central de Segurança do Windows Defender Configurações de proteção contra ameaças contra vírus.</span><span class="sxs-lookup"><span data-stu-id="837cb-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="837cb-116">Verifique se todas as opções estão es cinzas.</span><span class="sxs-lookup"><span data-stu-id="837cb-116">Verify that all options are grayed out.</span></span> 
    
    ![As configurações de proteção contra vírus e ameaças estão es cinzas.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="837cb-118">Tópicos Relacionados</span><span class="sxs-lookup"><span data-stu-id="837cb-118">Related Topics</span></span>

[<span data-ttu-id="837cb-119">Documentação e recursos do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="837cb-119">Microsoft 365 for business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="837cb-120">Começar a trabalhar com o Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="837cb-120">Get started with Microsoft 365 for business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="837cb-121">Gerenciar o Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="837cb-121">Manage Microsoft 365 for business</span></span>](manage.md)
  
[<span data-ttu-id="837cb-122">Definir configurações de dispositivo para computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="837cb-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

