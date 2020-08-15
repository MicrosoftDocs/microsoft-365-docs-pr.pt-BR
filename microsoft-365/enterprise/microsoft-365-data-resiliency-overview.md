---
title: Resiliência de dados no Microsoft 365
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
description: Neste artigo, Aprenda sobre o design e os princípios de resiliência e recuperação de dados no Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e6ca643fe9842a71102fbabd3c05324ba52b70
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687109"
---
# <a name="data-resiliency-in-microsoft-365"></a>Resiliência de dados no Microsoft 365

Dada a natureza complexa da computação em nuvem, a Microsoft está atento a que não é um caso de coisas erradas, mas sim quando. Projetamos nossos serviços em nuvem para maximizar a confiabilidade e minimizar os efeitos negativos sobre os clientes quando as coisas entram erradas. Mudamos além da estratégia tradicional de depender de uma infraestrutura física complexa, e criamos redundância diretamente em nossos serviços de nuvem. Usamos uma combinação de infra-estrutura física menos complexa e software mais inteligente que cria resiliência de dados em nossos serviços e oferece alta disponibilidade para nossos clientes. 

## <a name="resiliency-and-recoverability-are-built-in"></a>Resiliência e capacidade de recuperação são internas 

A criação de resiliência e recuperação começa com a suposição de que a infraestrutura e os processos subjacentes falharão em algum momento: o hardware (infraestrutura) falhará, as pessoas farão erros e o software terá bugs. Embora seja incorreto dizer que os desenvolvedores de software não estavam pensando nesses itens antes da nuvem, como esses problemas foram tratados em uma implementação de ti típica era muito diferente antes da nuvem:

- Primeiro, as proteções de hardware e infraestrutura eram significativas. Isso significava que os datacenters com confiabilidade de 99,99% exigiam uma capacidade significativa de energia e de rede, e os servidores foram implementados com clustering baseado em hardware, fontes de alimentação duais, interfaces de rede duplas e semelhantes. 
- Segundo, o processo era fundamental. As equipes de operações mantiveram procedimentos rigorosos, mudanças no Windows foram empregadas e, em geral, houve uma sobrecarga significativa de gerenciamento de projetos. 
- Terceiro, a implantação foi realizada em um glacial ritmo. A implantação do código sem a posse da origem está aguardando versões de patch e versões principais de versão envolveram a substituição de hardware e a capitalização outlay significativa. Além disso, a única maneira de corrigir um problema era reverter. Portanto, a maioria das organizações de ti implantaria apenas as versões principais para evitar que o trabalho seja atualizado. 
- Por fim, a escala de sistemas implantados, bem como o nível de sua interconexão era historicamente muito menor do que agora. 

Atualmente, os clientes esperam uma inovação contínua da Microsoft sem comprometer a qualidade, e essa é uma das razões pelas quais os serviços e software da Microsoft são criados com a resiliência e a capacidade de recuperação em mente. 

## <a name="microsoft-365-data-resiliency-principles"></a>Princípios de resiliência de dados do Microsoft 365

Resiliência refere-se à capacidade de um serviço baseado em nuvem de resistir a certos tipos de falhas e ainda permanecer totalmente funcional da perspectiva dos clientes. Resiliência de dados significa que não importa quais falhas ocorram no Microsoft 365, os dados críticos do cliente permanecem intactos e não são afetados. Para esse fim, os serviços do Microsoft 365 foram projetados em torno de cinco princípios de resiliência específicos:

- Há dados críticos e não críticos. Dados não críticos (por exemplo, se uma mensagem foi lida) podem ser descartados em situações raras de falha. Dados críticos (por exemplo, dados do cliente, como mensagens de email) devem ser protegidos com custo extremo. Como meta de design, as mensagens de email entregues são sempre críticas, e as coisas como se uma mensagem foi lida não são críticas. 
- As cópias dos dados dos clientes devem ser separadas em diferentes zonas de falha ou tantos domínios de falha quanto possível (por exemplo, datacenters, acessíveis por credenciais únicas (processo, servidor ou operador)) para fornecer falha no isolamento. 
- Dados críticos do cliente devem ser monitorados com falha em qualquer parte da atomicidade, consistência, isolamento, durabilidade (ACID). 
- Os dados do cliente devem estar protegidos contra corrupção. Ele deve ser ativamente examinado ou monitorado, reparável e recuperável. 
- A maioria dos resultados de perda de dados de ações do cliente permite que os clientes se recuperem por conta própria usando uma GUI que permite restaurar itens excluídos acidentalmente. 
 
Por meio da criação de nossos serviços em nuvem para esses princípios, em conjunto com um teste e validação robustos, a Microsoft 365 é capaz de atender e exceder os requisitos dos clientes ao mesmo tempo em que garante uma plataforma para inovação contínua e melhorias. 

## <a name="related-links"></a>Links relacionados

- [Lidando com dados corrompidos](microsoft-365-dealing-with-data-corruption.md)
- [Proteção contra ransomware e malware](microsoft-365-malware-and-ransomware-protection.md)
- [Monitoramento e Autorrecuperação](microsoft-365-monitoring-and-self-healing.md)
- [Resiliência de dados do Exchange](microsoft-365-exchange-data-resiliency.md)
