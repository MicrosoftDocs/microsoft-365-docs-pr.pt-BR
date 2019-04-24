---
title: Validar as configurações de proteção de aplicativo em computadores Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Saiba como validar as configurações de proteção do Microsoft 365 Business app em dispositivos Windows 10.
ms.openlocfilehash: 5ab91d65fa7bd40ebc118df217c9711b7bbfe7a4
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286686"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="8b20b-103">Validar configurações de proteção do dispositivo em computadores com Windows 10</span><span class="sxs-lookup"><span data-stu-id="8b20b-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="8b20b-104">Verificar se as políticas de dispositivo do Windows 10 estão definidas</span><span class="sxs-lookup"><span data-stu-id="8b20b-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="8b20b-105">Depois de [configurar as políticas de dispositivos](protection-settings-for-windows-10-pcs.md), pode levar algumas horas para que a política entre em vigor nos dispositivos dos usuários.</span><span class="sxs-lookup"><span data-stu-id="8b20b-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="8b20b-106">Você pode confirmar que as políticas tomaram efeito examinando várias telas de configurações do Windows nos dispositivos dos usuários.</span><span class="sxs-lookup"><span data-stu-id="8b20b-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="8b20b-107">Como os usuários não poderão modificar as configurações de Windows Update e antivírus do Windows Defender em seus dispositivos Windows 10, muitas dessas opções ficarão acinzentadas.</span><span class="sxs-lookup"><span data-stu-id="8b20b-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, a lot of those options will be greyed out.</span></span>
  
1. <span data-ttu-id="8b20b-108">Vá para **configurações** \> **atualização &amp; de segurança** \> do **Windows Update** \> **Opções** de reinicialização e confirme se todas as configurações estão acinzentadas.</span><span class="sxs-lookup"><span data-stu-id="8b20b-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are greyed out.</span></span> 
    
    ![Todas as opções de reInicialização ficam acinzentadas.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="8b20b-110">Vá para **configurações** \> **avançadas** de **atualização &amp; de segurança** \> do **Windows Update** \> e confirme se todas as configurações estão acinzentadas.</span><span class="sxs-lookup"><span data-stu-id="8b20b-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are greyed out.</span></span> 
    
    ![As opções avançadas do Windows estão esmaecidas.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="8b20b-112">Vá até **configurações** \> **atualização &amp; de segurança** \> do **Windows Update** \> **Opções** \> avançadas **escolha como as atualizações são entregues**.</span><span class="sxs-lookup"><span data-stu-id="8b20b-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="8b20b-113">Confirme que você pode ver a mensagem (em vermelho) que algumas configurações estão ocultas ou gerenciadas pela sua organização, e todas as opções estão acinzentadas.</span><span class="sxs-lookup"><span data-stu-id="8b20b-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are greyed out.</span></span>
    
    ![Escolha a página como as atualizações são entregues indica que as configurações estão ocultas ou gerenciadas pela sua organização.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="8b20b-115">Para abrir a central de segurança do Windows Defender, acesse **configurações** \> de **atualização &amp; de segurança** \*\*\*\* \> \> Windows Defender clique em abrir o thread de \> vírus \*\*\*\* \*\* &amp; da central de segurança do Windows Defender \*\* \> **configurações de &amp; proteção contra ameaças de vírus**de proteção.</span><span class="sxs-lookup"><span data-stu-id="8b20b-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="8b20b-116">Verifique se todas as opções estão acinzentadas.</span><span class="sxs-lookup"><span data-stu-id="8b20b-116">Verify that all options are greyed out.</span></span> 
    
    ![As configurações de proteção contra vírus e ameaças estão acinzentadas.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="8b20b-118">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8b20b-118">Related Topics</span></span>

[<span data-ttu-id="8b20b-119">Documentação e recursos do Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="8b20b-119">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="8b20b-120">Introdução ao Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="8b20b-120">Get started with Microsoft 365 Business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="8b20b-121">Gerenciar o Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="8b20b-121">Manage Microsoft 365 Business</span></span>](manage.md)
  
[<span data-ttu-id="8b20b-122">Definir configurações de dispositivo para computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="8b20b-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

