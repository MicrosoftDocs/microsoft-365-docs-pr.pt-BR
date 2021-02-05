---
title: Prepare seu ambiente para os tópicos do Microsoft Viva
description: Prepare seu ambiente para que você possa fornecer o máximo de conteúdo possível para seus usuários com tópicos do Microsoft Viva.
ms.author: samanro
author: samanro
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 5a13af3e78848471b436d44ab051eca945176c74
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107691"
---
# <a name="get-your-environment-ready-for-microsoft-viva-topics"></a>Prepare seu ambiente para os tópicos do Microsoft Viva

Para usar ao máximo os tópicos do Viva, você deseja ter o máximo de conteúdo possível incluído para a descoberta de tópicos, para que possa ter um conjunto rico de tópicos para seus usuários. Mas qual conteúdo deve ser usado para descoberta de tópicos? Como maximizar o conteúdo indexado enquanto permanece no controle? Quanto mais conteúdo está no escopo, melhor as informações que a inteligência artificial pode descobrir. Este artigo orienta você pelas etapas de planejamento para garantir que você está incluindo o conteúdo apropriado e que você tenha as pessoas e recursos certos para fazer uma boa experiência para seus usuários.

Para planejar os Tópicos do Viva, você precisa:

![Migrar, conectar, modernizar, proteger e identificar etapas para integração ao gerenciamento de conhecimento](../media/knowledge-management/km-adoption-onboarding-checklist.png)

1. [Migrar conteúdo para o SharePoint](#1-migrate-content-to-microsoft-365)
    - A indexação de tópicos inclui apenas conteúdo em sites do SharePoint.
      - Sempre que possível, migre conteúdo valioso para o SharePoint Online de fontes externas.
      - Priorizar fontes de conteúdo com alto potencial para conhecer melhor o conteúdo.
      - Realça os benefícios do gerenciamento de conhecimento para incentivar os usuários a mover conteúdo do OneDrive para sites do SharePoint.

2. [Conectar informações ao Microsoft Graph](#2-connect-information-to-microsoft-graph)
    - No futuro, o conteúdo externo pode ser trazido para o gráfico de conhecimento e ficar disponível.
    - Para o conteúdo que não pode ser movido, considere usar os Conectores do Graph para aprimorar a pesquisa e preparar a inclusão futura.

3. [Modernizar páginas do SharePoint](#3-modernize-sharepoint-pages)
    - Os cartões de tópico só podem ser divulgados em páginas modernas.
    - Identifique páginas clássicas de alto perfil que são candidatas à modernização.

4. [Proteger o conteúdo adequadamente](#4-secure-content-appropriately)
    - Os recursos de tópicos são cortados com base nas permissões de um usuário.
    - Identifique qualquer conteúdo que possa ter permissões incorretamente amplas ou restritivas:
      - Incentivar os proprietários do site a usar os relatórios de compartilhamento para revisar as permissões
      - Fazer com que os administradores auditem conteúdo amplamente compartilhado usando a Pesquisa
      - Incentive os proprietários de conteúdo a compartilhar conteúdo que não seja sensível e que possa ter benefícios mais amplos para a organização.
    - Revise a configuração do Microsoft Graph em usuários e conteúdo:
      - A indexação de tópicos reconhece a configuração excluindo o conteúdo da Pesquisa ou do Delve (por exemplo, NOINDEX). Revise se essas configurações ainda são relevantes.

5. [Identificar gerentes de conhecimento e tópicos](#5-identify-knowledge-managers-and-topics)
    - Use taxonomias existentes para criar tópicos manualmente ou ajudar a confirmar tópicos sugeridos por IA.
    - Identifique especialistas no assunto (SMEs) para tópicos previstos ou semedados.
    - Identifique sites que abrangem um grande corpo de dados valiosos que podem ser usados para a mineração de tópicos piloto.
    - Envolva gerentes de conhecimento e comunidades de práticas.

## <a name="1-migrate-content-to-microsoft-365"></a>1. Migrar conteúdo para o Microsoft 365

Há várias ferramentas e serviços para ajudar na migração: você pode obter uma visão geral e informações sobre como migrar em Migrar seu conteúdo para o [Microsoft 365.](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) As ferramentas de migração incluem:

- [Gerenciador de Migração](https://docs.microsoft.com/sharepointmigration/mm-get-started)
- [Ferramenta de Migração do SharePoint (SPMT)](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)
- [Microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)
- [Serviços e ferramentas de migração de parceiros](https://www.microsoft.com/solution-providers)

Faça o máximo da sua migração:

- Migre para um site moderno, que inclui o Microsoft Teams. Embora a indexação possa acontecer em qualquer site do SharePoint (clássico ou moderno), exibir tópicos para os usuários por meio de destaques e cartões só acontece em páginas modernas.
- Manter nomes de usuário - a maioria das ferramentas de migração permite que você mapeie as identidades dos usuários durante a migração, para que as propriedades como Criado por ou Modificado por sejam mantidas após a migração. Isso é importante para os tópicos porque a autoria dos arquivos é usada para identificar os especialistas que são adicionados a uma página de tópico ou cartão. 
- Tornar os nomes de contas de serviço descritivos – haverá alguns casos em que não é possível manter nomes de usuário. Por exemplo, se você estiver migrando o conteúdo que foi criado por alguém que não é mais um funcionário da organização. Nesse caso, a maioria das ferramentas de migração move um arquivo como se tivesse sido criado por uma conta de administrador ou uma conta de serviço. Se isso acontecer com frequência, essa conta de serviço poderá ser listada em relação aos tópicos como um especialista. É aqui que a nomeação dessa conta se torna muito importante. Se você fizer isso descritivo, a presença dessas contas não humanas será compreensível pelos tópicos de consumo de usuários.

## <a name="2-connect-information-to-microsoft-graph"></a>2. Conectar informações ao Microsoft Graph

Se não for possível migrar algum conteúdo, conecte-o ao Microsoft Graph:

- Considere implementar [conectores de conteúdo do Graph.](https://docs.microsoft.com/microsoftsearch/connectors-overview) Usando conectores, o conteúdo externo pode ser indexado no Microsoft Graph, onde os usuários podem descobrir isso por meio da Pesquisa da Microsoft.
- Desenvolvimentos futuros trazerão dados externos para tópicos do Viva.

## <a name="3-modernize-sharepoint-pages"></a>3. Modernizar páginas do SharePoint

Como os cartões de tópico e os destaques só podem aparecer em páginas modernas, atualize todas as páginas que você deseja incluir nos Tópicos do Viva do clássico para o moderno. Confira [Modernizar seus sites clássicos do SharePoint.](https://docs.microsoft.com/sharepoint/dev/transform/modernize-classic-sites) Você pode usar o [scanner de modernização do SharePoint](https://docs.microsoft.com/sharepoint/dev/transform/modernize-scanner) para preparar seus sites clássicos para modernização.

Se você tiver muitos sites clássicos, priorize as páginas de alto perfil para converter em modernas.

## <a name="4-secure-content-appropriately"></a>4. Proteger o conteúdo adequadamente

Quando os usuários interagem com um cartão de tópico ou uma página de tópico, eles podem ver recursos diferentes. Isso porque eles têm acesso a arquivos diferentes associados ao tópico. Se suas permissões subjacentes são muito estritas, os aspectos serendipitous da descoberta de informações por meio de tópicos podem ser reduzidos. Por outro lado, se eles são muito amplos, um tópico pode apresentar conteúdo para um usuário que você não pretende que ele veja.
O gerenciamento de permissões é fundamental aqui. E o bom gerenciamento de permissões baseia-se em uma parceria contínua entre administradores e proprietários de conteúdo. Embora isso possa ser uma atividade contínua, há algumas etapas práticas que você pode seguir ao se preparar para os tópicos:

- Incentive os proprietários do site a revisar o compartilhamento e as permissões.

  Os proprietários de site do SharePoint podem revisar um relatório de compartilhamento para seu site que mostra detalhes completos de todas as permissões e links de compartilhamento configurados no site, consulte [Compartilhamento de relatórios.](https://docs.microsoft.com/sharepoint/sharing-reports) Isso lista usuários internos e externos (convidados).

  Os **proprietários** do site também podem ver quem tem permissões para o site indo para as páginas Permissões do Site e Configurações **de Permissões Avançadas.**

  1. Em seu site, escolha **as permissões do** Site de  >  **Configurações.** Verifique quem está listado em Proprietários de Site, Membros do Site e Visitantes do Site. Verifique se há usuários convidados.
  2. Na página **Permissões,** escolha **Configurações de Permissões Avançadas.** Você pode verificar se há permissões exclusivas e ver quem tem acesso limitado a todos os itens no site.

- Audite os Grupos do Microsoft 365 e o Teams para garantir que eles sejam definidos adequadamente como grupos ou equipes públicas ou privadas. Os novos Grupos do Microsoft 365 e do Teams são definidos como privados por padrão, mas quando lançados pela primeira vez foram públicos por padrão. Se você era usuários anteriores dessas tecnologias, talvez queira revisar. Além disso, a função de uma equipe frequentemente evolui durante seu ciclo de vida, e a configuração pode precisar ser atualizada para refletir o uso atual da equipe.
- Revise o uso de "todos", "todos exceto usuários externos" ou grupos de segurança amplos. O conteúdo pode ser compartilhado incorretamente com esses valores. Para revisar o uso desses grupos, você pode:
  - Criar uma conta que não tenha associações de grupo
  - Use a pesquisa com essa conta para descobrir o conteúdo amplamente compartilhado.
  - Se o conteúdo inadequado estiver visível para essa conta por meio de pesquisa, você poderá trabalhar com os proprietários do site para corrigir a configuração de permissão.

Além das permissões, você também pode controlar o escopo do que pode ser descoberto por meio de tópicos. Você está sempre no controle do que é indexado.

Os administradores podem configurar a indexação no Centro de Administração do Microsoft 365. Ao configurar o Gerenciamento [de Conhecimento,](set-up-topic-experiences.md)você pode:

- Permitir a descoberta em todos os sites do SharePoint ou especificar sites para incluir ou excluir como fontes de tópico.
- Onde você tiver termos confidenciais, também poderá excluir tópicos por nome. Por exemplo, se você tiver o nome de um projeto sensível, onde não quiser que um destaque ou cartão apareça, independentemente das permissões do usuário, você poderá excluir esse nome de projeto.

No nível do conteúdo, você também pode controlar o que pode ser descoberto. Qualquer configuração que você tenha feito para excluir o conteúdo da pesquisa também será usada pela descoberta de conteúdo. Portanto, por exemplo, se você excluiu uma biblioteca de documentos específica de aparecer nos resultados da pesquisa, essa biblioteca de documentos não será usada para descoberta de tópicos.

## <a name="5-identify-knowledge-managers-and-topics"></a>5. Identifique gerentes de conhecimento e tópicos

O gerenciamento de tópicos envolve três funções importantes, incluindo duas novas funções do Azure Active Directory (AAD), administrador de conhecimento e Gerente de Conhecimento:

- O KA (Administrador de Conhecimento) é uma função técnica, normalmente em TI. Essa função permite a configuração dos Tópicos do Viva no centro de administração do M365, bem como a configuração de descoberta e visibilidade de tópicos.
- O gerente de Conhecimento (KM) trabalha com os próprios tópicos e supervisiona sua qualidade e sua totalidade.
- Os colaboradores de tópicos (TCs) não se baseiam em uma função do AAD, mas em permissões no centro de administração. Eles são especialistas no assunto capazes de remediar o conteúdo em tópicos, adicionando recursos e pessoas.

Dependendo da sua organização, você pode ter algumas ou muitas pessoas atuando nessas funções. Para algumas organizações, elas podem ser as mesmas pessoas.

| Administrador de conhecimento | Gerente de conhecimento | Colaborador de tópicos |
|:-------|:-------|:-------|:-------|
| Função AAD | Função AAD | SME |
| Tem acesso ao centro de administração | Tem acesso ao centro de administração | Sem acesso ao centro de administração |
| Configura tópicos do Viva | Possui o gerenciamento e a qualidade dos tópicos | Contribui para tópicos com base em seus conhecimentos. |
| Garante que os padrões de segurança e conformidade sejam aplicados e compreendam o contrato de licenciamento.| Executa tarefas de gerenciamento de tópicos, como criar, editar, excluir e rejeitar tópicos. Dá suporte a colaboradores de tópicos com suas tarefas. | Cura as informações e o conteúdo nas páginas de tópicos, incluindo quais pessoas e recursos são fixados nesse tópico. |

Destaques e cartões aparecerão para os usuários no contexto de seu trabalho, por exemplo, à medida que navegarem por páginas modernas no SharePoint. Você controla a experiência do usuário final para tópicos.

- Quem pode ver Tópicos? A visibilidade do tópico está configurada no Centro de Administração do Microsoft 365. Escolha quais grupos permitirão ver tópicos:
  - Todos na minha organização. "Todos" não inclui convidados, são todos os usuários internos em seu diretório
  - Somente pessoas selecionadas ou grupos de segurança (essa opção é boa enquanto você ainda está lançando tópicos do Viva, para que você possa testar com um subconjunto de usuários). Se quiser que os convidados consultem Tópicos, você precisará usar a opção "pessoas ou grupos de segurança selecionados" e conceder uma licença a eles.
  - Ninguém.

    Todos os usuários, mesmo os convidados, precisarão ter uma licença aplicada para exibir a experiência do tópico. E lembre-se de que as permissões sempre controlam o que pode ser visto.

- Quais tópicos estão visíveis? Você pode optar por:
  - Mostrar todos os tópicos de candidatos.
  - Mostrar apenas tópicos confirmados.

Agora que temos os gerentes, especialistas e usuários, podemos falar sobre os próprios tópicos.

- É uma boa prática fazer a semeia de tópicos em sua lista de tópicos. A qualidade e a quantidade de tópicos são baseadas em seu conteúdo. Ele só será criado como um tópico se estiver incluído no conteúdo que está no escopo. Se houver informações e evidências suficientes para o tópico, eles serão criados pela IA. A seeding topics is where the Knowledge Manager and subject-matter experts can help. Combinar o conhecimento humano com a IA é a melhor rota para tópicos de qualidade. Portanto, se houver tópicos antecipados, você poderá criar manualmente esses tópicos no Centro de tópicos. Fazer isso dará à IA um sinal forte da relevância desse tópico e identificará recursos e pessoas a associar a esse tópico.
- Use taxonomias existentes para ajudar no planejamento de tópicos, seja no SharePoint ou em outro lugar. Taxonomias existentes geralmente incluem termos organizacionais, produtos, áreas de assunto e assim por diante. As fontes para tópicos também podem vir de listas de projetos, indicadores de pesquisa existentes e assim por diante.
