---
title: Prepare seu ambiente para experiências de tópico (versão prévia)
description: Prepare seu ambiente para que você possa fornecer o máximo de conteúdo possível para seus usuários com experiências de tópico (versão prévia).
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX
ms.openlocfilehash: 19112b222be328eb75b7eea807bea94e524fd56d
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683391"
---
# <a name="get-your-environment-ready-for-topic-experiences-preview"></a>Prepare seu ambiente para experiências de tópico (versão prévia)

> [!Note]
> O conteúdo deste artigo é para a visualização privada do Project Cortex. [Mais informações sobre o Projeto Cortex](https://aka.ms/projectcortex).

Para aproveitar ao máximo a experiência de tópicos, você deseja ter tanto conteúdo possível para a descoberta de tópicos, para que você possa ter um conjunto avançado de tópicos para seus usuários. Mas qual conteúdo deve ser usado para descoberta de tópico? Como maximizar o conteúdo indexado e permanecer no controle? Quanto mais conteúdo estiver em escopo, melhor o insights que a inteligência artificial poderá gerar. Este artigo orienta você pelas etapas de planejamento para garantir que você esteja incluindo o conteúdo apropriado e que você tem as pessoas e os recursos certos para fazer uma boa experiência para os seus usuários.

Para planejar experiências de tópico (versão prévia), você precisa:

![Migrar, conectar, modernizar, proteger e identificar as etapas para integração com o gerenciamento de conhecimento](../media/knowledge-management/km-adoption-onboarding-checklist.png)

1. [Migrar conteúdo para o SharePoint](#1-migrate-content-to-microsoft-365)
    - O tópico Mining inclui conteúdo em sites do SharePoint.
      - Quando possível, migre conteúdo valioso para o SharePoint Online de fontes externas.
      - Priorize as fontes de conteúdo com alto potencial para conhecimento do Tacit.
      - Destaque os benefícios do gerenciamento de conhecimento para incentivar os usuários a mover o conteúdo do OneDrive para sites do SharePoint.

2. [Conectar informações ao Microsoft Graph](#2-connect-information-to-microsoft-graph)
    - No futuro, o conteúdo externo pode ser colocado no gráfico de conhecimento e tornar-se disponível.
    - Para o conteúdo que não pode ser movido, considere o uso de conectores do Graph para aprimorar a pesquisa e preparar para futura inclusão.

3. [Modernizar páginas do SharePoint](#3-modernize-sharepoint-pages)
    - Os cartões de tópicos só podem ser exibidos em páginas modernas.
    - Identificar páginas clássicas de alto perfil que são candidatos à modernização.

4. [Proteger o conteúdo de forma apropriada](#4-secure-content-appropriately)
    - Os recursos do tópico são excluídos de segurança com base nas permissões de um usuário.
    - Identifique qualquer conteúdo que possa ter permissões amplas ou restritivas incorretas:
      - Incentivar os proprietários do site a usar os relatórios de compartilhamento para revisar as permissões
      - Ter administradores auditar conteúdo compartilhado amplamente usando a pesquisa
      - Incentive os proprietários de conteúdo a compartilhar conteúdo que não seja confidencial e que possam ter benefícios mais abrangentes para a organização.
    - Revise a configuração do Microsoft Graph em usuários e conteúdo:
      - O tópico mineração honra a configuração excluindo conteúdo da pesquisa ou do Delve. Verifique se essas configurações ainda são relevantes.

5. [Identificar os tópicos e gerentes de conhecimento](#5-identify-knowledge-managers-and-topics)
    - Use taxonomias existentes para criar tópicos manualmente.
    - Identificar especialistas no assunto (SMEs) para tópicos provistos ou propagados.
    - Identificar os sites que abrangem um grande corpo de dados valiosos que podem ser usados para a mineração de tópico piloto.
    - Envolva gerentes de conhecimento e comunidades de prática.

## <a name="1-migrate-content-to-microsoft-365"></a>1. migrar conteúdo para o Microsoft 365

Há várias ferramentas e serviços para ajudá-lo com sua migração-você pode obter uma visão geral e informações sobre como migrar [o conteúdo para o Microsoft 365](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online). As ferramentas de migração incluem:

- [Gerenciador de Migração](https://docs.microsoft.com/sharepointmigration/mm-get-started)
- [Ferramenta de Migração do SharePoint (SPMT)](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)
- [Microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)
- [Ferramentas e serviços de migração de parceiros](https://www.microsoft.com/solution-providers)

Aproveitar ao máximo a migração:

- Migrar para um site moderno-que inclui o Microsoft Teams. Embora a indexação possa acontecer em qualquer site do SharePoint (clássico ou moderno), a exibição de tópicos para os usuários por meio de destaques e cartões ocorre apenas em páginas modernas.
- Maintain User Names – a maioria das ferramentas de migração permite mapear identidades de usuário na migração, de modo que as propriedades como criadas ou modificadas por sejam mantidas após a migração. Isso é importante para tópicos porque a criação de arquivos é usada para identificar os especialistas que são adicionados a uma página de tópico ou cartão. 
- Tornar os nomes das contas de serviço descritivos-haverá alguns casos em que a manutenção de nomes de Usernão é possível. Por exemplo, se você estiver migrando conteúdo que foi criado por alguém que não é mais um funcionário da organização. Nessa instância, a maioria das ferramentas de migração moverá um arquivo como se ele tiver sido criado por uma conta de administrador ou uma conta de serviço. Se isso acontecer com frequência, essa conta de serviço poderá então ser listada em relação aos tópicos como um especialista. É aí que o nome da conta se torna realmente importante. Se você o tornar descritivo, a presença dessas contas não-humanas será compreensível pelos usuários que consumam os tópicos.

## <a name="2-connect-information-to-microsoft-graph"></a>2. Conecte as informações ao Microsoft Graph

Se você não puder migrar alguns conteúdos, conecte-o ao Microsoft Graph:

- Considere implementar os [conectores de conteúdo do Graph](https://docs.microsoft.com/microsoftsearch/connectors-overview). Usando conectores, o conteúdo externo pode ser indexado no Microsoft Graph, onde os usuários podem descobri-lo por meio da pesquisa da Microsoft.
- Os desenvolvimentos futuros trará dados externos para experiências de tópico.

## <a name="3-modernize-sharepoint-pages"></a>3. modernizar páginas do SharePoint

Como os cartões de tópicos e os realces só podem aparecer em páginas modernas, atualize as páginas que você deseja incluir no tópico experiências de clássico para o moderno. Confira [modernizar seus sites clássicos do SharePoint](https://docs.microsoft.com/sharepoint/dev/transform/modernize-classic-sites). Você pode usar o [Verificador de modernização do SharePoint](https://docs.microsoft.com/sharepoint/dev/transform/modernize-scanner) para preparar seus sites clássicos para modernização.

Se você tiver muitos sites clássicos, Priorize as páginas de perfil alto para serem convertidas para modernas.

## <a name="4-secure-content-appropriately"></a>4. proteger o conteúdo de forma apropriada

Quando os usuários interagem com um cartão de tópico ou uma página de tópico, eles podem ver recursos diferentes. Isso ocorre porque eles têm acesso a arquivos diferentes associados ao tópico. Se suas permissões subjacentes forem muito estritas, os aspectos serendipitous da descoberta de informações por meio de tópicos podem ser reduzidos. Por outro lado, se eles forem muito amplos, um tópico poderá trazer o conteúdo para um usuário que você não pretenda ver.
O gerenciamento de permissões recomendadas é essencial aqui. E o bom gerenciamento de permissões é baseado em uma parceria contínua entre administradores e proprietários de conteúdo. Embora isso possa ser uma atividade contínua, há algumas etapas práticas que podem ser tomadas ao preparar tópicos:

- Incentive os proprietários de sites a revisar o compartilhamento e as permissões.

  Os proprietários de site do SharePoint podem analisar um relatório de compartilhamento para o site que mostra detalhes completos de todas as permissões e links de compartilhamento configurados no site, consulte [Sharing Reports](https://docs.microsoft.com/sharepoint/sharing-reports). Isso lista usuários internos e externos (convidados).

  Os proprietários do site também podem ver quem tem permissões para o site, acessando as páginas **permissões do site** e **configurações de permissões avançadas** .

  1. Em seu site, escolha **configurações** de  >  **permissões do site**. Verifique quem está listado em proprietários do site, membros do site e visitantes do site. Verifique se há usuários convidados.
  2. Na página **permissões** , escolha **configurações de permissões avançadas**. Você pode verificar se há permissões exclusivas e ver quem tem acesso limitado a qualquer item no site.

- Faça auditoria em grupos e equipes do Microsoft 365 para garantir que eles sejam definidos apropriadamente como grupos públicos ou privados ou equipes. As novas equipes e os grupos da Microsoft 365 são definidos como privados por padrão, mas quando lançadas pela primeira vez foram públicas por padrão. Se você tiver adotado mais cedo essas tecnologias, talvez queira analisar. Além disso, a função de uma equipe geralmente evolui ao longo do ciclo de vida, e a configuração pode precisar ser atualizada para refletir o uso atual da equipe.
- Revise o uso de "todos", "todos exceto usuários externos" ou grupos de segurança amplos. O conteúdo pode ser compartilhado incorretamente com estes valores. Para revisar o uso desses grupos, você pode:
  - Criar uma conta que não tenha associações de grupo
  - Use a pesquisa com esta conta para descobrir o conteúdo que é compartilhado amplamente.
  - Se o conteúdo inadequado estiver visível para esta conta por meio da pesquisa, você poderá trabalhar com os proprietários do site para corrigir a configuração de permissão.

Além das permissões, você também pode controlar o escopo do que é detectável por meio de tópicos. Você está sempre no controle do que está indexado.

Os administradores podem configurar a indexação no centro de administração do Microsoft 365. Ao configurar o [Gerenciamento de conhecimento](set-up-topic-experiences.md), você pode:

- Permitir descoberta em todos os sites do SharePoint ou especificar sites para incluir ou excluir como fontes de tópico.
- Onde você tem termos confidenciais, você também pode excluir tópicos por nome. Por exemplo, se você tiver o nome de um projeto confidencial, onde não deseja que um realce ou cartão seja exibido, independentemente das permissões do usuário, você pode excluir o nome do projeto.

No nível do conteúdo, você também pode controlar o que é detectável. Qualquer configuração que você tenha feito para excluir conteúdo da pesquisa também será usada pela descoberta de conteúdo. Por exemplo, se você excluiu uma biblioteca de documentos específica da exibição dos resultados da pesquisa, esta biblioteca de documentos não será usada para descoberta de tópicos.

## <a name="5-identify-knowledge-managers-and-topics"></a>5. identificar tópicos e gerentes de conhecimento

O gerenciamento de tópicos envolve três funções principais, incluindo duas novas funções do Azure Active Directory (AAD): administrador de conhecimento e gerente de conhecimento:

- O administrador de conhecimento (KA) é uma função técnica, geralmente ela. Essa função permite que a configuração do tópico apresente o centro de administração do M365, bem como a configuração da descoberta e da visibilidade do tópico.
- O gerente de conhecimento (KM) funciona com os tópicos e supervisiona sua qualidade e integridade.
- Os colaboradores de tópico (TCs) não são baseados em uma função AAD, mas permissões no centro de administração. Eles são especialistas no assunto que podem auxiliar o conteúdo em tópicos, adicionando recursos e pessoas.

Dependendo da sua organização, você pode ter poucas ou várias pessoas agindo nessas funções. Para algumas organizações, elas podem ser as mesmas pessoas.

| Administrador de conhecimento | Gerente de conhecimento | Tópico colaborador |
|:-------|:-------|:-------|:-------|
| Função AAD | Função AAD | EA |
| Tem acesso ao centro de administração | Tem acesso ao centro de administração | Sem acesso ao centro de administração |
| Configura experiências de tópico | Possui gerenciamento e qualidade de tópicos | Contribui para tópicos com base em sua especialização. |
| Garante que os padrões de segurança e conformidade sejam impostos e entenda o contrato de licenciamento.| Realiza tarefas de gerenciamento de tópicos, como criar, editar, excluir e rejeitar tópicos. Suporta colaboradores de tópico com suas tarefas. | Lista as informações e o conteúdo em páginas de tópicos, incluindo quais pessoas e recursos estão fixos no tópico. |

Os destaques e cartões serão exibidos para os usuários no contexto de seu trabalho, por exemplo, à medida que navegam por páginas modernas no SharePoint. Você controla a experiência do usuário final para tópicos.

- Quem pode ver os tópicos? A visibilidade do tópico é configurada no centro de administração do Microsoft 365. Escolha quais grupos permitir para ver tópicos:
  - Todos em minha organização. "Todos" não inclui convidados, todos os usuários internos do seu diretório
  - Apenas pessoas ou grupos de segurança selecionados (essa opção é boa enquanto você ainda está distribuindo experiências de tópico, para que você possa testar com um subconjunto de usuários). Se você quiser que os convidados exibam tópicos, será necessário usar a opção "pessoas ou grupos de segurança selecionados" e conceder a eles uma licença.
  - Ninguém.

    Todos os usuários, até mesmo os usuários convidados, precisarão ter uma licença aplicada para exibir a experiência do tópico. E lembre-se de que as permissões sempre controlam o que pode ser visto.

- Quais tópicos estão visíveis? Você pode optar por:
  - Mostrar todos os tópicos candidatos.
  - Mostrar apenas os tópicos confirmados.

Agora que temos os gerentes, especialistas e usuários, podemos falar sobre os tópicos propriamente ditos.

- É uma boa prática para propagar tópicos em sua lista de tópicos. A qualidade e a quantidade de tópicos baseiam-se no conteúdo-ele só será criado como um tópico se estiver incluído no conteúdo que está no escopo. Se houver informações e evidências suficientes para o tópico, elas serão criadas pelo AI. Tópicos de propagação é onde o gerente de conhecimento e especialistas no assunto podem ajudar. Combinar o conhecimento humano com o AI é a melhor rota para os tópicos de qualidade. Portanto, se houver tópicos que você pode criar manualmente no centro de tópicos. Fazer isso dará ao AI um sinal forte da relevância desse tópico e identificará os recursos e as pessoas que serão associados a esse tópico.
- Use taxonomias existentes para ajudar o planejamento de seus tópicos do SharePoint ou em qualquer outro lugar. As taxonomias existentes geralmente incluem termos organizacionais, produtos, áreas de assunto e assim por diante. Fontes de tópicos também podem vir de listas de projetos, indicadores de pesquisa existentes e assim por diante.
