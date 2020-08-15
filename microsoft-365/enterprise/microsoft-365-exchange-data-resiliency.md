---
title: Resiliência de dados do Exchange Online no Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
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
description: Neste artigo, encontre uma explicação dos vários aspectos da resiliência de dados no Exchange Online e no Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfc53fd48a6de61cf47a0441cd2f8b0fa35a73f1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695342"
---
# <a name="exchange-online-data-resiliency-in-microsoft-365"></a>Resiliência de dados do Exchange Online no Microsoft 365

Há dois tipos de danos que podem afetar um banco de dados do Exchange: corrupção física, que normalmente é causado por problemas de hardware (em particular, hardware de armazenamento) e danos lógicos, que ocorre devido a outros fatores. Geralmente, há dois tipos de corrupção lógica que podem ocorrer em um banco de dados do Exchange: 
- **Corrupção lógica do banco** de dados-o checksum da página do banco de dados corresponde, mas os dados na página estão errados de forma lógica. Isso pode ocorrer quando o mecanismo de banco de dados (o mecanismo de armazenamento extensível (ESE) tenta gravar uma página de banco de dados e, embora o sistema operacional retorne uma mensagem de êxito, os dados nunca são gravados no disco ou gravados no lugar errado. Isso é conhecido como *liberação perdida*. O ESE inclui vários recursos e proteções projetadas para impedir a corrupção física de um banco de dados e outros cenários de perda de dados. Para evitar que as liberações perdidas percam dados, o ESE inclui um mecanismo de detecção de liberação perdido no banco de dados, juntamente com um recurso (restauração de página única) para corrigi-lo. 
- **Corrupção lógica de armazenamento** -os dados são adicionados, excluídos ou manipulados de forma que o usuário não espera. Esses casos normalmente são causados por aplicativos de terceiros. Ele normalmente é apenas um dano no sentido em que o usuário o considera assim. O repositório do Exchange considera a transação que produziu o dano lógico uma série de operações MAPI válidas. Os recursos de [bloqueio in-loco](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) no Exchange Online oferecem proteção contra corrupção lógica de armazenamento (porque impede que o conteúdo seja excluído permanentemente por um usuário ou um aplicativo). 

O Exchange Online executa várias verificações de consistência em arquivos de log replicados durante a inspeção de logs e a repetição de log. Essas verificações de consistência impedem que a corrupção física seja replicada pelo sistema. Por exemplo, durante a inspeção do log, há uma verificação de integridade física que verifica o arquivo de log e valida que a soma de verificação registrada no arquivo de log corresponde à soma de verificação gerada na memória. Além disso, o cabeçalho do arquivo de log é examinado para garantir que a assinatura do arquivo de log registrada no cabeçalho do log corresponda à do arquivo de log. Durante a repetição de log, o arquivo de log fica em uma análise mais detalhada. Por exemplo, o cabeçalho do banco de dados também contém a assinatura de log que é comparada com a assinatura do arquivo de log para garantir que eles correspondam. 

A proteção contra a corrupção dos dados de caixa de correio no Exchange Online é obtida usando a proteção de dados nativa do Exchange, uma estratégia de resiliência que aproveita a replicação de nível de aplicativo em vários servidores e vários datacenters, juntamente com outros recursos que ajudam a proteger os dados contra a perda ou outros motivos. Esses recursos incluem recursos nativos que são gerenciados pela Microsoft ou pelo próprio aplicativo Exchange Online, como:

- [Grupos de disponibilidade de dados](https://docs.microsoft.com/exchange/back-up-email)
- Correção de bit único 
- Verificação de banco de dados online 
- Detecção de liberação perdida 
- Restauração de página única 
- Serviço de replicação de caixa de correio 
- Verificações de arquivo de log 
- Implantação no sistema de arquivos resiliente 

Para obter mais informações sobre os recursos nativos listados acima, clique nos hiperlinks acima e veja a seguir as informações adicionais e para obter detalhes sobre os itens sem hiperlinks. Além desses recursos nativos, o Exchange Online também inclui recursos de resiliência de dados que os clientes podem gerenciar, como: 
- [Recuperação de item único (habilitada por padrão)](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages) 
- [Bloqueio In-loco e Retenção de Litígio](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds) 
- [Retenção de item excluído e caixas de correio excluídas por software (habilitadas por padrão)](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes) 

## <a name="database-availability-groups"></a>Grupos de disponibilidade de banco de dados 
Cada banco de dados de caixa de correio no Microsoft 365 é hospedado em um [grupo de disponibilidade de banco de dados (DAG)](https://docs.microsoft.com/exchange/back-up-email) e replicado para datacenters separados geograficamente dentro da mesma região. A configuração mais comum é de quatro cópias de banco de dados em quatro data centers; no entanto, algumas regiões têm menos datacenters (bancos de dados são replicados para três data centers na Índia e dois datacenters na Austrália e no Japão). Mas em todos os casos, cada banco de dados de caixa de correio tem quatro cópias que são distribuídas por vários datacenters, garantindo que os dados da caixa de correio estejam protegidos de software, hardware e até mesmo falhas de datacenter. 

Dessas quatro cópias, três delas são configuradas como altamente disponíveis. A quarta cópia é configurada como uma [cópia de banco de dados](https://docs.microsoft.com/Exchange/high-availability/manage-ha/activate-lagged-db-copies)com retardamento. A cópia de banco de dados com retardamento não se destina a recuperação de caixa de correio ou de caixa de correio individual. Sua finalidade é fornecer um mecanismo de recuperação para o raro evento de danos lógicos catastróficos em todo o sistema. 

Cópias de banco de dados com retardamento no Exchange Online são configuradas com um tempo de retardo de repetição de um arquivo de log de sete dias. Além disso, o Gerenciador de retardo de repetição do Exchange é habilitado para fornecer um arquivo de log dinâmico, que é executado para cópias com retardamento para permitir que cópias de bancos de dados com o autoreparo e gerenciar o aumento do arquivo de log Embora as cópias de banco de dados com retardamento sejam usadas no Exchange Online, é importante entender que elas não são um backup point-in-time garantido. Cópias de banco de dados com retardamento no Exchange Online têm um limite de disponibilidade, geralmente em torno de 90%, devido a pontos em que o disco que contém uma cópia com retardamento é perdido devido à falha de disco, a cópia com retardamento se torna uma cópia altamente disponível (devido à execução automática), bem como aos períodos em que a cópia de banco de dados com atraso é 

## <a name="transport-resilience"></a>Resiliência de transporte 
O Exchange Online inclui dois recursos de resiliência de transporte primários: redundância de sombra e rede de segurança. A redundância de sombra mantém uma cópia redundante de uma mensagem enquanto está em trânsito. A rede segura mantém uma cópia redundante de uma mensagem após a mensagem ser entregue com êxito. 

Com a redundância de sombra, cada servidor de transporte do Exchange Online faz uma cópia de cada mensagem que recebe antes de confirmar a recepção bem-sucedida da mensagem ao servidor de envio. Isso torna as mensagens no pipeline de transporte redundantes enquanto estão em trânsito. Se o Exchange Online determinar que a mensagem original foi perdida no trânsito, uma cópia redundante da mensagem será entregue novamente. 

A rede segura é uma fila de transporte associada ao serviço de transporte em um servidor de caixa de correio. Esta fila armazena cópias de mensagens que foram processadas com êxito pelo servidor. Quando um banco de dados de caixa de correio ou de servidor requer a ativação de uma cópia desatualizada do banco de dados de caixa de correio, as mensagens na fila da rede de segurança são reenviadas automaticamente para a nova cópia ativa do banco de dados de caixa de correio. A rede segura também é redundante, eliminando assim o transporte como um único ponto de falha. Ele usa o conceito de uma rede de segurança principal e uma rede de segurança de sombra em que se a rede de segurança principal não estiver disponível por mais de 12 horas, as solicitações de reenvio se tornarão as solicitações de reenvio de sombra e as mensagens são reenviadas da rede de segurança de sombra.

Os reenvios de mensagem da rede de segurança são iniciados automaticamente pelo componente Gerenciador ativo do serviço de replicação do Microsoft Exchange que gerencia as cópias de banco de dados de DAGs e de caixa de correio. Nenhuma ação manual é necessária para reenviar mensagens da rede de segurança. 

## <a name="single-bit-correction"></a>Correção de bit único 
O ESE inclui um mecanismo para detectar e resolver erros de CRC de um único bit (conhecidos como inversão de bit único) que são o resultado de erros de hardware (e, como eles representam corrupção física). Quando esses erros ocorrem, o ESE os corrige automaticamente e registra um evento no log de eventos. 

## <a name="online-database-scanning"></a>Verificação de banco de dados online 
A verificação de banco de dados online (também conhecida como soma de verificação de *banco*de dados) é o processo em que um ESE usa um verificador de consistência de banco de dados para ler cada página e verificar a corrupção da página O objetivo principal é detectar corrupção física e liberações perdidas que podem não ser detectadas por operações transacionais. A verificação de banco de dados também realiza operações de falha no post-Store. O espaço pode ser vazado devido a falhas, e a verificação de banco de dados online localiza e recupera o espaço perdido. O sistema é projetado com a expectativa de que todos os bancos de dados sejam totalmente verificados uma vez a cada sete dias. 

## <a name="lost-flush-detection"></a>Detecção de liberação perdida 
Uma liberação perdida ocorre quando uma operação de gravação de banco de dados que o subsistema de disco/sistema operacional retornou como concluído não foi realmente gravada no disco ou foi gravada no local errado. Os incidentes de liberação perdidos podem resultar em corrupção lógica do banco de dados, portanto, para evitar que as liberações perdidas resultem em perda de dados, o ESE inclui um mecanismo de detecção de liberação perdido. Como as páginas do banco de dados são gravadas em cópias passivas, uma verificação é realizada para liberações perdidas na cópia ativa. Se uma liberação perdida for detectada, o ESE poderá reparar o processo usando um processo de aplicação de patch de página. 

## <a name="single-page-restore"></a>Restauração de página única 
Restauração de página única, aka a *correção de página*, é um processo automático onde as páginas de banco de dados corrompidas são substituídas por cópias saudáveis de uma réplica íntegra. O processo de reparo para uma página corrompida depende se a cópia do banco de dados está ativa ou passiva. Quando uma cópia de banco de dados ativa encontra uma página corrompida, ela pode copiar uma página de uma de suas réplicas, desde que a página que ele copia esteja totalmente atualizada. Isso é feito colocando uma solicitação para a página no fluxo de log, que é a base da replicação de banco de dados de caixa de correio. Assim que uma réplica encontra a solicitação de página que responde enviando uma cópia da página para a cópia do banco de dados solicitante. A restauração de página única também fornece um mecanismo de comunicação assíncrono para que o Active solicite uma página de réplicas, mesmo que as réplicas estejam offline no momento. 

No caso de corrupção em uma cópia de banco de dados passiva, incluindo uma cópia de banco de dados com retardamento, pois essas cópias estão sempre atrás de sua cópia ativa, é sempre seguro copiar qualquer página da cópia ativa para uma cópia passiva. Uma cópia de banco de dados passiva é por natureza altamente disponível, portanto, durante o processo de correção de página, a repetição de log é suspensa, mas a cópia de log continua. A cópia de banco de dados passiva recupera uma cópia da página corrompida da cópia ativa, aguarda até que o arquivo de log que atenda ao requisito de geração de log máximo necessário seja copiado e inspecionado e, em seguida, correção a página corrompida. Depois que a página for corrigida, a repetição de log será retomada. O processo é o mesmo para a cópia de banco de dados com atraso, exceto pelo fato de que o banco de dados com atraso primeiro repete todos os arquivos de log necessários para obter um estado de patch. 

## <a name="mailbox-replication-service"></a>Serviço de replicação de caixa de correio 
A movimentação de caixas de correio é uma parte fundamental do gerenciamento de um serviço de email em larga escala. Há sempre tecnologias atualizadas e atualizações de hardware e versão para lidar com o, portanto, ter um sistema acelerado e robusto que permite que nossos engenheiros realizem esse trabalho e, ao mesmo tempo, mantém a caixa de correio transparente para os usuários (garantindo que eles permaneçam online ao longo do processo) é fundamental e garantir que o processo seja dimensionado com mais eficiência quando as caixas de correio 

O serviço de replicação de caixa de correio do Exchange (Sra) é responsável por mover caixas de correio entre bancos de dados. Durante a movimentação, a Sra executa uma verificação de consistência em todos os itens da caixa de correio. Se for encontrado um problema de consistência, o Sra corrigirá o problema ou ignorará os itens corrompidos, removendo assim os danos da caixa de correio. 

Como o Sra é um componente do Exchange Online, podemos fazer alterações em seu código para tratar de novas formas de danos que foram detectadas no futuro. Por exemplo, se detectarmos um problema de consistência que o Sra não consegue corrigir, podemos analisar a corrupção, alterar o código da Sra e corrigir a inconsistência (se entendermos como). 

## <a name="log-file-checks"></a>Verificações de arquivo de log 
Todos os arquivos de log de transações gerados por um banco de dados do Exchange passam por várias formas de verificações de consistência. Quando um arquivo de log é criado, a primeira coisa executada é um padrão de bits é escrito e uma série de gravações de log é executada. Isso permite que o Exchange Online execute uma série de verificações (liberação perdida, CRC e outras verificações) para validar cada arquivo de log conforme ele é gravado e, novamente, conforme é replicado. 

## <a name="deployment-on-resilient-file-system"></a>Implantação no sistema de arquivos resiliente 
Para ajudar a evitar que os danos ocorram no nível do sistema de arquivos, o Exchange Online está sendo implantado em partições do sistema de arquivos resiliente (ReFS) para fornecer recursos de recuperação aprimorados. ReFS é um sistema de arquivos no Windows Server 2012 e posterior que é projetado para ser mais resistente em relação à corrupção de dados, maximizando a disponibilidade e a integridade dos dados. Especificamente, o ReFS traz melhorias na forma em que os metadados são atualizados, oferecendo melhor proteção para os dados e reduz os casos de corrupção de dados. Ele também usa somas de verificação para verificar a integridade dos dados dos arquivos e dos metadados, garantindo que a corrupção dos dados seja facilmente encontrada e reparada. 

O Exchange Online aproveita as vantagens de vários benefícios de ReFS: 
- Mais resiliência na integridade dos dados significa menos incidentes de corrupção de dados. Reduzir o número de incidentes de corrupção significa menos resemente de banco de dados desnecessárias. 
- Checksum em execução em metadados permitindo detecções de casos de corrupção mais cedo e, de forma mais determinista, permitindo a correção dos dados de corrupção antes que as falhas de cinza ocorram nos volumes de dados.
- Projetado para funcionar bem com conjuntos de dados extremamente grandes — petabytes e maiores, sem impacto no desempenho
- Suporte para outros recursos usados pelo Exchange Online, como a criptografia BitLocker. 

O Exchange Online também se beneficia de outros recursos ReFS: 
- **Integridade (fluxos de integridade)** -ReFS armazena dados de uma maneira que o protege de muitos dos erros comuns que podem normalmente causar perda de dados. A pesquisa do Microsoft 365 usa fluxos de integridade para ajudar com a detecção de corrupção de disco inicial e somas de verificação do conteúdo do arquivo. O recurso também reduz incidentes de corrupção causados por "gravações rasgadas" (quando uma operação de gravação não é concluída devido a interrupções de energia, etc.). 
- **Disponibilidade (Salvage)** -ReFS prioriza a disponibilidade de dados. Historicamente, os sistemas de arquivos geralmente eram suscetíveis à corrupção de dados que exigiria que o sistema fosse colocado offline para reparos. Embora seja raro, se ocorrer corrupção, ReFS implementa Salvage, um recurso que remove os dados corrompidos do namespace em um volume ativo e garante que bons dados não sejam afetados de forma adversa por dados corrompidos não reemparelhados. A aplicação do recurso Salvage e o isolamento dos dados corrompidos aos volumes do banco de dados do Exchange Online significa que podemos manter os bancos de dados não afetados em um volume corrompido em integridade entre o tempo de corrupção e a ação de reparo. Isso aumenta a disponibilidade de bancos de dados que normalmente seriam afetados por problemas de corrupção de disco. 