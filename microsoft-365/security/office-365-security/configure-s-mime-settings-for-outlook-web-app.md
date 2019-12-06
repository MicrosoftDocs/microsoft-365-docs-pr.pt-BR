---
title: Configurar as definições S/MIME no Exchange Online para Outlook na Web
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Uma breve descrição do que os administradores do Exchange Online precisam fazer para exibir e configurar as configurações S/MIME no Outlook na Web no Exchange Online.
ms.openlocfilehash: 759e48544e9c9dedca15500edb56e9111987bf93
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39866333"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="97fd7-103">Configurar as definições S/MIME no Exchange Online para Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="97fd7-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="97fd7-104">Como administrador do Exchange Online, você pode configurar o Outlook na Web (anteriormente conhecido como Outlook Web App) para permitir o envio e recebimento de mensagens protegidas por S/MIME.</span><span class="sxs-lookup"><span data-stu-id="97fd7-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="97fd7-105">Use os cmdlets **Get-SmimeConfig** e **set-SmimeConfig** para exibir e gerenciar esse recurso no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="97fd7-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="97fd7-106">Para se conectar ao Exchange Online PowerShell, confira [Conectar ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="97fd7-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

<span data-ttu-id="97fd7-107">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig) e [set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="97fd7-107">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="97fd7-108">Considerações para o Chrome</span><span class="sxs-lookup"><span data-stu-id="97fd7-108">Considerations for Chrome</span></span>

<span data-ttu-id="97fd7-109">Para usar S/MIME no Outlook na Web no navegador Google Chrome, você (ou outro administrador) deve definir e configurar a política do Chromium chamada **ExtensionInstallForcelist** para instalar a extensão S/MIME da Microsoft no Chrome.</span><span class="sxs-lookup"><span data-stu-id="97fd7-109">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="97fd7-110">O valor da política `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`é.</span><span class="sxs-lookup"><span data-stu-id="97fd7-110">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="97fd7-111">E observe que a aplicação dessa política exige computadores associados ao domínio, portanto, usar S/MIME no Chrome requer computadores associados ao domínio.</span><span class="sxs-lookup"><span data-stu-id="97fd7-111">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="97fd7-112">Para obter detalhes sobre a política **ExtensionInstallForcelist** , consulte [ExtensionInstallForcelist](https://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).</span><span class="sxs-lookup"><span data-stu-id="97fd7-112">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).</span></span>

<span data-ttu-id="97fd7-113">Esta etapa é um pré-requisito para usar o Chrome; Ele não substitui o controle S/MIME instalado pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="97fd7-113">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="97fd7-114">Os usuários são solicitados a baixar e instalar o controle S/MIME no Outlook na Web durante o primeiro uso de S/MIME.</span><span class="sxs-lookup"><span data-stu-id="97fd7-114">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="97fd7-115">Ou, os usuários podem ir proativamente para o **S/MIME** em suas configurações do Outlook na Web para obter o link de download do controle.</span><span class="sxs-lookup"><span data-stu-id="97fd7-115">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="97fd7-116">Para saber mais</span><span class="sxs-lookup"><span data-stu-id="97fd7-116">For more information</span></span>

[<span data-ttu-id="97fd7-117">S/MIME para assinatura e criptografia de mensagens</span><span class="sxs-lookup"><span data-stu-id="97fd7-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
