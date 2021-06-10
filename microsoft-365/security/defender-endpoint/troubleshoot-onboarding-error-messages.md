---
title: Solucionar problemas de integração e mensagens de erro
description: Solucionar problemas de integração e mensagem de erro ao concluir a configuração do Microsoft Defender para Ponto de Extremidade.
keywords: solução de problemas, solução de Azure Active Directory, integração, mensagem de erro, mensagens de erro, microsoft defender para ponto de extremidade
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: b8e15f27ffe4babe730870fb576980c62cb0fd59
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844029"
---
# <a name="troubleshoot-subscription-and-portal-access-issues"></a><span data-ttu-id="f4eac-104">Solucionar problemas de assinatura e de acesso ao portal</span><span class="sxs-lookup"><span data-stu-id="f4eac-104">Troubleshoot subscription and portal access issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f4eac-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f4eac-105">**Applies to:**</span></span>
- [<span data-ttu-id="f4eac-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f4eac-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f4eac-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4eac-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f4eac-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="f4eac-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f4eac-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="f4eac-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troublshootonboarding-abovefoldlink)

<span data-ttu-id="f4eac-110">Esta página fornece etapas detalhadas para solucionar problemas que podem ocorrer ao configurar o serviço do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="f4eac-110">This page provides detailed steps to troubleshoot issues that might occur when setting up your Microsoft Defender for Endpoint service.</span></span>

<span data-ttu-id="f4eac-111">Se você receber uma mensagem de erro, Central de Segurança do Microsoft Defender fornecerá uma explicação detalhada sobre o problema e links relevantes serão fornecidos.</span><span class="sxs-lookup"><span data-stu-id="f4eac-111">If you receive an error message, Microsoft Defender Security Center will provide a detailed explanation on what the issue is and relevant links will be supplied.</span></span>

## <a name="no-subscriptions-found"></a><span data-ttu-id="f4eac-112">Nenhuma assinatura encontrada</span><span class="sxs-lookup"><span data-stu-id="f4eac-112">No subscriptions found</span></span>

<span data-ttu-id="f4eac-113">Se ao acessar Central de Segurança do Microsoft Defender você receber uma mensagem Sem **assinaturas encontradas,** isso significa que o Azure Active Directory (Azure AD) usado para fazer logoff no usuário no portal, não tem uma licença do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="f4eac-113">If while accessing Microsoft Defender Security Center you get a **No subscriptions found** message, it means the Azure Active Directory (Azure AD) used to log in the user to the portal, does not have a Microsoft Defender for Endpoint license.</span></span>

<span data-ttu-id="f4eac-114">Motivos potenciais:</span><span class="sxs-lookup"><span data-stu-id="f4eac-114">Potential reasons:</span></span>
- <span data-ttu-id="f4eac-115">As licenças do Windows E5 e do Office E5 são licenças separadas.</span><span class="sxs-lookup"><span data-stu-id="f4eac-115">The Windows E5 and Office E5 licenses are separate licenses.</span></span>
- <span data-ttu-id="f4eac-116">A licença foi comprada, mas não provisionada para esta instância do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f4eac-116">The license was purchased but not provisioned to this Azure AD instance.</span></span>
    - <span data-ttu-id="f4eac-117">Pode ser um problema de provisionamento de licença.</span><span class="sxs-lookup"><span data-stu-id="f4eac-117">It could be a license provisioning issue.</span></span>
    - <span data-ttu-id="f4eac-118">Pode ser que você provisionou inadvertidamente a licença para uma Microsoft Azure AD diferente da usada para autenticação no serviço.</span><span class="sxs-lookup"><span data-stu-id="f4eac-118">It could be you inadvertently provisioned the license to a different Microsoft Azure AD than the one used for authentication into the service.</span></span>

<span data-ttu-id="f4eac-119">Para ambos os casos, você deve entrar em contato com o suporte da Microsoft no [Suporte geral do Microsoft Defender para Endpoint ou](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) suporte a licença de [volume.](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx)</span><span class="sxs-lookup"><span data-stu-id="f4eac-119">For both cases, you should contact Microsoft support at [General Microsoft Defender for Endpoint Support](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) or [Volume license support](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx).</span></span>

![Imagem de nenhuma assinatura encontrada](images/atp-no-subscriptions-found.png)

## <a name="your-subscription-has-expired"></a><span data-ttu-id="f4eac-121">Sua assinatura expirou</span><span class="sxs-lookup"><span data-stu-id="f4eac-121">Your subscription has expired</span></span>

<span data-ttu-id="f4eac-122">Se ao acessar Central de Segurança do Microsoft Defender você receber **uma** mensagem Sua assinatura expirou, sua assinatura de serviço online expirou.</span><span class="sxs-lookup"><span data-stu-id="f4eac-122">If while accessing Microsoft Defender Security Center you get a **Your subscription has expired** message, your online service subscription has expired.</span></span> <span data-ttu-id="f4eac-123">A assinatura do Microsoft Defender para Ponto de Extremidade, como qualquer outra assinatura de serviço online, tem uma data de expiração.</span><span class="sxs-lookup"><span data-stu-id="f4eac-123">Microsoft Defender for Endpoint subscription, like any other online service subscription, has an expiration date.</span></span> 

<span data-ttu-id="f4eac-124">Você pode optar por renovar ou estender a licença a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="f4eac-124">You can choose to renew or extend the license at any point in time.</span></span> <span data-ttu-id="f4eac-125">Ao acessar o portal após **a** data de expiração, uma mensagem sua assinatura expirada será apresentada com uma opção para baixar o pacote de descarregamento do dispositivo, caso você opte por não renovar a licença.</span><span class="sxs-lookup"><span data-stu-id="f4eac-125">When accessing the portal after the expiration date a **Your subscription has expired** message will be presented with an option to download the device offboarding package, should you choose to not renew the license.</span></span>

> [!NOTE]
> <span data-ttu-id="f4eac-126">Por motivos de segurança, o pacote usado para dispositivos offboard expirará 30 dias após a data em que foi baixado.</span><span class="sxs-lookup"><span data-stu-id="f4eac-126">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="f4eac-127">Os pacotes de offboard expirados enviados para um dispositivo serão rejeitados.</span><span class="sxs-lookup"><span data-stu-id="f4eac-127">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="f4eac-128">Ao baixar um pacote de offboard, você será notificado sobre a data de expiração dos pacotes e ele também será incluído no nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="f4eac-128">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

![Imagem da assinatura expirada](images/atp-subscription-expired.png)

## <a name="you-are-not-authorized-to-access-the-portal"></a><span data-ttu-id="f4eac-130">Você não está autorizado a acessar o portal</span><span class="sxs-lookup"><span data-stu-id="f4eac-130">You are not authorized to access the portal</span></span>

<span data-ttu-id="f4eac-131">Se você receber um Você não está autorizado a acessar o **portal**, esteja ciente de que o Microsoft Defender for Endpoint é um produto de monitoramento de segurança, investigação e resposta de incidentes e, como tal, o acesso a ele é restrito e controlado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="f4eac-131">If you receive a **You are not authorized to access the portal**, be aware that Microsoft Defender for Endpoint is a security monitoring, incident investigation and response product, and as such, access to it is restricted and controlled by the user.</span></span>
<span data-ttu-id="f4eac-132">Para obter mais informações, consulte Assign [**user access to the portal**](/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="f4eac-132">For more information, see, [**Assign user access to the portal**](/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection).</span></span>

![Imagem de não autorizado a acessar portal](images/atp-not-authorized-to-access-portal.png)

## <a name="data-currently-isnt-available-on-some-sections-of-the-portal"></a><span data-ttu-id="f4eac-134">Os dados atualmente não estão disponíveis em algumas seções do portal</span><span class="sxs-lookup"><span data-stu-id="f4eac-134">Data currently isn't available on some sections of the portal</span></span>
<span data-ttu-id="f4eac-135">Se o painel do portal e outras seções mostrarem uma mensagem de erro como "Os dados no momento não estão disponíveis":</span><span class="sxs-lookup"><span data-stu-id="f4eac-135">If the portal dashboard and other sections show an error message such as "Data currently isn't available":</span></span>

![A imagem dos dados no momento não está disponível](images/atp-data-not-available.png)

<span data-ttu-id="f4eac-137">Você precisará permitir e todos os `securitycenter.windows.com` subdomas abaixo dele.</span><span class="sxs-lookup"><span data-stu-id="f4eac-137">You'll need to allow the `securitycenter.windows.com` and all subdomains under it.</span></span> <span data-ttu-id="f4eac-138">Por exemplo, `*.securitycenter.windows.com`.</span><span class="sxs-lookup"><span data-stu-id="f4eac-138">For example, `*.securitycenter.windows.com`.</span></span>


## <a name="portal-communication-issues"></a><span data-ttu-id="f4eac-139">Problemas de comunicação do portal</span><span class="sxs-lookup"><span data-stu-id="f4eac-139">Portal communication issues</span></span>
<span data-ttu-id="f4eac-140">Se você encontrar problemas ao acessar o portal, dados ausentes ou acesso restrito a partes do portal, você precisará verificar se as URLs a seguir são permitidas e abertas para comunicação.</span><span class="sxs-lookup"><span data-stu-id="f4eac-140">If you encounter issues with accessing the portal, missing data, or restricted access to portions of the portal, you'll need to verify that the following URLs are allowed and open for communication.</span></span>

- `*.blob.core.windows.net`
- `crl.microsoft.com`
- `https://*.microsoftonline-p.com`
- `https://*.securitycenter.windows.com` 
- `https://automatediracs-eus-prd.securitycenter.windows.com`
- `https://login.microsoftonline.com`
- `https://login.windows.net`
- `https://onboardingpackagescusprd.blob.core.windows.net`
- `https://secure.aadcdn.microsoftonline-p.com` 
- `https://securitycenter.windows.com` 
- `https://static2.sharepointonline.com` 



