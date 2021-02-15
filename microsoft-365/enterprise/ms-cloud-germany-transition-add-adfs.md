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
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Etapas de migração do AD FS para a migração do Microsoft Cloud Deutschland

Para migrar seu farm dos Serviços de Federação do Active Directory (AD FS) do Microsoft Cloud Deutschland:

1. Fazer o back up das configurações do AD FS, incluindo informações de confiança [FF, com estas etapas.](#backup) Nome do backup **do Microsoft Cloud Deutschland_Only** para indicar que ele tem apenas as informações de locatário do Microsoft Cloud Deutschland.
2. Teste a restauração usando o backup do Microsoft Cloud Deutschland_Only, o farm do AD FS deve continuar a operar apenas como Microsoft Cloud Deutschland.
3. Crie uma nova confiança de Terceiros Confiável a partir do **AD FS > serviços do Office 365.**
4. In **Relying Party Trusts** in the AD FS management console, select **Add Relying Party Trust**.
5. Selecione **Next na** página de **boas-vindas** do assistente Adicionar Confiança de Terceiros Confiável.
6. Na página **Selecionar Fonte de Dados,** selecione Importar dados sobre a confiança **de terceiros publicados online ou em uma rede local.** O **endereço de metadados de Federação (nome do host ou URL)** é definido como `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Clique em **Avançar**.
7. Na página **Selecionar Fonte de Dados,** digite o nome de exibição. A Microsoft recomenda **o Microsoft Office 365 Identity Platform WorldWide.** Clique em **Avançar**.
8. Click **Next** on the **Configure Multi-factor Authentication Now?**, **Choose Esuance Authorization Rules**, and Ready to Add **Trust** pages.
9. Clique **em Fechar** na **página** Concluir.

Ao fechar o assistente, o Confiança de Terceiros Confiável para o eSTS de serviços do Office 365 é estabelecido. No entanto, nenhuma regra de Transformação de Emissão é estabelecida.

Você pode usar [a Ajuda do AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) para gerar as regras corretas de Transformação de Emissão. As regras de declaração geradas criadas com a Ajuda do AD FS podem ser adicionadas manualmente por meio do console de gerenciamento do AD FS ou com o PowerShell. A Ajuda do AD FS gerará os scripts necessários do PowerShell que precisam ser executados.  

1. Execute **Gerar Declarações na** ajuda do AD FS e  copie o script de transformação de declarações do PowerShell usando a opção Copiar no canto superior direito do script.
2. Colar o PowerShell gerado no seguinte:

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  Execute o script concluído.
4.  Verifique se duas confianças de Terceiros Confiável estão presentes; um para todo o mundo e outro para BF.
5.  Faça backup de suas confianças [usando estas etapas.](#backup) Salve-o com o **nome FFAndWorldwide**.
6.  Conclua a migração de back-end e verifique se o AD FS ainda funciona durante o processo de migração.

## <a name="ad-fs-disaster-recovery-wid-database"></a>Recuperação de desastre do AD FS (banco de dados WID)

Para restaurar o farm do AD FS em um desastre, a Ferramenta de Restauração Rápida do [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) precisa ser aproveitada. Portanto, a ferramenta deve ser baixada e, antes do início da migração, um backup deve ser criado e armazenado com segurança. Neste exemplo (ambientes DOLS), os seguintes comandos foram executados para fazer o back up do farm:

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>Fazer o back up de um farm do AD FS

1. Instale a Ferramenta de Restauração Rápida do AD FS no servidor AD FS principal.
2. Importe o módulo em uma sessão do PowerShell com este comando.

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. Execute o comando de backup:

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. Armazene o backup com segurança em um destino desejado. 

### <a name="restore-an-ad-fs-farm"></a>Restaurar um farm do AD FS

Se o farm falhar completamente e não houver como retornar ao farm antigo, faça o seguinte. 

1. Mova o backup gerado e armazenado anteriormente para o novo servidor primário do AD FS.
2. Execute o seguinte `Restore-ADFS` comando do PowerShell. Se necessário, importe o certificado SSL do AD FS com antecedência.

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. Aponte seus novos registros DNS ou balanceador de carga para os novos servidores do AD FS.

## <a name="more-information"></a>Mais informações

Iniciando:

- [Migração do Microsoft Cloud Deutschland para os serviços do Office 365 nas novas regiões de datacenter alemãs](ms-cloud-germany-transition.md)
- [Assistência de Migração do Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Como aceitar a migração](ms-cloud-germany-migration-opt-in.md)
- [Experiência do cliente durante a migração](ms-cloud-germany-transition-experience.md)

Passando pela transição:

- [Ações e impactos das fases de migração](ms-cloud-germany-transition-phases.md)
- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)
- Informações adicionais para [o Azure AD](ms-cloud-germany-transition-azure-ad.md), [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicativos em nuvem:

- [Informações do programa de migração do Dynamics 365](https://aka.ms/d365ceoptin)
- [Informações do programa de migração do Power BI](https://aka.ms/pbioptin)
- [Introdução à atualização do Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
