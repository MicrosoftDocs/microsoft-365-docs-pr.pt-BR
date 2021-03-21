---
title: Usar o PowerShell para realizar uma migração IMAP para o Microsoft 365
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
ms.assetid: c28de4a5-1e8e-4491-9421-af066cde7cdd
description: Saiba como usar o PowerShell para executar uma migração IMAP (Internet Mail Access Protocol) para o Microsoft 365.
ms.openlocfilehash: fbfc0340e80ce70aa8a706d89a4d27729b91535b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924763"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a>Usar o PowerShell para realizar uma migração IMAP para o Microsoft 365

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Como parte do processo de implantação do Microsoft 365, você pode optar por migrar o conteúdo das caixas de correio de usuário de um serviço de email IMAP (Internet Mail Access Protocol) para o Microsoft 365. Este artigo apresenta as tarefas para uma migração IMAP de email usando o PowerShell do Exchange Online. 
  
> [!NOTE]
> Você também pode usar o Centro de administração do Exchange para executar a migração IMAP. Consulte [Migrar suas caixas de correio IMAP.](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes) 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

Tempo estimado para a conclusão da tarefa: 2-5 minutos para criar um lote de migração. Depois que o lote de migração é iniciado, a duração da migração irá variar com base no número de caixas de correio no lote, no tamanho de cada caixa de correio e na sua capacidade de rede disponível. Para obter informações sobre outros fatores que afetam quanto tempo leva para migrar caixas de correio para o Microsoft 365, consulte [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).
  
Para executar esses procedimentos, você precisa receber permissões. Para saber quais permissões são necessárias, confira a entrada "Migração" em uma tabela no tópico [Permissões de destinatários](/exchange/recipients-permissions-exchange-2013-help).
  
Para usar os cmdlets do PowerShell do Exchange Online, você precisa entrar e importar os cmdlets para sua sessão local do Windows PowerShell. Confira [Conectar-se ao Exchange Online usando o PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell) para obter instruções.
  
Para obter uma lista completa dos comandos de migração, confira [Cmdlets de movimentação e migração](/powershell/exchange/).
  
As seguintes restrições se aplicam às migrações IMAP:
  
- Apenas itens na caixa de entrada de um usuário ou outras pastas de email pode ser migradas. Não é possível migrar contatos, itens de calendário ou tarefas.
    
- No máximo 500.000 itens podem ser migrados de uma caixa de correio de usuário.
    
- O tamanho máximo da mensagem que pode ser migrada é de 35 MB.
    
## <a name="migration-steps"></a>Etapas da migração

### <a name="step-1-prepare-for-an-imap-migration"></a>Etapa 1: Preparar uma migração IMAP
<a name="BK_Step1"> </a>

- **Se você tiver um domínio para sua organização IMAP, adicione-o como um domínio aceito da sua organização do Microsoft 365.** Se você quiser usar o mesmo domínio que já possui para suas caixas de correio do Microsoft 365, primeiro você precisa adicioná-lo como um domínio aceito ao Microsoft 365. Depois de adicionar, você pode criar seus usuários no Microsoft 365. Para obter mais informações, consulte[Verify your domain](../admin/setup/add-domain.md).
    
- **Adicione cada usuário ao Microsoft 365 para que ele tenha uma caixa de correio.** Para obter instruções,[consulte Adicionar usuários ao Microsoft 365 para empresas](../admin/add-users/add-users.md).
    
- **Obter o FQDN do servidor IMAP**. Você precisa fornecer o FQDN (nome de domínio totalmente qualificado) (também chamado de nome completo do computador) do servidor IMAP do qual você migrará dados de caixa de correio ao criar um ponto de extremidade de migração IMAP. Use um cliente IMAP ou o comando PING para verificar se você pode usar o FQDN para se comunicar com o servidor IMAP pela Internet.
    
- **Configurar o firewall para permitir conexões IMAP**. Você pode precisar abrir portas no firewall da organização que hospeda o servidor IMAP para que o tráfego de rede originário do data center da Microsoft durante a migração tenha permissão para entrar na organização que hospeda o servidor IMAP. Para obter uma lista de endereços IP usada pelos datacenters do Microsoft, confira [Intervalos de endereços IP e URLs do Exchange Online](./urls-and-ip-address-ranges.md).
    
- **Atribuir ao administrador permissões de conta para acessar caixas de correio em sua organização IMAP** Se você usar credenciais de administrador no arquivo CSV, a conta usada deverá ter as permissões necessárias para acessar as caixas de correio locais. As permissões necessárias para acessar as caixas de correio do usuário são determinadas pelo servidor IMAP específico. 
    
- **Para usar os cmdlets do PowerShell do Exchange Online**, você precisa entrar e importar os cmdlets para sua sessão local do Windows PowerShell. Confira [Conectar-se ao Exchange Online usando o PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell) para obter instruções.
    
    Para obter uma lista completa dos comandos de migração, confira [Cmdlets de movimentação e migração](/powershell/exchange/).
    
- **Verifique se você pode se conectar ao servidor IMAP**. Execute o seguinte comando no PowerShell do Exchange Online para testar as configurações de conexão ao servidor IMAP.
    
  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    Para o valor do parâmetro **Port**, é normal usar 143 para conexões descriptografadas ou TLS (Transport Layer Security) e usar 993 para conexões SSL.
    
### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a>Etapa 2: Criar um arquivo CSV para um lote de migração IMAP
<a name="BK_Step2"> </a>

Identifique o grupo de usuários cujas caixas de correio você deseja migrar em um lote de migração IMAP. Cada linha no arquivo CSV contém as informações necessárias para se conectar a uma caixa de correio no sistema de mensagens IMAP.
  
Veja a seguir os atributos necessários para cada usuário: 
  
- **EmailAddress** especifica a ID do usuário para a caixa de correio do Microsoft 365 do usuário.
    
- **UserName** especifica o nome de logon da conta a ser usada para acessar a caixa de correio no servidor IMAP.
    
- **Password** especifica a senha para a conta na coluna **UserName**.
    
Aqui está um exemplo do formato do arquivo CSV. Neste exemplo, três caixas de correio são migradas:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

Para o atributo **UserName**, além do nome de usuário, você pode usar as credenciais de uma conta que recebeu as permissões necessárias para acessar caixas de correio no servidor IMAP. A seguir estão alguns dos formatos específicos usados para alguns dos servidores IMAP:
  
 **Microsoft Exchange:**
  
Se você estiver migrando emails da implementação de IMAP para Microsoft Exchange, use o formato **Domain/Admin_UserName/User_UserName** para o atributo **UserName** no arquivo CSV. Digamos que você esteja migrando email do Exchange para Henrique Castro, Alice Pena e Pedro Gonçalves. Você tem uma conta de administrador de email, onde o nome de usuário **é mailadmin** e a senha é **P \@ ssw0rd**. Esta seria a aparência do seu arquivo CSV:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 **Dovecot:**
  
Para servidores IMAP que dão suporte a SASL (Simple Authentication and Security Layer), como um servidor Dovecot IMAP, use o formato **User_UserName*Admin_UserName**, em que o asterisco (*) é um caractere separador configurável. Digamos que você esteja migrando o email desses mesmos usuários de um servidor IMAP do Dovecot usando as credenciais de administrador **mailadmin** e **P \@ ssw0rd**. Esta seria a aparência do seu arquivo CSV:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 **Mirapoint:**
  
Se você estiver migrando emails do Mirapoint Message Server, use o formato #user **\@ domínio#Admin_UserName#** para as credenciais do administrador. Para migrar emails do Mirapoint usando as credenciais de administrador **mailadmin** e **P \@ ssw0rd**, seu arquivo CSV teria esta aparência:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 **Courier IMAP:**
  
Alguns sistemas de email de origem, como o Courier IMAP, não suportam o uso de credenciais de administrador de caixa de correio para migrar caixas de correio para o Microsoft 365. Em vez disso, você pode configurar seu sistema de email de origem para usar pastas compartilhadas virtuais. Usando pastas compartilhadas virtuais, você pode usar as credenciais de administrador de caixa de correio para acessar caixas de correio do usuário no sistema de email de origem. Para saber mais sobre como configurar as pastas virtuais compartilhadas do Courier IMAP, confira [Pastas Compartilhadas](https://go.microsoft.com/fwlink/p/?LinkId=398870).
  
Para migrar as caixas de correio depois de configurar as pastas compartilhadas virtuais em seu sistema de email de origem, você deve incluir o atributo **UserRoot** opcional no arquivo de migração. Esse atributo especifica o local da caixa de correio de cada usuário na estrutura de pastas compartilhadas virtuais do sistema de email de origem. Por exemplo, o caminho para a caixa de correio de Pedro é /users/pedro.goncalves.
  
Aqui está um exemplo de um arquivo CSV que contém o atributo **UserRoot**:
  
```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a>Etapa 3: Criar um ponto de extremidade de migração IMAP
<a name="BK_Step3"> </a>

Para migrar emails com êxito, o Microsoft 365 precisa se conectar e se comunicar com o sistema de email de origem. Para fazer isso, o Microsoft 365 usa um ponto de extremidade de migração. O ponto de extremidade de migração também define o número de caixas de correio para migração simultânea e o número de caixas de correio para sincronização simultânea durante a sincronização incremental, que ocorre uma vez a cada 24 horas. Para criar um ponto de extremidade de migração para migração IMAP, [conecte-se primeiro ao Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). 
  
Para obter uma lista completa dos comandos de migração, confira [Cmdlets de movimentação e migração](/powershell/exchange/).
  
Para criar o ponto de extremidade de migração IMAP chamado "IMAPEndpoint" no PowerShell do Exchange Online, execute o seguinte comando:
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

Você também pode adicionar parâmetros para especificar migrações simultâneas, migrações simultâneas incrementais e a porta a ser usada. O comando a seguir do PowerShell do Exchange Online cria um ponto de extremidade de migração IMAP chamado "IMAPEndpoint" que dá suporte a 50 migrações simultâneas e até 25 sincronizações incrementais simultâneas. Também configura o ponto de extremidade para usar a porta 143 para criptografia TLS.
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

Para saber mais sobre o cmdlet **New-MigrationEndpoint**, confira [New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint).
  
#### <a name="verify-it-worked"></a>Verifique se funcionou

Execute o seguinte comando no PowerShell do Exchange Online para exibir informações sobre o "IMAPEndpoint":
  
```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a>Etapa 4: Criar e iniciar um lote de migração IMAP
<a name="BK_Step4"> </a>

Você pode usar o cmdlet [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) para criar um lote de migração para uma migração IMAP. É possível criar um lote de migração e iniciá-lo automaticamente incluindo o parâmetro _AutoStart_. Como alternativa, você pode criar o lote de migração e iniciá-lo mais tarde usando o cmdlet [Start-MigrationBatch](/powershell/module/exchange/start-migrationbatch).
  
O seguinte comando do PowerShell do Exchange Online iniciará automaticamente o lote de migração chamado "IMAPBatch1" usando o ponto de extremidade IMAP chamado "IMAPEndpoint":
  
```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a>Verifique se funcionou

Execute o cmdlet [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch) para exibir informações sobre o "IMAPBatch1":
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

Você também pode verificar se o lote foi iniciado executando o seguinte comando:
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>Etapa 5: Rotear seu email para o Microsoft 365
<a name="BK_Step5"> </a>

Os sistemas de email usam um registro DNS chamado registro MX para descobrir onde entregar emails. Durante o processo de migração de email, seu registro MX estava apontando para o sistema de email de origem. Agora que a migração de email para o Microsoft 365 está concluída, é hora de apontar seu registro MX para o Microsoft 365. Isso ajuda a garantir que o email seja entregue às caixas de correio do Microsoft 365. Movendo o registro MX, você também poderá desativar seu sistema de email antigo quando estiver pronto. 
  
Em muitos provedores DNS, existem instruções específicas para alterar o seu registro MX. Se o provedor DNS não estiver incluído ou se você quiser ter uma noção das instruções gerais, as instruções gerais de registro [MX ](https://go.microsoft.com/fwlink/?LinkId=397449) também serão fornecidas.
  
Pode levar até 72 horas para que os sistemas de email de seus clientes e parceiros reconheçam o registro MX alterado. Aguarde pelo menos 72 horas antes de prosseguir para a próxima tarefa: Etapa 6: Excluir o lote de migração IMAP. 
  
### <a name="step-6-delete-imap-migration-batch"></a>Etapa 6: Excluir o lote de migração IMAP
<a name="BK_Step6"> </a>

Depois de alterar o registro MX e verificar se todos os emails estão sendo roteados para caixas de correio do Microsoft 365, notifique os usuários de que seus emails estão indo para o Microsoft 365. Depois disso, você pode excluir o lote de migração IMAP. Antes de excluir o lote de migração, verifique os itens a seguir.
  
- Todos os usuários estão usando caixas de correio do Microsoft 365. Depois que o lote é excluído, os emails enviados às caixas de correio no local Exchange Server não são copiados para as caixas de correio correspondentes do Microsoft 365.
    
- As caixas de correio do Microsoft 365 foram sincronizadas pelo menos uma vez depois que os emails começaram a ser enviados diretamente a elas. Para fazer isso, certifique-se de que o valor na caixa Última Hora Sincronizada para o lote de migração seja mais recente do que quando os emails começaram a ser roteados diretamente para caixas de correio do Microsoft 365.
    
Para excluir o lote de migração "IMAPBatch1" do PowerShell do Exchange Online, execute o seguinte comando:
  
```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

Para saber mais sobre o cmdlet **Remove-MigrationBatch**, confira [Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch).
  
#### <a name="verify-it-worked"></a>Verifique se funcionou

Execute o seguinte comando no PowerShell do Exchange Online para exibir informações sobre o "IMAPBatch1":
  
```powershell
Get-MigrationBatch IMAPBatch1"
```

O comando retornará o lote de migração com um status de **Removing** ou retornará um erro afirmando que o lote de migração não foi encontrado, confirmando que o lote foi excluído.
  
Para saber mais sobre o cmdlet **Get-MigrationBatch**, confira [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch).
  
## <a name="see-also"></a>Confira também

[Solução de problemas de migração IMAP](/exchange/troubleshoot/move-or-migrate-mailboxes/troubleshoot-issues-with-imap-mailbox-migration)