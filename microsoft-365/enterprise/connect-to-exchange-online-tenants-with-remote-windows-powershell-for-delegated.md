---
title: Conectar-se aos locatários do Exchange Online com o Windows PowerShell remoto para parceiros DAP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: ''
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
ms.assetid: ae5f1a87-8b77-4f93-a1b8-56f800aeb283
description: 'Resumo: use o Windows PowerShell remoto para se conectar ao Exchange Online utilizando o valor DelegatedOrg.'
ms.openlocfilehash: 1351a6a6d19fac408b673796c1179bca0ede9c9f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687273"
---
# <a name="connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Conectar-se aos locatários do Exchange Online com o Windows PowerShell remoto para parceiros com permissões de acesso delegado (DAP)

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

> [!IMPORTANT]
> Os procedimentos neste tópico servem apenas para parceiros de permissão de acesso delegado (DAP). Se você não for um parceiro DAP, não use os procedimentos neste tópico. 
  
Os parceiros DAP são parceiros de agregação e Provedores de Soluções na Nuvem (CSP). Muitas vezes, eles são provedores de rede ou de telecomunicações para outras empresas. Eles reúnem assinaturas em suas ofertas de serviço aos respectivos clientes. Eles possuem uma locação de parceiros que recebe automaticamente as permissões de administração em nome de (AOBO) para o seu cliente da Microsoft 365 locações, para que possam administrar e relatar todos os seus locações clientes.

Os parceiros DAP podem usar o Exchange Online PowerShell para gerenciar as configurações do Exchange Online do cliente e obter relatórios do Microsoft 365 a partir da linha de comando. Use o Windows PowerShell em seu computador local para criar uma sessão do PowerShell remoto para o Exchange Online. É um processo simples de três etapas onde você insere suas credenciais, fornece as configurações de conexão necessárias e, em seguida, importa os cmdlets do Exchange Online para a sua sessão local do Windows PowerShell, para que você possa usá-las.

> [!NOTE]
> Parceiros DAP não podem usar os procedimentos [Conectar-se ao PowerShell do Exchange Online usando a autenticação multifatorial](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell) para se conectar a suas organizações de locatário do cliente no PowerShell do Exchange Online. A autenticação multifatorial (MFA) e o Módulo do PowerShell remoto do Exchange Online não funcionam com autenticação delegada.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Tempo estimado para conclusão: 5 minutos

- Você pode usar as seguintes versões do Windows:
    
  - Windows 10

  - Windows 8.1

  - Windows Server 2016

  - Windows Server 2012 ou Windows Server 2012 R2

  - Windows 7 Service Pack 1 (SP1) <sup>*</sup>

  - Windows Server 2008 R2 SP1<sup>*</sup>

    <sup>*</sup> Nas versões anteriores do Windows, você precisa instalar o Microsoft.NET Framework 4.5 ou posterior e uma versão atualizada do Windows Management Framework: 3.0, 4.0 ou 5.1 (somente uma). Para saber mais, confira [Instalação do .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757), [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344), e [Windows Management Framework 5.1](https://aka.ms/wmf5download).

- O Windows PowerShell precisa ser configurado para executar scripts e, por padrão, ele não é. Ao tentar se conectar, você obtém o seguinte erro:

  `Files cannot be loaded because running scripts is disabled on this system. Provide a valid certificate with which to sign the files.`

  Para permitir que todos os scripts do PowerShell que você baixar da Internet sejam assinados por um fornecedor confiável, execute o seguinte comando em uma janela elevada do Windows PowerShell (uma janela do Windows PowerShell que você abre selecionando **Executar como administrador**):

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

  Você só precisa definir essa configuração uma vez em seu computador, e não sempre que se conectar.

- Para saber mais sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, confira o artigo [Atalhos de teclado no Centro de administração do Exchange ](https://go.microsoft.com/fwlink/p/?LinkId=534017).

## <a name="connect-to-exchange-online-for-customer-organizations"></a>Conectar ao Exchange Online para organizações do cliente

1. Em seu computador local, abra o Windows PowerShell e execute o comando a seguir.
    
    ```
    $UserCredential = Get-Credential
    ```

    Na caixa de diálogo **Solicitação de Credenciais do Windows PowerShell**, digite seu nome de usuário e senha do administrador DAP e clique em **OK**.
    
2. Substitua _\<customer tenant domain name\>_ pelo nome do domínio do locatário ao qual você deseja se conectar e execute o seguinte comando:
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid?DelegatedOrg=<customer tenant domain name> -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

    A etapa principal deste comando especifica qual cliente acessar para obter as informações do relatório. Isso é feito no parâmetro  _ConnectionURI_ , onde você fornece o FQDN do nome de domínio inicial como o valor para `?DelegatedOrg=` . Esse valor indica o ponto de extremidade correto do PowerShell do Exchange Online para se conectar. O PowerShell remoto deve se conectar aos relatórios do Microsoft 365 no contexto de um cliente específico cada vez que um relatório é executado. Depois de se conectar ao PowerShell do Exchange Online, todos os comandos subsequentes são executados no contexto do cliente, que oferece acesso a todos os relatórios disponíveis para o cliente.
    
3. Execute o seguinte comando.
    
    ```
    Import-PSSession $Session
    ```

> [!NOTE]
> Há um limite de três sessões que podem ser executadas simultaneamente em uma conta. Quando concluir, verifique se desconectou a sessão do PowerShell remoto. Quando você fecha a janela do PowerShell sem desconectar a sessão, pode usar todas as sessões do PowerShell remoto disponíveis; no entanto, será necessário aguardar a expiração das sessões. Para desconectar a sessão do PowerShell remoto, execute o seguinte comando:

```
Remove-PSSession $Session
```
  
## <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Após a etapa 3, os cmdlets do Exchange Online são importados para sua sessão local do Windows PowerShell, como é possível acompanhar por uma barra de progresso. Se você não receber nenhum erro, se conectará com êxito. Execute um cmdlet do Exchange Online como um teste rápido (por exemplo, o **Get-Mailbox**), e confira os resultados.
  
Caso você receba erros, verifique os seguintes requisitos:
  
- Um problema comum é uma senha incorreta. Execute as três etapas novamente e preste muita atenção ao nome de usuário e à senha inseridos na Etapa 1.
    
- A conta que você usa para se conectar ao Exchange Online deve estar habilitada para o PowerShell remoto. Para saber mais, confira o artigo [Habilitar ou desabilitar o acesso ao PowerShell no Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534018).
    
- O tráfego da porta TCP 80 precisa estar aberto entre seu computador local e o Exchange Online. Provavelmente ele está aberto, mas é algo a ser considerado caso a sua organização tenha uma política de acesso à Internet restritiva.
    
## <a name="call-the-cmdlet-directly-with-invoke-command"></a>Chamar o cmdlet diretamente com Invoke-Command

A importação de uma sessão do PowerShell remoto (Etapa 3) pode ser um processo demorado, pois ela carrega _todos_ os cmdlets do Exchange Online. Isso pode ser um problema no processamento em lotes (por exemplo, quando você executa relatórios ou faz alterações em massa em diferentes locatários). Como uma alternativa ao uso do **Import-PSSession**, chame os cmdlets que deseja usar diretamente com o **Invoke-Command**. Por exemplo, para chamar o cmdlet **Get-Mailbox**, substitua essa sintaxe para no comando `Import-PSSession $Session` na Etapa 3:
  
```
Invoke-Command -Session $Session -ScriptBlock {Get-Mailbox}
```

## <a name="more-reporting-cmdlets"></a>Mais cmdlets de relatórios

Os cmdlets usados neste tópico são os cmdlets do Windows PowerShell. Para saber mais sobre esses cmdlets, confira os tópicos a seguir:
  
- [Get-Credential](https://go.microsoft.com/fwlink/p/?LinkId=389618)
    
- [New-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389621)
    
- [Import-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389619)
    
- [Remove-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389620)
    
- [Set-ExecutionPolicy](https://go.microsoft.com/fwlink/p/?LinkId=389623)
    

