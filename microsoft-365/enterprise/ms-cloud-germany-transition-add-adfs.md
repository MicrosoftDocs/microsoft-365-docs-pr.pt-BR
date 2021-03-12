---
title: Etapas de migração do AD FS para a migração do Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Resumo: Etapas de migração dos Serviços de Federação do Active Directory (AD FS) para a migração do Microsoft Cloud Deutschland.'
ms.openlocfilehash: 030515227f3abdae82736807a01d1691d2d45552
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727462"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="c11ff-103">Etapas de migração do AD FS para a migração do Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="c11ff-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="c11ff-104">Essa alteração de configuração pode ser aplicada a qualquer momento antes do início da fase 4.</span><span class="sxs-lookup"><span data-stu-id="c11ff-104">This configuration change can be applied at any time before phase 4 is starting.</span></span>
<span data-ttu-id="c11ff-105">Depois que a fase 2 for concluída, a alteração de configuração funcionará e você poderá entrar nos pontos de extremidade globais do Office 365, como `https://portal.office.com` .</span><span class="sxs-lookup"><span data-stu-id="c11ff-105">Once phase 2 is completed the configuration change will work and you are able to sign in to Office 365 Global endpoints such as `https://portal.office.com`.</span></span> <span data-ttu-id="c11ff-106">Se você estiver implementando a alteração de configuração antes da fase  2, os pontos de extremidade globais do Office 365 ainda não funcionarão, mas a nova confiança de parte confiável ainda faz parte da configuração dos Serviços de Federação do Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="c11ff-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="c11ff-107">Para migrar seu farm do AD FS do Microsoft Cloud Deutschland:</span><span class="sxs-lookup"><span data-stu-id="c11ff-107">To migrate your AD FS farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="c11ff-108">Fazer o back up your AD FS settings including FF trust info with [these steps](#backup).</span><span class="sxs-lookup"><span data-stu-id="c11ff-108">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="c11ff-109">Nomeia o backup **do Microsoft Cloud Deutschland_Only** para indicar que ele tem apenas as informações de locatário do Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="c11ff-109">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="c11ff-110">Teste a restauração usando o backup do Microsoft Cloud Deutschland_Only, o farm do AD FS deve continuar a operar como Microsoft Cloud Deutschland somente.</span><span class="sxs-lookup"><span data-stu-id="c11ff-110">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="c11ff-111">Depois de concluir e testar o backup do AD FS, execute as etapas a seguir para adicionar uma nova confiança de terceiros confiável à configuração do ADFS:</span><span class="sxs-lookup"><span data-stu-id="c11ff-111">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="c11ff-112">Abra o console de gerenciamento do AD FS</span><span class="sxs-lookup"><span data-stu-id="c11ff-112">Open the AD FS management console</span></span>
2. <span data-ttu-id="c11ff-113">No painel esquerdo do console de gerenciamento do ADFS, expanda **a ADFS**, depois **relações** de confiança, e, em seguida, **confianças de terceiros confiável**</span><span class="sxs-lookup"><span data-stu-id="c11ff-113">In the left pane of the ADFS management console, expand **ADFS**, then **Trust Relationships**, then **Relying Party Trusts**</span></span>
3. <span data-ttu-id="c11ff-114">No painel direito, selecione **Adicionar Confiança de Parte Confiável...**</span><span class="sxs-lookup"><span data-stu-id="c11ff-114">In the right pane, select **Add Relying Party Trust...**</span></span>
4. <span data-ttu-id="c11ff-115">Selecione **Próximo** na página **Bem-vindo** do assistente Adicionar Confiança de Parte Confiável.</span><span class="sxs-lookup"><span data-stu-id="c11ff-115">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
5. <span data-ttu-id="c11ff-116">Na página **Selecionar Fonte de** Dados, selecione Importar dados sobre a parte confiável publicada online ou em uma rede **local.**</span><span class="sxs-lookup"><span data-stu-id="c11ff-116">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="c11ff-117">O **valor do endereço de metadados de** federação (nome do host ou URL) deve ser definido como `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="c11ff-117">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="c11ff-118">Em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c11ff-118">Then, click **Next**.</span></span>
6. <span data-ttu-id="c11ff-119">Na página **Selecionar Fonte de** Dados, digite o nome de exibição como Microsoft Office **365 Identity Platform WorldWide**.</span><span class="sxs-lookup"><span data-stu-id="c11ff-119">On the **Select Data Source** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="c11ff-120">Em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c11ff-120">Then, click **Next**.</span></span>
7. <span data-ttu-id="c11ff-121">Na página do assistente **Configure Multifator Authentication Now?**, selecione a escolha apropriada de acordo com seus requisitos de autenticação.</span><span class="sxs-lookup"><span data-stu-id="c11ff-121">On the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="c11ff-122">Se você permanecer com o padrão, selecione Não quero configurar configurações de autenticação multifator para essa confiança de parte confiável **neste momento**.</span><span class="sxs-lookup"><span data-stu-id="c11ff-122">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="c11ff-123">Você pode alterar essa configuração mais tarde, se quiser.</span><span class="sxs-lookup"><span data-stu-id="c11ff-123">You can change this setting later if you want to.</span></span>
8. <span data-ttu-id="c11ff-124">Na opção **Escolher Regras** de Autorização de Emissão , mantenha Permitir que todos os usuários acessem essa parte **de** confiança selecionada clique em **Próximo**</span><span class="sxs-lookup"><span data-stu-id="c11ff-124">On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected click **Next**</span></span>
9. <span data-ttu-id="c11ff-125">Clique **em Próximo** na página Pronto para Adicionar **Confiança** para concluir o assistente.</span><span class="sxs-lookup"><span data-stu-id="c11ff-125">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>
10. <span data-ttu-id="c11ff-126">Clique **em Fechar** na página Concluir. </span><span class="sxs-lookup"><span data-stu-id="c11ff-126">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="c11ff-127">Ao fechar o assistente, a Confiança de Parte Confiável com os serviços Globais do Office 365 é estabelecida.</span><span class="sxs-lookup"><span data-stu-id="c11ff-127">By closing the wizard, the Relying Party Trust with the Office 365 Global services is established.</span></span> <span data-ttu-id="c11ff-128">No entanto, nenhuma regra de Transformação de Emissão ainda está configurada.</span><span class="sxs-lookup"><span data-stu-id="c11ff-128">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="c11ff-129">Você pode usar [a Ajuda do AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) para gerar as regras corretas de Transformação de Emissão.</span><span class="sxs-lookup"><span data-stu-id="c11ff-129">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="c11ff-130">As regras de declaração geradas criadas com a Ajuda do AD FS podem ser adicionadas manualmente por meio do console de gerenciamento do AD FS ou com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c11ff-130">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="c11ff-131">A Ajuda do AD FS gerará os scripts necessários do PowerShell que precisam ser executados.</span><span class="sxs-lookup"><span data-stu-id="c11ff-131">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. <span data-ttu-id="c11ff-132">Execute **Gerar Declarações no** AD FS ajuda e copie o script de transformação de declarações do PowerShell usando a opção **Copiar** no canto superior direito do script.</span><span class="sxs-lookup"><span data-stu-id="c11ff-132">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="c11ff-133">Abra seu editor de texto preferencial e colar o script do PowerShell em uma nova janela de texto.</span><span class="sxs-lookup"><span data-stu-id="c11ff-133">Open your preferred text editor and paste the PowerShell script into a new text window.</span></span>
3. <span data-ttu-id="c11ff-134">Adicione as seguintes linhas do PowerShell ao final do script pastado da etapa 2</span><span class="sxs-lookup"><span data-stu-id="c11ff-134">Add the following PowerShell lines to the end of the pasted script from step 2</span></span>
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. <span data-ttu-id="c11ff-135">Safe e execute o script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c11ff-135">Safe and execute the PowerShell script.</span></span>
5. <span data-ttu-id="c11ff-136">Verifique se duas confianças de Parte Confiável estão presentes; um para o Microsoft Cloud Deutschland e outro para o serviço Global do Office 365.</span><span class="sxs-lookup"><span data-stu-id="c11ff-136">Verify that two Relying Party trusts are present; one for the Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span>
6. <span data-ttu-id="c11ff-137">Faça backup de suas confiações usando [estas etapas.](#backup)</span><span class="sxs-lookup"><span data-stu-id="c11ff-137">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="c11ff-138">Salve-o com o nome **FFAndWorldwide**.</span><span class="sxs-lookup"><span data-stu-id="c11ff-138">Save it with the name **FFAndWorldwide**.</span></span>
7. <span data-ttu-id="c11ff-139">Conclua a migração de back-end e verifique se o AD FS ainda funciona durante o processo de migração.</span><span class="sxs-lookup"><span data-stu-id="c11ff-139">Complete your backend migration and verify that AD FS still works during the migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="c11ff-140">Recuperação de Desastre do AD FS (Banco de Dados WID)</span><span class="sxs-lookup"><span data-stu-id="c11ff-140">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="c11ff-141">Para restaurar o farm do AD FS em um desastre, a Ferramenta de Restauração Rápida do [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) precisa ser aproveitada.</span><span class="sxs-lookup"><span data-stu-id="c11ff-141">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="c11ff-142">Portanto, a ferramenta deve ser baixada e, antes do início da migração, um backup deve ser criado e armazenado com segurança.</span><span class="sxs-lookup"><span data-stu-id="c11ff-142">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="c11ff-143">Neste exemplo (ambientes DOAA) os seguintes comandos foram executados para fazer o back up do farm:</span><span class="sxs-lookup"><span data-stu-id="c11ff-143">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="c11ff-144">Back up an AD FS Farm</span><span class="sxs-lookup"><span data-stu-id="c11ff-144">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="c11ff-145">Instale a Ferramenta de Restauração Rápida do AD FS no servidor principal do AD FS.</span><span class="sxs-lookup"><span data-stu-id="c11ff-145">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="c11ff-146">Importe o módulo em uma sessão do PowerShell com este comando.</span><span class="sxs-lookup"><span data-stu-id="c11ff-146">Import the module in a PowerShell session with this command.</span></span>
    ```powershell
    Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
    ```
3. <span data-ttu-id="c11ff-147">Execute o comando de backup:</span><span class="sxs-lookup"><span data-stu-id="c11ff-147">Run the backup command:</span></span>
    ```powershell
    Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
    ```
4. <span data-ttu-id="c11ff-148">Armazene o backup com segurança em um destino desejado.</span><span class="sxs-lookup"><span data-stu-id="c11ff-148">Store the backup safely on a desired destination.</span></span>

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="c11ff-149">Restaurar um farm do AD FS</span><span class="sxs-lookup"><span data-stu-id="c11ff-149">Restore an AD FS Farm</span></span>

<span data-ttu-id="c11ff-150">Se o farm falhou completamente e não há como retornar ao farm antigo, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="c11ff-150">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="c11ff-151">Mova o backup gerado e armazenado anteriormente para o novo servidor AD FS principal.</span><span class="sxs-lookup"><span data-stu-id="c11ff-151">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="c11ff-152">Execute o seguinte `Restore-ADFS` comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c11ff-152">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="c11ff-153">Se necessário, importe o certificado SSL do AD FS antecipadamente.</span><span class="sxs-lookup"><span data-stu-id="c11ff-153">If necessary, import the AD FS SSL certificate beforehand.</span></span>

    ```powershell
    Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
    ```

3. <span data-ttu-id="c11ff-154">Aponte seus novos registros DNS ou balanceador de carga para os novos servidores do AD FS.</span><span class="sxs-lookup"><span data-stu-id="c11ff-154">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="c11ff-155">Mais Informações</span><span class="sxs-lookup"><span data-stu-id="c11ff-155">More information</span></span>

<span data-ttu-id="c11ff-156">Como começar:</span><span class="sxs-lookup"><span data-stu-id="c11ff-156">Getting started:</span></span>

- [<span data-ttu-id="c11ff-157">Migração do Microsoft Cloud Deutschland para serviços do Office 365 nas novas regiões do datacenter alemão</span><span class="sxs-lookup"><span data-stu-id="c11ff-157">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="c11ff-158">Assistência de Migração do Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="c11ff-158">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="c11ff-159">Como aceitar a migração</span><span class="sxs-lookup"><span data-stu-id="c11ff-159">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="c11ff-160">Experiência do cliente durante a migração</span><span class="sxs-lookup"><span data-stu-id="c11ff-160">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="c11ff-161">Movendo-se pela transição:</span><span class="sxs-lookup"><span data-stu-id="c11ff-161">Moving through the transition:</span></span>

- [<span data-ttu-id="c11ff-162">Ações e impactos das fases de migração</span><span class="sxs-lookup"><span data-stu-id="c11ff-162">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="c11ff-163">Pré-trabalho adicional</span><span class="sxs-lookup"><span data-stu-id="c11ff-163">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="c11ff-164">Informações adicionais para [o Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos, experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md). [](ms-cloud-germany-transition-add-devices.md)</span><span class="sxs-lookup"><span data-stu-id="c11ff-164">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="c11ff-165">Aplicativos de nuvem:</span><span class="sxs-lookup"><span data-stu-id="c11ff-165">Cloud apps:</span></span>

- [<span data-ttu-id="c11ff-166">Informações do programa de migração do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c11ff-166">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="c11ff-167">Informações do programa de migração do Power BI</span><span class="sxs-lookup"><span data-stu-id="c11ff-167">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="c11ff-168">Introdução à atualização do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c11ff-168">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
