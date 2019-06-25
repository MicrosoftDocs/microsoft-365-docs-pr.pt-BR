---
title: Proteger PCs e Macs não gerenciados do Windows 10
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Proteger contra phishing e outros ataques com o Microsoft 365 para campanhas.
ms.openlocfilehash: 8b83fa9c145f2c17347fc4c2983c64d4003f46c8
ms.sourcegitcommit: c452413dff5d5388c9725f38871246237c313e65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2019
ms.locfileid: "35183206"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="7c681-103">Proteger PCs e Macs não gerenciados do Windows 10</span><span class="sxs-lookup"><span data-stu-id="7c681-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="7c681-104">Você pode gerenciar os computadores com Windows 10 e Macs, registrando-os no Microsoft Intune, o que permite garantir que eles sejam íntegros e seguros antes de acessar dados em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="7c681-104">You can manage Windows 10 PCs and Macs by enrolling these into Microsoft Intune, which allows you to ensure these are healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="7c681-105">No entanto, muitas campanhas e pequenas empresas incluem funcionários que trazem seus próprios dispositivos (BYOD), que não serão gerenciados pela organização.</span><span class="sxs-lookup"><span data-stu-id="7c681-105">However, many campaigns and small businesses include staff that bring their own devices (byod) which will not be managed by the organization.</span></span> <span data-ttu-id="7c681-106">Para esses PCs e Macs não gerenciados, use este artigo para garantir que os recursos de segurança mínimos sejam configurados.</span><span class="sxs-lookup"><span data-stu-id="7c681-106">For these unmanaged PCs and Macs, use this article to ensure minimum security capabilities are configured.</span></span> 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 Business username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="7c681-107">Proteger um computador que executa o Windows 10 ou um Mac</span><span class="sxs-lookup"><span data-stu-id="7c681-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365 Business, or a Mac, the Microsoft 365 Business protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="7c681-108">Se o seu computador com o Windows 10 ou Mac não for gerenciado pela sua organização, certifique-se de configurar esses recursos de segurança.</span><span class="sxs-lookup"><span data-stu-id="7c681-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10tabwindows10"></a>[<span data-ttu-id="7c681-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="7c681-109">Windows 10</span></span>](#tab/Windows10)
<span data-ttu-id="7c681-110">**Ativar a criptografia do dispositivo**</span><span class="sxs-lookup"><span data-stu-id="7c681-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="7c681-111">A criptografia do dispositivo está disponível em uma ampla variedade de dispositivos Windows e ajuda a proteger seus dados criptografando-os.</span><span class="sxs-lookup"><span data-stu-id="7c681-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="7c681-112">Se você ativar a criptografia de dispositivo, apenas pessoas autorizadas poderão acessar o dispositivo e os dados.</span><span class="sxs-lookup"><span data-stu-id="7c681-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="7c681-113">Consulte [ativar a criptografia de dispositivo](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="7c681-113">See [turn on device encryption](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="7c681-114">Se a criptografia do dispositivo não estiver disponível em seu dispositivo, você poderá ativar a [criptografia BitLocker](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption) padrão.</span><span class="sxs-lookup"><span data-stu-id="7c681-114">If device encryption is not available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="7c681-115">(O BitLocker não está disponível no Windows 10 Home Edition.)</span><span class="sxs-lookup"><span data-stu-id="7c681-115">(BitLocker is not available on Windows 10 Home edition.)</span></span> 



<span data-ttu-id="7c681-116">**Proteger seu dispositivo com a segurança do Windows**</span><span class="sxs-lookup"><span data-stu-id="7c681-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="7c681-117">Se você tiver o Windows 10, obterá a proteção antivírus mais recente com a segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="7c681-117">If you have Windows 10, you’ll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="7c681-118">Quando você inicia o Windows 10 pela primeira vez, a segurança do Windows está ativada e ajudando ativamente a proteger seu computador examinando malware (software mal-intencionado), vírus e ameaças de segurança.</span><span class="sxs-lookup"><span data-stu-id="7c681-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="7c681-119">A segurança do Windows usa a proteção em tempo real para verificar tudo o que você baixa ou executa no seu computador.</span><span class="sxs-lookup"><span data-stu-id="7c681-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="7c681-120">O Windows Update baixa as atualizações da segurança do Windows automaticamente para ajudar a manter seu computador seguro e protegê-lo contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="7c681-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="7c681-121">Se você tiver uma versão anterior do Windows e estiver usando o Microsoft Security Essentials, é uma boa ideia mudar para a segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="7c681-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it’s a good idea to move to Windows Security.</span></span> <span data-ttu-id="7c681-122">Consulte [ajudar a proteger meu dispositivo com a segurança do Windows](https://support.microsoft.com/en-us/help/17464/windows-10-help-protect-my-device-with-windows-security) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="7c681-122">See [help protect my device with Windows Security](https://support.microsoft.com/en-us/help/17464/windows-10-help-protect-my-device-with-windows-security) for more information.</span></span>

<span data-ttu-id="7c681-123">**Ativar o Firewall do Windows**</span><span class="sxs-lookup"><span data-stu-id="7c681-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="7c681-124">Você deve sempre executar o Firewall do Windows mesmo se tiver outro firewall ativado.</span><span class="sxs-lookup"><span data-stu-id="7c681-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="7c681-125">Desativar o Firewall do Windows pode tornar seu dispositivo (e sua rede, se você tiver um) mais vulnerável a acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="7c681-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="7c681-126">Consulte [Ativar ou desativar o Firewall do Windows](https://support.microsoft.com/en-us/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) para obter instruções</span><span class="sxs-lookup"><span data-stu-id="7c681-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/en-us/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions</span></span>

## <a name="mactabmac"></a>[<span data-ttu-id="7c681-127">Mac</span><span class="sxs-lookup"><span data-stu-id="7c681-127">Mac</span></span>](#tab/Mac)
<span data-ttu-id="7c681-128">**Usar o FileVault para criptografar seu disco Mac**</span><span class="sxs-lookup"><span data-stu-id="7c681-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="7c681-129">A criptografia de disco protege os dados quando os dispositivos são perdidos ou roubados.</span><span class="sxs-lookup"><span data-stu-id="7c681-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="7c681-130">FileVault a criptografia de disco completo ajuda a impedir o acesso não autorizado às informações no seu disco de inicialização.</span><span class="sxs-lookup"><span data-stu-id="7c681-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="7c681-131">Consulte [usar FileVault para criptografar o disco de inicialização no Mac](https://support.apple.com/HT204837) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="7c681-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="7c681-132">**Proteger o Mac contra malware**</span><span class="sxs-lookup"><span data-stu-id="7c681-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="7c681-133">A Microsoft recomenda que você instale e use um software antivírus confiável no seu Mac.</span><span class="sxs-lookup"><span data-stu-id="7c681-133">Microsoft recommends you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="7c681-134">Consulte o seguinte artigo para obter uma lista de opções: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span><span class="sxs-lookup"><span data-stu-id="7c681-134">See the following article for a list of choices: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="7c681-135">Você também pode reduzir o risco de malware usando software apenas de fontes confiáveis.</span><span class="sxs-lookup"><span data-stu-id="7c681-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="7c681-136">As configurações nas preferências de segurança & privacidade permitem que você especifique as fontes do software instalado no seu Mac.</span><span class="sxs-lookup"><span data-stu-id="7c681-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="7c681-137">Consulte [proteger seu Mac contra malware](https://support.apple.com/kb/PH25087) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="7c681-137">See [protect your Mac from malware](https://support.apple.com/kb/PH25087) for more information.</span></span>

<span data-ttu-id="7c681-138">**Ativar proteção de firewall**</span><span class="sxs-lookup"><span data-stu-id="7c681-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="7c681-139">Use as configurações de firewall para proteger seu Mac do contato indesejado iniciado por outros computadores quando você estiver conectado à Internet ou a uma rede.</span><span class="sxs-lookup"><span data-stu-id="7c681-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you’re connected to the Internet or a network.</span></span> <span data-ttu-id="7c681-140">Sem essa proteção, seu Mac pode estar mais vulnerável a acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="7c681-140">Without this protection your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="7c681-141">Consulte [sobre o Firewall do aplicativo](https://support.apple.com/HT201642) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="7c681-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>
