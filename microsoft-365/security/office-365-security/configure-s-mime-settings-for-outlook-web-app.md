---
title: Definir configurações de S/MIME - Exchange Online para Outlook na Web
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Uma breve descrição do que os administradores do Exchange Online precisam fazer para exibir e definir as configurações S/MIME no Outlook na Web no Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ccadfc46e42713601b115c18a119e48dcfdcbf4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290028"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="ad701-103">Definir configurações de S/MIME no Exchange Online para Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="ad701-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ad701-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="ad701-104">**Applies to**</span></span>
- [<span data-ttu-id="ad701-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ad701-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ad701-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="ad701-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ad701-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad701-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="ad701-108">Como administrador do Exchange Online, você pode configurar o Outlook na Web (anteriormente conhecido como Outlook Web App) para permitir o envio e o recebimento de mensagens protegidas por S/MIME.</span><span class="sxs-lookup"><span data-stu-id="ad701-108">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="ad701-109">Use os cmdlets **Get-SmimeConfig** e **Set-SmimeConfig** para exibir e gerenciar esse recurso no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ad701-109">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="ad701-110">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ad701-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="ad701-111">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) e [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="ad701-111">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="ad701-112">Considerações para o novo Microsoft Edge (baseado no Chromium)</span><span class="sxs-lookup"><span data-stu-id="ad701-112">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="ad701-113">Para usar S/MIME no Outlook na Web no novo navegador da Web [Microsoft Edge,](https://www.microsoft.com/windows/microsoft-edge) você (ou outro administrador) deve definir e configurar a política de navegador do Microsoft Edge chamada **ExtensionInstallForcelist** para instalar a extensão S/MIME da Microsoft no novo Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="ad701-113">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="ad701-114">O valor da política é `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="ad701-114">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="ad701-115">E observe que a aplicação dessa política requer dispositivos ingressados no domínio ou ingressados no Azure AD, portanto, o uso de S/MIME no novo navegador Microsoft Edge requer efetivamente dispositivos ingressados no domínio ou ingressados no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ad701-115">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="ad701-116">Para obter detalhes sobre a **política ExtensionInstallForcelist,** consulte [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span><span class="sxs-lookup"><span data-stu-id="ad701-116">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="ad701-117">Esta etapa é um pré-requisito para usar o novo Microsoft Edge; não substitui o controle S/MIME instalado pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="ad701-117">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="ad701-118">Os usuários são solicitados a baixar e instalar o controle S/MIME no Outlook na Web durante seu primeiro uso de S/MIME.</span><span class="sxs-lookup"><span data-stu-id="ad701-118">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="ad701-119">Ou os usuários podem ir proativamente para **S/MIME** em suas configurações do Outlook na Web para obter o link de download do controle.</span><span class="sxs-lookup"><span data-stu-id="ad701-119">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="ad701-120">Considerações para o Chrome</span><span class="sxs-lookup"><span data-stu-id="ad701-120">Considerations for Chrome</span></span>

<span data-ttu-id="ad701-121">Para usar S/MIME no Outlook na Web no navegador da Web Google Chrome, você (ou outro administrador) deve definir e configurar a política do Chromium chamada **ExtensionInstallForcelist** para instalar a extensão Microsoft S/MIME no Chrome.</span><span class="sxs-lookup"><span data-stu-id="ad701-121">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="ad701-122">O valor da política é `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="ad701-122">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="ad701-123">E observe que a aplicação dessa política requer computadores ingressados no domínio, portanto, usar S/MIME no Chrome efetivamente requer computadores ingressados no domínio.</span><span class="sxs-lookup"><span data-stu-id="ad701-123">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="ad701-124">Para obter detalhes sobre a **política ExtensionInstallForcelist,** consulte [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span><span class="sxs-lookup"><span data-stu-id="ad701-124">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="ad701-125">Esta etapa é um pré-requisito para usar o Chrome; não substitui o controle S/MIME instalado pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="ad701-125">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="ad701-126">Os usuários são solicitados a baixar e instalar o controle S/MIME no Outlook na Web durante seu primeiro uso de S/MIME.</span><span class="sxs-lookup"><span data-stu-id="ad701-126">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="ad701-127">Ou os usuários podem ir proativamente para **S/MIME** em suas configurações do Outlook na Web para obter o link de download do controle.</span><span class="sxs-lookup"><span data-stu-id="ad701-127">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="ad701-128">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="ad701-128">For more information</span></span>

[<span data-ttu-id="ad701-129">S/MIME para assinatura e criptografia de mensagens</span><span class="sxs-lookup"><span data-stu-id="ad701-129">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
