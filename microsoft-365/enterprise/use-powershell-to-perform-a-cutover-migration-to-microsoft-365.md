---
title: Usar o PowerShell para realizar uma migração de substituição para o Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
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
ms.assetid: b468cb4b-a35c-43d3-85bf-65446998af40
description: Saiba como usar o PowerShell para mover o conteúdo de um sistema de email de origem de uma só vez executando uma migração de recortamento para o Microsoft 365.
ms.openlocfilehash: 6e59ac4d590208e0faed22e94cabe05601b17f18
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581053"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a>Usar o PowerShell para realizar uma migração de substituição para o Microsoft 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Você pode migrar o conteúdo das caixas de correio de usuário de um sistema de email de origem para o Microsoft 365 de uma só vez usando uma migração de transferência. Este artigo apresenta as tarefas para uma migração de substituição de email usando o PowerShell do Exchange Online.

Ao analisar o tópico, o que você precisa saber sobre uma migração de email de recortamento para o [Microsoft 365](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration), você pode obter uma visão geral do processo de migração. Quando você estiver familiarizado com os conteúdos do artigo, use o seguinte para começar a migrar caixas de correio de um sistema de email para outro.

> [!NOTE]
> Você também pode usar o Centro de administração do Exchange para executar uma migração de recortamento. Consulte [Perform a cutover migration of email to Microsoft 365](/Exchange/mailbox-migration/cutover-migration-to-office-365).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

Tempo estimado para a conclusão da tarefa: 2-5 minutos para criar um lote de migração. Depois que o lote de migração é iniciado, a duração da migração irá variar com base no número de caixas de correio no lote, no tamanho de cada caixa de correio e na sua capacidade de rede disponível. Para obter informações sobre outros fatores que afetam quanto tempo leva para migrar caixas de correio para o Microsoft 365, consulte [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).

Para executar esses procedimentos, você precisa receber permissões. Para saber quais permissões são necessárias, confira a entrada "Migração" em uma tabela no tópico [Permissões de destinatários](/exchange/recipients-permissions-exchange-2013-help).

Para usar os cmdlets do PowerShell do Exchange Online, você precisa entrar e importar os cmdlets para sua sessão local do Windows PowerShell. Confira [Conectar-se ao Exchange Online usando o PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell) para obter instruções.

Para obter uma lista completa dos comandos de migração, confira [Cmdlets de movimentação e migração](/powershell/exchange/).

## <a name="migration-steps"></a>Etapas da migração

### <a name="step-1-prepare-for-a-cutover-migration"></a>Etapa 1: preparar para uma migração de transferência
<a name="BK_Step1"> </a>

- **Adicione sua organização local do Exchange como um domínio aceito da sua organização do Microsoft 365.** O serviço de migração usa o endereço SMTP de suas caixas de correio locais para criar Microsoft Online Services ID de usuário e endereço de email para as novas caixas de correio do Microsoft 365. A migração falhará se o domínio do Exchange não for um domínio aceito ou o domínio principal da sua organização do Microsoft 365. Para obter mais informações, consulte [Verify your domain](../admin/setup/add-domain.md).

- **Configure o Outlook em Qualquer Lugar no servidor Exchange no local** O serviço de migração de email usa o RPC sobre HTTP ou o Outlook em Qualquer Lugar para se conectar ao servidor do Exchange no local. Para saber mais sobre como configurar o Outlook em Qualquer Lugar para Exchange 2010, Exchange 2007 e Exchange 2003, confira o seguinte:

  - [Exchange 2010: Habilitar o Outlook em Qualquer Lugar](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))

  - [Exchange 2007: Como Habilitar o Outlook em Qualquer Lugar](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))

  - [Exchange 2003: Cenários de implantação para RPC sobre HTTP](/previous-versions/tn-archive/bb124876(v=exchg.65))

  - [Como Configurar o Outlook em Qualquer Lugar com o Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))

    > [!IMPORTANT]
    > Sua configuração do Outlook em Qualquer Lugar deve ser configurada com um certificado emitido por uma autoridade de certificação (AC) confiável. Ele não pode ser configurado com um certificado autoassinado. Para saber mais, confira [Como configurar o SSL para o Outlook em Qualquer Lugar](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)).

- **Verifique se você pode se conectar à organização do Exchange usando o Outlook em Qualquer Lugar** Experimente um destes métodos para testar suas configurações de conexão:

  - Use o Microsoft Outlook de fora da rede corporativa para se conectar à sua caixa de correio do Exchange no local.

  - Use o [Analisador de Conectividade Remota do Microsoft Exchange](https://www.testexchangeconnectivity.com/) para testar suas configurações de conexão. Use o Outlook em Qualquer Lugar (RPC sobre HTTP) ou testes de descoberta automática do Outlook.

  - Execute os comandos a seguir no PowerShell do Exchange Online.

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- **Atribua as permissões necessárias a uma conta de usuário local para acessar caixas de correio em sua organização do Exchange.** A conta de usuário local que você usa para se conectar à sua organização local do Exchange (também chamada de administrador de migração) deve ter as permissões necessárias para acessar as caixas de correio locais que você deseja migrar para o Microsoft 365. Essa conta de usuário é usada para criar um ponto de extremidade de migração para a sua organização local.

    A lista a seguir mostra os privilégios administrativos necessários para migrar caixas de correio usando uma migração de transferência. Existem três opções possíveis.

  - O administrador de migração deve ser membro do grupo **Administradores de Domínio** no Active Directory na organização local.

    Ou

  - O administrador de migração deve ser atribuído a permissão **FullAccess** para cada caixa de correio local.

    Ou

  - O administrador de migração deve ser atribuído a permissão **Receber como** no banco de dados da caixa de correio local que armazena as caixas de correio do usuário.

- **Desabilite a Unificação de Mensagens.** Se as caixas de correio locais que você está migrando estiverem habilitadas para a UM (Unificação de Mensagens), será necessário desabilitar a UM nas caixas de correio antes de migrá-las. Em seguida, você poderá habilitar a UM nas caixas de correio depois que a migração for concluída.

- **Grupos de segurança e representantes** O serviço de migração de email não pode detectar se os grupos locais do Active Directory são grupos de segurança ou não, portanto, ele não pode provisioná-los como grupos de segurança no Microsoft 365. Se você quiser ter grupos de segurança em seu locatário do Microsoft 365, primeiro provisione um grupo de segurança habilitado para email vazio em seu locatário do Microsoft 365 antes de iniciar a migração de recortamento. Além disso, esse método de migração só move caixas de correio, usuários de email, contatos de email e grupos habilitados para email. Se qualquer outro objeto do Active Directory, como o usuário que não foi migrado para o Microsoft 365, for atribuído como gerente ou representante para um objeto que está sendo migrado, ele deverá ser removido do objeto antes de migrar.

### <a name="step-2-create-a-migration-endpoint"></a>Etapa 2: criar um ponto de extremidade de migração
<a name="BK_Step2"> </a>

Para migrar emails com êxito, o Microsoft 365 precisa se conectar e se comunicar com o sistema de email de origem. Para fazer isso, o Microsoft 365 usa um ponto de extremidade de migração. Para criar um ponto de extremidade de migração de migração do Outlook Em Qualquer Lugar para migração de redução, [conecte-se](/powershell/exchange/connect-to-exchange-online-powershell)primeiro ao Exchange Online .

Para obter uma lista completa dos comandos de migração, confira [Cmdlets de movimentação e migração](/powershell/exchange/).

Execute os seguintes comandos no PowerShell do Exchange Online:

```powershell
$Credentials = Get-Credential
```

O exemplo usa o cmdlet [Test-MigrationServerAvailability](/powershell/module/exchange/test-migrationserveravailability) para obter e testar as configurações de conexão ao servidor do Exchange local e usa essas configurações de conexão para criar o ponto de extremidade de migração chamado "CutoverEndpoint".

```powershell
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> O cmdlet **New-MigrationEndpoint** pode ser usado para especificar um banco de dados do serviço a usar, utilizando a opção **-TargetDatabase**. Caso contrário, o banco de dados é atribuído de forma aleatória do site do Serviços de Federação do Active Directory (AD FS) 2.0, no qual a caixa de correio de gerenciamento está localizada.

#### <a name="verify-it-worked"></a>Verifique se funcionou

No PowerShell do Exchange Online, execute o seguinte comando para exibir informações sobre o ponto de extremidade de migração "CutoverEndpoint":

```powershell
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a>Etapa 3: criar o lote de migração de transferência
<a name="BK_Step3"> </a>

Você pode usar o cmdlet **New-MigrationBatch** no PowerShell do Exchange Online para criar um lote de migração de uso em uma migração de transferência. É possível criar um lote de migração e iniciá-lo automaticamente incluindo o parâmetro _AutoStart_. Como alternativa, você pode criar o lote de migração e iniciá-lo manualmente mais tarde usando o cmdlet **Start-MigrationBatch**. Este exemplo cria um lote de migração chamado "CutoverBatch" e utiliza o ponto de extremidade de migração criado na etapa anterior.

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

Este exemplo também cria um lote de migração chamado "CutoverBatch" e utiliza o ponto de extremidade de migração criado na etapa anterior. Como o parâmetro  _AutoStart_ não está incluído, o lote de migração deve ser iniciado manualmente no painel de migração ou usando o cmdlet **Start-MigrationBatch**. Como dito anteriormente, apenas um lote de migração de transferência pode existir de cada vez.

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a>Verifique se funcionou

Para verificar se você criou com êxito um lote de migração para uma migração de substituição, execute o seguinte comando no PowerShell do Exchange Online para exibir informações sobre o novo lote de migração:

```powershell
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a>Etapa 4: iniciar o lote de migração de transferência
<a name="BK_Step4"> </a>

Para iniciar o lote de migração no PowerShell do Exchange Online, execute o seguinte comando. Isso criará um lote de migração chamado "CutoverBatch".

```powershell
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a>Verifique se funcionou

Se um lote de migração for iniciado com êxito, seu status no painel de migração será especificado como Sincronizando. Para verificar se você iniciou com êxito um lote de migração usando o PowerShell do Exchange Online, execute o seguinte comando:

```powershell
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>Etapa 5: Rotear seu email para o Microsoft 365
<a name="BK_Step5"> </a>

Os sistemas de email usam um registro DNS chamado registro MX para descobrir onde entregar emails. Durante o processo de migração de email, seu registro MX estava apontando para o sistema de email de origem. Agora que a migração de email para o Microsoft 365 está concluída, é hora de apontar seu registro MX para o Microsoft 365. Isso ajuda a garantir que o email seja entregue às caixas de correio do Microsoft 365. Movendo o registro MX, você também poderá desativar seu sistema de email antigo quando estiver pronto.

Em muitos provedores DNS, existem instruções específicas para alterar o seu registro MX. Se o seu provedor DNS não for incluído, ou se você quiser ver diretrizes gerais, também são fornecidas [instruções gerais de registro MX](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx).

Pode levar até 72 horas para que os sistemas de email de seus clientes e parceiros reconheçam o registro MX alterado. Aguarde pelo menos 72 horas antes de prosseguir para a próxima tarefa: [Etapa 6: excluir o lote de migração de transferência](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).

### <a name="step-6-delete-the-cutover-migration-batch"></a>Etapa 6: excluir o lote de migração de transferência
<a name="Bk_step6"> </a>

Depois de alterar o registro MX e verificar se todos os emails estão sendo roteados para caixas de correio do Microsoft 365, notifique os usuários de que seus emails estão indo para o Microsoft 365. Depois disso, você pode excluir o lote de migração de substituição. Antes de excluir o lote de migração, verifique os itens a seguir.

- Todos os usuários estão usando caixas de correio do Microsoft 365. Depois que o lote é excluído, os emails enviados às caixas de correio no local Exchange Server não são copiados para as caixas de correio correspondentes do Microsoft 365.

- As caixas de correio do Microsoft 365 foram sincronizadas pelo menos uma vez depois que os emails começaram a ser enviados diretamente a elas. Para fazer isso, certifique-se de que o valor na caixa Última Hora Sincronizada para o lote de migração seja mais recente do que quando os emails começaram a ser roteados diretamente para caixas de correio do Microsoft 365.

Para excluir o lote de migração "CutoverBatch" no PowerShell do Exchange Online, execute o seguinte comando:

```powershell
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a>Seção 7: atribuir licenças de usuários
<a name="BK_Step7"> </a>

 **Ative as contas de usuário do Microsoft 365 para as contas migradas atribuindo licenças.** Se você não atribuir uma licença, a caixa de correio será desabilitada quando terminar o período de carência (30 dias). Para atribuir uma licença no Centro de administração do Microsoft 365, consulte [Assign or unassign licenses](../admin/manage/assign-licenses-to-users.md).

### <a name="step-8-complete-post-migration-tasks"></a>Etapa 8: concluir tarefas pós-migração
<a name="BK_Step8"> </a>

- **Crie um registro DNS de Descoberta Automática para que os usuários possam acessar facilmente suas caixas de correio.** Depois que todas as caixas de correio locais são migradas para o Microsoft 365, você pode configurar um registro DNS de Descoberta Automática para sua organização do Microsoft 365 para permitir que os usuários se conectem facilmente às suas novas caixas de correio do Microsoft 365 com o Outlook e clientes móveis. Esse novo registro DNS de Descoberta Automática precisa usar o mesmo namespace que você está usando para sua organização do Microsoft 365. Por exemplo, se seu namespace baseado na nuvem for cloud.contoso.com, o registro DNS de Descoberta Automática que você precisa criar será autodiscover.cloud.contoso.com.

    Se você manter seu Exchange Server, certifique-se de que o registro CNAME DNS de Descoberta Automática tenha que apontar para o Microsoft 365 no DNS interno e externo após a migração para que o cliente do Outlook se conecte à caixa de correio correta.

    > [!NOTE]
    >  No Exchange 2007, Exchange 2010 e no Exchange 2013, você também deve definir o  `Set-ClientAccessServer AutodiscoverInternalConnectionURI` como `Null`.

    O Microsoft 365 usa um registro CNAME para implementar o serviço de Descoberta Automática para o Outlook e clientes móveis. O registro CNAME de Descoberta Automática deve conter as seguintes informações:

  - **Alias:** descoberta automática

  - **Destino:** autodiscover.outlook.com

    Para obter mais informações, [consulte Adicionar registros DNS para conectar seu domínio](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

- **Encerrar servidores locais do Exchange.** Depois de verificar se todos os emails estão sendo roteados diretamente para as caixas de correio do Microsoft 365 e não precisar mais manter sua organização de email local ou não planejar a implementação de uma solução de logom único (SSO), você pode desinstalar o Exchange de seus servidores e remover sua organização local do Exchange.

    Para obter mais informações, confira o seguinte:

  - [Modificar ou remover o Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))

  - [Como remover uma Organização do Exchange 2007](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))

  - [Como desinstalar o Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))