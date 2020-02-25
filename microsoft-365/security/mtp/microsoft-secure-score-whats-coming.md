---
title: O que está acontecendo na pontuação segura da Microsoft?
description: Descreve a pontuação segura da Microsoft na central de segurança do Microsoft 365, como os detalhes são calculados e quais administradores de segurança podem esperar.
keywords: segurança, malware, Microsoft 365, M365, Pontuação segura, central de segurança, ações de melhoria
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 55c7cb34c5484eaf8f6693be0ce439e33a82550f
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266959"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="773fe-104">O que está acontecendo na pontuação segura da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="773fe-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="773fe-105">Para tornar a pontuação segura da Microsoft um melhor representante da postura de segurança e melhorar a usabilidade, estamos fazendo algumas alterações em um futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="773fe-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="773fe-106">Sua pontuação e a pontuação máxima possível mudarão.</span><span class="sxs-lookup"><span data-stu-id="773fe-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="773fe-107">No entanto, isso não implica uma alteração na postura de segurança.</span><span class="sxs-lookup"><span data-stu-id="773fe-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="773fe-108">Para saber mais sobre as alterações recentes, confira [o que há de novo na pontuação segura da Microsoft?](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="773fe-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-2nd-2020"></a><span data-ttu-id="773fe-109">2 de março de 2020</span><span class="sxs-lookup"><span data-stu-id="773fe-109">March 2nd 2020</span></span>

### <a name="removing-improvement-actions-from-intune"></a><span data-ttu-id="773fe-110">Removendo ações de melhoria do Intune</span><span class="sxs-lookup"><span data-stu-id="773fe-110">Removing improvement actions from Intune</span></span>

<span data-ttu-id="773fe-111">Após uma avaliação das ações de melhoria de Pontuação segura da Microsoft fornecidas pelo Intune, foi decidido que eles não oferecem uma representação útil da postura de segurança dos dispositivos nas organizações.</span><span class="sxs-lookup"><span data-stu-id="773fe-111">After an evaluation of the Microsoft Secure Score improvement actions supplied from Intune, it was decided that they do not provide a useful representation of the security posture of devices in organizations.</span></span> <span data-ttu-id="773fe-112">Em vez de se concentrar em políticas, estamos trabalhando para trazer os controles de segurança que avaliam diretamente o estado de configuração dos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="773fe-112">Instead of focusing on policies, we are working to bring in security controls that directly assess the configuration state of the devices.</span></span>

<span data-ttu-id="773fe-113">As seguintes ações de aprimoramento do Intune serão removidas:</span><span class="sxs-lookup"><span data-stu-id="773fe-113">The following Intune improvement actions will be removed:</span></span>

- <span data-ttu-id="773fe-114">Habilitar o gerenciamento de dispositivos móveis do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="773fe-114">Enable Microsoft Intune Mobile Device Management</span></span>
- <span data-ttu-id="773fe-115">Criar uma política de conformidade do Microsoft Intune para Android</span><span class="sxs-lookup"><span data-stu-id="773fe-115">Create a Microsoft Intune Compliance Policy for Android</span></span>
- <span data-ttu-id="773fe-116">Criar uma política de conformidade do Microsoft Intune para Android para trabalho</span><span class="sxs-lookup"><span data-stu-id="773fe-116">Create a Microsoft Intune Compliance Policy for Android for Work</span></span>
- <span data-ttu-id="773fe-117">Criar uma política de proteção de aplicativos do Microsoft Intune para Android</span><span class="sxs-lookup"><span data-stu-id="773fe-117">Create a Microsoft Intune App Protection Policy for Android</span></span>
- <span data-ttu-id="773fe-118">Criar uma política de proteção de aplicativos do Microsoft Intune para iOS</span><span class="sxs-lookup"><span data-stu-id="773fe-118">Create a Microsoft Intune App Protection Policy for iOS</span></span>
- <span data-ttu-id="773fe-119">Marcar dispositivos sem política de conformidade do Microsoft Intune atribuída como não compatível</span><span class="sxs-lookup"><span data-stu-id="773fe-119">Mark devices with no Microsoft Intune Compliance Policy assigned as not compliant</span></span>
- <span data-ttu-id="773fe-120">Criar uma política de conformidade do Microsoft Intune para iOS</span><span class="sxs-lookup"><span data-stu-id="773fe-120">Create a Microsoft Intune Compliance Policy for iOS</span></span>
- <span data-ttu-id="773fe-121">Criar uma política de conformidade do Microsoft Intune para o macOS</span><span class="sxs-lookup"><span data-stu-id="773fe-121">Create a Microsoft Intune Compliance Policy for macOS</span></span>
- <span data-ttu-id="773fe-122">Criar uma política de conformidade do Microsoft Intune para o Windows</span><span class="sxs-lookup"><span data-stu-id="773fe-122">Create a Microsoft Intune Compliance Policy for Windows</span></span>
- <span data-ttu-id="773fe-123">Criar um perfil de configuração do Microsoft Intune para Android</span><span class="sxs-lookup"><span data-stu-id="773fe-123">Create a Microsoft Intune Configuration Profile for Android</span></span>
- <span data-ttu-id="773fe-124">Criar um perfil de configuração do Microsoft Intune para Android para trabalho</span><span class="sxs-lookup"><span data-stu-id="773fe-124">Create a Microsoft Intune Configuration Profile for Android for Work</span></span>
- <span data-ttu-id="773fe-125">Criar um perfil de configuração do Microsoft Intune para o macOS</span><span class="sxs-lookup"><span data-stu-id="773fe-125">Create a Microsoft Intune Configuration Profile for macOS</span></span>
- <span data-ttu-id="773fe-126">Criar um perfil de configuração do Microsoft Intune para iOS</span><span class="sxs-lookup"><span data-stu-id="773fe-126">Create a Microsoft Intune Configuration Profile for iOS</span></span>
- <span data-ttu-id="773fe-127">Criar um perfil de configuração do Microsoft Intune para Windows</span><span class="sxs-lookup"><span data-stu-id="773fe-127">Create a Microsoft Intune Configuration Profile for Windows</span></span>
- <span data-ttu-id="773fe-128">Habilitar a detecção avançada do jailbreak no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="773fe-128">Enable enhanced jailbreak detection in Microsoft Intune</span></span>
- <span data-ttu-id="773fe-129">Exigir que todos os dispositivos sejam corrigidos, ter antivírus e firewalls habilitados</span><span class="sxs-lookup"><span data-stu-id="773fe-129">Require all devices to be patched, have anti-virus, and firewalls enabled</span></span>
- <span data-ttu-id="773fe-130">Habilitar a integração ATP do Windows Defender no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="773fe-130">Enable Windows Defender ATP integration into Microsoft Intune</span></span>
- <span data-ttu-id="773fe-131">Criar uma política de proteção de informações do Windows do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="773fe-131">Create a Microsoft Intune Windows Information Protection Policy</span></span>
- <span data-ttu-id="773fe-132">Exigir que todos os dispositivos tenham configurações de segurança avançadas</span><span class="sxs-lookup"><span data-stu-id="773fe-132">Require all devices to have advanced security configurations</span></span>
- <span data-ttu-id="773fe-133">Examinar o relatório de dispositivos bloqueados semanalmente</span><span class="sxs-lookup"><span data-stu-id="773fe-133">Review blocked devices report weekly</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="773fe-134">Removendo ações de melhoria que não atendem às expectativas de medição confiável</span><span class="sxs-lookup"><span data-stu-id="773fe-134">Removing improvement actions that don't meet expectations for reliable measurement</span></span>

<span data-ttu-id="773fe-135">Para garantir que a pontuação segura da Microsoft seja significativa e que cada ação de melhoria seja mensurável e confiável, estamos removendo as seguintes ações de aprimoramento.</span><span class="sxs-lookup"><span data-stu-id="773fe-135">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="773fe-136">Ativar a gravação de dados de auditoria</span><span class="sxs-lookup"><span data-stu-id="773fe-136">Turn on audit data recording</span></span>
- <span data-ttu-id="773fe-137">Descobrir aplicativos de ti de sombra arriscados e não compatíveis</span><span class="sxs-lookup"><span data-stu-id="773fe-137">Discover risky and non-compliant shadow IT applications</span></span>
- <span data-ttu-id="773fe-138">Examinar permissões & bloquear aplicativos OAuth arriscados conectados ao seu ambiente</span><span class="sxs-lookup"><span data-stu-id="773fe-138">Review permissions & block risky OAuth applications connected to your environment</span></span>
- <span data-ttu-id="773fe-139">Configurar o controle de versão em bibliotecas de documentos do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="773fe-139">Set up versioning on SharePoint online document libraries</span></span>

### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="773fe-140">Atualizações das ações de melhoria da MFA</span><span class="sxs-lookup"><span data-stu-id="773fe-140">MFA improvement action updates</span></span>

<span data-ttu-id="773fe-141">Para refletir a necessidade de que as empresas garantam o máximo de segurança durante a aplicação de políticas que funcionam com seus negócios, a pontuação segura da Microsoft é remover três ações de melhoria centralizada em relação à autenticação multifator e adição de dois.</span><span class="sxs-lookup"><span data-stu-id="773fe-141">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score is removing three improvement actions centered around multi-factor authentication, and adding two.</span></span>

<span data-ttu-id="773fe-142">Os três que serão removidos:</span><span class="sxs-lookup"><span data-stu-id="773fe-142">The three that will be removed:</span></span>

- <span data-ttu-id="773fe-143">Registrar todos os usuários para autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="773fe-143">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="773fe-144">Exigir MFA para todos os usuários</span><span class="sxs-lookup"><span data-stu-id="773fe-144">Require MFA for all users</span></span>
- <span data-ttu-id="773fe-145">Exigir MFA para funções privilegiadas do Azure AD</span><span class="sxs-lookup"><span data-stu-id="773fe-145">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="773fe-146">Novas ações de aprimoramento foram adicionadas:</span><span class="sxs-lookup"><span data-stu-id="773fe-146">New improvement actions added:</span></span>

- <span data-ttu-id="773fe-147">Garantir que todos os usuários possam concluir a autenticação multifator para acesso seguro</span><span class="sxs-lookup"><span data-stu-id="773fe-147">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="773fe-148">Exigir MFA para funções administrativas</span><span class="sxs-lookup"><span data-stu-id="773fe-148">Require MFA for administrative roles</span></span>

 <span data-ttu-id="773fe-149">Essas novas ações de melhoria exigirão o registro de seus usuários ou administradores para a autenticação multifator (MFA) em seu diretório e o estabelecimento do conjunto certo de políticas que atendam às suas necessidades organizacionais.</span><span class="sxs-lookup"><span data-stu-id="773fe-149">These new improvement actions will require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="773fe-150">O objetivo principal é ter flexibilidade enquanto garante que todos os seus usuários e administradores podem autenticar com vários fatores ou solicitações de verificação de identidade baseadas em risco.</span><span class="sxs-lookup"><span data-stu-id="773fe-150">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="773fe-151">Isso pode ter a forma de ter várias políticas que aplicam decisões com escopo ou definir padrões de segurança (chegando a 16 de março) que permitem que a Microsoft decida quando desafiar os usuários para a MFA.</span><span class="sxs-lookup"><span data-stu-id="773fe-151">That can take the form of having multiple policies that apply scoped decisions, or setting security defaults (coming March 16th) that let Microsoft decide when to challenge users for MFA.</span></span>

### <a name="removing-review-improvement-actions"></a><span data-ttu-id="773fe-152">Removendo ações de melhoria de "revisão"</span><span class="sxs-lookup"><span data-stu-id="773fe-152">Removing “review” improvement actions</span></span>

<span data-ttu-id="773fe-153">Um dos princípios de Pontuação segura é que a pontuação deve ser padronizada e fácil de se relacionar.</span><span class="sxs-lookup"><span data-stu-id="773fe-153">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="773fe-154">Ter ações de melhoria que não podem ser mensuráveis ou acionável está causando confusão.</span><span class="sxs-lookup"><span data-stu-id="773fe-154">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="773fe-155">Uma pontuação segura da Microsoft faz sentido quando cada recomendação pode ter um efeito claro na pontuação.</span><span class="sxs-lookup"><span data-stu-id="773fe-155">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="773fe-156">Revisar as ações de melhoria não são medidas para o mesmo padrão que outras ações de aprimoramento.</span><span class="sxs-lookup"><span data-stu-id="773fe-156">Review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="773fe-157">Por esses motivos, todas as ações de melhoria que exigiram uma cadência de revisão serão removidas temporariamente.</span><span class="sxs-lookup"><span data-stu-id="773fe-157">For these reasons, all improvement actions that required a review cadence will be temporarily removed.</span></span> <span data-ttu-id="773fe-158">Nenhuma ação é necessária em sua parte.</span><span class="sxs-lookup"><span data-stu-id="773fe-158">No action is needed on your part.</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="773fe-159">16 de março de 2020</span><span class="sxs-lookup"><span data-stu-id="773fe-159">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="773fe-160">Removendo ações de melhoria que não atendem às expectativas de medição confiável</span><span class="sxs-lookup"><span data-stu-id="773fe-160">Removing improvement actions that don't meet expectations for reliable measurement</span></span>

<span data-ttu-id="773fe-161">Para garantir que a pontuação segura da Microsoft seja significativa e que cada ação de melhoria seja mensurável e confiável, estamos removendo as seguintes ações de aprimoramento.</span><span class="sxs-lookup"><span data-stu-id="773fe-161">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="773fe-162">Armazenar documentos de usuário no OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="773fe-162">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="773fe-163">Configurar as políticas de anexo seguro do Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="773fe-163">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="773fe-164">Configurar links seguros do Office 365 para verificar URLs</span><span class="sxs-lookup"><span data-stu-id="773fe-164">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="773fe-165">Não permitir a delegação de caixa de correio</span><span class="sxs-lookup"><span data-stu-id="773fe-165">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="773fe-166">Permitir links de compartilhamento de convidados anônimos para sites e documentos</span><span class="sxs-lookup"><span data-stu-id="773fe-166">Allow anonymous guest sharing links for sites and docs</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="773fe-167">Padrões de segurança de suporte para ações de melhoria do Azure AD</span><span class="sxs-lookup"><span data-stu-id="773fe-167">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="773fe-168">A pontuação segura da Microsoft atualizará as ações de aperfeiçoamento para suportar os [padrões de segurança no Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), o que facilita a proteção da sua organização com configurações de segurança pré-configuradas para ataques comuns.</span><span class="sxs-lookup"><span data-stu-id="773fe-168">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="773fe-169">Isso afetará as seguintes ações de melhoria:</span><span class="sxs-lookup"><span data-stu-id="773fe-169">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="773fe-170">Garantir que todos os usuários possam concluir a autenticação multifator para acesso seguro</span><span class="sxs-lookup"><span data-stu-id="773fe-170">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="773fe-171">Exigir MFA para funções administrativas</span><span class="sxs-lookup"><span data-stu-id="773fe-171">Require MFA for administrative roles</span></span>
- <span data-ttu-id="773fe-172">Habilitar política para bloquear autenticação herdada</span><span class="sxs-lookup"><span data-stu-id="773fe-172">Enable policy to block legacy authentication</span></span>
