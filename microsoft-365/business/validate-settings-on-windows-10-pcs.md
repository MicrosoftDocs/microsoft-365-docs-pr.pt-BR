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
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Saiba como verificar se as configurações do Microsoft 365 Business app Protection foram efetivadas nos dispositivos Windows 10 dos usuários.
ms.openlocfilehash: 47977f8d79eb6dbb2f4d087af8f8ad7da4313c61
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42560671"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="0c3f2-103">Validar configurações de proteção do dispositivo em computadores com Windows 10</span><span class="sxs-lookup"><span data-stu-id="0c3f2-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="0c3f2-104">Verificar se as políticas de dispositivo do Windows 10 estão definidas</span><span class="sxs-lookup"><span data-stu-id="0c3f2-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="0c3f2-105">Depois de [configurar as políticas de dispositivos](protection-settings-for-windows-10-pcs.md), pode levar algumas horas para que a política entre em vigor nos dispositivos dos usuários.</span><span class="sxs-lookup"><span data-stu-id="0c3f2-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="0c3f2-106">Você pode confirmar que as políticas tomaram efeito examinando várias telas de configurações do Windows nos dispositivos dos usuários.</span><span class="sxs-lookup"><span data-stu-id="0c3f2-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="0c3f2-107">Como os usuários não poderão modificar as configurações do Windows Update Antivirus e do Windows Defender em seus dispositivos Windows 10, muitas opções serão acinzentadas.</span><span class="sxs-lookup"><span data-stu-id="0c3f2-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="0c3f2-108">Vá para **configurações** \> **atualização &amp; de segurança** \> do **Windows Update** \> **Opções de reinicialização** e confirme se todas as configurações estão acinzentadas.</span><span class="sxs-lookup"><span data-stu-id="0c3f2-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![Todas as opções de reinicialização ficam esmaecidas.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="0c3f2-110">Vá para **configurações** \> **avançadas** de **atualização &amp; de segurança** \> do **Windows Update** \> e confirme se todas as configurações estão acinzentadas.</span><span class="sxs-lookup"><span data-stu-id="0c3f2-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![As opções avançadas do Windows estão esmaecidas.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="0c3f2-112">Vá até **configurações** \> **atualização &amp; de segurança** \> do **Windows Update** \> **Opções** \> avançadas **escolha como as atualizações são entregues**.</span><span class="sxs-lookup"><span data-stu-id="0c3f2-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="0c3f2-113">Confirme que você pode ver a mensagem (em vermelho) que algumas configurações estão ocultas ou gerenciadas pela sua organização, e todas as opções estão acinzentadas.</span><span class="sxs-lookup"><span data-stu-id="0c3f2-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![Escolha a página como as atualizações são entregues indica que as configurações estão ocultas ou gerenciadas pela sua organização.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="0c3f2-115">Para abrir a central de segurança do Windows Defender, vá para **configurações** \> de segurança \> de \*\* &amp; atualização\*\* do **Windows Defender** \> clique em **abrir a central** \> \*\* &amp; \*\* de segurança do Windows Defender proteção \> contra \*\* &amp; ameaças\*\*de vírus.</span><span class="sxs-lookup"><span data-stu-id="0c3f2-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="0c3f2-116">Verifique se todas as opções estão acinzentadas.</span><span class="sxs-lookup"><span data-stu-id="0c3f2-116">Verify that all options are grayed out.</span></span> 
    
    ![As configurações de proteção contra vírus e ameaças são esmaecidas.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="0c3f2-118">Tópicos Relacionados</span><span class="sxs-lookup"><span data-stu-id="0c3f2-118">Related Topics</span></span>

[<span data-ttu-id="0c3f2-119">Documentação e recursos do Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="0c3f2-119">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="0c3f2-120">Introdução ao Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="0c3f2-120">Get started with Microsoft 365 Business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="0c3f2-121">Gerenciar o Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="0c3f2-121">Manage Microsoft 365 Business</span></span>](manage.md)
  
[<span data-ttu-id="0c3f2-122">Definir configurações de dispositivo para computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="0c3f2-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

