---
title: Isolamento e controle de acesso no Microsoft 365
ms.author: robmazz
author: robmazz
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
- SPO_Content
f1.keywords:
- NOCSH
description: 'Resumo: uma explicação de isolamento e controle de acesso dentro dos vários aplicativos do Microsoft 365.'
ms.openlocfilehash: 53f60c09b94bdcc2515bcc5ff70dfbcd47f42bb4
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332323"
---
# <a name="isolation-and-access-control-in-microsoft-365"></a>Isolamento e controle de acesso no Microsoft 365

O Azure Active Directory (Azure AD) e o Microsoft 365 usam um modelo de dados altamente complexo que inclui dezenas de serviços, centenas de entidades, milhares de relações e dezenas de milhares de atributos. Em um nível alto, o Azure AD e os diretórios de serviço são os contêineres de locatários e destinatários mantidos em sincronia usando protocolos de replicação baseados em estado. Além das informações de diretório mantidas no Azure AD, cada uma das cargas de trabalho de serviço tem sua própria infraestrutura de serviços de diretório.
 
![Sincronização de dados do locatário do Microsoft 365](../media/office-365-isolation-tenant-data-sync.png)

Nesse modelo, não há uma única fonte de dados de diretório. Sistemas específicos têm dados individuais, mas nenhum sistema contém todos os dados. Os serviços do Microsoft 365 cooperam com o Azure AD nesse modelo de dados. O Azure AD é o "sistema de verdade" para dados compartilhados, que geralmente são dados pequenos e estáticos usados por cada serviço. O modelo federado usado no Microsoft 365 e no Azure AD fornece a exibição compartilhada dos dados.

O Microsoft 365 usa armazenamento físico e armazenamento em nuvem do Azure. O Exchange Online (incluindo a Proteção do Exchange Online) e o Skype for Business usam seu próprio armazenamento para dados do cliente. O SharePoint Online usa o armazenamento do SQL Server e o Armazenamento do Azure, por isso a necessidade de isolamento adicional dos dados do cliente no nível de armazenamento.

## <a name="exchange-online"></a>Exchange Online

O Exchange Online armazena dados do cliente em caixas de correio. As caixas de correio são hospedadas nos bancos de dados do Mecanismo de Armazenamento Extensível (ESE), chamados de bancos de dados de caixa de correio. Isso inclui caixas de correio de usuário, caixas de correio vinculadas, caixas de correio compartilhadas e caixas de correio de pasta pública. As caixas de correio do usuário incluem conteúdo salvo do Skype for Business, como históricos de conversas.

O conteúdo da caixa de correio do usuário inclui:

- Emails e anexos de email
- Informações de calendário e de livre/ocupado
- Contatos
- Tarefas
- Observações
- Grupos
- Dados de inferência

Cada banco de dados de caixa de correio no Exchange Online contém caixas de correio de vários locatários. Um código de autorização protegerá cada caixa de correio, incluindo em um local de trabalho. Por padrão, somente o usuário atribuído tem acesso a uma caixa de correio. A lista de controle de acesso (ACL) que segura uma caixa de correio contém uma identidade autenticada pelo Azure AD no nível do locatário. As caixas de correio de cada locatário são limitadas a identidades autenticadas no provedor de autenticação do locatário, que inclui apenas usuários desse locatário. O conteúdo no locatário A não pode ser obtido de forma alguma pelos usuários no locatário B, a menos que seja explicitamente aprovado pelo locatário A.

## <a name="skype-for-business"></a>Skype for Business

O Skype for Business armazena dados em vários lugares:

- As informações de usuário e conta, que incluem pontos de extremidade de conexão, IDs de locatário, planos de discagem, configurações de roaming, estado de presença, listas de contatos, etc., são armazenadas nos servidores do Active Directory do Skype for Business e em vários servidores de banco de dados do Skype for Business. As listas de contatos são armazenadas na caixa de correio do Exchange Online do usuário se o usuário estiver habilitado para ambos os produtos ou em servidores do Skype for Business, se o usuário não estiver. Os servidores de banco de dados do Skype for Business não são particionados por locatário, mas o isolamento de multilocatária dos dados é imposto por meio do RBAC (controle de acesso baseado em função).
- O conteúdo da reunião e os dados carregados são armazenados em compartilhamentos do SISTEMA de Arquivos Distribuídos (DFS). Esse conteúdo também pode ser arquivado no Exchange Online, se habilitado. Os compartilhamentos DFS não são particionados por locatário. o conteúdo é protegido com ACLs e a multi-aluguel é imposta por meio do RBAC.
- Os registros de detalhes das chamada, que são o histórico de atividades, como histórico de chamada, sessões de IM, compartilhamento de aplicativos, histórico de IM etc., também podem ser armazenados no Exchange Online, mas a maioria dos registros de detalhes das chamada é armazenada temporariamente em servidores cdr (registros de detalhes das chamada). O conteúdo não é particionado por locatário, mas a multi-locação é imposta por meio do RBAC.

## <a name="sharepoint-online"></a>SharePoint Online

O SharePoint Online tem vários mecanismos independentes que fornecem isolamento de dados. Ele armazena objetos como código abstraído em bancos de dados de aplicativos. Por exemplo, quando um usuário carrega um arquivo no SharePoint Online, o arquivo é desmontado, convertido em código de aplicativo e armazenado em várias tabelas em vários bancos de dados.

Se um usuário puder obter acesso direto ao armazenamento que contém os dados, o conteúdo não será interpretado por uma pessoa ou qualquer outro sistema que não seja o SharePoint Online. Esses mecanismos incluem propriedades e controle de acesso de segurança. Todos os recursos do SharePoint Online são protegidos pelo código de autorização e pela política RBAC, incluindo em um aluguel. A lista de controle de acesso (ACL) que segura um recurso contém uma identidade autenticada no nível do locatário. Os dados do SharePoint Online para um locatário são limitados às identidades autenticadas pelo provedor de autenticação do locatário.

Além das ACLs, uma propriedade no nível do locatário que especifica o provedor de autenticação (que é o Azure AD específico do locatário) é gravado uma vez e não pode ser alterado uma vez definido. Depois que a propriedade de locatário do provedor de autenticação tiver sido definida para um locatário, ela não poderá ser alterada usando quaisquer APIs expostas a um locatário.

Uma *SubscriptionId exclusiva* é usada para cada locatário. Todos os sites de clientes pertencem a um locatário e uma *SubscriptionId* exclusiva é atribuída ao locatário. A *propriedade SubscriptionId* em um site é escrita uma vez e é permanente. Depois de atribuído a um locatário, um site não pode ser movido para um locatário diferente. *SubscriptionId* é a chave usada para criar o escopo de segurança para o provedor de autenticação e está vinculada ao locatário.

O SharePoint Online usa o SQL Server e o Armazenamento do Azure para armazenamento de metadados de conteúdo. A chave de partição para o armazenamento de conteúdo *é SiteId* no SQL. Ao executar uma consulta SQL, o SharePoint Online usa um *SiteId* verificado como parte de uma verificação *subscriptionId* no nível do locatário.

O SharePoint Online armazena conteúdo de arquivo criptografado em blobs do Microsoft Azure. Cada farm do SharePoint Online tem sua própria conta do Microsoft Azure e todos os blobs salvos no Azure são criptografados individualmente com uma chave armazenada no armazenamento de conteúdo do SQL. A chave de criptografia protegida em código pela camada de autorização e não exposta diretamente ao usuário final. O SharePoint Online tem monitoramento em tempo real para detectar quando uma solicitação HTTP lê ou grava dados para mais de um locatário. A identidade de *solicitação SubscriptionId* é rastreada em relação à *SubscriptionId* do recurso acessado. As solicitações para acessar recursos de mais de um locatário nunca devem ocorrer pelos usuários finais. As solicitações de serviço em um ambiente de vários locatários são a única exceção. Por exemplo, o rastreador de pesquisa recebe as alterações de conteúdo de um banco de dados inteiro de uma só vez. Isso geralmente envolve consultar sites de mais de um locatário em uma única solicitação de serviço, o que é feito por motivos de eficiência.

## <a name="teams"></a>Teams

Os dados do Teams são armazenados de forma diferente, dependendo do tipo de conteúdo. 

Confira a sessão [de breakout do Ignite na arquitetura do Microsoft Teams](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) para uma discussão detalhada.

### <a name="core-teams-customer-data"></a>Principais dados do cliente do Teams

Se seu locatário estiver provisionado na Austrália, Canadá, União Europeia, França, Alemanha, Índia, Japão, África do Sul, Coreia do Sul, Suíça (que inclui Liechtenstein), Emirados Árabes Unidos, Reino Unido ou Estados Unidos, a Microsoft armazenará os seguintes dados de cliente em repouso somente nesse local:

- Chats do Teams, conversas de equipe e canal, imagens, mensagens de caixa postal e contatos.
- O conteúdo do site do SharePoint Online e os arquivos armazenados neste site.
- Arquivos carregados no OneDrive para trabalho ou escola.

#### <a name="chat-channel-messages-team-structure"></a>Chat, mensagens de canal, estrutura da equipe

Todas as equipes no Teams são respaldadas por um Grupo do Microsoft 365, seu site do SharePoint e caixa de correio do Exchange. Chats privados (incluindo chats em grupo), mensagens enviadas como parte de uma conversa em um canal e a estrutura de equipes e canais são armazenadas em um serviço de chat em execução no Azure. Os dados também são armazenados em uma pasta oculta nas caixas de correio de usuário e grupo para habilitar recursos de Proteção de Informações.

#### <a name="voicemail-and-contacts"></a>Caixa postal e contatos

As caixas postal são armazenadas no Exchange. Os contatos são armazenados no armazenamento de dados na nuvem baseado no Exchange. O Exchange e o armazenamento em nuvem baseado no Exchange já fornecem residência de dados em cada uma das re análises geográficas de datacenter em todo o mundo. Para todas as equipes, a caixa postal e os contatos são armazenados no país para Austrália, Canadá, França, Alemanha, Índia, Japão, Emirados Árabes Unidos, Reino Unido, África do Sul, Coreia do Sul, Suíça (que inclui Liechtenstein) e os Estados Unidos. Para todos os outros países, os arquivos são armazenados nos EUA, na Europa ou Asia-Pacific local com base na afinidade de locatários.

#### <a name="images-and-media"></a>Imagens e mídia

A mídia usada em chats (exceto giphy GIFs que não são armazenados, mas são um link de referência para a URL de serviço Giphy original, Giphy é um serviço não Microsoft) é armazenada em um serviço de mídia baseado no Azure que é implantado nos mesmos locais que o serviço de chat.

#### <a name="files"></a>Arquivos

Arquivos (incluindo OneNote e Wiki) que alguém compartilha em um canal são armazenados no site do SharePoint da equipe. Os arquivos compartilhados em um chat privado ou em um chat durante uma reunião ou chamada são carregados e armazenados na conta do OneDrive for work or school do usuário que compartilha o arquivo. O Exchange, o SharePoint e o OneDrive já fornecem residência de dados em cada uma das redução geográficas de datacenter em todo o mundo. Portanto, para clientes existentes, todos os arquivos, blocos de anotações do OneNote, conteúdo wiki do Teams e caixas de correio que fazem parte da experiência do Teams já estão armazenados no local com base na afinidade do locatário. Os arquivos são armazenados no país para Austrália, Canadá, França, Alemanha, Índia, Japão, Emirados Árabes Unidos, Reino Unido, África do Sul, Coreia do Sul e Suíça (que inclui Liechtenstein). Para todos os outros países, os arquivos são armazenados nos EUA, Europa ou Pacífico Asiático com base na afinidade de locatários.
