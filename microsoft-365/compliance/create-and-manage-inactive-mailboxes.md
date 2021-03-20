---
title: Criar e gerenciar caixas de correio inativas
f1.keywords:
- NOCSH
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
ms.custom:
- seo-marvel-apr2020
description: Saiba como manter o conteúdo de caixas de correio excluídas usando o recurso caixas de correio inativas no Office 365.
ms.openlocfilehash: 45de882cf0931b85d3acd6368f619f94fce636d7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908375"
---
# <a name="create-and-manage-inactive-mailboxes"></a>Criar e gerenciar caixas de correio inativas

O Microsoft 365 possibilita que você mantenha o conteúdo das caixas de correio excluídas. Esse recurso é chamado de [caixas de correio inativas](inactive-mailboxes-in-office-365.md). Caixas de correio inativas permitem que você retenha os emails de ex-funcionários depois que eles saem da sua organização. Uma caixa de correio fica inativa quando uma Retenção de Litígio ou uma política de retenção (criada no centro de segurança e conformidade no Office 365 ou no Microsoft 365) é aplicada à caixa de correio antes da exclusão da conta de usuário correspondente. O conteúdo de uma caixa de correio inativa é mantido durante a espera que foi colocada na caixa de correio antes de ser inativa. Isso permite que administradores, gerentes de conformidade e gerentes de registros usem a Pesquisa de Conteúdo para pesquisar e exportar o conteúdo de uma caixa de correio inativa. As caixas de correio inativas não podem receber emails e não são exibidas no catálogo de endereços compartilhados da sua organização ou em outras listas.
  
> [!IMPORTANT]
> À medida que continuamos a investir em diferentes maneiras de preservar o conteúdo da caixa de correio, anunciamos a ress contração de In-Place no Centro de administração do Exchange. Isso significa que você deve usar as Políticas de Retenção e Retenção de Litígio para criar uma caixa de correio inativa. A partir de 1º de julho de 2020, você não poderá criar novos In-Place no Exchange Online. Mas você ainda poderá alterar a duração de espera de uma In-Place de espera colocada em uma caixa de correio inativa. No entanto, a partir de 1º de outubro de 2020, você não poderá alterar a duração da espera. Você só poderá excluir uma caixa de correio inativa removendo o In-Place Hold. As caixas de correio inativas existentes que estão em In-Place de espera ainda serão preservadas até que a espera seja removida. Para obter mais informações sobre a aposentadoria de In-Place Detém, consulte A aposentadoria de ferramentas [de Descoberta eDiscovery herdado.](legacy-ediscovery-retirement.md)
  
## <a name="preparations-before-creating-an-inactive-mailbox"></a>Preparações antes de criar uma caixa de correio inativa

- Para tornar uma caixa de correio inativa, ela deve receber uma licença do Plano 2 do Exchange Online para que uma Retenção de Litígio ou uma política de retenção possa ser aplicada à caixa de correio antes de ser excluída. As licenças do Plano 2 do Exchange Online fazem parte de uma assinatura do Office 365 Enterprise E3 e E5. Se uma caixa de correio for atribuída a uma licença do Plano 1 ou Quiosque do Exchange Online do Exchange Online (que fazem parte de uma assinatura do Office 365 E1 e F1, respectivamente), você terá que atribuí-la uma licença de Arquivamento do Exchange Online separada para que uma responsabilidade possa ser aplicada à caixa de correio antes de ser excluída. Para saber mais, confira [Arquivamento do Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286153).

- As licenças associadas à caixa de correio excluída do Exchange Online estarão disponíveis depois que você excluir a conta de usuário correspondente. Em seguida, [você pode atribuir essas licenças a outro usuário](../admin/manage/assign-licenses-to-users.md).

- Se uma Retenção de Litígio ou uma política de retenção (configurada para reter ou reter e excluir conteúdo) não for aplicada a uma caixa de correio antes de ser excluída, o conteúdo da caixa de correio não será retido ou descoberto. No entanto, a caixa de correio excluída pode ser recuperada dentro de 30 dias após a exclusão, mas a caixa de correio e seu conteúdo serão excluídos permanentemente após 30 dias se ela não for recuperada.

- Para obter mais informações sobre a responsabilidade por litígio, consulte [In-Place Hold and Litigation Hold](/exchange/security-and-compliance/in-place-and-litigation-holds). Para obter mais informações sobre políticas de retenção, [consulte Saiba mais sobre políticas de retenção e rótulos de retenção.](retention.md)
  
## <a name="create-an-inactive-mailbox"></a>Criar uma caixa de correio inativa

Tornar uma caixa de correio inativa envolve duas etapas: 1) colocar a caixa de correio em Retenção de Litígio ou aplicar uma política de retenção a ela e 2) excluir a caixa de correio ou a conta de usuário correspondente. Após a caixa de correio ficar inativa, seu conteúdo será mantido até que a política de retenção ou retenção seja removida.
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-a-retention-policy"></a>Etapa 1: colocar uma caixa de correio em Retenção de Litígio ou aplicar uma política de retenção

Colocar uma caixa de correio em Retenção de Litígio ou aplicar uma política de retenção (configurada para reter ou reter e excluir conteúdo) retém o conteúdo na caixa de correio antes de ser excluída. Ambos os tipos de retenção manterão todo o conteúdo da caixa de correio, incluindo itens excluídos e versões originais de itens modificados. Os itens excluídos e modificados são mantidos na caixa de correio inativa por um período especificado ou até que você exclua permanentemente a caixa de correio inativa removendo a política de retenção ou retenção aplicada à caixa de correio inativa.
  
Se uma retenção já estiver colocada em uma caixa de correio ou se uma política de retenção já estiver aplicada a uma caixa de correio, tudo o que você precisa fazer é excluir a conta de usuário correspondente, conforme explicado na Etapa 2.
  
Para procedimentos passo a passo para colocar uma caixa de correio em Retenção de Litígio ou aplicar uma política de retenção, consulte:
  
- [Colocar uma caixa de correio em Retenção de Litígio](./create-a-litigation-hold.md)
    
- [Saiba mais sobre políticas de retenção e rótulos de retenção no Office 365](retention.md)
    
> [!NOTE]
> Para as Políticas de Retenção e Retenção de Litígio, você pode criar uma retenção por tempo indeterminado ou em uma retenção baseada em tempo. Em uma espera indefinida, o conteúdo da caixa de correio inativa será mantido para sempre, ou até que a espera seja removida ou até que a duração da espera seja alterada. Depois que a política de retenção ou retenção for removida (supondo que a caixa de correio foi excluída há mais de 30 dias), a caixa de correio inativa será marcada para exclusão permanente e o conteúdo da caixa de correio não será mais retido ou descoberto. Em uma política de retenção ou retenção baseada em tempo, você especifica a duração da retenção. Essa duração é aplicada a cada item e é calculada a partir da data em que o item foi recebido ou criado. Depois que a retenção expirar para um item de caixa de correio e esse item for movido para ou está localizado na pasta Itens Recuperáveis na caixa de correio inativa, o item será excluído permanentemente (limpo) da caixa de correio inativa após o período de retenção do item excluído expirar. 
  
### <a name="step-2-delete-the-mailbox"></a>Etapa 2: Excluir a caixa de correio

Depois que a caixa de correio é colocada em retenção ou uma política de retenção é aplicada a ela, a próxima etapa é excluir a caixa de correio. A melhor maneira de excluir uma caixa de correio é excluir a conta de usuário correspondente no centro de administração do Microsoft 365. Para obter informações sobre como excluir contas de usuário, consulte [Excluir um usuário de sua organização](../admin/add-users/delete-a-user.md).
  
> [!NOTE]
> Você também pode excluir a caixa de correio usando o cmdlet **Remove-Mailbox** no PowerShell do Exchange Online. Para saber mais, confira [Excluir ou restaurar caixas de correio do usuário no Exchange Online](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes). 
  

## <a name="view-a-list-of-inactive-mailboxes"></a>Exibir uma lista de caixas de correio inativas

Para exibir uma lista das caixas de correio inativas em sua organização:
  
1. Vá para [https://protection.office.com](https://protection.office.com) e entre usando as credenciais de uma conta de administrador em sua organização. 
    
2. Clique **em Retenção de Governança de**  >  **Informações.**
    
3. Na página **Retenção,** clique em **Mais** releições da Barra de Navegação e clique ![ em Caixas de correio ](../media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) **inativas**.
    
    ![Na página Retenção, clique em Mais e em Caixas de Correio Inativas para exibir uma lista de caixas de correio inativas](../media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    A **página Caixas de correio inativas** é exibida. Observe que o número total de caixas de correio inativas em sua organização é exibido. 
    
    ![Uma lista de todas as caixas de correio inativas em sua organização é exibida](../media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
Como alternativa, você pode executar o seguinte comando no PowerShell do Exchange Online para exibir a lista de caixas de correio inativas.

```powershell
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

Você pode clicar em Exportar ícone de resultados de pesquisa Exportar para exibir ou baixar um arquivo CSV que contém informações adicionais sobre as caixas de correio ![ ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)  inativas em sua organização. 
  
Você também pode executar o seguinte comando para exportar a lista de caixas de correio inativas e outras informações para um arquivo CSV. Neste exemplo, o arquivo CSV é criado no diretório atual.

```powershell
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```

> [!NOTE]
> É possível que uma caixa de correio inativa possa ter o mesmo endereço SMTP de uma caixa de correio de usuário ativa. Nesse caso, o valor da propriedade **DistinguishedName** ou **ExchangeGuid** pode ser usado para identificar exclusivamente uma caixa de correio inativa. 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>Pesquisar e exportar o conteúdo de uma caixa de correio inativa

Você pode acessar o conteúdo da caixa de correio inativa usando a ferramenta Pesquisa de Conteúdo no Centro de Conformidade & Segurança. Ao pesquisar uma caixa de correio inativa, você pode criar uma pesquisa por palavras chave para buscar itens específicos ou pode obter todo o conteúdo da caixa de correio inativa. Você pode visualizar os resultados da pesquisa ou exportar os resultados da pesquisa para um arquivo de Dados do Outlook (PST) ou como mensagens de email individuais. Para procedimentos passo a passo para pesquisar caixas de correio e exportar resultados de pesquisa, consulte os seguintes tópicos:
  
- [Pesquisa de Conteúdo no Office 365](content-search.md)
    
- [Exportar resultados de Pesquisa de Conteúdo](export-search-results.md)
    
Eis alguns pontos a serem levados em consideração durante a pesquisa de caixas de correio inativas.
  
- Se uma pesquisa de conteúdo incluir uma caixa de correio de usuário e essa caixa de correio for inativa, a pesquisa de conteúdo continuará a pesquisar a caixa de correio inativa quando você reprisar a pesquisa depois que ela se tornar inativa.
    
- Em alguns casos, um usuário pode ter uma caixa de correio ativa e uma caixa de correio inativa com o mesmo endereço SMTP. Nesse caso, somente a caixa de correio específica selecionada como local para uma pesquisa de conteúdo será pesquisada. Em outras palavras, se você adicionar a caixa de correio de um usuário a uma pesquisa, não poderá supor que suas caixas de correio ativas e inativas serão pesquisadas; somente a caixa de correio que você adicionar explicitamente à pesquisa será pesquisada.
    
- Não é recomendável de forma alguma que você tenha uma caixa de correio ativa e uma inativa com o mesmo endereço SMTP. Se você precisar reutilizar o endereço SMTP atualmente atribuído a uma caixa de correio inativa, recomendamos recuperar a caixa de correio inativa ou restaurar o conteúdo de uma caixa de correio inativa para uma caixa de correio ativa (ou o arquivo morto de uma caixa de correio ativa) e excluir a caixa de correio inativa.
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Alterar a duração do bloqueio para uma caixa de correio inativa

Depois que uma caixa de correio é inativa, você pode alterar a duração da retenção ou a política de retenção aplicada à caixa de correio inativa. Para procedimentos passo a passo, consulte Alterar a duração da espera de uma caixa de correio [inativa no Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).
  
## <a name="recover-an-inactive-mailbox"></a>Recuperar uma caixa de correio inativa

Se um ex-funcionário retornar à sua organização ou se um novo funcionário for contratado para assumir as responsabilidades de trabalho do funcionário desapurado, você poderá recuperar o conteúdo da caixa de correio inativa. Ao recuperar uma caixa de correio inativa, ela é convertida em uma nova caixa de correio, o conteúdo e a estrutura de pastas da caixa de correio inativa são mantidos e ela é vinculada a uma nova conta de usuário. Após sua recuperação, a caixa de correio inativa deixa de existir. Para obter procedimentos passo a passo e mais informações sobre o que acontece quando você recupera uma caixa de correio inativa, consulte Recover an [inactive mailbox in office 365](recover-an-inactive-mailbox.md).
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>Restaurar o conteúdo de uma caixa de correio inativa em outra caixa de correio

Se outro funcionário assumir as responsabilidades de trabalho de um ex-funcionário ou se outra pessoa precisar acessar o conteúdo da caixa de correio inativa, você poderá restaurar (ou mesclar) o conteúdo da caixa de correio inativa para uma caixa de correio existente. Quando você restaura uma caixa de correio inativa, o conteúdo é copiado para outra caixa de correio. A caixa de correio inativa é mantida e permanece uma caixa de correio inativa. A caixa de correio inativa ainda pode ser pesquisada usando a Descoberta Eletrônica, seu conteúdo pode ser restaurado para outra caixa de correio ou ela pode ser recuperada ou excluída posteriormente. Para procedimentos passo a passo, consulte [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).
  
## <a name="delete-an-inactive-mailbox"></a>Excluir uma caixa de correio inativa

Se você não precisar mais reter o conteúdo de uma caixa de correio inativa, poderá excluir permanentemente a caixa de correio inativa removendo a retenção ou removendo a política de retenção aplicada à caixa de correio inativa. Se a caixa de correio foi excluída há mais de 30 dias, ela será marcada para exclusão permanente após você remover o bloqueio e não poderá mais ser recuperada. Se a caixa de correio foi excluída nos últimos 30 dias, você ainda poderá recuperar a caixa de correio após remover a política de retenção ou retenção. Para procedimentos passo a passo para remover uma retenção ou uma política de retenção para excluir permanentemente uma caixa de correio inativa, consulte Excluir uma caixa de correio [inativa](delete-an-inactive-mailbox.md).