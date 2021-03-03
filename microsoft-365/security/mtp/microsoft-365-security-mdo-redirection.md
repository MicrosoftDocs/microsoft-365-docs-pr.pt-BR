---
title: Redirecionando contas do Microsoft Defender para o Office 365 para o novo centro de segurança do Microsoft 365
description: Como redirecionar do Defender para o Office 365 para o centro de segurança do Microsoft 365.
keywords: Centro de segurança do Microsoft 365, Iniciando o centro de segurança do Microsoft 365, redirecionamento do centro de segurança
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 30fa10e23fd6a0c92bd5a56c797d3b7ff5b4bfd6
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50416763"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a><span data-ttu-id="43f38-104">Redirecionando contas do Microsoft Defender para o Office 365 para o centro de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="43f38-104">Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="43f38-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="43f38-105">**Applies to:**</span></span>

- <span data-ttu-id="43f38-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43f38-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="43f38-107">O que é o Defender para Office 365?</span><span class="sxs-lookup"><span data-stu-id="43f38-107">Defender for Office 365</span></span>

<span data-ttu-id="43f38-108">Este artigo explica como rotear contas para o centro de segurança do Microsoft 365 habilitando o redirecionamento automático do antigo Centro de Conformidade e Segurança da Microsoft (protection.office.com ou securitycenter.microsoft.com), para o centro de segurança do Microsoft 365 (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="43f38-108">This article explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Security and Compliance Center (protection.office.com or securitycenter.microsoft.com), to the Microsoft 365 security center (security.microsoft.com).</span></span>

>[!NOTE]
> <span data-ttu-id="43f38-109">O recurso de redirecionamento de portal está disponível apenas para clientes do Office 365 E5 e do Microsoft Defender para Office P2</span><span class="sxs-lookup"><span data-stu-id="43f38-109">Portal redirection capability is available for Office 365 E5 and Microsoft Defender for Office P2 customers only</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="43f38-110">O que esperar</span><span class="sxs-lookup"><span data-stu-id="43f38-110">What to expect</span></span>
<span data-ttu-id="43f38-111">Depois que o redirecionamento automático for habilitado e ativo, os usuários que acessarem os recursos relacionados à segurança no Office 365 Security and Compliance (protection.office.com), serão automaticamente roteados para o centro de segurança do Microsoft 365 ( https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="43f38-111">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to the Microsoft 365 security center (https://security.microsoft.com).</span></span>  

<span data-ttu-id="43f38-112">Saiba mais sobre o que mudou: Microsoft Defender para Office 365 no centro de segurança [do Microsoft 365.](microsoft-365-security-center-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="43f38-112">Learn more about what’s changed: [Microsoft Defender for Office 365 in the Microsoft 365 security center](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="43f38-113">Com o redirecionamento automático ligado, os usuários serão roteados para o Centro de Segurança do Microsoft 365 quando usarem recursos de segurança no Centro de Conformidade e Segurança do Office 365.</span><span class="sxs-lookup"><span data-stu-id="43f38-113">With automatic redirection turned on, users will be routed to Microsoft 365 security center when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="43f38-114">Eles incluem recursos na seção Gerenciamento de Ameaças e no painel e relatórios de Gerenciamento de Ameaças.</span><span class="sxs-lookup"><span data-stu-id="43f38-114">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="43f38-115">Itens no Centro de Conformidade e Segurança do Office 365 que não estão relacionados à segurança não são redirecionados para o centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="43f38-115">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to the Microsoft 365 security center.</span></span>

<span data-ttu-id="43f38-116">Os itens relacionados à conformidade podem ser encontrados no centro de conformidade do Microsoft 365 e os itens relacionados ao fluxo de emails podem ser encontrados no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="43f38-116">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="43f38-117">Todos os outros recursos, sejam eles relacionados à conformidade ou aos recursos que atendem a ambos, não são afetados pelo redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="43f38-117">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="43f38-118">Os alertas de segurança do Office 365 aparecem no Centro de segurança do Microsoft 365 e no Centro de Conformidade e Segurança do Office 365, sem redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="43f38-118">Office 365 security alerts appear in both the Microsoft 365 security center and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="43f38-119">Configurar redirecionamento de portal</span><span class="sxs-lookup"><span data-stu-id="43f38-119">Set up portal redirection</span></span>
<span data-ttu-id="43f38-120">Para iniciar o roteamento de contas para o centro de segurança do Microsoft 365 em security.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="43f38-120">To start routing accounts to the Microsoft 365 security center at security.microsoft.com:</span></span>

1. <span data-ttu-id="43f38-121">Certifique-se de ser um administrador global ou ter permissões de administrador de segurança no Azure Active directory.</span><span class="sxs-lookup"><span data-stu-id="43f38-121">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="43f38-122">[Entre no](https://security.microsoft.com/) centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="43f38-122">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>
3. <span data-ttu-id="43f38-123">Navegue **até Configurações**  >  **Email &**  >  **redirecionamento do Portal de colaboração**.</span><span class="sxs-lookup"><span data-stu-id="43f38-123">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="43f38-124">Alterne a configuração de redirecionamento automático para **On**.</span><span class="sxs-lookup"><span data-stu-id="43f38-124">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="43f38-125">Clique **em Habilitar** para aplicar redirecionamento automático ao portal do Centro de Segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="43f38-125">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

> [!NOTE]
> <span data-ttu-id="43f38-126">Depois que o redirecionamento estiver habilitado, as contas em sessões ativas enquanto essa configuração for aplicada não serão ejetadas de suas sessões e serão roteadas apenas para o centro de segurança do Microsoft 365 depois de encerrar a sessão atual e entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="43f38-126">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="43f38-127">Posso voltar a usar o portal anterior?</span><span class="sxs-lookup"><span data-stu-id="43f38-127">Can I go back to using the former portal?</span></span>
<span data-ttu-id="43f38-128">Se algo não estiver funcionando para você ou se houver algo que você não consiga concluir por meio do portal do Centro de Segurança do Microsoft 365, queremos ouvir sobre isso usando a opção comentários do portal.</span><span class="sxs-lookup"><span data-stu-id="43f38-128">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="43f38-129">Se você tiver encontrado algum problema com redirecionamento, recomendamos que você entre em contato com seu parceiro de PM diretamente por meio da visualização privada ou nos avise por meio do formulário De envio de comentários.</span><span class="sxs-lookup"><span data-stu-id="43f38-129">If you’ve encountered any issues with redirection, we encourage you to reach out to your PM buddy directly through private preview or let us know via the Give feedback submission form.</span></span>

<span data-ttu-id="43f38-130">Para reverter para o portal anterior:</span><span class="sxs-lookup"><span data-stu-id="43f38-130">To revert to the former portal:</span></span>

1. <span data-ttu-id="43f38-131">[Entre no](https://security.microsoft.com/) centro de segurança do Microsoft 365 como administrador global ou usando e conta com permissões de administrador de segurança no Azure Active directory.</span><span class="sxs-lookup"><span data-stu-id="43f38-131">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="43f38-132">Navegue **até Configurações**  >  **Endpoints**  >  **Redirecionamento**  >  **geral do Portal**.</span><span class="sxs-lookup"><span data-stu-id="43f38-132">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection**.</span></span>  

3. <span data-ttu-id="43f38-133">Alterne a configuração de redirecionamento automático para **Off**.</span><span class="sxs-lookup"><span data-stu-id="43f38-133">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="43f38-134">Clique **em Desabilitar** & comentários de compartilhamento quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="43f38-134">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="43f38-135">Essa configuração pode ser habilitada novamente a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="43f38-135">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="43f38-136">Depois de desabilitada, as contas não serão mais roteadas para security.microsoft.com, e você terá novamente acesso ao portal anterior - securitycenter.windows.com ou securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="43f38-136">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="43f38-137">Informações relacionadas</span><span class="sxs-lookup"><span data-stu-id="43f38-137">Related information</span></span>
- [<span data-ttu-id="43f38-138">Visão geral do Centro de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="43f38-138">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="43f38-139">Microsoft Defender para Ponto de Extremidade no centro de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="43f38-139">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="43f38-140">A Microsoft oferece SIEM e XDR unificados para modernizar operações de segurança</span><span class="sxs-lookup"><span data-stu-id="43f38-140">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="43f38-141">Infográfico XDR versus SIEM</span><span class="sxs-lookup"><span data-stu-id="43f38-141">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="43f38-142">O Novo Defensor</span><span class="sxs-lookup"><span data-stu-id="43f38-142">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="43f38-143">Sobre o Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43f38-143">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="43f38-144">Portais de segurança e centros de administração da Microsoft</span><span class="sxs-lookup"><span data-stu-id="43f38-144">Microsoft security portals and admin centers</span></span>](portals.md)