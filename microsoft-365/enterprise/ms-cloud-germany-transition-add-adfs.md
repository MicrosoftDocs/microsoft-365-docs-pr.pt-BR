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
ms.openlocfilehash: c946ec3c0772cf95ab696266475b50959d682ef2
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688653"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="d1c89-103">Etapas de migração do AD FS para a migração do Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="d1c89-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="d1c89-104">Para migrar seu farm dos Serviços de Federação do Active Directory (AD FS) do Microsoft Cloud Deutschland:</span><span class="sxs-lookup"><span data-stu-id="d1c89-104">To migrate your Active Directory Federation Services (AD FS) farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="d1c89-105">Fazer o back up das configurações do AD FS, incluindo informações de confiança [FF, com estas etapas.](#backup)</span><span class="sxs-lookup"><span data-stu-id="d1c89-105">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="d1c89-106">Nome do backup **do Microsoft Cloud Deutschland_Only** para indicar que ele tem apenas as informações de locatário do Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="d1c89-106">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="d1c89-107">Teste a restauração usando o backup do Microsoft Cloud Deutschland_Only, o farm do AD FS deve continuar a operar apenas como Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="d1c89-107">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>
3. <span data-ttu-id="d1c89-108">Crie uma nova confiança de Terceiros Confiável a partir do **AD FS > serviços do Office 365.**</span><span class="sxs-lookup"><span data-stu-id="d1c89-108">Create a new Relying Party trust from **AD FS >  Office 365 services**.</span></span>
4. <span data-ttu-id="d1c89-109">In **Relying Party Trusts** in the AD FS management console, select **Add Relying Party Trust**.</span><span class="sxs-lookup"><span data-stu-id="d1c89-109">In **Relying Party Trusts** in the AD FS management console, select **Add Relying Party Trust**.</span></span>
5. <span data-ttu-id="d1c89-110">Selecione **Next na** página de **boas-vindas** do assistente Adicionar Confiança de Terceiros Confiável.</span><span class="sxs-lookup"><span data-stu-id="d1c89-110">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
6. <span data-ttu-id="d1c89-111">Na página **Selecionar Fonte de Dados,** selecione Importar dados sobre a confiança **de terceiros publicados online ou em uma rede local.**</span><span class="sxs-lookup"><span data-stu-id="d1c89-111">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="d1c89-112">O **endereço de metadados de Federação (nome do host ou URL)** é definido como `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="d1c89-112">The **Federation metadata address (host name or URL)** value is set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="d1c89-113">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d1c89-113">Click **Next**.</span></span>
7. <span data-ttu-id="d1c89-114">Na página **Selecionar Fonte de Dados,** digite o nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="d1c89-114">On the **Select Data Source** page, type the display name.</span></span> <span data-ttu-id="d1c89-115">A Microsoft recomenda **o Microsoft Office 365 Identity Platform WorldWide.**</span><span class="sxs-lookup"><span data-stu-id="d1c89-115">Microsoft recommends **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="d1c89-116">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d1c89-116">Click **Next**.</span></span>
8. <span data-ttu-id="d1c89-117">Click **Next** on the **Configure Multi-factor Authentication Now?**, **Choose Esuance Authorization Rules**, and Ready to Add **Trust** pages.</span><span class="sxs-lookup"><span data-stu-id="d1c89-117">Click **Next** on the **Configure Multi-factor Authentication Now?**, **Choose Issuance Authorization Rules**, and **Ready to Add Trust** pages.</span></span>
9. <span data-ttu-id="d1c89-118">Clique **em Fechar** na **página** Concluir.</span><span class="sxs-lookup"><span data-stu-id="d1c89-118">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="d1c89-119">Ao fechar o assistente, o Confiança de Terceiros Confiável para o eSTS de serviços do Office 365 é estabelecido.</span><span class="sxs-lookup"><span data-stu-id="d1c89-119">By closing the wizard, the Relying Party Trust to the Office 365 services eSTS is established.</span></span> <span data-ttu-id="d1c89-120">No entanto, nenhuma regra de Transformação de Emissão é estabelecida.</span><span class="sxs-lookup"><span data-stu-id="d1c89-120">However, no Issuance Transform rules are established.</span></span>

<span data-ttu-id="d1c89-121">Você pode usar [a Ajuda do AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) para gerar as regras corretas de Transformação de Emissão.</span><span class="sxs-lookup"><span data-stu-id="d1c89-121">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="d1c89-122">As regras de declaração geradas criadas com a Ajuda do AD FS podem ser adicionadas manualmente por meio do console de gerenciamento do AD FS ou com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1c89-122">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="d1c89-123">A Ajuda do AD FS gerará os scripts necessários do PowerShell que precisam ser executados.</span><span class="sxs-lookup"><span data-stu-id="d1c89-123">AD FS Help will generate the necessary PowerShell scripts that need to be run.</span></span>  

1. <span data-ttu-id="d1c89-124">Execute **Gerar Declarações na** ajuda do AD FS e  copie o script de transformação de declarações do PowerShell usando a opção Copiar no canto superior direito do script.</span><span class="sxs-lookup"><span data-stu-id="d1c89-124">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="d1c89-125">Colar o PowerShell gerado no seguinte:</span><span class="sxs-lookup"><span data-stu-id="d1c89-125">Paste the generated PowerShell into the following:</span></span>

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  <span data-ttu-id="d1c89-126">Execute o script concluído.</span><span class="sxs-lookup"><span data-stu-id="d1c89-126">Execute the completed script.</span></span>
4.  <span data-ttu-id="d1c89-127">Verifique se duas confianças de Terceiros Confiável estão presentes; um para todo o mundo e outro para BF.</span><span class="sxs-lookup"><span data-stu-id="d1c89-127">Verify that two Relying Party trusts are present; one for worldwide and one for BF.</span></span>
5.  <span data-ttu-id="d1c89-128">Faça backup de suas confianças [usando estas etapas.](#backup)</span><span class="sxs-lookup"><span data-stu-id="d1c89-128">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="d1c89-129">Salve-o com o **nome FFAndWorldwide**.</span><span class="sxs-lookup"><span data-stu-id="d1c89-129">Save it with the name **FFAndWorldwide**.</span></span>
6.  <span data-ttu-id="d1c89-130">Conclua a migração de back-end e verifique se o AD FS ainda funciona durante o processo de migração.</span><span class="sxs-lookup"><span data-stu-id="d1c89-130">Complete your backend migration and verify that AD FS still works during migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="d1c89-131">Recuperação de desastre do AD FS (banco de dados WID)</span><span class="sxs-lookup"><span data-stu-id="d1c89-131">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="d1c89-132">Para restaurar o farm do AD FS em um desastre, a Ferramenta de Restauração Rápida do [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) precisa ser aproveitada.</span><span class="sxs-lookup"><span data-stu-id="d1c89-132">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="d1c89-133">Portanto, a ferramenta deve ser baixada e, antes do início da migração, um backup deve ser criado e armazenado com segurança.</span><span class="sxs-lookup"><span data-stu-id="d1c89-133">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="d1c89-134">Neste exemplo (ambientes DOLS), os seguintes comandos foram executados para fazer o back up do farm:</span><span class="sxs-lookup"><span data-stu-id="d1c89-134">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="d1c89-135">Fazer o back up de um farm do AD FS</span><span class="sxs-lookup"><span data-stu-id="d1c89-135">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="d1c89-136">Instale a Ferramenta de Restauração Rápida do AD FS no servidor AD FS principal.</span><span class="sxs-lookup"><span data-stu-id="d1c89-136">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="d1c89-137">Importe o módulo em uma sessão do PowerShell com este comando.</span><span class="sxs-lookup"><span data-stu-id="d1c89-137">Import the module in a PowerShell session with this command.</span></span>

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. <span data-ttu-id="d1c89-138">Execute o comando de backup:</span><span class="sxs-lookup"><span data-stu-id="d1c89-138">Run the backup command:</span></span>

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. <span data-ttu-id="d1c89-139">Armazene o backup com segurança em um destino desejado.</span><span class="sxs-lookup"><span data-stu-id="d1c89-139">Store the backup safely on a desired destination.</span></span> 

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="d1c89-140">Restaurar um farm do AD FS</span><span class="sxs-lookup"><span data-stu-id="d1c89-140">Restore an AD FS Farm</span></span>

<span data-ttu-id="d1c89-141">Se o farm falhar completamente e não houver como retornar ao farm antigo, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="d1c89-141">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="d1c89-142">Mova o backup gerado e armazenado anteriormente para o novo servidor primário do AD FS.</span><span class="sxs-lookup"><span data-stu-id="d1c89-142">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="d1c89-143">Execute o seguinte `Restore-ADFS` comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1c89-143">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="d1c89-144">Se necessário, importe o certificado SSL do AD FS com antecedência.</span><span class="sxs-lookup"><span data-stu-id="d1c89-144">If necessary, import the AD FS SSL certificate beforehand.</span></span>

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. <span data-ttu-id="d1c89-145">Aponte seus novos registros DNS ou balanceador de carga para os novos servidores do AD FS.</span><span class="sxs-lookup"><span data-stu-id="d1c89-145">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="d1c89-146">Mais informações</span><span class="sxs-lookup"><span data-stu-id="d1c89-146">More information</span></span>

<span data-ttu-id="d1c89-147">Iniciando:</span><span class="sxs-lookup"><span data-stu-id="d1c89-147">Getting started:</span></span>

- [<span data-ttu-id="d1c89-148">Migração do Microsoft Cloud Deutschland para os serviços do Office 365 nas novas regiões de datacenter alemãs</span><span class="sxs-lookup"><span data-stu-id="d1c89-148">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="d1c89-149">Assistência de Migração do Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="d1c89-149">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="d1c89-150">Como aceitar a migração</span><span class="sxs-lookup"><span data-stu-id="d1c89-150">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="d1c89-151">Experiência do cliente durante a migração</span><span class="sxs-lookup"><span data-stu-id="d1c89-151">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="d1c89-152">Passando pela transição:</span><span class="sxs-lookup"><span data-stu-id="d1c89-152">Moving through the transition:</span></span>

- [<span data-ttu-id="d1c89-153">Ações e impactos das fases de migração</span><span class="sxs-lookup"><span data-stu-id="d1c89-153">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="d1c89-154">Pré-trabalho adicional</span><span class="sxs-lookup"><span data-stu-id="d1c89-154">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="d1c89-155">Informações adicionais para [o Azure AD](ms-cloud-germany-transition-azure-ad.md), [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="d1c89-155">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="d1c89-156">Aplicativos em nuvem:</span><span class="sxs-lookup"><span data-stu-id="d1c89-156">Cloud apps:</span></span>

- [<span data-ttu-id="d1c89-157">Informações do programa de migração do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="d1c89-157">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="d1c89-158">Informações do programa de migração do Power BI</span><span class="sxs-lookup"><span data-stu-id="d1c89-158">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="d1c89-159">Introdução à atualização do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1c89-159">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
