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
ms.openlocfilehash: 2d62a49b93fa7bd5f2d747525de7244e8014e6a7
ms.sourcegitcommit: b8e9b2ecdc4927b67088c5fffb1585424c66fb10
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50050766"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="3e1a9-103">Usar um código QR para entrar nos aplicativos móveis do Outlook</span><span class="sxs-lookup"><span data-stu-id="3e1a9-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e1a9-104">Esse recurso do Microsoft 365 está na visualização pública.</span><span class="sxs-lookup"><span data-stu-id="3e1a9-104">This Microsoft 365 feature is in public preview.</span></span> <span data-ttu-id="3e1a9-105">A visualização pública fornece acesso antecipado aos recursos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3e1a9-105">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="3e1a9-106">Como administrador do Microsoft 365, você pode permitir que os usuários entrem no Outlook para Android ou no aplicativo iOS em seus dispositivos móveis sem precisar inserir o nome de usuário e a senha.</span><span class="sxs-lookup"><span data-stu-id="3e1a9-106">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="3e1a9-107">Ao digitalizar um código QR, os usuários podem autenticar com segurança e entrar no Outlook Mobile.</span><span class="sxs-lookup"><span data-stu-id="3e1a9-107">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="3e1a9-108">No Outlook na Web ou em outros aplicativos da área de trabalho do Outlook, os usuários podem ver notificações informando que podem usar o Outlook em seus dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="3e1a9-108">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="3e1a9-109">Essas notificações podem ser gerenciadas pelo administrador usando o Exchange Powershell.</span><span class="sxs-lookup"><span data-stu-id="3e1a9-109">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="3e1a9-110">Se os usuários optarem por enviar uma mensagem de texto SMS para baixar o aplicativo em seus dispositivos móveis, um código QR aparecerá em seus computadores.</span><span class="sxs-lookup"><span data-stu-id="3e1a9-110">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="3e1a9-111">Eles poderão verificar o código QR para fazer logoff no Outlook em seu telefone ou tablet.</span><span class="sxs-lookup"><span data-stu-id="3e1a9-111">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="3e1a9-112">Esse código QR é um token de curta duração que só pode ser resgatado uma vez.</span><span class="sxs-lookup"><span data-stu-id="3e1a9-112">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="3e1a9-113">Em alguns casos, os usuários terão que se autenticar outra vez em seus computadores para gerar o código QR.</span><span class="sxs-lookup"><span data-stu-id="3e1a9-113">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="3e1a9-114">Usar o Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e1a9-114">Use Exchange PowerShell</span></span>

<span data-ttu-id="3e1a9-115">Por padrão, essa experiência está 1.000.</span><span class="sxs-lookup"><span data-stu-id="3e1a9-115">This experience is on by default.</span></span> <span data-ttu-id="3e1a9-116">Para desabilitar esse recurso, siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="3e1a9-116">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="3e1a9-117">[Conecte-se ao Exchange PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="3e1a9-117">[Connect to Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="3e1a9-118">Usando o PowerShell, você pode desabilitar as notificações informando os usuários sobre os aplicativos móveis do Outlook.</span><span class="sxs-lookup"><span data-stu-id="3e1a9-118">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="3e1a9-119">Isso também impedirá que o fluxo de login do código QR seja mostrado.</span><span class="sxs-lookup"><span data-stu-id="3e1a9-119">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-Organization -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="3e1a9-120">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3e1a9-120">Related topics</span></span>

[<span data-ttu-id="3e1a9-121">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="3e1a9-121">Set-OrganizationConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)