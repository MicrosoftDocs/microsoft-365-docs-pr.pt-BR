---
title: Redirecionando contas do Microsoft Defender para Office 365 para o novo Microsoft 365 de segurança
description: Como redirecionar do Defender para Office 365 para o Microsoft 365 de segurança.
keywords: Microsoft 365 de segurança, Iniciando com o centro de segurança Microsoft 365, redirecionamento do centro de segurança
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 2a4b122b3ef3a1ddaf61d8f9373bec3e721db177
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651375"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a><span data-ttu-id="6092a-104">Redirecionando contas do Microsoft Defender para Office 365 para o Microsoft 365 de segurança</span><span class="sxs-lookup"><span data-stu-id="6092a-104">Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6092a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6092a-105">**Applies to:**</span></span>

- <span data-ttu-id="6092a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6092a-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="6092a-107">Microsoft Defender para Office 365?</span><span class="sxs-lookup"><span data-stu-id="6092a-107">Defender for Office 365</span></span>

<span data-ttu-id="6092a-108">Este artigo explica como rotear contas para o centro de segurança do Microsoft 365 habilitando o redirecionamento automático do antigo Centro de Conformidade e Segurança da Microsoft (protection.office.com ou securitycenter.microsoft.com), para o centro de segurança Microsoft 365 (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="6092a-108">This article explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Security and Compliance Center (protection.office.com or securitycenter.microsoft.com), to the Microsoft 365 security center (security.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="6092a-109">O que esperar</span><span class="sxs-lookup"><span data-stu-id="6092a-109">What to expect</span></span>
<span data-ttu-id="6092a-110">Depois que o redirecionamento automático for habilitado e ativo, os usuários que acessarem os recursos relacionados à segurança no Office 365 Security and Compliance (protection.office.com), serão automaticamente roteados para o centro de segurança do Microsoft 365 ( https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="6092a-110">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to the Microsoft 365 security center (https://security.microsoft.com).</span></span>  

<span data-ttu-id="6092a-111">Saiba mais sobre o que mudou: [o Microsoft Defender para Office 365 no centro Microsoft 365 segurança.](microsoft-365-security-center-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="6092a-111">Learn more about what’s changed: [Microsoft Defender for Office 365 in the Microsoft 365 security center](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="6092a-112">Com o redirecionamento automático ligado, os usuários serão roteados para o centro de segurança Microsoft 365 quando usarem recursos de segurança no Centro de Conformidade e Segurança Office 365.</span><span class="sxs-lookup"><span data-stu-id="6092a-112">With automatic redirection turned on, users will be routed to Microsoft 365 security center when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="6092a-113">Eles incluem recursos na seção Gerenciamento de Ameaças e no painel e relatórios de Gerenciamento de Ameaças.</span><span class="sxs-lookup"><span data-stu-id="6092a-113">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="6092a-114">Os itens no centro Office 365 segurança e conformidade que não estão relacionados à segurança não são redirecionados para o Microsoft 365 de segurança.</span><span class="sxs-lookup"><span data-stu-id="6092a-114">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to the Microsoft 365 security center.</span></span>

<span data-ttu-id="6092a-115">Os itens relacionados à conformidade podem ser encontrados no centro de conformidade do Microsoft 365, e os itens relacionados ao fluxo de emails podem ser encontrados no centro de administração Exchange de email.</span><span class="sxs-lookup"><span data-stu-id="6092a-115">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="6092a-116">Todos os outros recursos, sejam eles relacionados à conformidade ou aos recursos que atendem a ambos, não são afetados pelo redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="6092a-116">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="6092a-117">Office 365 alertas de segurança aparecem no centro de segurança Microsoft 365 e no centro Office 365 Segurança e Conformidade, sem redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="6092a-117">Office 365 security alerts appear in both the Microsoft 365 security center and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="6092a-118">Configurar redirecionamento de portal</span><span class="sxs-lookup"><span data-stu-id="6092a-118">Set up portal redirection</span></span>
<span data-ttu-id="6092a-119">Para iniciar o roteamento de contas para o Microsoft 365 de segurança em security.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="6092a-119">To start routing accounts to the Microsoft 365 security center at security.microsoft.com:</span></span>

1. <span data-ttu-id="6092a-120">Certifique-se de ser um administrador global ou ter permissões de administrador de segurança no Azure Active directory.</span><span class="sxs-lookup"><span data-stu-id="6092a-120">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="6092a-121">[Entre no](https://security.microsoft.com/) centro de Microsoft 365 segurança.</span><span class="sxs-lookup"><span data-stu-id="6092a-121">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>
3. <span data-ttu-id="6092a-122">Navegue **até Configurações** Email &  >  **portal** de colaboração  >  **redirecionamento**.</span><span class="sxs-lookup"><span data-stu-id="6092a-122">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="6092a-123">Alterne a configuração de redirecionamento automático para **On**.</span><span class="sxs-lookup"><span data-stu-id="6092a-123">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="6092a-124">Clique **em Habilitar** para aplicar redirecionamento automático ao portal Microsoft 365 central de segurança.</span><span class="sxs-lookup"><span data-stu-id="6092a-124">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

> [!NOTE]
> <span data-ttu-id="6092a-125">Depois que o redirecionamento estiver habilitado, as contas em sessões ativas enquanto essa configuração for aplicada não serão ejetadas de suas sessões e serão roteadas apenas para o centro de segurança do Microsoft 365 depois de encerrar a sessão atual e entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="6092a-125">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="6092a-126">Posso voltar a usar o portal anterior?</span><span class="sxs-lookup"><span data-stu-id="6092a-126">Can I go back to using the former portal?</span></span>
<span data-ttu-id="6092a-127">Se algo não estiver funcionando para você ou se houver algo que você não consiga concluir por meio do portal do centro de segurança do Microsoft 365, queremos ouvir sobre isso usando a opção comentários do portal.</span><span class="sxs-lookup"><span data-stu-id="6092a-127">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="6092a-128">Se você tiver encontrado algum problema com redirecionamento, por favor, nos avise.</span><span class="sxs-lookup"><span data-stu-id="6092a-128">If you’ve encountered any issues with redirection, please let us know.</span></span>

<span data-ttu-id="6092a-129">Para reverter para o portal anterior:</span><span class="sxs-lookup"><span data-stu-id="6092a-129">To revert to the former portal:</span></span>

1. <span data-ttu-id="6092a-130">[Entre no](https://security.microsoft.com/) centro de segurança Microsoft 365 como administrador global ou usando e conta com permissões de administrador de segurança no Azure Active directory.</span><span class="sxs-lookup"><span data-stu-id="6092a-130">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="6092a-131">Navegue **até Configurações** Email &  >  **portal** de colaboração  >  **redirecionamento**.</span><span class="sxs-lookup"><span data-stu-id="6092a-131">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>   

3. <span data-ttu-id="6092a-132">Alterne a configuração de redirecionamento automático para **Off**.</span><span class="sxs-lookup"><span data-stu-id="6092a-132">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="6092a-133">Clique **em Desabilitar** & comentários de compartilhamento quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="6092a-133">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="6092a-134">Essa configuração pode ser habilitada novamente a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="6092a-134">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="6092a-135">Depois de desabilitada, as contas não serão mais roteadas para security.microsoft.com, e você terá novamente acesso ao portal anterior - securitycenter.windows.com ou securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="6092a-135">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="6092a-136">Informações relacionadas</span><span class="sxs-lookup"><span data-stu-id="6092a-136">Related information</span></span>
- [<span data-ttu-id="6092a-137">Visão geral do Centro de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6092a-137">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="6092a-138">Microsoft Defender para Ponto de Extremidade no centro de Microsoft 365 de segurança</span><span class="sxs-lookup"><span data-stu-id="6092a-138">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="6092a-139">A Microsoft oferece SIEM e XDR unificados para modernizar operações de segurança</span><span class="sxs-lookup"><span data-stu-id="6092a-139">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="6092a-140">Infográfico XDR versus SIEM</span><span class="sxs-lookup"><span data-stu-id="6092a-140">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="6092a-141">O Novo Defensor</span><span class="sxs-lookup"><span data-stu-id="6092a-141">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="6092a-142">Sobre Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6092a-142">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="6092a-143">Portais de segurança e centros de administração da Microsoft</span><span class="sxs-lookup"><span data-stu-id="6092a-143">Microsoft security portals and admin centers</span></span>](portals.md)
