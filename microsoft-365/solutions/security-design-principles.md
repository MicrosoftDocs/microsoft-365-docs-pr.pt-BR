---
title: Microsoft 365 Enterprise de recursos - arquitetura de segurança cibernética
description: Saiba como superar os desafios de segurança no Microsoft Enterprise arquitetura de Kozeta Garrett, Arquiteto de Segurança Cibernética da Microsoft.
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
- M365solutions
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: 7cd9098766024093a0b9fa2d6e95131bf13d09df
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052477"
---
# <a name="security-hurdles-you-can-sail-overone-architects-viewpoint"></a>Barreiras de segurança que você pode navegar — um ponto de vista de arquiteto

Neste artigo, [Kozeta Garrett](https://www.linkedin.com/in/kozeta-garrett-53013a6/), Arquiteto de Segurança Cibernética da Microsoft, descreve os principais desafios de segurança que encontra em organizações corporativas e recomenda abordagens para navegar sobre esses obstáculos.

## <a name="about-the-author"></a>Sobre o autor

![Foto de Kozeta Garrett](../media/solutions-architecture-center/kozeta-garrett-security.jpg)

Em minha função como Arquiteto de Segurança na Nuvem, tenho trabalhado com várias organizações para fornecer diretrizes estratégicas e técnicas com foco na criação e implementação da arquitetura de segurança para clientes que migram para o Microsoft 365 e o Azure, desenvolver soluções de segurança corporativa e ajudar a transformar a arquitetura e a cultura de segurança para a resiliência dos negócios. Minha experiência inclui detecção e resposta a incidentes, análise de malware, testes de penetração e recomendando melhorias na postura de segurança e defesa de IT. Sou muito entusiasmado com as principais transformações que resultam na segurança como um habilitador para os negócios, incluindo os esforços de modernização.

Foi muito satisfatório ver como as organizações que adotaram uma mentalidade de modernização de segurança nos últimos dois anos estão em uma ótima posição que está permitindo que elas continuem a operar remotamente de forma segura, apesar da recente situação do COVID-19. Infelizmente, essas circunstâncias também serviram como uma chamada de alerta para alguns clientes, que não estavam prontos para essa necessidade imediata. Muitas organizações estão cientes de que devem se modernizar rapidamente, retirar suas dívidas de segurança de IT acumuladas e melhorar sua postura de segurança durante a noite para que possam operar nessas circunstâncias extremamente incomuns.

A boa notícia é que a Microsoft tem alguns excelentes recursos para ajudar as organizações a aumentar rapidamente sua postura de segurança. Além desses recursos, gostaria de compartilhar os principais desafios que tenho encontrado com os clientes diariamente na esperança de que você possa navegar sobre esses obstáculos.

Atualmente, vivo na Virgínia do Norte, perto da Capital do nosso país, Washington DC. Eu amo quase todas as formas de atividades ao ar livre e exercícios, como corrida, bicicleta, caminhada e nadação. Para combater isso, eu gosto tanto de cozinhar, de comida gourmet e de viagens.

## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>Parceria com a equipe de Segurança desde o início da adoção na nuvem

Para começar, não consigo enfatizar o quanto é importante que as equipes em sua organização coordenem desde o início. As equipes de segurança devem ser adotadas como parceiros críticos nos estágios iniciais da adoção e do design na nuvem. Isso significa fazer com que as equipes de segurança ingressem para impulsionar a adoção na nuvem, não apenas para os recursos adicionados à empresa (como uma ótima experiência do usuário de dispositivos móveis seguros, aplicativos de funcionalidade completa ou criação de valor em dados corporativos além dos aplicativos de produtividade e email de funcionalidade limitada), mas também para aproveitar os recursos de armazenamento, AI e análise de computação que ajudam a resolver novos e antigos desafios de segurança. As equipes de segurança devem ser incluídas no gerenciamento de todos os aspectos dessa mudança, incluindo pessoas (cultura), processos (treinamento) e tecnologia para serem bem-sucedidos. Isso também significa investir na modernização e melhoria contínua do Centro de Operações de Segurança (SOC). Trabalhe em conjunto para alinhar sua estratégia de segurança com suas tendências de ambiente e estratégia de negócios para garantir que a transformação digital seja feita com segurança. Quando isso é bem feito, as organizações desenvolvem a capacidade de se adaptar mais rapidamente às alterações, incluindo alterações nos negócios, na IT e na segurança.

Onde eu vejo os clientes mais viajando com obstáculos é quando não há nenhuma parceria real entre as operações e as equipes do SOC. Enquanto a equipe de operações está sendo pressionada e ordenada com prazos rígidos para adotar a nuvem, as equipes de segurança nem sempre são incluídas no início do processo para revisar e planejar uma estratégia de segurança abrangente. Isso envolve a integração de componentes e componentes de nuvem diferentes no momento. Essa falta de parceria ajuda ainda mais as diferentes equipes que parecem trabalhar em silos para implementar controles para seus componentes específicos, levando à complexidade adicionada de implementação, solução de problemas e integração.

Os clientes que navegam sobre esses obstáculos têm boas parcerias entre operações e governança e as equipes de gerenciamento de Segurança e Risco para renovar a estratégia de segurança e os requisitos para proteger cargas de trabalho híbridas na nuvem. Eles se concentram nos objetivos e resultados de segurança final— proteção de dados e disponibilidade de sistemas e serviços, de acordo com os requisitos de governança, risco e conformidade de segurança cibernética. Essas organizações desenvolvem parcerias em estágio inicial entre sua equipe de Operações e Governança e SOC, o que é fundamental para a abordagem de design de segurança e maximizará o valor de seus investimentos.

## <a name="build-a-modern-identity-based-security-perimeter"></a>Criar um perímetro de segurança moderno (baseado em identidade)

Em seguida, adote uma abordagem de arquitetura de Confiança Zero. Isso começa com a criação de um perímetro de segurança moderno baseado em identidade. Projete a arquitetura de segurança em que cada tentativa de acesso, seja no local ou na nuvem, seja tratada como não confiável até que seja verificada, "nunca confie, sempre verifique". Essa abordagem de design não só aumenta a segurança e a produtividade, mas também permite que os usuários trabalhem de qualquer lugar com qualquer tipo de dispositivo. Os controles de nuvem sofisticados incluídos Microsoft 365 ajudar você a proteger as identidades dos usuários ao controlar o acesso a recursos valiosos com base no nível de risco do usuário.

Para uma configuração recomendada, consulte [Configurações de identidade e acesso a dispositivos.](../security/defender-365-security/microsoft-365-policies-configurations.md)

## <a name="transition-security-controls-to-the-cloud"></a>Controles de segurança de transição para a nuvem

Muitas equipes de segurança ainda estão usando as práticas recomendadas de segurança tradicionais criadas para um mundo inteiro local, incluindo a manutenção de uma "segurança de perímetro de rede" e a tentativa de "forçar" as ferramentas de segurança local e controles para soluções de nuvem. Esses controles não foram projetados para a nuvem, são ineficientes e impedem a adoção de recursos modernos de nuvem. Os processos e ferramentas que funcionam para uma abordagem de segurança de perímetro de rede provaram ser ineficientes, obstrutivos para recursos de nuvem e não permitem tirar proveito dos recursos de segurança modernos e automatizados.

Você pode navegar sobre esse obstáculo mudando as estratégias de defesa para proteção gerenciada na nuvem, investigação automatizada e correção, teste automático de caneta, Defender para Office 365 e análise de incidentes. Os clientes que estão usando soluções modernas de gerenciamento de dispositivo implementaram o gerenciamento automatizado, a correção padronizada, o antivírus, a aplicação de políticas e a proteção de aplicativos em todos os dispositivos (seja um smartphone, computador pessoal, laptop ou tablet). Isso elimina a necessidade de uma VPN, microsoft System Center Configuration Manager (SCCM) e políticas de grupo do Active Directory. Isso, combinado com políticas de acesso condicional, fornece controle e visibilidade eficientes, bem como acesso simplificado aos recursos, independentemente de onde seus usuários estão operando.

## <a name="strive-for-best-together-security-tools"></a>Procurar ferramentas de segurança "melhores juntos"

Outro obstáculo que vejo os clientes se depararem é ter uma abordagem "melhor de raça" para ferramentas de segurança. O uso contínuo de soluções de pontos "melhores de raça" para atender às necessidades de segurança emergentes faz com que a segurança empresarial seja desapresado. Mesmo com as melhores intenções, as ferramentas na maioria dos ambientes não são integradas porque se tornam muito caras e complexas. Isso, por sua vez, cria lacunas de visibilidade, pois há mais alertas para a triagem do que a equipe pode manipular. A retreinamento da equipe SecOps em novas ferramentas também se torna um desafio constante.

A abordagem "simples é melhor" também funciona para segurança. Em vez de ir atrás de ferramentas "melhores de raça", navegue sobre esse obstáculo adotando uma estratégia "melhor juntos" com ferramentas que funcionam em conjunto por padrão. Os recursos de segurança da Microsoft protegem toda a organização com proteção integrada contra ameaças que abrange aplicativos, usuários e nuvens. A integração permite que uma organização seja mais resiliente e reduza o risco, contendo invasores na entrada e remediando rapidamente os ataques.

## <a name="balance-security-with-functionality"></a>Balancear a segurança com a funcionalidade

À medida que eu vim de um longo plano de fundo e experiência de segurança cibernética, eu tendem a preferir começar com a configuração mais segura e permitir que as organizações descontraam as configurações de segurança com base em suas necessidades operacionais e de segurança. No entanto, isso pode vir a um preço alto da funcionalidade perdida e da experiência do usuário ruim. Como muitas organizações a apuram, se a segurança for muito difícil para os usuários, elas encontrarão uma maneira de trabalhar ao seu redor, incluindo o uso de serviços de nuvem sem gestão. Por mais difícil que seja para mim aceitar, percebi que o equilíbrio entre funcionalidade e segurança precisa ser atingido.

As organizações que percebem que os usuários fazem o que for preciso para realizar seus trabalhos reconhecem que a "batalha de TIs sombra" não vale a pena combater. Eles reconhecem que os funcionários de IT são os maiores infratores quando se trata de SHADOW IT e o uso de aplicativos SaaS não aprovados para seu trabalho. Eles mudaram sua estratégia para incentivar seu uso (em vez de suprimir) e se concentrar em reduzir os riscos de exposição que poderia criar. Essas equipes de segurança da organização não insistem que tudo seja bloqueado, registrado e enviado por meio de um proxy reverso ou uma VPN. Em vez disso, essas equipes de segurança dobram seus esforços para proteger dados valiosos e confidenciais de serem expostos a terceiros ou aplicativos mal-intencionados. Eles trabalham para proteger a integridade dos dados. Eles estão fazendo uso total de recursos mais avançados de proteção de informações na nuvem, incluindo criptografia, autenticação multifato segura, riscos e conformidade automatizados e recursos do Cloud App Security Broker (CASB) ao mesmo tempo que permitem e até incentivam o compartilhamento protegido em várias plataformas. Eles estão transformando a ÁREA DE SOMBRA em uma criatividade inspiradora, produtividade e colaboração, o que permite que seus negócios permaneçam na borda competitiva.

## <a name="adopt-a-methodical-approach"></a>Adotar uma abordagem metodista

A maioria dos desafios que tenho enfrentado com a implementação da segurança na nuvem em organizações diferentes, independentemente do setor, foram muito semelhantes. Em primeiro lugar, embora haja uma grande documentação sobre recursos e recursos específicos, há um nível de confusão no nível da organização sobre o que se aplica a eles, onde os recursos de segurança se sobrepõem e como os recursos devem ser integrados. Há também um nível de incerteza sobre quais recursos de segurança vêm pré-configurados da caixa e que exigem configuração pela organização. Além disso, as equipes soc infelizmente não tiveram a exposição completa, o treinamento ou a alocação de orçamento necessária para se preparar para a adoção rápida de nuvem e transformação digital que suas organizações já estão passando.

Para ajudá-lo a limpar esses obstáculos, a Microsoft criou vários recursos projetados para ajudá-lo a fazer uma abordagem metodista para sua estratégia e implementação de segurança.

|Recurso   |Mais informações  |
|---------|---------|
|[Principais tarefas para as equipes de segurança dar suporte ao trabalho em casa](../security/top-security-tasks-for-remote-work.md)      | Se você se encontrar de repente dando suporte a uma força de trabalho em casa, este artigo ajuda você a aumentar a segurança rapidamente. Ele inclui as principais tarefas recomendadas com base no seu plano de licenciamento.    |
|[Microsoft 365 Criadores de decisões de segurança para empresas](../security/Microsoft-365-security-for-bdm.md)    | Quando você tem tempo para um plano mais abrangente, este artigo inclui recomendações que abrangem Microsoft 365, priorizadas pela superfície de ataque. Ele ainda vem com uma planilha que você pode usar para classificar em licenciamento e área (como identidade, proteção contra ameaças e monitoramento).  |
|[Recomendações de arquitetura de segurança da Microsoft](/security/compass/compass)    | Se você for um arquiteto de segurança, certifique-se de ver as recomendações de segurança organizadas pela disciplina, incluindo as operações de identidade, rede e segurança.   |
|[Recomendações de Operações de Segurança da Microsoft](/security/compass/security-operations-videos-and-decks)|Saiba as recomendações da Microsoft para configurar e executar um SOC (Centro de Operações de Segurança) |
|[Treinamento do Diretor de Segurança da Informação (CISO)](/security/ciso-workshop/ciso-workshop)   | Se você for novo na segurança na nuvem, não perca esta série de vídeos.        |
|[docs.security.com/security](/security/)    | Diretrizes técnicas de toda a Microsoft para estratégia e arquitetura de segurança.        |
| | |

Todos esses recursos foram projetados para serem usados como ponto de partida e adaptados para as necessidades da sua organização.