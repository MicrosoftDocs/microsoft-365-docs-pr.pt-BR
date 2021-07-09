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
ms.openlocfilehash: c8e784c8e582185b4bdebc0cb359cc4c19503d1a
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339605"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Etapas de migração do AD FS para a migração do Microsoft Cloud Deutschland

Essa alteração de configuração precisa ser aplicada a qualquer momento antes do início da fase 2.
Depois que a fase 2 for concluída, a alteração de configuração funcionará e você poderá entrar Office 365 pontos de extremidade globais, como `https://admin.microsoft.com` . Se você estiver implementando a alteração de configuração antes da fase  2, os pontos de extremidade globais do Office 365 ainda não funcionarão, mas a nova confiança de parte confiável ainda faz parte da configuração dos Serviços de Federação do Active Directory (AD FS).

Os clientes que usam autenticação federada com os Serviços de Federação do Active Directory (AD FS) não devem fazer alterações nas URIs do emissor que são usadas para todas as autenticações com os Serviços de Domínio do Active Directory (AD DS) locais durante a migração. Alterar URIs do emissor levará a falhas de autenticação para usuários no domínio. URIs do emissor podem ser alteradas diretamente no AD  FS ou quando um domínio é convertido de gerenciado para _federado_ e vice-versa. Recomendamos que você não adicione, remova ou converta um domínio federado no locatário do Azure AD que foi migrado. As URIs do emissor podem ser alteradas depois que a migração estiver completa.

Para preparar seu farm do AD FS para a migração do Microsoft Cloud Deutschland, execute as seguintes etapas:

1. Fazer o back up your AD FS settings, including the existing Microsoft Cloud Deutschland Relying Party trust, with [these steps](#backup). Nomeia o backup **do MicrosoftCloudDeutschlandOnly** para indicar que ele tem apenas as informações de locatário do Microsoft Cloud Deutschland.

   > [!NOTE]
   > O backup conterá não apenas a confiança de Office 365 de terceiros confiável para o Microsoft Cloud Deutschland, mas também todas as outras Confianças de Parte Confiável presentes no respectivo farm do AD FS.

2. Teste a restauração usando o backup do MicrosoftCloudDeutschlandOnly, o farm do AD FS deve continuar a operar como Microsoft Cloud Deutschland somente.

Depois de concluir e testar o backup do AD FS, execute as etapas a seguir para adicionar uma nova confiança de terceiros confiável à configuração do ADFS:

1. Abra o de gerenciamento AD FS.

2. No painel esquerdo do console de gerenciamento do ADFS, navegue até o menu **Confianças da Parte Confiável.**

3. No painel direito, selecione **Adicionar Confiança de Parte Confiável...**

4. Selecione **Iniciar** na página **De boas-vindas** do assistente Adicionar Confiança de Parte Confiável.

5. Na página **Selecionar Fonte de** Dados, selecione Importar dados sobre a parte confiável publicada online ou em uma rede **local.** O **valor do endereço de metadados de** federação (nome do host ou URL) deve ser definido como `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Clique em **Avançar**.

6. Na página **Especificar Nome de Exibição,** digite o nome de exibição como Microsoft Office 365 Identity **Platform WorldWide**. Clique em **Avançar**.

7. Se você estiver usando o ADFS no Windows Server 2012, na página do assistente Configurar Autenticação **Multifator Agora?**, selecione a escolha apropriada de acordo com seus requisitos de autenticação. Se você permanecer com o padrão, selecione Não quero configurar configurações de autenticação multifator para essa confiança de parte confiável **neste momento**. Você pode alterar essa configuração mais tarde, se quiser.

8. Para o AD FS 2012: na opção Escolher  Regras de Autorização de Emissão, mantenha Permitir que todos os usuários acessem essa parte de confiança selecionada e clique em **Próximo**.

9. Para o AD FS 2016 e o AD  FS 2019: na página Escolher Política de Controle de Acesso, selecione a política de controle de acesso apropriada e clique em **Próximo**. Se nenhuma for escolhida, a Confiança da Parte Confiável **NÃO funcionará.**

10. Clique **em Próximo** na página Pronto para Adicionar **Confiança** para concluir o assistente.

11. Clique **em Fechar** na página Concluir. 

Ao fechar o assistente, a Confiança de Parte Confiável com o Office 365 Global é estabelecida. No entanto, nenhuma regra de Transformação de Emissão ainda está configurada.

Você pode usar [a Ajuda do AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) para gerar as regras corretas de Transformação de Emissão. As regras de declaração geradas criadas com a Ajuda do AD FS podem ser adicionadas manualmente por meio do console de gerenciamento do AD FS ou com o PowerShell. A Ajuda do AD FS gerará os scripts necessários do PowerShell que precisam ser executados.  

> [!NOTE]
> [A Ajuda do AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) gerará as regras padrão de transformação de emissão que são fornecidas com o produto. No entanto, se as regras de transformação de emissão personalizadas estão em vigor na Microsoft Cloud Deutschland Relying Party Trust (por exemplo, URIs de emissor personalizado, IDs imutáveis não padrão ou qualquer outra personalização), as regras geradas pela ajuda do AD FS devem ser modificadas de forma que elas se ajustem à lógica personalizada atualmente em vigor para a confiança da parte confiável do Microsoft Cloud Deutschland. Se essas personalizações não são integradas às regras geradas por meio da Ajuda do  [AD FS,](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)a autenticação para Microsoft Office 365 **Identity Platform WorldWide** provavelmente não funcionará para suas identidades federadas.

1. Execute **Gerar Declarações** na Ajuda [do AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) e copie o script do PowerShell usando a opção Copiar no canto superior direito do script. 

2. Siga as etapas descritas na Ajuda do [AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) sobre como executar o script do PowerShell em seu farm do AD FS para gerar a Confiança de Parte Confiável global. Antes de executar o script, substitua as seguintes linhas de código no script gerado conforme descrito abaixo:

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

3. Verifique se duas PartyTtrusts De base estão presentes; um para o Microsoft Cloud Deutschland e outro para o serviço Office 365 Global. O comando a seguir pode ser aproveitado para a verificação. Ele deve retornar duas linhas e os respectivos nomes e identificadores.

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. Faça backup de sua configuração de migração completa, incluindo ambas as confianças de Parte Confiável, usando [estas etapas.](#backup) Salve-o com o nome **MicrosoftCloudDeutschlandAndWorldwide**.

5. Enquanto seu locatário estiver em migração, verifique regularmente se a autenticação do AD FS está funcionando com o Microsoft Cloud Deutschland e a nuvem global da Microsoft nas várias etapas de migração com suporte.

## <a name="ad-fs-disaster-recovery-wid-database"></a>Recuperação de Desastre do AD FS (Banco de Dados WID)

Para restaurar o farm do AD FS em um desastre, a Ferramenta de Restauração Rápida do [AD FS](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) precisa ser aproveitada. Portanto, a ferramenta deve ser baixada e, antes do início da migração, um backup deve ser criado e armazenado com segurança. Neste exemplo, os seguintes comandos foram executados para fazer o back up de um farm em execução em um banco de dados WID:

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

## <a name="more-information"></a>Mais informações

Como começar:

- [Migração do Microsoft Cloud Deutschland para serviços Office 365 nas novas regiões do datacenter alemão](ms-cloud-germany-transition.md)
- [Assistência de Migração do Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Como aceitar a migração](ms-cloud-germany-migration-opt-in.md)
- [Experiência do cliente durante a migração](ms-cloud-germany-transition-experience.md)

Movendo-se pela transição:

- [Ações e impactos das fases de migração](ms-cloud-germany-transition-phases.md)
- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)
- Informações adicionais para [o Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos, experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md). [](ms-cloud-germany-transition-add-devices.md)

Aplicativos de nuvem:

- [Informações do programa de migração do Dynamics 365](/dynamics365/get-started/migrate-data-german-region)
- [Informações do programa de migração do Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here)
