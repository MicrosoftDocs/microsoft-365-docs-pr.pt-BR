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
ms.openlocfilehash: 12465acf5b4afe7e252586ddd076250628b57dd3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165652"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="e21be-103">Etapas de migração do AD FS para a migração do Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="e21be-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="e21be-104">Essa alteração de configuração precisa ser aplicada a qualquer momento antes do início da fase 2.</span><span class="sxs-lookup"><span data-stu-id="e21be-104">This configuration change needs to be applied any time before phase 2 is starting.</span></span>
<span data-ttu-id="e21be-105">Depois que a fase 2 for concluída, a alteração de configuração funcionará e você poderá entrar Office 365 pontos de extremidade globais, como `https://portal.office.com` .</span><span class="sxs-lookup"><span data-stu-id="e21be-105">Once phase 2 is completed the configuration change will work and you are able to sign in via Office 365 Global endpoints such as `https://portal.office.com`.</span></span> <span data-ttu-id="e21be-106">Se você estiver implementando a alteração de configuração antes da fase  2, os pontos de extremidade globais do Office 365 ainda não funcionarão, mas a nova confiança de parte confiável ainda faz parte da configuração dos Serviços de Federação do Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="e21be-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="e21be-107">Os clientes que usam autenticação federada com os Serviços de Federação do Active Directory (AD FS) não devem fazer alterações nas URIs do emissor que são usadas para todas as autenticações com os Serviços de Domínio do Active Directory (AD DS) locais durante a migração.</span><span class="sxs-lookup"><span data-stu-id="e21be-107">Customers who use federated authentication with Active Directory Federation Services (AD FS) shouldn't make changes to issuer URIs that are used for all authentications with on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="e21be-108">Alterar URIs do emissor levará a falhas de autenticação para usuários no domínio.</span><span class="sxs-lookup"><span data-stu-id="e21be-108">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="e21be-109">URIs do emissor podem ser alteradas diretamente no AD  FS ou quando um domínio é convertido de gerenciado para _federado_ e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="e21be-109">Issuer URIs can be changed directly in AD FS or when a domain is converted from _managed_ to _federated_ and vice-versa.</span></span> <span data-ttu-id="e21be-110">Recomendamos que você não adicione, remova ou converta um domínio federado no locatário do Azure AD que foi migrado.</span><span class="sxs-lookup"><span data-stu-id="e21be-110">We recommend that you do not add, remove, or convert a federated domain in the Azure AD tenant that has been migrated.</span></span> <span data-ttu-id="e21be-111">As URIs do emissor podem ser alteradas depois que a migração estiver completa.</span><span class="sxs-lookup"><span data-stu-id="e21be-111">Issuer URIs can be changed after the migration is fully complete.</span></span>

<span data-ttu-id="e21be-112">Para preparar seu farm do AD FS para a migração do Microsoft Cloud Deutschland, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="e21be-112">To prepare your AD FS farm for the migration from Microsoft Cloud Deutschland perform the following steps:</span></span>

1. <span data-ttu-id="e21be-113">Fazer o back up your AD FS settings, including the existing Microsoft Cloud Deutschland Relying Party trust, with [these steps](#backup).</span><span class="sxs-lookup"><span data-stu-id="e21be-113">Back up your AD FS settings, including the existing Microsoft Cloud Deutschland Relying Party trust, with [these steps](#backup).</span></span> <span data-ttu-id="e21be-114">Nomeia o backup **do MicrosoftCloudDeutschlandOnly** para indicar que ele tem apenas as informações de locatário do Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="e21be-114">Name the backup **MicrosoftCloudDeutschlandOnly** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e21be-115">O backup conterá não apenas a confiança de Office 365 de terceiros confiável para o Microsoft Cloud Deutschland, mas também todas as outras Confianças de Parte Confiável presentes no respectivo farm do AD FS.</span><span class="sxs-lookup"><span data-stu-id="e21be-115">The backup will not only contain the existing Office 365 Relying Party Trust for Microsoft Cloud Deutschland, but also all other Relying Party Trusts present on the respective AD FS farm.</span></span>

2. <span data-ttu-id="e21be-116">Teste a restauração usando o backup do MicrosoftCloudDeutschlandOnly, o farm do AD FS deve continuar a operar como Microsoft Cloud Deutschland somente.</span><span class="sxs-lookup"><span data-stu-id="e21be-116">Test the restore using the MicrosoftCloudDeutschlandOnly backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="e21be-117">Depois de concluir e testar o backup do AD FS, execute as etapas a seguir para adicionar uma nova confiança de terceiros confiável à configuração do ADFS:</span><span class="sxs-lookup"><span data-stu-id="e21be-117">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="e21be-118">Abra o de gerenciamento AD FS.</span><span class="sxs-lookup"><span data-stu-id="e21be-118">Open the AD FS management console.</span></span>

2. <span data-ttu-id="e21be-119">No painel esquerdo do console de gerenciamento do ADFS, navegue até o menu **Confianças da Parte Confiável.**</span><span class="sxs-lookup"><span data-stu-id="e21be-119">In the left pane of the ADFS management console navigate to the **Relying Party Trusts** menu.</span></span>

3. <span data-ttu-id="e21be-120">No painel direito, selecione **Adicionar Confiança de Parte Confiável...**</span><span class="sxs-lookup"><span data-stu-id="e21be-120">In the right pane, select **Add Relying Party Trust...**</span></span>

4. <span data-ttu-id="e21be-121">Selecione **Iniciar** na página **De boas-vindas** do assistente Adicionar Confiança de Parte Confiável.</span><span class="sxs-lookup"><span data-stu-id="e21be-121">Select **Start** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>

5. <span data-ttu-id="e21be-122">Na página **Selecionar Fonte de** Dados, selecione Importar dados sobre a parte confiável publicada online ou em uma rede **local.**</span><span class="sxs-lookup"><span data-stu-id="e21be-122">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="e21be-123">O **valor do endereço de metadados de** federação (nome do host ou URL) deve ser definido como `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="e21be-123">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="e21be-124">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e21be-124">Click **Next**.</span></span>

6. <span data-ttu-id="e21be-125">Na página **Especificar Nome de Exibição,** digite o nome de exibição como Microsoft Office 365 Identity **Platform WorldWide**.</span><span class="sxs-lookup"><span data-stu-id="e21be-125">On the **Specify Display Name** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="e21be-126">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e21be-126">Click **Next**.</span></span>

7. <span data-ttu-id="e21be-127">Se você estiver usando o ADFS no Windows Server 2012, na página do assistente Configurar Autenticação **Multifator Agora?**, selecione a escolha apropriada de acordo com seus requisitos de autenticação.</span><span class="sxs-lookup"><span data-stu-id="e21be-127">If you are using ADFS in Windows Server 2012, on the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="e21be-128">Se você permanecer com o padrão, selecione Não quero configurar configurações de autenticação multifator para essa confiança de parte confiável **neste momento**.</span><span class="sxs-lookup"><span data-stu-id="e21be-128">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="e21be-129">Você pode alterar essa configuração mais tarde, se quiser.</span><span class="sxs-lookup"><span data-stu-id="e21be-129">You can change this setting later if you want to.</span></span>

8. <span data-ttu-id="e21be-130">Para o AD FS 2012: na opção Escolher  Regras de Autorização de Emissão, mantenha Permitir que todos os usuários acessem essa parte de confiança selecionada e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e21be-130">For AD FS 2012: On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected and click **Next**.</span></span>

9. <span data-ttu-id="e21be-131">Para o AD FS 2016 e o AD  FS 2019: na página Escolher Política de Controle de Acesso, selecione a política de controle de acesso apropriada e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e21be-131">For AD FS 2016 and AD FS 2019: On the **Choose Access Control Policy** page, select the appropriate access control policy and click **Next**.</span></span> <span data-ttu-id="e21be-132">Se nenhuma for escolhida, a Confiança da Parte Confiável **NÃO funcionará.**</span><span class="sxs-lookup"><span data-stu-id="e21be-132">If none is chosen, the Relying Party Trust will **NOT** work.</span></span>

10. <span data-ttu-id="e21be-133">Clique **em Próximo** na página Pronto para Adicionar **Confiança** para concluir o assistente.</span><span class="sxs-lookup"><span data-stu-id="e21be-133">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>

11. <span data-ttu-id="e21be-134">Clique **em Fechar** na página Concluir. </span><span class="sxs-lookup"><span data-stu-id="e21be-134">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="e21be-135">Ao fechar o assistente, a Confiança de Parte Confiável com o Office 365 Global é estabelecida.</span><span class="sxs-lookup"><span data-stu-id="e21be-135">By closing the wizard, the Relying Party Trust with the Office 365 Global service is established.</span></span> <span data-ttu-id="e21be-136">No entanto, nenhuma regra de Transformação de Emissão ainda está configurada.</span><span class="sxs-lookup"><span data-stu-id="e21be-136">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="e21be-137">Você pode usar [a Ajuda do AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) para gerar as regras corretas de Transformação de Emissão.</span><span class="sxs-lookup"><span data-stu-id="e21be-137">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="e21be-138">As regras de declaração geradas criadas com a Ajuda do AD FS podem ser adicionadas manualmente por meio do console de gerenciamento do AD FS ou com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e21be-138">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="e21be-139">A Ajuda do AD FS gerará os scripts necessários do PowerShell que precisam ser executados.</span><span class="sxs-lookup"><span data-stu-id="e21be-139">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

> [!NOTE]
> <span data-ttu-id="e21be-140">[A Ajuda do AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) gerará as regras padrão de transformação de emissão que são fornecidas com o produto.</span><span class="sxs-lookup"><span data-stu-id="e21be-140">[AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) will generate the standard issuance transform rules that ship with the product.</span></span> <span data-ttu-id="e21be-141">No entanto, se as regras de transformação de emissão personalizadas estão em vigor na Microsoft Cloud Deutschland Relying Party Trust (por exemplo, URIs de emissor personalizado, IDs imutáveis não padrão ou qualquer outra personalização), as regras geradas pela ajuda do AD FS devem ser modificadas de forma que elas se ajustem à lógica personalizada atualmente em vigor para a confiança da parte confiável do Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="e21be-141">However, if custom issuance transform rules are in place in the Microsoft Cloud Deutschland Relying Party Trust (for example, custom issuer URIs, non-standard immutable IDs, or any other customizations), the rules generated by AD FS help must be modified in a way that they fit the custom logic currently in place for the Microsoft Cloud Deutschland relying party trust.</span></span> <span data-ttu-id="e21be-142">Se essas personalizações não são integradas às regras geradas por meio da Ajuda do  [AD FS,](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)a autenticação para Microsoft Office 365 **Identity Platform WorldWide** provavelmente não funcionará para suas identidades federadas.</span><span class="sxs-lookup"><span data-stu-id="e21be-142">If these customizations are not integrated in the rules generated via [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator), authentication to **Microsoft Office 365 Identity Platform WorldWide** will most likely **not** work for your federated identities.</span></span>

1. <span data-ttu-id="e21be-143">Execute **Gerar Declarações** na Ajuda [do AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) e copie o script do PowerShell usando a opção Copiar no canto superior direito do script. </span><span class="sxs-lookup"><span data-stu-id="e21be-143">Run **Generate Claims** on [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) and copy the PowerShell script using the **Copy** option on the right upper corner of the script.</span></span>

2. <span data-ttu-id="e21be-144">Siga as etapas descritas na Ajuda do [AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) sobre como executar o script do PowerShell em seu farm do AD FS para gerar a Confiança de Parte Confiável global.</span><span class="sxs-lookup"><span data-stu-id="e21be-144">Follow the steps outlined at [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) on how to run the PowerShell script in your AD FS farm to generate the global Relying Party Trust.</span></span> <span data-ttu-id="e21be-145">Antes de executar o script, substitua as seguintes linhas de código no script gerado conforme descrito abaixo:</span><span class="sxs-lookup"><span data-stu-id="e21be-145">Before you run the script, replace the following code lines in the generated script as outlined below:</span></span>

   ```powershell
   # AD FS Help generated value
   $claims = Get-AdfsRelyingPartyTrust -Identifier $(Get-RpIdentifier) | Select-Object IssuanceTransformRules;
   # replace with
   $claims = Get-AdfsRelyingPartyTrust -Identifier urn:federation:MicrosoftOnline | Select-Object IssuanceTransformRules;

   # AD FS Help generated value
   Set-AdfsRelyingPartyTrust -TargetIdentifier $(Get-RpIdentifier) -IssuanceTransformRules $RuleSet.ClaimRulesString;
   # replace with
   Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:MicrosoftOnline -IssuanceTransformRules $RuleSet.ClaimRulesString;
   ```

3. <span data-ttu-id="e21be-146">Verifique se duas PartyTtrusts De base estão presentes; um para o Microsoft Cloud Deutschland e outro para o serviço Office 365 Global.</span><span class="sxs-lookup"><span data-stu-id="e21be-146">Verify that two Relying PartyTtrusts are present; one for Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span> <span data-ttu-id="e21be-147">O comando a seguir pode ser aproveitado para a verificação.</span><span class="sxs-lookup"><span data-stu-id="e21be-147">The following command can be leveraged for the check.</span></span> <span data-ttu-id="e21be-148">Ele deve retornar duas linhas e os respectivos nomes e identificadores.</span><span class="sxs-lookup"><span data-stu-id="e21be-148">It should return two rows and the respective names and identifiers.</span></span>

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. <span data-ttu-id="e21be-149">Faça backup de sua configuração de migração completa, incluindo ambas as confianças de Parte Confiável, usando [estas etapas.](#backup)</span><span class="sxs-lookup"><span data-stu-id="e21be-149">Backup your full migration configuration, including both Relying Party trusts, using [these steps](#backup).</span></span> <span data-ttu-id="e21be-150">Salve-o com o nome **MicrosoftCloudDeutschlandAndWorldwide**.</span><span class="sxs-lookup"><span data-stu-id="e21be-150">Save it with the name **MicrosoftCloudDeutschlandAndWorldwide**.</span></span>

5. <span data-ttu-id="e21be-151">Enquanto seu locatário estiver em migração, verifique regularmente se a autenticação do AD FS está funcionando com o Microsoft Cloud Deutschland e a nuvem global da Microsoft nas várias etapas de migração com suporte.</span><span class="sxs-lookup"><span data-stu-id="e21be-151">While your tenant is in migration, regularly verify that AD FS authentication is working with Microsoft Cloud Deutschland and Microsoft Global cloud in the various supported migration steps.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="e21be-152">Recuperação de Desastre do AD FS (Banco de Dados WID)</span><span class="sxs-lookup"><span data-stu-id="e21be-152">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="e21be-153">Para restaurar o farm do AD FS em um desastre, a Ferramenta de Restauração Rápida do [AD FS](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) precisa ser aproveitada.</span><span class="sxs-lookup"><span data-stu-id="e21be-153">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="e21be-154">Portanto, a ferramenta deve ser baixada e, antes do início da migração, um backup deve ser criado e armazenado com segurança.</span><span class="sxs-lookup"><span data-stu-id="e21be-154">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="e21be-155">Neste exemplo, os seguintes comandos foram executados para fazer o back up de um farm em execução em um banco de dados WID:</span><span class="sxs-lookup"><span data-stu-id="e21be-155">In this example, the following commands have been run to back up a farm running on a WID database:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="e21be-156">Back up an AD FS Farm</span><span class="sxs-lookup"><span data-stu-id="e21be-156">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="e21be-157">Instale a Ferramenta de Restauração Rápida do AD FS no servidor principal do AD FS.</span><span class="sxs-lookup"><span data-stu-id="e21be-157">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>

2. <span data-ttu-id="e21be-158">Importe o módulo em uma sessão do PowerShell com este comando.</span><span class="sxs-lookup"><span data-stu-id="e21be-158">Import the module in a PowerShell session with this command.</span></span>

   ```powershell
   Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
   ```

3. <span data-ttu-id="e21be-159">Execute o comando de backup:</span><span class="sxs-lookup"><span data-stu-id="e21be-159">Run the backup command:</span></span>

   ```powershell
   Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
   ```

4. <span data-ttu-id="e21be-160">Armazene o backup com segurança em um destino desejado.</span><span class="sxs-lookup"><span data-stu-id="e21be-160">Store the backup safely on a desired destination.</span></span>

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="e21be-161">Restaurar um farm do AD FS</span><span class="sxs-lookup"><span data-stu-id="e21be-161">Restore an AD FS Farm</span></span>

<span data-ttu-id="e21be-162">Se o farm falhou completamente e não há como retornar ao farm antigo, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="e21be-162">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="e21be-163">Mova o backup gerado e armazenado anteriormente para o novo servidor AD FS principal.</span><span class="sxs-lookup"><span data-stu-id="e21be-163">Move the previously generated and stored backup to the new primary AD FS server.</span></span>

2. <span data-ttu-id="e21be-164">Execute o seguinte `Restore-ADFS` comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e21be-164">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="e21be-165">Se necessário, importe o certificado SSL do AD FS antecipadamente.</span><span class="sxs-lookup"><span data-stu-id="e21be-165">If necessary, import the AD FS SSL certificate beforehand.</span></span>

   ```powershell
   Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
   ```

3. <span data-ttu-id="e21be-166">Aponte seus novos registros DNS ou balanceador de carga para os novos servidores do AD FS.</span><span class="sxs-lookup"><span data-stu-id="e21be-166">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="e21be-167">Mais informações</span><span class="sxs-lookup"><span data-stu-id="e21be-167">More information</span></span>

<span data-ttu-id="e21be-168">Como começar:</span><span class="sxs-lookup"><span data-stu-id="e21be-168">Getting started:</span></span>

- [<span data-ttu-id="e21be-169">Migração do Microsoft Cloud Deutschland para serviços Office 365 nas novas regiões do datacenter alemão</span><span class="sxs-lookup"><span data-stu-id="e21be-169">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="e21be-170">Assistência de Migração do Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="e21be-170">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="e21be-171">Como aceitar a migração</span><span class="sxs-lookup"><span data-stu-id="e21be-171">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="e21be-172">Experiência do cliente durante a migração</span><span class="sxs-lookup"><span data-stu-id="e21be-172">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="e21be-173">Movendo-se pela transição:</span><span class="sxs-lookup"><span data-stu-id="e21be-173">Moving through the transition:</span></span>

- [<span data-ttu-id="e21be-174">Ações e impactos das fases de migração</span><span class="sxs-lookup"><span data-stu-id="e21be-174">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="e21be-175">Pré-trabalho adicional</span><span class="sxs-lookup"><span data-stu-id="e21be-175">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="e21be-176">Informações adicionais para [o Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos, experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md). [](ms-cloud-germany-transition-add-devices.md)</span><span class="sxs-lookup"><span data-stu-id="e21be-176">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="e21be-177">Aplicativos de nuvem:</span><span class="sxs-lookup"><span data-stu-id="e21be-177">Cloud apps:</span></span>

- [<span data-ttu-id="e21be-178">Informações do programa de migração do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e21be-178">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="e21be-179">Informações do programa de migração do Power BI</span><span class="sxs-lookup"><span data-stu-id="e21be-179">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="e21be-180">Introdução à atualização do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e21be-180">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)
