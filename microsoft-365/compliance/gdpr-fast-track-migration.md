---
title: RGPD
description: Orientação técnica da Microsoft — CONJUNTO DE FERRAMENTAS DE MIGRAÇÕES FASTTRACK PARA ENVIAR SOLICITAÇÃO DE EXCLUSÃO
keywords: Migração FastTrack, Microsoft 365 Education, documentação do Microsoft 365, RGPD
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
ms.prod: Microsoft-365-enterprise
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
ms.openlocfilehash: c5b79c29c6946ae66e53073189376e858e3d978b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073281"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a>Conjunto de ferramentas de migração FastTrack para envio de solicitação de exclusão

## <a name="toolset-purpose"></a>Finalidade do conjunto de ferramentas

Se você for um cliente envolvido atualmente com migrações FastTrack, a exclusão da conta de usuário do Office 365 não excluirá a cópia dos dados em posse da equipe do Microsoft FastTrack, mantida apenas para a conclusão da migração. Se, durante a migração, você quiser que a equipe do Microsoft FastTrack também exclua a cópia dos dados, envie uma solicitação por esse conjunto de ferramentas. No curso normal dos negócios, o Microsoft FastTrack excluirá todas as cópias dos dados após a conclusão da migração.

### <a name="supported-platforms"></a>Plataformas compatíveis
A Microsoft oferece suporte à versão inicial deste conjunto de ferramentas na plataforma do Windows e no console do PowerShell. Este conjunto de ferramentas oferece suporte às plataformas conhecidas a seguir:
 
***Tabela 1 - Plataformas compatíveis com este conjunto de ferramentas***
 
<!--start table here HEADER -->
 
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
| |**Windows 7**|**Windows 8**|**Windows 10**|**Windows Server 2012**|**Windows Server 2016**|
|PS 5.0|Not<br/>Com suporte|Com suporte|Com suporte|Com suporte|Com suporte|
|PS 5.1|Not<br/>Com suporte|Com suporte|Com suporte|Com suporte|Com suporte|
|||
 
<!-- end of table -->

### <a name="obtaining-the-toolset"></a>Como obter o conjunto de ferramentas

Este conjunto de ferramentas está disponível na Galeria do PowerShell no aplicativo de console do PowerShell. Para localizar e carregar o módulo desse cmdlet, primeiro abra o PowerShell no modo de administrador para que ele tenha as permissões apropriadas para instalar o módulo. Se você nunca usou o PowerShell, acesse a Barra de Tarefas do Windows e, na caixa de pesquisa, digite "PowerShell". Selecione o aplicativo de console usando o botão direito e escolha **Executar como administrador**, depois clique em **Sim** para executar o Windows PowerShell.

![PowerShell - Executar como administrador](../media/fasttrack-powershell_image.png)

![PowerShell - Permitir que o aplicativo faça alterações](../media/fasttrack-run-powershell_image.png)

Agora que o console está aberto, você precisa definir permissões para a execução do script. Digite o seguinte comando para permitir a execução dos scripts: ‘Set-ExecutionPolicy – ExecutionPolicy: Bypass – Scope:Process’

Você receberá uma solicitação para confirmar essa ação, pois o administrador pode alterar o escopo de acordo com seu critério.

***Definir a política de execução***

![Definir alteração de política de execução no PowerShell](../media/powershell-set-execution-policy_image.png)

Agora que o console está configurado para permitir o script, execute o próximo comando para instalar o módulo:

>`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery `
>        
>               -WarningAction: SilentlyContinue `
>               -Force’

### <a name="prerequisites-for-module"></a>Pré-requisitos para o módulo
Para executar com êxito este módulo, você precisará instalar módulos dependentes para uso, caso eles ainda não estejam instalados. Talvez seja necessário reiniciar o PowerShell.  

Para enviar um DSR, primeiro você deve fazer logon usando suas credenciais do Office 365 – as credenciais adequadas validarão seu status de administrador global e coletarão informações de locatário. 

**Login-FastTrackAccount -ApiKey: \<chave de API fornecida pela FastTrack MVM\>**

Após o logon bem-sucedido, as credenciais e a chave serão armazenadas para uso com os módulos do FastTrack durante o restante da sessão atual do PowerShell.

Se você precisar se conectar a um ambiente de nuvem que não seja comercial, será necessário adicionar *-Environment* ao comando de *Logon* com um dos seguintes ambientes válidos:
- AzureCloud
- AzureChinaCloud
- AzureGermanCloud
- AzureUSGovernmentCloud

**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <ambiente de nuvem\>**

Para enviar uma solicitação de DSR, execute o seguinte comando: Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: SubjectUserEmail@mycompany.com

Em caso de sucesso – o cmdlet retornará um objeto com um objeto ID da Transação. Guarde a ID da Transação.


#### <a name="checking-the-status-of-a-request-transaction"></a>Verificar o status da transação de uma solicitação

Execute a seguinte função usando a ID da Transação obtida anteriormente: FastTrackGdprDsrRequest Get - TransactionID: "SuaIDDaTransação"

#### <a name="transaction-status-codes"></a>Códigos de Status da Transação
<!--start table here no header -->

|||
|:-----|:-----|:-----|
|**Transação** |**Status**|
|**Created** |A solicitação foi criada|
|**Falhou**|Falha na criação da solicitação, envie de novo ou contate o suporte|
|**Concluída**|Solicitação foi concluída e corrigida|
|||

<!-- end of table -->

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->


## <a name="learn-more"></a>Saiba mais
[Central de Confiabilidade da Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
