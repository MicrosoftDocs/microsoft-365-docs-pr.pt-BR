---
title: Proteger dispositivos Windows 10
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: Saiba mais sobre como configurar as configurações da política de dispositivo padrão que qualquer dispositivo Windows 10 receberá ao entrar em sua conta de trabalho ou de estudante.
ms.openlocfilehash: 3f85549e722c9aa4196cf50fc02bee2e89506017
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925230"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="7e0d5-103">Proteger dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="7e0d5-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="7e0d5-104">Este artigo se aplica a Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="7e0d5-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="7e0d5-105">As configurações que você define aqui fazem parte da política de dispositivo padrão para Windows 10.</span><span class="sxs-lookup"><span data-stu-id="7e0d5-105">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="7e0d5-106">Todos os usuários que conectam um Windows 10, incluindo dispositivos móveis e PCs, ao entrar com sua conta de trabalho receberão automaticamente essas configurações.</span><span class="sxs-lookup"><span data-stu-id="7e0d5-106">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="7e0d5-107">Recomendamos aceitar a política padrão durante a instalação e, mais tarde, adicionar políticas destinadas a grupos de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="7e0d5-107">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="7e0d5-108">Configurações para proteger dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="7e0d5-108">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="7e0d5-p102">Todas as configurações são **Ativadas** por padrão. As configurações a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="7e0d5-p102">By default all settings are **On**. The following settings are available:</span></span>
  


|<span data-ttu-id="7e0d5-111">Setting</span><span class="sxs-lookup"><span data-stu-id="7e0d5-111">Setting</span></span>  <br/> |<span data-ttu-id="7e0d5-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="7e0d5-112">Description</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="7e0d5-113">Ajudar a proteger PCs contra vírus e outras ameaças usando o Windows Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="7e0d5-113">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="7e0d5-114">Exige que o Windows Defender Antivírus esteja ativado para proteger computadores contra os riscos de estar conectado à Internet.</span><span class="sxs-lookup"><span data-stu-id="7e0d5-114">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="7e0d5-115">Ajudar a proteger PCs contra ameaças baseadas na Web no Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7e0d5-115">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="7e0d5-116">Ativa as configurações do Microsoft Edge que ajudam a proteger os usuários contra sites e downloads mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="7e0d5-116">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="7e0d5-117">Ajudar a proteger os arquivos e pastas em computadores contra acesso não autorizado com o BitLocker</span><span class="sxs-lookup"><span data-stu-id="7e0d5-117">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="7e0d5-118">O BitLocker protege os dados por meio da criptografia das unidades de disco do computador e da proteção contra exposição de dados caso um computador seja perdido ou roubado.</span><span class="sxs-lookup"><span data-stu-id="7e0d5-118">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen.</span></span> <span data-ttu-id="7e0d5-119">Para obter mais informações, consulte [Perguntas frequentes do Bitlocker](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).</span><span class="sxs-lookup"><span data-stu-id="7e0d5-119">For more information, see [Bitlocker FAQ](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).</span></span>  <br/> |
|<span data-ttu-id="7e0d5-120">Desligar a tela do dispositivo quando ele ficar ocioso durante este período</span><span class="sxs-lookup"><span data-stu-id="7e0d5-120">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="7e0d5-p104">Garante que os dados da empresa estejam protegidos se um usuário ficar ocioso. Um usuário pode estar trabalhando em um local público, como um café, e se distanciar ou distrair por um momento, deixando seu dispositivo vulnerável a olhares aleatórios. Essa configuração permite que você controle quanto tempo o usuário pode ficar ocioso antes que a tela seja desligada.</span><span class="sxs-lookup"><span data-stu-id="7e0d5-p104">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|