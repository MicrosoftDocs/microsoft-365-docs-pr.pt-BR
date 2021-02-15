---
title: Proteja PCs e Macs com Windows 10 não gerenciados
f1.keywords:
- NOCSH
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
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Proteja os dispositivos não-manados ou traga seus próprios dispositivos (BYOD) com o Microsoft 365.
ms.openlocfilehash: 5c27b29b5bb4fb445655e671d8c654ad8e9abc6b
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044379"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="ef0da-103">Proteja PCs e Macs com Windows 10 não gerenciados</span><span class="sxs-lookup"><span data-stu-id="ef0da-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="ef0da-104">Você pode gerenciar computadores e Macs Com o Windows 10 registrando-os no Microsoft Intune, o que permite garantir que eles estão seguros e saudável antes de acessar os dados em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="ef0da-104">You can manage Windows 10 PCs and Macs by enrolling them in Microsoft Intune, which allows you to ensure they're healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="ef0da-105">No entanto, muitas campanhas e pequenas empresas incluem funcionários que trazem seus próprios dispositivos (BYOD), que não serão gerenciados pela organização.</span><span class="sxs-lookup"><span data-stu-id="ef0da-105">However, many campaigns and small businesses include staff who bring their own devices (BYOD), which will not be managed by the organization.</span></span> <span data-ttu-id="ef0da-106">Para esses PCs e Macs não gerenciamento, use este artigo para garantir que os recursos mínimos de segurança sejam configurados.</span><span class="sxs-lookup"><span data-stu-id="ef0da-106">For these unmanaged PCs and Macs, use this article to ensure that minimum security capabilities are configured.</span></span>

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="ef0da-107">Proteger um computador executando o Windows 10 ou um Mac</span><span class="sxs-lookup"><span data-stu-id="ef0da-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="ef0da-108">Se o seu PC ou Mac do Windows 10 não for gerenciado pela sua organização, certifique-se de configurar esses recursos de segurança.</span><span class="sxs-lookup"><span data-stu-id="ef0da-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10"></a>[<span data-ttu-id="ef0da-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="ef0da-109">Windows 10</span></span>](#tab/Windows10)

<span data-ttu-id="ef0da-110">**Ativar a criptografia de dispositivo**</span><span class="sxs-lookup"><span data-stu-id="ef0da-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="ef0da-111">A criptografia de dispositivo está disponível em uma ampla variedade de dispositivos Windows e ajuda a proteger seus dados criptografando-os.</span><span class="sxs-lookup"><span data-stu-id="ef0da-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="ef0da-112">Se você ativar a criptografia de dispositivo, somente pessoas autorizadas poderão acessar seu dispositivo e dados.</span><span class="sxs-lookup"><span data-stu-id="ef0da-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="ef0da-113">Consulte [ativar a criptografia de dispositivo](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="ef0da-113">See [turn on device encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="ef0da-114">Se a criptografia de dispositivo não estiver disponível em seu dispositivo, você poderá ativar a criptografia [BitLocker padrão.](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption)</span><span class="sxs-lookup"><span data-stu-id="ef0da-114">If device encryption isn't available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="ef0da-115">(O BitLocker não está disponível no Windows 10 Home Edition.)</span><span class="sxs-lookup"><span data-stu-id="ef0da-115">(BitLocker isn't available on Windows 10 Home edition.)</span></span> 

<span data-ttu-id="ef0da-116">**Proteger seu dispositivo com segurança do Windows**</span><span class="sxs-lookup"><span data-stu-id="ef0da-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="ef0da-117">Se você tiver o Windows 10, obterá a proteção antivírus mais recente com a Segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="ef0da-117">If you have Windows 10, you'll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="ef0da-118">Quando você inicia o Windows 10 pela primeira vez, a Segurança do Windows está ativa e ajudando ativamente a proteger seu computador, procurando malware (software mal-intencionado), vírus e ameaças à segurança.</span><span class="sxs-lookup"><span data-stu-id="ef0da-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="ef0da-119">A Segurança do Windows usa proteção em tempo real para verificar tudo o que você baixa ou executado em seu computador.</span><span class="sxs-lookup"><span data-stu-id="ef0da-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="ef0da-120">O Windows Update baixa atualizações da Segurança do Windows automaticamente para ajudar a manter seu computador seguro e protegido contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="ef0da-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="ef0da-121">Se você tiver uma versão anterior do Windows e estiver usando o Microsoft Security Essentials, é uma boa ideia mudar para a Segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="ef0da-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it's a good idea to move to Windows Security.</span></span> <span data-ttu-id="ef0da-122">Para obter mais informações, consulte [Ajuda para proteger meu dispositivo com Segurança do Windows.](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)</span><span class="sxs-lookup"><span data-stu-id="ef0da-122">For more information, see [help protect my device with Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span></span>

<span data-ttu-id="ef0da-123">**Ativar o Firewall do Windows**</span><span class="sxs-lookup"><span data-stu-id="ef0da-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="ef0da-124">Você sempre deve executar o Firewall do Windows mesmo se tiver outro firewall ativado.</span><span class="sxs-lookup"><span data-stu-id="ef0da-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="ef0da-125">Desligar o Firewall do Windows pode tornar seu dispositivo (e sua rede, se você tiver um) mais vulnerável a acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="ef0da-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="ef0da-126">Consulte [Ativar ou desativar o Firewall do Windows para obter](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) instruções</span><span class="sxs-lookup"><span data-stu-id="ef0da-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions</span></span>

## <a name="mac"></a>[<span data-ttu-id="ef0da-127">Mac</span><span class="sxs-lookup"><span data-stu-id="ef0da-127">Mac</span></span>](#tab/Mac)

<span data-ttu-id="ef0da-128">**Usar FileVault para criptografar seu disco Mac**</span><span class="sxs-lookup"><span data-stu-id="ef0da-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="ef0da-129">A criptografia de disco protege os dados quando os dispositivos são perdidos ou roubados.</span><span class="sxs-lookup"><span data-stu-id="ef0da-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="ef0da-130">A criptografia de disco completo FileVault ajuda a impedir o acesso não autorizado às informações no disco de inicialização.</span><span class="sxs-lookup"><span data-stu-id="ef0da-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="ef0da-131">Consulte [usar FileVault para criptografar o disco de inicialização em seu Mac para](https://support.apple.com/HT204837) obter instruções.</span><span class="sxs-lookup"><span data-stu-id="ef0da-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="ef0da-132">**Proteger seu mac contra malware**</span><span class="sxs-lookup"><span data-stu-id="ef0da-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="ef0da-133">A Microsoft recomenda que você instale e use software antivírus confiável no Mac.</span><span class="sxs-lookup"><span data-stu-id="ef0da-133">Microsoft recommends that you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="ef0da-134">Confira o artigo a seguir para ver uma lista de opções: [Melhor Mac antivírus 2019. ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)</span><span class="sxs-lookup"><span data-stu-id="ef0da-134">See the following article for a list of choices: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="ef0da-135">Você também pode reduzir o risco de malware usando software apenas de fontes confiáveis.</span><span class="sxs-lookup"><span data-stu-id="ef0da-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="ef0da-136">As configurações em Segurança & privacidade permitem que você especifique as fontes de software instaladas em seu Mac.</span><span class="sxs-lookup"><span data-stu-id="ef0da-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="ef0da-137">Para obter mais informações, confira [proteger seu Mac contra malware.](https://support.apple.com/kb/PH25087)</span><span class="sxs-lookup"><span data-stu-id="ef0da-137">For more information, see [protect your Mac from malware](https://support.apple.com/kb/PH25087).</span></span>

<span data-ttu-id="ef0da-138">**Ativar a proteção de firewall**</span><span class="sxs-lookup"><span data-stu-id="ef0da-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="ef0da-139">Use as configurações de firewall para proteger seu Mac contra contatos indesejados iniciados por outros computadores quando você estiver conectado à Internet ou a uma rede.</span><span class="sxs-lookup"><span data-stu-id="ef0da-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you're connected to the Internet or a network.</span></span> <span data-ttu-id="ef0da-140">Sem essa proteção, seu Mac pode ficar mais vulnerável a acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="ef0da-140">Without this protection, your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="ef0da-141">Consulte [o firewall do aplicativo](https://support.apple.com/HT201642) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="ef0da-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>
