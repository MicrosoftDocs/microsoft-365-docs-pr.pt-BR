---
title: Etapas de migração do AD FS para a migração do Microsoft Cloud Alemanha
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
description: 'Resumo: etapas de migração dos serviços de Federação do Active Directory (AD FS) para a migração do Microsoft Cloud Alemanha.'
ms.openlocfilehash: c946ec3c0772cf95ab696266475b50959d682ef2
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688653"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Etapas de migração do AD FS para a migração do Microsoft Cloud Alemanha

Para migrar o farm dos serviços de Federação do Active Directory (AD FS) do Microsoft Cloud Alemanha:

1. Faça backup das configurações do AD FS, incluindo as informações de confiança FF com [estas etapas](#backup). Nomeie o backup da **nuvem da microsoft Deutschland_Only** para indicar que ele tem apenas as informações de locatário do Microsoft Cloud Alemanha.
2. Testar a restauração usando o backup do Deutschland_Only de nuvem da Microsoft, o farm do AD FS deve continuar a operar somente como o Microsoft Cloud Alemanha.
3. Criar um novo confiança de terceira parte confiável do **AD FS > serviços do Office 365**.
4. Em **relações de confiança** de terceira parte confiável no console de gerenciamento do AD FS, selecione **Adicionar confiança de terceira parte confiável**.
5. Selecione **Avançar** na página de **boas-vindas** do assistente para adicionar confiança de terceira parte confiável.
6. Na página **selecionar fonte de dados** , selecione **importar dados sobre a terceira parte confiável publicada online ou em uma rede local**. O valor do **endereço de metadados da Federação (nome do host ou URL)** está definido como `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Clique em **Avançar**.
7. Na página **selecionar fonte de dados** , digite o nome para exibição. A Microsoft recomenda a **plataforma de identidade do Microsoft Office 365 em todo o mundo**. Clique em **Avançar**.
8. Clique em **Avançar** para **Configurar a autenticação multifator agora?**, **escolha regras de autorização de emissão** e **pronto para adicionar páginas de confiança** .
9. Clique em **fechar** na página **concluir** .

Ao fechar o assistente, a confiança da terceira parte confiável para o eSTS de serviços do Office 365 é estabelecida. No entanto, nenhuma regra de transformação de emissão é estabelecida.

Você pode usar a [ajuda do AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) para gerar as regras de transformação de emissão corretas. As regras de declaração geradas criadas com a ajuda do AD FS podem ser manualmente adicionadas por meio do console de gerenciamento do AD FS ou do PowerShell. A ajuda do AD FS irá gerar os scripts necessários do PowerShell que precisam ser executados.  

1. Execute **gerar declarações** na ajuda do AD FS e copie o script de transformação de declarações do PowerShell usando a opção **Copy** no canto superior direito do script.
2. Cole o PowerShell gerado no seguinte:

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  Executar o script concluído.
4.  Verifique se duas relações de confiança de terceira parte confiável estão presentes; um para o mundo e outro para o BF.
5.  Faça backup de suas relações de confiança usando [estas etapas](#backup). Salve-o com o nome **FFAndWorldwide**.
6.  Conclua a migração de backend e verifique se o AD FS ainda funciona durante o processo de migração.

## <a name="ad-fs-disaster-recovery-wid-database"></a>Recuperação de desastre do AD FS (banco de dados WID)

Para restaurar o farm do AD FS em uma [ferramenta de restauração rápida do AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) de desastres precisa ser aproveitado. Portanto, a ferramenta deve ser baixada e antes do início da migração um backup deve ser criado e armazenado com segurança. Neste exemplo (ambientes de TAT) os seguintes comandos foram executados para fazer o backup do farm:

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>Fazer backup de um farm do AD FS

1. Instale a ferramenta de restauração rápida do AD FS no servidor primário do AD FS.
2. Importe o módulo em uma sessão do PowerShell com esse comando.

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. Execute o comando de backup:

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. Armazene o backup com segurança em um destino desejado. 

### <a name="restore-an-ad-fs-farm"></a>Restaurar um farm do AD FS

Se o farm falhou completamente e não há uma maneira de retornar ao farm antigo, faça o seguinte. 

1. Mova o backup gerado e armazenado anteriormente para o novo servidor do AD FS principal.
2. Execute o comando do PowerShell a seguir `Restore-ADFS` . Se necessário, importe o certificado SSL do AD FS antecipadamente.

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. Aponte seus novos registros DNS ou balanceador de carga para os novos servidores do AD FS.

## <a name="more-information"></a>Mais informações

Introdução:

- [Migração do Microsoft Cloud Alemanha para os serviços do Office 365 nas novas regiões do datacenter alemão](ms-cloud-germany-transition.md)
- [Assistência de Migração do Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Como aceitar a migração](ms-cloud-germany-migration-opt-in.md)
- [Experiência do cliente durante a migração](ms-cloud-germany-transition-experience.md)

Mover-se pela transição:

- [Ações e impactos das fases de migração](ms-cloud-germany-transition-phases.md)
- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)
- Informações adicionais para o [Azure ad](ms-cloud-germany-transition-azure-ad.md), [dispositivos](ms-cloud-germany-transition-add-devices.md), [experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicativos de nuvem:

- [Informações do programa de migração do Dynamics 365](https://aka.ms/d365ceoptin)
- [Informações do programa de migração do Power BI](https://aka.ms/pbioptin)
- [Introdução à atualização do Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
