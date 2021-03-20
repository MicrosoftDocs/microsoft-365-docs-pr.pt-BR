---
title: Usar um código QR para entrar nos aplicativos móveis do Outlook
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: Saiba como usar um código QR para autenticar e baixar o Outlook Mobile.
ms.openlocfilehash: bc8ab14d3c1c0621e84d0c95ad7448c6c50825d6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914961"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="31c44-103">Usar um código QR para entrar nos aplicativos móveis do Outlook</span><span class="sxs-lookup"><span data-stu-id="31c44-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31c44-104">Esse recurso só está disponível para organizações que tenham a versão direcionada no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31c44-104">This feature is only available to organizations who have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="31c44-105">Para ativar a versão direcionada e saber mais sobre como ela funciona, consulte Configurar as opções de versão [Padrão ou Direcionada.](release-options-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="31c44-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="31c44-106">Vamos expandir para mais organizações nas próximas semanas por meio da visualização pública.</span><span class="sxs-lookup"><span data-stu-id="31c44-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="31c44-107">A visualização pública fornece acesso antecipado aos recursos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31c44-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="31c44-108">Como administrador do Microsoft 365, você pode permitir que seus usuários entrem no Outlook para Android ou aplicativo iOS em seus dispositivos móveis sem precisar inserir seu nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="31c44-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="31c44-109">Ao digitalizar um código QR, os usuários podem autenticar com segurança e entrar no Outlook mobile.</span><span class="sxs-lookup"><span data-stu-id="31c44-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="31c44-110">No Outlook na Web ou em outros aplicativos do Outlook da área de trabalho, os usuários podem ver notificações informando que podem usar o Outlook em seu dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="31c44-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="31c44-111">Essas notificações podem ser gerenciadas pelo administrador usando o Exchange Powershell.</span><span class="sxs-lookup"><span data-stu-id="31c44-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="31c44-112">Se os usuários optarem por enviar uma mensagem de texto SMS para baixar o aplicativo em seu dispositivo móvel, um código QR aparecerá em seu computador.</span><span class="sxs-lookup"><span data-stu-id="31c44-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="31c44-113">Eles poderão verificar o código QR para fazer logoff no Outlook em seu telefone ou tablet.</span><span class="sxs-lookup"><span data-stu-id="31c44-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="31c44-114">Esse código QR é um token de vida curta que só pode ser resgatado uma vez.</span><span class="sxs-lookup"><span data-stu-id="31c44-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="31c44-115">Em alguns casos, os usuários terão que se autenticar no computador para gerar o código QR.</span><span class="sxs-lookup"><span data-stu-id="31c44-115">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="31c44-116">Usar o Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="31c44-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="31c44-117">Esse recurso não está habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="31c44-117">This feature is on by default.</span></span> <span data-ttu-id="31c44-118">Para desabilitar esse recurso, siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="31c44-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="31c44-119">[Conecte-se ao Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="31c44-119">[Connect to Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="31c44-120">Usando o PowerShell, você pode desabilitar as notificações informando seus usuários sobre os aplicativos móveis do Outlook.</span><span class="sxs-lookup"><span data-stu-id="31c44-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="31c44-121">Isso também impedirá que o fluxo de login do código QR seja mostrado.</span><span class="sxs-lookup"><span data-stu-id="31c44-121">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="31c44-122">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="31c44-122">Related topics</span></span>

[<span data-ttu-id="31c44-123">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="31c44-123">Set-OrganizationConfig</span></span>](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)