---
title: Detectar e remediar concessões de consentimento ilícito
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Saiba como reconhecer e remediar o consentimento ilícito concede ataques Microsoft Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7869419677ba1d5d6b480b7f0dea7f67880af0c7
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644675"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a><span data-ttu-id="41a68-103">Detectar e remediar concessões de consentimento ilícito</span><span class="sxs-lookup"><span data-stu-id="41a68-103">Detect and Remediate Illicit Consent Grants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="41a68-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="41a68-104">**Applies to**</span></span>
- [<span data-ttu-id="41a68-105">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="41a68-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="41a68-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41a68-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="41a68-107">**Resumo**  Saiba como reconhecer e remediar o consentimento ilícito concede ataques no Office 365.</span><span class="sxs-lookup"><span data-stu-id="41a68-107">**Summary**  Learn how to recognize and remediate the illicit consent grants attack in Office 365.</span></span>

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a><span data-ttu-id="41a68-108">Qual é o ataque de concessão de consentimento ilícito no Office 365?</span><span class="sxs-lookup"><span data-stu-id="41a68-108">What is the illicit consent grant attack in Office 365?</span></span>

<span data-ttu-id="41a68-109">Em um ataque de concessão de consentimento ilícito, o invasor cria um aplicativo registrado no Azure que solicita acesso a dados como informações de contato, email ou documentos.</span><span class="sxs-lookup"><span data-stu-id="41a68-109">In an illicit consent grant attack, the attacker creates an Azure-registered application that requests access to data such as contact information, email, or documents.</span></span> <span data-ttu-id="41a68-110">Em seguida, o invasor faz com que um usuário final conceda ao aplicativo o consentimento para acessar seus dados por meio de um ataque de phishing ou injetando código ilícito em um site confiável.</span><span class="sxs-lookup"><span data-stu-id="41a68-110">The attacker then tricks an end user into granting that application consent to access their data either through a phishing attack, or by injecting illicit code into a trusted website.</span></span> <span data-ttu-id="41a68-111">Após o consentimento do aplicativo ilícito, ele tem acesso no nível da conta aos dados sem a necessidade de uma conta organizacional.</span><span class="sxs-lookup"><span data-stu-id="41a68-111">After the illicit application has been granted consent, it has account-level access to data without the need for an organizational account.</span></span> <span data-ttu-id="41a68-112">As etapas normais de correção, como redefinir senhas para contas violadas ou exigir A autenticação multifato (MFA) em contas, não são eficazes contra esse tipo de ataque, pois são aplicativos de terceiros e são externos à organização.</span><span class="sxs-lookup"><span data-stu-id="41a68-112">Normal remediation steps, like resetting passwords for breached accounts or requiring Multi-Factor Authentication (MFA) on accounts, are not effective against this type of attack, since these are third-party applications and are external to the organization.</span></span>

<span data-ttu-id="41a68-113">Esses ataques aproveitam um modelo de interação que presume que a entidade que está chamando as informações seja automação e não humana.</span><span class="sxs-lookup"><span data-stu-id="41a68-113">These attacks leverage an interaction model which presumes the entity that is calling the information is automation and not a human.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41a68-114">Você suspeita que está enfrentando problemas com concessões ilícitas de consentimento de um aplicativo, agora?</span><span class="sxs-lookup"><span data-stu-id="41a68-114">Do you suspect you're experiencing problems with illicit consent-grants from an app, right now?</span></span> <span data-ttu-id="41a68-115">O Microsoft Cloud App Security (MCAS) tem ferramentas para detectar, investigar e remediar seus aplicativos OAuth.</span><span class="sxs-lookup"><span data-stu-id="41a68-115">Microsoft Cloud App Security (MCAS) has tools to detect, investigate, and remediate your OAuth apps.</span></span> <span data-ttu-id="41a68-116">Este artigo do MCAS tem um tutorial que descreve como investigar aplicativos [OAuth arriscados.](/cloud-app-security/investigate-risky-oauth)</span><span class="sxs-lookup"><span data-stu-id="41a68-116">This MCAS article has a tutorial that outlines how to go about [investigating risky OAuth apps](/cloud-app-security/investigate-risky-oauth).</span></span> <span data-ttu-id="41a68-117">Você também pode definir políticas de aplicativo [OAuth](/cloud-app-security/app-permission-policy) para investigar permissões solicitadas pelo aplicativo, quais usuários estão autorizando esses aplicativos e aprovar ou proibir amplamente essas solicitações de permissão.</span><span class="sxs-lookup"><span data-stu-id="41a68-117">You can also set [OAuth app policies](/cloud-app-security/app-permission-policy) to investigate app-requested permissions, which users are authorizing these apps, and widely approve or ban these permissions requests.</span></span>

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a><span data-ttu-id="41a68-118">Qual é a aparência de um ataque de concessão de consentimento ilícito no Office 365?</span><span class="sxs-lookup"><span data-stu-id="41a68-118">What does an illicit consent grant attack look like in Office 365?</span></span>

<span data-ttu-id="41a68-119">Você precisa pesquisar no **log de auditoria para** encontrar sinais, também chamados indicadores de comprometimento (IOC) desse ataque.</span><span class="sxs-lookup"><span data-stu-id="41a68-119">You need to search the **audit log** to find signs, also called Indicators of Compromise (IOC) of this attack.</span></span> <span data-ttu-id="41a68-120">Para organizações com muitos aplicativos registrados no Azure e uma grande base de usuários, a melhor prática é revisar as concessões de consentimento de suas organizações semanalmente.</span><span class="sxs-lookup"><span data-stu-id="41a68-120">For organizations with many Azure-registered applications and a large user base, the best practice is to review your organizations consent grants on a weekly basis.</span></span>

### <a name="steps-for-finding-signs-of-this-attack"></a><span data-ttu-id="41a68-121">Etapas para encontrar sinais desse ataque</span><span class="sxs-lookup"><span data-stu-id="41a68-121">Steps for finding signs of this attack</span></span>

1. <span data-ttu-id="41a68-122">Abra o **Centro de Conformidade & segurança** em <https://protection.office.com> .</span><span class="sxs-lookup"><span data-stu-id="41a68-122">Open the **Security & Compliance Center** at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="41a68-123">Navegue até **Pesquisar** e selecione **Pesquisa de log de auditoria.**</span><span class="sxs-lookup"><span data-stu-id="41a68-123">Navigate to **Search** and select **Audit log search**.</span></span>

3. <span data-ttu-id="41a68-124">Pesquise (todas as atividades e todos os usuários) e insira a data de início e a data de término, se necessário, e clique em **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="41a68-124">Search (all activities and all users) and enter the start date and end date if required and then click **Search**.</span></span>

4. <span data-ttu-id="41a68-125">Clique **em Filtrar resultados** e insira Consentimento para aplicativo no **campo** Atividade.</span><span class="sxs-lookup"><span data-stu-id="41a68-125">Click **Filter results** and enter Consent to application in the **Activity** field.</span></span>

5. <span data-ttu-id="41a68-126">Clique no resultado para ver os detalhes da atividade.</span><span class="sxs-lookup"><span data-stu-id="41a68-126">Click on the result to see the details of the activity.</span></span> <span data-ttu-id="41a68-127">Clique **em Mais Informações** para obter detalhes da atividade.</span><span class="sxs-lookup"><span data-stu-id="41a68-127">Click **More Information** to get details of the activity.</span></span> <span data-ttu-id="41a68-128">Verifique se IsAdminContent está definido como True.</span><span class="sxs-lookup"><span data-stu-id="41a68-128">Check to see if IsAdminContent is set to True.</span></span>

> [!NOTE]
>
> <span data-ttu-id="41a68-129">Pode levar de 30 minutos até 24 horas para que a entrada de log de auditoria correspondente seja exibida nos resultados da pesquisa depois que um evento ocorrer.</span><span class="sxs-lookup"><span data-stu-id="41a68-129">It can take from 30 minutes up to 24 hours for the corresponding audit log entry to be displayed in the search results after an event occurs.</span></span>
>
> <span data-ttu-id="41a68-130">O período em que um registro de auditoria é mantido e pesquisável no log de auditoria depende da sua assinatura do Microsoft 365 e, especificamente, do tipo de licença atribuída a um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="41a68-130">The length of time that an audit record is retained and searchable in the audit log depends on your Microsoft 365 subscription, and specifically the type of the license that is assigned to a specific user.</span></span> <span data-ttu-id="41a68-131">Para obter mais informações, consulte [Log de auditoria](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="41a68-131">For more information, see [Audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>
>
> <span data-ttu-id="41a68-132">Se esse valor for verdadeiro, ele indicará que alguém com acesso ao Administrador Global pode ter concedido amplo acesso aos dados.</span><span class="sxs-lookup"><span data-stu-id="41a68-132">If this value is true, it indicates that someone with Global Administrator access may have granted broad access to data.</span></span> <span data-ttu-id="41a68-133">Se isso for inesperado, tome medidas para [confirmar um ataque](#how-to-confirm-an-attack).</span><span class="sxs-lookup"><span data-stu-id="41a68-133">If this is unexpected, take steps to [confirm an attack](#how-to-confirm-an-attack).</span></span>

## <a name="how-to-confirm-an-attack"></a><span data-ttu-id="41a68-134">Como confirmar um ataque</span><span class="sxs-lookup"><span data-stu-id="41a68-134">How to confirm an attack</span></span>

<span data-ttu-id="41a68-135">Se você tiver uma ou mais instâncias dos IOCs listados acima, será necessário fazer uma investigação posterior para confirmar positivamente que o ataque ocorreu.</span><span class="sxs-lookup"><span data-stu-id="41a68-135">If you have one or more instances of the IOCs listed above, you need to do further investigation to positively confirm that the attack occurred.</span></span> <span data-ttu-id="41a68-136">Você pode usar qualquer um desses três métodos para confirmar o ataque:</span><span class="sxs-lookup"><span data-stu-id="41a68-136">You can use any of these three methods to confirm the attack:</span></span>

- <span data-ttu-id="41a68-137">Aplicativos de inventário e suas permissões usando o portal do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="41a68-137">Inventory applications and their permissions using the Azure Active Directory portal.</span></span> <span data-ttu-id="41a68-138">Esse método é completo, mas você só pode verificar um usuário por vez, o que pode levar muito tempo se você tiver muitos usuários para verificar.</span><span class="sxs-lookup"><span data-stu-id="41a68-138">This method is thorough, but you can only check one user at a time which can be very time consuming if you have many users to check.</span></span>

- <span data-ttu-id="41a68-139">Aplicativos de inventário e suas permissões usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41a68-139">Inventory applications and their permissions using PowerShell.</span></span> <span data-ttu-id="41a68-140">Esse é o método mais rápido e completo, com a menor quantidade de sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="41a68-140">This is the fastest and most thorough method, with the least amount of overhead.</span></span>

- <span data-ttu-id="41a68-141">Verifique individualmente seus aplicativos e permissões e reporte os resultados aos administradores para correção.</span><span class="sxs-lookup"><span data-stu-id="41a68-141">Have your users individually check their apps and permissions and report the results back to the administrators for remediation.</span></span>

## <a name="inventory-apps-with-access-in-your-organization"></a><span data-ttu-id="41a68-142">Inventário de aplicativos com acesso em sua organização</span><span class="sxs-lookup"><span data-stu-id="41a68-142">Inventory apps with access in your organization</span></span>

<span data-ttu-id="41a68-143">Você pode fazer isso para seus usuários com o Portal do Azure Active Directory ou o PowerShell ou fazer com que seus usuários enumerem individualmente o acesso ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="41a68-143">You can do this for your users with either the Azure Active Directory Portal, or PowerShell or have your users individually enumerate their application access.</span></span>

### <a name="steps-for-using-the-azure-active-directory-portal"></a><span data-ttu-id="41a68-144">Etapas para usar o Portal do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="41a68-144">Steps for using the Azure Active Directory Portal</span></span>

<span data-ttu-id="41a68-145">Você pode procurar os aplicativos aos quais qualquer usuário individual concedeu permissões usando o Portal do [Azure Active Directory](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="41a68-145">You can look up the applications to which any individual user has granted permissions by using the [Azure Active Directory Portal](https://portal.azure.com/).</span></span>

1. <span data-ttu-id="41a68-146">Entre no portal do Azure com direitos administrativos.</span><span class="sxs-lookup"><span data-stu-id="41a68-146">Sign in to the Azure portal with administrative rights.</span></span>

2. <span data-ttu-id="41a68-147">Selecione a folha do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="41a68-147">Select the Azure Active Directory blade.</span></span>

3. <span data-ttu-id="41a68-148">Selecione **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="41a68-148">Select **Users**.</span></span>

4. <span data-ttu-id="41a68-149">Selecione o usuário que você deseja revisar.</span><span class="sxs-lookup"><span data-stu-id="41a68-149">Select the user that you want to review.</span></span>

5. <span data-ttu-id="41a68-150">Selecione **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="41a68-150">Select **Applications**.</span></span>

<span data-ttu-id="41a68-151">Isso mostrará os aplicativos atribuídos ao usuário e quais permissões os aplicativos têm.</span><span class="sxs-lookup"><span data-stu-id="41a68-151">This will show you the apps that are assigned to the user and what permissions the applications have.</span></span>

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a><span data-ttu-id="41a68-152">Etapas para que seus usuários enumeram o acesso ao aplicativo</span><span class="sxs-lookup"><span data-stu-id="41a68-152">Steps for having your users enumerate their application access</span></span>

<span data-ttu-id="41a68-153">Fazer com que os usuários https://myapps.microsoft.com acessem e revisem seu próprio acesso ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="41a68-153">Have your users go to https://myapps.microsoft.com and review their own application access there.</span></span> <span data-ttu-id="41a68-154">Eles devem poder ver todos os aplicativos com acesso, exibir detalhes sobre eles (incluindo o escopo de acesso) e revogar privilégios para aplicativos suspeitos ou ilícitos.</span><span class="sxs-lookup"><span data-stu-id="41a68-154">They should be able to see all the apps with access, view details about them (including the scope of access), and be able to revoke privileges to suspicious or illicit apps.</span></span>

### <a name="steps-for-doing-this-with-powershell"></a><span data-ttu-id="41a68-155">Etapas para fazer isso com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="41a68-155">Steps for doing this with PowerShell</span></span>

<span data-ttu-id="41a68-156">A maneira mais simples de verificar o ataque de Concessão de Consentimento Ilícito é executar o [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), que despeja todas as concessões de consentimento OAuth e aplicativos OAuth para todos os usuários em sua posição em um arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="41a68-156">The simplest way to verify the Illicit Consent Grant attack is to run [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), which will dump all the OAuth consent grants and OAuth apps for all users in your tenancy into one .csv file.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="41a68-157">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="41a68-157">Pre-requisites</span></span>

- <span data-ttu-id="41a68-158">A biblioteca do Azure AD PowerShell instalada.</span><span class="sxs-lookup"><span data-stu-id="41a68-158">The Azure AD PowerShell library installed.</span></span>

- <span data-ttu-id="41a68-159">Direitos de administrador global no locatário em que o script será executado.</span><span class="sxs-lookup"><span data-stu-id="41a68-159">Global administrator rights on the tenant that the script will be run against.</span></span>

- <span data-ttu-id="41a68-160">Administrador local no computador do qual executará os scripts.</span><span class="sxs-lookup"><span data-stu-id="41a68-160">Local Administrator on the computer from which will run the scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41a68-161">É ***altamente recomendável*** que você exige autenticação multifafação em sua conta administrativa.</span><span class="sxs-lookup"><span data-stu-id="41a68-161">We ***highly recommend*** that you require multi-factor authentication on your administrative account.</span></span> <span data-ttu-id="41a68-162">Este script dá suporte à autenticação MFA.</span><span class="sxs-lookup"><span data-stu-id="41a68-162">This script supports MFA authentication.</span></span>

1. <span data-ttu-id="41a68-163">Entre no computador de onde você executará o script com direitos de administrador local.</span><span class="sxs-lookup"><span data-stu-id="41a68-163">Sign in to the computer that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="41a68-164">Baixe ou copie o [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) do GitHub para uma pasta da qual você executará o script.</span><span class="sxs-lookup"><span data-stu-id="41a68-164">Download or copy the [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script from GitHub to a folder from which you will run the script.</span></span> <span data-ttu-id="41a68-165">Essa será a mesma pasta na qual o arquivo de saída "permissions.csv" será gravado.</span><span class="sxs-lookup"><span data-stu-id="41a68-165">This will be the same folder to which the output "permissions.csv" file will be written.</span></span>

3. <span data-ttu-id="41a68-166">Abra uma instância do PowerShell como administrador e abra para a pasta em que você salvou o script.</span><span class="sxs-lookup"><span data-stu-id="41a68-166">Open a PowerShell instance as an administrator and open to the folder you saved the script to.</span></span>

4. <span data-ttu-id="41a68-167">Conecte-se ao diretório usando o cmdlet [Connect-AzureAD.](/powershell/module/azuread/connect-azuread)</span><span class="sxs-lookup"><span data-stu-id="41a68-167">Connect to your directory using the [Connect-AzureAD](/powershell/module/azuread/connect-azuread) cmdlet.</span></span>

5. <span data-ttu-id="41a68-168">Execute este comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="41a68-168">Run this PowerShell command:</span></span>

   ```powershell
   .\Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

<span data-ttu-id="41a68-169">O script produz um arquivo chamado Permissions.csv.</span><span class="sxs-lookup"><span data-stu-id="41a68-169">The script produces one file named Permissions.csv.</span></span> <span data-ttu-id="41a68-170">Siga estas etapas para procurar concessões de permissão ilícitas de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="41a68-170">Follow these steps to look for illicit application permission grants:</span></span>

1. <span data-ttu-id="41a68-171">Na coluna ConsentType (coluna G) procure o valor "AllPrinciples".</span><span class="sxs-lookup"><span data-stu-id="41a68-171">In the ConsentType column (column G) search for the value "AllPrinciples".</span></span> <span data-ttu-id="41a68-172">A permissão AllPrincipals permite que o aplicativo cliente acesse o conteúdo de todos na área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="41a68-172">The AllPrincipals permission allows the client application to access everyone's content in the tenancy.</span></span> <span data-ttu-id="41a68-173">Os aplicativos nativos do Microsoft 365 precisam dessa permissão para funcionar corretamente.</span><span class="sxs-lookup"><span data-stu-id="41a68-173">Native Microsoft 365 applications need this permission to work correctly.</span></span> <span data-ttu-id="41a68-174">Todos os aplicativos que não são da Microsoft com essa permissão devem ser analisados cuidadosamente.</span><span class="sxs-lookup"><span data-stu-id="41a68-174">Every non-Microsoft application with this permission should be reviewed carefully.</span></span>

2. <span data-ttu-id="41a68-175">Na coluna Permissão (coluna F), revise as permissões que cada aplicativo delegado tem para o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="41a68-175">In the Permission column (column F) review the permissions that each delegated application has to content.</span></span> <span data-ttu-id="41a68-176">Procure a permissão "Leitura" e "Gravação" ou "\*. Permissão All" e revise-os cuidadosamente porque podem não ser apropriados.</span><span class="sxs-lookup"><span data-stu-id="41a68-176">Look for "Read" and "Write" permission or "\*.All" permission, and review these carefully because they may not be appropriate.</span></span>

3. <span data-ttu-id="41a68-177">Revise os usuários específicos que têm consentimentos concedidos.</span><span class="sxs-lookup"><span data-stu-id="41a68-177">Review the specific users that have consents granted.</span></span> <span data-ttu-id="41a68-178">Se usuários de alto perfil ou de alto impacto têm consentimentos inadequados concedidos, você deve investigar mais.</span><span class="sxs-lookup"><span data-stu-id="41a68-178">If high profile or high impact users have inappropriate consents granted, you should investigate further.</span></span>

4. <span data-ttu-id="41a68-179">Na coluna ClientDisplayName (coluna C), procure aplicativos que pareçam suspeitos.</span><span class="sxs-lookup"><span data-stu-id="41a68-179">In the ClientDisplayName column (column C) look for apps that seem suspicious.</span></span> <span data-ttu-id="41a68-180">Os aplicativos com nomes mal escritos, nomes super sem graça ou nomes de sons de hackers devem ser analisados cuidadosamente.</span><span class="sxs-lookup"><span data-stu-id="41a68-180">Apps with misspelled names, super bland names, or hacker-sounding names should be reviewed carefully.</span></span>

## <a name="determine-the-scope-of-the-attack"></a><span data-ttu-id="41a68-181">Determinar o escopo do ataque</span><span class="sxs-lookup"><span data-stu-id="41a68-181">Determine the scope of the attack</span></span>

<span data-ttu-id="41a68-182">Depois de terminar o inventário do acesso ao aplicativo, revise o log de **auditoria** para determinar o escopo completo da violação.</span><span class="sxs-lookup"><span data-stu-id="41a68-182">After you have finished inventorying application access, review the **audit log** to determine the full scope of the breach.</span></span> <span data-ttu-id="41a68-183">Pesquise os usuários afetados, os períodos em que o aplicativo ilícito teve acesso à sua organização e as permissões que o aplicativo tinha.</span><span class="sxs-lookup"><span data-stu-id="41a68-183">Search on the affected users, the time frames that the illicit application had access to your organization, and the permissions the app had.</span></span> <span data-ttu-id="41a68-184">Você pode pesquisar o **log de auditoria** no Centro de Conformidade e Segurança do Microsoft [365.](../../compliance/search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="41a68-184">You can search the **audit log** in the [Microsoft 365 Security and Compliance Center](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41a68-185">[A auditoria de caixa](../../compliance/enable-mailbox-auditing.md) de correio e a [auditoria](../../compliance/turn-audit-log-search-on-or-off.md) de atividade para administradores e usuários devem ter sido habilitadas antes do ataque para que você receba essas informações.</span><span class="sxs-lookup"><span data-stu-id="41a68-185">[Mailbox auditing](../../compliance/enable-mailbox-auditing.md) and [Activity auditing for admins and users](../../compliance/turn-audit-log-search-on-or-off.md) must have been enabled prior to the attack for you to get this information.</span></span>

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a><span data-ttu-id="41a68-186">Como parar e remediar um ataque de concessão de consentimento ilícito</span><span class="sxs-lookup"><span data-stu-id="41a68-186">How to stop and remediate an illicit consent grant attack</span></span>

<span data-ttu-id="41a68-187">Depois de identificar um aplicativo com permissões ilícitas, você tem várias maneiras de remover esse acesso.</span><span class="sxs-lookup"><span data-stu-id="41a68-187">After you have identified an application with illicit permissions, you have several ways to remove that access.</span></span>

- <span data-ttu-id="41a68-188">Você pode revogar a permissão do aplicativo no Portal do Azure Active Directory por:</span><span class="sxs-lookup"><span data-stu-id="41a68-188">You can revoke the application's permission in the Azure Active Directory Portal by:</span></span>

  - <span data-ttu-id="41a68-189">Navegue até o usuário afetado na folha **Usuário do Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="41a68-189">Navigate to the affected user in the **Azure Active Directory User** blade.</span></span>

  - <span data-ttu-id="41a68-190">Selecione **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="41a68-190">Select **Applications**.</span></span>

  - <span data-ttu-id="41a68-191">Selecione o aplicativo ilícito.</span><span class="sxs-lookup"><span data-stu-id="41a68-191">Select the illicit application.</span></span>

  - <span data-ttu-id="41a68-192">Clique **em Remover** na broca para baixo.</span><span class="sxs-lookup"><span data-stu-id="41a68-192">Click **Remove** in the drill down.</span></span>

- <span data-ttu-id="41a68-193">Você pode revogar a concessão de consentimento OAuth com o PowerShell seguindo as etapas em [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span><span class="sxs-lookup"><span data-stu-id="41a68-193">You can revoke the OAuth consent grant with PowerShell by following the steps in [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span></span>

- <span data-ttu-id="41a68-194">Você pode revogar a atribuição de função de aplicativo de serviço com o PowerShell seguindo as etapas em [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).</span><span class="sxs-lookup"><span data-stu-id="41a68-194">You can revoke the Service App Role Assignment with PowerShell by following the steps in [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).</span></span>

- <span data-ttu-id="41a68-195">Você também pode desabilitar completamente a entrada para a conta afetada, o que, por sua vez, desabilitará o acesso do aplicativo aos dados nessa conta.</span><span class="sxs-lookup"><span data-stu-id="41a68-195">You can also disable sign-in for the affected account altogether, which will in turn disable app access to data in that account.</span></span> <span data-ttu-id="41a68-196">Isso não é ideal para a produtividade do usuário final, é claro, mas se você estiver trabalhando para limitar o impacto rapidamente, pode ser uma correção viável a curto prazo.</span><span class="sxs-lookup"><span data-stu-id="41a68-196">This isn't ideal for the end user's productivity, of course, but if you are working to limit impact quickly, it can be a viable short-term remediation.</span></span>

- <span data-ttu-id="41a68-197">Você pode desativar aplicativos integrados para a sua adimplência.</span><span class="sxs-lookup"><span data-stu-id="41a68-197">You can turn integrated applications off for your tenancy.</span></span> <span data-ttu-id="41a68-198">Esta é uma etapa drástica que desabilita a capacidade de os usuários finais concederem consentimento em toda a locatário.</span><span class="sxs-lookup"><span data-stu-id="41a68-198">This is a drastic step that disables the ability for end users to grant consent on a tenant-wide basis.</span></span> <span data-ttu-id="41a68-199">Isso impede que seus usuários concedam inadvertidamente acesso a um aplicativo mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="41a68-199">This prevents your users from inadvertently granting access to a malicious application.</span></span> <span data-ttu-id="41a68-200">Isso não é altamente recomendado, pois prejudica gravemente a capacidade dos usuários de serem produtivos com aplicativos de terceiros.</span><span class="sxs-lookup"><span data-stu-id="41a68-200">This isn't strongly recommended as it severely impairs your users' ability to be productive with third party applications.</span></span> <span data-ttu-id="41a68-201">Você pode fazer isso seguindo as etapas em [Ligar ou desligar aplicativos integrados.](../../admin/misc/user-consent.md)</span><span class="sxs-lookup"><span data-stu-id="41a68-201">You can do this by following the steps in [Turning Integrated Apps on or off](../../admin/misc/user-consent.md).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="41a68-202">Proteja o Microsoft 365 como um profissional de segurança cibernética</span><span class="sxs-lookup"><span data-stu-id="41a68-202">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="41a68-203">Sua assinatura do Microsoft 365 vem com um poderoso conjunto de recursos de segurança que você pode usar para proteger seus dados e seus usuários.</span><span class="sxs-lookup"><span data-stu-id="41a68-203">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="41a68-204">Use o [roteiro de segurança do Microsoft 365: principais prioridades para os primeiros 30 dias, 90 dias e depois](security-roadmap.md) para implementar práticas recomendadas para proteger o seu locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41a68-204">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="41a68-205">Tarefas a realizar nos primeiros 30 dias.</span><span class="sxs-lookup"><span data-stu-id="41a68-205">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="41a68-206">Estas têm efeito imediato e baixo impacto para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="41a68-206">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="41a68-207">Tarefas para realizar em 90 dias.</span><span class="sxs-lookup"><span data-stu-id="41a68-207">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="41a68-208">Estas levam um pouco mais de tempo para planejar e implementar, mas melhoram muito sua postura de segurança.</span><span class="sxs-lookup"><span data-stu-id="41a68-208">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="41a68-209">Além de 90 dias.</span><span class="sxs-lookup"><span data-stu-id="41a68-209">Beyond 90 days.</span></span> <span data-ttu-id="41a68-210">Estes aprimoramentos são desenvolvidos nos seus primeiros 90 dias de trabalho.</span><span class="sxs-lookup"><span data-stu-id="41a68-210">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="41a68-211">Confira também:</span><span class="sxs-lookup"><span data-stu-id="41a68-211">See also:</span></span>

- <span data-ttu-id="41a68-212">[O aplicativo inesperado em minha lista de](/azure/active-directory/application-access-unexpected-application) aplicativos orienta os administradores por meio de várias ações que podem ser tomadas depois de perceber que há aplicativos inesperados com acesso a dados.</span><span class="sxs-lookup"><span data-stu-id="41a68-212">[Unexpected application in my applications list](/azure/active-directory/application-access-unexpected-application) walks administrators through various actions they may want to take after realizing there are unexpected applications with access to data.</span></span>

- <span data-ttu-id="41a68-213">[Integrar aplicativos ao Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) é uma visão geral de alto nível de consentimento e permissões.</span><span class="sxs-lookup"><span data-stu-id="41a68-213">[Integrating applications with Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) is a high-level overview of consent and permissions.</span></span>

- <span data-ttu-id="41a68-214">[Problemas no desenvolvimento do meu aplicativo](/azure/active-directory/active-directory-application-dev-development-content-map) fornece links para vários artigos relacionados ao consentimento.</span><span class="sxs-lookup"><span data-stu-id="41a68-214">[Problems developing my application](/azure/active-directory/active-directory-application-dev-development-content-map) provides links to various consent related articles.</span></span>

- <span data-ttu-id="41a68-215">Os objetos principais de aplicativo e serviço no [Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) fornece uma visão geral dos objetos principais de Aplicativo e Serviço que são fundamentais para o modelo de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="41a68-215">[Application and service principal objects in Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.</span></span>

- <span data-ttu-id="41a68-216">[Gerenciar o acesso a aplicativos](/azure/active-directory/active-directory-managing-access-to-apps) é uma visão geral dos recursos que os administradores têm para gerenciar o acesso do usuário aos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="41a68-216">[Manage access to apps](/azure/active-directory/active-directory-managing-access-to-apps) is an overview of the capabilities that administrators have to manage user access to apps.</span></span>
