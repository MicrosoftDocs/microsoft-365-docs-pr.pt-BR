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
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Etapas de migração do AD FS para a migração do Microsoft Cloud Deutschland

Essa alteração de configuração pode ser aplicada a qualquer momento antes do início da fase 4.
Depois que a fase 2 for concluída, a alteração de configuração funcionará e você poderá entrar nos pontos de extremidade globais do Office 365, como `https://portal.office.com` . Se você estiver implementando a alteração de configuração antes da fase  2, os pontos de extremidade globais do Office 365 ainda não funcionarão, mas a nova confiança de parte confiável ainda faz parte da configuração dos Serviços de Federação do Active Directory (AD FS).

Para migrar seu farm do AD FS do Microsoft Cloud Deutschland:

1. Fazer o back up your AD FS settings including FF trust info with [these steps](#backup). Nomeia o backup **do Microsoft Cloud Deutschland_Only** para indicar que ele tem apenas as informações de locatário do Microsoft Cloud Deutschland.
2. Teste a restauração usando o backup do Microsoft Cloud Deutschland_Only, o farm do AD FS deve continuar a operar como Microsoft Cloud Deutschland somente.

Depois de concluir e testar o backup do AD FS, execute as etapas a seguir para adicionar uma nova confiança de terceiros confiável à configuração do ADFS:

1. Abra o console de gerenciamento do AD FS
2. No painel esquerdo do console de gerenciamento do ADFS, expanda **a ADFS**, depois **relações** de confiança, e, em seguida, **confianças de terceiros confiável**
3. No painel direito, selecione **Adicionar Confiança de Parte Confiável...**
4. Selecione **Próximo** na página **Bem-vindo** do assistente Adicionar Confiança de Parte Confiável.
5. Na página **Selecionar Fonte de** Dados, selecione Importar dados sobre a parte confiável publicada online ou em uma rede **local.** O **valor do endereço de metadados de** federação (nome do host ou URL) deve ser definido como `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Em seguida, clique em **Avançar**.
6. Na página **Selecionar Fonte de** Dados, digite o nome de exibição como Microsoft Office **365 Identity Platform WorldWide**. Em seguida, clique em **Avançar**.
7. Na página do assistente **Configure Multifator Authentication Now?**, selecione a escolha apropriada de acordo com seus requisitos de autenticação. Se você permanecer com o padrão, selecione Não quero configurar configurações de autenticação multifator para essa confiança de parte confiável **neste momento**. Você pode alterar essa configuração mais tarde, se quiser.
8. Na opção **Escolher Regras** de Autorização de Emissão , mantenha Permitir que todos os usuários acessem essa parte **de** confiança selecionada clique em **Próximo**
9. Clique **em Próximo** na página Pronto para Adicionar **Confiança** para concluir o assistente.
10. Clique **em Fechar** na página Concluir. 

Ao fechar o assistente, a Confiança de Parte Confiável com os serviços Globais do Office 365 é estabelecida. No entanto, nenhuma regra de Transformação de Emissão ainda está configurada.

Você pode usar [a Ajuda do AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) para gerar as regras corretas de Transformação de Emissão. As regras de declaração geradas criadas com a Ajuda do AD FS podem ser adicionadas manualmente por meio do console de gerenciamento do AD FS ou com o PowerShell. A Ajuda do AD FS gerará os scripts necessários do PowerShell que precisam ser executados.  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. Execute **Gerar Declarações no** AD FS ajuda e copie o script de transformação de declarações do PowerShell usando a opção **Copiar** no canto superior direito do script.
2. Abra seu editor de texto preferencial e colar o script do PowerShell em uma nova janela de texto.
3. Adicione as seguintes linhas do PowerShell ao final do script pastado da etapa 2
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. Safe e execute o script do PowerShell.
5. Verifique se duas confianças de Parte Confiável estão presentes; um para o Microsoft Cloud Deutschland e outro para o serviço Global do Office 365.
6. Faça backup de suas confiações usando [estas etapas.](#backup) Salve-o com o nome **FFAndWorldwide**.
7. Conclua a migração de back-end e verifique se o AD FS ainda funciona durante o processo de migração.

## <a name="ad-fs-disaster-recovery-wid-database"></a>Recuperação de Desastre do AD FS (Banco de Dados WID)

Para restaurar o farm do AD FS em um desastre, a Ferramenta de Restauração Rápida do [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) precisa ser aproveitada. Portanto, a ferramenta deve ser baixada e, antes do início da migração, um backup deve ser criado e armazenado com segurança. Neste exemplo (ambientes DOAA) os seguintes comandos foram executados para fazer o back up do farm:

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>Back up an AD FS Farm

1. Instale a Ferramenta de Restauração Rápida do AD FS no servidor principal do AD FS.
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

Se o farm falhou completamente e não há como retornar ao farm antigo, faça o seguinte. 

1. Mova o backup gerado e armazenado anteriormente para o novo servidor AD FS principal.
2. Execute o seguinte `Restore-ADFS` comando do PowerShell. Se necessário, importe o certificado SSL do AD FS antecipadamente.

    ```powershell
    Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
    ```

3. Aponte seus novos registros DNS ou balanceador de carga para os novos servidores do AD FS.

## <a name="more-information"></a>Mais Informações

Como começar:

- [Migração do Microsoft Cloud Deutschland para serviços do Office 365 nas novas regiões do datacenter alemão](ms-cloud-germany-transition.md)
- [Assistência de Migração do Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Como aceitar a migração](ms-cloud-germany-migration-opt-in.md)
- [Experiência do cliente durante a migração](ms-cloud-germany-transition-experience.md)

Movendo-se pela transição:

- [Ações e impactos das fases de migração](ms-cloud-germany-transition-phases.md)
- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)
- Informações adicionais para [o Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos, experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md). [](ms-cloud-germany-transition-add-devices.md)

Aplicativos de nuvem:

- [Informações do programa de migração do Dynamics 365](https://aka.ms/d365ceoptin)
- [Informações do programa de migração do Power BI](https://aka.ms/pbioptin)
- [Introdução à atualização do Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
