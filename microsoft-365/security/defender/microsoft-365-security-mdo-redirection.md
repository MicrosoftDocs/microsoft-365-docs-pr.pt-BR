---
title: Redirecionando contas do Office 365 De segurança e conformidade para o novo Microsoft 365 Defender
description: Como redirecionar do Defender para Office 365 para Microsoft 365 Defender.
keywords: Microsoft 365 Defender, Iniciando o Microsoft 365 Defender, redirecionamento do centro de segurança
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
ms.openlocfilehash: f13e8235eb5f70e2d851b9b8b7600913d4e4023f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842513"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a><span data-ttu-id="461a6-104">Redirecionando contas do Office 365 De segurança e conformidade para o Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="461a6-104">Redirecting accounts from Office 365 Security and Compliance Center to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="461a6-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="461a6-105">**Applies to:**</span></span>

- <span data-ttu-id="461a6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="461a6-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="461a6-107">O que é o Defender para Office 365?</span><span class="sxs-lookup"><span data-stu-id="461a6-107">Defender for Office 365</span></span>

<span data-ttu-id="461a6-108">Este artigo explica como rotear contas para o Microsoft 365 Defender habilitando o redirecionamento automático do antigo Centro de Conformidade e Segurança do Office 365 (protection.office.com) para o Microsoft 365 Defender (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="461a6-108">This article explains how to route accounts to Microsoft 365 Defender by enabling automatic redirection from the former Office 365 Security and Compliance Center (protection.office.com), to Microsoft 365 Defender (security.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="461a6-109">O que esperar</span><span class="sxs-lookup"><span data-stu-id="461a6-109">What to expect</span></span>
<span data-ttu-id="461a6-110">Depois que o redirecionamento automático for habilitado e ativo, os usuários que acessarem os recursos relacionados à segurança no Office 365 Security and Compliance (protection.office.com), serão automaticamente roteados para o Microsoft 365 Defender ( https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="461a6-110">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to Microsoft 365 Defender (https://security.microsoft.com).</span></span>  

<span data-ttu-id="461a6-111">Saiba mais sobre o que mudou: [Microsoft Defender para Office 365 no Microsoft 365 Defender](microsoft-365-security-center-mdo.md).</span><span class="sxs-lookup"><span data-stu-id="461a6-111">Learn more about what’s changed: [Microsoft Defender for Office 365 in Microsoft 365 Defender](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="461a6-112">Com o redirecionamento automático ligado, os usuários serão roteados para o Microsoft 365 Defender quando usarem recursos de segurança no Centro de Conformidade e Segurança Office 365.</span><span class="sxs-lookup"><span data-stu-id="461a6-112">With automatic redirection turned on, users will be routed to Microsoft 365 Defender when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="461a6-113">Eles incluem recursos na seção Gerenciamento de Ameaças e no painel e relatórios de Gerenciamento de Ameaças.</span><span class="sxs-lookup"><span data-stu-id="461a6-113">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="461a6-114">Os itens no centro Office 365 segurança e conformidade que não estão relacionados à segurança não são redirecionados para o Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="461a6-114">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to Microsoft 365 Defender.</span></span>

<span data-ttu-id="461a6-115">Os itens relacionados à conformidade podem ser encontrados no centro de conformidade do Microsoft 365, e os itens relacionados ao fluxo de emails podem ser encontrados no centro de administração Exchange de email.</span><span class="sxs-lookup"><span data-stu-id="461a6-115">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="461a6-116">Todos os outros recursos, sejam eles relacionados à conformidade ou aos recursos que atendem a ambos, não são afetados pelo redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="461a6-116">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="461a6-117">Office 365 alertas de segurança aparecem no Microsoft 365 Defender e no centro Office 365 Segurança e Conformidade, sem redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="461a6-117">Office 365 security alerts appear in both Microsoft 365 Defender and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="461a6-118">Configurar redirecionamento de portal</span><span class="sxs-lookup"><span data-stu-id="461a6-118">Set up portal redirection</span></span>
<span data-ttu-id="461a6-119">Para iniciar o roteamento de contas Microsoft 365 Defender em security.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="461a6-119">To start routing accounts to Microsoft 365 Defender at security.microsoft.com:</span></span>

1. <span data-ttu-id="461a6-120">Certifique-se de ser um administrador global ou ter permissões de administrador de segurança no Azure Active directory.</span><span class="sxs-lookup"><span data-stu-id="461a6-120">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="461a6-121">[Entre no](https://security.microsoft.com/) Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="461a6-121">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender.</span></span>
3. <span data-ttu-id="461a6-122">Navegue **até Configurações** Email &  >  **portal** de colaboração  >  **redirecionamento**.</span><span class="sxs-lookup"><span data-stu-id="461a6-122">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="461a6-123">Alterne a configuração de redirecionamento automático para **On**.</span><span class="sxs-lookup"><span data-stu-id="461a6-123">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="461a6-124">Clique **em Habilitar** para aplicar redirecionamento automático ao Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="461a6-124">Click **Enable** to apply automatic redirection to Microsoft 365 Defender.</span></span>

> [!NOTE]
> <span data-ttu-id="461a6-125">Depois que o redirecionamento estiver habilitado, as contas em sessões ativas enquanto essa configuração for aplicada não serão ejetadas de suas sessões e serão roteadas somente para o Microsoft 365 Defender depois de encerrar a sessão atual e entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="461a6-125">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to Microsoft 365 Defender after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="461a6-126">Posso voltar a usar o portal anterior?</span><span class="sxs-lookup"><span data-stu-id="461a6-126">Can I go back to using the former portal?</span></span>
<span data-ttu-id="461a6-127">Se algo não estiver funcionando para você ou se houver algo que você não consiga concluir por meio do Microsoft 365 Defender, queremos ouvir sobre isso usando a opção de feedback do portal.</span><span class="sxs-lookup"><span data-stu-id="461a6-127">If something isn’t working for you or if there’s anything you’re unable to complete through Microsoft 365 Defender, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="461a6-128">Se você tiver encontrado algum problema com redirecionamento, por favor, nos avise.</span><span class="sxs-lookup"><span data-stu-id="461a6-128">If you’ve encountered any issues with redirection, please let us know.</span></span>

<span data-ttu-id="461a6-129">Para reverter para o portal anterior:</span><span class="sxs-lookup"><span data-stu-id="461a6-129">To revert to the former portal:</span></span>

1. <span data-ttu-id="461a6-130">[Entre no](https://security.microsoft.com/) Microsoft 365 Defender como administrador global ou usando e conta com permissões de administrador de segurança no Azure Active directory.</span><span class="sxs-lookup"><span data-stu-id="461a6-130">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="461a6-131">Navegue **até Configurações** Email &  >  **portal** de colaboração  >  **redirecionamento**.</span><span class="sxs-lookup"><span data-stu-id="461a6-131">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>   

3. <span data-ttu-id="461a6-132">Alterne a configuração de redirecionamento automático para **Off**.</span><span class="sxs-lookup"><span data-stu-id="461a6-132">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="461a6-133">Clique **em Desabilitar** & comentários de compartilhamento quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="461a6-133">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="461a6-134">Essa configuração pode ser habilitada novamente a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="461a6-134">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="461a6-135">Depois de desabilitada, as contas não serão mais roteadas para security.microsoft.com, e você terá novamente acesso ao portal anterior — securitycenter.windows.com ou securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="461a6-135">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal—securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="461a6-136">Informações relacionadas</span><span class="sxs-lookup"><span data-stu-id="461a6-136">Related information</span></span>
- [<span data-ttu-id="461a6-137">Microsoft 365 Visão geral do Defender</span><span class="sxs-lookup"><span data-stu-id="461a6-137">Microsoft 365 Defender overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="461a6-138">Microsoft Defender para Ponto de Extremidade no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="461a6-138">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="461a6-139">A Microsoft oferece SIEM e XDR unificados para modernizar operações de segurança</span><span class="sxs-lookup"><span data-stu-id="461a6-139">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="461a6-140">Infográfico XDR versus SIEM</span><span class="sxs-lookup"><span data-stu-id="461a6-140">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="461a6-141">O Novo Defensor</span><span class="sxs-lookup"><span data-stu-id="461a6-141">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="461a6-142">Sobre Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="461a6-142">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="461a6-143">Portais de segurança e centros de administração da Microsoft</span><span class="sxs-lookup"><span data-stu-id="461a6-143">Microsoft security portals and admin centers</span></span>](portals.md)
