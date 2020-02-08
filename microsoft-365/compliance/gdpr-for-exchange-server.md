---
title: RGPD para Exchange Server
description: Saiba mais sobre como atender aos requisitos de RGPD no Exchange Server local.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 7d7837716cd453ee3331dced52fc82872a09fc8f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596438"
---
# <a name="gdpr-for-exchange-server"></a>RGPD para Exchange Server

Como parte da proteção de informações pessoais, recomendamos o seguinte:

-   Use [marcas e políticas de retenção](https://technet.microsoft.com/library/dd297955(v=exchg.160).aspx) no Exchange Server para implementar uma política de ciclo de vida de email.

-   Implante o [Gerenciamento de Direitos de Informação](https://technet.microsoft.com/library/dd638140(v=exchg.160).aspx) para limitar quem tem acesso às informações armazenadas no Exchange Server.

-   Habilite a [criptografia BitLocker](https://blogs.technet.microsoft.com/exchange/2015/10/20/enabling-bitlocker-on-exchange-servers/) em seus servidores.

## <a name="identifying-in-scope-content"></a>Identificar o conteúdo dentro do escopo

O Exchange usa dois repositórios de armazenamento principais para o conteúdo gerado pelo usuário final: caixas de correio e pastas públicas. O conteúdo armazenado na caixa de correio de um usuário individual está exclusivamente associado a esse usuário e representa seu repositório padrão no Exchange. Os dados armazenados em uma caixa de correio do usuário incluem conteúdo criado usando o Outlook, o Outlook na web (anteriormente conhecido como Outlook Web App), o Exchange ActiveSync, o Skype for Business e outras ferramentas de terceiros que se conectam aos servidores do Exchange usando POP, IMAP ou Serviços Web do Exchange (EWS). Exemplos desses itens incluem: mensagens, itens de calendário (reuniões e compromissos), contatos, anotações e tarefas. Excluir a caixa de correio de um usuário individual remove o conteúdo gerado ou enviado para esse usuário no contexto da sua caixa de correio. Você pode excluir caixas de correio de usuários usando o Centro de administração do Exchange (EAC) ou o cmdlet [Remove-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/remove-mailbox?view=exchange-ps) no Shell de Gerenciamento do Exchange. \
Observação: o parâmetro Permanent no cmdlet Remove-Mailbox deve ser usado com cuidado, pois os dados não poderão ser recuperados se essa opção for usada.

O Exchange também fornece caixas de correio compartilhadas que permitem que um ou mais usuários tenham acesso para enviar e receber o conteúdo que está armazenado em uma caixa de correio comum. A caixa de correio compartilhada é uma entidade exclusiva não associada a uma única conta. Em vez disso, vários usuários terão acesso para enviar, receber e analisar o conteúdo de email na caixa de correio compartilhada. Caixas de correio compartilhadas são administradas usando o Centro de administração do Exchange e os mesmos cmdlets usados para gerenciar caixas de correio de usuários normais. Se precisar remover mensagens individuais de uma caixa de correio, há diferentes opções disponíveis dependendo da sua versão do Exchange. No Exchange Server 2010 e 2013, você pode usar o cmdlet [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/search-mailbox?view=exchange-ps) com o parâmetro DeleteContent para identificar e remover as mensagens de uma caixa de correio. No Exchange Server 2016 e posterior, você precisa usar o recurso [New-ComplianceSearch](https://technet.microsoft.com/library/ff459253(v=exchg.160).aspx).

Pastas públicas são uma implementação de armazenamento compartilhado não associado a um usuário específico. Em vez disso, os usuários terão acesso às pastas públicas para gerar conteúdo. A implementação real de pastas públicas varia de acordo com a versão do Exchange (o Exchange Server 2010 usa uma implementação diferente do que o Exchange Server 2013 e posteriores). Existem ferramentas limitadas para gerenciar o conteúdo das pastas públicas. Ferramentas do cliente (por exemplo, o Outlook) são o principal mecanismo para gerenciar o conteúdo de pastas públicas. Há cmdlets de gerenciamento de objetos de pastas públicas, mas não para gerenciar itens de conteúdo individuais dentro da pasta pública. Um script personalizado que utiliza os Serviços Web do Exchange (EWS) ou outra ferramenta de terceiros provavelmente será necessário para gerenciar itens de pastas públicas individuais.

O principal requisito provavelmente será gerenciar o conteúdo da caixa de correio de um usuário individual. Essa exigência será facilmente cumprida com as ferramentas gráficas ou baseadas em cmdlets que você usa regularmente para gerenciar caixas de correio. Se precisar processar o conteúdo em várias caixas de correio ou tipos de recursos, a [Descoberta Eletrônica](https://technet.microsoft.com/library/dd298021(v=exchg.160).aspx) é o mecanismo preferencial do Exchange para identificar o conteúdo dentro do escopo.

## <a name="deleted-item-retention"></a>Retenção de item excluído

Quando você exclui mensagens individuais ou itens de uma caixa de correio (não a caixa de correio inteira ou o recurso de pasta pública propriamente dito), o conteúdo é mantido em uma forma recuperável com base no valor do parâmetro DeletedItemRetention para o banco de dados de caixa de correio ou da pasta pública. O valor padrão é 14 dias, mas esse valor é configurado por um administrador do Exchange.

## <a name="removing-soft-deleted-and-disconnected-mailboxes"></a>Remover caixas de correio excluídas temporariamente e desconectadas

Quando uma caixa de correio do Exchange é desabilitada, excluída ou movida entre bancos de dados (por exemplo, como parte do balanceamento de carga), ela é desabilitada, excluída temporariamente ou desconectada, dependendo da operação. Enquanto a caixa de correio estiver em qualquer um desses estados, o Exchange a manterá (incluindo seu conteúdo) com base no valor atual do parâmetro MailboxRetention especificado no banco de dados da caixa de correio. O valor padrão é 30 dias, mas esse valor pode ser configurado por um administrador do Exchange. Você pode usar o cmdlet [Remove-StoreMailbox](https://docs.microsoft.com/powershell/module/exchange/mailbox-databases-and-servers/remove-storemailbox?view=exchange-ps) para forçar o Exchange a remover permanentemente (eliminar) todos os dados associados a uma caixa de correio antes da expiração natural do período de retenção.

> [!IMPORTANT]
> Use o cmdlet Remove-StoreMailbox com cuidado, pois ele resulta em uma irrecuperável perda de dados para a caixa de correio de destino. 

## <a name="on-prem-to-cloud-migrations"></a>Migrações do local para a nuvem

Ao migrar dados do Exchange Server para o Exchange Online, os dados migrados podem permanecer no Exchange Server local de origem em um formato que pode ser recuperado por um administrador do Exchange. Por padrão, esses dados serão automaticamente removidos do banco de dados dentro de 30 dias (confira a seção Remover caixas de correio excluídas temporariamente e desconectadas acima).

## <a name="automatic-data-collection-reported-to-microsoft-by-exchange-server"></a>Coleta de dados automática reportada à Microsoft pelo Exchange Server

Servidores do Exchange implantados em ambientes locais não fornecem qualquer tipo de relatório automatizado ou captura de dados do usuário final para a Microsoft. Servidores do Exchange com relatórios de despejo de falha Watson habilitados no sistema operacional Windows podem receber uma porção limitada da memória no momento em que o relatório de falha é produzido.
