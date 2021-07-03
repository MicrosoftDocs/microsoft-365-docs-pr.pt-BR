---
title: Usar um código QR para entrar no Outlook móveis
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
description: Saiba como usar um código QR para autenticar e baixar Outlook celular.
ms.openlocfilehash: a403fbbed90229300e707653062c552104c47d97
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286700"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="b420c-103">Usar um código QR para entrar no Outlook móveis</span><span class="sxs-lookup"><span data-stu-id="b420c-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b420c-104">Esse recurso só está disponível para organizações que tenham a versão direcionada no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b420c-104">This feature is only available to organizations that have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="b420c-105">Para ativar a versão direcionada e saber mais sobre como ela funciona, consulte Configurar as opções de versão [Padrão ou Direcionada.](release-options-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="b420c-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="b420c-106">Vamos expandir para mais organizações nas próximas semanas por meio da visualização pública.</span><span class="sxs-lookup"><span data-stu-id="b420c-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="b420c-107">A visualização pública fornece acesso antecipado Microsoft 365 recursos.</span><span class="sxs-lookup"><span data-stu-id="b420c-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="b420c-108">Como administrador Microsoft 365, você pode permitir que seus usuários entrem no Outlook para Android ou aplicativo iOS em seus dispositivos móveis sem precisar inserir seu nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="b420c-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="b420c-109">Ao digitalizar um código QR, os usuários podem autenticar e entrar com segurança Outlook celular.</span><span class="sxs-lookup"><span data-stu-id="b420c-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="b420c-110">Em Outlook na Web ou em outros aplicativos de Outlook desktop, os usuários podem ver notificações informando que eles podem usar Outlook em seu dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="b420c-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="b420c-111">Essas notificações podem ser gerenciadas pelo administrador usando Exchange Powershell.</span><span class="sxs-lookup"><span data-stu-id="b420c-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="b420c-112">Se os usuários optarem por enviar uma mensagem de texto SMS para baixar o aplicativo em seu dispositivo móvel, um código QR aparecerá em seu computador.</span><span class="sxs-lookup"><span data-stu-id="b420c-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="b420c-113">Eles poderão examinar o código QR para fazer logoff Outlook telefone ou tablet.</span><span class="sxs-lookup"><span data-stu-id="b420c-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="b420c-114">Esse código QR é um token de vida curta que só pode ser resgatado uma vez.</span><span class="sxs-lookup"><span data-stu-id="b420c-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="b420c-115">Em alguns casos, os usuários devem se autenticar no computador para gerar o código QR.</span><span class="sxs-lookup"><span data-stu-id="b420c-115">In some cases, your users must re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="b420c-116">Usar Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="b420c-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="b420c-117">Esse recurso não está habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="b420c-117">This feature is on by default.</span></span> <span data-ttu-id="b420c-118">Para desabilitar esse recurso, siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="b420c-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="b420c-119">[Conexão para Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b420c-119">[Connect to Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
2. <span data-ttu-id="b420c-120">Usando o PowerShell, você pode desabilitar as notificações informando aos usuários sobre os aplicativos Outlook móveis.</span><span class="sxs-lookup"><span data-stu-id="b420c-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="b420c-121">Isso também impede que o fluxo de login do código QR seja mostrado.</span><span class="sxs-lookup"><span data-stu-id="b420c-121">This also prevents the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a><span data-ttu-id="b420c-122">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="b420c-122">Related content</span></span>

<span data-ttu-id="b420c-123">[Configurar as opções de versão Padrão](release-options-in-office-365.md) ou Direcionada (artigo)</span><span class="sxs-lookup"><span data-stu-id="b420c-123">[Set up the Standard or Targeted release options](release-options-in-office-365.md) (article)</span></span>\
<span data-ttu-id="b420c-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (artigo)</span><span class="sxs-lookup"><span data-stu-id="b420c-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (article)</span></span>