---
title: Usar o PowerShell para executar uma migração em etapas para o Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: a20f9dbd-6102-4ffa-b72c-ff813e700930
description: Saiba como usar o PowerShell para mover conteúdo de um sistema de email de origem ao longo do tempo usando uma migração em estágios para o Microsoft 365.
ms.openlocfilehash: 0c93de181c54fb1c4021d23d787b63577317aad4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924787"
---
# <a name="use-powershell-to-perform-a-staged-migration-to-microsoft-365"></a>Usar o PowerShell para executar uma migração em etapas para o Microsoft 365

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Você pode migrar o conteúdo das caixas de correio de usuário de um sistema de email de origem para o Microsoft 365 ao longo do tempo usando uma migração em estágios.
  
Este artigo o orienta ao longo das tarefas envolvidas para uma migração em estágios de email usando o PowerShell do Exchange Online. O tópico, [O que você precisa saber sobre uma migração](/Exchange/mailbox-migration/what-to-know-about-a-staged-migration)de email em estágios, fornece uma visão geral do processo de migração. Quando você estiver familiarizado com os conteúdos do artigo, use o seguinte para começar a migrar caixas de correio de um sistema de email para outro.
  
> [!NOTE]
> Você também pode usar o Centro de administração do Exchange para executar a migração em estágios. Consulte [Executar uma migração em estágios de email para o Microsoft 365](/Exchange/mailbox-migration/perform-a-staged-migration/perform-a-staged-migration). 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

Tempo estimado para a conclusão da tarefa: 2-5 minutos para criar um lote de migração. Depois que o lote de migração é iniciado, a duração da migração irá variar com base no número de caixas de correio no lote, no tamanho de cada caixa de correio e na sua capacidade de rede disponível. Para obter informações sobre outros fatores que afetam quanto tempo leva para migrar caixas de correio para o Microsoft 365, consulte [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).
  
Para executar esses procedimentos, você precisa receber permissões. Para ver quais são as permissões necessárias, confira a entrada "Migração" no tópico [Permissões de destinatários](/exchange/recipients-permissions-exchange-2013-help).
  
Para usar os cmdlets do PowerShell do Exchange Online, você precisa entrar e importar os cmdlets para sua sessão local do Windows PowerShell. Confira [Conectar-se ao Exchange Online usando o PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell) para obter instruções.
  
Para obter uma lista completa dos comandos de migração, confira [Cmdlets de movimentação e migração](/powershell/exchange/).
  
## <a name="migration-steps"></a>Etapas da migração

### <a name="step-1-prepare-for-a-staged-migration"></a>Etapa 1: preparar para uma migração em estágios

Antes de migrar caixas de correio para o Microsoft 365 usando uma migração em estágios, há algumas alterações que você deve fazer no seu ambiente do Exchange.
  
 **Configurar o Outlook em Qualquer Lugar em seu Exchange Server** local O serviço de migração de email usa o Outlook em Qualquer Lugar (também conhecido como RPC sobre HTTP) para se conectar a seu Exchange Server local. Para saber mais sobre como configurar o Outlook em Qualquer Lugar para o Exchange Server 2007 e para o Exchange 2003, confira o seguinte:
  
- [Exchange 2007: Como Habilitar o Outlook em Qualquer Lugar](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))
    
- [Como configurar o Outlook em Qualquer Lugar com o Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))
    
> [!IMPORTANT]
> Você deve usar um certificado emitido por uma AC (autoridade de certificação) confiável com sua configuração do Outlook em Qualquer Lugar. O Outlook em Qualquer Lugar não pode ser configurado com um certificado autoassinado. Para saber mais, confira [Como configurar o SSL para o Outlook em Qualquer Lugar](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)) 
  
 **Opcional: Verifique se você pode se conectar à sua organização do Exchange usando o Outlook em Qualquer Lugar** Tente um dos métodos a seguir para testar as configurações de conexão.
  
- Use o Outlook fora de sua rede corporativa para se conectar a sua caixa de correio local do Exchange.
    
- Use o [Analisador de Conectividade Remota da Microsoft](https://https://testconnectivity.microsoft.com/) para testar as configurações de conexão. Use o Outlook em Qualquer Lugar (RPC sobre HTTP) ou os testes de Descoberta Automática do Outlook.
    
- Execute os seguintes comandos no PowerShell do Exchange Online:
    
  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

 **Definir permissões** A conta de usuário local que você usa para se conectar à sua organização local do Exchange (também chamada de administrador de migração) deve ter as permissões necessárias para acessar as caixas de correio locais que você deseja migrar para o Microsoft 365. Essa conta de usuário é usada quando você se conecta ao seu sistema de email criando um ponto de extremidade de migração posteriormente neste procedimento ( Etapa[3: Criar](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint) um ponto de extremidade de migração ).
  
Para migrar as caixas de correio, o administrador deve ter um dos seguintes conjuntos de permissão:
  
- Ser membro do grupo **Administradores de Domínio** no Active Directory na organização local.
    
    ou
    
- Ter a permissão **FullAccess** para cada caixa de correio local e a permissão **WriteProperty** para modificar a propriedade **TargetAddress** nas contas de usuário locais.
    
    ou
    
- Ter a permissão **Receive As** no banco de dados de caixa de correio local que armazena as caixas de correio do usuário e a permissão **WriteProperty** para modificar a propriedade **TargetAddress** nas contas de usuário locais.
    
Para obter instruções sobre como definir essas permissões, consulte Atribuir permissões para migrar caixas de correio [para o Microsoft 365](/Exchange/mailbox-migration/assign-permissions-for-migration).
  
 **Desabilitar a UM (Unificação de Mensagens)** Se a UM estiver habilitada para as caixas de correio locais que você está migrando, desabilite a UM antes da migração. Habilite a UM para as caixas de correio após a conclusão da migração. Para obter instruções, confira [desabilitar a unificação de mensagens](/previous-versions/office/exchange-server-2007/bb124691(v=exchg.80)).
  
 **Use a sincronização de diretórios para criar novos usuários no Microsoft 365.** Você usa a sincronização de diretórios para criar todos os usuários locais em sua organização do Microsoft 365.
  
Você precisa licenciar os usuários depois que eles são criados. O prazo é de 30 dias para adicionar licenças depois que os usuários são criados. Para obter as etapas para adicionar licenças, confira [Etapa 8: concluir tarefas pós-migração](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration).
  
 Você pode usar a Ferramenta de Sincronização do Microsoft Azure Active Directory (Azure AD) ou o Microsoft Azure AD Sync Services para sincronizar e criar seus usuários locais no Microsoft 365. Depois que as caixas de correio são migradas para o Microsoft 365, você gerencia contas de usuário em sua organização local e elas são sincronizadas com sua organização do Microsoft 365. Para obter mais informações, consulte[Integração de Diretórios](/previous-versions/azure/azure-services/jj573653(v=azure.100)) .
  
### <a name="step-2-create-a-csv-file-for-a-staged-migration-batch"></a>Etapa 2: criar um arquivo CSV para um lote de migração em estágios

Depois de identificar os usuários cujas caixas de correio locais você deseja migrar para o Microsoft 365, use um arquivo CSV (valor separado por vírgula) para criar um lote de migração. Cada linha no arquivo CSV , usada pelo Microsoft 365 para executar a migração, contém informações sobre uma caixa de correio local. 
  
> [!NOTE]
> Não há um limite para o número de caixas de correio que você pode migrar para o Microsoft 365 usando uma migração em estágios. O arquivo CSV para um lote de migração pode conter um máximo de 2.000 linhas. Para migrar mais de 2.000 caixas de correio, crie arquivos CSV adicionais e use cada arquivo para criar um novo lote de migração. 
  
 **Atributos com suporte**
  
O arquivo CSV para uma migração em estágios dá suporte aos três atributos a seguir. Cada linha no arquivo CSV corresponde a uma caixa de correio e deve conter um valor para cada um desses atributos.
  
|**Atributo**|**Descrição**|**Obrigatório?**|
|:-----|:-----|:-----|
|EmailAddress  <br/> |Especifica o endereço de email SMTP principal, por exemplo, laurac@contoso.com, para caixas de correio locais.  <br/> Use o endereço SMTP principal para caixas de correio locais e não IDs de usuário do Microsoft 365. Por exemplo, se o domínio local for chamado contoso.com, mas o domínio de email do Microsoft 365 for chamado service.contoso.com, você usará o nome de domínio contoso.com para endereços de email no arquivo CSV.  <br/> |Obrigatório  <br/> |
|Senha  <br/> |A senha a ser definida para a nova caixa de correio do Microsoft 365. Quaisquer restrições de senha aplicadas à sua organização do Microsoft 365 também se aplicam às senhas incluídas no arquivo CSV.  <br/> |Opcional  <br/> |
|ForceChangePassword  <br/> |Especifica se um usuário deve alterar a senha na primeira vez que entrar na nova caixa de correio do Microsoft 365. Use **True** ou **False** para o valor deste parâmetro. <br/> > [!NOTE]> Se você implementou uma solução de SSO (Logon Único) com a implantação do AD FS (Serviços de Federação do Active Directory) em sua organização local, deve usar **False** para o valor do atributo **ForceChangePassword**.          |Opcional  <br/> |
   
 **Formato de arquivo CSV**
  
Veja a seguir um exemplo do formato do arquivo CSV. Neste exemplo, três caixas de correio locais são migradas para o Microsoft 365.
  
A primeira linha, ou linha de cabeçalho, do arquivo CSV lista os nomes dos atributos ou campos especificados nas linhas a seguir. Cada nome de atributo é separado por uma vírgula.
  
```powershell
EmailAddress,Password,ForceChangePassword 
pilarp@contoso.com,Pa$$w0rd,False 
tobyn@contoso.com,Pa$$w0rd,False 
briant@contoso.com,Pa$$w0rd,False 
```

Cada linha embaixo da linha de cabeçalho representa um usuário e fornece as informações que serão utilizadas para migrar a caixa de correio dele. Os valores de atributo em cada linha devem estar na mesma ordem que os nomes dos atributos na linha de cabeçalho. 
  
Use qualquer editor de texto ou um aplicativo como o Excel para criar o arquivo CSV. Salve-o como um arquivo .csv ou .txt.
  
> [!NOTE]
> Se o arquivo CSV contiver caracteres não-ASCII ou especiais, salve-o com UTF-8 ou outra codificação Unicode. Dependendo do aplicativo, salvar o arquivo CSV com UTF-8 ou outra codificação Unicode pode ser mais fácil quando a localidade do sistema do computador corresponde ao idioma usado no arquivo CSV. 
  
### <a name="step-3-create-a-migration-endpoint"></a>Etapa 3: criar um ponto de extremidade de migração
<a name="BK_Endpoint"> </a>

Para migrar emails com êxito, o Microsoft 365 precisa se conectar e se comunicar com o sistema de email de origem. Para fazer isso, o Microsoft 365 usa um ponto de extremidade de migração. Para criar um ponto de extremidade de migração do Outlook Em Qualquer Lugar usando o PowerShell, para migração em estágios, [conecte-se](/powershell/exchange/connect-to-exchange-online-powershell)primeiro ao Exchange Online . 
  
Para obter uma lista completa dos comandos de migração, confira [Cmdlets de movimentação e migração](/powershell/exchange/).
  
Para criar um ponto de extremidade de migração do Outlook em Qualquer Lugar chamado "StagedEndpoint" no PowerShell do Exchange Online, execute os seguintes comandos:
  
```powershell
$Credentials = Get-Credential
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name StagedEndpoint -Autodiscover -EmailAddress administrator@contoso.com -Credentials $Credentials
```

Para saber mais sobre o cmdlet **New-MigrationEndpoint**, confira [New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint).
  
> [!NOTE]
> O cmdlet **New-MigrationEndpoint** pode ser usado para especificar um banco de dados do serviço a usar, utilizando a opção **-TargetDatabase**. Caso contrário, o banco de dados é atribuído de forma aleatória do site do Serviços de Federação do Active Directory (AD FS) 2.0, no qual a caixa de correio de gerenciamento está localizada.
  
#### <a name="verify-it-worked"></a>Verifique se funcionou

No PowerShell do Exchange Online, execute o seguinte comando para exibir informações sobre o ponto de extremidade de migração "StagedEndpoint":
  
```powershell
Get-MigrationEndpoint StagedEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*
```

### <a name="step-4-create-and-start-a-stage-migration-batch"></a>Etapa 4: criar e iniciar um lote de migração em estágios
<a name="BK_Endpoint"> </a>

Você pode usar o cmdlet **New-MigrationBatch** no PowerShell do Exchange Online para criar um lote de migração de uso em uma migração de transferência. É possível criar um lote de migração e iniciá-lo automaticamente incluindo o parâmetro _AutoStart_. Como alternativa, você pode criar o lote de migração e iniciá-lo manualmente mais tarde usando o cmdlet **Start-MigrationBatch**. Este exemplo cria um lote de migração chamado "StagedBatch1" e utiliza o ponto de extremidade de migração criado na etapa anterior.
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint -AutoStart
```

Este exemplo também cria um lote de migração chamado "StagedBatch1" e utiliza o ponto de extremidade de migração criado na etapa anterior. Como o parâmetro  _AutoStart_ não está incluído, o lote de migração deve ser iniciado manualmente no painel de migração ou usando o cmdlet **Start-MigrationBatch**. Como dito anteriormente, apenas um lote de migração de transferência pode existir de cada vez.
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint
```

#### <a name="verify-it-worked"></a>Verifique se funcionou

Execute o seguinte comando no PowerShell do Exchange Online para exibir informações sobre o "StagedBatch1":
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List
```

Você também pode verificar se o lote foi iniciado executando o seguinte comando:
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List Status
```

Para saber mais sobre o cmdlet **Get-MigrationBatch**, confira [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch).
  
### <a name="step-5-convert-on-premises-mailboxes-to-mail-enabled-users"></a>Etapa 5: converter caixas de correio locais em usuários habilitados para email
<a name="BK_Endpoint"> </a>

Após ter migrado com êxito um lote de caixas de correio, é necessário permitir que os usuários acessem seus emails de alguma forma. Um usuário cuja caixa de correio foi migrada agora tem uma caixa de correio local e uma no Microsoft 365. Os usuários que têm uma caixa de correio no Microsoft 365 param de receber novos emails em suas caixas de correio locais. 
  
Como você não terminou com suas migrações, ainda não está pronto para direcionar todos os usuários para o Microsoft 365 para seus emails. Então o que fazer para as pessoas que possuem ambas? O que você pode fazer é alterar as caixas de correio locais que você já tiver migrado para usuários habilitados para email. Quando você altera de uma caixa de correio para um usuário habilitado para email, você pode direcionar o usuário para o Microsoft 365 para seus emails em vez de ir para a caixa de correio local. 
  
Outro motivo importante para converter caixas de correio locais em usuários habilitados para email é manter endereços proxy das caixas de correio do Microsoft 365 copiando endereços proxy para os usuários habilitados para email. Isso permite gerenciar usuários baseados em nuvem da sua organização local usando o Active Directory. Além disso, se você decidir desmantelar sua organização local Exchange Server depois que todas as caixas de correio são migradas para o Microsoft 365, os endereços proxy que você copiou para os usuários habilitados para email permanecerão no Active Directory local.
    
### <a name="step-6-delete-a-staged-migration-batch"></a>Etapa 6: excluir um lote de migração em estágios
<a name="BK_Endpoint"> </a>

 Depois que todas as caixas de correio em um lote de migração foram migradas com êxito e você converteu as caixas de correio locais no lote para usuários habilitados para email, você está pronto para excluir um lote de migração em estágios. Verifique se o email está sendo encaminhado para as caixas de correio do Microsoft 365 no lote de migração. Ao excluir um lote de migração em estágios, o serviço de migração limpa todos os registros relacionados ao lote e o exclui.
  
Para excluir o lote de migração "StagedBatch1" no PowerShell do Exchange Online, execute o comando a seguir.
  
```powershell
Remove-MigrationBatch -Identity StagedBatch1
```

Para saber mais sobre o cmdlet **Remove-MigrationBatch**, confira [Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch).
  
#### <a name="verify-it-worked"></a>Verifique se funcionou

Execute o seguinte comando no PowerShell do Exchange Online para exibir informações sobre o "IMAPBatch1":
  
```powershell
Get-MigrationBatch StagedBatch1
```

O comando retornará o lote de migração com um status de **Removing** ou retornará um erro afirmando que o lote de migração não foi encontrado, confirmando que o lote foi excluído.
  
Para saber mais sobre o cmdlet **Get-MigrationBatch**, confira [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch).
  
### <a name="step7-assign-licenses-to-microsoft-365-users"></a>Etapa7: Atribuir licenças aos usuários do Microsoft 365
<a name="BK_Endpoint"> </a>

Ative as contas de usuário do Microsoft 365 para as contas migradas atribuindo licenças. Se você não atribuir uma licença, a caixa de correio será desabilitada quando terminar o período de cortesia (30 dias). Para atribuir uma licença no Centro de administração do Microsoft 365, consulte [Assign or unassign licenses](../admin/manage/assign-licenses-to-users.md).
  
### <a name="step-8-complete-post-migration-tasks"></a>Etapa 8: concluir tarefas pós-migração
<a name="BK_Postmigration"> </a>

- **Crie um registro DNS de Descoberta Automática para que os usuários possam acessar facilmente suas caixas de correio.** Depois que todas as caixas de correio locais são migradas para o Microsoft 365, você pode configurar um registro DNS de Descoberta Automática para sua organização do Microsoft 365 para permitir que os usuários se conectem facilmente às suas novas caixas de correio do Microsoft 365 com o Outlook e clientes móveis. Esse novo registro DNS de Descoberta Automática precisa usar o mesmo namespace que você está usando para sua organização do Microsoft 365. Por exemplo, se seu namespace baseado na nuvem for cloud.contoso.com, o registro DNS de Descoberta Automática que você precisa criar será autodiscover.cloud.contoso.com.
    
    O Microsoft 365 usa um registro CNAME para implementar o serviço de Descoberta Automática para o Outlook e clientes móveis. O registro CNAME de Descoberta Automática deve conter as seguintes informações:
    
  - **Alias:** descoberta automática
    
  - **Destino:** autodiscover.outlook.com
    
    Para obter mais informações, [consulte Adicionar registros DNS para conectar seu domínio](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).
    
- **Encerrar servidores locais do Exchange.** Depois de verificar se todos os emails estão sendo roteados diretamente para as caixas de correio do Microsoft 365 e não precisar mais manter sua organização de email local ou não planejar a implementação de uma solução SSO, você pode desinstalar o Exchange de seus servidores e remover sua organização local do Exchange.
    
    Para obter mais informações, confira o seguinte:
    
  - [Modificar ou remover o Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))
    
  - [Como remover uma Organização do Exchange 2007](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))
    
  - [Como desinstalar o Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))
