---
title: Exclusão de dados do Exchange Online da Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Saiba como as exclusões de dados suaves e difíceis para caixas de correio e itens em caixas de correio são tratadas no Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63bb5dcde334f7c53554f910b1a8d17e1d0d69cc
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332515"
---
# <a name="exchange-online-data-deletion-in-microsoft-365"></a>Exclusão de dados do Exchange Online no Microsoft 365

No Exchange Online, há dois tipos de exclusões: exclusões suaves e exclusões graves. Isso se aplica a caixas de correio e itens em uma caixa de correio.

## <a name="soft-deleted-and-hard-deleted-mailboxes"></a>Caixas de correio excluídas de forma reversível e excluída
Uma caixa de correio de usuário excluída por software é uma caixa de correio que foi excluída usando o centro de administração do Microsoft 365 ou o cmdlet Remove-Mailbox e ainda está na lixeira do Azure Active Directory por menos de 30 dias. Uma caixa de correio pode ser excluída de forma reversível de uma das seguintes maneiras:
- A conta de usuário do Azure Active Directory associada da caixa de correio do usuário é excluída por software (o objeto do usuário está fora do escopo ou no contêiner da lixeira).
- A conta de usuário do Azure Active Directory associada da caixa de correio do usuário foi excluída, mas a caixa de correio do Exchange Online está em uma retenção de litígio ou em retenção de descoberta eletrônica.
- A conta de usuário do Azure Active Directory associada da caixa de correio do usuário foi removida nos últimos 30 dias; que é o comprimento máximo de retenção do Exchange Online manterá a caixa de correio em um estado de exclusão reversível antes de ser limpada permanentemente e não poderá ser recuperada.

Uma caixa de correio de usuário excluída por hardware é uma caixa de correio excluída de uma das seguintes maneiras:
- A caixa de correio do usuário foi excluída por mais de 30 dias e o usuário do Azure Active Directory associado foi excluído de forma permanente. Todo o conteúdo da caixa de correio, como emails, contatos e arquivos, é excluído permanentemente.
- A conta de usuário associada à caixa de correio do usuário foi excluída do Azure Active Directory. A caixa de correio do usuário agora é excluída de forma reversível no Exchange Online e permanece em um estado de exclusão reversível por 30 dias. Se, no período de 30 dias, um novo usuário do Azure Active Directory é sincronizado da conta de destinatário original com o mesmo **ExchangeGuid** ou **ArchiveGuid**e essa nova conta é licenciada para o Exchange Online, isso resultará em uma exclusão difícil da caixa de correio do usuário original. Todo o conteúdo da caixa de correio, como emails, contatos e arquivos, é excluído permanentemente.
- Uma caixa de correio excluída por software é excluída usando **Remove-Mailbox-PermanentlyDelete**.

Os cenários de exclusão acima supõem que a caixa de correio do usuário não está em nenhum dos Estados de espera, como retenção de litígio ou bloqueio de descoberta eletrônica. Se houver algum tipo de bloqueio na caixa de correio, a caixa de correio não poderá ser excluída. Para todos os tipos de destinatários do usuário de email, todas as configurações de [retenção](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e?ui=en-US&rs=en-US&ad=US) são ignoradas e não têm efeito sobre exclusões ou exclusões reversível.

## <a name="soft-deleted-and-hard-deleted-items"></a>Itens excluídos por software e excluídos por hardware
Quando um usuário exclui um item de caixa de correio (como uma mensagem de email, um contato, um compromisso de calendário ou uma tarefa), o item é movido para a pasta itens recuperáveis e para uma subpasta chamada "exclusões". Isso é conhecido como exclusão reversível. O tempo de permanência dos itens excluídos na pasta Exclusões depende do período de retenção do item excluído que é definido para a caixa de correio. Uma caixa de correio do Exchange Online mantém itens excluídos por padrão para 14 dias, mas os administradores do Exchange Online podem alterar essa configuração para aumentar o período de até 30 dias. (Para obter etapas detalhadas sobre como aumentar o período de retenção de itens excluídos para uma caixa de correio do Exchange Online, confira [alterar o tempo que os itens excluídos permanentemente são mantidos para uma caixa de correio do Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/change-deleted-item-retention).) Os usuários podem recuperar ou excluir itens excluídos antes que o tempo de retenção de um item excluído expire. Para fazer isso, eles usam o recurso recuperar itens excluídos no Microsoft Outlook ou no Outlook na Web.

Se um usuário limpar um item excluído usando o recurso recuperar itens excluídos no Outlook ou no Outlook na Web, isso é conhecido como exclusão difícil. No Exchange Online, a recuperação de item individual é habilitada por padrão quando uma nova caixa de correio é criada, de forma que um administrador ainda pode [recuperar](https://docs.microsoft.com/Exchange/recipients/user-mailboxes/recover-deleted-messages) os itens excluídos por hardware antes que o período de retenção do item excluído expire. Além disso, se uma mensagem for alterada por um usuário ou processo, cópias do item original também serão mantidas quando a recuperação de item único estiver habilitada.

## <a name="page-zeroing"></a>Anulação de página
A *anulação* é um mecanismo de segurança que grava zeros ou um padrão binário sobre dados excluídos para que os dados excluídos sejam mais difíceis de recuperar. No Exchange Online, os bancos de dados de caixa de correio usam *páginas* como sua unidade de armazenamento e implementam um processo de substituição chamado *anulação de página*. A anulação de página é habilitada por padrão e não pode ser desabilitada por clientes ou pela Microsoft. Operações de anulação de página são registradas nos arquivos de log de transações para que todas as cópias de um determinado banco de dados sejam de página de forma semelhante. A anulação de uma página em uma cópia de banco de dados ativa faz com que a página seja zerada em cópias passivas do banco de dados.

A anulação de página grava um padrão binário sobre registros excluídos de forma fixa. O padrão de anulação de página é específico para operações do mecanismo de armazenamento extensível (ESE) (o nome do mecanismo de banco de dados interno usado por servidores no Exchange Online) e é diferente para operações em tempo de execução versus operações de manutenção de banco de dados em segundo plano. (A manutenção de banco de dados em segundo plano é um processo que efetua a soma de verificação continuamente e examina cada banco de dados Sua função principal é a página de banco de dados de soma de verificação, mas também manipula o espaço de limpeza e zera os registros e as páginas que não foram zeradas por causa de uma falha de armazenamento.)

A tabela a seguir lista os padrões de preenchimento que correspondem a operações em tempo de execução específicas.

| Operação em tempo real do ESE   | Padrão de preenchimento |
|--------------------------|--------------|
| Substituir                  | R            |
| Exclusão de valor longo/registro | D            |
| Liberação de espaço em página         | H            |


A tabela a seguir lista os padrões de preenchimento que correspondem a operações específicas que ocorrem durante a manutenção de banco de dados em segundo plano do ESE.

| Operação de manutenção de banco de dados em segundo plano do ESE | Padrão de preenchimento |
|-----------------------------------------------|--------------|
| Exclusão de gravação                                 | D            |
| Exclusão de valor longo                             | L            |
| Liberação de espaço em página parcialmente utilizada       | Z            |
| Liberação de espaço em página não utilizada               | U            |


### <a name="page-zeroing-process"></a>Processo de anulação de página
O processo de anulação de página depende do cenário de exclusão. A tabela a seguir discute os cenários de exclusão de banco de dados, e quando as funções de anulação de página ocorrem.

| Cenário de exclusão de banco de dados | Processo do ESE e tempo para anulação dos dados do banco de dados |
|-----------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| O item expira com base no período de retenção do item excluído. | Um thread assíncrono grava um padrão binário sobre os dados excluídos. Essa ação ocorre milissegundos após a exclusão do registro. Se o processo de armazenamento falhar enquanto o trabalho com a anulação assíncrona ainda estiver pendente (ou a limpeza do repositório de versão for cancelada devido ao aumento do armazenamento de versão), a anulação será concluída quando a manutenção do banco de dados de fundo processar essa seção do banco de dados. |
| Cenário de exibição: expiração de itens do Outlook/Outlook no modo de exibição pasta da Web (por exemplo, modo de exibição de conversa) | A anulação de dados ocorre quando uma manutenção de banco de dados em segundo plano processa esta seção do banco de dados. |
| Cenário mover caixa de correio/excluir caixa de correio: fonte excluída (expiração da caixa de correio excluída) | A anulação de dados ocorre quando uma manutenção de banco de dados em segundo plano processa esta seção do banco de dados. |

### <a name="mailbox-data-types-without-page-zeroing"></a>Tipos de dados de caixa de correio sem anulação de página
Os seguintes tipos de dados de caixa de correio não têm nenhuma cláusula para anulação de página:
- **Logs de transação de banco de dados de caixa de correio** -quando os logs de transação são excluídos como parte de operações normais, não há nenhum processo como zero os blocos no sistema de arquivos que armazenou os arquivos de log excluídos. É provável que o sistema de arquivos reutilize rapidamente esse espaço livre para logs recém-criados, mas não há garantias de que isso ocorrerá.
- **Arquivos de catálogo de índice de conteúdo** -o Exchange Online usa o Search Foundation (também conhecido como rápido) para a funcionalidade de indexação de pesquisa. O catálogo de índice de pesquisa é composto por vários arquivos de dezenas armazenados no mesmo volume que o arquivo de banco de dados de caixa de correio. Quando um arquivo é excluído de forma irreversível do banco de dados de caixa de correio, o conteúdo associado no catálogo de pesquisa não é excluído imediatamente. A exclusão de conteúdo ocorre quando o Search Foundation faz uma sombra (ou mesclagem mestra) de muitos arquivos de catálogo pequenos em um único arquivo maior. Depois que a mesclagem mestre é concluída, os arquivos menores de catálogo são excluídos. Não há processo para anular os blocos que armazenavam os arquivos de catálogo excluídos.

## <a name="continuous-replication"></a>Replicação Contínua
A replicação contínua (também conhecida como envio de logs e repetição) é a tecnologia do Exchange Online que cria e mantém cópias de cada banco de dados de caixa de correio para fornecer alta disponibilidade, resiliência de site e recuperação de desastre. A replicação contínua aproveita o suporte à recuperação de falhas de banco de dados do Exchange Server para fornecer tecnologia que realiza a atualização assíncrona de uma ou mais cópias de um banco de dados de caixa de correio. Cada servidor de caixa de correio registra as atualizações feitas em um banco de dados ativo (por exemplo, atividade de email do usuário) como registros de log em um conjunto seqüencial de 1 MB de arquivos de log de transações. Esse conjunto de arquivos é conhecido como o fluxo de log. Na replicação contínua, o fluxo de log também é usado para atualizar de forma assíncrona uma ou mais cópias de um banco de dados. Isso é feito por meio da transmissão dos logs para um local que contém uma cópia passiva do banco de dados ativo e, em seguida, reproduzindo-os na cópia de banco de dados passiva. Se todos os logs do banco de dados ativo são reproduzidos em uma cópia passiva do banco de dados, os dois bancos de dados são equivalentes e é o processo pelo qual qualquer alteração física feita em um banco de dados ativo é replicada para todas as cópias passivas desse banco de dados.

Qualquer exclusão de um banco de dados de caixa de correio, se um item de caixa de correio ou uma caixa de correio inteira, e se uma exclusão reversível ou uma exclusão de hardware, representa uma alteração física no banco de dados ativo. A anulação de página também envolve a realização de alterações físicas no banco de dados ativo. Essas alterações são gravadas nos arquivos de log por meio de um processo chamado replicação contínua e, quando esses arquivos de log são reproduzidos em relação a cópias passivas do banco de dados, as mesmas alterações físicas são feitas nesses bancos de dados passivos.