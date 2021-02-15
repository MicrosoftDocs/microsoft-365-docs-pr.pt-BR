---
title: Planejamento de recursos do Microsoft 365 Enterprise - Arquitetura de segurança cibernética
description: Saiba como superar os desafios de segurança na arquitetura do Microsoft Enterprise da SecurityEta Medidas, arquiteto de segurança cibernética da Microsoft.
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
ms.openlocfilehash: 7b84094fecc1ddbd58bcdfca808df6585958a6dc
ms.sourcegitcommit: ddfb4f3e34deb733e8625e845e4dfd1fcc066ceb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49771926"
---
# <a name="security-hurdles-you-can-sail-overone-architects-viewpoint"></a>Barreiras de segurança que você pode navegar — Um arquiteto

Neste artigo, [Securityeta Ltd](https://www.linkedin.com/in/kozeta-garrett-53013a6/), Cybersecurity Architect da Microsoft, descreve os principais desafios de segurança que encontra em organizações empresariais e recomenda abordagens para se aproximar desses obstáculos.

## <a name="about-the-author"></a>Sobre o autor

![Foto de Rúsca (Brasil)](../media/solutions-architecture-center/kozeta-garrett-security.jpg)

Na minha função de arquiteto de segurança na nuvem, eu tenho trabalhado com várias organizações para fornecer orientação estratégica e técnica focada no design e na implementação da arquitetura de segurança para clientes que migram para o Microsoft 365 e Ozure, desenvolvendo soluções de segurança corporativa e ajudando a transformar a arquitetura de segurança e a cultura para resiliência de negócios. Minha experiência inclui detecção e resposta a incidentes, análise de malware, teste de penetração e recomendação de melhorias na postura de segurança e defesa de IT. Sou muito entusiasmado com as principais transformações que resultam na segurança como um ativador para os negócios, incluindo esforços de modernização.

Foi mais satisfatório ver como as organizações que adotaram uma mentalidade de modernização de segurança nos últimos dois anos estão em uma ótima posição que está permitindo que elas continuem a operar remotamente de maneira segura, apesar da recente situação do COVID-19. Infelizmente, essas circunstâncias também serviram como uma chamada de adoção para alguns clientes, que não estavam prontos para essa necessidade imediata. Muitas organizações estão cientes de que devem modernizar rapidamente, retirar seu débito acumulado de segurança de IT e melhorar a postura de segurança durante a noite para que possam operar nessas circunstâncias extremamente incomuns.

A boa notícia é que a Microsoft redorou alguns excelentes recursos para ajudar as organizações a aumentarem rapidamente a postura de segurança. Além desses recursos, gostaria de compartilhar os principais desafios que eu tenho com os clientes diariamente, na expectativa de que você possa navegar sobre esses obstáculos.

Atualmente, eu vivo na Costa norte do Norte, perto da capital do nosso país, Washington DC. Eu quero quase todas as formas de atividades do ar livre e exercício, como executar, fazer biking, relembir e reatar. Para combater esses casos, eu faço o máximo de café, café e viagem.

## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>Parceria com a equipe de Segurança desde o início da adoção da nuvem

Para começar, não consigo enfatizar o quanto é importante que as equipes da sua organização coordenem desde o início. As equipes de segurança devem ser adotadas como parceiros essenciais nos estágios iniciais de adoção e design na nuvem. Isso significa fazer as equipes de segurança se integram à adoção de nuvem de defensores, não apenas para os recursos adicionados aos negócios (como uma excelente experiência de usuário de dispositivos móveis seguros, aplicativos de funcionalidade total ou criação de valor em dados corporativos além dos aplicativos de produtividade e email de funcionalidade limitada), mas também para aproveitar os recursos de armazenamento, inteligência artificial e análise de computação que ajudam a resolver desafios de segurança novos e antigos. As equipes de segurança devem ser incluídas no gerenciamento de todos os aspectos dessa mudança, incluindo pessoas (cultura), processos (treinamento) e tecnologia para serem bem-sucedidos. Isso também significa investir na modernização e na melhoria contínua do Centro de Operações de Segurança (SOC). Trabalhe em conjunto para alinhar sua estratégia de segurança com suas tendências de ambiente e estratégia de negócios para garantir que a transformação digital seja feita com segurança. Quando isso é feito bem, as organizações desenvolvem a capacidade de se adaptar com mais rapidez às alterações, incluindo alterações nos negócios, na IT e na segurança.

Onde vejo os clientes se desempejem mais, é quando não há parceria real entre as operações e as equipes do SOC. Enquanto a equipe de operações está sendo pressionada e ordenada com prazos rígidos para adotar a nuvem, as equipes de segurança nem sempre são incluídas no início do processo para revisar e planejar uma estratégia de segurança abrangente. Isso envolve a integração de diferentes componentes e componentes de nuvem locais. Essa falta de parceria ajuda ainda mais as diferentes equipes que parecem funcionar em silos para implementar controles para seus componentes específicos, levando à maior complexidade de implementação, solução de problemas e integração.

Os clientes que se arriscam por essas barreiras têm boas parcerias entre as equipes de Operações e Governança e segurança e gerenciamento de risco para reformular a estratégia de segurança e os requisitos para proteger cargas de trabalho de nuvem híbridas. Eles se concentram nas metas e resultados de segurança mais recentes— proteção de dados e disponibilidade de sistemas e serviços de acordo com os requisitos de conformidade, risco e governança de segurança cibernética. Essas organizações desenvolvem parcerias de estágio inicial entre sua equipe de Operações e Governança e SOC, que é fundamental para a abordagem de design de segurança e maximizará o valor de seus investimentos.

## <a name="build-a-modern-identity-based-security-perimeter"></a>Criar um perímetro de segurança moderno (baseado em identidade)

Em seguida, adote uma abordagem de arquitetura de Confiança Zero. Isso começa com a criação de um perímetro de segurança moderno baseado em identidade. Projete a arquitetura de segurança em que todas as tentativas de acesso, seja no local ou na nuvem, sejam tratadas como não confiável até que sejam verificadas: "nunca confie, sempre verifique". Essa abordagem de design não só aumenta a segurança e a produtividade, mas também permite que os usuários trabalhem de qualquer lugar com qualquer tipo de dispositivo. Os controles de nuvem sofisticados incluídos no Microsoft 365 ajudam a proteger as identidades dos usuários enquanto controlam o acesso a recursos valiosos com base no nível de risco do usuário.

Para uma configuração recomendada, consulte Configurações de acesso a identidades [e dispositivos.](../security/office-365-security/microsoft-365-policies-configurations.md)

## <a name="transition-security-controls-to-the-cloud"></a>Fazer a transição de controles de segurança para a nuvem

Muitas equipes de segurança ainda estão usando as práticas recomendadas de segurança tradicionais criadas para todo o mundo local, incluindo a manutenção de uma "segurança de perímetro de rede" e a tentativa de "forçar" as ferramentas de segurança local e os controles para soluções de nuvem. Esses controles não foram projetados para a nuvem, são ineficientes e prejudicam a adoção de recursos modernos de nuvem. Os processos e ferramentas que funcionam para uma abordagem de segurança de perímetro de rede provaram ser ineficientes, obstrutivos em recursos de nuvem e não permitem tirar proveito dos recursos de segurança modernos e automatizados.

Você pode se sobressalçar ao deslocar as estratégias de defesa para a proteção gerenciada na nuvem, investigação e correção automatizadas, teste de caneta automatizado, Defender para Office 365 e análise de incidentes. Os clientes que estão usando soluções modernas de gerenciamento de dispositivo implementaram gerenciamento automatizado, correção padronizada, antivírus, imposição de política e proteção de aplicativos em todos os dispositivos (seja um smartphone, computador pessoal, laptop ou tablet). Isso elimina a necessidade de uma VPN, do Microsoft System Center Configuration Manager (SCCM) e de políticas de grupo do Active Directory. Isso, combinado com políticas de acesso condicional, fornece controle e visibilidade poderosos, bem como acesso simplificado aos recursos, independentemente de onde seus usuários estão operando.

## <a name="strive-for-best-together-security-tools"></a>Procurar as ferramentas de segurança "melhor juntos"

Outro obstáculo que vejo os clientes se aproximarem é ter uma abordagem "melhor do que pode ser" para as ferramentas de segurança. A camada contínua de soluções de ponto "da melhor maneira" para atender às necessidades de segurança emergentes faz com que a segurança empresarial seja inovada. Mesmo com as melhores intenções, as ferramentas na maioria dos ambientes não são integradas porque se tornam muito caras e complexas. Isso, por sua vez, cria lacunas de visibilidade, pois há mais alertas para triagem do que a equipe pode manipular. Retraining the SecOps team on new tools also becomes a constant challenge.

A abordagem "simples é melhor" também funciona para segurança. Em vez de ir atrás das ferramentas "da melhor forma", navegue sobre esse obstáculo adotando uma estratégia "melhor em conjunto" com ferramentas que funcionam juntas por padrão. Os recursos de segurança da Microsoft protegem toda a organização com proteção integrada contra ameaças que abrange aplicativos, usuários e nuvens. A integração permite que uma organização seja mais resiliente e reduza o risco, contendo invasores na entrada e remediando rapidamente os ataques.

## <a name="balance-security-with-functionality"></a>Equilibrar segurança com funcionalidade

À medida que começo de uma experiência e experiência de segurança cibernética longas, começo a preferir começar com a configuração mais segura e permitir que as organizações controlem as configurações de segurança com base em suas necessidades operacionais e de segurança. No entanto, isso pode ter um preço alto de perda de funcionalidade e experiência do usuário ruim. Como muitas organizações a aprenderam, se a segurança for muito difícil para os usuários, eles encontrarão uma maneira de trabalhar com você, incluindo o uso de serviços de nuvem nãomanagedos. Por mais difícil que eu aceite, eu percebi que o equilíbrio funcionalidade e segurança deve ser alcançado.

As organizações que percebem que os usuários fazem o que for necessário para realizar seus trabalhos reconhecem que não vale a pena combater o "Shadow IT". Eles reconhecem que os funcionários de IT são os maiores problemas quando se trata de SOMBRA IT e o uso de aplicativos SaaS não aprovados para seu trabalho. Eles mudaram sua estratégia para incentivar seu uso (em vez de suprimir) e se concentrar na redução dos riscos que ela poderia criar. Essas equipes de segurança da organização não resistem que tudo seja bloqueado, registrado e enviado por meio de um proxy reverso ou uma VPN. Em vez disso, essas equipes de segurança rebaixam seus esforços para proteger dados valiosos e confidenciais de serem expostos a terceiros ou aplicativos mal-intencionados. Eles trabalham para proteger a integridade dos dados. Eles estão fazendo uso total dos recursos de proteção de informações de nuvem mais avançados, incluindo criptografia, autenticação multifatória segura, risco automatizado e conformidade e recursos casB (Agente de Segurança de Aplicativo na Nuvem), permitindo e até incentivando o compartilhamento protegido em várias plataformas. Eles estão transformando a SOMBRA DA EQUIPE em criatividade, produtividade e colaboração, o que permite que seus negócios permaneçam na borda competitiva.

## <a name="adopt-a-methodical-approach"></a>Adotar uma abordagem metométrica

A maioria dos desafios que eu tenho enfrentado com a implementação da segurança na nuvem em diferentes organizações, independentemente do setor, foram muito semelhantes. Primeiro, embora haja uma grande documentação sobre recursos e recursos específicos, há um nível de confusão no nível da organização sobre o que se aplica a eles, em que os recursos de segurança se sobrepõem e como os recursos devem ser integrados. Também há um nível de dúvida sobre quais recursos de segurança vêm pré-configurados e que exigem configuração pela organização. Além disso, infelizmente as equipes do SOC não tiveram a exposição completa, o treinamento ou a alocação de orçamento necessária para se preparar para a rápida adoção da nuvem e a transformação digital que suas organizações já estão passando.

Para ajudá-lo a limpar esses obstáculos, a Microsoft criou vários recursos projetados para ajudá-lo a tomar uma abordagem metométrica para sua estratégia e implementação de segurança.

|Recurso   |Mais informações  |
|---------|---------|
|[Principais tarefas para as equipes de segurança dar suporte ao trabalho em casa](../security/top-security-tasks-for-remote-work.md)      | Se você se desempaldamente suportar uma força de trabalho em casa principalmente, este artigo ajuda a aumentar a segurança rapidamente. Ele inclui as principais tarefas recomendadas com base no seu plano de licenciamento.    |
|[Tomadores de decisões de segurança para negócios do Microsoft 365](../security/Microsoft-365-security-for-bdm.md)    | Quando você tiver tempo para um plano mais abrangente, este artigo inclui recomendações que abrangem o Microsoft 365, priorizadas por superfície de ataque. Ele também vem com uma planilha que você pode usar para classificar o licenciamento e a área (como identidade, proteção contra ameaças e monitoramento).  |
|[Recomendações de arquitetura de segurança da Microsoft](https://docs.microsoft.com/security/compass/compass)    | Se você for um arquiteto de segurança, certifique-se de ver as recomendações de segurança organizadas por disciplina, incluindo operações de identidade, rede e segurança.   |
|[Recomendações de operações de segurança da Microsoft](https://docs.microsoft.com/security/compass/security-operations-videos-and-decks)|Conheça as recomendações da Microsoft para configurar e executar um SOC (Centro de Operações de Segurança) |
|[Treinamento do diretor de segurança da informação (CISO)](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop)   | Se você for novo na segurança na nuvem, não perca esta série de vídeos.        |
|[docs.security.com/security](https://docs.microsoft.com/security/)    | Diretrizes técnicas da Microsoft para estratégia e arquitetura de segurança.        |
| | |

Todos esses recursos foram projetados para serem usados como ponto de partida e adaptados para as necessidades da sua organização.
