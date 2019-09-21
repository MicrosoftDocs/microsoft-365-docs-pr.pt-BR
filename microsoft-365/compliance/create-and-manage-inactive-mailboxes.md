---
title: Criar e gerenciar caixas de correio inativas no Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
description: Você pode criar uma caixa de correio inativa no Office 365 aplicando uma política de retenção de bloqueio ou do Office 365 à caixa de correio e, em seguida, excluindo a conta de usuário do Office 365 correspondente. Os itens em uma caixa de correio inativa são mantidos pela duração da política de retenção ou retenção aplicada a ele antes de ser tornado inativo. Para excluir permanentemente uma caixa de correio inativa, apenas remova a política de retenção ou bloqueio.
ms.openlocfilehash: ca6fc5b579b6974ce89db14d318a6dc5a50f3f5c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072091"
---
# <a name="create-and-manage-inactive-mailboxes-in-office-365"></a>Criar e gerenciar caixas de correio inativas no Office 365

O Office 365 torna possível manter o conteúdo de caixas de correio excluídas. Esse recurso é chamado de [caixas de correio inativas](inactive-mailboxes-in-office-365.md). As caixas de correio inativas permitem manter os emails de ex-funcionários dos funcionários depois de saírem da sua organização. Uma caixa de correio fica inativa quando uma retenção de litígio ou uma política de retenção do Office 365 (criada no centro de segurança e conformidade do Office 365 ou Microsoft 365) é aplicada à caixa de correio antes que a conta de usuário do Office 365 correspondente seja excluída. O conteúdo de uma caixa de correio inativa é mantido pela duração da retenção que foi colocada na caixa de correio antes de ser desativada. Isso permite que administradores, gerentes de conformidade e gerentes de registros usem a pesquisa de conteúdo para pesquisar e exportar o conteúdo de uma caixa de correio inativa. As caixas de correio inativas não podem receber emails e não são exibidas no catálogo de endereços compartilhados da sua organização ou em outras listas.
  
> [!NOTE]
> Adiamos o prazo de 1º de julho de 2017 para criar novos Bloqueios In-loco para tornar uma caixa de correio inativa. Mas no final deste ano ou no início do próximo, você não poderá criar novos Bloqueios In-loco no Exchange Online. Nesse momento, somente retenções de litígio e políticas de retenção do Office 365 poderão ser usadas para criar uma caixa de correio inativa. No entanto, as caixas de correio inativas existentes que estão com Bloqueio In-loco ainda terão suporte, e você poderá continuar a gerenciar Bloqueios In-loco em caixas de correio inativas. Isso inclui a alteração da duração de um Bloqueio In-loco e a exclusão permanente de uma caixa de correio inativa, removendo o Bloqueio In-loco. 
  
## <a name="before-you-begin"></a>Antes de começar

- Para tornar uma caixa de correio inativa, deve ser atribuída uma licença do Exchange Online Plan 2 para que uma retenção de litígio ou uma política de retenção do Office 365 possa ser aplicada à caixa de correio antes de ser excluída. As licenças do Exchange Online Plan 2 fazem parte de uma assinatura do Office 365 Enterprise E3 e e5. Se uma caixa de correio for atribuída a uma licença de quiosque do Exchange Online plano 1 ou do Exchange Online (que fazem parte de uma assinatura do Office 365 E1 e F1, respectivamente), você precisará atribuir uma licença de arquivamento do Exchange Online separada para que uma retenção possa ser aplicada à caixa de correio b efore ele é excluído. Para saber mais, confira [Arquivamento do Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286153).
    
- As licenças associadas à caixa de correio do Exchange Online excluída estarão disponíveis após a exclusão da conta de usuário do Office 365 correspondente. Você pode [atribuir essas licenças a outro usuário](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc). 
    
- Se uma retenção de litígio ou uma política de retenção do Office 365 (que é configurada para reter ou reter e excluir conteúdo) não for aplicada a uma caixa de correio antes de ser excluída, o conteúdo da caixa de correio não será mantido ou detectável. No entanto, a caixa de correio excluída pode ser recuperada em até 30 dias após a exclusão, mas a caixa de correio e seu conteúdo serão excluídos permanentemente após 30 dias, se não for recuperado.
    
- Para obter mais informações sobre retenção de litígio, consulte [bloqueio in-loco e retenção de litígio](https://go.microsoft.com/fwlink/p/?LinkId=846124). Para obter mais informações sobre as políticas de retenção do Office 365, consulte [visão geral das políticas de retenção no Office 365](retention-policies.md).
  
## <a name="create-an-inactive-mailbox"></a>Criar uma caixa de correio inativa

Tornar uma caixa de correio inativa envolve duas etapas: 1) colocar a caixa de correio em retenção de litígio ou aplicar uma política de retenção do Office 365 a ela e 2) excluir a caixa de correio ou a conta de usuário do Office 365 correspondente. Depois que a caixa de correio estiver inativa, seu conteúdo será retido até que a política de retenção ou bloqueio seja removida.
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-an-office-365-retention-policy"></a>Etapa 1: colocar uma caixa de correio em retenção de litígio ou aplicar uma política de retenção do Office 365

Colocar uma caixa de correio em retenção de litígio ou aplicar uma política de retenção do Office 365 (que é configurada para reter ou reter e excluir conteúdo) retém o conteúdo da caixa de correio antes de ser excluída. Ambos os tipos de bloqueio manterão todo o conteúdo da caixa de correio, incluindo itens excluídos e versões originais de itens modificados. Itens excluídos e modificados são mantidos na caixa de correio inativa por um período especificado ou até que você exclua permanentemente a caixa de correio inativa, removendo a política de retenção ou bloqueio aplicada à caixa de correio inativa.
  
Se uma retenção já estiver colocada em uma caixa de correio ou se uma política de retenção do Office 365 já estiver aplicada a uma caixa de correio, tudo o que você precisará é excluir a conta de usuário do Office 365 correspondente, conforme explicado na etapa 2.
  
Para obter os procedimentos passo a passo para colocar uma caixa de correio em retenção de litígio ou aplicar uma política de retenção do Office 365, consulte:
  
- [Colocar uma caixa de correio em Retenção de Litígio](https://go.microsoft.com/fwlink/?linkid=856286)
    
- [Visão geral das políticas de retenção no Office 365](retention-policies.md)
    
> [!NOTE]
> Para contenções de litígio e políticas de retenção do Office 365, você pode criar uma retenção indefinida ou em uma retenção baseada em tempo. Em um bloqueio indefinido, o conteúdo da caixa de correio inativa será mantido para sempre ou até que a retenção seja removida ou até que a duração da retenção seja alterada. Após a remoção ou não da política de retenção (supondo que a caixa de correio tenha sido excluída há mais de 30 dias), a caixa de correio inativa será marcada para exclusão permanente e o conteúdo da caixa de correio não será mais mantido ou detectável. Em uma política de retenção baseada em tempo ou no Office 365, você especifica a duração da retenção. Essa duração é aplicada a cada item e é calculada a partir da data em que o item foi recebido ou criado. Após a expiração de um item de caixa de correio, e esse item é movido para ou localizado na pasta itens recuperáveis da caixa de correio inativa, o item é excluído permanentemente (removido) da caixa de correio inativa após o período de retenção do item excluído expirar. 
  
### <a name="step-2-delete-the-mailbox"></a>Etapa 2: Excluir a caixa de correio

Depois que a caixa de correio é colocada em espera ou uma política de retenção do Office 365 é aplicada a ela, a próxima etapa é excluir a caixa de correio. A melhor maneira de excluir uma caixa de correio é excluir a conta de usuário do Office 365 correspondente no centro de administração do Microsoft 365. Para obter informações sobre como excluir contas de usuário do Office 365, consulte [excluir um usuário da sua organização](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e).
  
> [!NOTE]
> Você também pode excluir a caixa de correio usando o cmdlet **Remove-Mailbox** no PowerShell do Exchange Online. Para saber mais, confira [Excluir ou restaurar caixas de correio do usuário no Exchange Online](https://go.microsoft.com/fwlink/?linkid=856287). 
  

## <a name="view-a-list-of-inactive-mailboxes"></a>Exibir uma lista de caixas de correio inativas

Para exibir uma lista das caixas de correio inativas em sua organização:
  
1. Acesse [https://protection.office.com](https://protection.office.com) e entre usando as credenciais de uma conta de administrador na sua organização do Office 365. 
    
2. Clique em**retenção**de **governança** > de dados.
    
3. Na página **retenção** , clique em **mais**![elipses](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)de barra de navegação e clique em **caixas de correio inativas**.
    
    ![Na página retenção, clique em mais e em caixas de correio inativas para exibir uma lista de caixas de correio inativas](media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    A página **caixas de correio inativas** é exibida. Observação o número total de caixas de correio inativas em sua organização é exibido. 
    
    ![Uma lista de todas as caixas de correio inativas em sua organização é exibida](media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
Como alternativa, você pode executar o seguinte comando no PowerShell do Exchange Online para exibir a lista de caixas de correio inativas.

```
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

Você pode clicar ![em exportar ícone](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) de resultados de pesquisa **Exportar** para exibir ou baixar um arquivo CSV que contém informações adicionais sobre as caixas de correio inativas em sua organização. 
  
Você também pode executar o seguinte comando para exportar a lista de caixas de correio inativas e outras informações para um arquivo CSV. Neste exemplo, o arquivo CSV é criado no diretório atual.

```
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```
   
> [!NOTE]
> É possível que uma caixa de correio inativa tenha o mesmo endereço SMTP de uma caixa de correio de usuário ativo. Nesse caso, o valor da propriedade **distinguishedName** ou **ExchangeGuid** pode ser usado para identificar exclusivamente uma caixa de correio inativa. 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>Pesquisar e exportar o conteúdo de uma caixa de correio inativa

Você pode acessar o conteúdo da caixa de correio inativa usando a ferramenta de pesquisa de conteúdo no centro de conformidade do & de segurança. Ao pesquisar uma caixa de correio inativa, você pode criar uma pesquisa por palavras chave para buscar itens específicos ou pode obter todo o conteúdo da caixa de correio inativa. Você pode visualizar os resultados da pesquisa ou exportar os resultados da pesquisa para um arquivo de dados do Outlook (PST) ou para mensagens de email individuais. Para obter os procedimentos passo a passo para pesquisar caixas de correio e exportar resultados de pesquisa, consulte os seguintes tópicos:
  
- [Pesquisa de conteúdo no Office 365](content-search.md)
    
- [Exportar os resultados da Pesquisa de Conteúdo](export-search-results.md)
    
Veja algumas coisas que você deve ter em mente ao pesquisar caixas de correio inativas.
  
- Se uma pesquisa de conteúdo incluir uma caixa de correio de usuário e essa caixa de correio for desativada, a pesquisa de conteúdo continuará a Pesquisar a caixa de correio inativa quando você executar novamente a pesquisa após ela se tornar inativa.
    
- Em alguns casos, um usuário pode ter uma caixa de correio ativa e uma caixa de correio inativa que tenha o mesmo endereço SMTP. Nesse caso, somente a caixa de correio específica que você selecionar como um local para uma pesquisa de conteúdo será pesquisada. Em outras palavras, se você adicionar a caixa de correio de um usuário a uma pesquisa, não poderá supor que as suas caixas de correio ativas e inativas serão pesquisadas; somente a caixa de correio que você adicionar explicitamente à pesquisa será pesquisada.
    
- É altamente recomendável que você evite ter uma caixa de correio ativa e uma caixa de correio inativa com o mesmo endereço SMTP. Se você precisar reutilizar o endereço SMTP atualmente atribuído a uma caixa de correio inativa, recomendamos recuperar a caixa de correio inativa ou restaurar o conteúdo de uma caixa de correio inativa para uma caixa de correio ativa (ou o arquivo de uma caixa de correio ativa) e excluir o caixa de correio inativa.
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Alterar a duração do bloqueio para uma caixa de correio inativa

Depois que uma caixa de correio é disponibilizada, você pode alterar a duração da retenção ou a política de retenção do Office 365 aplicada à caixa de correio inativa. Para obter os procedimentos passo a passo, consulte [alterar a duração da retenção para uma caixa de correio inativa no Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).
  
## <a name="recover-an-inactive-mailbox"></a>Recuperar uma caixa de correio inativa

Se um antigo funcionário retornar à sua organização ou se um novo funcionário for contratado para tomar as responsabilidades do trabalho do funcionário de parte, você poderá recuperar o conteúdo da caixa de correio inativa. Ao recuperar uma caixa de correio inativa, ela é convertida em uma nova caixa de correio, o conteúdo e a estrutura de pastas da caixa de correio inativa são mantidos e ela é vinculada a uma nova conta de usuário. Após sua recuperação, a caixa de correio inativa deixa de existir. Para obter os procedimentos passo a passo e obter mais informações sobre o que acontece quando você recupera uma caixa de correio inativa, consulte [recuperar uma caixa de correio inativa no Office 365](recover-an-inactive-mailbox.md).
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>Restaurar o conteúdo de uma caixa de correio inativa em outra caixa de correio

Se outro funcionário tomar as responsabilidades de trabalho de um funcionário antigo ou se outra pessoa precisar acessar o conteúdo da caixa de correio inativa, você poderá restaurar (ou mesclar) o conteúdo da caixa de correio inativa para uma caixa de correio existente. Quando você restaura uma caixa de correio inativa, o conteúdo é copiado para outra caixa de correio. A caixa de correio inativa é mantida e permanece uma caixa de correio inativa. A caixa de correio inativa ainda pode ser pesquisada usando a Descoberta Eletrônica, seu conteúdo pode ser restaurado para outra caixa de correio ou ela pode ser recuperada ou excluída posteriormente. Para obter os procedimentos passo a passo, consulte [restaurar uma caixa de correio inativa no Office 365](restore-an-inactive-mailbox.md).
  
## <a name="delete-an-inactive-mailbox"></a>Excluir uma caixa de correio inativa

Se você não precisar mais reter o conteúdo de uma caixa de correio inativa, você pode excluir permanentemente a caixa de correio inativa, removendo a isenção ou removendo a política de retenção do Office 365 aplicada à caixa de correio inativa. Se a caixa de correio foi excluída há mais de 30 dias, ela será marcada para exclusão permanente após você remover o bloqueio e não poderá mais ser recuperada. Se a caixa de correio foi excluída nos últimos 30 dias, ainda será possível recuperar a caixa de correio após remover a política de retenção ou bloqueio. Para obter os procedimentos passo a passo para remover uma retenção ou uma política de retenção do Office 365 para excluir permanentemente uma caixa de correio inativa, consulte [excluir uma caixa de correio inativa no Office 365](delete-an-inactive-mailbox.md).