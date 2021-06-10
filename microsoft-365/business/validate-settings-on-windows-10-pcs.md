---
title: Validar as configurações de proteção de aplicativo em computadores Windows 10
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Saiba como verificar se as configurações Microsoft 365 de proteção de aplicativos comerciais entrou em vigor nos dispositivos Windows 10 dos usuários.
ms.openlocfilehash: fcb463fd98f692f7d4802689e0c03fe4e3e648a1
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579833"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="d3ba8-103">Validar configurações de proteção de dispositivo em Windows 10 PCs</span><span class="sxs-lookup"><span data-stu-id="d3ba8-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="d3ba8-104">Verifique se as Windows 10 de dispositivo estão definidas</span><span class="sxs-lookup"><span data-stu-id="d3ba8-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="d3ba8-105">Depois de [configurar políticas de](protection-settings-for-windows-10-pcs.md)dispositivos, pode levar até algumas horas para que a política entre em vigor nos dispositivos dos usuários.</span><span class="sxs-lookup"><span data-stu-id="d3ba8-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="d3ba8-106">Você pode confirmar se as políticas foram efetivadas analisando várias Windows Configurações nos dispositivos dos usuários.</span><span class="sxs-lookup"><span data-stu-id="d3ba8-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="d3ba8-107">Como os usuários não poderão modificar as configurações Windows Update e Windows Defender Antivírus em seus dispositivos Windows 10, muitas opções serão acinzentados.</span><span class="sxs-lookup"><span data-stu-id="d3ba8-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="d3ba8-108">Vá para **Configurações** Atualizar Windows Opções de Reinicialização de Atualização e confirme se todas as \> **&amp;** \>  \>  configurações estão acinzenadas.</span><span class="sxs-lookup"><span data-stu-id="d3ba8-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![Todas as opções reiniciar estão acinzenadas.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="d3ba8-110">Vá para **Configurações** Atualizar Windows Atualizar Opções Avançadas e confirme se todas as \> **&amp;** \>  \>  configurações estão acinzenadas.</span><span class="sxs-lookup"><span data-stu-id="d3ba8-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Windows As opções de atualizações avançadas estão todas acinzenadas.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="d3ba8-112">Vá para **Configurações** Atualizar \> **&amp; Windows** \> **Opções** Avançadas De atualização Escolha como \>  \> **as atualizações são entregues.**</span><span class="sxs-lookup"><span data-stu-id="d3ba8-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="d3ba8-113">Confirme se você pode ver a mensagem (em vermelho) de que algumas configurações estão ocultas ou gerenciadas por sua organização, e todas as opções estão acinzenadas.</span><span class="sxs-lookup"><span data-stu-id="d3ba8-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![Escolha como as atualizações são entregues página indica que as configurações estão ocultas ou gerenciadas pela sua organização.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="d3ba8-115">Para abrir Windows Defender Central de Segurança, vá Configurações Atualização de segurança Windows Defender clique em  \> **&amp;** \>  \> **Abrir** \> **&amp;** \> **&amp;** Windows Defender Proteção contra vírus do Centro de Segurança.</span><span class="sxs-lookup"><span data-stu-id="d3ba8-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="d3ba8-116">Verifique se todas as opções estão acinzenadas.</span><span class="sxs-lookup"><span data-stu-id="d3ba8-116">Verify that all options are grayed out.</span></span> 
    
    ![As configurações de proteção contra vírus e ameaças estão acinzenadas.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="d3ba8-118">Tópicos Relacionados</span><span class="sxs-lookup"><span data-stu-id="d3ba8-118">Related Topics</span></span>

[<span data-ttu-id="d3ba8-119">Microsoft 365 para recursos e documentação de negócios</span><span class="sxs-lookup"><span data-stu-id="d3ba8-119">Microsoft 365 for business documentation and resources</span></span>](./index.yml)
  
[<span data-ttu-id="d3ba8-120">Começar com o Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="d3ba8-120">Get started with Microsoft 365 for business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="d3ba8-121">Gerenciar Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="d3ba8-121">Manage Microsoft 365 for business</span></span>](manage.md)
  
[<span data-ttu-id="d3ba8-122">Definir configurações de dispositivo para computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="d3ba8-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
