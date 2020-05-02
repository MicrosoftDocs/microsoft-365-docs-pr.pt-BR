---
title: Obstáculos de segurança que você pode sailr, o ponto de vista de um arquiteto
description: Descrição.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.custom:
- M365solutions
f1.keywords: NOCSH
ms.openlocfilehash: bb9a9d046ed51690f5f7cab5b94e65c3c2e62f11
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002404"
---
# <a name="security-hurdles-you-can-sail-over--one-architects-viewpoint"></a>Obstáculos de segurança que você pode sailr, o ponto de vista de um arquiteto

Neste artigo, [Kozeta Garrett](https://www.linkedin.com/in/kozeta-garrett-53013a6/), cybersecurity arquiteto da Microsoft, descreve os principais desafios de segurança que ele encontra em organizações corporativas e recomenda abordagens para Sailing sobre esses obstáculos. 

## <a name="about-the-author"></a>Sobre o autor

![Foto Kozeta Garrett](../media/solutions-architecture-center/kozeta-garrett-security.jpg) 

Em minha função como arquiteto de segurança de nuvem, eu trabalhei com várias organizações para fornecer orientações estratégicas e técnicas com foco no design e na implementação da arquitetura de segurança para clientes que estão migrando para o Microsoft 365 e o Azure, desenvolvendo soluções de segurança corporativas e ajudando a transformar a arquitetura e a cultura de segurança para resiliência de negócios. Minha experiência inclui detecção e resposta de incidentes, análise de malware, teste de penetração e recomendações recomendadas para a segurança de ti e a postura de defesa. Sou muito apaixonado por transformações principais que resultam em segurança como um viabilizador para os negócios, incluindo esforços de modernização.

Foi mais satisfatório saber como as organizações que adotaram uma mentalidade de segurança em relação aos últimos anos estão em uma ótima posição, o que permite continuar a operar remotamente de uma maneira segura, apesar da recente situação COVID-19. Infelizmente, essas circunstâncias também foram atendidas como uma chamada de ativação para alguns clientes, que não estavam prontos para essa necessidade imediata. Muitas organizações estão percebendo que devem modernizar rapidamente, retirar a dívida de segurança de ti acumulada e aprimorar a postura de segurança durante a noite para que possam operar nesses casos extremamente incomuns.

A boa notícia é que a Microsoft selecionou alguns ótimos recursos para ajudar as organizações a aumentar a postura de segurança rapidamente. Além desses recursos, gostaria de compartilhar os principais desafios que encontrei com os clientes diariamente na esperança de que você possa Sail-los.

No momento, eu mora no norte da Virgínia, perto do nosso país de capital, Washington DC. Eu adoro quase todos os formulários de atividades e exercícios do ar-feira, como executar, biking, caminhada e nadare. Para combater isso, eu gosto tanto de culinária, gourmet comidas e viagens. 


## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>Parceria com a equipe de segurança do início da adoção da nuvem

Para começar, não posso enfatizar o suficiente para que o Microsoft Teams em sua organização possa coordenar desde o início. As equipes de segurança devem ser adotadas como parceiros críticos nos estágios iniciais da adoção e design da nuvem. Isso significa que as equipes de segurança integradas à adoção da nuvem para o campeão, não apenas para os recursos adicionados à empresa (por exemplo, uma ótima experiência do usuário de dispositivos móveis seguros, aplicativos de funcionalidade completa ou criação de valor em dados corporativos além dos aplicativos de funcionalidade limitada e email), mas também para aproveitar os recursos de análise de armazenamento, AI As equipes de segurança devem ser incluídas no gerenciamento de todos os aspectos dessa mudança, incluindo pessoas (cultura), processos (treinamento) e tecnologia para serem bem-sucedidos. Também significa investir na modernização e melhorias contínuas do SOC (Security Operations Center). Trabalhe em conjunto para alinhar sua estratégia de segurança com a estratégia de negócios e as tendências de ambiente para garantir que a transformação digital seja realizada com segurança. Quando isso é feito, as organizações desenvolvem a capacidade de adaptação mais rápida às alterações, incluindo alterações na empresa, ti e segurança. 

Onde os clientes viajam mais por obstáculos, a maioria é quando não há uma parceria real entre as operações e as equipes do SOC. Embora a equipe de operações esteja com pressão e seja obrigada a adotar a nuvem com prazos apertados, as equipes de segurança nem sempre foram incluídas no início do processo para revisar e planejar uma estratégia de segurança abrangente. Isso envolve a integração de diferentes componentes de nuvem, bem como os componentes locais. Essa falta de parcerias é mais interessante para diferentes equipes que parecem trabalhar em silos para implementar controles para seus componentes específicos, levando à complexidade adicional de implementação, solução de problemas e integração.

Os clientes que sailem essas barreiras têm boas parcerias entre as operações e a governança e as equipes de gerenciamento de riscos e segurança para Revamp a estratégia de segurança e os requisitos para proteger as cargas de trabalho de nuvem híbridas. Eles se concentram nas metas e resultados de segurança finais, proteção de dados e disponibilidade de sistemas e serviços de acordo com os requisitos de governança, risco e conformidade do cybersecurity. Essas organizações desenvolvem parcerias de estágio inicial entre suas operações e a equipe de governança e a SOC que são fundamentais para a abordagem de design de segurança e maximizarão o valor de seus investimentos. 

## <a name="build-a-modern-identity-based-security-perimeter"></a>Criar um perímetro de segurança moderno (baseado em identidade)

Em seguida, adote uma abordagem de arquitetura de confiança zero. Isso começa com a criação de um perímetro de segurança moderno e baseado em identidade. Projetar a arquitetura de segurança em que cada tentativa de acesso, seja ela local ou nuvem, seja tratada como não confiável até ser verificada: "nunca confiar, sempre verificar". Essa abordagem de design não só aumenta a segurança e a produtividade, mas também permite que os usuários trabalhem de qualquer lugar com qualquer tipo de dispositivo. Os sofisticados controles de nuvem incluídos no Microsoft 365 ajudam a proteger as identidades dos usuários enquanto controlam o acesso a recursos valiosos com base no nível de risco do usuário.

Para obter uma configuração recomendada, confira [configurações de acesso de dispositivo e identidade](../enterprise/microsoft-365-policies-configurations.md). 

## <a name="transition-security-controls-to-the-cloud"></a>Transição dos controles de segurança para a nuvem

Muitas equipes de segurança ainda estão usando as práticas recomendadas de segurança tradicionais criadas para todo o mundo local, incluindo a manutenção de uma "segurança de perímetro de rede" e a tentativa de "forçar" as ferramentas e os controles de segurança no local para as soluções de nuvem. Esses controles não foram projetados para a nuvem, são ineficazes e atrapalham a adoção de recursos de nuvem modernos. Processos e ferramentas que funcionam para uma abordagem de segurança de perímetro de rede comprovadamente são ineficientes, obstrutivos para recursos de nuvem e não permitem aproveitar os recursos de segurança modernas e automatizados.

Você pode Sail essa barreira mudando as estratégias de defesa para a proteção gerenciada em nuvem, investigação e correção automatizadas, testes automáticos de caneta, proteção avançada contra ameaças e análise de incidentes. Os clientes que usam as soluções modernas de gerenciamento de dispositivos implementaram o gerenciamento automatizado, o patching padronizado, o antivírus, a aplicação de políticas e a proteção de aplicativos em todos os dispositivos (seja um smartphone, computador pessoal, laptop ou Tablet). Isso elimina a necessidade de uma VPN, o Microsoft System Center Configuration Manager (SCCM) e as políticas de grupo do Active Directory. Isso, combinado com políticas de acesso condicional, oferece um controle e visibilidade eficientes, bem como o acesso simplificado aos recursos, independentemente de onde seus usuários estão operando.

## <a name="strive-for-best-together-security-tools"></a>Buscar as melhores ferramentas de segurança

Outro obstáculo para os quais os clientes se deparam é pegar uma abordagem de melhor opção para ferramentas de segurança. A disposição contínua de soluções de pontos melhores para atender às necessidades de segurança emergente causa a divisão da segurança da empresa. Mesmo com as melhores intenções, as ferramentas na maioria dos ambientes não são integradas porque se tornam muito caras e complexas. Isso, por sua vez, cria intervalos de visibilidade, pois há mais alertas a serem interexistentes do que a equipe pode lidar. O novo treinamento da equipe do SecOps em novas ferramentas também se torna um desafio constante.

A abordagem ' simples é melhor ' funciona também para segurança. Em vez de usar as ferramentas de melhor para a categoria, Sail sobre esse obstáculo, adotando uma estratégia de "melhor juntos" com ferramentas que funcionam juntas por padrão. Os recursos de segurança da Microsoft protegem toda a sua organização com proteção integrada contra ameaças que abrange aplicativos, usuários e nuvens. A integração permite que uma organização seja mais resistente e reduza o risco com ataques de entrada e correção rápida.

## <a name="balance-security-with-functionality"></a>Equilíbrio de segurança com funcionalidade

Como inicio de um longo plano e experiência do cybersecurity, eu gostaria de preferir começar com a configuração mais segura pronta para uso e permitir que as organizações relaxar as configurações de segurança com base em suas necessidades operacionais e de segurança. No entanto, isso pode ser um preço Hefty de funcionalidade perdida e uma experiência de usuário ruim. Como muitas organizações aprenderam, se a segurança for muito difícil para os usuários, elas encontrarão uma maneira de contornar você, incluindo o uso de serviços de nuvem não gerenciados. Tão difícil quanto aceitar, já percebi que o equilíbrio de segurança de funcionalidade do delicado deve ser alcançado.

As organizações que percebem que os usuários farão o que for necessário para que seus trabalhos sejam confirmados de que a "batalha de ti de sombra" não vale a pena combater. Eles reconhecem que os funcionários de ti são os maiores invasores quando se trata de sombrear o uso de aplicativos SaaS não aprovados para o trabalho. Eles mudaram sua estratégia para encorajar seu uso (em vez de suprimir) e se concentrar na redução da exposição de riscos que pode ser criada. As equipes de segurança da organização não insistem que tudo é bloqueado, registrado e enviado por meio de um proxy reverso ou de uma VPN. Em vez disso, essas equipes de segurança dobram seus esforços para proteger dados confidenciais e importantes de serem expostos a partes erradas ou aplicativos mal-intencionados. Eles funcionam para proteger a integridade dos dados. Eles estão realizando o uso completo de recursos de proteção de informações de nuvem mais avançados, incluindo criptografia, autenticação segura de vários fatores, risco e conformidade automatizados e recursos do Cloud app Security Broker (CASB) e, ao mesmo tempo, incentivam o compartilhamento protegido em várias plataformas. Eles estão transformando o sombreamento em uma criatividade, produtividade e colaboração inspiradoras que permitem que sua empresa permaneça na borda competitiva.


## <a name="adopt-a-methodical-approach"></a>Adotar uma abordagem de método 

A maioria dos desafios que tenho experiência com a implementação da segurança na nuvem em diferentes organizações, independentemente do setor, tem sido muito parecida. Em primeiro lugar, embora haja muita documentação sobre recursos e recursos específicos, há um nível de confusão no nível da organização sobre o que se aplica a eles, onde os recursos de segurança se sobrepõem e como os recursos devem ser integrados. Há também um nível de incerteza sobre quais recursos de segurança são pré-configurados e que requerem configuração pela organização. Além disso, as equipes do SOC infelizmente não tinham a exposição completa, o treinamento ou a alocação de orçamento necessária para se preparar para a adoção rápida na nuvem e a transformação digital suas organizações já estão em andamento.

Para ajudar você a desmarcar essas barreiras, a Microsoft acessou vários recursos projetados para ajudá-lo a adotar uma abordagem unificada para a sua estratégia e implementação de segurança. 


|Resource   |Mais informações  |
|---------|---------|
|[Principais tarefas de equipes de segurança para dar suporte ao trabalho de casa](../security/top-security-tasks-for-remote-work.md)      | Se você achar que, de repente, o suporte a uma força de trabalho em casa, este artigo ajuda você a aumentar rapidamente a segurança. Ele inclui as principais tarefas recomendadas com base no seu plano de licenciamento.    |
|[Microsoft 365 Security para os responsáveis pelas decisões de negócios](../security/Microsoft-365-security-for-bdm.md)    | Quando você tem tempo para um plano mais abrangente, este artigo inclui recomendações que abrangem o Microsoft 365, priorizado por superfície de ataque. Ele vem inclusive com uma planilha que você pode usar para classificar o licenciamento e a área (como identidade, proteção contra ameaças e monitoramento).  |
|[Recomendações de arquitetura de segurança da Microsoft](https://docs.microsoft.com/security/compass/compass)    | Se você for um arquiteto de segurança, certifique-se de ver as recomendações de segurança organizadas por disciplina, incluindo identidade, rede e operações de segurança.   |
|[Recomendações de operações de segurança da Microsoft](https://docs.microsoft.com/security/compass/security-operations-videos-and-decks)|Conheça as recomendações da Microsoft para configurar e executar um Security Operations Center (SOC) |
|[Treinamento de workshop do diretor de segurança de informações (CISO)](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop)   | Se você é novo para a segurança na nuvem, não perca esta série de vídeos.        |
|[docs.security.com/security](https://docs.microsoft.com/security/)    | Orientação técnica da Microsoft para estratégia e arquitetura de segurança.        |
| | |

Todos esses recursos foram projetados para serem usados como ponto de partida e adaptados para as necessidades da sua organização. 

