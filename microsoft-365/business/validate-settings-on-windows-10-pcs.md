---
title: Validar as configurações de proteção de aplicativo em computadores Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Saiba como validar configurações de proteção do aplicativo Microsoft 365 Business em dispositivos Windows 10.
ms.openlocfilehash: db05c86bd75cc30e22e025034a3dab478d0f5365
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864846"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="66c18-103">Validar configurações de proteção de dispositivo em PCs de 10 do Windows</span><span class="sxs-lookup"><span data-stu-id="66c18-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="66c18-104">Verificar se as políticas de dispositivo do Windows 10 estão definidas</span><span class="sxs-lookup"><span data-stu-id="66c18-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="66c18-p101">Após você [Configurar políticas de dispositivos](protection-settings-for-windows-10-pcs.md), ele pode demorar algumas horas para a política entrem em vigor em dispositivos dos usuários. Você pode confirmar que as políticas está em vigor examinando várias telas de configurações do Windows em dispositivos dos usuários. Porque os usuários não poderão modificar as configurações do Windows Update e Windows Defender antivírus em seus dispositivos Windows 10, muitas dessas opções serão esmaecida.</span><span class="sxs-lookup"><span data-stu-id="66c18-p101">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices. You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices. Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, a lot of those options will be greyed out.</span></span>
  
1. <span data-ttu-id="66c18-108">Vá para **configurações** \> **atualização &amp; segurança** \> **Windows Update** \> **reiniciar as opções** e confirme que todas as configurações estão em cinza.</span><span class="sxs-lookup"><span data-stu-id="66c18-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are greyed out.</span></span> 
    
    ![Todas as opções de reinicialização ficam cinza.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="66c18-110">Vá para **configurações** \> **atualização &amp; segurança** \> **Windows Update** \> **Opções avançadas** e confirme que todas as configurações estão em cinza.</span><span class="sxs-lookup"><span data-stu-id="66c18-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are greyed out.</span></span> 
    
    ![Opções de atualizações do Windows Advanced todos esmaecidas.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="66c18-112">Vá para **configurações** \> **atualização &amp; segurança** \> **Windows Update** \> **Opções avançadas** \> **escolher como as atualizações são entregues**.</span><span class="sxs-lookup"><span data-stu-id="66c18-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="66c18-113">Confirme que você pode ver a mensagem (em vermelho) que algumas configurações estiverem ocultas ou gerenciadas por sua organização, e todas as opções ficam cinza.</span><span class="sxs-lookup"><span data-stu-id="66c18-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are greyed out.</span></span>
    
    ![Escolher como as atualizações são entregues página indica as configurações estiverem ocultas ou gerenciadas por sua organização.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="66c18-115">Para abrir a Central de segurança do Windows Defender, vá para **configurações** \> **atualização &amp; segurança** \> **Windows Defender** \> clique em **Abrir Windows Defender Security Center** \> **vírus &amp; thread proteção** \> **vírus &amp; configurações de proteção de ameaça**.</span><span class="sxs-lookup"><span data-stu-id="66c18-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="66c18-116">Verifique se todas as opções são esmaecidas.</span><span class="sxs-lookup"><span data-stu-id="66c18-116">Verify that all options are greyed out.</span></span> 
    
    ![As configurações de proteção de vírus e ameaças ficam cinza.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="66c18-118">Tópicos Relacionados</span><span class="sxs-lookup"><span data-stu-id="66c18-118">Related Topics</span></span>

[<span data-ttu-id="66c18-119">Documentação e recursos do Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="66c18-119">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="66c18-120">Introdução ao Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="66c18-120">Get started with Microsoft 365 Business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="66c18-121">Gerenciar o Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="66c18-121">Manage Microsoft 365 Business</span></span>](manage.md)
  
[<span data-ttu-id="66c18-122">Definir configurações de dispositivo para computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="66c18-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

