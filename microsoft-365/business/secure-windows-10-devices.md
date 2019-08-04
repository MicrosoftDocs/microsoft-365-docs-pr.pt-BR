---
title: Proteger dispositivos Windows 10
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: 'Saiba mais sobre o padrão e outras configurações para proteger dispositivos Windows 10. '
ms.openlocfilehash: b56aac0c760aa0e57d48683b5f1726c9add16d20
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074411"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="cfe8e-103">Proteger dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="cfe8e-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="cfe8e-p101">As configurações que você define aqui fazem parte da política de dispositivo padrão para Windows 10. Todos os usuários que se conectam a dispositivos Windows 10, inclusive dispositivos móveis e computadores, usando uma conta corporativa, recebem essas configurações automaticamente. Recomendamos aceitar a política padrão durante a instalação e, mais tarde, adicionar políticas destinadas a grupos de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="cfe8e-p101">The settings that you configure here are part of the default device policy for Windows 10. All users that connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account, will automatically receive these settings. We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="cfe8e-107">Configurações para proteger dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="cfe8e-107">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="cfe8e-p102">Todas as configurações são **Ativadas** por padrão. As configurações a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="cfe8e-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cfe8e-110">Setting</span><span class="sxs-lookup"><span data-stu-id="cfe8e-110">Setting</span></span>  <br/> |<span data-ttu-id="cfe8e-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="cfe8e-111">Description</span></span>  <br/> |
|<span data-ttu-id="cfe8e-112">Ajudar a proteger PCs contra vírus e outras ameaças usando o Windows Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="cfe8e-112">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="cfe8e-113">Exige que o Windows Defender Antivírus esteja ativado para proteger computadores contra os riscos de estar conectado à Internet.</span><span class="sxs-lookup"><span data-stu-id="cfe8e-113">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="cfe8e-114">Ajudar a proteger PCs contra ameaças baseadas na Web no Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="cfe8e-114">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="cfe8e-115">Ativa as configurações do Microsoft Edge que ajudam a proteger os usuários contra sites e downloads mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="cfe8e-115">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="cfe8e-116">Desligar a tela do dispositivo quando ele ficar ocioso durante este período</span><span class="sxs-lookup"><span data-stu-id="cfe8e-116">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="cfe8e-p103">Garante que os dados da empresa estejam protegidos se um usuário ficar ocioso. Um usuário pode estar trabalhando em um local público, como um café, e se distanciar ou distrair por um momento, deixando seu dispositivo vulnerável a olhares aleatórios. Essa configuração permite que você controle quanto tempo o usuário pode ficar ocioso antes que a tela seja desligada.</span><span class="sxs-lookup"><span data-stu-id="cfe8e-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="cfe8e-120">Permitir que os usuários baixem aplicativos da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="cfe8e-120">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="cfe8e-p104">Permite aos usuários baixar e instalar os aplicativos da Microsoft Store. Aplicativos incluem desde jogos a ferramentas de produtividade, portanto, deixamos essa configuração **Ativada**, mas você pode desativá-la para obter mais segurança.  </span><span class="sxs-lookup"><span data-stu-id="cfe8e-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="cfe8e-123">Permitir que os usuários acessem a Cortana</span><span class="sxs-lookup"><span data-stu-id="cfe8e-123">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="cfe8e-p105">A Cortana pode ser muito útil! Ela pode ativar ou desativar configurações para você, fornecer instruções e garantir que você cumpra compromissos pontualmente, então nós a mantemos **Ativadas**.  </span><span class="sxs-lookup"><span data-stu-id="cfe8e-p105">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="cfe8e-126">Permitir que os usuários recebam anúncios e dicas sobre o Windows da Microsoft</span><span class="sxs-lookup"><span data-stu-id="cfe8e-126">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="cfe8e-127">Dicas sobre o Windows podem ser úteis e ajudar a orientar os usuários quando novos recursos forem lançados.</span><span class="sxs-lookup"><span data-stu-id="cfe8e-127">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="cfe8e-128">Manter dispositivos Windows 10 atualizados automaticamente</span><span class="sxs-lookup"><span data-stu-id="cfe8e-128">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="cfe8e-129">Garante que os dispositivos Windows 10 recebam automaticamente as atualizações mais recentes.</span><span class="sxs-lookup"><span data-stu-id="cfe8e-129">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
   

