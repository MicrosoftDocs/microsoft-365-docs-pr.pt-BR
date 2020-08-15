---
title: Monitoramento e auto-recuperação da Microsoft 365
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
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá sobre os recursos de monitoramento e auto-recuperação do Microsoft 365.
ms.openlocfilehash: 459fdb50577c255d3cf27a31dbbbdd5768392c44
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687487"
---
# <a name="microsoft-365-monitoring-and-self-healing"></a>Monitoramento e auto-recuperação da Microsoft 365

Dada a escala do Microsoft 365, seria impossível manter os dados do cliente resistentes e seguros contra malware sem o monitoramento integrado, que é um alerta abrangente e de auto-recuperação, que é mais rápido e confiável. Monitorar um conjunto de serviços na escala do Microsoft 365 é muito desafiador. Novas mentalidades e metodologias precisavam ser introduzidas, e todos os novos conjuntos de tecnologia precisavam ser criados para operar e gerenciar o serviço em um ambiente global conectado. Mudamos para longe da abordagem de monitoramento tradicional da coleta de dados e filtragem para criar alertas para uma abordagem baseada na análise de dados; demorando sinais e criando confiança nesses dados e usando a automação para recuperar ou resolver o problema. Essa abordagem ajuda a tirar os seres humanos da equação de recuperação, o que, por sua vez, torna as operações menos dispendiosas, mais rápidas e menos sujeitas a erros. 

Fundamental para o monitoramento do Microsoft 365 é uma coleção de tecnologias que compõem nosso mecanismo de insights de dados, que foi criado no Azure, no SQL Azure e na [tecnologia de banco de dados de streaming de origem aberta](https://cassandra.apache.org/). Ele foi projetado para coletar e agregar dados e chegar às conclusões. Atualmente, ele processa mais de 500 milhões eventos por hora de mais de 100.000 servidores (aproximadamente 15 TB por dia) espalhados por dezenas de datacenters em várias regiões, e esses números estão crescendo. 

O Microsoft 365 usa *monitoramento externo*, que envolve a criação de transações sintéticas para testar tudo o que é importante. Por exemplo, no Exchange Online, cada cenário está testando cada banco de dados em todo o mundo a cada cinco minutos de forma dispersa, fornecendo cobertura quase contínua de tudo o que reside no sistema. De vários locais, 250 milhões transações de teste por dia são realizadas para criar uma linha de base ou pulsação robusta para o serviço. 

O Microsoft 365 também usa o conceito de *alerta vermelho*, que reduz todos os sinais de monitoramento de todas as máquinas em nossos datacenters para algo que é gerenciável por um ser humano. O conceito é bem simples: se algo estiver acontecendo em vários sinais, deve haver algo em andamento. Não está prestes a criar confiança em um sinal, ele está prestes a ter fidelidade razoável para cada sinal, para que você tenha maior precisão. Este sistema de monitoramento é tão poderoso que não temos a equipe 24x7 assistindo nossos monitores; Tudo o que temos é a máquina que é ativada se detectar um problema e, nesse caso, a página é a equipe de chamadas apropriada ou com mais frequência como é o caso, ela vai avançar e resolver o problema. Depois de começar a coleta de sinais e a criação de alertas vermelhos, podemos começar a triangulares em todas as partições de serviço. 

Com base na combinação do alerta de falha e dos alertas vermelhos, esse alerta indica exatamente quais componentes podem ter um problema e se o sistema tentará corrigir o problema sozinho, reiniciando um servidor de caixa de correio. 

Além de recursos de auto-recuperação, como a restauração de uma única página, o Exchange Online inclui vários recursos que usam uma abordagem para monitoramento e auto-recuperação que se concentram em preservar a experiência do usuário final. Esses recursos incluem a *disponibilidade gerenciada*, que fornece ações internas de monitoramento e recuperação, e o AutoReseed, que restaura automaticamente a redundância do banco de dados após uma falha de disco. 

## <a name="managed-availability"></a>Disponibilidade gerenciada 

A disponibilidade gerenciada oferece uma solução de recuperação e verificação de integridade nativa que monitora e protege a experiência do usuário final por meio de ações orientadas à recuperação. A disponibilidade gerenciada é a integração das ações internas de monitoramento e recuperação com a plataforma de alta disponibilidade do Exchange. O recurso foi projetado para detectar e se recuperar de problemas assim que eles ocorrem e são descobertos pelo sistema. Diferentemente das soluções e técnicas anteriores de monitoramento externo do Exchange, a disponibilidade gerenciada não tenta identificar ou comunicar a causa raiz de um problema. Em vez disso, ele está voltado para os aspectos de recuperação que lidam com três áreas principais da experiência do usuário final:

- **Disponibilidade** : os usuários podem acessar o serviço? 
- **Latência** -como é a experiência para os usuários? 
- **Erros** – os usuários podem realizar o que querem? 

A disponibilidade gerenciada é um recurso interno que é executado em todos os servidores Microsoft 365 que executam o Exchange Online. Ela examina e analisa centenas de métricas de integridade a cada segundo. Se algo for considerado errado, a maior parte do tempo é corrigida automaticamente. Mas sempre haverá problemas que a disponibilidade gerenciada não será capaz de corrigir por conta própria. Nesses casos, a disponibilidade gerenciada escalará o problema para uma equipe de suporte do Microsoft 365 por meio do log de eventos.

## <a name="autoreseed"></a>Propagação automática

Os servidores do Exchange Online são implantados em uma configuração que armazena vários bancos de dados e seus fluxos de log no mesmo disco não-RAID. Essa configuração geralmente é chamada de *apenas um monte de discos* (JBOD) porque nenhum mecanismo de redundância de armazenamento, como RAID, está sendo usado para duplicar os dados no disco. Quando um disco falha em um ambiente JBOD, os dados desse disco são perdidos. 

Dado o tamanho do Exchange Online e o fato de que implantado dentro dele são milhões de drives de disco, as falhas de unidade de disco são uma ocorrência normal no Exchange Online. Na verdade, mais de 100 falha todos os dias. Quando um disco falha em uma implantação corporativa local, um administrador deve substituir manualmente o disco com falha e restaurar os dados afetados. Em uma implantação de nuvem o tamanho do Microsoft 365, ter operadores (administradores de nuvem) a substituição manual dos discos não é prático ou economicamente viável. 

A repropagação automática, ou *AutoReseed*, é um recurso que é a substituição do que normalmente é orientada por operador em resposta a uma falha de disco, evento de corrupção de banco de dados ou outro problema que requer uma repropagação de uma cópia de banco de dados. A AutoReseed foi projetada para restaurar automaticamente a redundância de banco de dados após uma falha de disco usando discos sobressalentes provisionados no sistema. Se um disco falhar, as cópias de banco de dados armazenadas nesse disco são automaticamente propagadas para um disco de reserva pré-configurado no servidor, restaurando assim a redundância. 