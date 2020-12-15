---
title: O que há de novo no centro de administração do Microsoft 365?
f1.keywords:
- CSH
ms.author: anfowler
author: adefowler
manager: shohara
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
- FRP150
description: O centro de administração do Microsoft 365-Aprenda sobre os recursos que foram adicionados este mês.
ms.custom:
- MACDashWhatsNew
- AdminSurgePortfolio
ms.openlocfilehash: 90805568d77cf55cbd0e77fb3085435df09824ab
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668044"
---
# <a name="whats-new-in-the-microsoft-365-admin-center"></a>O que há de novo no centro de administração do Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Algumas das informações deste artigo podem não se aplicar ao Office 365 operado pela 21Vianet.

::: moniker-end

Estamos adicionando continuamente novos recursos ao [centro de administração do Microsoft 365](microsoft-365-admin-center-preview.md), corrigindo os problemas que aprendemos e fazendo alterações com base em seus comentários. Veja o que está disponível para você hoje. Alguns recursos são implementados em diferentes velocidades para nossos clientes. Se ainda não estiver vendo um recurso, [tente adicioná-lo ao lançamento direcionado](manage/release-options-in-office-365.md).

E se você quiser saber o que há de novo em outros serviços de nuvem da Microsoft:

- [O que há de novo no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/whats-new)
- [O que há de novo no centro de administração do Exchange](https://docs.microsoft.com/Exchange/whats-new)
- [Novidades do Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/whats-new)
- [O que há de novo no centro de conformidade da Microsoft 365](https://docs.microsoft.com/Office365/SecurityCompliance/whats-new)
- [Novidades no Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)
- [O que há de novo no centro de administração do SharePoint](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)
- [Atualizações do Office](https://docs.microsoft.com/OfficeUpdates/)

## <a name="ignite-2020-august--september"></a>Ignite 2020 (agosto de & setembro)

Bem-vindo ao Microsoft Ignite-nosso primeiro Ignite somente online. Esperamos ver você em uma de nossas sessões: catálogo de [sessão do Microsoft Ignite 2020](https://myignite.microsoft.com/sessions). Veja aqui apenas algumas das coisas que falaremos em Ignite. 
> [!NOTE]
> Nem todos os recursos estarão disponíveis para todas as pessoas imediatamente. Se você não estiver vendo os novos recursos, [ingresse no lançamento direcionado](manage/release-options-in-office-365.md).

### <a name="multi-tenant-management"></a>Gerenciamento de vários locatários

Desenvolvemos um conjunto de recursos para administradores de vários locatários como você para que o trabalho seja feito de forma mais rápida e eficiente.

- **Seus locatários**: alternar rapidamente entre os locatários que você gerencia.
- **Todos os locatários**: uma nova página na qual você pode ver rapidamente a integridade de todos os serviços de seus locatários, todas as solicitações de serviço abertas, seus produtos e cobrança, as tarefas de configuração recomendadas e o número de usuários nesse locatário.
- **Configuração**: a página de configuração de vários locatários fornece um modo de exibição de lista da página de configuração, mas organizadas para vários locatários. Você pode ver quais recursos não estão ativados, quais tarefas são concluídas para todos os locatários, tarefas que os locatários ainda precisam concluir. Este modo de exibição o ajudará a acompanhar a adoção de recursos e a garantir que as tarefas de configuração de segurança recomendadas sejam sempre realizadas.
- **Integridade do serviço**: o modo de exibição de integridade do serviço mostra se algum incidentes ou comunicados estão afetando os locatários. Ele até mesmo dirá quantos de seus locatários gerenciados são afetados. Apenas selecione um incidente para obter mais informações sobre a guia Visão geral e, em seguida, alterne para a guia de locatários afetados para detalhar e dar suporte a esse locatário.
- As **migrações de caixa de correio de vários locatários** são um novo serviço, agora em visualização pública, que permite mover caixas de correio entre locatários sem a necessidade de externamente e, em seguida, caixas de correio integradas. 
- **Compartilhamento de domínios entre locatários**: em breve, você pode ingressar em uma visualização privada para recursos que permitem compartilhar um domínio em vários locatários. Por exemplo, se a contoso adquire a Wingtip Toys, a Contoso pode compartilhar o domínio com a Wingtip Toys para que as pessoas em ambos os locatários possam usar o "contoso.com" como seus endereços de email.

![Página integridade do serviço para vários locatários com um incidente selecionado e a guia de locatários afetados aberta. O menu de navegação tem todos os locatários, a configuração e a integridade do serviço como as únicas opções.](../media/MAC-WN-MTinServiceHealth.png)

### <a name="monitor-your-most-important-accounts"></a>Monitorar suas contas mais importantes

Você pode monitorar e acompanhar mensagens de email com falha ou atrasadas enviadas para seus usuários com alto impacto nos negócios, como seu CEO. Você controla as contas de prioridade adicionando usuários à sua lista de contas de prioridade no centro de administração do Microsoft 365. Adicione executivos, líderes, gerentes ou outros usuários que tenham acesso a informações confidenciais ou de alta prioridade.

As contas de prioridade só estão disponíveis para as organizações que atendem aos dois requisitos a seguir:

- Office 365 E3 ou Microsoft 365 E3 ou Office 365 E5 ou Microsoft 365 e5.
- Pelo menos 10.000 licenças e pelo menos 50 usuários ativos mensais do Exchange Online.

![Página de configuração do recurso: monitorar suas contas mais importantes](../media/MAC-WN-PriorityAccounts.png)

Há duas maneiras de começar:

- Vá para **usuários** e, no menu "mais ações", selecione **gerenciar contas de prioridade** para adicionar usuários à lista.
- Vá para **configuração**, encontre a tarefa de configuração para **monitorar suas contas mais importantes** e, em seguida, selecione **introdução**.

Para obter mais informações sobre contas de prioridade, consulte [monitorando contas de prioridade](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).

### <a name="search-faster-and-get-better-results-from-any-page"></a>Pesquisar mais rápido e obter melhores resultados de qualquer página

Começamos a implantar uma nova experiência de pesquisa para o centro de administração e não podemos esperar por você experimentá-lo. A ![ caixa de pesquisa foi movida para a região de faixa. ALT + S para Pesquisar de qualquer página.](../media/MAC-WN-GlobalSearch.png)

- A caixa de pesquisa foi movida para a área de cabeçalho onde diz "centro de administração do Microsoft 365" para que você agora pesquise em qualquer página, e não apenas na página inicial. Temos até obter um atalho: **ALT + S**.
- A pesquisa é mais inteligente e fornecerá melhores resultados, até mesmo mais rápido. Tente digitar "2Fa" para começar.
- Os resultados da pesquisa são organizados pelo tipo de item ou ação que você pode tomar.
  - **Usuários**: selecione o nome do usuário e você pode editar esse usuário diretamente lá. Se você selecionar o menu "mais ações" ao lado do nome, poderá redefinir a senha. Você pode pesquisar por nome de exibição, sobrenome, nome, nome de usuário ou endereço de email principal e aliases de email. Mas para obter uma correspondência exata, pesquise por endereço de email principal ou nome de usuário.
  - **Grupos**: editar o grupo de qualquer página, adicionar membros, atribuir proprietários.
  - **Ações**: semelhante à forma como você pode pesquisar um usuário e redefinir sua senha, você também pode Pesquisar "Redefinir senha" em qualquer página e, em seguida, redefinir uma ou mais senhas para usuários.
  - **Navegação**: os resultados na navegação podem ajudá-lo rapidamente a obter rapidamente uma página no centro de administração. Por exemplo, a pesquisa de "funções" levará você para a página de funções das funções do Azure AD.
  - **Configurações**: Procure qualquer configuração relacionada à sua organização, os serviços que você assina e as configurações de segurança e privacidade. 
  - **Domínios**: você pode encontrar links rápidos para seus domínios e, em seguida, o link o levará para a página Visão geral e integridade desse domínio.
  - **Documentação**: se não for possível encontrar um resultado para você, tentaremos encontrar uma documentação para ajudar. Demora um pouco mais para a lista organizada de artigos para localizar uma correspondência, portanto, aguarde um segundo para que a pesquisa encontre os resultados. 
  - **Feedback**: não encontrou o que você estava procurando? Envie-nos comentários da pesquisa. Adicionaremos funcionalidade de pesquisa para mais páginas e mais recursos no centro de administração.

### <a name="microsoft-365-admin-mobile-app"></a>Aplicativo móvel de administração do Microsoft 365

O [aplicativo microsoft 365 admin Mobile](https://www.microsoft.com/microsoft-365/business/manage-office-365-admin-app), que está incluído na sua assinatura, permite que você gerencie o Microsoft 365 do seu dispositivo móvel para que você possa sair da sua mesa para realizar tarefas diárias. Na verdade, há mais de 90 recursos no aplicativo e acabamos de adicionar mais alguns:

- **Suporte para políticas de acesso condicional e de gerenciamento de aplicativo móvel do Microsoft Intune**: agora você pode usar seu dispositivo pessoal para gerenciar o Microsoft 365 mesmo que sua organização tenha ativado as políticas de acesso condicional e de gerenciamento de aplicativo móvel do Intune.
- **Notificações do centro de mensagens**: Ative as notificações de central de mensagens em **configurações**, caso queira  >   ser alertado sobre novas postagens do centro de mensagens. Por meio de notificações, queremos garantir que você fique informado sobre informações importantes e eventos em seu locatário.
- **Alertas de cobrança**: você também pode ativar notificações de cobrança em notificações de **configurações**  >   se quiser obter notificações de cobrança no seu dispositivo se uma assinatura estiver prestes a expirar.
- **Modo escuro**: Bem-vindo ao lado escuro do aplicativo móvel. Este foi um dos recursos mais solicitados. Vá para   >  **temas** de configurações para ativá-la.
- **Relatar um problema**: agora você pode relatar um problema no aplicativo ou exibir problemas relatados por outros administradores. Visite **integridade do serviço** para fazer o check-out.

![A página de integridade no aplicativo de administração do Microsoft 365 com notificações para o centro de mensagens, integridade do serviço, alertas de cobrança.](../media/MAC-WN-AdminMobileApp.png)

### <a name="usage-recommendations-for-small-and-medium-businesses"></a>Recomendações de uso para pequenas e médias empresas

Pequenas e médias empresas podem obter uma recomendação na **Home** Page se algumas pessoas da organização não estiverem usando ativamente o Teams, o onedrive ou os aplicativos do Office. Ao exibir a recomendação, você pode enviar emails rapidamente para o treinamento da Microsoft para usuários inativos para ajudá-los a começar a usar o aplicativo e a garantir que você esteja obtendo o valor completo de suas assinaturas.

### <a name="remote-work-collection"></a>Conjunto de trabalho remoto

Em outubro, adicionaremos uma coleção de trabalho remota para ajudar os proprietários de pequenas empresas e sua equipe a ficar online e a trabalhar remotamente.  Configuração do **Essentials de trabalho remoto** é uma lista organizada de todos os recursos que a Microsoft recomenda para habilitar o trabalho remoto e colaborar de forma segura. Em algumas semanas, você pode experimentá-lo em **Configurar** o  >  **princípios de trabalho remoto**.

![Página recursos de trabalho remoto no programa de instalação com sete tarefas não iniciadas.](../media/MAC-WN-RemoteWork.png)

Para obter mais informações sobre como permitir com segurança o trabalho remoto e um endereço da Web útil que seja fácil de lembrar e compartilhar, acesse [aka.ms/Remote-Business](https://aka.ms/remote-business).

### <a name="need-help-moving-to-more-admin-centers"></a>Precisa de ajuda? movendo para mais centros de administração

Estamos examinando e atualizando continuamente o conteúdo e as ferramentas para acompanhar as alterações no produto. Agora, temos muito mais ferramentas de diagnóstico de autoatendimento para ajudá-lo a resolver problemas com rapidez e eficiência. Veja algumas que foram adicionadas recentemente:

- Alterar sua política de limitação de serviços Web do Exchange
- Verificando o status do provisionamento e da validação do teams para usuários específicos
- Corrigir problemas de configuração do DKIM
- Diagnosticar erros de registro do usuário do Intune

E estamos distribuindo a experiência de suporte nova e aprimorada que você já vê no centro de administração do Microsoft 365 para alguns dos outros centros de administração. O centro de administração do Microsoft Teams e os centros de administração de segurança e conformidade já têm essa nova experiência. Logo, o **centro de administração do Exchange**, o **centro de administração do SharePoint** e o **Office.com** serão atualizados junto com essa nova experiência de ajuda para administradores.

### <a name="manage-changes-with-microsoft-planner"></a>Gerenciar alterações com o Microsoft Planner

Em maio, anunciamos que você poderá sincronizar as postagens do centro de mensagens para o Microsoft Planner e agora ela está disponível para que todos possam usar o.  Agora você pode criar tarefas a partir de mensagens, atribuí-las e rastreá-las à conclusão. Na primeira vez, você seleciona a **sincronização de planejador** , precisará se conectar ao plano apropriado.

![Página do centro de mensagens com a "sincronização do planejador" realçada na barra de comandos ao lado do botão preferências.](../media/MAC-WN-MCPlannerSync.png)

Para saber mais sobre ele, confira este artigo e vídeo para ver como funciona: [controle suas postagens do centro de mensagens no Planner](https://docs.microsoft.com/Office365/Planner/track-message-center-tasks-planner)

### <a name="documentation-training-and-videos"></a>Documentação, treinamento e vídeos

- Nova marca e tempo para o Microsoft Ignite--[o Hub virtual](https://adoption.microsoft.com/virtual-hub/). Aprofundamento no treinamento técnico para profissionais de ti e desenvolvedores. Encontre rapidamente 20 novos vídeos como parte do #SIDETRACKED, o nome do controle de administração do Ignite este ano.
- [O que há de novo com a série de vídeo da Microsoft 365](https://www.youtube.com/watch?v=OVjb2lGJ4GU&t=2s) : este mês, abordamos os novos recursos disponíveis no whiteboard para Teams e na Web, como automatizar o provisionamento de usuários para o Azure AD, nova potência automatizar gatilhos e ações no Teams e muito mais. E fique atento no próximo mês, onde teremos uma recapitulação de todas as coisas boas que ocorrem em Ignite!
- Fizemos um novo design da página de [documentação da Microsoft 365](https://docs.microsoft.com/microsoft-365) que se concentra nas soluções primeiro. Vamos destacar novas soluções à medida que elas forem disponibilizadas nesta página, portanto, fique atento.

![Nova página de aterrissagem para a documentação de soluções do Microsoft 365 com soluções como "capacitar funcionários remotos".](../media/MAC-WN-M365Docspage.png)

## <a name="july-2020"></a>Julho de 2020

### <a name="getting-ready-for-ignite-2020"></a>Preparando-se para o Ignite 2020

Como estamos migrando para a temporada Ignite da Microsoft, não estamos lançando o máximo de recursos para que possamos falar sobre durante nossas sessões.

A próxima atualização deste artigo será no dia de abertura do nosso primeiro Ignite somente online. E este ano, é gratuito participar! Faça o check-out, conecte-se: [Microsoft Ignite 2020](https://www.microsoft.com/ignite).

### <a name="your-products"></a>Seus produtos

Houve muito trabalho no gerenciamento de assinaturas para tornar a página mais rápida para carregar, mais rápido localizar o que você está procurando e para atender aos padrões de acessibilidade da Web ([WCAG 2,1 Guidelines](http://www.w3.org/TR/WCAG21/)).

- **Redesign de tabela**: a tabela foi reprojetada para que você possa agrupar assinaturas semelhantes. Vá para **cobrança**  >  **de seus produtos**.
- **Detalhes do produto**: Obtenha mais detalhes do que nunca sobre suas assinaturas selecionando o produto na lista.
- **Faça tudo** daqui: e você não precisa ir para várias páginas para gerenciar um produto. Por exemplo, se você precisar cancelar uma assinatura, o painel será aberto para executar a ação imediatamente.

![Página de produtos com o painel cancelar inscrição aberto.](../media/MAC-WN-SubscrDetails.png)

### <a name="domains"></a>Domínios

O gerenciamento de domínio pode ser complicado e lançamos um novo recurso para facilitar isso. Vá até configurações > domínios e selecione um domínio para obter mais informações sobre o domínio e a integridade do domínio.

:::image type="content" source="../media/MAC-WN-DomainDNS.PNG" alt-text="Página de detalhes de domínios para contoso.com":::

### <a name="docs-training-and-videos-july-2020"></a>Docs, treinamento e vídeos (julho de 2020)

[O que há de novo com](https://youtu.be/m1Nu8WJgCDY) a série de vídeo da Microsoft 365: este mês, abordamos a nova experiência do Yammer para Web e móvel, como integrar o aplicativo de comunidades do Yammer para o Microsoft Teams, novos pacotes de política para dar suporte a operadores e gerentes de primeira e mais.

## <a name="june-2020"></a>Junho de 2020

### <a name="keeping-up-with-office-whats-new-management"></a>Acompanhar o gerenciamento de novidades do Office

Há alguns meses, adicionamos uma configuração que permite que você gerencie as [mensagens de novidades que aparecem em aplicativos do Office de um usuário](#office-whats-new-management). Este mês, lançamos um novo cartão de Home Page que o ajudarão a agir rapidamente e acompanhará as mensagens de **novidades** que você deseja exibir para os usuários em sua organização.

### <a name="docs-training-and-videos-june"></a>Docs, treinamento e vídeos (junho)

- [Introdução ao Teams](https://support.microsoft.com/office/184f1aba-2f91-43f0-86e1-9fae607e24f6)

## <a name="may-2020"></a>Maio de 2020

### <a name="new-update-channel-for-office"></a>Novo canal de atualização para o Office

Em 12 de maio, anunciamos a disponibilidade de um novo canal de atualização para o Office: canal corporativo mensal. Este canal de atualização fornece aos usuários novos recursos do Office uma vez por mês, na segunda terça-feira do mês.

Se você permitir que os usuários instalem o Office de forma automática no portal, poderá selecionar canal corporativo mensal para eles. Para fazer isso, entre no centro de administração do Microsoft 365 e vá para **Mostrar todas** as configurações da  >   >  **organização** de  >  **Serviços** de  >  **download de software do Office**. Se você selecionar **uma vez por mês (canal corporativo mensal)**, qualquer autoinstalação do Office será configurada para usar o canal corporativo mensal.

Em conjunto com o lançamento do canal corporativo mensal, também estamos revisando os nomes dos canais de atualização existentes. Por exemplo, o canal mensal está sendo renomeado para o canal atual. Os novos nomes têm efeito em 9 de junho de 2020.

Para obter mais informações, consulte [Changes to update Channels for Microsoft 365 apps](https://docs.microsoft.com/DeployOffice/update-channels-changes).

### <a name="new-admin-roles"></a>Novas funções de administrador

Adicionamos algumas novas funções de administrador do Azure Active Directory ao centro de administração do Microsoft 365.

- A função de administrador de identidade híbrida dá aos usuários permissão para gerenciar o provisionamento na nuvem e os serviços de autenticação.
- A função de administrador de rede permite que os usuários gerenciem locais de rede e analisem as informações de rede do software Microsoft 365 como um aplicativo de serviço.
- A função de administrador da impressora concede permissão para gerenciar todos os aspectos de impressoras e conexões de impressora.
- O técnico da impressora é um subconjunto da função de administrador da impressora onde esses usuários podem registrar e cancelar o registro de impressoras e atualizar o status da impressora.
Para saber mais sobre essas funções, consulte [sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

### <a name="export-groups-list"></a>Lista de grupos de exportação

Ouvimos muitos administradores de que eles precisam compartilhar informações sobre grupos e seu uso para pessoas que não têm acesso aos centros de administração. Agora você pode exportar a lista de grupos para um arquivo CSV para fins de auditoria, o que significa que você pode jogar esse script antigo do PowerShell. Para experimentá-lo, vá **para grupos de grupos**  >  e selecione **Exportar grupos** na barra de comandos.

### <a name="microsoft-365-solution-and-architecture-center"></a>Centro de soluções e arquitetura da Microsoft 365

Apenas este mês, lançamos um novo site [https://docs.microsoft.com](https://docs.microsoft.com) chamado do [centro de soluções e arquiteturas da Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/solution-architecture-center), que reúne as orientações técnicas de que você precisa para entender, planejar e implementar soluções integradas da Microsoft 365 para colaboração segura e compatível. Neste centro, você encontrará:

- Diretrizes de solução básica
- Soluções de carga de trabalho e orientações de cenário
- Ilustrações de solução e arquitetura (os cartazes!!!)
- Orientação específica do setor
- Entidades de design de arquitetura corporativa

### <a name="docs-training-and-videos-may"></a>Docs, treinamento e vídeos (maio)

- **O que há de novo na série de vídeo do Microsoft 365**: este mês, abordamos a nova experiência de suporte no administrador do Teams e nos centros de segurança e conformidade, a integração do Planner com o centro de mensagens e o novo layout de vídeo 3x3 no Microsoft Teams. 
- A página do hub de [ajuda do centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/) foi atualizada para ajudá-lo a encontrar o que você precisa mais rapidamente. E se você examinar essa página agora, adicionamos um cartão para informá-lo sobre atualizações e alterações importantes.

## <a name="april-2020"></a>Abril de 2020

### <a name="intune-roles-management"></a>Gerenciamento de funções do Intune

[Abril de 2020](#april-2020)

Bem, fizemos! Fizemos a segunda etapa em direção a uma experiência de funções unificadas e agora você pode gerenciar as funções do Intune no centro de administração do Microsoft 365. Você também pode aproveitar recursos como a capacidade de Pesquisar funções e exibir permissões de função. Isso significa que você não precisa de duas ferramentas separadas para gerenciar as funções do Microsoft 365 e do Intune. Ao entrar no centro de administração do Microsoft 365, você verá que há duas pivôs na página funções, uma para o Azure AD e outra para o Intune.

![Página de funções com a tabela dinâmica do Intune selecionada](../media/MAC-WN-IntuneRoles.png)

### <a name="sync-message-center-posts-to-planner"></a>Sincronizar postagens do centro de mensagens no Planner

A partir de maio, os administradores que estão no lançamento direcionado começarão a exibir o botão "sincronização de planejador" no centro de mensagens. Agora você pode rastrear mensagens que precisam de ação, selecionar o tipo de mensagens que deseja rastrear, atribuir mensagens a serem rastreadas como tarefas e marcar mensagens para atenção posterior.

[Ingresse no lançamento direcionado](manage/release-options-in-office-365.md) para começar!

### <a name="need-help-launched-in-teams-admin-center--security-and-compliance-centers"></a>"Precisa de ajuda?" iniciado no centro de administração do Microsoft Teams & segurança e centros de conformidade

O centro de administração do Microsoft Teams, a central de segurança e o centro de conformidade estão agora usando o mesmo "precisa de ajuda?" recurso que o centro de administração do Microsoft 365 usa para localizar ajuda e suporte de contato. Recebemos muitos comentários de administradores que você queria do mesmo nível de ajuda e suporte e estamos felizes em levá-lo para você. Experimente e nos envie seus comentários!

#### <a name="need-chat"></a>Precisa de chat?

Nossos agentes de suporte trabalham em casa enquanto ainda estão levando os casos e limitações do cliente na largura de banda da Internet enquanto o trabalho de casa pode afetar a qualidade de chamadas do cliente. Para continuar dando suporte a você, lançamos a opção de suporte ao Live Chat para clientes comerciais no centro de administração do Microsoft 365.

Ao criar uma solicitação de serviço, agora você verá o chat como uma opção, além de telefone e email. Selecione chat como um canal de comunicação preferencial e crie a solicitação. Depois de criar a solicitação, você pode iniciar o chat quando estiver pronto para bater papo com os agentes da Microsoft.

### <a name="teams-updates"></a>Atualizações do teams

Com o uso mais elevado do Teams, adicionamos alguns recursos para ajudá-lo a gerenciá-los.

- Um novo cartão de recomendação na home page do centro de administração mostra quais usuários não usaram ativamente o Teams por 30 dias. Você pode enviar a esses usuários um email de treinamento para começar a usar o Microsoft Teams.
- **Reúna pessoas com o Teams**: Vá para **configuração** para ver uma nova página para ajudá-lo a ativar o Teams para usuários licenciados e permitir acesso de convidados, para que você possa trabalhar com clientes externos no Microsoft Teams.
- Um cartão Microsoft Teams agora está fixado por padrão à sua Home Page. Ele mostra se o Microsoft Teams está ativado e se o acesso de convidados é permitido. Ele também permite que você verifique o status de configuração de usuários de equipes recentemente licenciados e verifique se os problemas de rede podem afetar os usuários do teams.
- Por fim, o Microsoft Teams agora é uma etapa no fluxo de configuração inicial, se você comprou uma licença que inclui o Microsoft Teams.

### <a name="productivity-score"></a>Pontuação de produtividade

A pontuação de produtividade fornece informações sobre como as pessoas usam os serviços de nuvem da Microsoft e as experiências tecnológicas que dão suporte a eles. A pontuação reflete o desempenho da organização em relação à experiência de funcionários e tecnologias e compara sua pontuação com organizações como a sua. Este mês, apresentamos os seguintes novos conceitos para a experiência de visualização:

- Exibição de tendência de principais ideias nas páginas de detalhes da Home Page e da categoria-categorias de ponto de extremidade e de conectividade de rede adicionadas à experiência de tecnologia
- Informações relevantes sobre a experiência tecnológica mostradas nas categorias de experiência do funcionário
- Nova categoria de comunicações como parte da experiência do funcionário
- Detalhes do usuário com metadados organizacionais em categorias de experiência do funcionário

Se quiser saber mais, confira o blog: [meça e aprimore a experiência da microsoft 365 com a pontuação de produtividade da Microsoft](https://techcommunity.microsoft.com/t5/microsoft-365-blog/measure-and-improve-the-microsoft-365-experience-with-microsoft/ba-p/1348618). A pontuação de produtividade está atualmente em visualização privada. [Participe da visualização privada da Pontuação de produtividade](https://aka.ms/productivityscorepreview) para começar.

### <a name="groups-updates"></a>Atualizações de grupos

Temos duas atualizações para grupos este mês:

- Agora você pode editar endereços de email para grupos do Office 365 (também conhecidos como grupos no Outlook e, em breve, ser conhecido como Microsoft 365 grupos).
- Ouvimos seus comentários e adicionamos mensagens de erro mais claras por que você não pode converter um grupo em uma equipe da Microsoft.

### <a name="docs-videos-and-training-april"></a>Docs, vídeos e treinamento (abril)

**O que há de novo na série de vídeo do Microsoft 365**: este mês, abordamos dicas e recursos para ajudar as pequenas empresas a migrar para o trabalho remoto, incluindo como distribuir o Microsoft Teams, recursos de treinamento de trabalho remoto para permanecer conectado com clientes e parceiros e o novo plano Microsoft 365 Business Voice. [O que há de novo no Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096)

#### <a name="for-your-users"></a>Para seus usuários

- [Agendar uma reunião](https://support.microsoft.com/office/c61b4f61-ee62-4a06-8bf7-0a1cd302700a)
- [Ingressar em uma reunião do teams](https://support.microsoft.com/office/078e9868-f1aa-4414-8bb9-ee88e9236ee4)
- [Criar uma equipe de toda a organização](https://support.microsoft.com/office/037bb27a-bcc9-48fe-8d72-44d9482420a3)
- [Criar uma equipe com convidados](https://support.microsoft.com/office/11fbb083-52ee-434d-8c6e-63711fdafac7)
- [Ingressar em uma equipe como convidado](https://support.microsoft.com/office/928d1eef-61e2-49ec-b754-c2fe86b34824)
- [Criar um endereço de email do grupo](https://support.microsoft.com/office/ded875f9-a9de-437f-b559-2ae4f235bb2b)

#### <a name="for-admins-and-business-owners"></a>Para administradores e proprietários de negócios

- [Capacitar sua pequena empresa com trabalho remoto](https://support.microsoft.com/office/9b91a85a-39b4-40a6-a590-0f9bea0ba8e6)
- [Executando uma pequena empresa remota](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)
- [Inscreva-se no Microsoft Business Basic](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)
- [Configurando a entrada de dois fatores](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)

## <a name="march-2020"></a>Março de 2020

### <a name="featured-feedback-fix-improve-add-user-reliability-for-licensing"></a>Correção de comentários em destaque: melhorar a confiabilidade "Adicionar usuário" para licenciamento

Recebemos muitos comentários de administradores sobre o quão difícil é atribuir licenças ao adicionar usuários. Fizemos a primeira atualização dessa correção e migramos para um serviço por trás de bastidores mais confiável para processar essas solicitações. E, se algo der errado, você receberá uma mensagem de erro que permite que você tente novamente.

![Adicione a página de confirmação do usuário com o erro.](../media/MAC-WN-ImprovedLicensing.png)

### <a name="microsoft-teams-home-page-card"></a>Cartão de home page do Microsoft Teams

Com o uptick no uso do Teams, alguns organizações expandidas receberão um cartão de painel afixado que torna o Microsoft Teams mais detectável. O cartão também tem links para treinamento e documentos para ajudar sua organização a fazer a transição para o trabalho remoto. Basta ir para a **Home** Page para ver o novo cartão.

![Cartão de home page do Microsoft Teams](../media/MAC-WN-TeamsCard.PNG)

### <a name="customize-your-organizations-sharepoint-mobile-app-theme"></a>Personalizar o tema do aplicativo móvel do SharePoint da sua organização

Usando o centro de administração do Microsoft 365, agora você pode personalizar o tema da sua organização no aplicativo móvel do SharePoint para iOS e o aplicativo móvel do SharePoint para Android. Esse recurso fornece convenientemente uma experiência de aplicativo de intranet móvel que pode corresponder ao seu SharePoint Online para funcionários em trânsito. A personalização do tema inclui a imagem do logotipo, a cor da barra de navegação, as cores de texto e ícone e as cores de ênfase, fazendo com que o reconhecimento seja fácil.

![Mapeamento de diagrama as configurações do centro de administração para o aplicativo móvel.](../media/MAC-WN-CustThemeSP.png)

### <a name="improvements-to-the-add-a-group-wizard"></a>Aprimoramentos para o assistente "adicionar um grupo"

Quando os administradores criaram um novo grupo e o tornaram uma equipe ao mesmo tempo, eles podem atribuir proprietários que não têm uma licença que inclui o Microsoft Teams. E que criou algumas dores de dor. Atualizamos o fluxo do assistente para verificar se os proprietários têm uma licença do Teams e se não a opção de ativar o grupo em uma equipe está desabilitada.

### <a name="microsoft-365-offerings-for-small-and-medium-businesses"></a>Ofertas da Microsoft 365 para pequenas e médias empresas

Sabemos que este é um comunicado para o próximo mês, mas queremos garantir que você está preparado.

A partir de 21 de abril, estamos fazendo alterações relacionadas às assinaturas do Office 365 para pequenas e médias empresas – e para o Office 365 ProPlus. Agora, esses produtos usarão a marca Microsoft 365.

Os novos nomes de produto entram em vigor em 21 de abril de 2020. Essa é uma alteração no nome do produto e não há alterações de preços ou recursos no momento.

|Nome atual |Novo nome  |
|---------|---------|
|Office 365 Business Essentials     |   Microsoft 365 Business Basic      |
|Office 365 Business Premium     |    Microsoft 365 Business Standard     |
|Microsoft 365 Business     |    Microsoft 365 Business Premium     |
|Office 365 Business     |    Aplicativos do Microsoft 365 para empresas       |
|Office 365 ProPlus    |   Aplicativos da Microsoft 365 para empresas      |

### <a name="videos-training-and-docs"></a>Vídeos, treinamento e documentos

[O que há de novo no microsoft 365 Web Series](https://go.microsoft.com/fwlink/p/?linkid=2118096): no episódio deste mês, destacamos o aniversário de três anos do Microsoft Teams e abordam novos recursos, incluindo qualidade de áudio aprimorada em reuniões online, comunicações direcionadas para gerentes de primeira função com o aplicativo turnos, o Teams e a interoperabilidade de consumidor do Skype e muito mais.

## <a name="february-2020"></a>Fevereiro de 2020

### <a name="featured-feedback-fix-multi-organization-switcher"></a>Correção de comentários em destaque: alternador de várias organizações

Recebemos muitos comentários de parceiros e administradores sobre os desafios de gerenciamento de vários Microsoft Cloud organizações expandidas. Um dos nossos primeiros recursos de gerenciamento de vários org é o **alternador de organização**, que permite que você altere entre o organizações expandidas que você gerencia em apenas dois cliques.
> [!TIP]
> Você não precisa fazer nada para fazer com que o alternador de organização seja exibido enquanto você é o parceiro de pelo menos uma organização.

1. No centro de administração do Microsoft 365, selecione o nome da organização.
![Captura de tela: parte superior da Home Page mostrando o nome do perfil da organização com o ícone do alternador.](../media/MAC-Organization-switcher.png)

2. No alternador de organização, selecione o org que você deseja gerenciar.
![Captura de tela: o seletor de locatários de minhas organizações com o locatário do exconsolidated Messenger](../media/MAC-OrgSwitcherSelected.png)

Isso é literalmente!!!

### <a name="groups"></a>Grupos

Há algumas alterações na área de grupos deste mês:

- **Classificar por nome de grupo**: é possível classificar a lista de grupos alfabeticamente, selecionando a coluna **nome do grupo** .
- **Restore Deleted microsoft 365 groups**: não é necessário ir para o centro de administração do Exchange mais para restaurar os grupos excluídos da Microsoft 365. Vá para **centro de administração do Microsoft 365** \> **grupos** \> de **grupos excluídos** \> (selecione um grupo no \> **grupo de restauração** de lista). Ele restaurará o grupo de volta para a lista de **grupos** e restaurará o email, as conversas, o bloco de anotações, os arquivos e o calendário do grupo.

### <a name="videos-training-and-docs-february"></a>Vídeos, treinamento e documentos (fevereiro)

- **O que há de novo na série de vídeo da Microsoft 365**: este mês, nos concentramos nos recursos de pesquisa personalizados para o SharePoint Online, o recurso de gerenciamento "o que há de novo" do Office que permite mostrar ou ocultar recursos específicos de usuários finais por meio do painel de ajuda no aplicativo, as últimas atualizações de segurança e conformidade no Yammer e muito mais. Este é o episódio mais recente: [o que há de novo no Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096)

- **Movimentação de docs**: combinamos os artigos do Office 365 admin Web com o conteúdo do Microsoft 365 e você pode ter notado a nova URL. Por exemplo, este artigo costumava ser hospedado em: **docs.Microsoft.com/Office365/admin/Whats-New-in-Preview**, mas a URL agora é: **docs.Microsoft.com/Microsoft-365/admin/Whats-New-in-Preview**. Se você tiver marcado as páginas, deverá atualizar seus links; no entanto, os links de conteúdo serão redirecionados para o novo repositório de conteúdo.

## <a name="january-2020---happy-new-year"></a>Janeiro de 2020-feliz ano novo

> [!NOTE]
> Você sabia que há uma [novidade no Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096) Video Series no YouTube? Ele realça os recursos mais recentes que foram implantados para os usuários. A cada mês, começaremos a vincular o episódio mais recente na seção [vídeos, treinamento e documentos](#videos-training-and-docs) . <br> <br> Este é o episódio mais recente: [o que há de novo no Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096)

### <a name="dark-mode"></a>Modo escuro

Quando fizemos pela primeira vez o modo escuro, ele estava disponível apenas na página inicial. O modo escuro agora está fora da visualização e está no lançamento direcionado na maioria das páginas no centro de administração.

1. Primeiro, você precisará ativar o lançamento direcionado: Vá para configurações de **configurações** \>  \> **perfil da organização** \> **preferências de versão**.
1. E, em seguida, ative o modo escuro, vá para a página **inicial** e selecione o botão **modo escuro** . (Está ao lado do campo de **pesquisa** e o link **novidades** do artigo.)
1. Para qualquer página que tenha um modo escuro disponível, o botão fica na parte superior da página, ao lado **do novo centro de administração** .

### <a name="office-whats-new-management"></a>Gerenciamento de o que há de novo no Office

Os administradores desejam controlar como a Microsoft se comunica "What ' s New" aos seus usuários nos aplicativos do Office – e agora você tem esse controle. Vá para **configurações** do \> **Office o que é a visualização de gerenciamento de** novidades. Selecione um recurso para exibir seus detalhes e, em seguida, selecione o botão **ocultar de usuários** se não quiser que seus usuários vejam uma mensagem específica "novidades". Por exemplo, sua organização pode estar esperando para permitir que os usuários saibam de um recurso até que todos em sua organização sejam treinados nele.

![Captura de tela do Office What ' s New Preview com o painel de detalhes de um recurso aberto.](../media/whatsnew-officemgmt-preview.png)

Este recurso foi lançado pela primeira vez em novembro, mas há algumas atualizações de recursos que você deve conhecer: [Office What ' s New Management Preview updates Now Available](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-preview/ba-p/1020438)

### <a name="partners"></a>Parceiros

Howdy, parceiros! (Não foi possível ajudar). Também temos uma atualização para esse mês. Há um novo recurso que permite aos parceiros conceder aos clientes de CSP a opção de aceitar seu contrato de cliente da Microsoft (MCA) na seção **contas de cobrança** do centro de administração. Nesta nova experiência:

1. O cliente recebe um email de convite com um link para aceitar o relacionamento de parceiro e o MCA.
2. Depois que o cliente entrar, eles poderão exibir e aceitar as permissões MCA e parceiros no centro de administração.

### <a name="resource-mailboxes"></a>Caixas de correio de recurso

A lista de caixas de correio de recursos foi atualizada para o novo estilo. No centro de administração do Microsoft 365, acesse salas de **recursos** \> **& equipamento**.

### <a name="videos-training-and-docs-january"></a>Vídeos, treinamento e docs (Janeiro)

Confira o treinamento de administrador do Small Business que lançamos em janeiro:

- [Criar seu site de negócios](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9)
- [Encontre respostas e ajuda](https://support.microsoft.com/office/7f681212-c649-4a3e-a43b-32b1d1e58988)
- [Obter ajuda ou suporte](https://support.microsoft.com/office/18948a4c-3eb1-4b30-b1bc-a4cc29eb7655)
- [Excluir um usuário](https://support.microsoft.com/office/6bcdad7b-732a-4260-997a-8c176bc3d9d6)
- [Escolha uma assinatura da Microsoft](https://support.microsoft.com/office/b9f7c78e-430f-4117-89ec-2eeb1dced2ca)
- [Visão geral da segurança do Microsoft 365 para empresas](https://support.microsoft.com/office/3274b159-a825-46d7-9421-7d6e209389d1)

## <a name="november-and-december-2019"></a>Novembro e dezembro de 2019

Estamos combinando notícias de novembro e de dezembro porque, após o Ignite, tínhamos poucos anúncios a fazer. Veja você no ano novo!

### <a name="change-from-credit-card-to-invoice-payment"></a>Alterar do cartão de crédito para o pagamento da fatura

Começamos a distribuir a capacidade de alterar sua forma de pagamento do cartão de crédito para uma fatura. Vá para **cobrança** \> **de seus produtos**, selecione uma assinatura e, em seguida, selecione o link **Editar** ao lado do pagamento do cartão de crédito.

![Captura de tela: seção de cobrança do cartão de assinatura com um cartão de crédito como método de pagamento.](../media/MAC-BillingEditCreditCard.png)

Quer ler mais sobre ele? [Mudar de cartão de crédito ou conta bancária para fatura](../commerce/billing-and-payments/change-payment-method.md)

### <a name="global-reader"></a>Leitor global

Mencionamos a função de leitor global na [edição de outubro de 2019-Ignite](#october-2019---ignite-edition), mas à medida que ela é distribuída mais amplamente, vamos discutir alguns detalhes:

- A função de leitor global é a contraparte somente leitura para a função de administrador global. O leitor global pode ver tudo o que o administrador global tem permissão para fazer.
- Com algumas exceções, como alguns recursos de conformidade e segurança, os leitores globais têm acesso para exibir todos os centros de administração do Microsoft Cloud que sua organização está licenciado para usar.
- Atribua a função leitor global aos usuários que precisarem de planejamento, auditorias e investigações.
- Você também pode combinar a função leitor global com outra função que tenha menos permissões. Por exemplo, o proprietário de uma pequena empresa pode ter atribuído as funções do leitor global do **administrador de cobrança**  +   para que eles possam pagar as contas e permanecer na parte superior das alterações em sua organização na nuvem.
- Os leitores globais podem ir para qualquer página no centro de administração do Microsoft 365. Quando abrir uma página editável, haverá um aviso na parte superior informando que eles não têm permissão para salvar as alterações, e o botão salvar será desabilitado.

Adoraríamos obter seus comentários sobre a função de leitor global e qualquer uma das permissões baseadas em função que você gostaria de ver no futuro. [Fornecer comentários sobre permissões baseadas em função](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/10115430-have-a-consistent-experience-when-assigning-admin)

### <a name="new-settings-page"></a>Nova página de configurações

As páginas de **perfil da organização**, **segurança & privacidade** e **Serviços & suplementos** foram combinadas em uma página com três guias verticais. E a melhor parte, de um único local, agora você pode pesquisar todas as configurações.
![Captura de tela: página de configurações com o campo "Pesquisar todas as configurações" realçado na parte superior da página.](../media/MAC-SettingsMultiPivotSearch.png)

### <a name="training--docs"></a>Treinamento & docs

Esta seção é um novo recurso deste artigo, onde vamos começar a criar um novo treinamento e documentação que achamos que você achará interessante.

Em novembro, lançamos alguns caminhos de aprendizado para [o site do Microsoft Learn](https://docs.microsoft.com/learn/) para ajudar os profissionais de ti a aprender e a ser treinado no Microsoft 365. Faça o check-out:

- [Fundamentos da Microsoft 365](https://docs.microsoft.com/learn/paths/m365-fundamentals/)
- [Estender conceitos básicos do Office](https://docs.microsoft.com/learn/paths/extend-office-fundamentals/)
- [Microsoft 365 – modernizar sua implantação corporativa com o Windows 10 e o Microsoft 365 aplicativos para empresas](https://docs.microsoft.com/learn/paths/m365-getmodern/)
- [Gerenciar a implantação empresarial com o Microsoft 365](https://docs.microsoft.com/learn/paths/manage-enterprise-deployment-m365/)
- [Atualizar o Microsoft Office para TI em escala](https://docs.microsoft.com/learn/paths/m365-office-for-it/)
- [Entregar áreas de trabalho remotas e aplicativos do Azure com a área de trabalho virtual do Windows ](https://docs.microsoft.com/learn/paths/m365-wvd/)
- [Modernize seu local de trabalho com o Microsoft 365 e o Surface para Empresas](https://docs.microsoft.com/learn/paths/modernize-workplace-with-m365-and-surface/)
- [Proteger a identidade e o acesso com o Microsoft 365](https://docs.microsoft.com/learn/paths/m365-identity/)
- [Proteja as informações da empresa com o Microsoft 365](https://docs.microsoft.com/learn/paths/m365-information-protection/)
- [Gerenciar a segurança com o Microsoft 365](https://docs.microsoft.com/learn/paths/m365-security-management/)
- [Defesa contra ameaças com o Microsoft 365 defender](https://docs.microsoft.com/learn/paths/m365-security-threat-protection/)
- [Gerenciar a colaboração em equipe com o Microsoft Teams](https://docs.microsoft.com/learn/paths/m365-manage-team-collaboration/)
- [Colaborar com o SharePoint no Microsoft 365](https://docs.microsoft.com/learn/paths/m365-teams-sharepoint/)

## <a name="october-2019---ignite-edition"></a>Edição de outubro de 2019 Ignite

Bem-vindo à edição do Ignite do que há de novo no centro de administração do Microsoft 365! Obviamente, esta não é uma lista completa de comunicados, mas aqui estão alguns destaques. Além disso, confira os Blogs do Ignite para obter mais informações sobre as versões:

- [Administração – segurança, produtividade e aprimoramentos de rede para o Microsoft 365](https://techcommunity.microsoft.com/t5/Microsoft-365-Blog/ADMIN-Security-Productivity-and-Network-Enhancements-for/ba-p/964019).
- [O que há de novo no Microsoft Teams – Ignite 2020](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-New-in-Microsoft-Teams-Ignite-2019/ba-p/937025).

### <a name="role-based-access-control"></a>Controle de acesso baseado em função

Há muitas alterações para funções no centro de administração, pois começamos a ser distribuído em junho:

- **Compare Roles** -selecione até 3 funções para comparar as permissões de cada uma. Isso ajudará a localizar a função menos permissiva a ser atribuída aos usuários. Vá para **funções**, use a caixa de seleção de seleção múltipla na primeira coluna para escolher até 3 funções e selecione **comparar funções**.

    ![Comparando as funções de administrador do Exchange, administrador de assistência técnica e administrador do usuário.](../media/RBAC-CompareRoles.png)

- **Favoritos** -você pode adicionar uma estrela às suas funções favoritas ou mais usadas, para que possa encontrá-las facilmente classificando a coluna ou criando um filtro.
- **Usuários ativos**  >  **Manage Roles** -isso foi atualizado para alinhar-se às alterações nas funções. Da mesma forma que com a lista de funções, escopomos a lista padrão de funções para o mais útil, mas você pode ver todas as funções expandindo **Mostrar tudo por categoria**.
- **Função leitor global** -você pediu! Você chegou! A função [leitor global](add-users/about-admin-roles.md) !

### <a name="report-an-issue"></a>Relatar um problema

A integridade do serviço foi atualizada para o novo estilo e, se você for afetado por um problema que não está aparecendo no painel de integridade do serviço, é possível **relatar um problema** para permitir que a Microsoft saiba. Vá para   >  **integridade do serviço** de integridade.

### <a name="viral-subscriptions"></a>Assinaturas "viral"

Como você sabe, os usuários podem ativar assinaturas gratuitas para uma infinidade de produtos como o Power BI e o app Connect. Agora você pode ver as "assinaturas viral" que os usuários tentaram. Vá para **cobrança**  >  **de seus produtos**. Selecione o filtro de **tipo de conta** na guia assinaturas para ver as assinaturas adquiridas pelo usuário. Se necessário, agora você tem a capacidade de remover essas assinaturas da sua conta.

### <a name="user-templates"></a>Modelos do usuário

Os modelos permitem que você adicione facilmente muitos usuários salvando e reutilizando as configurações compartilhadas desses usuários. Você pode salvar valores para funções, licenças atribuídas, informações de contato, local e muito mais. Quando você usa o modelo para criar um novo usuário, ele obtém automaticamente o valor salvo para essas configurações. Vá para usuários ativos do **usuários**  >  e selecione **modelos de usuário** para experimentá-lo.

### <a name="office-whats-new-management-preview"></a>Gerenciamento de "novidades" do Office (visualização)

Quando um recurso importante do Office é lançado para um aplicativo do Office, os usuários receberão o cartão "What ' s New" para saber mais sobre o novo recurso. Se você não quiser que os usuários vejam o cartão, é possível ocultá-lo. Você também pode escolher quando deseja que os usuários vejam o cartão mostrando-o. Vá para **configurações**  >  **do Office o que é novo gerenciamento** para fazer o check-out.

### <a name="sharepoint-url-change"></a>Alteração de URL do SharePoint

Tecnicamente, esta não é a novidade do centro de administração do Microsoft 365 a ser avisada, mas estamos tão entusiasmados para que você veja esta notícia:
> [!IMPORTANT]
> Agora você pode acessar o seu centro de administração do SharePoint com uma URL regular: [https://admin.microsoft.com/SharePoint](https://admin.microsoft.com/SharePoint)

Para obter mais informações, consulte [What ' s New in the SharePoint Admin Center](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center).

## <a name="september-2019"></a>Setembro de 2019

Estamos nos estendendo para algumas versões incríveis de recursos no Ignite 2019, então estamos apenas anunciando alguns novos recursos lançados em setembro. Mas fique atento no artigo do próximo mês, ele será publicado no primeiro dia de Ignite!

### <a name="featured-feedback-fix--the-option-to-convert-the-deleted-users-mailbox-to-a-shared-mailbox-is-back"></a>Correção de comentários em destaque – a opção de converter a caixa de correio do usuário excluído em uma caixa de correio compartilhada está de volta

Ouvimos seus comentários com voz alta e desmarcada e recolocamos a capacidade de permitir que outra pessoa acesse a caixa de correio de um usuário excluído, convertendo-o em uma **caixa de correio compartilhada**. Adicionar isso novamente ao assistente de exclusão de usuário permite que você decida o que fazer com os dados:

- Email: conceda a outra pessoa acesso à caixa de correio do usuário excluído, convertendo-a em uma caixa de correio compartilhada.
- Arquivos: salvar seus arquivos do OneDrive e conceder a alguém acesso a outras pessoas.
- Permissões: remover permissões se outras pessoas tivessem acesso a essa caixa de correio.
- Aliases: remover aliases de email para que eles fiquem disponíveis para uso de outro usuário imediatamente.
![Captura de tela: excluir o assistente de usuário com aliases de email, permissões, OneDrive e opções de email exibidas](../media/WhatsNew-DeleteUserWiz.png)

### <a name="initial-setup"></a>Configuração inicial

Há uma atualização para outro dos nossos assistentes de instalação inicial: Microsoft 365 for Business. As etapas foram otimizadas e movemos duas das tarefas de configuração para a página de instalação:

- **Proteger computadores Windows 10** -configurar políticas para proteger melhor seus dispositivos Windows 10 contra vírus, malware e ataques por hackers.
- **Instalar automaticamente o Office** -quando você ativar essa opção e os usuários tiverem conectado seus computadores ao Microsoft 365 Business, seus computadores serão atualizados automaticamente para os aplicativos do Office mais recentes e permanecerão atualizados.

## <a name="august-2019"></a>Agosto de 2019

### <a name="billing"></a>Cobrança

Temos algumas atualizações para cobrança e assinaturas neste mês:

- Assinaturas baseadas em dispositivo: você pode atribuir ou cancelar a atribuição **de licenças do microsoft 365 Apps for Education (Device)** a dispositivos no centro de administração do Microsoft 365. **O Microsoft 365 Apps for Education (dispositivo)** é uma licença complementar que lhe permitirá atribuir uma licença a um dispositivo. Vá para **cobrança** de  >  **seus produtos** para encontrar e comprar a licença.
- Gerenciamento de licença baseado em usuário: atualizamos o modo como você atribui licenças aos usuários ativos de **usuários**  >   para o novo estilo. Para saber mais, confira:
  - [Atribuir licenças a usuários](manage/assign-licenses-to-users.md)
  - [Cancelar licenças de usuários](manage/remove-licenses-from-users.md)

### <a name="setup-page-updates"></a>Configurar atualizações de página

Agora, a instalação tem categorias e seções, incluindo uma seção **recomendada para você** , onde sugerimos de forma inteligente a próxima etapa para ativar os recursos e configurar sua organização. Também adicionamos um novo recurso para configurar:

- **Microsoft defender para office 365** -se sua organização está licenciada para usar o Microsoft defender para Office 365 e você ainda não a configurou ou a ativou, você verá esta página. Vá para **configuração** para experimentá-lo.

### <a name="report-an-issue-august"></a>Relatar um problema (agosto)

Se você for afetado por um problema que não está aparecendo no painel de integridade do serviço, o recurso **relatar um problema** lhe fornecerá uma maneira rápida e fácil de nos informar. Vá para   >  **integridade do serviço** de integridade.

## <a name="july-2019"></a>Julho de 2019

### <a name="message-center"></a>Centro de mensagens

O centro de mensagens foi atualizado para o novo design e parece incrível!

![Captura de tela: centro de mensagens atualizado com a guia "todas as mensagens ativas" selecionada e o menu de filtro aberto.](../media/MAC-MessageCenterUpdated.png)

- Agora você pode exibir **mensagens por status**. Basta selecionar uma das guias: **todas as mensagens ativas**, **alta prioridade**, **mensagens não lidas** e **mensagens descartadas**.
- Você também pode filtrar por **privacidade de dados** de categoria, **planejar alterações**, **impedir ou corrigir problemas** e manter categorias de mensagens **informadas** .
- Selecione uma mensagem na lista e tenha algumas opções na barra de comandos: **descartar**, **Marcar como lida** ou **Marcar como não lida** ou **compartilhar**.
- E ao abrir uma mensagem, você tem ainda mais opções:
  - Copie um link da mensagem para a área de transferência para salvá-lo para mais tarde ou para compartilhá-lo com colegas.
  - Marcar mensagens como **lidas** ou não **lidas**.
  - Faça comentários sobre uma mensagem selecionando **como** ou **não, um painel de comentários** é aberto solicitando que você forneça comentários específicos sobre o que você gostou ou não gostou sobre esta mensagem.

### <a name="navigation-pane-intelligence"></a>Inteligência do painel de navegação

 Agora, o painel de navegação lembra suas últimas ações e mostra o painel no último estado em que você o deixou. Ele também fará com que itens usados com frequência fiquem visíveis por padrão.

### <a name="initial-setup--the-setup-page"></a>Instalação inicial & página de configuração

Temos algumas alterações empolgantes para ajudá-lo a configurar sua organização. Primeiro, vamos discutir a diferença entre a **configuração** e a **página de configuração**. A **instalação** refere-se ao assistente de instalação inicial que você usou para se conectar aos serviços online da Microsoft. Isso geralmente inclui três etapas específicas: **Conecte um domínio**, **adicione usuários** e **Baixe os aplicativos do Office**. A **página de configuração** é a página no centro de administração que recomendava configurar tarefas para garantir que você esteja obtendo o máximo de suas assinaturas, como ativar os recursos para os quais comprou licenças.

- **Instalação** : o assistente de configuração inicial foi atualizado para assinaturas do **Microsoft 365 for Business** . Esse novo design ajudará as novas organizações a obter o assistente mais rapidamente e com um sucesso maior.
- **Página de instalação** -a página de **configuração** ajuda você a concluir a configuração e a proteção dos serviços que vêm com suas assinaturas. Você também pode ver quaisquer recomendações descartadas na página de **configuração** . Para ver se ele está disponível para suas assinaturas ainda, vá para a instalação do **centro de administração do 365 da Microsoft**  >  .

### <a name="billing--subscriptions"></a>Cobrança & assinaturas

- Tipo de produto de **software** – agora você pode exibir produtos de software adquiridos por meio de um provedor de serviços de nuvem (CSP). Para ver seus downloads e chaves, vá para **cobrança**  >  **da**  >  guia **software** de produtos.
- Você pode exibir os produtos e serviços modernos do Azure no centro de administração do Microsoft 365, se você os comprou da Microsoft ou de um provedor de terceiros. Exemplos de produtos modernos do Azure incluídos:
  - Instâncias virtuais do Azure reservadas
  - Planos de suporte do Azure
  - Benefícios de uso híbrido do Azure (AHUB)
  - Gerenciar aplicativos
  - Serviços de dispositivos
  - Assinaturas do Azure

### <a name="simplify-multi-factor-authentication"></a>Simplificar a autenticação multifator

Os administradores têm acesso a informações confidenciais em sua organização. Exija que todos os administradores usem a autenticação multifator ao entrar. O novo assistente o ajuda a fazer isso com apenas uma etapa. Para experimentar, vá para **a configuração**  >  **reforçar a segurança de entrada**.

### <a name="users"></a>Usuários

As páginas **usuários excluídos** e **usuários convidados** foram atualizadas para o novo estilo.

- **Usuários convidados**: Adicione usuários convidados convidando-os a exibir ou compartilhar arquivos do SharePoint ou do onedrive. Você pode exibir os usuários convidados de usuários convidados dos **usuários**  >  .
- **Usuários excluídos**: na página **usuários atualizados excluídos** , você pode fazer todas as ações que você poderia no centro de administração mais antigo, mas agora adiciona e remove colunas. E temos muitas opções de coluna para escolher. Na verdade, são as mesmas colunas que você pode escolher na página **usuários ativos** .

## <a name="june-2019"></a>Junho de 2019

### <a name="featured-feedback-request---dark-mode"></a>Solicitação de comentários de destaque-modo escuro

A exibição do centro de administração no modo escuro está em visualização! Você pode testá-lo apenas na **Home** Page no momento. Na **Home** Page, o botão **modo escuro** está na barra de comandos ao lado do link **What ' s New** .

### <a name="roles-management"></a>Gerenciamento de funções

No final de junho, começamos a implantar a nova maneira de gerenciar funções de administrador. Quando estiver disponível para você, vá para funções de **funções**  >  . Até lá, vamos dar uma olhada: é incrível!
<br> ![Captura de tela: lista de funções de administrador com o painel de detalhes função de administrador de usuário realçada.](../media/MAC-AdminRoles-Featured.png) <br>

Essa nova experiência facilita a visualização de quem tem permissões de administrador e a atribuição de funções que concedem o nível certo de acesso aos seus administradores. Além disso, adicionamos mais funções do Azure AD para que você não perca tempo indo para vários centros de administração.
O que mais você pode fazer aqui?

- Exporte uma lista de todos os administradores da sua organização aos quais as funções do Azure Active Directory estão atribuídas no Microsoft 365.  
- Exibir todos os administradores atribuídos a uma função específica, adicionar ou remover administradores de uma função específica, procurar funções por nome e palavra-chave e saber mais sobre o que cada função permite que um usuário faça.
- Pesquise rapidamente por uma função específica e crie filtros.

### <a name="payment-method"></a>Método de pagamento

Atualizamos o modo como você paga por suas assinaturas. Acesse os métodos de pagamento **de faturas**  >  **& pagamentos**  >  . Você pode ver seus métodos de pagamento em um modo de exibição de lista. Selecione qualquer item na lista para removê-lo, editá-lo e, facilmente, ver a assinatura à qual o método de pagamento está associado.

## <a name="may-2019"></a>Maio de 2019

### <a name="mays-featured-fix---case-sensitivity"></a>Correção de maiúsculas e minúsculas de maio

Agora, quando você procura caixas de correio compartilhadas, contatos, recursos e permissões de caixa de correio, seus termos de pesquisa não precisam diferenciar maiúsculas de minúsculas.

**Gerenciamento de usuários e grupos** Este mês, atualizamos o **usuário bloquear**, **Redefinir senha**, exibição de lista de **contatos** , exibição de lista de **grupos** e as páginas de detalhes de **grupos** para o novo estilo de centro de administração.

- Com o novo modo de exibição de lista de **grupos** , você obtém dados mais ricos sobre seus grupos e pode personalizar a maneira como você vê seus dados – e a lista de grupos lembra como deseja ver seus dados. Por exemplo, agora você pode filtrar **grupos com o Teams** para ver se seus grupos fazem parte de uma equipe e você pode adicionar a coluna **status do teams** .
- A lista de grupos também traz todos os aprimoramentos que fizemos na experiência de lista no gerenciamento de usuários, incluindo ações rápidas e a barra de comandos contextual.

**Recomendações**<br>
Você pode ver um novo pop-up de recomendação em seu centro de administração, que acabamos de adicionar 4 novos. Naturalmente, você só verá recomendações se achar que ela será beneficiada pela sua organização. Mas não espere até mostrarmos a recomendação-você pode adicioná-lo a partir da biblioteca de cartões.

- **Expiração da senha** -recomendamos que as senhas sejam definidas para **nunca expirar**. Se sua organização tiver uma configuração diferente, você poderá apenas ver essa recomendação.
- **Muitos administradores globais** – como ter muitos administradores globais é uma ameaça de segurança, se você tiver mais de quatro administradores globais, verá essa recomendação. Sugerimos dar aos usuários apenas o acesso que eles precisam para realizar o trabalho.
- **Proteção de dispositivo do Intune** – se suas licenças incluem o Intune e detectamos que você não concluiu a configuração do Intune ou inscreveu seus dispositivos, recomendamos que você crie uma política do Intune para proteger os arquivos da sua organização quando os usuários os acessam de seus dispositivos móveis.
- **Obter atualizações mensais dos recursos do Office** – obtemos comentários de nossos pequenos clientes que quando recebem atualizações mensais dos recursos do Office, seus usuários estão mais felizes. Portanto, se você é um negócio muito pequeno e você atualmente Obtém as atualizações de recursos do Office a cada seis meses, verá essa recomendação.

**Settings** <br>
Quanto às configurações, há algumas alterações. Principalmente, apenas a atualização das configurações existentes para o novo estilo de centro de administração. À medida que estamos avançando e adicionamos novas configurações que você nunca viu antes, vamos começar a menciona-las aqui. E temos uma configuração completa para anunciar: **autenticação moderna**. Sim, há uma nova configuração para ativar a **autenticação moderna**! Para fazer o check-out, acesse serviços de **configurações**  >  **&** a  >  **autenticação moderna** dos suplementos.

## <a name="april-2019"></a>Abril de 2019

As coisas estão com uma ótima aparência para o centro de administração. Estamos lendo seus comentários e sugestões, respondendo a maioria deles e realmente tirando tudo o que você tem para dizer ao coração. Naturalmente, ainda estamos fazendo o trabalho para garantir que tudo esteja em paridade com o antigo centro de administração. E lembre-se de que, à medida que os novos recursos são distribuídos, você não pode obtê-lo imediatamente.

### <a name="featured-feature---add-users"></a>Recurso de destaque-adicionar usuários

Para abril, estamos apresentando o assistente para **Adicionar usuário** que orienta você por meio de... Aguarde... adição de usuários. Ele é um passo a passo para adicionar as informações básicas do usuário, como o nome de exibição e email, atribuindo uma licença e uma função, adicionando suas informações de contato e, em seguida, examinando a conta do usuário antes de confirmar. **Por que fizemos essa alteração?** Ouvimos seus comentários que você não gostou da rolagem quase infinita para adicionar usuários na experiência anterior.
<br> ![Captura de tela do assistente de adição de usuário.](../media/MAC-AddUserWizard.png) <br>

Há duas maneiras de fazer o check-out: <br>

1. Na página **inicial** , selecione **Adicionar usuário** na placa de **Gerenciamento de usuários** . O assistente é aberto imediatamente para que você não precise navegar de qualquer trabalho que esteja fazendo na página **inicial** .
2. Vá para usuários ativos do **usuários**  >  e selecione **Adicionar usuário** na barra de comandos.
<br><br>

Fizemos mais algumas alterações no **Gerenciamento de usuários**, aqui está uma lista rápida:

- O painel **gerenciar funções** foi atualizado para o novo estilo e está acessível. Também atualizamos o **usuário em bloco** e **excluímos** os painéis do usuário para o novo estilo.
- **Gerenciar licenças de produtos** alteração de posição na barra de comandos.
- Agora, alterar a foto de um usuário é mais fácil. Em **usuários ativos** , selecione um usuário e **altere a foto** sob sua imagem.

### <a name="but-wait-theres-more"></a>Mas espere! Há mais

- Há uma nova faixa de instalação na **Home** Page que você verá se não tiver concluído as etapas de configuração, como adicionar um domínio, adicionar usuários e baixar aplicativos do Office.
- A lista de **grupos** e o painel de detalhes foram atualizados para o novo estilo. Vá para   >  **grupos** de grupos para exibir as alterações.
  - Falando sobre grupos, também adicionamos uma guia **do Microsoft Teams** ao painel de detalhes de grupos, onde você pode transformar qualquer grupo do Microsoft 365 em uma equipe. Para "teamify" um grupo selecione qualquer grupo do Microsoft 365 na lista, selecione a guia **Microsoft Teams** e, em seguida, **criar equipe**. Se o grupo já for uma equipe, você receberá um link para gerenciá-lo no centro de administração do Microsoft **Teams**.
  - Por fim, você pode adicionar o **status do teams** à lista de **grupos** . No cabeçalho da coluna, selecione **escolher colunas**  >  **Teams status**  >  **salvar**.
- **Novas funções de administrador limitadas** – lançamos algumas novas funções de administrador para que você possa fornecer aos usuários somente o acesso de que precisam.
  - **Administração do Kaizala**: os usuários desta função têm permissão para executar todas as tarefas de gerenciamento no Microsoft Kaizala, incluindo criar e gerenciar usuários no diretório do Kaizala, gerenciar grupos do Kaizala, gerenciar cartões de ação e conectores e criar solicitações de serviço.
  - **Administração de pesquisa**: os usuários desta função têm acesso total a todos os recursos de gerenciamento de pesquisa da Microsoft no centro de administração do Microsoft 365. Os administradores de pesquisa podem delegar as funções de administrador de pesquisa e editor de pesquisa aos usuários, e criar e gerenciar conteúdo, como indicadores, Q&itens e locais. Além disso, esses usuários podem exibir o centro de mensagens, monitorar a integridade do serviço e criar solicitações de serviço.
  - **Editor de pesquisa**: os usuários nessa função podem criar, gerenciar e excluir conteúdo para o Microsoft Search no centro de administração do Microsoft 365, incluindo indicadores, Q&itens e locais.
- Há uma Bonanza de alterações de **cobrança** neste mês...
  - Agora você pode atualizar o CVV para cartões de crédito existentes sem precisar excluí-lo e adicioná-lo novamente. Você pode atualizar o CVV indo até **Bills**  >  **Payment Methods**.
    - Tornamos mais fácil localizar suas **faturas** e compreender qualquer problema de cobrança que sua conta pode estar tendo. E agora você pode ver suas listas no navegador da Web em vez de precisar baixar o PDF. Vá para   >  **faturas** de faturas.
    - Na página **seus produtos** , agora agregamos suas informações de assinatura se você tiver várias assinaturas do mesmo tipo.

## <a name="march-2019---weve-officially-released-the-admin-center"></a>Março de 2019 – lançamos oficialmente o centro de administração

Bem, se você perdeu as notícias empolgantes, oficialmente lançamos o novo e aprimorado centro de administração do Microsoft 365! Aqui está a postagem de blog onde anunciamos: [o novo centro de administração 365 da Microsoft disponível atualmente](https://techcommunity.microsoft.com/t5/Microsoft-365-Blog/The-new-Microsoft-365-admin-center-available-today/ba-p/377870). Em março, vamos confiar na postagem de blog para que você confira os recursos lançados-mais, você também pode ler a postagem dos recursos que estão sendo lançados em um futuro próximo, que não podemos fazer no conteúdo principal.
<br> ![Captura de tela da página inicial do centro de administração do Microsoft 365.](../media/M365AC-HomePage.png) <br>
Temos uma alteração na área de **cobrança & assinaturas** que gostaríamos de mencionar. Quero dizer, o y'all não achamos que nós fizemos o melhor aprimoramento. Porque não estamos! Na verdade, este mês adicionamos a capacidade de gerenciar suas relações de parceiros para **cobrança** de  >  **contas de cobrança**. A partir daqui, você pode revisar as relações de parceria entre o supervisor, o CSP e os revendedores indiretos. Você também pode aceitar novas solicitações de relacionamento de parceiros, incluindo permissões de administrador delegadas.

Como sempre, seus comentários são importantes para nós, portanto, vamos mantê-los chegando! Em qualquer página no centro de administração, você pode fazer comentários selecionando **enviar comentários** no canto inferior direito, ao lado de **precisar de ajuda?**

## <a name="february-2019---billing--subscriptions-edition"></a>Versão de fevereiro de 2019-faturamento & edição de assinaturas

Este mês, vamos nos concentrar em todos os aprimoramentos que fizemos nas áreas Affectionately referenciadas como "cobranças e assinaturas". No passado, você provavelmente não fez referência a essas coisas Affectionately, mas achamos que agora você vai...

- **Métodos de pagamento** : ouvimos seus comentários que a atualização de seu método de pagamento era difícil e fizemos muitas alterações em torno dele. Vá para   >  **métodos de pagamento** de cobrança. Você pode ver facilmente os métodos de pagamento, como o cartão Visa e a qual assinatura está associada. Na lista de métodos de pagamento, selecione o menu **mais** (3 pequenos pontos ao lado da data de vencimento) e, em seguida, selecione **Exibir assinaturas**. Você também pode editar e excluir seus métodos de pagamento usando o menu **mais** .
- **Conta de cobrança** – os clientes do lançamento direcionado verão primeiro a página da nova conta de cobrança e, em seguida, iremos revertê-la em todo o mundo. Quando estiver disponível para você, acesse a   >  **conta de cobrança** de cobrança. O que você pode fazer na página nova conta de cobrança? Estou feliz por você ter perguntado:
  - Atualize o endereço e outras informações de contato em seu perfil organizacional diretamente desta página. Não é necessário acessar o perfil de organização de **configurações**  >  , a menos que você queira.
  - E estamos facilitando a vida dos clientes de licenciamento por volume ou diretos, você pode aceitar e revisar os contratos de clientes de **contas de cobrança**. Você também pode se conectar com outros organizações expandidas permitindo que você vincule o organizações expandidas para compartilhar licenças e recursos.
- Também fizemos alguns aprimoramentos menores e correções de erros:
  - Reativar uma assinatura com um pagamento de fatura
  - Editar o endereço de uso do serviço para suas assinaturas
  - E, na página detalhes de inventário, adicionamos alguns aprimoramentos de notificação, nós nos vinculamos à página real onde você pode fazer o trabalho, e há mais ações no cartão de detalhes de inventário. Vá para títulos de **cobrança**  >    >  **Exibir detalhes** em qualquer fatura.

## <a name="january-2019---happy-new-year"></a>Janeiro de 2019-feliz ano novo

- Ainda adicionando em **serviços & suplementos** , atualizamos mais das **configurações do > Services & Add-ins** . Experimente aplicativos integrados ou relatórios para ver a versão mais recente.
- **Procurando melhorias?** Não veja mais a caixa de **pesquisa** na barra de comandos. Ele foi atualizado para permitir que você pesquise tarefas. Por exemplo, tente "redefinição de senha" ou "adicionar um usuário".

### <a name="featured-feedback-fix---licenses-and-apps"></a>Correção de comentários em destaque-licenças e aplicativos

Recombinamos **licenças e aplicativos** no painel de detalhes do usuário com base em seus comentários. Inicialmente, separamos os dois recursos para fornecer espaço para os detalhes de todas as possibilidades de licença e de todos os aplicativos. Ouvimos que separar licenças e aplicativos em dois painéis adicionou confusão. Escutamos e colocamos as licenças e os aplicativos novamente em uma guia. Agora você pode certificar-se de que um aplicativo está desativado em todas as licenças atribuídas a um usuário em um painel. Leite e cookies. Licenças e aplicativos. Podemos obtê-lo agora.

Confira: **usuários > usuários ativos > editar** ou **adicionar licenças e aplicativos de > de usuário**
