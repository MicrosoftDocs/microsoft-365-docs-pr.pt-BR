---
title: RGPD
description: Orientação técnica da Microsoft — CONJUNTO DE FERRAMENTAS DE MIGRAÇÕES FASTTRACK PARA ENVIAR SOLICITAÇÃO DE EXCLUSÃO
keywords: Migração FastTrack, Microsoft 365 Education, documentação do Microsoft 365, RGPD
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: mohitku
author: MohitKumar
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 10a983297640ac4b65aaf181ef35ac19918e74fe
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547370"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a>Conjunto de ferramentas de migração FastTrack para envio de solicitação de exclusão

## <a name="toolset-purpose"></a>Finalidade do conjunto de ferramentas

Se você for um cliente envolvido atualmente com migrações FastTrack, a exclusão da conta de usuário não excluirá a cópia dos dados em posse da equipe do Microsoft FastTrack, mantida apenas para a conclusão da migração. Se, durante a migração, você quiser que a equipe do Microsoft FastTrack também exclua a cópia dos dados, envie uma solicitação por esse conjunto de ferramentas. No curso normal dos negócios, o Microsoft FastTrack excluirá todas as cópias dos dados após a conclusão da migração.

### <a name="supported-platforms"></a>Plataformas compatíveis

A Microsoft oferece suporte à versão inicial deste conjunto de ferramentas na plataforma do Windows e no console do PowerShell. Este conjunto de ferramentas oferece suporte às plataformas conhecidas a seguir:

***Tabela 1 - Plataformas compatíveis com este conjunto de ferramentas***

****

|Versão do Windows PowerShell|Windows 7|Windows 8|Windows 10|Windows Server 2012|Windows Server 2016|
|:---:|:---:|:---:|:---:|:---:|:---:|
|5.0|Não suportado|Com suporte|Com suporte|Com suporte|Com suporte|
|5.1|Não suportado|Com suporte|Com suporte|Com suporte|Com suporte|
|

### <a name="obtaining-the-toolset"></a>Como obter o conjunto de ferramentas

Este conjunto de ferramentas está disponível na Galeria do PowerShell no aplicativo de console do PowerShell. Para localizar e carregar o módulo desse cmdlet, primeiro abra o PowerShell no modo de administrador para que ele tenha as permissões apropriadas para instalar o módulo. Se você nunca usou o PowerShell, acesse a Barra de Tarefas do Windows e, na caixa de pesquisa, digite "PowerShell". Selecione o aplicativo de console usando o botão direito e escolha **Executar como administrador**, depois clique em **Sim** para executar o Windows PowerShell.

![PowerShell - Executar como administrador](../media/fasttrack-powershell_image.png)

![PowerShell - Permitir que o aplicativo faça alterações](../media/fasttrack-run-powershell_image.png)

Agora que o console está aberto, você precisa definir permissões para a execução de scripts. Digite o seguinte comando para permitir a execução de scripts:

```powershell
Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope Process
```

Você receberá uma solicitação para confirmar essa ação, pois o administrador pode alterar o escopo de acordo com seu critério.

***Definir a política de execução***

![Definir alteração de política de execução no PowerShell](../media/powershell-set-execution-policy_image.png)

Agora que o console está configurado para permitir o script, execute o próximo comando para instalar o módulo:

```powershell
Install-Module -Name Microsoft.FastTrack -Repository PSGallery -WarningAction SilentlyContinue -Force
```

### <a name="prerequisites-for-module"></a>Pré-requisitos para o módulo

Para executar com êxito este módulo, você precisará instalar módulos dependentes para uso, caso eles ainda não estejam instalados. Talvez seja necessário reiniciar o PowerShell.

Para enviar um DSR, primeiro você deve fazer logon usando suas credenciais do Office 365. Inserir as credenciais adequadas validará o status do administrador global e coletará informações do locatário.

```powershell
Login-FastTrackAccount -ApiKey <API Key provided by FastTrack MVM>
```

Após o logon bem-sucedido, as credenciais e a chave serão armazenadas para uso com os módulos do FastTrack durante o restante da sessão atual do PowerShell.

Se você precisar se conectar a um ambiente de nuvem que não seja comercial, será necessário adicionar *-Environment* ao comando de *Logon* com um dos seguintes ambientes válidos:

- AzureCloud
- AzureChinaCloud
- AzureGermanCloud
- AzureUSGovernmentCloud

```powershell
Login-FastTrackAccount -ApiKey <API Key provided by FastTrack MVM> -Environment <cloud environment>
```

Para enviar uma solicitação de DSR, execute o seguinte comando:

```powershell
Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail SubjectUserEmail@mycompany.com
```

Em caso de sucesso, o cmdlet retornará um objeto ID da Transação. Mantenha a ID da Transação.

#### <a name="checking-the-status-of-a-request-transaction"></a>Verificar o status da transação de uma solicitação

Execute a seguinte função usando a ID da Transação obtida anteriormente:

```powershell
Get-FastTrackGdprDsrRequest -TransactionID "YourTransactionID"
```

#### <a name="transaction-status-codes"></a>Códigos de Status da Transação

|Transação|Status|
|---|---|
|**Criado**|A solicitação foi criada.|
|**Falhou**|Falha na criação da solicitação. Envie novamente ou contate o suporte.|
|**Concluída**|A solicitação foi concluída e corrigida.|
|

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->

## <a name="learn-more"></a>Saiba mais

[Central de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
