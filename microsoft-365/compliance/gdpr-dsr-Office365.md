---
title: Solicitações do Titular dos Dados do Office 365 no RGPD e CCPA
description: Entenda os direitos do usuário de acordo com o RGPD e CCPA e como o Office 365 ajuda as empresas a encontrar dados e a agir sobre eles em resposta às DSRs.
keywords: Office 365, DSR, Microsoft 365, Microsoft 365 Education, documentação do Microsoft 365, RGPD, CCPA
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: bedce9c71e18749d6a394af17788e07ce79c2820
ms.sourcegitcommit: a418195dc11e6251ae37e788c102bbaa7087e44e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2020
ms.locfileid: "44579266"
---
# <a name="office-365-data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitações de assunto de dados do Office 365 para o GDPR e o CCPA

## <a name="introduction-to-dsrs"></a>Introdução às DSRs

O [Regulamento Geral de Proteção de Dados da União Europeia (RGPD)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) concede direitos a pessoas (conhecidas no regulamento como *entidades de dados*) para gerenciar os dados pessoais que foram coletados por um empregador ou outro tipo de agência ou organização (conhecido como *controlador de dados* ou apenas *controlador*). Os dados pessoais são definidos de forma ampla no âmbito do RGPD como qualquer dado relacionado a uma pessoa natural identificada ou identificável. O RGPD concede às entidades de dados direitos específicos sobre seus dados pessoais; esses direitos incluem a obtenção de cópias, a solicitação de correções, a restrição do processamento e a exclusão de dados pessoais, ou o seu recebimento em formato eletrônico para que possam ser transferidos para outro controlador. Um pedido formal de uma entidade de dados a um controlador para efetuar uma ação nos seus dados pessoais é chamado de *Solicitação de Entidade de Dados* ou DSR. O controlador é obrigado a considerar prontamente cada DSR e fornecer uma resposta substantiva, seja tomando a ação solicitada, seja fornecendo uma explicação do por que a DSR não pode ser recebida pelo controlador. Os controladores devem consultar seus próprios consultores legais ou de conformidade com relação às medidas adequadas para qualquer DSR.

Da mesma forma, a Lei de Privacidade do Consumidor da Califórnia (CCPA), fornece direitos e obrigações de privacidade aos consumidores da Califórnia, incluindo direitos semelhantes aos Direitos do Titular dos Dados do GDPR, como o direito de excluir, acessar e receber (portabilidade) suas informações pessoais. O CCPA também fornece certas divulgações, proteções contra discriminação ao eleger direitos de exercício e requisitos de "aceitação/recusa" para determinadas transferências de dados classificadas como "vendas". As vendas são amplamente definidas para incluir o compartilhamento de dados para uma consideração valiosa. Para obter mais informações sobre o CCPA, confira a [Lei de Privacidade do Consumidor da Califórnia](offering-ccpa.md) e as [Perguntas Frequentes Sobre a Lei de Privacidade do Consumidor da Califórnia](ccpa-faq.md).

O guia aborda como usar produtos, serviços e ferramentas administrativas do Office 365 para ajudá-lo a encontrar e a trabalhar com dados pessoais ou informações pessoais para responder ao DSRs. Especificamente, isso inclui como localizar, acessar e atuar em dados pessoais ou informações pessoais que estão na nuvem da Microsoft. Veja a seguir uma visão geral rápida dos processos descritos neste guia:

- **Descobrir** – use ferramentas de pesquisa e descoberta para localizar dados pessoais que possam ser a entidade de uma solicitação DSR. Após a coleta dos documentos que atendem à solicitação, você pode executar uma ou mais das ações de DSR a seguir para responder à solicitação. Como alternativa, você pode determinar que a solicitação não atende às diretrizes da sua organização para responder a DSRs.
- **Acesso:** recupere dados pessoais que residem na nuvem da Microsoft e, se solicitado, faça uma cópia para disponibilizar para o titular dos dados.
- **Retificação:** faça alterações ou implemente outras ações solicitadas nos dados pessoais, onde for possível.
- **Restringir:** restrinja o processamento de dados pessoais, removendo licenças de vários serviços em nuvem da Microsoft ou desativando os serviços desejados sempre que possível. Você também pode remover dados da nuvem da Microsoft e retê-los localmente ou em outro lugar.
- **Exclusão:** remova permanentemente os dados pessoais que residem na nuvem da Microsoft.
- **Exportar/Receber (Portabilidade): ** forneça uma cópia eletrônica (em formato legível para computador) de dados pessoais ou informações pessoais para o titular dos dados. Os dados pessoais do CCPA são quaisquer informações relacionadas a uma pessoa, identificável ou não. Não há distinção entre as funções pública, privada ou de trabalho de uma pessoa. O termo definido "informações pessoais" se alinha aproximadamente aos "dados pessoais" do RGPD. No entanto, o CCPA também inclui dados da família e do domicílio. Para obter mais informações sobre o CCPA, confira a [Lei de Privacidade do Consumidor da Califórnia](offering-ccpa.md) e as [Perguntas Frequentes Sobre a Lei de Privacidade do Consumidor da Califórnia](ccpa-faq.md).

### <a name="terminology"></a>Terminologia

Veja a seguir as definições dos termos do RGPD que são relevantes para este guia.

- **Controlador:** a pessoa física ou jurídica, autoridade pública, órgão ou outra entidade que, sozinha ou em conjunto com terceiros, determina os fins e os meios do processamento de dados pessoais, onde tais fins e meios são determinados por lei da União ou Estado-Membro, o controlador ou os critérios específicos para sua indicação podem ser fornecidos por lei da União ou Estado-Membro.
- **Dados pessoais e titular dos dados:** qualquer informação relativa a uma pessoa natural identificada ou identificável (“titular dos dados”); uma pessoa natural identificável é aquela que pode ser identificada, direta ou indiretamente, especialmente por referência a um identificador, como nome, um número de identificação, dados de localização, um identificador online ou um ou mais fatores específicos de natureza física, fisiológica, genética, mental, econômica, cultural ou social dessa pessoa natural.
- **Processador:** uma pessoa física ou jurídica, autoridade pública, órgão ou outra entidade que processa dados pessoais em nome do controlador.
- **Dados do cliente:** Todos os dados, incluindo todos os arquivos de texto, som, vídeo ou imagem e software, fornecidos à Microsoft por um cliente, em nome de um cliente ou por meio do uso do serviço corporativo. Os Dados do Cliente incluem tanto (1) informações identificáveis de usuários finais (por exemplo, nomes de usuário e informações de contato no Active Directory do Azure) quanto Conteúdo do Cliente para o qual o cliente carrega arquivos ou que é criado em serviços específicos (por exemplo, conteúdo do cliente em um documento de Word ou Excel, ou no texto de um email do Exchange Online; conteúdo do cliente adicionado a um site do SharePoint Online ou salvo em uma conta do OneDrive for Business).
- **Logs gerados pelo sistema:** logs e dados relacionados gerados pela Microsoft que ajudam a Microsoft a fornecer serviços corporativos aos usuários. Os logs gerados pelo sistema contêm principalmente dados pseudonimizados, como identificadores exclusivos — normalmente, um número gerado pelo sistema não pode, por si só, identificar uma pessoa individual, mas é usado para fornecer os serviços corporativos aos usuários. Os logs gerados pelo sistema também podem conter informações identificáveis sobre os usuários finais, como um nome de usuário.

### <a name="how-to-use-this-guide"></a>Como usar este guia

Para ajudar você a encontrar informações relevantes ao seu caso de uso, este guia está dividido em quatro partes.

- **[Parte 1: Respondendo a DSRs para Dados do Cliente](#part-1-responding-to-dsrs-for-customer-data):** *Dados do Cliente* são dados produzidos e armazenados no Office 365 nas operações diárias da sua empresa. Exemplos de aplicativos mais usados do Office 365 que permitem a criação de dados incluem Word, Excel, PowerPoint, Outlook e OneNote. O Office 365 também consiste em aplicativos como o SharePoint Online, Teams e Forms, que permitem uma melhor colaboração com outras pessoas. A Parte 1 deste guia discute como descobrir, acessar, retificar, restringir, excluir e exportar dados de aplicativos do Office 365 que tenham sido usados para criar e armazenar dados em serviços online do Office 365. Ela aborda produtos e serviços para os quais a Microsoft atua como um processador de dados para sua organização e, portanto, o recurso de DSR é disponibilizado para o administrador do locatário.
- **[Parte 2: Respondendo a DSRs relacionadas aos Insights Gerados pelo Office 365](#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365):** O Office 365 fornece certos insights por meio de serviços como o Delve, o MyAnalytics e o Workplace Analytics. Como esses insights são gerados e como responder a DSRs relacionadas a eles é explicado na Parte 2 deste guia.
- **[Parte 3: Respondendo a DSRs para logs gerados pelo sistema](#part-3-responding-to-dsrs-for-system-generated-logs):** Quando você usa os serviços corporativos do Office 365, a Microsoft gera algumas informações, como logs de serviço que registram o uso ou o desempenho dos recursos nos serviços online. A maioria dos dados gerados pelo serviço contém identificadores pseudônimos gerados pela Microsoft e, portanto, essa categoria é geralmente referida neste documento como *logs gerados pelo sistema*. Embora esses dados não possam ser atribuídos a uma entidade de dados específica sem o uso de informações adicionais, alguns deles podem ser considerados pessoais de acordo com a definição do RGPD para "dados pessoais". A Parte 3 deste guia discute como acessar, excluir e exportar logs gerados pelo sistema.
- **[Parte 4: Recursos adicionais para ajudá-lo com as DSRs](#part-4-additional-resources-to-assist-you-with-dsrs):** A Parte 4 deste guia lista cenários limitados em que a Microsoft é o controlador de dados quando determinados produtos e serviços do Office 365 são usados.

>[!NOTE]
>Na maioria dos casos, quando os usuários em sua organização usam serviços e produtos do Microsoft Office 365, você é o controlador de dados e a Microsoft é o processador. Como um controlador de dados, você é responsável por responder ao titular dos dados diretamente. Para ajudar com isso, as Partes 1 a 3 deste guia detalham os recursos técnicos disponíveis para sua organização responder a uma solicitação DSR. No entanto, em alguns cenários limitados, a Microsoft será o controlador de dados quando as pessoas usarem determinados produtos e serviços do Office 365. Nesses casos, as informações na Parte 4 fornecem orientação sobre como os titulares de dados podem enviar solicitações DSR à Microsoft.

### <a name="office-365-national-clouds"></a>Nuvens nacionais do Office 365

Os serviços do Microsoft Office 365 também estão disponíveis nos seguintes ambientes de nuvem nacional: [Office 365 Germany](https://docs.microsoft.com/microsoft-365/admin/admin-overview/learn-about-office-365-germany), [Office 365 operado pela 21Vianet (China)](https://docs.microsoft.com/microsoft-365/admin/services-in-china/services-in-china) e [Office 365 US Government](https://www.microsoft.com/microsoft-365/government/compare-office-365-government-plans). A maioria das diretrizes para gerenciar solicitações de titulares de dados descritas neste artigo se aplica a esses ambientes de nuvem nacional. No entanto, devido à natureza isolada desses ambientes, há algumas exceções. Quando considerável para determinado subseção, essas exceções são destacadas em uma observação correspondente.

### <a name="hybrid-deployments"></a>Implantações híbridas

Sua organização pode consistir em ofertas da Microsoft que são uma combinação de serviços baseados em nuvem e produtos de servidor local. Em geral, uma implantação híbrida é o compartilhamento de contas de usuário (gerenciamento de identidades) e recursos (como caixas de correio, sites e dados) que existem na nuvem e localmente. Cenários híbridos comuns incluem:

- Implantações híbridas do Exchange, em que alguns usuários têm uma caixa de correio local e outros usuários têm caxas de correio do Exchange Online.
- Implantações híbridas do SharePoint, em que servidores de sites e arquivos são locais, e contas do OneDrive for Business estão no Office 365.
- O sistema de gerenciamento de identidade local (Active Directory) que é sincronizado com o Azure Active Directory, que é o serviço de diretório no Office 365.

Ao responder a uma solicitação de DSR, talvez você precise determinar se os dados em resposta a uma solicitação de DSR estão na nuvem da Microsoft ou em sua organização local e executar as etapas apropriadas para responder à solicitação. O Guia de Solicitação de Titular de Dados do Office 365 (este guia) fornece diretrizes para responder a dados baseados na nuvem. Para obter diretrizes para os dados em sua organização local, confira [RGPD para servidores locais do Office](https://docs.microsoft.com/Office365/Enterprise/gdpr-for-office-servers).

## <a name="part-1-responding-to-dsrs-for-customer-data"></a>Parte 1: Responder às DSRs para Dados do Cliente

As diretrizes para responder às DSRs para Dados do Cliente estão divididas nas quatro seções a seguir:

- [Usar a ferramenta Descoberta Eletrônica de Pesquisa de Conteúdo para responder às DSRs](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)
- [Usar a funcionalidade no aplicativo para responder às DSRs](#using-in-app-functionality-to-respond-to-dsrs)
- [Responder às solicitações de retificação de DSR](#responding-to-dsr-rectification-requests)
- [Responder às solicitações de restrição de DSR](#responding-to-dsr-restriction-requests)

### <a name="how-to-determine-the-office-365-applications-that-may-be-in-scope-for-a-dsr-for-customer-data"></a>Como determinar os aplicativos do Office 365 que podem estar no escopo de uma DSR para Dados do Cliente

Para ajudá-lo a determinar onde procurar dados pessoais ou o que pesquisar, ele ajuda a identificar os aplicativos do Office 365 que as pessoas em sua organização podem usar para criar e armazenar dados no Office 365. Saber isso restringe os aplicativos do Office 365 que estão no escopo de uma DSR e ajuda a determinar como pesquisar e acessar dados pessoais relacionados a uma DSR. Especificamente, isso significa se você pode usar a ferramenta Pesquisa de Conteúdo ou se deve usar a funcionalidade do aplicativo em que os dados foram criados.

Uma maneira rápida de identificar os aplicativos do Office 365 que as pessoas na sua organização estão usando para criar Dados do Cliente é determinar quais aplicativos estão incluídos na assinatura do Microsoft 365 para empresas da sua organização. Para fazer isso, você pode acessar as contas de usuário no portal de administração do Office 365 e analisar as informações de licenciamento de produto. Confira [Atribuir licenças aos usuários](../admin/manage/assign-licenses-to-users.md).

## <a name="using-the-content-search-ediscovery-tool-to-respond-to-dsrs"></a>Usar a ferramenta Descoberta Eletrônica de Pesquisa de Conteúdo para responder às DSRs

Ao pesquisar dados pessoais dentro do conjunto maior de dados que sua organização cria e armazena usando o Office 365, você pode considerar primeiro quais aplicativos as pessoas provavelmente usaram para criar os dados que você está procurando. A Microsoft estima que mais de 90% dos dados de uma organização armazenados no Office 365 são criados no Word, Excel, PowerPoint, OneNote e Outlook. Os documentos criados nesses aplicativos do Office, mesmo que adquiridos pelos Aplicativos do Microsoft 365 para empresas ou por uma licença permanente do Office, provavelmente são armazenados em um site do SharePoint Online, na conta do OneDrive for Business do usuário ou na caixa de correio do Exchange Online do usuário. Isso significa que você pode usar a ferramenta de Descoberta Eletrônica da Pesquisa de Conteúdo para pesquisar (e executar outras ações relacionadas a DSRs) em sites do SharePoint Online, contas do OneDrive for Business e caixas de correio do Exchange Online (incluindo sites e caixas de correio associados aos Grupos do Microsoft 365, Microsoft Teams, Atribuições EDU) para encontrar documentos e itens de caixa de correio que possam ser relevantes para a DSR que você está investigando. Você também pode usar a ferramenta Pesquisa de Conteúdo para descobrir Dados do Cliente criados em outros aplicativos do Office 365.

A tabela a seguir lista os aplicativos do Office 365 que as pessoas usam para criar Conteúdo Criado pelo Cliente e que pode ser descoberto usando a Pesquisa de Conteúdo. Esta seção do guia da DSR fornece orientação sobre como descobrir, acessar, exportar e excluir dados criados com esses aplicativos do Office 365.

***Tabela 1: Aplicativos em que a Pesquisa de Conteúdo pode ser usada para encontrar Dados do Cliente***

| | |
| :---: | :---:|
![Ícone do calendário](../media/O365-DSR-Doc-Final_image3.png) <br> Calendário | ![Ícone do SharePoint](../media/o365-sharepoint-64x64.png) <br> SharePoint  |
| ![Ícone do Excel](../media/o365-excel-64x64.png) <br> Excel | ![Ícone do Skype for Business](../media/o365-skypeforbusiness-64x64.png) <br> Skype for Business |
| ![Ícone do Office Lens](../media/o365-lens-64x64.png) <br> Office Lens | ![Ícone de Tarefas](../media/O365-DSR-Doc-Final_image8.png) <br> Tarefas |
| ![Ícone do OneDrive](../media/o365-OneDrive-64x64.png) <br> OneDrive for Business |![Ícone do Teams](../media/o365-teams-64x64.png) <br> Teams |
| ![Ícone do OneNote](../media/o365-onenote-64x64.png) <br> OneNote| ![Ícone do To Do](../media/o365-todo-64x64.png) <br> To Do |
| ![Ícone do Outlook](../media/o365-outlook-64x64.png) <br> Outlook/Exchange | ![Ícone de Vídeo](../media/O365-DSR-Doc-Final_image14.png) <br> Vídeo |
| ![Ícone de pessoas](../media/O365-DSR-Doc-Final_image15.png) <br> Pessoas | ![Ícone do Visio](../media/o365-visio-64x64.png) <br> Visio |
| ![Ícone do PowerPoint](../media/o365-powerpoint-64x64.png) <br> PowerPoint | ![Ícone do Word](../media/o365-word-64x64.png) <br> Word
||

>[!NOTE]
>A ferramenta eDiscovery da pesquisa de conteúdo não está disponível no [Office 365 operado pela 21Vianet (China)](https://docs.microsoft.com/microsoft-365/admin/services-in-china/services-in-china). Isso significa que você não poderá usar essa ferramenta para pesquisar e exportar dados do cliente nos aplicativos do Office 365 mostrados na Tabela 1. No entanto, você pode usar a ferramenta de descoberta eletrônica local no Exchange Online para pesquisar conteúdo em caixas de correio de usuário. Você também pode usar o Centro de Descoberta Eletrônica no SharePoint Online para pesquisar conteúdo em sites do SharePoint e contas do OneDrive. Como alternativa, você pode pedir ao proprietário do documento para ajudá-lo a encontrar e fazer alterações ou exclusões no conteúdo ou exportá-lo, se necessário. Para mais informações, veja:</br><br> * [Criar uma pesquisa de Descoberta Eletrônica no local](https://docs.microsoft.com/exchange/create-in-place-ediscovery-search-exchange-2013-help)<br> * [Configurar um Centro de Descoberta Eletrônica no SharePoint Online](https://support.office.com/article/Set-up-an-eDiscovery-Center-in-SharePoint-Online-A18F8975-AA7F-43B4-A7D6-001D14744D8E)

### <a name="using-content-search-to-find-personal-data"></a>Usar a Pesquisa de Conteúdo para encontrar dados pessoais

A primeira etapa ao responder a uma DSR é localizar os dados pessoais do titular da DSR. Isso consiste em usar as ferramentas de Descoberta Eletrônica do Office 365 para pesquisar dados pessoais (entre todos os dados da sua organização no Office 365) ou ir diretamente para o aplicativo nativo no qual os dados foram criados. Esta primeira etapa, localizar e revisar os dados pessoais em questão, ajuda a determinar se uma DSR atende aos requisitos de sua organização para aceitar ou recusar uma solicitação de entidade de dados. Por exemplo, depois de encontrar e revisar os dados pessoais em questão, você pode determinar que a solicitação não atende aos requisitos da sua organização, pois isso pode afetar adversamente os direitos e liberdades de outras pessoas ou porque os dados pessoais estão contidos em um registro comercial que sua organização tem um interesse comercial legítimo em reter.

Conforme mencionado anteriormente, a Microsoft estima que mais de 90% dos dados de uma organização sejam criados com aplicativos do Office, como Word e Excel. Isso significa que é possível usar a Pesquisa de Conteúdo no Centro de Conformidade e Segurança para pesquisar pela maioria dos dados relacionados a DSRs.

Este guia pressupõe que você ou a pessoa que está pesquisando dados pessoais que possam ser responsivos a uma solicitação DSR esteja familiarizado ou tenha experiência em usar a ferramenta Pesquisa de Conteúdo no Centro de Conformidade e Segurança. Para obter as diretrizes gerais de como usar a Pesquisa de Conteúdo, confira [Pesquisa de Conteúdo no Office 365](https://docs.microsoft.com/microsoft-365/compliance/content-search). Certifique-se de que a pessoa que esteja fazendo as pesquisas tenha recebido as permissões necessárias no Centro de Conformidade e Segurança. Essa pessoa deve ser adicionada como membro do grupo de função Gerente de Descoberta Eletrônica no Centro de Conformidade e Segurança. Confira [Atribuir permissões de Descoberta Eletrônica no Centro de Conformidade e Segurança](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions). Considere a adição de outras pessoas da organização que estejam envolvidas na investigação de DSRs ao grupo de função Gerente de Descoberta Eletrônica, de modo que elas possam executar as ações necessárias na ferramenta Pesquisa de Conteúdo, como visualizar e exportar resultados da pesquisa. No entanto, a menos que você tenha configurado limites de conformidade (conforme descrito [aqui](#set-up-compliance-boundaries-to-limit-the-scope-of-content-searches)), esteja ciente de que um Gerente de Descoberta Eletrônica pode pesquisar todos os locais de conteúdo da organização, incluindo aqueles que podem não estar relacionados a uma investigação de DSR.

Depois de encontrar os dados, você pode executar uma ação específica que atenda à solicitação feita pelo titular dos dados.

>[!NOTE]
>No Office 365 Germany, o Centro de Conformidade e Segurança está localizado em https://protection.office.de.

#### <a name="searching-content-locations"></a>Pesquisar locais de conteúdo

Você pode pesquisar os tipos de local de conteúdo a seguir com a ferramenta Pesquisa de Conteúdo.

- Caixas de correio do Exchange Online. Isso inclui as caixas de correio associadas aos Grupos do Microsoft 365 e o Microsoft Teams
- Pastas públicas do Exchange Online
- Sites do SharePoint Online. Isso inclui os sites associados aos Grupos do Microsoft 365 e ao Microsoft Teams
- Contas do OneDrive for Business

>[!NOTE]
>Este guia pressupõe que todos os dados que possam ser relevantes para uma investigação de DSR estejam armazenados no Office 365; em outras palavras, armazenados na nuvem da Microsoft. Os dados armazenados no computador local de um usuário ou nos servidores locais de arquivos da organização estão fora do escopo de uma investigação DSR para dados armazenados no Office 365. Para obter orientações sobre como responder a solicitações de DSR de dados em organizações locais, confira [GDPR para servidores locais do Office](https://docs.microsoft.com/Office365/Enterprise/gdpr-for-office-servers).

#### <a name="tips-for-searching-content-locations"></a>Dicas para pesquisar locais de conteúdo

- Comece pesquisando todos os locais de conteúdo da organização (o que pode ser feito em uma única pesquisa) para determinar rapidamente quais locais de conteúdo possuem itens que correspondem à sua consulta de pesquisa. Em seguida, você pode fazer uma nova pesquisa e limitar o escopo dela aos locais específicos que apresentam itens relevantes.
- Use as estatísticas de pesquisa para identificar os principais locais que contêm itens que correspondem à sua consulta de pesquisa. Consulte [Exibir as estatísticas de palavra-chave para resultados de pesquisa de conteúdo](https://docs.microsoft.com/microsoft-365/compliance/view-keyword-statistics-for-content-search).
- Pesquise no log de auditoria as atividades recentes de arquivos e pastas executadas pelo usuário que é o titular do DSR. Pesquisar o log de auditoria traz uma lista de registros de auditoria que contêm o nome e o local de recursos que o usuário interagiu recentemente.  Você pode usar essas informações para criar uma consulta de pesquisa de conteúdo. Confira [Pesquisar o log de auditoria no Centro de Conformidade e Segurança](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

#### <a name="building-search-queries-to-find-personal-data"></a>Criar consultas de pesquisa para encontrar dados pessoais

A DSR que você está investigando provavelmente contém identificadores que você pode usar na consulta de pesquisa de palavras-chave para pesquisar os dados pessoais. Aqui estão alguns identificadores comuns que podem ser usados em uma consulta de pesquisa para localizar dados pessoais:

- Alias ou endereço de email
- Número de telefone
- Endereço para correspondência
- Número de identificação do funcionário
- Número de identificação nacional ou versão de um número de seguro social do membro da UE

A DSR que você está investigando provavelmente terá um identificador e outros detalhes sobre os dados pessoais que são o assunto da solicitação e podem ser usados em uma consulta de pesquisa.

Pesquisar apenas um endereço de email ou ID do funcionário provavelmente retornará muitos resultados. Para limitar o escopo da pesquisa para que ela retorne o conteúdo mais relevante à DSR, você pode adicionar condições à consulta de pesquisa. Quando você adiciona uma condição, a palavra-chave e uma condição de pesquisa são conectadas de modo lógico pelo operador Booliano **AND**.  Isso significa que apenas os itens que corresponderem a *ambas* (palavra-chave e condição) serão retornados nos resultados da pesquisa. 

A tabela a seguir lista algumas condições que podem ser usadas para limitar o escopo de uma pesquisa. A tabela também lista os valores que podem ser usados para cada condição, de modo a pesquisar tipos de documento e itens de caixa de correio específicos.

***Tabela 2: Limitar o escopo da pesquisa usando condições***

||||
| :--- | :--- |:--- |
|**Condição**|**Descrição** |**Exemplo de valores de condição**|
| Tipo de arquivo | A extensão de um documento ou arquivo. Use esta condição para pesquisar documentos e arquivos do Office criados por aplicativos do Office 365. Use essa condição ao pesquisar documentos em sites do SharePoint Online e em contas do OneDrive for Business.<br/>A propriedade do documento correspondente é o tipo de arquivo. <br/>Para obter uma lista completa das extensões de arquivo que podem ser pesquisadas, confira o artigo sobre extensões de nome de arquivo rastreadas e tipos de arquivo analisados padrão no SharePoint](https://technet.microsoft.com/library/jj219530.aspx).|&nbsp;&bull;&nbsp;&nbsp;csv — pesquisa arquivos CSV (valores separados por vírgula); os arquivos do Excel podem ser salvos no formato CSV e o arquivo CSV pode ser importado facilmente no Excel<br><br>&bull;&nbsp;&nbsp;docx —pesquisa arquivos do Word <br><br>&bull;&nbsp;&nbsp;mpp — pesquisa arquivos do Project<br/><br>&bull;&nbsp;&nbsp;one — pesquisa arquivos do OneNote <br><br>&bull;&nbsp;&nbsp;pdf — pesquisa arquivos salvos em um formato PDF <br><br>&bull;&nbsp;&nbsp;pptx — pesquisa arquivos do PowerPoint <br><br>&bull;&nbsp;&nbsp;xlxs — pesquisa arquivos do Excel <br><br>&bull;&nbsp;&nbsp;vsd — pesquisa arquivos do Visio <br><br>&bull;&nbsp;&nbsp;wmv — pesquisa arquivos do Windows Media <br>|
| Tipo de mensagem | Tipo de mensagem de email para pesquisar. Use esta condição para pesquisar caixas de correio de contatos (Pessoas), tarefas de reuniões (Calendário) ou conversas do Skype for Business. A propriedade de email correspondente é *tipo*.|&bull;&nbsp;&nbsp;*contatos — pesquisa a lista Meus Contatos (Pessoas) de uma caixa de correio <br><br>&bull;&nbsp;&nbsp;* email — pesquisa mensagens de email <br><br>&bull;&nbsp;&nbsp;*im — pesquisa conversas do Skype for Business <br><br>&bull;&nbsp;&nbsp;* reuniões — pesquisa compromissos e solicitações de reunião (Calendário) <br><br>&bull;&nbsp;&nbsp;*tarefas — pesquisa a lista Minhas Tarefas (Tarefas); usar esse valor também retornará tarefas criadas no Microsoft To Do.<br>|
| Marca de conformidade |O rótulo atribuído a uma mensagem de email ou um documento. Os rótulos são usados para classificar emails e documentos para governança de dados e imposição de regras de retenção com base na classificação definida pelo rótulo. Use essa condição para pesquisar itens que receberam um rótulo automática ou manualmente.<br/>Essa é uma condição útil para investigações de DSR porque sua organização pode estar usando rótulos para classificar conteúdos relacionados à privacidade dos dados ou que contenham dados pessoais ou informações confidenciais. Consulte a seção "Usando a Pesquisa de Conteúdo para encontrar todos os conteúdos com rótulos específicos aplicados" em [Visão geral dos rótulos no Office 365.](https://docs.microsoft.com/microsoft-365/compliance/labels)|compliancetag="personal data"|
||||

Há muito mais condições de pesquisa e propriedades de documento ou email que você pode usar para criar consultas de pesquisa mais complexas. Veja a seção a seguir no tópico da Ajuda [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions) para obter mais informações.

- [Propriedades de emails pesquisáveis](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)
- [Propriedades de site pesquisáveis (documento)](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)
- [Condições de pesquisa](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)

#### <a name="searching-for-personal-data-in-sharepoint-lists-discussions-and-forms"></a>Pesquisar dados pessoais em listas, discussões e formulários do SharePoint

Além de pesquisar dados pessoais em documentos, você também pode usar a Pesquisa de Conteúdo para pesquisar outros tipos de dados criados usando aplicativos nativos do SharePoint Online. Isso inclui dados criados usando listas, discussões e formulários do SharePoint. Quando você executar uma Pesquisa de Conteúdo e pesquisar os dados de sites do SharePoint Online (ou contas do OneDrive for Business), listas, discussões e formulários que correspondam aos critérios de pesquisa serão retornados nos resultados.

##### <a name="examples-of-search-queries"></a>Exemplos de consultas de pesquisa

Aqui estão alguns exemplos de consultas de pesquisa que usam palavras-chave e condições para pesquisar dados pessoais em resposta a uma DSR. Os exemplos mostram duas versões da consulta: uma mostrando a sintaxe de palavra-chave (onde a condição está incluída na caixa de palavra-chave) e outra mostrando a versão baseada em GUI da consulta com condições.

##### <a name="example-1"></a>Exemplo 1

Este exemplo retorna arquivos do Excel ou sites do SharePoint Online e contas do OneDrive for Business que contêm o endereço de email especificado. Os arquivos podem ser retornados se o endereço de email aparecer nos metadados do arquivo.

***Sintaxe da palavra-chave***

```Query
pilar@contoso.com AND filetype="xlxs"
```

***GUI***

![caixa de diálogo palavra-chave](../media/O365-DSR-Doc_image18.png)

##### <a name="example-2"></a>Exemplo 2

Este exemplo retorna arquivos do Excel ou Word nos sites do SharePoint Online e contas do OneDrive for Business que contêm a ID ou a data de nascimento especificada do funcionário.

(98765 OU "01-20-1990") E (tipo de arquivo="xlxs" OU tipo de arquivo="docx")

***GUI***

![caixa de diálogo palavra-chave](../media/O365-DSR-Doc_image19.png)

##### <a name="example-3"></a>Exemplo 3

Este exemplo retorna mensagens de email que contêm o número de identificação especificado, que é o Número de Inscrição na Previdência Social na França (INSEE)

```Query
"1600330345678 97" AND kind="email"
```

***GUI***

![caixa de diálogo palavra-chave](../media/O365-DSR-Doc_image20.png)

#### <a name="working-with-partially-indexed-items-in-content-search"></a>Trabalhar com itens parcialmente indexados na Pesquisa de Conteúdo

Itens parcialmente indexados (também chamados de *itens não indexados*) são itens e documentos da caixa de correio do Exchange Online nos sites do SharePoint Online e OneDrive for Business que, por algum motivo, não foram indexados para pesquisa, o que significa que eles não podem ser pesquisados usando a Pesquisa de Conteúdo. A maioria das mensagens de email e dos documentos de site é indexada com êxito, pois eles se enquadram nos [limites de indexação do Office 365](https://docs.microsoft.com/microsoft-365/compliance/limits-for-content-search).  Os motivos pelos quais as mensagens ou arquivos de email não são indexados para pesquisa incluem:

- O tipo de arquivo não é [reconhecido ou não tem suporte para indexação](https://docs.microsoft.com/microsoft-365/compliance/partially-indexed-items-in-content-search).  No entanto, às vezes o tipo de arquivo tem suporte para indexação, mas houve um erro de indexação com um arquivo específico.
- As mensagens de email têm um arquivo anexado sem um manipulador válido, como um arquivo de imagem (essa é a causa mais comum de itens de email parcialmente indexados)
- Os arquivos anexados às mensagens de email são muito grandes ou há muitos arquivos anexados

É recomendável saber mais sobre itens parcialmente indexados para que você possa trabalhar com eles ao responder às solicitações DSR. Para obter mais informações, confira:

- [Itens parcialmente indexados na Pesquisa de Conteúdo do Office 365](https://docs.microsoft.com/microsoft-365/compliance/partially-indexed-items-in-content-search)
- [Investigar itens parcialmente indexados na Descoberta Eletrônica do Office 365](https://docs.microsoft.com/microsoft-365/compliance/investigating-partially-indexed-items-in-ediscovery)
- [Exportar itens não indexados](https://docs.microsoft.com/microsoft-365/compliance/export-search-results#unidexeditems)

#### <a name="tips-for-working-with-partially-indexed-items"></a>Dicas para trabalhar com itens parcialmente indexados

É possível que os dados responsivos a uma investigação de DSR estejam em um item parcialmente indexado. Aqui estão algumas sugestões para trabalhar com itens parcialmente indexados:

- Depois de executar uma pesquisa, o número de itens parcialmente estimados é exibido nas estatísticas de pesquisa.  Essa estimativa não inclui itens parcialmente indexados no SharePoint Online e no OneDrive for Business. Exporte os relatórios para uma Pesquisa de Conteúdo a fim de obter informações sobre itens parcialmente indexados. O relatório **Unindexed Items.csv** contém informações sobre itens não indexados, incluindo o local do item, a URL, se o item estiver no SharePoint Online ou no OneDrive for Business, e a linha do assunto (para mensagens) ou o nome do documento. Para saber mais, confira [Exportar um relatório da Pesquisa de Conteúdo](https://docs.microsoft.com/microsoft-365/compliance/export-a-content-search-report).

- As estatísticas e a lista de itens parcialmente indexados que são retornadas com os resultados de uma Pesquisa de Conteúdo são todos os itens parcialmente indexados dos locais de conteúdo que são pesquisados.

- Para recuperar itens parcialmente indexados potencialmente responsivos a uma investigação de DSR, você pode executar uma das ações a seguir:

##### <a name="export-all-partially-indexed-items"></a>Exportar todos os itens parcialmente indexados

Você exporta os resultados de uma pesquisa de conteúdo e os itens parcialmente indexados do local de conteúdo que foi pesquisado. Você também pode exportar somente os itens parcialmente indexados. Em seguida, você pode abri-los em seus aplicativos nativos e analisar o conteúdo. Você deve usar essa opção para exportar itens do SharePoint Online e do OneDrive for Business. Confira [Exportar os resultados da Pesquisa de Conteúdo do Centro de Conformidade e Segurança](https://docs.microsoft.com/microsoft-365/compliance/export-search-results).

##### <a name="export-a-specific-set-of-partially-indexed-items-from-mailboxes"></a>Exportar um conjunto específico de itens parcialmente indexados das caixas de correio

Em vez de exportar todos os itens de caixa de correio parcialmente indexados de uma pesquisa, você pode executar novamente uma Pesquisa de Conteúdo para procurar uma lista específica de itens parcialmente indexados e exportá-los. Você só pode fazer isso com itens de caixa de correios. Confira [Preparar um arquivo CSV para uma Pesquisa de Conteúdo direcionada no Office 365](https://docs.microsoft.com/microsoft-365/compliance/csv-file-for-an-id-list-content-search). 

### <a name="next-steps"></a>Próximas etapas

Depois de encontrar os dados pessoais relevantes para a DSR, certifique-se de manter a Pesquisa de Conteúdo específica que você usou para localizar os dados. Provavelmente, você reutilizará essa pesquisa para concluir outras etapas no processo de resposta DSR, como [obter uma cópia dela](#providing-a-copy-of-personal-data), [exportá-la](#exporting-personal-data) ou [excluí-la permanentemente](#deleting-personal-data). 

### <a name="additional-considerations-for-selected-applications"></a>Considerações adicionais para seleção de aplicativos

As seções a seguir descrevem o que você deve ter em mente durante a pesquisa de dados nos aplicativos do Office 365 que se seguem.

- [Office Lens](#office-lens)
- [Configurações de experiência do OneDrive for Business e SharePoint](#onedrive-for-business-and-sharepoint-online-experience-settings)
- [Microsoft Teams educacional](#microsoft-teams-for-education)
- [Microsoft To Do](#microsoft-to-do)
- [Skype for Business](#skype-for-business)

#### <a name="office-lens"></a>Office Lens

Uma pessoa usando o Office Lens (um aplicativo de câmera compatível com dispositivos iOS, Android e Windows) pode fotografar quadros de comunicações, documentos impressos, cartões de visita, entre outras coisas com muito texto. O Office Lens usa tecnologia de reconhecimento óptico de caracteres que extrai o texto em uma imagem e o salva em um documento do Office, como Word, PowerPoint e OneNote ou em um arquivo PDF. Os usuários podem então carregar o arquivo que contém o texto da imagem na respectiva conta do OneDrive for Business no Office 365.  Isso significa que você pode usar a ferramenta Pesquisa de Conteúdo para pesquisar, acessar, excluir e exportar dados em arquivos que foram criados a partir de uma imagem do Office Lens. Para saber mais sobre o Office Lens, confira:

- [Office Lens para iOS](https://support.microsoft.com/pt-BR/office/microsoft-office-lens-for-ios-fbdca5f4-1b1b-4391-a931-dc1c2582397b)
- [Office Lens para Android](https://support.office.com/article/Office-Lens-for-Android-ec124207-0049-4201-afaf-b5874a8e6f2b)
- [Office Lens para Windows](https://support.microsoft.com/pt-BR/office/office-lens-for-windows-577ec09d-8da2-4029-8bb7-12f8114f472a)

#### <a name="onedrive-for-business-and-sharepoint-online-experience-settings"></a>Configurações de experiência do OneDrive for Business e SharePoint

Além dos arquivos criados pelo usuário armazenados em contas do OneDrive for Business e sites do SharePoint Online, esses serviços armazenam informações sobre o usuário que são usadas para possibilitar várias experiências. Os usuários ainda em sua organização podem acessar grande parte dessas informações usando a funcionalidade no produto. As informações a seguir fornecem diretrizes sobre como acessar, exibir e exportar dados de aplicativo do OneDrive for Business e SharePoint Online.

##### <a name="sharepoint-user-profiles"></a>Perfis de usuário do SharePoint

O perfil dos usuários no Delve permite que estes mantenham propriedades armazenadas no perfil de usuário do SharePoint, incluindo aniversário, número do celular (e outras informações de contato), sobre mim, projetos, habilidades e competências, escolas e formação, interesses e hobbies.

###### <a name="end-users"></a>Usuários finais

Os usuários finais podem descobrir, acessar e retificar dados do perfil de usuário do SharePoint Online usando a experiência com o perfil do Delve. Confira [Exibir e atualizar seu perfil no Office Delve](https://support.office.com/article/view-and-update-your-profile-in-office-delve-4e84343b-eedf-45a1-aeb9-8627ccca14ba) para obter mais detalhes.

Outra maneira de os usuários acessarem os dados de perfil do SharePoint é navegar até a **página de edição de perfil** na conta do OneDrive for Business, que pode ser acessada pelo caminho **EditProfile.aspx** sob a URL da conta do OneDrive for Business. Por exemplo, para um usuário <strong>usuario1@contoso.com</strong>, a conta do OneDrive for Business dele está localizada em:

```URL
`https://contoso-my.sharepoint.com/personal/user1\_contoso\_com/\_layouts/15/OneDrive.aspx`
```

A URL para a página de edição de perfil seria:

```URL
`https://contoso-my.sharepoint.com/personal/user1\_contoso\_com/\_layouts/15/EditProfile.aspx`
```

As propriedades originadas no Azure Active Directory não podem ser alteradas no SharePoint Online. No entanto, os usuários podem ir para a respectiva página **Conta** selecionando a respectiva **foto** no cabeçalho do Office 365 e, em seguida, selecionando **Minha Conta**. Alterar as propriedades aqui pode exigir que os usuários trabalhem com seus administradores para descobrir, acessar ou retificar uma propriedade do perfil de usuário.

###### <a name="admins"></a>Administradores

Um administrador pode acessar e retificar propriedades de perfil no centro de administração do SharePoint. No **centro de administração do SharePoint**, clique na guia **perfis de usuário**. Clique em **Gerenciar perfis de usuário**, insira um nome de usuário e clique em **Localizar**. O administrador pode clicar com o botão direito do mouse em qualquer usuário e selecionar **Editar meu Perfil**.  As propriedades originadas no Azure Active Directory não podem ser alteradas no SharePoint Online.

Um administrador pode exportar todas as propriedades de Perfil de Usuário para um usuário usando o cmdlet **Export-SPOUserProfile** no PowerShell do SharePoint Online. Veja [Export-SPOUserProfile](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spouserprofile?view=sharepoint-ps).

Para saber mais sobre perfis de usuário, confira [Gerenciar perfis de usuário no Centro de administração do SharePoint](https://docs.microsoft.com/sharepoint/manage-user-profiles).

##### <a name="user-information-list-on-sharepoint-online-sites"></a>Lista de informações do usuário em sites do SharePoint Online

Um subconjunto de perfis de usuário do SharePoint de um usuário é sincronizado com a lista Informações do usuário de todos os sites que ele visita ou tem permissões para acessar.  Isso é usado pelas experiências do SharePoint Online, como as colunas Pessoas nas bibliotecas de documentos, para exibir informações básicas sobre o usuário, como o nome do criador de um documento. Os dados em uma lista Informações do usuário correspondem às informações armazenadas no perfil de usuário do SharePoint e serão retificados automaticamente se a fonte for alterada. Para usuários excluídos, esses dados permanecem nos sites com os quais eles interagiram, para a integridade referencial dos campos de colunas do SharePoint. 

Os administradores podem controlar quais propriedades são replicáveis no centro de administração do SharePoint. Para fazer isso:

1. Acesse o **Centro de Administração do SharePoint** e clique na guia **Perfis de usuário**.
2. Clique em **Gerenciar Propriedades do Usuário** para ver uma lista de propriedades.
3. Clique com o botão direito do mouse em qualquer propriedade, selecione **Editar** e ajuste várias configurações.
4. Em **Configurações de Política**, a propriedade replicável controla se a propriedade será representada na lista Informações do usuário.  Nem todas as propriedades dão suporte a esse ajuste.

Um administrador pode exportar todas as propriedades de Informações do usuário para um usuário em determinado site usando o cmdlet **Export-SPOUserInfo** no PowerShell do SharePoint Online. Veja [Export-SPOUserInfo](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spouserinfo?view=sharepoint-ps).

##### <a name="onedrive-for-business-experience-settings"></a>Configurações de experiência do OneDrive for Business

A experiência do OneDrive for Business de um usuário armazena informações que ajudam o usuário a encontrar o conteúdo de seu interesse e a navegar nele. A maioria dessas informações pode ser acessada pelos usuários finais usando os recursos do produto. Um administrador pode exportar as informações usando um [Script do PowerShell](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6) e [comandos do CSOM (Modelo de Objeto do Lado do Cliente do SharePoint)](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-client-library-code).

Veja [Exportar as configurações da experiência do OneDrive for Business](https://docs.microsoft.com/sharepoint/export-odfb-lists) para saber mais sobre as configurações, como elas são armazenadas e como exportá-las.

##### <a name="onedrive-for-business-and-sharepoint-online-search"></a>Pesquisa do OneDrive for Business e SharePoint Online

A experiência de pesquisa no aplicativo no OneDrive for Business e no SharePoint Online armazena consultas de pesquisa do usuário por até 30 dias para aumentar a relevância dos resultados da pesquisa. Um administrador pode exportar consultas de pesquisa de um usuário usando o cmdlet **Export-SPOQueryLogs** no PowerShell do SharePoint Online. Veja [Export-SPOQueryLogs](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spoquerylogs?view=sharepoint-ps).

#### <a name="microsoft-teams-for-education"></a>Microsoft Teams educacional

O Microsoft Teams educacional oferece dois recursos adicionais de colaboração que professores e alunos podem usar para criar e armazenar dados pessoais: Atribuições e Bloco de Anotações de Classe do OneNote. Você pode usar a Pesquisa de Conteúdo para descobrir dados em ambos.

##### <a name="assignments"></a>Atribuições

Os arquivos de alunos associados a uma Atribuição são armazenados em uma biblioteca de documentos no site do SharePoint Online do Teams correspondente. Os administradores de TI podem usar a ferramenta Pesquisa de Conteúdo para pesquisar arquivos de alunos que estejam relacionados a atribuições. Por exemplo, um administrador pode pesquisar todos os sites do SharePoint Online na organização e usar o nome do aluno e o nome da classe ou da tarefa na consulta de pesquisa para encontrar dados relevantes para uma DSR.

Existem outros dados relacionados a atribuições que não são armazenados no site do SharePoint Online da equipe de classe, o que significa que não podem ser descobertos com a Pesquisa de Conteúdo. Isso inclui:

- Arquivos que o professor atribui aos alunos como parte da atribuição
- Notas do aluno e comentários do professor
- A lista de documentos enviados para uma atribuição por cada aluno
- Metadados de atribuição

Para esse tipo de dado, um administrador de TI ou proprietário de dados (como um professor) pode ter que entrar em Atribuição na equipe da classe para encontrar dados relevantes a uma DSR.

##### <a name="onenote-class-notebook"></a>Bloco de Anotações de Classe do OneNote

O Bloco de Anotações de Classe do OneNote é armazenado no site do SharePoint Online da equipe de classe. Cada aluno em uma classe tem um bloco de anotações privado que é compartilhado com o professor. Também há uma biblioteca de conteúdo em que um professor pode compartilhar documentos com alunos, bem como um espaço de colaboração para todos os alunos na classe. Os dados relacionados a esses recursos podem ser descobertos com a Pesquisa de Conteúdo.

Veja a seguir as diretrizes específicas para pesquisar por um Bloco de Anotações de Classe.

1. Execute uma Pesquisa de Conteúdo usando os seguintes critérios de pesquisa:

   - Pesquisar todos os sites do SharePoint Online

   - Inclua o nome da equipe de classe como uma palavra-chave de pesquisa; por exemplo, "Biologia 9C".

2. Visualize os resultados da pesquisa e procure o item que corresponde ao Bloco de Anotações de Classe.
3. Selecione esse item e copie o caminho da pasta que é exibido no painel de detalhes. Essa é a pasta raiz do Bloco de Anotações de Classe.
4. Edite a pesquisa que você criou na etapa 1, substitua o nome da classe na consulta de palavra-chave pelo caminho da pasta do Bloco de Anotações de Classe e preceda o caminho da pasta com a propriedade do site **caminho**; por exemplo, **caminho:<https://contosoedu.onmicrosoft.com/sites/9C> Biology/SiteAssets/9C Biology Notebook/**. Certifique-se de incluir as aspas e a barra à direita.
5. Adicione uma condição de pesquisa e selecione a condição Tipo de Arquivo e use um para o valor do tipo de arquivo.  Isso retorna todos os arquivos do OneNote nos resultados da pesquisa. A sintaxe da palavra-chave resultante seria parecida com esta: [](#building-search-queries-to-find-personal-data)

    ```Query
   path:"<https://contosoedu.onmicrosoft.com/sites/9C> Biology/SiteAssets/9C Biology Notebook/" AND filetype="one"
   ```

6.  Executar novamente a Pesquisa de Conteúdo. Os resultados da pesquisa devem incluir todos os arquivos do OneNote para o Bloco de Anotações de Classe da equipe da classe.

#### <a name="microsoft-to-do"></a>Microsoft To Do

As tarefas (chamadas de *tarefas pendentes*, que são salvas em *listas de tarefas*) no Microsoft To Do são salvas como tarefas na caixa de correio do Exchange Online de um usuário. Isso significa que você pode usar a ferramenta de Pesquisa de Conteúdo para pesquisar, acessar, excluir e exportar tarefas pendentes. Para obter mais informações, consulte [Configurar o Microsoft To Do](https://support.microsoft.com/pt-BR/office/set-up-microsoft-to-do-490c1a8c-2333-4952-8125-841afadb9620).

#### <a name="skype-for-business"></a>Skype for Business

Veja algumas informações adicionais sobre como acessar, exibir e exportar dados pessoais no Skype for Business.

- Os arquivos anexados a uma reunião são mantidos na reunião real por 180 dias e depois disso ficam inacessíveis. Esses arquivos podem ser acessados pelos participantes da reunião, ingressando na reunião a partir da solicitação de reunião e visualizando ou baixando o arquivo anexado. Consulte a seção "Usar os anexos na reunião" em [Pré-carregar os anexos de uma reunião do Skype for Business](https://support.microsoft.com/pt-BR/office/preload-attachments-for-a-skype-for-business-meeting-fd3d9f9d-b448-4754-b813-02e49393f251).
- As conversas do Skype for Business são mantidas na pasta Histórico da Conversa nas caixas de correio do usuário. Você pode usar a Pesquisa de Conteúdo para pesquisar caixas de correio em busca de dados nas conversas do Skype.
- Um titular de dados pode exportar seus contatos no Skype for Business. Para isso, ele clica com o botão direito do mouse em um grupo de contatos no Skype for Business e clica em **Copiar**. Em seguida, ele pode colar a lista de endereços de email em um documento do Word ou texto.
- Se a caixa de correio do Exchange Online de um participante da reunião for colocada em Retenção de Litígio ou atribuída a uma política de retenção do Office 365, os arquivos anexados a uma reunião serão retidos na caixa de correio dos participantes. Você pode usar a Pesquisa de Conteúdo para pesquisar esses arquivos na caixa de correio do participante, se o período de retenção do arquivo não tiver expirado. Para obter mais informações sobre como reter arquivos, confira [Retenção de arquivos grandes anexados a uma reunião do Skype for Business](https://docs.microsoft.com/skypeforbusiness/set-up-policies-in-your-organization/retaining-large-files-attached-to-a-meeting).

## <a name="providing-a-copy-of-personal-data"></a>Fornecer uma cópia dos dados pessoais

Depois de encontrar dados pessoais potencialmente responsivos a uma DSR, cabe a você e à sua organização decidir quais dados fornecer ao titular dos dados. Por exemplo, você pode fornecer a ele uma cópia do documento original, uma versão adequadamente redigida ou uma captura de tela das partes que você considerou apropriado compartilhar. Para cada uma dessas respostas a uma solicitação de acesso, você terá que recuperar uma cópia do documento ou outro item que contenha os dados responsivos.

Ao oferecer uma cópia ao titular dos dados, talvez você tenha que remover ou redigir informações pessoais sobre outros titulares de dados e quaisquer informações confidenciais.

### <a name="using-content-search-to-get-a-copy-of-personal-data"></a>Usar a Pesquisa de Conteúdo para obter uma cópia dos dados pessoais

Existem duas maneiras de usar a ferramenta Pesquisa de Conteúdo para obter uma cópia de um documento ou item da caixa de correio que você encontrou após executar uma pesquisa.

- Visualize os resultados da pesquisa e baixe uma cópia do documento ou item. Essa é uma boa maneira de baixar alguns itens ou arquivos.
- Exporte os resultados da pesquisa e baixe uma cópia de todos os itens retornados pela pesquisa. Esse método é mais complexo, mas é uma boa maneira de baixar muitos itens que respondam à DSR. Relatórios úteis também são incluídos com os resultados da pesquisa exportados. Você pode usar esses relatórios para obter informações adicionais sobre cada item. O relatório **Results.csv** é útil, pois contém muitas informações sobre os itens exportados, como o local exato do item (por exemplo, a caixa de correio das mensagens de email, ou a URL para documentos ou listas localizados em sites do SharePoint Online e OneDrive for Business).  Essas informações ajudarão a identificar o proprietário do item, caso você precise contatá-lo durante o processo de investigação de DSR. Para saber mais sobre os relatórios que são incluídos na exportação dos resultados da pesquisa, confira [Exportar um relatório de Pesquisa de Conteúdo](https://docs.microsoft.com/microsoft-365/compliance/export-a-content-search-report). 

#### <a name="preview-and-download-items"></a>Visualizar e baixar itens

Depois de executar uma nova pesquisa ou abrir uma pesquisa existente, é possível visualizar cada item que correspondeu à consulta de pesquisa a fim de verificar se ele está relacionado à DSR que você está investigando. Isso também inclui listas e páginas da Web do SharePoint que são retornadas nos resultados da pesquisa. Também é possível baixar o arquivo original se você tiver que fornecê-lo ao titular dos dados.  Em ambos os casos, você faz uma captura a tela para atender à solicitação do titular dos dados de obter as informações.

Alguns tipos de itens não podem ser visualizados. Se um tipo de item ou arquivo não tiver suporte para visualização, existe a opção de baixar um item individual para o seu computador local, ou uma unidade de rede mapeada, ou outro local de rede. Você pode visualizar apenas [tipos de arquivo com suporte](https://docs.microsoft.com/microsoft-365/compliance/content-search).

Para visualizar e baixar itens:

1. Abra a Pesquisa de Conteúdo no Centro de Conformidade e Segurança.
2. Se os resultados não forem exibidos, clique em **Visualizar resultados**.
3. Clique em um item para exibi-lo.
4. Clique em **Baixar arquivo original** para baixar o item no seu computador local. Você também terá que baixar itens que não podem ser visualizados.

Para obter mais informações sobre como visualizar resultados da pesquisa, confira [Visualizar resultados da pesquisa](https://docs.microsoft.com/microsoft-365/compliance/content-search).

#### <a name="export-and-download-items"></a>Exportar e baixar itens

Você também pode exportar os resultados de uma pesquisa de conteúdo para obter uma cópia de mensagens de email, documentos, listas e páginas da Web contendo dados pessoais, embora esse método seja mais complexo do que a visualização de itens. Confira a próxima seção para obter detalhes sobre como [exportar os resultados de uma Pesquisa de Conteúdo](#export-and-download-content-using-content-search).

## <a name="exporting-personal-data"></a>Exportar dados pessoais

O "direito de portabilidade dos dados" permite que um titular de dados solicite uma cópia eletrônica dos dados pessoais que estejam em um "formato estruturado, frequentemente usado, que possa ser lido por máquina", bem como solicite que sua organização transmita esses arquivos eletrônicos para outro controlador de dados. A Microsoft dá suporte a esse direito de duas maneiras:

- Oferecendo aplicativos do Office 365 que salvam dados em formato eletrônico nativo frequentemente usado, que possa ser lido por máquina. Para saber mais sobre formatos de arquivo do Office, confira os [Documentos Técnicos sobre os Formatos de Arquivo do Office](https://msdn.microsoft.com/library/office/cc313105(v=office.12).aspx).
- Permitindo que a sua organização exporte os dados no formato de arquivo nativo ou em um formato (como CSV, TXT e JSON) que possa ser facilmente importado para outro aplicativo.

Para atender a uma solicitação de exportação de DSR, você pode exportar documentos do Office em seu formato de arquivo nativo e exportar os dados de outros aplicativos do Office 365.

### <a name="export-and-download-content-using-content-search"></a>Exportar e baixar conteúdo usando a Pesquisa de Conteúdo

Quando você exporta os resultados de uma Pesquisa de Conteúdo, os itens de email podem ser baixados como arquivos PST ou como mensagens individuais (arquivos .msg). Quando você exporta documentos e listas de sites do SharePoint Online e OneDrive for Business, as cópias nos formatos de arquivos nativos são exportadas. Por exemplo, as listas do SharePoint são exportadas como arquivos CSV e as páginas da Web são exportadas como arquivos .aspx ou html.

>[!NOTE]
>Exportar itens da caixa de correio de um usuário usando a Pesquisa de Conteúdo exige que o usuário (de cuja caixa de correio você está exportando itens) receba uma licença Plano 2 do Exchange Online. 

Para exportar e baixar itens:

1. Abra a Pesquisa de Conteúdo no Centro de Conformidade e Segurança.
2. Na página do submenu de pesquisa, clique em ![carregar ícone](../media/o365-dsr_image21.png) **Mais**, e em **Exportar resultados**. Também é possível exportar um relatório.
3. Conclua as seções na página do submenu **Exportar resultados**. Certifique-se de usar a barra de rolagem para exibir todas as opções de exportação.
4. Volte para a página Pesquisa de Conteúdo no Centro de Conformidade e Segurança e clique na guia **Exportar**.
5. Clique em **Atualizar** para atualizar a página.
6. Na coluna **Nome**, clique no trabalho de exportação que você criou. O nome do trabalho de exportação é o nome da pesquisa de conteúdo acrescido de **\_Export**.
7. Na página do submenu de exportação, em **Chave de exportação**, **clique em copiar para a área de transferência**. Você usará essa chave na etapa 10 para baixar os resultados da pesquisa.
8. Na parte superior da página do submenu, clique em ![baixar ícone](../media/o365-dsr_image21.png) **Baixar resultados**.
9. Caso você receba uma solicitação para instalar a **Ferramenta de Exportação de Descoberta Eletrônica do Office 365**, clique em **Instalar**.
10. Na **Ferramenta de Exportação de Descoberta Eletrônica**, cole na caixa apropriada a chave de exportação que você copiou na etapa 7.
11. Clique em **Procurar** para especificar o local onde deseja baixar os arquivos de resultado da pesquisa.
12. Clique em **Iniciar** para baixar os resultados da pesquisa em seu computador.

Quando o processo de exportação estiver concluído, você poderá acessar os arquivos no seu computador local onde eles foram baixados. Os resultados de uma pesquisa de conteúdo são baixados em uma pasta nomeada após a Pesquisa de Conteúdo. Os documentos de sites são copiados em uma subpasta chamada **SharePoint**. Os itens de caixa de correio são copiados na subpasta chamada **Exchange**.

Para ver instruções passo a passo detalhadas, confira [Exportar resultados da Pesquisa de Conteúdo do Centro de Conformidade e Segurança](https://docs.microsoft.com/microsoft-365/compliance/export-search-results).

### <a name="downloading-documents-and-lists-from-sharepoint-online-and-onedrive-for-business"></a>Baixar documentos e listas do SharePoint Online e OneDrive for Business

Outra maneira de exportar dados do SharePoint Online e OneDrive for Business é baixar documentos e listas diretamente de um site do SharePoint Online ou de uma conta do OneDrive for Business. Você teria que obter as permissões para acessar um site, acessar o site e baixar o conteúdo. Consulte:

- [Baixar arquivos e pastas do OneDrive ou SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)
- [Exportar listas do SharePoint para o Excel](https://support.office.com/article/export-to-excel-from-sharepoint-bfb2ea48-6118-4fa9-abb6-cced9424e5d9)

Para algumas solicitações de exportação de DSR, pode ser conveniente permitir que o próprio titular dos dados baixe o conteúdo. Isso permite que ele acesse o site ou a pasta compartilhada do SharePoint Online e clique em **Sincronizar** para sincronizar todo o conteúdo na biblioteca de documentos ou nas pastas selecionadas. Consulte:

- [Permitir que os usuários sincronizem arquivos do SharePoint com o novo cliente de sincronização do OneDrive](https://docs.microsoft.com/sharepoint/let-users-use-new-onedrive-sync-client)
- [Sincronizar arquivos do SharePoint com o novo cliente de sincronização do OneDrive](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-client-6de9ede8-5b6e-4503-80b2-6190f3354a88)

## <a name="deleting-personal-data"></a>Excluir dados pessoais

O “direito de apagar” através da remoção de dados pessoais dos Dados de Clientes de uma organização é uma proteção fundamental do RGPD. Entre as ações de remoção de dados pessoais, estão excluir documentos ou arquivos inteiros ou excluir dados específicos em um documento ou arquivo (que seria como as ações e os processos descritos na seção de retificação deste guia).

Conforme você investiga ou se prepara para excluir dados pessoais em resposta a uma DSR, existem alguns pontos importantes a serem entendidos sobre como a exclusão (e retenção) de dados funciona no Office 365.

- **Exclusão reversível versus exclusão irreversível**: nos serviços do Office 365 como o Exchange Online, o SharePoint Online e o OneDrive for Business, há os conceitos de *exclusão reversível* e *exclusão irreversível*, que estão relacionados à capacidade de recuperação de um item excluído (em geral, por um período limitado) antes de ele ser permanentemente removido da nuvem da Microsoft, sem possibilidade de recuperação. Nesse contexto, um item que sofreu uma exclusão reversível poderá ser recuperado pelo usuário e/ou administrador por um período limitado antes de ser excluído irreversivelmente. Quando um item é excluído de forma irreversível, fica marcado para remoção permanente e é eliminado assim que é processado pelo serviço correspondente do Office 365. Veja como a exclusão reversível e a exclusão irreversível funcionam com itens de caixas de correio e sites (independentemente de o proprietário ou administrador dos dados ter excluído o item):

    - **Caixas de correio:** um item é excluído de forma reversível quando ele é excluído da pasta Itens Excluídos ou quando o usuário exclui esse item pressionando **Shift + Delete**. Quando o item é excluído de forma reversível, ele é movido para a pasta Itens Recuperáveis na caixa de correio. Nesse ponto, o item poderá ser recuperado pelo usuário até que o período de retenção de itens excluídos expire (no Office 365, o período de retenção de itens excluídos é de 14 dias, mas pode ser aumentado para até 30 dias pelo administrador). Após a expiração do período de retenção, o item é excluído de forma irreversível e movido para uma pasta oculta (chamada pasta *Limpezas*). O item será permanentemente removido (limpo) do Office 365 na próxima vez que a caixa de correio for processada (as caixas de correio são processadas a cada sete dias).

    - **Sites do SharePoint Online e OneDrive for Business**: quando um arquivo ou documento é excluído, ele é movido para a Lixeira do site (também chamada de *Lixeira de primeiro estágio* (que é como a Lixeira do Windows). O item permanece na Lixeira por 93 (período de retenção de itens excluídos para sites no Office 365). Após esse período, o item é movido automaticamente para a Lixeira do conjunto de sites, também chamada de *Lixeira de segundo estágio*. (Observe que os usuários ou administradores, com as permissões apropriadas, podem também excluir itens da Lixeira de primeiro estágio). Nesse ponto, o item é excluído de forma reversível; ele ainda poderá ser recuperado por um administrador de conjunto de sites no SharePoint Online ou por um usuário ou administrador no OneDrive for Business). Quando um item é excluído da Lixeira de segundo estágio (de forma manual ou automática), ele é excluído de forma irreversível e fica inacessível ao usuário ou administrador. O período de retenção é de 93 dias tanto para a lixeira de primeiro estágio quanto para a de segundo estágio. Isso significa que a retenção na Lixeira de segundo estágio começa quando o item é excluído pela primeira vez.  Portanto, o período de retenção máximo total é de 93 dias em ambas as lixeiras.

>[!NOTE]
>Entender as ações que resultam na exclusão temporária ou na exclusão irreversível de um item ajudará você a determinar como excluir dados de maneira que atenda aos requisitos de RGPD ao responder a uma solicitação de exclusão.

- **Políticas de retenção e retenções legais:** no Office 365, uma “retenção” pode ser colocada em caixas de correio e sites. Em resumo, isso significa que nada será permanentemente removido (exclusão irreversível) se uma caixa de correio ou um site estiver em retenção, até que o período de retenção de um item expire ou até que a retenção seja removida.  Isso é importante no contexto da exclusão do Conteúdo do Cliente em resposta a uma DSR: se um item for excluído irreversivelmente de um local de conteúdo que está em retenção, o item não será permanentemente removido do Office 365. Isso significa que ele pode ser recuperado de modo aceitável por um administrador de TI. Se a sua organização tiver um requisito ou uma política de que os dados sejam excluídos de maneira permanente e irrecuperável no Office 365 em resposta à DSR, uma retenção terá que ser removida de uma caixa de correio ou um site para excluir dados permanentemente do Office 365. Muito provavelmente, as diretrizes da sua organização para responder a DSRs têm um processo em vigor para determinar se uma solicitação específica de exclusão de DSR ou uma retenção legal tem precedência. Se uma retenção for removida para excluir itens, ela poderá ser reimplementada depois que o item for excluído.

### <a name="deleting-documents-in-sharepoint-online-and-onedrive-for-business"></a>Excluir documentos no SharePoint Online e OneDrive for Business

Depois de encontrar o documento localizado em um site do SharePoint Online ou em uma conta do OneDrive for Business (seguindo as diretrizes na seção Descobrir deste guia) que precisa ser excluído, o responsável pela privacidade de dados ou administrador de TI precisa atribuir as permissões necessárias para acessar o site e excluir o documento. Se adequado, o proprietário do documento também pode ser orientado a excluir o documento.

Veja a seguir o processo detalhado para excluir documentos de sites.

1. Acesse o site e localize o documento.
2. Exclua o documento. Quando você exclui um documento de um site, ele é enviado para a Lixeira de primeiro estágio.
3. Vá para a Lixeira de primeiro estágio (a Lixeira do site) e exclua o mesmo documento excluído na etapa anterior. O documento é enviado para a Lixeira de segundo estágio. **Nesse ponto, o documento é excluído temporariamente**.
4. Vá para a Lixeira de segundo estágio (que é a Lixeira do conjunto de sites) e exclua o mesmo documento excluído da Lixeira de primeiro estágio. **Nesse ponto, o documento é excluído irreversivelmente.**

>[!IMPORTANT]
>Não é possível excluir um documento localizado em um site que está em retenção (com um dos recursos de retenção ou retenção legal do Office 365). No caso em que uma solicitação de exclusão de DSR tiver precedência sobre uma retenção legal, a retenção terá que ser removida do site para que um documento possa ser excluído permanentemente.

Confira os tópicos a seguir para ver os procedimentos detalhados.

- [Excluir um arquivo, pasta ou link de uma biblioteca de documentos do SharePoint](https://support.microsoft.com/pt-BR/office/delete-a-file-folder-or-link-from-a-sharepoint-document-library-71f3c90a-0d24-4d80-8b66-f88234b79a52)
- [Excluir itens ou esvaziar a Lixeira de um site do SharePoint](https://support.microsoft.com/pt-BR/office/delete-items-or-empty-the-recycle-bin-of-a-sharepoint-site-2e713599-d13e-40d6-96dc-66f0a366f74e)
- [Excluir itens da Lixeira do conjunto de sites](https://support.microsoft.com/pt-BR/office/delete-items-from-the-site-collection-recycle-bin-dd5c00c2-aef6-4458-9d04-80b185077653)
- Seção "Obter acesso aos documentos de OneDrive for Business do ex-funcionário" em [Obter acesso e fazer backup dos dados de um usuário antigo](https://docs.microsoft.com/microsoft-365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data)
- [Excluir arquivos ou pastas no OneDrive for Business](https://support.office.com/article/Delete-files-or-folders-in-OneDrive-21fe345a-e488-4fa7-932b-f053c1bebe8a)
- [Excluir uma lista no SharePoint](https://support.microsoft.com/pt-BR/office/delete-a-list-in-sharepoint-2a7bca5b-b8fd-4e5b-8f4b-2ac034f3070d)
- [Excluir itens de lista no SharePoint Online](https://support.office.com/article/delete-list-items-in-sharepoint-online-db722233-4a38-4889-a6cf-4b33fe5c60c0)

### <a name="deleting-a-sharepoint-site"></a>Excluir um site do SharePoint

Você pode decidir que a melhor maneira de responder a uma solicitação de exclusão de DSR é excluir um site inteiro do SharePoint, o que excluirá todos os dados localizados no site. Isso pode ser feito executando os cmdlets no PowerShell do SharePoint Online.

- Use o cmdlet [Remover-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-sposite?view=sharepoint-ps) para excluir o site e movê-lo para a Lixeira do SharePoint Online (exclusão temporária).
- Use o cmdlet [Remove-SPODeletedSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spodeletedsite?view=sharepoint-ps) para excluir permanentemente o site (exclusão irreversível).

Não é possível excluir um site localizado em uma retenção de Descoberta Eletrônica ou atribuído a uma política de retenção. Os sites devem ser removidos de uma retenção de Descoberta Eletrônica ou de uma política de retenção antes que você possa excluí-los.

### <a name="deleting-a-onedrive-for-business-site"></a>Excluir um site do OneDrive for Business

Da mesma forma, você pode optar por excluir o site do OneDrive for Business de um usuário em resposta a uma solicitação de exclusão de DSR. Se você excluir a conta do Office 365 do usuário, o site do OneDrive for Business ficará retido (e restaurável) por 30 dias. Após 30 dias, ele será movido para a Lixeira do SharePoint Online (excluído por software) e, depois de 93 dias, excluído permanentemente (exclusão irreversível). Para acelerar esse processo, você pode usar o cmdlet [Remove-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-sposite?view=sharepoint-ps) para mover o site do OneDrive for Business para a Lixeira e, em seguida, usar o cmdlet [Remove-SPODeletedSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spodeletedsite?view=sharepoint-ps) para excluí-lo permanentemente. Assim como nos sites do SharePoint Online, você não pode excluir o site do OneDrive for Business de um usuário se ele tiver sido atribuído a uma retenção de Descoberta Eletrônica ou a uma política de retenção antes da exclusão da conta do usuário.

### <a name="deleting-onedrive-for-business-and-sharepoint-online-experience-settings"></a>Excluir configurações de experiência do OneDrive for Business e SharePoint Online

Além dos arquivos criados pelo usuário e armazenados nas contas do OneDrive for Business e sites do SharePoint Online, esses serviços armazenam informações sobre o usuário que são usadas para habilitar várias experiências. Essas informações eram anteriormente registradas neste documento. Confira as [Considerações adicionais para aplicativos selecionados](#additional-considerations-for-selected-applications) na seção [Usando a ferramenta de Descoberta Eletrônica de Pesquisa de Conteúdo para responder a DSRs](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs) para saber mais sobre como acessar, exibir e exportar dados de aplicativos do OneDrive for Business e do SharePoint Online.

#### <a name="deleting-a-sharepoint-user-profile"></a>Excluir um perfil de usuário do SharePoint

O perfil de usuário do SharePoint será permanentemente excluído 30 dias depois que a conta de usuário for excluída no Azure Active Directory. No entanto, você pode excluir irreversivelmente a conta do usuário, o que removerá o perfil de usuário do SharePoint. Para saber mais, confira a seção [Excluir um usuário neste guia](#deleting-a-user).

Um administrador pode acelerar a exclusão do Perfil de Usuário de um usuário usando o cmdlet **Remove-SPOUserProfile** no PowerShell do SharePoint Online. Veja [Remove-SPOUserProfile](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spouserprofile?view=sharepoint-ps). Isso requer que o usuário seja pelo menos excluído por software no Azure Active Directory.

#### <a name="deleting-user-information-lists-on-sharepoint-online-sites"></a>Excluir listas de informações do usuário em sites do SharePoint Online

Para usuários que saíram da organização, esses dados permanecem em sites com os quais eles interagiram, para a integridade referencial de campos de coluna do SharePoint. Um administrador pode excluir todas as propriedades de Informações do Usuário para um usuário em determinado site usando o comando **Remove-SPOUserInfo** no PowerShell do SharePoint Online. Veja [Remove-SPOUserInfo](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spouserinfo?view=sharepoint-ps) para obter informações sobre como executar esse cmdlet do PowerShell.

Por padrão, esse comando manterá o nome de exibição do usuário e excluirá propriedades desnecessárias, como número de telefone endereço de email, habilidade e competências, ou outras propriedades que foram copiadas do perfil de usuário do SharePoint Online. O administrador pode usar o parâmetro **RedactUser** para especificar um nome de exibição alternativo para o usuário na lista de Informações do Usuário. Isso afeta várias partes da experiência do usuário e resultará em perda de informações ao ser examinado o histórico de arquivos no site.

Por fim, o recurso de edição não removerá dos documentos todos os metadados ou conteúdo que fazem referência a um usuário. A maneira de realizar a edição de conteúdo de arquivo e metadados é descrita na seção [Fazer alterações no conteúdo do OneDrive for Business e do SharePoint Online](#making-changes-to-content-in-onedrive-for-business-and-sharepoint-online) deste guia. Esse método consiste em baixar, excluir e carregar uma cópia editada do arquivo.

#### <a name="deleting-onedrive-for-business-experience-settings"></a>Excluir configurações de experiência do OneDrive for Business

A maneira recomendada de excluir todas as configurações e informações da experiência do OneDrive for Business é remover o site do OneDrive for Business do usuário, após a reatribuição de quaisquer arquivos retidos para outros usuários. Um administrador pode excluir essas listas usando um [Script do PowerShell](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6)  e [comandos de CSOM (Modelo de Objeto do Lado do Cliente do SharePoint)](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-client-library-code). Confira [Excluir as configurações da experiência do OneDrive for Business para saber mais sobre as configurações](https://docs.microsoft.com/sharepoint/delete-odfb-lists), como elas são armazenadas e como excluí-las.

#### <a name="onedrive-for-business-and-sharepoint-online-search-queries"></a>Consultas de pesquisa do OneDrive for Business e SharePoint Online

As consultas de pesquisa de um usuário criadas na experiência de pesquisa do OneDrive for Business e SharePoint Online são excluídas automaticamente 30 dias depois que o usuário cria a consulta.

### <a name="deleting-items-in-exchange-online-mailboxes"></a>Excluir itens em caixas de correio do Exchange Online

Talvez você tenha que excluir itens nas caixas de correio do Exchange Online para atender a uma solicitação de exclusão de DSR. O administrador de TI pode excluir itens da caixa de correio de duas maneiras, dependendo de como deseja excluir os itens de destino: por exclusão temporária ou exclusão irreversível. Como os documentos nos sites do SharePoint Online ou OneDrive for Business, os itens em uma caixa de correio que está em retenção não podem ser excluídos permanentemente do Office 365. A retenção deve ser removida para que o item possa ser excluído. Novamente, você terá que determinar se a retenção na caixa de correio ou a solicitação de exclusão de DSR tem precedência.

#### <a name="soft-delete-mailbox-items"></a>Exclusão temporária dos Itens de caixa de correio

Você pode usar a funcionalidade Ação de Pesquisa de Conteúdo para excluir temporariamente itens que são retornados por uma Pesquisa de Conteúdo.  Como explicado anteriormente, os itens excluídos temporariamente são movidos para a pasta Itens Recuperáveis na caixa de correio.

Veja a seguir uma visão geral rápida desse processo:

1. Crie e execute uma Pesquisa de Conteúdo para encontrar os itens que deseja excluir da caixa de correio do usuário. Talvez você tenha que executar novamente a pesquisa a fim de limitar os resultados para que apenas os itens que você deseja excluir sejam retornados.
2. Use o comando **New-ComplianceSearchAction** **-Purge** no PowerShell do Office 365 para excluir temporariamente os itens que são retornados pela Pesquisa de Conteúdo que foi criada na etapa anterior.

Para obter instruções detalhadas, confira [Pesquisar e excluir mensagens de email em sua organização](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).

#### <a name="hard-delete-mailbox-items"></a>Exclusão irreversível dos Itens de caixa de correio

Caso tenha que excluir irreversivelmente itens de caixa de correio em resposta à solicitação de exclusão de DSR, você poderá usar o comando **Search-Mailbox -DeleteContent** no PowerShell do Exchange Online. Ao usar esse método, considere o uso da Pesquisa de Conteúdo para desenvolver e refinar uma consulta de pesquisa de modo que apenas os itens que devem ser excluídos sejam retornados na pesquisa. Depois você pode usar essa sintaxe de consulta quando executar o comando **Search-Mailbox -DeleteContent**.

Para obter instruções detalhadas, confira [Pesquisar e excluir mensagens](https://technet.microsoft.com/library/ff459253(v=exchg.150).aspx).

#### <a name="hard-delete-items-in-a-mailbox-on-hold"></a>Exclusão irreversível de itens em uma caixa de correio em retenção

Conforme explicado anteriormente, se você excluir irreversivelmente itens de uma caixa de correio em retenção, os itens não serão removidos da caixa de correio. Eles serão movidos para uma pasta oculta na pasta Itens Recuperáveis (a pasta **Limpezas**) e permanecerão nela até que o tempo de retenção do item expire ou até que a retenção seja removida da caixa de correio. Quando isso acontecer, os itens serão limpos do Office 365 na próxima vez que a caixa de correio for processada.

Sua organização pode determinar que os itens que forem excluídos permanentemente quando o período de retenção expirar atendam aos requisitos de uma solicitação de exclusão de DSR. No entanto, se você determinar que os itens de caixa de correio devem ser imediatamente limpos do Office 365, será preciso remover a retenção da caixa de correio e, em seguida, excluir irreversivelmente os itens da caixa de correio. Para obter instruções detalhadas, confira [Excluir itens da pasta Itens recuperáveis das caixas de correio baseadas em nuvem em retenção](https://docs.microsoft.com/microsoft-365/compliance/delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold).

>[!NOTE]
>Para excluir irreversivelmente os itens de caixa de correio a fim de atender a uma solicitação de exclusão de DSR seguindo o procedimento no tópico anterior, você pode ter que excluir temporariamente esses itens enquanto a caixa de correio ainda estiver em retenção para que eles sejam movidos para a pasta Itens Recuperáveis.

## <a name="deleting-a-user"></a>Excluir um usuário

Além de excluir dados pessoais em resposta a uma solicitação de exclusão de DSR, o "direito de ser esquecido" de um titular de dados também pode ser cumprido pela exclusão da respectiva conta de usuário. Veja a seguir alguns motivos pelos quais você talvez queira excluir um usuário:

- O titular dos dados saiu (ou está em processo de saída) da sua organização.
- O titular dos dados solicitou que você exclua logs gerados pelo sistema que foram coletados sobre ele. Exemplos de dados nos logs gerados pelo sistema incluem dados de uso de serviço e aplicativo do Office 365, informações sobre solicitações de pesquisa realizadas pelo titular dos dados, bem como dados gerados por produtos e serviços como um produto da funcionalidade do sistema e interação por usuários ou outros sistemas. Para obter mais informações, confira [Parte 3: Responder às DSRs para logs gerados pelo sistema](#part-3-responding-to-dsrs-for-system-generated-logs) neste guia.
- Impedir permanentemente que o titular dos dados acesse ou processe dados no Office 365 (em contraposição ao acesso temporariamente restrito pelos métodos descritos na seção [Responder às solicitações de restrição de DSR](#responding-to-dsr-restriction-requests).

Após excluir uma conta de usuário:

- O usuário não pode mais entrar no Office 365 nem acessar nenhum dos recursos da Microsoft da sua organização, como a conta do OneDrive for Business, sites do SharePoint Online ou a caixa de correio do Exchange Online.
- Os dados pessoais, como endereço de email, alias, número de telefone e endereço para correspondência, que estão associados à conta do usuário são excluídos
- Alguns aplicativos do Office 365 removem informações sobre o usuário. Por exemplo, no Microsoft Flow, o usuário excluído é removido da lista de proprietários de um fluxo compartilhado.
- Os logs gerados pelo sistema sobre o titular dos dados, com exceção dos dados que possam comprometer a segurança ou estabilidade do serviço, serão excluídos 30 dias após a exclusão da conta do usuário. Para saber mais, confira a seção [Excluir logs gerados pelo sistema](#deleting-system-generated-logs).

>[!IMPORTANT]
>Depois de excluir uma conta de usuário, essa pessoa perderá a capacidade de entrar no Office 365 e de entrar em qualquer outro produto ou serviço dos quais ela dependia antigamente para uma conta corporativa ou de estudante. Essa pessoa também não poderá iniciar qualquer solicitação DSR por meio da Microsoft diretamente em instâncias onde a Microsoft é o controlador de dados. Para saber mais, confira a seção [Produtos e serviços autenticados com uma ID de organização para a qual a Microsoft é um controlador de dados](#product-and-services-authenticated-with-an-org-id-for-which-microsoft-is-a-data-controller), na Parte 4 deste guia.

>[!NOTE]
>Se você for um cliente envolvido atualmente com migrações do FastTrack, a exclusão da conta de usuário não excluirá a cópia dos dados em posse da equipe do Microsoft FastTrack, mantida apenas para a conclusão da migração. Se, durante a migração, você quiser que a equipe do Microsoft FastTrack também exclua a cópia dos dados, [envie uma solicitação](https://go.microsoft.com/fwlink/?linkid=874544). No curso normal dos negócios, o Microsoft FastTrack excluirá todas as cópias dos dados após a conclusão da migração.

Como a exclusão temporária e a exclusão irreversível de dados que foram descritas na seção anterior sobre como excluir dados pessoais, quando você exclui uma conta de usuário, também há um estado de exclusão temporária e exclusão irreversível.

- Quando você inicialmente exclui uma conta de usuário (excluindo o usuário no centro de administração ou no portal do Azure), ela é excluída temporariamente e movida para a Lixeira do Azure por até 30 dias.  Nesse ponto, a conta de usuário pode ser restaurada.
- Se você excluiu permanentemente a conta de usuário, ela será excluída irreversivelmente e removida da Lixeira no Azure. Nesse ponto, a conta de usuário não pode ser restaurada e todos os dados associados a ela serão permanentemente removidos da nuvem da Microsoft. A exclusão irreversível de uma conta exclui os logs gerados pelo sistema sobre o titular dos dados, exceto os dados que podem comprometer a segurança ou a estabilidade do serviço.

Veja a seguir o processo detalhado para excluir um usuário da sua organização.

1. Vá para o centro de administração ou portal do Azure e localize o usuário.

2. Exclua o usuário. Quando você inicialmente exclui o usuário, a conta do usuário é enviada para a Lixeira. Nesse ponto, o usuário é excluído temporariamente. Na exclusão temporária, a conta é retida por 30 dias, o que permite restaurá-la. Após 30 dias, a conta é excluída de modo irreversível automaticamente. Para obter instruções específicas, confira [Excluir usuários do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/add-users-azure-active-directory).<br><br> Você também pode excluir temporariamente uma conta no centro de administração. Confira [Excluir um usuário da sua organização](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user). 

3. Se não desejar aguardar 30 das para que a conta de usuário seja excluída irreversivelmente, você pode fazer essa exclusão irreversível de modo manual. Para fazer isso no portal do Azure, vá até a lista de usuários excluídos recentemente e exclua o usuário permanentemente. Nesse ponto, o usuário é excluído irreversivelmente. Para obter instruções, confira [Como excluir permanentemente um usuário excluído recentemente](https://docs.microsoft.com/azure/active-directory/active-directory-users-restore). 

Não é possível excluir irreversivelmente um usuário no portal de administração do Office 365.

>[!NOTE]
>No Office 365 operado pela 21Vianet (China), você não pode excluir permanentemente um usuário conforme descrito anteriormente. Para excluir permanentemente um usuário, você pode enviar uma solicitação por meio do portal de administração do Office 365 nesta [URL](https://portal.partner.microsoftonline.cn/AdminPortal/Home#/homepage). Vá para **Comércio** e selecione **Assinatura** -> **Privacidade** ->  **RGPD** e insira as informações necessárias.

### <a name="removing-exchange-online-data"></a>Remover dados do Exchange Online

O que precisa ser compreendido ao excluir um usuário é o que acontece com a caixa de correio do Exchange Online do usuário. Depois que a conta do usuário é excluída irreversivelmente (na etapa 3 do processo anterior), a caixa de correio excluída do usuário não é limpa automaticamente do Office 365. Leva até 60 dias depois que a conta de usuário é excluída irreversivelmente para removê-la permanentemente do Office 365. Veja a seguir o ciclo de vida da caixa de correio depois que a conta de usuário é excluída e uma descrição do estado dos dados da caixa de correio durante esse período:

- **Do 1º ao 30º dia** — A caixa de correio pode ser totalmente restaurada pela restauração da conta de usuário excluída temporariamente.
- **Do 31º ao 60º dia** — Por 30 dias, depois que a conta de usuário é excluída irreversivelmente, um administrador da organização poderá recuperar os dados na caixa de correio e importá-los em outra caixa de correio.  Isso permite que as organizações possam recuperar os dados da caixa de correio, caso necessário.
- **Do 61º ao 90º dia** – Um administrador não poderá recuperar os dados na caixa de correio. Os dados da caixa de correio serão marcados para remoção permanente e levará mais 30 dias para que os dados da caixa de correio sejam limpos do Office 365.

Se você determinar que o ciclo de vida dessa caixa de correio não atende aos requisitos da organização para responder a uma solicitação de exclusão de DSR, será possível [contatar o Suporte da Microsoft](https://support.microsoft.com/) *depois* de excluir irreversivelmente a conta do usuário, bem como solicitar a Microsoft que inicie manualmente o processo para remover permanentemente os dados da caixa de correio.  Esse processo para remover permanentemente os dados de caixa de correio começa automaticamente após o 61º dia do ciclo de vida, de modo que não há motivo para contatar a Microsoft depois desse ponto no ciclo de vida.

## <a name="using-in-app-functionality-to-respond-to-dsrs"></a>Usar a funcionalidade no aplicativo para responder às DSRs

Embora a maioria dos Dados do Cliente seja criada e produzida usando os aplicativos descritos na seção anterior, o Office 365 também oferece muitos outros aplicativos que os clientes podem usar para produzir e armazenar Dados do Cliente. No entanto, a Pesquisa de Conteúdo atualmente não tem a capacidade de encontrar dados criados nesses outros aplicativos do Office 365. Para encontrar dados gerados por esses aplicativos, você ou o proprietário dos dados devem usar a funcionalidade ou os recursos no produto para encontrar dados que possam ser relevantes para uma DSR. A tabela a seguir lista esses aplicativos do Office 365. Clique no ícone do aplicativo para ir até a seção neste guia que descreve como responder às solicitações DSR para dados criados no aplicativo.

***Tabela 3: Aplicativos em que a funcionalidade no aplicativo pode ser usada para encontrar Dados do Cliente***

||||
|:-----:|:-----:|:-----:|:-----:|
| ![Ícone do Access](../media/o365-access-64x64.png) <br> [Access](#access) | ![Ícone do Office](../media/O365-DSR-Doc_image22.png) <br> [Aplicativo para empresas <br> do Office 365](#business-apps-for-office-365) | ![Ícone do Office](../media/O365-DSR-Doc_image22.png) <br> [Educação](#education)|
| ![Ícone de Fluxo](../media/o365-flow-64x64.png) <br> [Fluxo](#flow) | ![Ícone do Forms](../media/o365-forms-64x64.png) <br> [Forms](#forms) |![Ícone do Kaizala](../media/o365-kaizala-64x64.png) <br> [Kaizala](#kaizala) |
| ![Ícone do Planner](../media/o365-planner-64x64.png) <br> [Planner](#planner) |![Ícone do PowerApps](../media/o365-powerapps-64x64.png) <br> [Power Apps](#powerapps) |![Ícone do Power BI](../media/o365-powerbi-64x64.png) <br> [Power BI](#power-bi) |
|![Ícone do Project](../media/o365-project-64x64.png) <br> [Project](#project-online) |![Ícone do Publisher](../media/o365-publisher-64x64.png) <br> [Publisher](#publisher) |![Ícone do Stream](../media/o365-stream-64x64.png) <br> [Stream](#stream) |![Ícone do Sway](../media/o365-sway-64x64.png) <br> [Sway](#sway) | ![Ícone do quadro de comunicações](../media/O365-DSR-Doc_image36.png) <br> [Quadro de comunicações](#whiteboard) |
|![Ícone do Yammer](../media/o365-yammer-64x64.png) <br> [Yammer](#yammer) |
|||

### <a name="access"></a>Access

As seções a seguir explicam como usar a funcionalidade no aplicativo do Microsoft Access para localizar, acessar, exportar e excluir dados pessoais.

##### <a name="discover"></a>Descobrir

Há várias maneiras de pesquisar registros em um banco de dados do Access que podem estar respondendo a uma solicitação de DSR. Para uma investigação de DSR, você pode procurar registros relacionados ao titular dos dados ou procurar registros que contêm dados específicos. Por exemplo, você pode pesquisar ou acessar um registro que corresponde ao titular dos dados. Ou então, pode procurar registros que contêm dados específicos, como dados pessoais sobre o titular dos dados. Para saber mais, confira:

- [Localizar registros em um banco de dados do Access](https://support.microsoft.com/pt-BR/office/find-records-in-an-access-database-705220b7-0255-4ef9-9349-6bd7442d1b7e) 
- [Criar uma consulta de seleção simples](https://support.office.com/article/create-a-simple-select-query-de8b1c8d-14e9-4b25-8e22-70888d54de59)

##### <a name="access"></a>Access

Depois de localizar registros ou campos que são relevantes para a solicitação de DSR, você pode criar um instantâneo dos dados ou exportá-los para um arquivo do Excel, um arquivo do Word ou um arquivo de texto. Você também pode criar e imprimir um relatório com base em uma fonte de registro ou uma consulta de seleção que criou para encontrar os dados. Confira:

- [Introdução aos relatórios no Access](https://support.office.com/article/introduction-to-reports-in-access-e0869f59-7536-4d19-8e05-7158dcd3681c)
- [Exportar dados para o Excel](https://support.office.com/article/export-data-to-excel-64e974e6-ae43-4301-a53e-20463655b1a9)
- [Exportar dados para um documento do Word](https://support.microsoft.com/pt-BR/office/export-access-data-to-a-word-document-6e954c8e-2243-4cb9-8544-607e5b7bfc12)
- [Exportar dados para um arquivo de texto](https://support.microsoft.com/pt-BR/office/export-data-to-a-text-file-f72dfc38-a8a0-4c5b-8c2c-bf2950814140)

##### <a name="export"></a>Exportar

Como explicado anteriormente, você pode exportar dados de um banco de dados do Access para formatos de arquivos diferentes. O formato de arquivos que você escolhe para a exportação pode ser determinado pela solicitação de DSR específica de um titular de dados. Confira [Importar e exportar](https://support.microsoft.com/pt-BR/office/import-and-export-c060505b-d8ac-4499-8879-733e56c6106f) para obter uma lista de tópicos que descrevem como exportar dados do Access para diferentes formatos de arquivo.

##### <a name="delete"></a>Excluir

Você pode excluir um registro inteiro ou apenas um campo de um banco de dados do Access. A maneira mais rápida de excluir um registro de um banco de dados do Access é abrir a tabela no modo Folha de dados, selecionar o registro (linha) ou apenas os dados em um campo que você deseja excluir e pressionar Excluir. Você também pode usar uma consulta de seleção que criou para localizar dados e convertê-la em uma consulta de exclusão.  Confira:

- [Excluir um ou mais registros de um banco de dados](https://support.office.com/article/ways-to-add-edit-and-delete-records-5e90a80c-106d-4c55-996e-07d7200980ce)
- [Criar e executar uma consulta exclusão](https://support.office.com/article/create-and-run-a-delete-query-6da65fe1-0fc7-4a64-8ef0-c052cd4c3ec5)

### <a name="business-apps-for-office-365"></a>Aplicativos para empresas do Office 365

Esta seção explica como usar a funcionalidade no aplicativo em cada um dos Aplicativos de Negócios do Office 365 a seguir para responder a solicitações de DSR.

- [Bookings](#bookings)
- [Listings](#listings)
- [Connections](#connections)
- [Outlook Customer Manager](#outlook-customer-manager)
- [Faturas](#invoicing)

#### <a name="bookings"></a>Reservas

As seções a seguir explicam como usar a funcionalidade no aplicativo do Microsoft Bookings para localizar, acessar, exportar e excluir dados pessoais. Isso se aplica ao aplicativo Bookings autônomo e Bookings quando acessado por meio do Centro de Empresas.

O Microsoft Bookings permite que administradores e usuários ou funcionários com uma licença do Bookings em sua organização configurem páginas de reserva para que os clientes possam agendar e fazer alterações em compromissos e receber emails de confirmação, atualizações, cancelamento e lembretes. Os proprietários de empresas e suas equipes também podem agendar eventos em nome de clientes com o Bookings. 

Os seguintes tipos de dados são criados pelos clientes, administradores ou funcionários:

- **Informações de contato de clientes, parceiros e amigos. ** Esses dados contêm nome, número de telefone, endereço de email, endereço e anotações.

    - Contatos de qualquer pessoa podem ser criados manualmente usando os clientes do Bookings para a Web, para iOS e Android.
    
    - Contatos de qualquer pessoa podem ser importados de um dispositivo móvel de C1 para o Bookings com os clientes do Bookings para iOS e Android.
    
    - Contatos também são criados automaticamente no momento da criação da reserva no fluxo de trabalho de reserva para qualquer pessoa que esteja reservando, quer a reserva seja criada por um usuário em nome do cliente, quer seja criada pelo cliente usando a página de reserva do proprietário.

- **Eventos de reserva** – Estas são as reuniões entre o proprietário da empresa ou o funcionário designado e um cliente, que pode ser criada pelo proprietário da empresa ou pelo cliente através da página pública de reserva do proprietário da empresa. Esses dados incluem nome, endereço, endereço de email, telefone e outras informações que o proprietário da empresa coleta do cliente no momento da reserva.

- **Confirmações/cancelamentos/atualizações de email** – Estas são as mensagens de email geradas e enviadas pelo sistema em associação a eventos de reserva específicos. Elas contêm dados pessoais sobre os funcionários que estão agendados para prestar o serviço relevante e contêm dados pessoais sobre o cliente que foram inseridos pelo proprietário da empresa ou pelo cliente no momento da reserva.

Todo o conteúdo do cliente é armazenado na caixa de correio do Exchange Online que hospeda o Bookings da organização. Esse conteúdo é mantido enquanto o proprietário da empresa e os clientes estiverem ativos no serviço, a menos que eles explicitamente solicitem que os dados sejam excluídos ou caso eles saiam do serviço.  Esse conteúdo pode ser excluído por meio da interface do usuário no produto, com um cmdlet ou por meio da exclusão da caixa de correio de reserva relevante. Após o início da ação de exclusão, os dados serão excluídos no período de tempo definido pelo proprietário da empresa.  

Se um cliente decide deixar o serviço, o conteúdo do cliente é excluído após 90 dias. Para saber mais sobre quando o conteúdo da caixa de correio é excluído depois que uma conta de usuário é excluída, confira [Remover dados do Exchange Online](#removing-exchange-online-data). 

#### <a name="end-user-identifiable-information"></a>Informações de identificação de usuário final

As EUII (Informações de Identificação do Usuário Final) incluem informações pessoais e de contato sobre a equipe que é agendada no Bookings. Elas são adicionadas às páginas de detalhes da Equipe quando o proprietário da empresa configura o Bookings e faz atualizações após a instalação. Elas contêm o nome, as iniciais, o endereço de email e o número de telefone do membro da equipe. Esses dados são armazenados na caixa de correio do Exchange Online que hospeda o Bookings.

Esses dados são mantidos enquanto o membro da equipe estiver ativo no serviço, a menos que ele seja excluído explicitamente pelo proprietário da empresa ou por um administrador usando a interface do usuário no aplicativo ou excluindo a caixa de correio de reserva relevante. Quando o administrador inicia a exclusão dos detalhes da equipe ou o membro da equipe deixa o serviço, os detalhes são excluídos de acordo com as políticas de retenção do conteúdo de caixa de correio do Exchange Online definidas pelo proprietário da empresa ou pelo administrador.

##### <a name="discoveraccess"></a>Descobrir/Acessar

O Bookings reúne e armazena os seguintes tipos de dados:

- **Informações do perfil da empresa:** o conteúdo do cliente sobre a empresa usando o Bookings é coletado por meio do formulário de informações comerciais do Bookings e é sincronizado com o Perfil Comercial do Centro de Negócios se um cliente estiver usando o Bookings juntamente com o Centro de Negócios. O único EUII associado a esses dados é um endereço de email de C1. As novas notificações de reserva e os emails de atualização são enviados para este email.
- **Contatos do cliente:** Os contatos podem ser criados manualmente nos clientes Web, iOS e Android do Bookings ou podem ser importados de um dispositivo móvel. Os contatos também são criados automaticamente durante o uso da página de reserva de autoatendimento. Eles contêm EUII e são armazenados na caixa de correio do Bookings.
- **Detalhes da equipe:** o conteúdo do cliente inclui dados sobre a equipe qualificada para fornecer os serviços criados a partir dos clientes da Bookings Web, iOS ou Android. Os detalhes da equipe podem conter nome, endereço de email e número de telefone.
- **Eventos de reserva:** são reuniões de clientes e conteúdo de clientes relacionado criado pela empresa usando um cliente Web ou aplicativo Android/iOS ou criado pelo cliente usando uma página de reserva pública (ou uma página do Facebook). Esses eventos podem incluir nome, endereço, endereço de email, número de telefone e detalhes do compromisso.
- **Solicitações de reunião, confirmações/cancelamentos/atualizações por email e lembretes por email:** são mensagens de email enviadas pelo sistema associadas a reservas. Elas contêm os dados de funcionários e dados de clientes que foram inseridas no momento da reserva.

##### <a name="export"></a>Exportar

Para exportar dados correspondentes ao proprietário da empresa, aos funcionários e aos clientes, você pode usar o portal de privacidade do Centro de empresas. Veja [Exportar ou excluir dados de usuário usando o portal de privacidade do Centro de empresas](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>Excluir

Você pode excluir os seguintes tipos de dados do Bookings em resposta a uma solicitação de exclusão de DSR:

- **Informações de perfil e negócios e contatos:** você pode excluir a caixa de correio do Bookings no centro de administração. Depois de excluir a caixa de correio, é possível restaurá-la com 30 dias. Após 30 dias, a conta do usuário e a caixa de correio correspondente são excluídas permanentemente. Para obter detalhes sobre como excluir uma conta de usuário, confira a seção [Excluir um usuário](#deleting-a-user).
- **Detalhes da equipe:** Você pode excluir a equipe do painel do Bookings. Para detalhar permanentemente a equipe, você pode excluir a conta do Office 365.
- **Eventos do Bookings:** você pode excluir eventos de reservas do calendário do Bookings, o que removerá as informações do cliente.
- **Solicitações de reunião, confirmações/cancelamentos/atualizações por email e lembretes por email:** você pode excluí-los do calendário do Bookings, o que removerá as informações do cliente.

Os administradores e os proprietários de empresas também podem excluir dados do cliente usando o portal de privacidade do Centro de Empresas. Veja [Exportar ou excluir dados de usuário usando o portal de privacidade do Centro de Empresas](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

Além disso, você pode excluir dados de funcionários e do proprietário da empresa e pode excluir a conta de usuário correspondente. Veja a seção[Excluir um usuário](#deleting-a-user).

#### <a name="listings"></a>Listings

As seções a seguir explicam como usar a funcionalidade no aplicativo do Microsoft Listings para localizar, acessar, exportar e excluir dados pessoais. 

##### <a name="discover"></a>Descobrir

O proprietário do Listings pode conectar seus negócios ao Google, ao Bing, ao Yelp e ao Facebook para obter uma exibição agregada de classificações e avaliações.  O Listings coleta e armazena os seguintes tipos de dados:

- Classificações e avaliações do Google
- Classificações e avaliações do Bing
- Classificações e avaliações do Yelp
- Classificações e avaliações do Facebook

##### <a name="access"></a>Acessar
O proprietário do Listings pode entrar no painel Listings para ver suas avaliações e classificações.

##### <a name="export"></a>Exportar

Para exportar dados do proprietário da empresa, de funcionários e de clientes, use o portal de privacidade do Centro de empresas. Ver [exportar ou excluir dados de usuário usando o portal de privacidade do Centro de Empresas](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>Excluir

Se um proprietário do Listings quiser excluir as informações do Listings, poderá se desconectar do provedor na página do Listings. Depois que ele se desconectar, suas informações do Listings serão excluídas.

#### <a name="connections"></a>Conexões

As seções a seguir explicam como usar a funcionalidade no aplicativo para localizar, acessar, exportar e excluir dados pessoais.

##### <a name="discover"></a>Descobrir

O Connections coleta e armazena os seguintes tipos de dados: 

- Os clientes/contatos são criados pela empresa usando o cliente da Web ou o aplicativo móvel (iOS e Android) ou usando o aplicativo quando uma campanha de marketing por email é enviada a um contato de negócios. Os dados de clientes podem incluir nome, endereço, endereço de email e número de ID fiscal. Os contatos são compartilhados em todos os aplicativos do Centro de Empresas.
- Os clientes podem se inscrever na página de inscrição do Connections e salvar suas informações pessoais.
- Links de campanhas de email

##### <a name="access"></a>Acessar

Um proprietário do Connections pode entrar no painel do Connections e ver as campanhas de email que enviou.

##### <a name="export"></a>Exportar

Para exportar dados do proprietário da empresa, de funcionários e de clientes, use o portal de privacidade do Centro de empresas. Ver [exportar ou excluir dados de usuário usando o portal de privacidade do Centro de Empresas](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>Excluir

Depois que um proprietário do Connections envia uma campanha de email, ele não pode excluir a campanha. Se houver campanhas de rascunho que deseje excluir, ele poderá entrar no painel do Connections e excluir as campanhas de rascunho.

#### <a name="outlook-customer-manager"></a>Outlook Customer Manager

As seções a seguir explicam como usar a funcionalidade no aplicativo do Outlook Customer Manager para localizar, acessar, exportar e excluir dados pessoais.

##### <a name="discover"></a>Descobrir

O Outlook Customer Manager reúne e armazena informações de usuário para o proprietário do Outlook Customer Manager e seus clientes e contatos de negócios.

- Dados do proprietário. Isso inclui nome, endereço e email endereço. Documentos e arquivos que um proprietário compartilha com um cliente são armazenados no OneDrive for Business, no SharePoint Online e como tarefas no Outlook.
- Dados de contatos de negócios e clientes. Dados de clientes podem incluir nome, endereço e endereço de email. Dados de cliente e contato são criados pela empresa no Outlook ou no Outlook Web app. Contatos são compartilhados no Centro de empresas. Documentos e arquivos que um cliente compartilha com uma empresa são armazenados no OneDrive for Business, no SharePoint Online e como tarefas no Outlook.

O Outlook Customer Manager também armazena atividades e informações sobre os clientes do Exchange.

##### <a name="access"></a>Acessar

Proprietários do Outlook Customer Manager podem entrar no Outlook ou no Outlook Web app e acessar o painel do Outlook Customer Manager para ver as interações que tiveram com seus clientes.

##### <a name="export"></a>Exportar

Para exportar dados do proprietário da empresa e de clientes, use o portal de privacidade do Outlook Customer Manager. Para obter detalhes, veja [Exportar ou excluir dados de usuário usando o portal de privacidade do Outlook Customer Manager](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>Excluir

Para excluir dados dos clientes, use o portal de privacidade do Outlook Customer Manager. Veja [Exportar ou excluir dados de usuário usando o portal de privacidade do Outlook Customer Manager](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

#### <a name="invoicing"></a>Faturas

As seções a seguir explicam como usar a funcionalidade no aplicativo do Microsoft Invoicing para localizar, acessar, exportar e excluir dados pessoais.

##### <a name="discover"></a>Descobrir

O faturamento coleta e armazena os seguintes tipos de dados:

- **Contatos:** são criados pela empresa quando uma fatura ou estimativa é criada para um contato de cliente/empresa. Os Contatos são compartilhados no Centro de negócios. Os Dados de cliente incluem nome, endereço, endereço de email e números de ID do imposto.
- **Faturas:** são criadas e enviadas aos clientes e representam uma dívida e um passivo fiscal.
- **Estimativas:** a empresa também pode enviar estimativas para os clientes. Se um cliente aceitar uma estimativa, ela é convertida em uma fatura. Uma estimativa é convertida em uma fatura depois que ela é aceita pelo cliente. Os registros das estimativas não são mantidos após serem convertidass em uma fatura.

##### <a name="access"></a>Acessar

Os usuários podem acessar o painel Faturamento na Central de Empresas para ver os rascunhos das faturas que criaram e das faturas que enviaram aos clientes.

##### <a name="export"></a>Exportar

Para exportar dados de faturamento do cliente, use o portal de privacidade do Centro de empresas. Veja [Exportar ou excluir dados de usuário usando o portal de privacidade do Centro de Empresas](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>Excluir

Depois que uma fatura é criada e enviada, ela não pode ser excluída devido às leis de contabilidade. O proprietário do Faturamento pode solicitar que a Microsoft exclua algumas de suas informações do Office 365 ou todas elas.

Como alternativa, você pode excluir a conta de usuário do proprietário de faturamento no Office 365. Veja a seção [Excluir um usuário](#deleting-a-user).

### <a name="education"></a>Educação

Esta seção explica como usar a funcionalidade no aplicativo dos seguintes aplicativos do Microsoft Education para responder a solicitações de DSR.

- Atribuições
- Bloco de Anotações de Classe

#### <a name="assignments"></a>Atribuições

As seções a seguir explicam como usar a funcionalidade no aplicativo do Assignments para localizar, acessar, exportar e excluir dados pessoais.

##### <a name="discoveraccess"></a>Descobrir/Acessar

As tarefas armazenam informações geradas por professores e alunos. Algumas dessas informações são armazenadas no SharePoint e outras são armazenadas em um local que não o SharePoint.

##### <a name="finding-assignments-data-stored-in-sharepoint"></a>Localizar dados de tarefas armazenados no SharePoint

Arquivos de alunos associados a um envio de tarefa são armazenados na biblioteca de documentos (chamada **Trabalho do Aluno**), e arquivos associados a tarefas e criados por professores (acessíveis a alunos) são armazenados em uma biblioteca de documentos diferente (chamada **Arquivos da Classe**). As duas bibliotecas de documentos estão no site do SharePoint de Equipe de Classe correspondente.

Um administrador pode usar a ferramenta Pesquisa de Conteúdo no Centro de Conformidade e Segurança para procurar arquivos de alunos (nas bibliotecas de Trabalho do Aluno e Arquivos da Classe) relacionados a envios em tarefas e arquivos relacionados a tarefas. Por exemplo, um administrador pode pesquisar todos os sites do SharePoint na organização e usar o nome do aluno e o nome da classe ou da tarefa na consulta de pesquisa para encontrar dados relevantes a uma solicitação DSR.

Da mesma forma, um administrador pode pesquisar arquivos de professores relacionados a tarefas de arquivos que um professor distribuiu aos alunos. Por exemplo, um administrador pode pesquisar todos os sites do SharePoint na organização e usar o nome do professor e a classe ou o nome da tarefa na consulta de pesquisa para localizar dados relevantes para uma solicitação DSR.

Para saber mais, confira:

- [Documentação do Administrador de Tarefas ](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-admin-documentation)
- [Usar a ferramenta de Descoberta Eletrônica de Pesquisa de Conteúdo para responder a DSRs](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs) (neste guia)

##### <a name="finding-assignments-data-not-stored-in-sharepoint"></a>Localizar dados de tarefas não armazenados no SharePoint

Os seguintes tipos de dados de Tarefas não são armazenados no site do SharePoint de equipe de classe e, portanto, não podem ser descobertos usando a Pesquisa de Conteúdo.  Esses dados incluem o seguinte:

- Notas do aluno e comentários do professor
- A lista de documentos enviados para uma atribuição por cada aluno
- Detalhes da tarefa, como data de vencimento da tarefa

Para encontrar dados, um administrador ou um professor deve acessar a tarefa no site de Equipe de Classe para localizar dados que podem ser relevantes a uma solicitação de DSR. Um administrador pode adicionar a si mesmo como um proprietário para a classe e exibir todas as tarefas da equipe da classe.

Mesmo que um aluno não faça mais parte de uma classe, os dados podem ainda estar presentes na classe e ser marcados como “não matriculado”. Nesse caso, um aluno que envia uma solicitação de DSR precisa fornecer ao administrador a lista de classes em que foi formalmente matriculado.

##### <a name="export"></a>Exportar

Você pode exportar dados de tarefas de um aluno específico para todas as classes nas quais o aluno está inscrito usando um script do PowerShell para obter uma lista de classes para o aluno e usar um script do PowerShell para exportar os dados. Confira:

- [Configurar Tarefas para o Teams](https://docs.microsoft.com/microsoft-365/education/deploy/configure-assignments-for-teams)
- [Obter uma lista de classes para um aluno específico](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-get)
- [Exportar dados de alunos e professores de tarefas](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-export).

Se o aluno foi removido do Site de Equipe de classe, o administrador pode adicionar o aluno ao site antes de executar o script de exportação. Ou então, o administrador pode usar o arquivo de entrada do script para identificar todas as classes em que o aluno já foi registrado. Você também pode usar o script de exportação de tarefa para exportar dados de envios de todas as tarefas às quais um professor tem acesso.

##### <a name="delete"></a>Excluir

Você pode excluir dados de tarefas de um aluno específico para todas as classes nas quais o aluno está inscrito usando um script do PowerShell para obter uma lista de classes para o aluno e usar um script do PowerShell para excluir os dados. Faça isso antes de remover o aluno da classe. Confira:

- [Configurar Tarefas para o Teams](https://docs.microsoft.com/microsoft-365/education/deploy/configure-assignments-for-teams)
- [Obter uma lista de classes para um aluno específico](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-get)
- [Excluir dados de alunos de Tarefas](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-delete).

Se o aluno foi removido do site de Equipe de Classe, o administrador pode adicionar o aluno de volta ao site antes de executar o script de exportação. Ou então, o administrador pode usar o arquivo de entrada do script para identificar todas as classes em que o aluno já foi registrado. Não é possível usar o script de exclusão de tarefas para excluir dados do professor, pois todas as tarefas são compartilhadas no site de Equipe de Classe. Como alternativa, um administrador precisaria se adicionar ao site de Equipe de Classe e excluir uma tarefa específica.

#### <a name="class-notebook"></a>Bloco de Anotações de Classe

A pesquisa de conteúdo no bloco de anotações de classe é discutida anteriormente neste guia. Veja a seção [Bloco de anotações de classe do OneNote](#onenote-class-notebook). Você também pode usar a ferramenta Pesquisa de Conteúdo para exportar dados de um bloco de anotações de classe. Como alternativa, um administrador ou a entidade de dados pode exportar dados de um bloco de anotações de classe. Confira [Salvar uma cópia de um bloco de anotações de classe](https://support.office.com/article/44733e18-0ef1-4d4b-be51-fc2ac5bfe9ec).

### <a name="flow"></a>Flow

As seções a seguir explicam como usar a funcionalidade no aplicativo do Microsoft Flow para encontrar, acessar, exportar e excluir dados pessoais.

#### <a name="discover"></a>Descobrir

As pessoas podem usar o Flow para executar tarefas relacionadas aos dados, como sincronizar arquivos entre aplicativos, copiar arquivos de um serviço do Office 365 para outro e coletar dados de um aplicativo do Office 365 e armazená-los em outro. Por exemplo, um usuário pode configurar um Flow para salvar anexos de email do Outlook na respectiva conta do OneDrive for Business. Nesse exemplo, você podia usar a ferramenta Pesquisa de Conteúdo para pesquisar a caixa de correio do usuário em busca de mensagens de email que contivessem o anexo ou pesquisar a conta do OneDrive for Business em busca do arquivo. Esse é um exemplo onde os dados manipulados pelo Flow podem ser descobertos nos serviços do Office 365 conectados por um fluxo de trabalho do Flow.

Além disso, as pessoas podem usar o Flow para copiar ou carregar arquivos do Office 365 em um serviço externo, como o Dropbox. Nesses casos, a solicitação DSR referente aos dados em um serviço externo teria que ser enviada ao serviço externo, que processa os dados nesse tipo de cenário.

Se um administrador receber uma solicitação DSR, ele poderá adicionar a si mesmo como um proprietário de fluxos de um usuário. Isso permite que um administrador execute funções, incluindo exportação de definições de fluxo, execução de históricos e reatribuições de permissão de fluxo.  Confira [Gerenciar fluxos no Centro de Administração](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/).

A capacidade de um administrador de adicionar a si mesmo como um proprietário de um Fluxo requer uma conta com as seguintes permissões:

- Licença de Plano 2 do Flow/PowerApps (paga ou versão de avaliação)

- [Administrador global\ ](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)

    ou

- [Administrador global do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)

Ter esses privilégios permite que o administrador use o centro de administração do Flow para acessar todos os fluxos na organização.

Para adicionar a si mesmo como um proprietário de um fluxo.

1. Acesse <https://admin.flow.microsoft.com>
2. Entre com suas credenciais do Office 365.
3. Na página **Ambientes**, clique no ambiente dos fluxos que deseja acessar. As organizações têm um ambiente padrão.
4. Na página do ambiente que você selecionou, clique em **Recursos** e em **Fluxos.** É exibida uma lista de todos os fluxos no ambiente.
5. Clique em **Exibir detalhes** do fluxo ao qual deseja adicionar a si mesmo como um proprietário.
6. Em **Proprietários**, clique em **Gerenciar compartilhamento**.
7. No submenu **Compartilhar**, adicione a si mesmo como um membro e salve a alteração.

Depois de tornar a si mesmo um proprietário, vá para **Fluxo** \> **Meus fluxos** \> **Fluxos da equipe** para acessar o fluxo. No fluxo, você pode baixar o histórico de execuções ou exportar o fluxo. Confira:

- [Baixar histórico de execuções de fluxo](https://flow.microsoft.com/blog/download-history-recurrence/)
- [Exportar e importar seus fluxos entre ambientes com empacotamento](https://flow.microsoft.com/blog/import-export-bap-packages/)

#### <a name="access"></a>Acessar

Um usuário pode acessar as definições e os históricos de execuções de seus fluxos.

- **Definições de fluxo:** Um usuário pode exportar a definição de um fluxo (que é exportado como um pacote Flow, formatado como JSON em um arquivo compactado). Consulte [Exportar e importar seus fluxos entre ambientes usando empacotamento](https://flow.microsoft.com/blog/import-export-bap-packages/).
- **Históricos de execução de fluxo**: um usuário pode fazer o download do histórico de execução de cada um de seus fluxos. Um histórico de execução de fluxo é baixado como um arquivo CSV, que pode ser aberto no Excel para filtrar ou pesquisar. Os usuários também podem baixar o histórico de execução de vários fluxos. Consulte o [Baixar histórico de execução de fluxo](https://flow.microsoft.com/blog/download-history-recurrence/).

#### <a name="delete"></a>Excluir

Um administrador pode a adicionar a si mesmo como proprietário dos fluxos de um usuário no centro de administração do Flow. Se um usuário sair da sua organização e a conta do Office 365 for excluída, os fluxos dos quais ele é o único proprietário serão retidos. Isso serve para ajudar sua organização a fazer a transição dos fluxos para novos proprietários e evitar qualquer interrupção nos negócios para fluxos que possam ser usados para processos de negócios compartilhados. Em seguida, um administrador precisa determinar se deseja excluir os fluxos pertencentes ao usuário ou redistribuí-los a novos proprietários e realizar essa ação. 

Para fluxos compartilhados, quando um usuário é excluído da organização, seu nome é removido da lista de proprietários.

#### <a name="export"></a>Exportar

Um administrador pode exportar a definição e o histórico de execuções de fluxos de um usuário. Para isso, um administrador deve adicionar a si mesmo como um proprietário do fluxo do usuário no centro de administração do Flow.

- **Definições de fluxo:** Depois que um administrador inclui a si mesmo como proprietário de um fluxo, ele pode ir para **Fluxo** \> **Meus fluxos** \> **Fluxos do Teams** para exportar a definição de fluxo (que é exportada como um pacote Flow formatado como JSON em um arquivo compactado). Consulte [Exportar e importar seus fluxos entre ambientes usando empacotamento](https://flow.microsoft.com/blog/import-export-bap-packages/).

- **Históricos de execução de fluxo:** Da mesma forma, um administrador deve adicionar a si mesmo como proprietário de um fluxo para exportar seu histórico de execução de fluxo. O histórico de execução de fluxo é baixado como um arquivo CSV, o que significa que você pode usar o Excel para filtrar ou pesquisar. Você também pode fazer o download do histórico de execução de vários fluxos, desde que seja proprietário. Consulte o [Baixar histórico de execução de fluxo](https://flow.microsoft.com/blog/download-history-recurrence/).

#### <a name="connections-and-custom-connectors-in-flow"></a>Conexões e conectores personalizados no Flow

As conexões exigem que os usuários forneçam credenciais para se conectarem a APIs, aplicativos SaaS e sistemas desenvolvidos personalizados. Essas conexões são de propriedade do usuário que estabeleceu a conexão e podem ser [gerenciadas](https://docs.microsoft.com/flow/add-manage-connections) no produto.  Depois que o Flow tiver sido reatribuído, um administrador poderá usar os cmdlets do PowerShell para listar e excluir essas conexões como parte da exclusão de dados do usuário.

Os conectores personalizados permitem que as organizações estendam os recursos do Flow conectando-se a sistemas em que um conector pronto para uso não está disponível. O autor de um conector personalizado pode [compartilhar](https://docs.microsoft.com/flow/register-custom-api) seu conector com outras pessoas em uma organização.  Depois de receber uma solicitação de exclusão de DSR, um administrador deve considerar a reatribuição da propriedade desses conectores a fim de evitar interrupção nos negócios. Para agilizar esse processo, um administrador pode usar cmdlets do PowerShell para listar, reatribuir ou excluir conectores personalizados.

### <a name="forms"></a>Forms

As seções a seguir explicam como usar a funcionalidade no aplicativo do Microsoft Forms para localizar, acessar, exportar e excluir dados pessoais.

#### <a name="discover"></a>Descobrir

Os usuários do Forms podem acessar <https://forms.office.com> e selecionar **Meus formulários** para ver os formulários que criaram. Eles também podem selecionar **Compartilhado comigo** para exibir formulários que outras pessoas compartilharam por um link. Se houver muitos formulários para classificar, os usuários poderão usar a barra de pesquisa no produto para pesquisar formulários por título ou autor. Para determinar se o Microsoft Forms é o lugar onde provavelmente os dados pessoais responsivos à sua DSR residem, você poderá pedir ao Titular dos Dados para pesquisar sua lista **Compartilhado comigo** a fim de determinar quais usuários ("Proprietários de Formulários") enviaram formulário ao Titular dos Dados. Você pode então pedir que os proprietários de formulários selecionem **Compartilhar** na barra de navegação superior e enviem a você um link para um formulário específico, de modo que seja possível exibi-lo e determinar se ele é essencial à sua DSR.

#### <a name="access"></a>Acessar

Depois que os formulários relevantes forem encontrados, você poderá acessar as respostas ao formulário clicando na guia **Respostas**. Saiba mais sobre como [verificar os resultados do seu teste](https://support.microsoft.com/pt-BR/office/check-and-share-your-quiz-results-c4a9b45c-d62f-4eb7-b5db-ad81892c7c07) ou [resultados do formulário](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af).  Para revisar os resultados da resposta no Excel, selecione a guia **Respostas** e clique em **Abrir no Excel**.  Se você deseja enviar ao Titular dos Dados uma cópia do formulário, será possível fazer capturas de tela das perguntas e respostas relevantes que são mostradas no aplicativo em formato rich text ou enviar ao Titular dos Dados uma cópia dos resultados em Excel.  Se estiver usando o Excel e desejar compartilhar com o Titular dos Dados apenas as partes do resultado da pesquisa, você poderá excluir determinadas linhas ou colunas, ou redigir as seções restantes antes de compartilhar os resultados.  Como alternativa, você pode ir para **Compartilhar \> Obter um link para duplicar** (em Compartilhar como um modelo) para fornecer ao Titular dos Dados uma réplica do formulário inteiro.

#### <a name="delete"></a>Excluir

Qualquer pesquisa, teste, questionário ou sondagem pode ser excluído permanentemente por seu proprietário. Se desejar exercer o direito "esqueça-me" da DSR e excluir um formulário por inteiro, encontre o formulário na lista de formulários, selecione a série de pontos (reticências) no canto superior direito da janela de visualização do formulário e clique em **Excluir**. Depois que um formulário for excluído, ele não poderá ser recuperado. Para obter informações, confira [Excluir um formulário](https://support.microsoft.com/pt-BR/office/delete-a-form-2207e468-ce1b-4c4a-a256-caf631d87af0).

#### <a name="export"></a>Exportar

Para exportar perguntas e respostas do formulário para um arquivo do Excel, abra o formulário, selecione a guia **Respostas** e selecione **Abrir no Excel**.

### <a name="kaizala"></a>Kaizala

As seções a seguir explicam como usar a funcionalidade no aplicativo do Microsoft Kaizala para localizar, acessar, exportar e excluir dados pessoais.

#### <a name="discover"></a>Descobrir

Os dados organizacionais de um usuário, que são dados compartilhados em grupos organizacionais, podem ser acessados por um administrador por meio do portal de gerenciamento do Kaizala. Dados organizacionais são mantidos por um período de tempo determinado pelas políticas de retenção de sua organização. Além de dados do usuário, os servidores do Kaizala também armazenam os seguintes tipos de dados organizacionais:

- Lista de membros que fazem parte dos grupos da organização
- Dados de mensagens de grupos da organização, que são mensagens e respostas compartilhadas entre grupos organizacionais
- Uma lista de usuários nas organizações
- Dados de uso de produtos e serviços capturados para todos os usuários na organização.
- Ações do Kaizala criadas pela organização
- Dados de conectores do Kaizala

Os dados de consumo de um usuário podem ser acessados pelo titular de dados usando o aplicativo móvel do Kaizala para dados de cliente. Os dados de consumo incluem os seguintes tipos de dados:

- Dados que pertencem a grupos privados no Kaizala (armazenadas em servidores do Kaizala por 90 dias)
- Informações de perfil do usuário e os contatos do usuário
- Lista de membros que fazem parte dos mesmos grupos que o usuário
- Mensagens e respostas de grupo compartilhadas em grupos
- Lista de contatos do usuário (armazenada no serviço Kaizala)
- Transações efetuadas pelo usuário no Kaizala (aplica-se a usuários do Kaizala apenas na Índia)
- Dados de uso de produtos e serviços do usuário

#### <a name="access"></a>Acessar

Os usuários do Kaizala podem usar seu dispositivo móvel para ver o conteúdo do Kaizala que você criou em seu dispositivo. Para determinar se os aplicativos móveis do Kaizala são um local onde dados pessoais responsivos a uma DSR provavelmente residem, você pode pedir ao titular de dados que pesquise as informações solicitadas no aplicativo do Kaizala.

#### <a name="export"></a>Exportar

Quando os usuários em sua organização usam o Kaizala, dados de clientes são gerados e dados organizacionais podem ser gerados se o usuário faz parte de um grupo da organização. Os administradores podem exportar dados organizacionais do usuário por meio do portal de gerenciamento do Kaizala. Os usuários do Kaizala podem exportar seus dados privados do aplicativo móvel do Kaizala. Em ambos os casos, observe que os dados de uso de produtos e serviços também são exportados quando um administrador ou usuário exporta dados do Kaizala. Para saber mais, confira:

- [Exportar ou excluir dados organizacionais do usuário no Kaizala](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)
- [Exportar ou excluir seus dados no aplicativo móvel Kaizala](https://docs.microsoft.com/office365/kaizala/export-or-delete-your-data)

#### <a name="delete"></a>Excluir

Um administrador do Kaizala pode remover contas de usuários do Kaizala no portal de gerenciamento do Kaizala. Depois que uma conta de usuário é excluída, o usuário é removido de todos os grupos que pertencem à sua organização, e os dados organizacionais são excluídos de seu dispositivo. 

Para remover todos os dados privados do dispositivo móvel do usuário, o usuário do Kaizala pode excluir a conta do Kaizala. Depois que a conta for excluída, todo o conteúdo relacionado do Kaizala, incluindo conversas, fotos e outros dados, será excluído do dispositivo.

Veja mais detalhes em:

- [Exportar ou excluir dados organizacionais do usuário no Kaizala](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)
- [Exportar ou excluir seus dados no aplicativo móvel Kaizala](https://docs.microsoft.com/office365/kaizala/export-or-delete-your-data)

### <a name="planner"></a>Planner

As seções a seguir explicam como usar a funcionalidade no aplicativo do Microsoft Planner para localizar, acessar, exportar e excluir dados pessoais.

#### <a name="discover"></a>Descobrir

Os planos do Planner são associados a um Grupo do Microsoft 365 e os arquivos desse grupo são armazenados em um site do SharePoint Online associado do grupo. Isso significa que você pode usar a Pesquisa de Conteúdo para encontrar arquivos do Planner pesquisando o site do Grupo do Microsoft 365. Para isso, você precisa ter a URL do Grupo do Microsoft 365. Confira [Pesquisar Grupos do Microsoft 365 e Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/content-search) no tópico de ajuda “Pesquisa de Conteúdo no Microsoft 365” para ver dicas de como obter informações sobre os Grupos do Office 365 que ajudem a pesquisar arquivos do Planner no site do SharePoint Online correspondente.

#### <a name="access"></a>Acessar

Como já explicado, você pode pesquisar o site e a caixa de correio subjacentes do SharePoint Online associados a um plano. Em seguida, você pode visualizar ou baixar os resultados da pesquisa relacionados para acessar os dados.

#### <a name="delete"></a>Excluir

Você pode excluir manualmente as informações pessoais de um usuário fornecendo a si mesmo permissões para acessar os planos dos quais o usuário faz parte ou conectando-se como o usuário para fazer as alterações. Consulte [Excluir dados do usuário no Microsoft Planner](https://support.office.com/article/delete-user-data-in-microsoft-planner-4349ded2-1891-4896-8e27-05fd40f3929f).

#### <a name="export"></a>Exportar

É possível usar um script do PowerShell para exportar dados de um usuário do Planner. Quando você exporta os dados, um arquivo JSON separado é exportado para cada plano do qual o usuário faz parte. Consulte [Exportar dados do usuário do Microsoft Planner](https://support.office.com/article/export-user-data-from-microsoft-planner-91258c96-b353-4da1-b6d9-d78e4809cf08).

### <a name="power-bi"></a>Power BI

As seções a seguir explicam como usar a funcionalidade no aplicativo do Microsoft Power BI para localizar, acessar, exportar e excluir dados pessoais.

#### <a name="discover"></a>Descobrir
Você pode procurar conteúdo nos diferentes espaços de trabalho do Power BI, incluindo painéis, relatórios, pastas de trabalho e conjuntos de dados. Cada tipo de espaço de trabalho contém um campo de pesquisa que você pode usar para pesquisar esse espaço de trabalho. Veja [Pesquisar, localizar e classificar o conteúdo no serviço do Power BI](https://docs.microsoft.com/power-bi/service-navigation-search-filter-sort).

#### <a name="access"></a>Access

Você pode imprimir painéis, relatórios e visuais de relatórios em Power BI para produzir uma cópia física. Você não pode imprimir relatórios inteiros; você só pode imprimir uma página de cada vez. Para fazer isso, vá até um relatório, use o campo de pesquisa para encontrar dados específicos e imprima a página.  Confira [Imprimir do serviço do Power BI](https://docs.microsoft.com/power-bi/service-print).

#### <a name="delete"></a>Excluir

Para excluir painéis, relatórios e pastas de trabalho, confira [Excluir quase tudo no serviço do Power BI](https://docs.microsoft.com/power-bi/service-delete).

Excluir um painel, relatório ou pasta de trabalho não exclui o conjunto de dados subjacente. Como o Power BI depende de uma conexão dinâmica com os dados de origem subjacente para estar completo e ser preciso, a exclusão de dados pessoais deve ser feita nele. (Por exemplo, se você criou um relatório do Power BI que está conectado ao Dynamics 365 for Sales como a fonte de dados dinâmica, qualquer correção nos dados terá que ser feita no Dynamics 365 for Sales.)

Depois que os dados são excluídos, você pode usar os recursos de [atualização de dados agendada](https://docs.microsoft.com/power-bi/refresh-scheduled-refresh) no Power BI para atualizar o conjunto de dados que está armazenado no Power BI. Depois disso, os dados excluídos não serão mais refletidos em nenhum relatório ou painel do Power BI que aproveitou esses dados.  Para ajudar a cumprir esses requisitos do RGPD, é preciso ter políticas definidas a fim de garantir que você esteja atualizando os dados em uma cadência adequada.

#### <a name="export"></a>Exportar

Para facilitar uma solicitação de portabilidade de dados, é possível exportar painéis e relatórios no Power BI:

- Você pode exportar os dados subjacentes de relatórios e painéis para um arquivo estático do Excel. Veja o vídeo em [Imprimir do serviço do Power BI](https://docs.microsoft.com/power-bi/service-print). Usando o Excel, é possível editar os dados pessoais para serem incluídos na solicitação de portabilidade e salvá-los em um formato frequentemente usado que pode ser lido por máquina, como .csv ou .xml.
- É possível exportar (baixar) um relatório do serviço do Power BI no Office 365 para um arquivo .pbix se ele foi originalmente publicado usando o Power BI Desktop. É possível então importar esse arquivo para o Power BI Desktop e publicá-lo (exportar) no serviço do Power BI de outra organização. Confira [Exportar um relatório do serviço do Power BI para o Desktop](https://docs.microsoft.com/power-bi/service-export-to-pbix).

### <a name="powerapps"></a>PowerApps

As seções a seguir explicam como usar a funcionalidade no aplicativo do Microsoft Power Apps para localizar, acessar, exportar e excluir dados pessoais. Essas etapas descrevem como um administrador pode fazer a transição de aplicativos e seus recursos dependentes para novos proprietários a fim de limitar a interrupção nos negócios.

#### <a name="discover"></a>Descobrir

O PowerApps é um serviço para criar aplicativos que podem ser compartilhados e usados em sua organização. Como parte do processo de criação ou execução de um aplicativo, um usuário acabará armazenando vários tipos de recurso e dados no serviço do PowerApps, incluindo aplicativos, ambientes, conexões, conectores personalizados e permissões.

Para ajudar a facilitar uma solicitação DSR relacionada ao PowerApps, você pode usar as operações de administração expostas no [Centro de Administração do PowerApps](https://admin.powerapps.com/) e [cmdlets do PowerShell de Administração do PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).  Acessar estas ferramentas exigirá uma conta com as seguintes permissões:

- Uma licença paga de Plano 2 do PowerApps ou uma licença de avaliação de Plano 2 do PowerApps. Você pode assinar uma licença de avaliação de avaliação de 30 dias [aqui](https://web.powerapps.com/trial). 
- [Administrador global](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) ou
- [Administrador global do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)

Para obter mais informações sobre como encontrar dados pessoais, confira [Descobrir dados pessoais do PowerApps](https://go.microsoft.com/fwlink/?linkid=871880).

O serviço do PowerApps também inclui o Common Data Service para Aplicativos, que permite aos usuários armazenar dados em entidades padrão e personalizadas em um banco de dados do Common Data Service. Você pode exibir os dados armazenados nessas entidades no [portal do PowerApps Maker](https://web.powerapps.com) e usar os recursos de pesquisa no produto e [Localização Avançada](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search) para pesquisar dados específicos na entidade. Para obter mais detalhes sobre a descoberta de dados pessoais no Common Data Service, confira [Descobrir dados pessoais do Common Data Service](https://go.microsoft.com/fwlink/?linkid=871881).

#### <a name="access"></a>Access

Os administradores têm a capacidade de atribuir a si mesmos privilégios para acessar e executar aplicativos e recursos associados (incluindo fluxos, conexões e conectores personalizados) usando o [Centro de Administração do PowerApps](https://admin.powerapps.com/) ou [cmdlets do PowerShell de Administrador do PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

Depois de ter acesso ao aplicativo do usuário, é possível usar um navegador da Web para abrir o aplicativo. Depois de abrir um aplicativo, você pode fazer uma captura de tela dos dados. Confira [Usar o PowerApps em um navegador da Web](https://docs.microsoft.com/powerapps/run-app-browser).

#### <a name="delete"></a>Excluir

Como o PowerApps permite aos usuários criar aplicativos de linha de negócios, que podem ser uma parte essencial das operações diárias da sua organização, quando um usuário sai da organização e sua conta do Office 365 é excluída, o administrador precisa determinar se exclui os aplicativos que pertenciam ao usuário ou simplesmente os reatribui a novos proprietários. Isso ajuda a organização a fazer a organização a fazer a transição de aplicativos para novos proprietários e evita interrupções nos negócios de aplicativos que podem ser usados em processos corporativos compartilhados.

Para dados compartilhados, como aplicativos, os administradores devem decidir se querem ou não excluir permanentemente os dados compartilhados desse usuário, ou se querem mantê-los reatribuindo os dados a si mesmos ou a alguém dentro da organização. Confira [Excluir dados pessoais do PowerApps](https://go.microsoft.com/fwlink/?linkid=871883).

Todos os dados que foram armazenados por um usuário em uma entidade em um banco de dados do Common Data Service para Aplicativos também precisarão ser revisados e (se desejado) excluídos por um administrador usando os recursos no produto. Confira [Excluir dados pessoais do usuário do Common Data Service](https://go.microsoft.com/fwlink/?linkid=871886).

#### <a name="export"></a>Exportar

Os administradores têm a capacidade de exportar dados pessoais de um usuário armazenados no serviço do PowerApps usando o [Centro de Administração do PowerApps](https://admin.powerapps.com/) e [cmdlets do PowerShell de Administrador do PowerApps](https://go.microsoft.com/fwlink/?linkid=871804). Confira [Exportar dados pessoais do PowerApps](https://go.microsoft.com/fwlink/?linkid=871883).

Também é possível usar os recursos de pesquisa no produto de [Localização Avançada](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search) para pesquisar dados pessoais de um usuário em qualquer entidade. Para obter detalhes sobre como exportar dados pessoais no Common Data Service, confira [Exportar dados pessoais do Common Data Service](https://go.microsoft.com/fwlink/?linkid=871889).

#### <a name="connections-and-custom-connectors-in-powerapps"></a>Conexões e conectores personalizados no PowerApps

As conexões exigem que os usuários forneçam credenciais para se conectarem a APIs, aplicativos SaaS e sistemas desenvolvidos personalizados. Essas conexões são de propriedade do usuário que estabeleceu a conexão e podem ser [gerenciadas](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection) no produto.  Depois que o PowerApps tiver sido reatribuído, um administrador poderá usar os cmdlets do PowerShell para listar e excluir essas conexões como parte da exclusão de dados do usuário.

Os conectores personalizados permite que as organizações estendam os recursos do PowerApps conectando-se a sistemas em que um conector pronto para uso não está disponível. O autor de um conector personalizado pode [compartilhar](https://docs.microsoft.com/connectors/custom-connectors/use-custom-connector-powerapps) seu conector com outras pessoas em uma organização.  Depois de receber uma solicitação de exclusão de DSR, um administrador deve considerar a reatribuição da propriedade desses conectores a fim de evitar interrupção nos negócios. Para agilizar esse processo, um administrador pode usar cmdlets do PowerShell para listar, reatribuir ou excluir conectores personalizados.

### <a name="project-online"></a>Project Online

As seções a seguir explicam como usar a funcionalidade no aplicativo do Microsoft Project Online para localizar, acessar, exportar e excluir dados pessoais.

#### <a name="discover-and-access"></a>Descobrir e acessar

Você pode usar a Pesquisa de Conteúdo para pesquisar o site do SharePoint Online que está associado a um projeto (quando um projeto é criado pela primeira vez, há uma opção para criar um site do SharePoint Online associado); a Pesquisa de Conteúdo não pesquisa os dados em um projeto real no Project Online, somente o site associado. De qualquer forma, a Pesquisa de Conteúdo pesquisa metadados sobre projetos (como pessoas mencionadas no assunto). No entanto, isso pode ajudá-lo a encontrar (e acessar) o projeto que contém os dados relacionados à DSR.

>[!TIP]
>A URL do conjunto de sites na organização onde os sites associados aos projetos estão é **https://\<your org\>.sharepoint.com/sites/pwa**; por exemplo, **https://contoso.sharepoint.com/pwa**. Você pode usar esse conjunto de sites específico como o local da sua pesquisa de conteúdo e, em seguida, o nome do projeto na consulta de pesquisa. Além disso, um administrador de TI pode usar a página Conjuntos de Sites no Centro de Administração do SharePoint Online para obter uma lista de conjuntos de sites PWA na organização.

#### <a name="delete"></a>Excluir

Você pode excluir informações sobre um usuário do ambiente do Project Online. Confira [Excluir dados do usuário do Project Online](https://support.office.com/article/delete-user-data-from-project-online-252fa593-9c25-47ed-b861-643fe8bf1cb7).

#### <a name="export"></a>Exportar

É possível exportar conteúdo específico de um usuário do ambiente do Project Online. Esses dados são exportados para vários arquivos no formato JSON. Para obter instruções passo a passo, confira [Exportar dados do usuário do Project Online](https://support.office.com/article/export-user-data-from-project-online-27f3838d-3dbe-4b98-80dc-df55f851154d). Para obter informações detalhadas sobre os arquivos que são exportados, confira [Definições de objeto json para exportação do Project Online](https://support.office.com/article/project-online-export-json-object-definitions-ce5faeae-9af4-4696-b847-a1f4f20327c7).

### <a name="publisher"></a>Publisher

As seções a seguir explicam como usar a funcionalidade no aplicativo do Microsoft Publisher para encontrar, acessar, exportar e excluir dados pessoais.

#### <a name="discover"></a>Descobrir

Você pode usar o recurso de pesquisa no aplicativo para localizar um texto em um arquivo do Publisher, da mesma forma que é possível na maioria dos aplicativos do Office. Confira [Localizar e substituir um texto](https://support.office.com/article/find-and-replace-text-bfe54275-b7c7-4d0f-904d-a2f38d322268).

#### <a name="access"></a>Acessar

Depois de encontrar os dados, você pode fazer uma captura de tela ou copiar e colar em um arquivo de Word ou de texto e fornecer isso à entidade de dados. Você também pode salvar uma publicação como um arquivo PDF, XPS ou Word. Confira:

  - [Salvar uma publicação como um documento do Word](https://support.microsoft.com/pt-BR/office/save-a-publication-as-a-word-document-b5eaaae5-6f1b-48c1-bebc-44460376b693)
  - [Salvar Como ou converter uma publicação para .pdf ou .xps usando o Publisher](https://support.microsoft.com/pt-BR/office/save-as-or-convert-a-publication-to-pdf-or-xps-using-publisher-657332d0-d2c2-464a-9870-e9b3d22e6469)

#### <a name="export"></a>Exportar

Você pode fornecer uma entidade de dados com o arquivo do Publisher real ou como já explicado, você pode salvar uma publicação como um arquivo PDF, XPS ou Word. Confira:

  - [Salvar uma publicação como um documento do Word](https://support.microsoft.com/pt-BR/office/save-a-publication-as-a-word-document-b5eaaae5-6f1b-48c1-bebc-44460376b693)
  - [Salvar Como ou converter uma publicação para .pdf ou .xps usando o Publisher](https://support.microsoft.com/pt-BR/office/save-as-or-convert-a-publication-to-pdf-or-xps-using-publisher-657332d0-d2c2-464a-9870-e9b3d22e6469)

#### <a name="delete"></a>Excluir

Você pode excluir o conteúdo de uma publicação, excluir páginas inteiras ou excluir um arquivo inteiro do Publisher. Confira [Adicionar ou excluir páginas](https://support.office.com/article/add-or-delete-pages-daf71e39-86e0-4bbc-a186-d5ec70450b08).

### <a name="stream"></a>Stream

As seções a seguir explicam como usar a funcionalidade no aplicativo do Microsoft Stream para localizar, acessar, exportar e excluir dados pessoais.

#### <a name="discover"></a>Descobrir

Para descobrir conteúdo gerado ou carregado para o Stream que pode ser relevante para uma solicitação do titular de dados, um administrador do Stream pode executar um relatório de usuário para determinar quais vídeos, descrições de vídeo, grupos, canais ou comentários, um usuário do Stream pode ter carregado, criado ou postado.  Para obter instruções sobre como gerar um relatório, confira [Gerenciamento de dados do usuário Microsoft Stream](https://docs.microsoft.com/stream/managing-user-data). A saída do relatório está no formato HTML e contém hiperlinks que podem ser usados para navegar até os vídeos de interesse potencial. Se quiser exibir um vídeo que tem permissão personalizada definida e não fizer parte dos usuários originais para os quais o vídeo foi destinado, você poderá exibir no modo de administrador. Confira [Recursos de administração no Microsoft Stream](https://docs.microsoft.com/stream/manage-content-permissions).  

#### <a name="access"></a>Acessar

Dependendo da natureza da solicitação do titular de dados, uma cópia do relatório descrito acima pode ser usada para ajudar a atender a uma solicitação do titular de dados. O relatório de usuário inclui o nome e ID exclusiva do usuário do Stream, uma lista de vídeos que o usuário carregou, uma lista de vídeos aos quais o usuário tem acesso, uma lista dos canais que o usuário criou, uma lista de todos os grupos dos quais o usuário é membro e uma lista de todos os comentários que o usuário deixou em vídeos. O relatório também mostra se o usuário exibiu cada vídeo listado no relatório do usuário. Se você quiser conceder ao titular de dados acesso a um vídeo para atender a uma solicitação de DSR, poderá compartilhar o vídeo.

#### <a name="export"></a>Exportar

Confira a seção Acessar do Stream. 

#### <a name="delete"></a>Excluir

Para excluir ou editar vídeos ou outro conteúdo do Stream, um administrador do Stream pode selecionar o modo de exibição no modo de administrador para realizar a função necessária. Veja [Recursos de administração do Microsoft Stream](https://docs.microsoft.com/stream/manage-content-permissions). Se um usuário sair da organização e desejar que seu nome seja removido para não ser exibido ao lado de vídeos que ele carregou, você poderá remover o nome ou substituí-lo por outro. Veja [Como gerenciar usuários excluídos do Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users).

### <a name="sway"></a>Sway

As seções a seguir explicam como usar a funcionalidade no aplicativo do Microsoft Sway para localizar, acessar, exportar e excluir dados pessoais.

#### <a name="discover"></a>Descobrir

O conteúdo criado usando o Sway (encontrado em [www.sway.com](https://sway.office.com/)) pode ser visto apenas pelo proprietário e por aqueles que o autor deu permissão para exibir o Sway.  Confira [Configurações de privacidade no Sway](https://support.microsoft.com/pt-BR/office/privacy-settings-in-sway-394b551c-be6f-4bd7-a70a-f318d72bf217).  Para determinar se o Sway é um local onde provavelmente dados pessoais responsivos à sua DSR residem, você pode pedir ao Titular dos Dados e aos usuários organizacionais que provavelmente têm conteúdo gerado sobre o Titular dos Dados para pesquisar seus Sways e compartilhar com você rodos os Sways que provavelmente contêm dados pessoais responsivos à solicitação do Titular dos Dados. Para obter informações sobre como compartilhar um Sway, confira "Compartilhar um Sway da sua Conta Organizacional" no artigo [Compartilhar o Sway](https://support.microsoft.com/pt-BR/office/share-your-sway-1cf853b8-ef7e-46b0-b704-003e58d28998).

#### <a name="access"></a>Acessar

Se você encontrou dados pessoais em um Sway que deseja compartilhar com o Titular do Dados, forneça a ele acesso aos dados por meio de um dos vários meios.  É possível fornecer ao Titular dos Dados uma cópia da versão online do Sway (conforme descrito acima); tirar capturas de tela da parte relevante do Sway que deseja compartilhar; ou imprimir ou baixar o Sway para o Word ou convertê-lo em um PDF.  Como baixar um Sway é descrito mais adiante na seção "exportar" abaixo.

#### <a name="delete"></a>Excluir

Para aprender como excluir um Sway, vá para a seção "Como excluo o meu Sway?", em [Configurações de privacidade do Sway](https://support.microsoft.com/pt-BR/office/privacy-settings-in-sway-394b551c-be6f-4bd7-a70a-f318d72bf217).

#### <a name="export"></a>Exportar

Para exportar um Sway, abra o Sway que deseja baixar, selecione a série de pontos (reticências) no canto superior direito, selecione **Exportar,** e escolha **Word** ou **PDF**.

### <a name="whiteboard"></a>Whiteboard

As seções a seguir explicam como usar a funcionalidade no aplicativo do Microsoft Whiteboard para localizar, acessar, exportar e excluir dados pessoais.

- [Whiteboard 2016 no Surface Hub](#whiteboard-2016-on-surface-hub)
- [Whiteboard em outras plataformas](#whiteboard-for-pc-surface-hub-and-other-platforms)

#### <a name="whiteboard-2016-on-surface-hub"></a>Whiteboard 2016 no Surface Hub

Esta seção descreve como responder a solicitações de DSR para dados criados usando o aplicativo interno Whiteboard 2016 no Surface Hub.

##### <a name="discover"></a>Descobrir

Os arquivos de quadro de comunicações (.wbx) são armazenados na conta do OneDrive for Business dos usuários. Você pode perguntar ao titular dos dados ou a outros usuários se os quadros de comunicações que eles criaram podem conter dados pessoais responsivos a uma solicitação de DSR. Eles podem compartilhar um quadro de comunicações com você, ou você pode obter uma cópia dele para dar ao titular dos dados.

Para acessar e transferir quadros de comunicações: 

1. Dê a si mesmo acesso à conta do OneDrive for Business do usuário. Veja a seção "Obter acesso aos documentos do OneDrive for Business do ex-funcionário" em [Obter acesso e fazer backup dos dados de um ex-usuário](https://docs.microsoft.com/microsoft-365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data).
2. Vá para a pasta Dados do Aplicativo do quadro de comunicações na conta do OneDrive for Business do usuário e copie os arquivos .wbx dos quadros de comunicações que você deseja transferir.
3. Dê a si mesmo acesso à conta do OneDrive for Business do titular de dados e acesse a pasta Dados de Aplicativos do Quadro de Comunicações.
4. Cole os arquivos .wbx que você copiou na etapa anterior.

##### <a name="access"></a>Acessar

Se encontrar dados pessoais em um quadro de comunicações responsivo a uma solicitação de acesso de DSR, você poderá fornecer ao titular dos dados o acesso a um quadro de comunicações de várias maneiras:

- Crie capturas de tela das partes relevantes de um quadro de comunicações.
- Carregue uma cópia do arquivo .wbx para a conta do OneDrive for Business do titular de dados. Confira a seção anterior para obter as etapas sobre como acessar e transferir arquivos .wbx.
- Exporte uma cópia de quadros de comunicações como um arquivo .png.

##### <a name="export"></a>Exportar

Se você tiver obtido uma cópia de um quadro de comunicações, poderá exportá-lo. 

1. Inicie o Whiteboard no Surface Hub.
2. Toque no botão Compartilhar e selecione Exportar uma cópia. Você pode exportar um quadro de comunicações para um arquivo do OneNote (.one) ou um arquivo de imagem (.png).

##### <a name="delete"></a>Excluir

Você pode dar a si mesmo acesso à conta do OneDrive for Business do usuário e excluir os quadros de comunicações.

1. Dê a si mesmo acesso à conta do OneDrive for Business do titular de dados. Veja a seção "Obter acesso aos documentos de OneDrive for Business do ex-funcionário" em [Obter acesso e fazer backup dos dados de um ex-usuário](https://docs.microsoft.com/microsoft-365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data)
2. Vá para a pasta Dados de Aplicativos do Whiteboard e exclua o conteúdo dessa pasta.

#### <a name="whiteboard-for-pc-surface-hub-and-other-platforms"></a>Whiteboard para PC, Surface Hub e outras plataformas

Se um administrador recebe uma solicitação de DSR para dados no novo aplicativo do Quadro de Comunicações, ele pode usar o PowerShell do Quadro de Comunicações para se adicionar (ou adicionar outros usuários) como um proprietário de quadros de comunicações de um usuário. Isso permite que um administrador realize ações como acessar, exportar e excluir quadros de comunicações. Use o cmdlet **Set-WhiteboardOwner** para adicionar outro usuário como o proprietário de um quadro de comunicações ou use o cmdlet **Invoke-TransferAllWhiteboards** para transferir a propriedade de todos os quadros de comunicações de um usuário específico para um novo proprietário. Para saber mais sobre como usar esses cmdlets e instalar o módulo do PowerShell do Quadro de Comunicações, confira a Referência de cmdlets do Quadro de Comunicações da Microsoft. Depois que você ou outra pessoa detiver a propriedade de um quadro de comunicações, confira a [Referência de cmdlets do Quadro de Comunicações da Microsoft](https://docs.microsoft.com/powershell/module/whiteboard/?view=whiteboard-ps).

Depois que você ou outra pessoa tiver a propriedade de um quadro de comunicações, confira o [Artigo de suporte do quadro de comunicações](https://go.microsoft.com/fwlink/?linkid=872780) para obter instruções detalhadas sobre como acessar, exportar e excluir quadros de comunicações.

### <a name="yammer"></a>Yammer

As seções a seguir explicam como usar a funcionalidade no aplicativo do Microsoft Yammer para localizar, acessar, exportar e excluir dados pessoais.

#### <a name="discover"></a>Descobrir

No centro de administração do Yammer, um administrador verificado pelo Yammer (administrador global ou administrador verificado configurado no Yammer) pode exportar dados pertencentes a um determinado usuário. A exportação inclui as mensagens e os arquivos postados e modificados pelo usuário e as informações sobre tópicos e grupos criados pelo usuário. Quando uma exportação de dados específica de usuário é executada, o administrador também recebe uma mensagem na caixa de entrada com os dados de atividade da conta do usuário se for de sua escolha. Para obter instruções detalhadas, confira [Yammer Enterprise: privacidade](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise).

As exportações específicas de usuário são para uma única rede, de modo que se o usuário estiver em uma rede externa do Yammer, o administrador deverá exportar dados para essa rede externa e para a rede doméstica.

Para acessar dados não incluídos na exportação de dados, capturas de tela podem ser feitas para o perfil do usuário, configurações, associações de grupos, mensagens marcadas com indicador, usuários seguidos e tópicos seguidos. Os usuários ou administradores podem coletar essas informações. Para saber mais, confira [Yammer Enterprise: privacidade](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise). 

#### <a name="access"></a>Access

Você pode exibir dados nos arquivos exportados, incluindo o texto completo de mensagens e do conteúdo dos arquivos. Também é possível clicar nos links dos arquivos exportados para ir diretamente para as mensagens e os arquivos postados no Yammer, grupos, tópicos criados pelos usuários, mensagens que os usuários curtiram, mensagens em que os usuários foram @mencionados, votações das quais os usuários participaram e links que os usuários adicionaram.

A exportação de dados por usuário não inclui:

- O perfil do usuário:
    - Se o usuário tiver uma identidade no Yammer, ele tem controle total de seu perfil. Para obter informações sobre como exibir e modificar o perfil, confira [Alterar meu perfil e configurações do Yammer](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851).
    
    - Se o usuário tiver uma identidade no Office 365, o perfil de usuário no Yammer será extraído automaticamente do Office 365, que obtém as informações de perfil do AAD (Azure Active Directory). Os usuários do Yammer podem alterar temporariamente os respectivos perfis no Yammer, mas essas alterações são substituídas quando há uma alteração no AAD, de modo que você deve exibir e alterar dados de diretório no AAD. Confira [Gerenciar usuários do Yammer em seu ciclo de vida do Office 365](https://docs.microsoft.com/yammer/manage-yammer-users/manage-users-across-their-lifecycle) e [Adicionar ou alterar informações de perfil de um usuário no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-users-profile-azure-portal).

-   As configurações do usuário:

- O usuário pode exibir e alterar suas próprias configurações. Para obter informações sobre como exibir e modificar configurações do usuário, confira [Alterar meu perfil e configurações do Yammer](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851). Um administrador pode exibir essas informações e fazer capturas de tela, mas não pode alterá-las. Vá para as configurações do Yammer de \>**Pessoas** e clique no nome do usuário.<br/>
    - Associação de grupo, mensagens marcadas com indicadores, usuários seguidos e tópicos seguidos do usuário.
    
    - O usuário pode exibir essas informações. Para obter informações sobre como fazer isso, confira [Dicas para manter-se organizado no Yammer](https://support.office.com/article/tips-for-staying-organized-in-yammer-40ae9666-75c0-4254-a84c-d87a9542f380). Um administrador pode exibir essas informações e fazer capturas de tela, mas não pode alterá-las. Vá para as configurações do Yammer de \>**Pessoas** e clique no nome do usuário.

#### <a name="export"></a>Exportar

Para obter instruções de como exportar dados, confira [Gerenciar solicitações de assuntos dados GDPR no Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise). Você deve executar uma exportação por usuário para cada rede do Yammer da qual o usuário é um membro.

O Yammer tem configurações de retenção de dados que exclui os dados de modo temporário e irreversível quando um usuário exclui uma mensagem ou um arquivo. Se essa opção for definida como exclusão temporária, os dados que um usuário excluiu estarão incluídos na exportação. Se a configuração de retenção de dados do Yammer for definida como Exclusão Irreversível, as informações excluídas já não serão armazenadas no Yammer, então não estarão incluídas na exportação.

#### <a name="delete"></a>Excluir

O Yammer permite que administradores verificados executem uma exclusão em conformidade com o RGPD usando o centro de administração do Yammer caso recebam uma DSR. Essa opção é chamada de Apagar Usuário e suspende o usuário por 14 dias e depois remove todos os seus dados pessoais, com exceção de arquivos e mensagens. Se o usuário for um usuário convidado, isso deve ser feito para cada rede externa da qual o usuário convidado é membro.

>[!NOTE]
>Se um administrador desejar remover os arquivos e mensagens de um usuário durante essa janela de 14 dias, ele terá que executar uma exportação no nível de usuário para identificar os arquivos e mensagens e, em seguida, decidir quais serão excluídos, ou por exclusão no produto, ou usando um script do PowerShell. Após a janela de 14 dias, o administrador não poderá mais associar o usuário aos respectivos arquivos ou mensagens.

Quando um usuário é excluído com a opção Apagar Usuário, a notificação é enviada para a caixa de entrada do Yammer de todos os administradores de rede e administradores verificados. A opção Apagar Usuário exclui um perfil do Yammer do usuário, mas não exclui seu perfil do Office 365 ou do Azure Active Directory.

Para obter etapas detalhadas para remover um usuário, confira [Gerenciar solicitações de assunto de dados GDPR no Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise).

## <a name="responding-to-dsr-rectification-requests"></a>Responder às solicitações de retificação de DSR

Se um titular dos dados pediu para corrigir os dados pessoais que residem nos dados da sua organização, armazenados no Office 365, você e sua organização precisam determinar se é apropriado aceitar a solicitação.  A correção dos dados pode incluir a execução de ações como editar, redigir ou remover dados pessoais de um documento ou de um outro tipo de item. A maneira mais conveniente de fazer isso é solicitar que o proprietário dos dados/documento use o aplicativo apropriado do Office 365 para fazer a alteração solicitada. Uma alternativa é pedir a um administrador de TI da organização que faça a alteração. Isso provavelmente exigirá que o administrador de TI (ou outras pessoas em sua organização com os privilégios adequados, como o administrador do conjunto de sites do SharePoint Online) atribua a si mesmo ou a alguém que esteja na DSR, as permissões necessárias para obter acesso ao local do conteúdo em que o documento está localizado para fazer a alteração diretamente no documento.

### <a name="requesting-that-the-data-owner-to-make-the-approved-change"></a>Solicitar que o proprietário dos dados faça a alteração aprovada

A maneira mais direta de retificar dados pessoais é solicitar ao proprietário dos dados que faça as alterações. Depois de localizar os dados que são o objeto da DSR, você poderá fornecer as informações a seguir para que ele possa fazer a alteração.

- O local e o nome do arquivo (para documentos e outros arquivos) do item que precisa ser alterado. Localizar os dados em questão faz parte do [processo de descoberta](#using-content-search-to-find-personal-data), que foi explicado anteriormente.
- A alteração aprovada que o proprietário dos dados deve fazer

Talvez você queira considerar a implementação de um processo de confirmação, onde você ou outra pessoa envolvida na investigação de DSR confirma que a alteração solicitada foi feita.

### <a name="gaining-access-to-a-sharepoint-online-site-or-onedrive-for-business-account-to-make-changes"></a>Obter acesso a um site do SharePoint Online ou a uma conta do OneDrive for Business para fazer alterações

Se não for viável para o proprietário dos dados implementar a solicitação de retificação do titular dos dados, um administrador de TI ou do SharePoint na organização pode obter acesso ao local do conteúdo e fazer as alterações necessárias. Ou, um administrador pode atribuir a você ou outro responsável pela privacidade de dados as permissões necessárias.

#### <a name="sharepoint-online"></a>SharePoint Online

Para atribuir as permissões de administrador ou proprietário para um site do SharePoint Online de modo que você ou outra pessoa possa acessar e editar o documento, confira:

- [Gerenciar administradores para um conjunto de sites](https://docs.microsoft.com/sharepoint/manage-site-collection-administrators)

- [Editar e gerenciar permissões para uma biblioteca ou lista do SharePoint](https://support.office.com/article/Edit-and-manage-permissions-for-a-SharePoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782)

#### <a name="onedrive-for-business"></a>OneDrive for Business

Um administrador global pode acessar a conta do OneDrive for Business de um usuário usando o .

1. Entre no Office 365 com suas credenciais de administrador global.
2. Acesse o Centro de Administração.
3. Vá para **Usuários ativos** e selecione o usuário.
4. Expanda **Configurações do OneDrive for Business** no painel de detalhes e clique em **Acessar arquivos**.
5. Clique na URL para acessar a conta do OneDrive for Business do usuário.

### <a name="gaining-access-to-an-exchange-online-mailbox-to-make-changes-to-data"></a>Obter acesso a uma caixa de correio do Exchange Online para fazer alterações nos dados

Um administrador global pode atribuir a si mesmo as permissões necessárias para abrir e editar (ou excluir) itens na caixa de correio de outro usuário, como se fosse o proprietário dela. Um administrador global também pode atribuir essas permissões a outro usuário. Especificamente, o administrador global precisa adicionar a permissão **Ler e gerenciar**, que é a permissão de Acesso Completo no Exchange Online. Para obter detalhes, confira:

- [Conceder permissões de caixa de correio para outros usuários no Office 365](https://docs.microsoft.com/microsoft-365/admin/add-users/give-mailbox-permissions-to-another-user)
- [Acessar a caixa de correio de terceiros](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081)

Se a caixa de correio do usuário foi colocada em retenção legal ou foi atribuída a uma política de retenção, todas as versões de uma caixa de correio serão retidas até que o período de retenção expire ou a retenção seja removida da caixa de correio. Isso significa que se um item de caixa de correio for alterado em resposta à solicitação de retificação de DSR, uma cópia do item original (antes da alteração ser feita) será retida e armazenada em uma pasta oculta na pasta Itens Recuperáveis da caixa de correio do usuário.

### <a name="making-changes-to-content-in-onedrive-for-business-and-sharepoint-online"></a>Fazer alterações no conteúdo do OneDrive for Business e SharePoint Online

Os proprietários de dados ou administradores IT podem fazer alterações em documentos, listas e páginas do SharePoint Online. Lembre-se destes pontos ao fazer alterações no conteúdo do SharePoint:

- A atualização de um documento salvará uma nova versão do documento, que conterá a revisão. As versões anteriores do documento não serão atualizadas. Isso significa que é possível que os dados que são o objeto de uma solicitação de retificação de DSR persistam em versões antigas do tópico. As versões antigas de um tópico podem ser excluídas e depois permanentemente removidas do Office 365. Confira a seção [Excluir documentos no SharePoint Online e OneDrive for Business](#deleting-documents-in-sharepoint-online-and-onedrive-for-business) neste guia.
- Para terminar de redigir um arquivo do SharePoint de maneira que remova do arquivo todos os rastros de um titular dos dados, inclusive todas as versões do arquivo e todas as atividades registradas pelo titular dos dados, você precisa executar as seguintes etapas:

    1. Baixe uma cópia do arquivo no computador local.
    2. Exclua permanentemente o arquivo do SharePoint Online, excluindo o arquivo e, em seguida, excluindo-o da Lixeira de primeiro estágio e da Lixeira de segundo estágio. Confira a seção [Excluir documentos no SharePoint Online e OneDrive for Business](#deleting-documents-in-sharepoint-online-and-onedrive-for-business) neste guia.
    3. Faça as revisões na cópia do documento no seu computador local.
    4. Carregue o arquivo revisado no local original do SharePoint Online.

- Os dados nas listas do SharePoint podem ser editados. Confira [Adicionar, editar ou excluir itens de lista](https://support.microsoft.com/pt-BR/office/add-edit-or-delete-list-items-a4b31f53-f044-470e-9823-4526594bacde).

Os administradores de TI também podem corrigir certas propriedades pessoais associadas a um documento:

As informações de usuário do Perfil de Usuário do SharePoint ou Office 365 muitas vezes são associadas aos documentos do OneDrive for Business e SharePoint Online para representar a pessoa. Por exemplo, o nome de um usuário em uma coluna Criado por ou Modificado por de um documento ou item de lista. As informações desse usuário podem ser retificadas de várias maneiras, dependendo da fonte:

- Retifique as propriedades no próprios Active Directory local do usuário. Para clientes que estão sincronizando propriedades do usuário, como Nome de Exibição, Nome, etc., de um AD local, essas propriedades devem ser retificadas nele. De maneira adequada, as propriedades mapeadas fluirão para o Office 365, depois para o OneDrive for Business e SharePoint Online.
- Retifique as propriedades do usuário no centro de administração. As alterações feitas nos dados da conta serão refletidas automaticamente nas experiências do OneDrive for Business e SharePoint Online. Para obter informações, confira [Adicionar ou alterar informações do perfil de um usuário no Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=864809). Para propriedades originadas no Office 365, nenhuma alteração pode ser feita no SharePoint.
- Retifique as propriedades do usuário na experiência do perfil de usuário do SharePoint no Centro de Administração do SharePoint. Na guia Perfis do usuário do centro de administração do SharePoint, os administradores podem clicar em **Gerenciar perfis de usuário** e procurar as propriedades de qualquer usuário. Em seguida, eles podem optar por editá-las.
- Retifique as propriedades do usuário em uma fonte personalizada. As propriedades de perfil personalizadas do SharePoint podem ser sincronizadas de uma fonte personalizada por meio do MIM (Microsoft Identity Manager) ou outro método.

Isso não afetará todas as experiências, o que pode reter as informações antigas. Por exemplo, o nome do usuário como texto no documento.

### <a name="making-changes-to-content-in-power-bi"></a>Fazer alterações no conteúdo no Power BI

O Power BI depende dos dados de origem subjacentes usados em seus painéis e relatórios para ser completo e preciso, de modo que a correção dos dados de origem imprecisos ou incompletos deve ser feita nele. Por exemplo, se você criou um relatório do Power BI que está conectado ao Dynamics 365 for Sales como a fonte de dados dinâmica, será preciso fazer as correções dos dados no Dynamics 365 for Sales.

Depois que essas alterações são feitas, você poderá aproveitar os recursos da [atualização de dados agendada](https://docs.microsoft.com/power-bi/refresh-scheduled-refresh) para atualizar o conjunto de dados que está armazenado no Power BI, de modo que os dados revisados sejam refletidos nos ativos do Power BI dependentes. Para ajudar a atender aos requisitos do RGPD, é preciso ter políticas definidas, a fim de garantir que você esteja atualizando os dados em uma cadência adequada.

### <a name="making-changes-to-content-in-yammer"></a>Fazer alterações no conteúdo no Yammer

Para mensagens, um usuário pode editar uma determinada mensagem de modo a retificar qualquer imprecisão. Ele pode solicitar uma lista de todas as respectivas mensagens a um administrador verificado do Yammer e clicar em um link do arquivo para revisar cada mensagem.

Para arquivos, um usuário pode editar um determinado arquivo de modo a retificar imprecisões. Eles podem solicitar uma lista de todos os arquivos publicados por um administrador verificado do Yammer e acessar os arquivos no mesmo. Os arquivos exportados para a pasta Arquivos podem ser visualizados ao pesquisá-los pelo número. Por exemplo, para um arquivo chamado 12345678.ppx na exportação, use a caixa Pesquisar no Yammer para buscar 1235678.ppx. Ou vá para <strong>https://www.yammer.com/\<network\_name\>/\#/files/\<file\_number\></strong>; por exemplo, <strong>https://www.yammer.com/contosomkt.onmicrosoft.com/\#/files/12345678</strong>.

Em dados que o usuário pode acessar por meio de seu perfil e pelas configurações, ele pode fazer todas as alterações necessárias.

- O perfil do usuário:

    - Se o usuário tiver uma identidade no Yammer, ele tem controle total de seu perfil. Para obter informações sobre como exibir e modificar o perfil, confira [Alterar meu perfil e configurações do Yammer](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851).
    - Se o usuário tiver uma identidade no Office 365, o perfil de usuário no Yammer será extraído automaticamente do Office 365, que obtém as informações de perfil do ADD (Azure Active Directory). Os usuários do Yammer podem alterar temporariamente os respectivos perfis no Yammer, mas essas alterações são substituídas quando há uma alteração no ADD, de modo que você deve exibir e alterar dados de diretório no ADD. O usuário precisa solicitar a atualização do ADD. Confira [Gerenciar usuários do Yammer em seu ciclo de vida do Office 365](https://docs.microsoft.com/yammer/manage-yammer-users/manage-users-across-their-lifecycle) e [Adicionar ou alterar informações de perfil de um usuário no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-users-profile-azure-portal). 

- As configurações do usuário:

    - O usuário pode alterar suas próprias configurações. Para obter informações sobre como exibir e modificar configurações do usuário, confira [Alterar meu perfil e configurações do Yammer](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851).
    - Associação de grupo, mensagens marcadas com indicadores, usuários seguidos e tópicos seguidos do usuário. O usuário pode alterar essas informações; confira [Dicas para manter-se organizado no Yammer](https://support.office.com/article/tips-for-staying-organized-in-yammer-40ae9666-75c0-4254-a84c-d87a9542f380).

## <a name="responding-to-dsr-restriction-requests"></a>Responder às solicitações de restrição de DSR

Veja a seguir como restringir o processamento de dados no Office 365:

- Remover uma licença de aplicativo do Office 365 para impedir os usuários de acessar dados por meio de um aplicativo
- Impedir os usuários de acessar a respectiva conta do OneDrive for Business
- Desativar o serviço de processamento de dados do Office 365
- Remover temporariamente os dados do SharePoint Online e OneDrive for Business e retê-los no local
- Restringir temporariamente todo o acesso a um site do SharePoint Online
- Impedir um usuário de entrar no Office 365

Se, mais tarde, sua organização determinar que alguma restrição não se aplica mais, você poderá encerrar a restrição revertendo as etapas realizadas para restringi-la, por exemplo, reatribuindo licenças, reativando um serviço ou permitindo que um usuário entre no Office 365.

### <a name="removing-the-license-for-an-office-365-application"></a>Remover a licença de um aplicativo do Office 365

Conforme explicado anteriormente, as licenças para todos os aplicativos do Office 365 que estão incluídas na assinatura do Microsoft 365 para empresas da sua organização são atribuídas a todos os usuários por padrão. Se for necessário restringir o acesso a dados que estão sujeitos a uma DSR, um administrador de TI pode usar o portal de administração do Office 365 para desativar temporariamente a licença de um aplicativo do usuário. Se o usuário tentar usar esse aplicativo, ele receberá uma notificação de produto não licenciado ou uma mensagem informando que ele não tem mais acesso. Para obter detalhes, confira [Remover licenças de usuário no Office 365 para empresa](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).

**Observações:**

- Para restringir o acesso de um usuário ao Yammer, primeiramente, você deve [impor a identidade do Office 365 para um usuário do Yammer](https://docs.microsoft.com/yammer/configure-your-yammer-network/enforce-office-365-identity) e, em seguida, remover a licença do Yammer do usuário.

- Em cenários em que se aproveita o Power BI Embedded, é possível restringir o acesso ao aplicativo ISV (fornecedor independente de software) no qual o conteúdo está inserido.

### <a name="preventing-users-from-accessing-their-onedrive-for-business-account"></a>Impedir os usuários de acessar a respectiva conta do OneDrive for Business

A remoção da licença do SharePoint Online de um usuário não o impedirá de acessar a respectiva conta do OneDrive for Business se ela existir.  É preciso remover as permissões do usuário para a respectiva conta do OneDrive for Business.  Você pode fazer isso removendo o usuário como um proprietário do conjunto de sites de sua conta do OneDrive for Business. Especificamente, é preciso remover o usuário dos grupos Administradores de Conjunto de Sites em seu perfil de usuário. Confira a seção “Adicionar e remover administradores em uma conta do OneDrive for Business” em [Gerenciar perfis de usuário no Centro de Administração do SharePoint](https://docs.microsoft.com/sharepoint/manage-user-profiles). 

### <a name="turning-off-an-office-365-service"></a>Desativar um serviço do Office 365

Outra maneira de atender a solicitação DSR para restringir o processamento de dados é desativar um serviço do Office 365. Obviamente, isso afetará todos os usuários em toda a organização e os impedirá de usar o serviço ou acessar dados no serviço.

A maneira mais conveniente de desativar um serviço é usar o PowerShell do Office 365 e remover a licença de usuário correspondente de todos os usuários na organização. Isso, de fato, impedirá a todos de acessar dados no serviço em questão. Para obter instruções detalhadas, confira [Desativar o acesso aos serviços com o PowerShell do Office 365](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) e siga os procedimentos para desativar os serviços do Office 365 para usuários de um único plano de licenciamento.

>[!NOTE]
>Para o Yammer, além de remover a licença do Yammer das contas de usuário, você também deve desativar a capacidade dos usuários de entrar no Yammer com as credenciais do Yammer (impondo o uso de suas credenciais do Office 365 ao entrar). Para obter instruções detalhadas, confira [Desativar o acesso ao Yammer para usuários do Microsoft 365](https://support.office.com/article/Turn-off-Yammer-access-for-Office-365-users-1f79bfad-f713-4143-aa5d-5584985ce53a).

### <a name="temporarily-removing-data-from-sharepoint-online-or-onedrive-for-business-sites"></a>Remover os dados temporariamente dos sites do SharePoint Online ou OneDrive for Business

Outra maneira de restringir o processamento de dados pessoais é removê-los temporariamente do Office 365 em resposta a uma DSR. Quando a organização determinar que a restrição não se aplica mais, você poderá importar os dados de volta no Office 365.

Como a maioria dos documentos do Office está localizada em um site do SharePoint Online ou OneDrive for Business, há um processo detalhado para remover documentos de sites e depois reimportá-los.

1. Obtenha uma cópia do documento que é o objeto da solicitação de restrição. Talvez seja preciso solicitar acesso ao site, ou pedir que um administrador global ou um administrador de conjunto de sites forneça uma cópia do documento.
2. Armazene o documento no local (como um servidor de arquivos ou compartilhamento de arquivos) ou outro local que não seja o seu locatário do Office 365 na nuvem da Microsoft.
3. Exclua permanentemente (limpe) o documento original do Office 365. Esse é um processo de 3 etapas:

    a. Exclua a cópia original do documento. Quando você exclui um documento de um site, ele é enviado à Lixeira do site (também chamada de *Lixeira de primeiro estágio*).

    b. Vá para a Lixeira do site e exclua essa cópia do documento. Quando você exclui um documento da Lixeira do site, ele é enviado à Lixeira do conjunto de sites (também chamada de *Lixeira de segundo estágio*). Confira [Excluir um arquivo, uma pasta ou um link de uma biblioteca de documentos do SharePoint](https://support.microsoft.com/pt-BR/office/delete-a-file-folder-or-link-from-a-sharepoint-document-library-71f3c90a-0d24-4d80-8b66-f88234b79a52).

    c. Vá para a Lixeira do conjunto de sites e exclua essa cópia do documento, o que a remove permanentemente do Office 365. Confira [Excluir itens da lixeira do conjunto de sites](https://support.microsoft.com/pt-BR/office/delete-items-from-the-site-collection-recycle-bin-dd5c00c2-aef6-4458-9d04-80b185077653).

4. Quando a restrição não se aplicar mais, a cópia do documento que foi armazenada no local poderá ser recarregada no site do Office 365.

>[!IMPORTANT]
>O procedimento anterior não funcionará se o documento estiver localizado em um site que está em retenção (com um dos recursos de retenção ou retenção legal do Office 365). No caso em que uma solicitação de restrição para uma DSR tiver precedência sobre uma retenção legal, a retenção terá que ser removida do site para que um documento possa ser permanentemente excluído. Além disso, o histórico de documentos para documentos excluídos será permanentemente removido.

### <a name="temporarily-restricting-access-to-sharepoint-online-sites"></a>Restringir temporariamente o acesso aos sites do SharePoint Online

Um administrador do SharePoint pode impedir temporariamente todos os usuários de acessar um conjunto de sites do SharePoint Online bloqueando o conjunto de sites (usando o comando usando o comando **Set-SPOSite - LockState** no PowerShell do SharePoint Online). Isso impedirá os usuários de acessar o conjunto de sites e quaisquer conteúdos ou dados que estejam localizados no site. Se, posteriormente, você determinar que os usuários devem poder acessar o site, o administrador poderá desbloquear o site. Confira [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) para obter informações sobre como executar esse cmdlet do PowerShell.

### <a name="preventing-a-user-from-signing-in-to-office-365"></a>Impedir um usuário de entrar no Office 365

Um administrador de TI também pode impedir um usuário de entrar no Office 365, o que pode impedi-lo de acessar qualquer serviço online do Office 365 ou processar quaisquer dados armazenados no Office 365. Confira [Bloquear o acesso de um funcionário antigo aos dados do Office 365](https://docs.microsoft.com/microsoft-365/admin/add-users/remove-former-employee).

## <a name="part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365"></a>Parte 2: Responder às DSRs com relação aos insights gerados pelo Office 365

O pacote de serviços do Office 365 da Microsoft inclui serviços online que fornecem insights aos usuários e organizações que optaram por usá-los.

- O Delve e o MyAnalytics fornecem insights aos usuários individuais
- O Workplace Analytics fornece percepções às organizações.

Esses serviços são descritos nas seções a seguir:

### <a name="delve"></a>Delve

No Delve, os usuários podem gerenciar o respectivo perfil do Office 365 e descobrir pessoas e documentos que podem ser relevantes para eles. Os usuários podem ver apenas documentos aos quais têm acesso. Para obter uma série de artigos úteis sobre o Delve, confira [Office Delve](https://support.office.com/article/What-is-Office-Delve-1315665a-c6af-4409-a28d-49f8916878ca).

#### <a name="access-and-export"></a>Acessar e exportar

Os administradores não podem acessar nem exportar os dados do Delve de um usuário. Isso significa que os usuários precisam acessar e exportar dados do Delve por conta própria. A maioria dos tipos de dados pode ser acessada e exportada diretamente do Delve, mas alguns estão disponíveis somente por meio de outros serviços.

##### <a name="data-available-in-the-delve-user-interface"></a>Dados disponíveis na interface de usuário do Delve

- **Dados de perfil:** essas são as informações de perfil da Lista de Endereço Global da sua organização no Active Directory do Azure, além de informações opcionais que os usuários escolheram adicionar sobre eles próprios. Para acessar ou exportar dados de perfil no Delve, o usuário deve clicar em**Eu** \> **Atualizar perfil**. Ele pode copiar o conteúdo diretamente da página ou
- **Dados de blog:** são postagens publicadas por um usuário. Para acessar ou exportar dados do blog, o usuário deve clicar **Eu** \> **Todas as postagens**. Podendo ainda copiar o conteúdo diretamente da página ou fazer uma captura de tela.
- **Dados de pessoas recentes:** essas são as pessoas da organização que o Delve inferiu serem mais relevantes para o usuário em um determinado momento. Quando o usuário clica em **Eu** \> **Ver tudo** no painel "Clicar em uma pessoa para ver no que ela está trabalhando", o Delve mostra as pessoas mais relevantes para o usuário em um dado momento.

##### <a name="data-available-through-an-export-link-in-delve"></a>Dados disponíveis por meio de um link de exportação no Delve

- **Dados da lista de pessoas:** são as pessoas que o usuário visualizou no Delve. A lista de **Pessoas** é exibida no painel esquerdo na página inicial. Os usuários podem exportar a lista de pessoas que eles vizualizaram mais recentemente no Delve.
- **Dados de favoritos:** são quadros e documentos que o usuário marcou como favoritos. A página **Favoritos** Mostra os quadros e documentos que o usuário tenha marcado como favoritos. Os usuários podem exportar uma lista dos seus documentos e quadros favoritos atuais.
- **Dados de configurações de recursos:** são configurações ou ações resultantes do uso do Delve por um usuário. Os usuários podem exportar uma lista completa dessas configurações.

Para acessar ou exportar o dado acima, o usuário pode clique no ícone de engrenagem no canto superior direito no Delve e clicar em **Configurações de recurso** > **Exportar dados**. As informações são exportadas em formato JSON.

##### <a name="data-thats-available-through-other-services"></a>Dados que estão disponíveis por meio de outros serviços

- **Dados de documentos populares:** são documentos e anexos de email que podem ser relevantes para o usuário. O Delve dinamicamente organiza esses documentos e emails com base nas atividades do usuário e das pessoas que trabalham com o Office 365. Quando um usuário abre o Delve ou clica em **Início**, o Delve mostra os documentos ou anexos do usuário mais relevantes em um dado momento. Para acessar ou exportar os documentos e anexos reais, o usuário pode acessar o serviço do Office 365,através do qual o documento ou anexo foi disponibilizado (como o Office.com, o SharePoint Online, o OneDrive for Business ou o Exchange Online).
- **Dados de documentos recentes e anexos de email:** estes são os documentos e anexos de email mais recentes que o usuário modificou. Quando um usuário clica em **Eu** \> **Ver todos** no painel de "Voltar aos documentos recentes e anexos de email", o Delve mostra os documentos e os anexos de email mais recentes que o usuário tenha modificado em um dado momento. Para acessar ou exportar documentos e anexos reais, o usuário pode acessar o serviço do Office 365 através do qual o documento ou anexo foi disponibilizado; como por exemplo, o Office.com, o SharePoint Online, o OneDrive for Business ou o Exchange Online.
- **Documentos das pessoas ao seu redor:** trata-se das pessoas na organização que o Delve tenha deduzido como sendo as mais relevantes para o usuário em um dado. Quando o usuário clica em **Eu** \> **Ver tudo** no painel "Descobrir documentos das pessoas ao seu redor", o Delve mostra as pessoas mais relevantes para o usuário em um dado momento. Para acessar ou exportar os documentos reais, o usuário pode acessar o serviço do Office 365 pelo qual o documento ou anexo foi disponibilizado (por exemplo, Office.com, SharePoint Online, OneDrive for Business ou Exchange Online).

#### <a name="rectify"></a>Retificar

Os usuários podem modificar as seguintes informações no Delve:

- **Informações de perfil:** o usuário pode clicar em **Eu** \> **Atualizar perfil** para atualizar suas informações. Dependendo das configurações da organização na Lista de Endereços Global, os usuários talvez não possam modificar todas as informações do perfil, como nome ou cargo.
- **Configurações de recurso:** o usuário pode clicar no ícone de engrenagem no canto superior direito no Delve e, em seguida, clicar em **Configurações de Recurso** \> para alterar as configurações desejadas.

#### <a name="restrict"></a>Restringir

Para restringir o processamento no Delve em sua organização, você pode desativar o Office Graph. Saiba mais [aqui](https://docs.microsoft.com/sharepoint/delve-for-office-365-admins).

#### <a name="delete"></a>Excluir

Os usuários podem excluir as seguintes informações no Delve:

- **Informações de perfil:** para excluir informações de perfil, o usuário pode clicar em **Eu** \> **Atualizar perfil** e excluir um texto de formato livre. Dependendo das configurações da organização na Lista de Endereços Global, os usuários talvez não possam excluir todas as informações do perfil, como nome ou cargo.
- **Documentos e anexos de email:** para excluir um documento ou anexo, os usuários devem ir para o serviço em que o documento ou anexo está armazenado (como o SharePoint Online, o OneDrive for Business ou o Exchange Online) e excluir o documento lá.

### <a name="myanalytics"></a>MyAnalytics

O MyAnalytics fornece estatísticas aos usuários para ajudar na compreensão de como eles usam o tempo no trabalho. Para ajudar os usuários a entenderem melhor os dados que são apresentados a eles no painel pessoal e como esses dados são calculados, direcione os usuários para o tópico da Ajuda [Painel pessoal do MyAnalytics](https://docs.microsoft.com/workplace-analytics/myanalytics/use/dashboard-2).

#### <a name="access-and-export"></a>Acessar e exportar

Se sua organização usa o MyAnalytics, a Microsoft gera insights para todos os usuários. Todas as informações do MyAnalytics são derivadas de cabeçalhos de email e reuniões na caixa de correio do usuário. Os usuários podem acessar o [painel MyAnalytics](https://delve.office.com) enquanto estiver conectado à sua conta do Office 365 para exibir as ideias geradas sobre como eles gastam o tempo no trabalho. Eles poderão criar capturas de tela de insights do MyAnalytics se quiserem ter cópias permanentes das informações.

#### <a name="rectify"></a>Retificar

Todos os insights gerados pelo MyAnalytics são derivados dos itens de calendário e email do usuário. Portanto, não há nada a ser retificado que não sejam os itens de calendário ou email da fonte.

#### <a name="restrict"></a>Restringir

Para restringir o processamento para um usuário específico, você pode optar por retirá-lo do MyAnalytics. Para saber como, confira o artigo sobre [definição das configurações de usuário do MyAnalytics](https://docs.microsoft.com/workplace-analytics/myanalytics/setup/configure-myanalytics).

#### <a name="delete"></a>Excluir

Todo o conteúdo da caixa de correio, incluindo dados de MyAnalytics, é descartado quando uma conta de usuário é "excluída permanentemente" do Active Directory. Para saber mais, confira a seção [Excluir um usuário](#deleting-a-user) deste guia.

### <a name="workplace-analytics"></a>Workplace Analytics

O Workplace Analytics permite que as organizações aumentem os dados do Office 365 com seus próprios dados corporativos para obter insights sobre a produtividade organizacional, os padrões de colaboração e o engajamento do funcionário. [Este artigo](https://docs.microsoft.com/workplace-analytics/index-orig) explica o controle que a sua organização tem sobre os dados que o Workplace Analytics processa e quem tem acesso a esses dados.

Para ajudar com as DSRs no Workplace Analytics: 

1. Determine se sua organização está usando o Workplace Analytics. Para saber mais, confira [Atribuir licenças a usuários](../admin/manage/assign-licenses-to-users.md). Se sua organização não estiver usando o Workplace Analytics, não haverá ação adicional.

2. Se a organização estiver usando Workplace Analytics, veja quem em sua organização foi atribuído à função de administrador do Workplace Analytics.  Você também deve determinar se a caixa de correio do titular dos dados está licenciada para o Workplace Analytics. Se necessário, peça ao administrador do Workplace Analytics que contate o Suporte da Microsoft para lidar com as DSRs a seguir: 

#### <a name="access-and-export"></a>Acessar e exportar

Os insights nos relatórios do Workplace Analytics podem ou não conter dados pessoais dos usuários que a sua organização licenciou para o Workplace Analytics, dependendo das informações que a organização usou para suplementar os dados do Office 365. O administrador do Workplace Analytics precisará revisar esses relatórios a fim de determinar se eles contêm dados pessoais de um usuário. Se um relatório não contiver dados pessoais de um usuário, você precisará decidir se deseja fornecer uma cópia desse relatório ao usuário.  O Workplace Analytics permite exportar o relatório. 

#### <a name="rectify"></a>Retificar

Conforme explicado acima, o Workplace Analytics usa os dados do Office 365 em combinação com os dados organizacionais que você fornece para gerar relatório de seu interesse. Os dados do Office 365 não podem ser retificados; eles se baseiam nas atividades de calendário e email de um usuário. No entanto, os dados organizacionais que você carregou no Workplace Analytics para gerar o relatório podem ser retificados.  Para fazer isso, será preciso corrigir os dados de origem, carregá-los e executar novamente o relatório para gerar um novo relatório do Workplace Analytics.

#### <a name="restrict"></a>Restringir

Para restringir o processamento de um usuário específico, você pode remover a licença do Workplace Analytics.

#### <a name="delete"></a>Excluir

Se um titular de dados quiser ser removido de um relatório do Workplace Analytics ou um conjunto de relatórios, você poderá excluir o relatório. É sua responsabilidade excluir usuários de quaisquer dados organizacionais usados para gerar o relatório e carregar os dados novamente. Todos os dados sobre o usuário são removidos quando uma conta de usuário é "excluída permanentemente" do Azure Active Directory.  

Para remover dados pessoais de um assunto de dados, o administrador global pode fazer o seguinte: 

1. Remover a licença do Workplace Analytics do assunto de dados.
2. Exclua a entrada do Azure Active Directory (AAD) para o assunto dos dados. (Para saber mais, confira [excluir um usuário](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory#delete-a-user).)
3. Contate o suporte e obtenha ajuda para a abrir um ticket de exclusão de usuário do Direitos de Assunto dos Dados (DSR). Nesse ticket identifique o assunto dos dados usando o Nome Principal do Usuário (UPN).
4. Exporte uma cópia dos dados de RH do sistema de RH da empresa (consulte [exportar dados](https://docs.microsoft.com/workplace-analytics/setup/prepare-organizational-data)), remova informações do assunto dos dados desse arquivo de dados de RH e carregue o arquivo de dados de RH editado no formato. csv para o Workplace Analytics (consulte [Carregar dados organizacionais](https://docs.microsoft.com/workplace-analytics/setup/upload-organizational-data)).

## <a name="part-3-responding-to-dsrs-for-system-generated-logs"></a>Parte 3: Responder às DSRs para logs gerados pelo sistema

A Microsoft também oferece a capacidade de acessar, exportar e excluir logs gerados pelo sistema que podem ser considerados pessoais de acordo com a definição ampla de "dados pessoais" do RGPD. Exemplos de logs gerados pelo sistema que podem ser considerados pessoais pelo RGPD incluem:

- Dados de uso de produtos e serviços, como os log de atividades do usuário
- Dados de solicitações e consultas de pesquisa do usuário
- Dados gerados por produtos e serviços como resultado da funcionalidade do sistema e da interação de usuários ou de outros sistemas

Não há suporte para a capacidade de restringir ou corrigir dados nos logs gerados pelo sistema. Dados em logs gerados pelo sistema constituem ações concretas realizadas na nuvem da Microsoft e dados de diagnóstico, e a modificação de tais dados comprometeria o registro histórico de ações e aumentaria os riscos de segurança e fraude.

### <a name="accessing-and-exporting-system-generated-logs"></a>Acessar e exportar logs gerados pelo sistema

O administrador de locatários é a única pessoa em sua organização que pode acessar os logs gerados pelo sistema associados ao uso de serviços e aplicativos do Office 365 por um usuário específico. Os dados recuperados de uma solicitação de exportação serão fornecidos em um formato legível para computador e serão fornecidos em arquivos que permitem ao usuário saber quais serviços são associados aos dados. Conforme observado acima, os dados recuperados não incluirão dados que possam comprometer a segurança ou estabilidade do serviço.

Para acessar e exportar logs gerados pelo sistema:

1. Acesse o portal do Azure e selecione **Todos os serviços**.
2. Digite política no filtro e, em seguida, selecione **Política**.
3. Na folha **Política**, selecione **Privacidade do usuário**, selecione **Gerenciar Solicitações de Usuário**e selecione **Adicionar solicitação de exportação**.
4. Preencha a **Solicitação de exportação de dados**:

    - **Usuário**. Digite o endereço de email do usuário do Azure Active Directory que solicitou a exportação.
    - **Assinatura**. Selecione a conta que você usa para informar o uso de recursos e cobrar por serviços. Essa também é a localização da sua conta de armazenamento do Azure.
    - **Conta de armazenamento**. Selecione a localização de seu Armazenamento do Microsoft Azure (Blob). Para saber mais, confira a Introdução ao Armazenamento do Microsoft Azure: armazenamento de Blob.
    - **Contêiner**. Crie um novo contêiner (ou selecione um existente) como o local de armazenamento para os dados de privacidade exportados do usuário.

5. Selecione **Criar**.

A solicitação de exportação entra no status **Pendente**. Você pode exibir o status do relatório em **Privacidade do usuário** > **Folha de visão geral**.

>[!IMPORTANT]
>Como os dados pessoais podem vir de vários sistemas, é possível que o processo de exportação possa levar até um mês para ser concluído.

### <a name="notify-about-exporting-or-deleting-issues"></a>Notificar problemas de exportação ou exclusão

Se você tiver problemas ao exportar ou excluir dados do Portal do Azure, acesse a folha **Ajuda + Suporte** do portal do Azure e envie um novo tíquete em **Gerenciamento de Assinaturas** > **Outra Solicitação de Segurança e Conformidade** > **Solicitações GDPR e Folha de Privacidade**.

>[!NOTE]
 >Ao exportar dados do portal do Azure, os dados gerados pelo sistema para alguns aplicativos não serão exportados. Para exportar dados para esses aplicativos, confira [Etapas adicionais para exportar dados de log gerados pelo sistema](https://docs.microsoft.com/microsoft-365/compliance/gdpr-system-generated-log-data).

A seguir há um resumo do acesso e da exportação de logs de gerados pelo sistema:

- **Quanto tempo leva para que uma solicitação de exportação usando o portal do Azure seja concluída?**: Isso pode depender de vários fatores. Geralmente, ela deve ser concluída em um ou dois dias, mas pode levar até 30 dias.
- **Em qual formato a saída estará?**: A saída será estruturada em arquivos legíveis por máquina, como XML, CSV ou JSON.
- **Quem tem acesso ao portal do Azure para enviar solicitações de acesso aos dados gerados pelo sistema?**: Os administradores globais do Office 365 têm acesso ao portal do Azure.
- **Quais dados são retornados pelos resultados da exportação?**: Os resultados contêm logs gerados pelo sistema armazenados pela Microsoft. Os dados exportados vão abranger vários serviços Microsoft, incluindo o Office 365, o Azure e o Dynamics. Os resultados não incluem dados que possam comprometer a segurança ou estabilidade do serviço.
- **Como os dados são retornados ao usuário?**: Os dados serão exportados para o local de armazenamento do Azure da organização; caberá aos administradores em sua organização determinar como eles exibirão/retornarão esses dados aos usuários.
- **Como serão os dados de log gerados pelo sistema?**: A seguir um exemplo, onde os dados estão no formato JSON:

    ```JSON
    [{
    "DateTime": "2017-04-28T12:09:29-07:00",
    "AppName": "SharePoint",
    "Action": "OpenFile",
    "IP": "154.192.13.131",
    "DevicePlatform": "Windows 1.0.1607"
    }]
    ```

Os dados de uso de produtos e serviços para alguns serviços mais frequentemente usados da Microsoft, como Exchange Online, SharePoint Online, Skype for Business, Yammer e Grupos do Office 365, também podem ser recuperados pesquisando o log de auditoria do Office 365 no Centro de Conformidade e Segurança.  Para saber mais, confira [Usar a ferramenta de pesquisa de log de auditoria do Office 365 nas investigações de DSR](#use-the-audit-log-search-tool-in-dsr-investigations) no Apêndice A. Usar o log de auditoria pode ser interessante para você, pois é possível atribuir permissões a outras pessoas na sua organização (como o responsável pela conformidade) para pesquisar o log de auditoria a fim de acessar esses dados.

### <a name="deleting-system-generated-logs"></a>Excluir os logs gerados pelo sistema

Para excluir logs gerados pelo sistema recuperados por meio de uma solicitação de acesso, você deve remover o usuário do serviço e excluir permanentemente sua conta do Azure Active Directory. Para obter instruções sobre como excluir permanentemente um usuário, confira a seção [Excluir um usuário](#deleting-a-user) deste guia. É importante observar que excluir permanentemente uma conta de usuário é um processo irreversível após iniciado.

Excluir permanentemente uma conta de usuário remove os dados do usuário dos logs gerados pelo sistema, exceto dados que possam comprometer a segurança ou estabilidade do serviço, para quase todos os serviços do Office 365 em 30 dias. 

Uma exceção a esse período de 30 dias é quando a exclusão permanente da conta de usuário no Exchange Online leva mais tempo do que isso. Isso ocorre devido à natureza crítica do conteúdo do Exchange Online e para evitar a perda acidental de dados. O Exchange Online foi intencionalmente projetado para colocar os dados em um estado de retenção por até 60 dias após a exclusão permanente de uma conta de usuário. Para excluir permanentemente os dados do Exchange Online de um usuário em um prazo de 30 dias, exclua permanentemente a conta do usuário no Azure Active Directory, contate o [suporte da Microsoft](https://support.microsoft.com/) e solicite que os dados do Exchange Online do usuário sejam manualmente removidos do processo de exclusão agendado.  Para saber mais, confira [Remover dados do Exchange Online](#removing-exchange-online-data), que foi explicado anteriormente neste guia

Excluir uma conta de usuário não removerá logs gerados pelo sistema para o Yammer e Kaizala. Para remover os dados desses aplicativos, siga um destes procedimentos:

- Yammer – [ gerenciar solicitações de entidades de dados GDPR do Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- Kaizala - [Exportar ou excluir dados organizacionais do usuário no Kaizala](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

#### <a name="national-clouds"></a>Nuvens nacionais

Um administrador de TI global precisa fazer o seguinte para exportar logs gerados pelo sistema nestas nuvens nacionais:

- **Office 365 Germany**: siga as etapas acima.
- **Office 365 US Government**: [acesse o portal de administração do Office 365](https://portal.office365.us) e envie uma solicitação ao Suporte da Microsoft.
- **Office 365 operado pela 21Vianet (China)**: [Vá para o portal de administração do Office 365 operado pela 21Vianet](https://portal.partner.microsoftonline.cn/AdminPortal/Home#/homepage) e acesse **Comércio** > **Assinatura** > **** Privacidade > **GDPR** e insira as informações necessárias.

## <a name="part-4-additional-resources-to-assist-you-with-dsrs"></a>Parte 4: Recursos adicionais para ajudar com as DSRs

### <a name="dsr-guides-for-other-microsoft-enterprise-services"></a>Guias de DSR para outros serviços corporativos da Microsoft

Este guia é dedicado ao tópico de como encontrar dados pessoais e agir sobre eles para responder às DSRs ao usar produtos, serviços e ferramentas administrativas do Office 365. Entre no [Portal de Confiança do Serviço Microsoft](https://servicetrust.microsoft.com/) para acessar guias semelhantes de outros serviços corporativos da Microsoft.

### <a name="microsoft-support"></a>Suporte da Microsoft

"Dados de Suporte" são os dados que você e os seus usuários fornecem à Microsoft em caso de engajamento com a Microsoft para receber suporte a produtos relacionados ao Office 365 ou outros produtos e serviços da Microsoft (por exemplo, para solução de comportamento inesperado de produtos). Alguns desses dados podem conter dados pessoais. Para saber mais, confira [Dados de serviços profissionais e Suporte da Microsoft que o titular solicita para o RGPD](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-prof-services).

### <a name="product-and-services-authenticated-with-an-org-id-for-which-microsoft-is-a-data-controller"></a>Produtos e serviços autenticados com uma ID da organização para os quais a Microsoft é um controlador de dados

As partes de 1 a 3 deste guia abrangem produtos e serviços para os quais a Microsoft é um processador de dados de sua organização e, portanto, o recurso DSR é disponibilizado para o administrador de locatários. Há várias circunstâncias em que os usuários podem usar a respectiva conta corporativa ou de estudante (também conhecida como “ID do Azure Active Directory” ou “ADD”) para entrar em produtos e serviços da Microsoft para os quais a Microsoft é um controlador de dados.  Para todos esses produtos e serviços, os usuários precisam inciar suas próprias solicitações de titular de dados diretamente com o usuário. Por natureza, os produtos e serviços que envolvem armazenamento de conteúdo criado pelo usuário permitem que os usuários acessem, exportem, retifiquem e excluam o respectivo conteúdo como parte da funcionalidade inerente dos produtos. Os cenários em que isso pode se aplicar incluem os seguintes:

- **Serviços online conectados opcionais:** Os Aplicativos do Microsoft 365 para empresas disponibilizam certos serviços online conectados opcionais ao usuário. Os serviços e controles de usuários relacionados estão listados [aqui](https://support.office.com/article/microsoft-s-other-connected-services-92c234f1-dc91-4dc1-925d-6c90fc3816d8). Você pode decidir se deseja permitir que seus usuários finais usem esses serviços. Para obter mais informações, confira [Como os administradores podem gerenciar serviços do controlador nos Aplicativos do Microsoft 365 para empresas](https://docs.microsoft.com/DeployOffice/manage-controller-services-office-365-proplus). Se esses serviços opcionais processam dados pessoais, a Microsoft é um controlador de dados para esses serviços.
- **Comentários do usuário:** se seus usuários optarem por fornecer feedback sobre produtos e serviços da Microsoft, a Microsoft é um controlador de dados para esse feedback na medida em que contiver dados pessoais. A Microsoft atende a solicitações de entidades de dados para feedback coletado pela Microsoft (incluindo feedback gerenciado por subprocessadores da Microsoft), exceto nos casos em que a Microsoft instruir os usuários a não incluírem dados pessoais durante o processo de coleta de feedback. Exceções: se a Microsoft tiver instruído os usuários a não incluírem dados pessoais durante o processo de coleta de feedback, a Microsoft contará com essa instrução e presumirá que nenhum dado foi fornecido. Os usuários que criaram uma conta separada com provedores de serviços de feedback de terceiros precisam preencher suas DSR diretamente com esses provedores.
- **Windows autenticado por meio de conta corporativa ou de estudante:** se a sua organização tiver adquirido licenças do Windows e seus usuários fizerem autenticação no Windows fornecido pela organização com suas contas corporativas ou de estudante, a Microsoft atuará como um controlador de dados.
- **Produtos ou serviços adquiridos pelo usuário:** se você permitir que seus usuários, agindo em sua capacidade individual, adquiram produtos ou serviços da Microsoft que usam o ADD para autenticação (por exemplo, complementos ou aplicativos do Office disponíveis em uma Loja da Microsoft), a Microsoft poderá ser um controlador de dados. Para quaisquer produtos ou serviços da Microsoft, os usuários precisarão entrar em contato diretamente com a Microsoft para iniciar uma DSR.

>[!IMPORTANT]
>Se você excluir um usuário enquanto habilitado por meio do Azure Active Directory, o usuário (antigo) perderá a capacidade de entrar em qualquer produto ou serviço no qual se baseava para uma conta corporativa ou de estudante. Além disso, a Microsoft não poderá mais autenticar o usuário em relação a uma solicitação DSR para produtos ou serviços para os quais a Microsoft é um controlador de dados. Se desejar permitir que um usuário inicie DSRs em relação a tais serviços, é importante orientá-lo a fazer isso antes de você excluir a conta do AAD do usuário.

### <a name="personal-accounts"></a>Contas pessoais

Se os usuários tiverem usado contas da Microsoft (isto é, contas pessoais) para adquirir produtos e serviços da Microsoft para uso e para os quais a Microsoft é um controlador de dados, eles poderão iniciar solicitações de DSR usando o [painel de privacidade da Microsoft](https://account.microsoft.com/account/privacy). 

### <a name="third-party-products"></a>Produtos de terceiros

Se a sua organização ou os usuários, agindo em sua capacidade individual, tiverem adquirido produtos ou serviços de terceiros e usado a respectiva conta corporativa ou de estudante da Microsoft para autenticação, todas as solicitações do titular dos dados deverão ser direcionadas ao terceiro aplicável.

## <a name="appendix-a-preparing-for-dsr-investigations"></a>Apêndice A: Preparar-se para investigações de DSR

Para ajudar a preparar a sua organização para assumir investigações de DSR usando os serviços do Office 365, considere as seguintes recomendações:

- Usar a ferramenta de ocorrência de Descoberta Eletrônica da DSR no Centro de Conformidade e Segurança para gerenciar as investigações de DSR
- Configurar os Limites de Conformidade para limitar o escopo das Pesquisas de Conteúdo
- Usar a ferramenta de pesquisa do log de auditoria em investigações de DSR

### <a name="use-the-dsr-case-tool-to-manage-dsr-investigations"></a>Usar a ferramenta de ocorrência da DSR para gerenciar as investigações de DSR

É recomendável usar a ferramenta de ocorrência da DSR no Centro de Conformidade e Segurança para gerenciar as investigações de DSR. Ao usar a ferramenta de ocorrência da DSR, você pode:

- Criar uma ocorrência separada para cada investigação de DSR.

- Usar a pesquisa interna para pesquisar todo o conteúdo relacionado a um titular de dados específico. Quando você cria uma ocorrência e inicia a pesquisa, estes locais de conteúdo são pesquisados:

   - Todas as caixas de correio em sua organização (incluindo caixas de correio associadas em todos os Grupos do Microsoft 365 e Microsoft Teams)
   - Todos os sites do SharePoint Online e contas do OneDrive for Business em sua organização
   - Todos os sites do Microsoft Teams e sites do grupo do Microsoft 365 em sua organização
   - Todas as pastas públicas no Exchange Online

- Revisar a consulta de pesquisa padrão e executar novamente a pesquisa para limitar os resultados da pesquisa.

- Controlar quem tem acesso à adicionando pessoas como membros da ocorrência; somente membros podem acessar a ocorrência e eles poderão ver apenas as respectivas ocorrências na lista de ocorrências na página de ocorrências de DSR no Centro de Conformidade e Segurança. Além disso, você pode atribuir diferentes permissões a diferentes membros da mesma ocorrência. Por exemplo, você pode permitir que alguns membros exibam somente a ocorrência e os resultados de uma Pesquisa de Conteúdo e permitir que outros membros criem pesquisas e exportem resultados da pesquisa.

- Criar trabalhos de exportação para exportar os resultados da pesquisa em resposta a uma solicitação de exportação de DSR. É possível exportar todo o conteúdo retornado pela Pesquisa de Conteúdo. Além disso, outros dados do Office 365 relacionados a um titular de dados também poderão ser exportados.

- Criar trabalhos de exportação para exportar os resultados da pesquisa em resposta a uma solicitação de exportação de DSR. É possível exportar todo o conteúdo retornado pela Pesquisa de Conteúdo. Você também pode exportar logs gerados pelo sistema para o serviço de Roaming do Office.

- Excluir ocorrências quando o processo de investigação quando o processo de investigação de DSR é concluído. Isso remove todas as pesquisas de conteúdo e exportará trabalhos associados à ocorrência.

Para começar a usar os casos de DSR, confira [Gerenciar solicitações de titular de dados do RGPD com a ferramenta de casos de DSR no Centro de Conformidade e Segurança](https://docs.microsoft.com/microsoft-365/compliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool).

>[!IMPORTANT]
>Um Administrador de Descoberta Eletrônica pode exibir e gerenciar todas as ocorrências de DSR em sua organização. Para obter informações sobre as diferentes funções relacionadas à Descoberta eletrônica, confira [Atribuir permissões da Descoberta Eletrônica a membros de ocorrência potenciais](https://docs.microsoft.com/Office365/SecurityCompliance/assign-ediscovery-permissions).

### <a name="set-up-compliance-boundaries-to-limit-the-scope-of-content-searches"></a>Configurar os Limites de Conformidade para limitar o escopo das Pesquisas de Conteúdo

Os Limites de Conformidade são implementados usando a funcionalidade de filtragem de permissões de pesquisa no Centro de Conformidade e Segurança. Os Limites de Conformidade criam limites de pesquisa lógicos em uma organização que controlam/limitam quais locais de conteúdo (por exemplo, caixas de correio do Exchange Online e sites do SharePoint Online) um administrador de TI ou responsável pela conformidade pode pesquisar. Os Limites de Conformidade são úteis para organizações multinacionais que precisam respeitar limites geográficos, organizações governamentais que precisam separar diferentes agências e organizações corporativas que são segregadas em unidades de negócios ou departamentos. Em todos esses cenários, os Limites de Conformidade podem ser usados em investigações de DSR para limitar quais caixas de correio e sites podem ser pesquisados pelas pessoas envolvidas na investigação.

Você pode usar Limites de Conformidade com ocorrências de Descoberta Eletrônica a fim de limitar os locais de conteúdo que podem ser pesquisados em uma investigação para esses locais somente dentro da agência ou da unidade de negócios.

Veja a seguir uma visão geral de alto nível de como implementar Limites de Conformidade (junto com casos de Descoberta Eletrônica) para investigações de DSR.

1. Determine as agências em sua organização que serão designadas como um limite de conformidade.

2. Determine qual atributo do objeto de usuário no Azure Active Directory será usado para definir o limite de conformidade. Por exemplo, você pode escolher o atributo Country, CountryCode ou Department, de modo que os membros do grupo de função de administrador que você cria na próxima etapa possam pesquisar apenas os locais de conteúdo dos usuários que têm um valor específico para esse atributo. Assim você limita quem pode pesquisar conteúdo em uma agência específica.

>[!NOTE]
>Atualmente, você deve executar uma etapa adicional para o OneDrive for Business e registrar uma solicitação ao Suporte da Microsoft para que o atributo seja sincronizado com as contas do OneDrive for Business.

4. Crie um grupo de função de administrador no Centro de Conformidade e Segurança para cada limite de conformidade. É recomendável criar esses grupos de funções copiando o grupo de função interno de Gerente de Descoberta Eletrônica e, em seguida, removendo todas as funções, conforme a necessidade.

5. Adicione membros a cada um dos grupos de funções específicos como Gerentes de Descoberta Eletrônica. Os membros são as pessoas responsáveis por investigar e responder às DSRs, e geralmente incluem administradores de TI, responsáveis pela privacidade de dados, gerentes de conformidade e representantes de recursos humanos.

6. Crie um filtro de permissões de pesquisa para cada limite de conformidade a fim de que os membros do grupo de função de administrador correspondente possam pesquisar apenas caixas de correio e sites de usuários dentro da agência/do limite de conformidade. O filtro de permissões de pesquisa permitirá que os membros do grupo de função correspondente pesquisem apenas os locais de conteúdo com valor do atributo de objeto de usuário que corresponda à agência/ao limite de conformidade.

Para obter instruções passo a passo, confira [Configurar limites de conformidade para investigações de Descoberta Eletrônica no Office 365](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries).

### <a name="use-the-audit-log-search-tool-in-dsr-investigations"></a>Usar a ferramenta de pesquisa do log de auditoria em investigações de DSR

Os administradores de TI podem usar a ferramenta de pesquisa do log de auditoria no Centro de Conformidade e Segurança para identificar documentos, arquivos e outros recursos do Office 365 que os usuários criaram, acessaram, alteraram ou excluíram. A pesquisa por esse tipo de atividade pode ser útil nas investigações de DSR. Por exemplo, no SharePoint Online e OneDrive for Business, os eventos de auditoria são registrados quando os usuários executam estas atividades:

- Acessam um arquivo
- Modificam um arquivo
- Movem um arquivo
- Carregam ou baixam um arquivo

É possível pesquisar o log de auditoria em busca de atividades específicas, tipos de atividade, atividades executadas por um usuário específico e outros critérios de pesquisa. Além das atividades do SharePoint Online e OneDrive for Business, você também pode pesquisar atividades no Flow, Power BI e Microsoft Teams. Os registros de auditoria são retidos por 90 dias. Portanto, não será possível pesquisar as atividades do usuário que ocorreram há mais de 90 dias. Para obter uma lista completa das atividades auditadas e como pesquisar o log de auditoria, confira [Pesquisar o log de auditoria no Centro de Conformidade e Segurança](search-the-audit-log-in-security-and-compliance.md).

>[!TIP]
>Para contornar a limitação de 90 dias discutida acima e manter um histórico de execução dos registros de auditoria da sua organização, você pode exportar todas as atividades em uma agenda recorrente (por exemplo, a cada 30 dias) para ter um registro contínuo de registros de auditoria da organização.

## <a name="appendix-b-change-log"></a>Apêndice B: log de alterações

A tabela a seguir lista as alterações ao guia DSR do Office 365 desde sua publicação inicial em 25 de maio de 2018.

|Data  |Seção/Aplicativo |Alteração  |
|:---------|:---------|:---------|
|18/09/2018 | [Quadro de comunicações](#whiteboard) |O Whiteboard Preview não está mais em visualização e foi lançado para disponibilidade geral. Portanto, a seção no Whiteboard Preview foi renomeada para "Whiteboard para PC, Surface Hub e outras plataformas;" os procedimentos para acesso, exportação e exclusão de dados foram removidos desta seção e substituídos por um link para o artigo de suporte do Whiteboard.|
|11/08/2018 | [Workplace Analytics](#workplace-analytics) |Obter orientações passo a passo adicionais para a seção excluir sobre como remover um assunto de dados com o Workplace Analytics e como remover informações sobre um assunto de dados de um relatório do Workplace Analytics.|
|11/12/2018| Todos| Corrigidos marcadores quebrados e links quebrados para tópicos externos.|
|9/1/2019| StaffHub |Na seção Excluir, foi atualizada a descrição do que acontece quando uma conta de usuário é excluída permanentemente.|
|8/5/2019| [Publisher](#publisher)|Conteúdo adicional sobre como responder os DSRs para o Publisher.|
|11/7/2019| [MyAnalytics](#myanalytics)|A capacidade de um administrador de usar a ferramenta de ocorrência de DSR no Centro de Conformidade e Segurança para exportar dados do MyAnalytics foi removida porque todos os usuários agora podem ver seus dados no aplicativo MyAnalytics. |
|11/6/2019 |[Educação](#education)|Vinculado a novos tópicos sobre o uso de scripts do PowerShell para obter uma lista de classes para um aluno específico e, em seguida, exportar ou excluir seus dados.|
|28/01/2020| Todos | Removido o StaffHub do documento, o StaffHub está desativado. |
||||
