---
title: Configurar as definições S/MIME-Exchange Online para Outlook na Web
f1.keywords:
- NOCSH
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0b98a853d81d5ce067233314dfc59c7f677656bd
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352028"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="8d46b-103">Configurar as definições S/MIME no Exchange Online para Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="8d46b-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="8d46b-104">Como administrador do Exchange Online, você pode configurar o Outlook na Web (anteriormente conhecido como Outlook Web App) para permitir o envio e recebimento de mensagens protegidas por S/MIME.</span><span class="sxs-lookup"><span data-stu-id="8d46b-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="8d46b-105">Use os cmdlets **Get-SmimeConfig** e **set-SmimeConfig** para exibir e gerenciar esse recurso no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8d46b-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="8d46b-106">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="8d46b-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="8d46b-107">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) e [set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="8d46b-107">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="8d46b-108">Considerações para o novo Microsoft Edge (baseado em Chromium)</span><span class="sxs-lookup"><span data-stu-id="8d46b-108">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="8d46b-109">Para usar S/MIME no Outlook na Web no novo navegador da Web do [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) , você (ou outro administrador) deve definir e configurar a política de navegador do Microsoft Edge chamada **ExtensionInstallForcelist** para instalar a extensão S/MIME da Microsoft em novo Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="8d46b-109">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in new Microsoft Edge.</span></span> <span data-ttu-id="8d46b-110">O valor da política é `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="8d46b-110">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="8d46b-111">E observe que a aplicação dessa política requer computadores associados a um domínio, portanto, usar S/MIME no novo navegador do Microsoft Edge requer efetivamente computadores associados ao domínio.</span><span class="sxs-lookup"><span data-stu-id="8d46b-111">And note that applying this policy requires domain-joined computers, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined computers.</span></span>

<span data-ttu-id="8d46b-112">Para obter detalhes sobre a política **ExtensionInstallForcelist** , consulte [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span><span class="sxs-lookup"><span data-stu-id="8d46b-112">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="8d46b-113">Esta etapa é um pré-requisito para usar o novo Microsoft Edge; Ele não substitui o controle S/MIME instalado pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="8d46b-113">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="8d46b-114">Os usuários são solicitados a baixar e instalar o controle S/MIME no Outlook na Web durante o primeiro uso de S/MIME.</span><span class="sxs-lookup"><span data-stu-id="8d46b-114">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="8d46b-115">Ou, os usuários podem ir proativamente para o **S/MIME** em suas configurações do Outlook na Web para obter o link de download do controle.</span><span class="sxs-lookup"><span data-stu-id="8d46b-115">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="8d46b-116">Considerações para o Chrome</span><span class="sxs-lookup"><span data-stu-id="8d46b-116">Considerations for Chrome</span></span>

<span data-ttu-id="8d46b-117">Para usar S/MIME no Outlook na Web no navegador Google Chrome, você (ou outro administrador) deve definir e configurar a política do Chromium chamada **ExtensionInstallForcelist** para instalar a extensão S/MIME da Microsoft no Chrome.</span><span class="sxs-lookup"><span data-stu-id="8d46b-117">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="8d46b-118">O valor da política é `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="8d46b-118">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="8d46b-119">E observe que a aplicação dessa política exige computadores associados ao domínio, portanto, usar S/MIME no Chrome requer computadores associados ao domínio.</span><span class="sxs-lookup"><span data-stu-id="8d46b-119">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="8d46b-120">Para obter detalhes sobre a política **ExtensionInstallForcelist** , consulte [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span><span class="sxs-lookup"><span data-stu-id="8d46b-120">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="8d46b-121">Esta etapa é um pré-requisito para usar o Chrome; Ele não substitui o controle S/MIME instalado pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="8d46b-121">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="8d46b-122">Os usuários são solicitados a baixar e instalar o controle S/MIME no Outlook na Web durante o primeiro uso de S/MIME.</span><span class="sxs-lookup"><span data-stu-id="8d46b-122">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="8d46b-123">Ou, os usuários podem ir proativamente para o **S/MIME** em suas configurações do Outlook na Web para obter o link de download do controle.</span><span class="sxs-lookup"><span data-stu-id="8d46b-123">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="8d46b-124">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="8d46b-124">For more information</span></span>

[<span data-ttu-id="8d46b-125">S/MIME para assinatura e criptografia de mensagens</span><span class="sxs-lookup"><span data-stu-id="8d46b-125">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
