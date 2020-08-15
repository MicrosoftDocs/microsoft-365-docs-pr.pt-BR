---
title: Isolamento e controle de acesso no Microsoft 365
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
- SPO_Content
f1.keywords:
- NOCSH
description: 'Resumo: uma explicação do isolamento e controle de acesso dentro dos vários aplicativos do Microsoft 365.'
ms.openlocfilehash: 40a1f1d93fe34333366e456cc006ab2d1c700a83
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687248"
---
# <a name="isolation-and-access-control-in-microsoft-365"></a>Isolamento e controle de acesso no Microsoft 365

O Azure Active Directory (Azure AD) e o Microsoft 365 usam um modelo de dados altamente complexo que inclui dezenas de serviços, centenas de entidades, milhares de relações e dezenas de milhares de atributos. Em um nível alto, o Azure AD e os diretórios de serviço são os contêineres de locatários e destinatários mantidos em sincronia usando protocolos de replicação baseados em estado. Além das informações de diretório mantidas no Azure AD, cada uma das cargas de trabalho de serviço tem sua própria infraestrutura de serviços de diretório.
 
![Sincronização de dados do Microsoft 365 locatário](../media/office-365-isolation-tenant-data-sync.png)

Dentro desse modelo, não há uma única fonte de dados de diretório. Sistemas específicos possuem partes individuais de dados, mas nenhum sistema único armazena todos os dados. Os serviços 365 da Microsoft cooperar com o Azure AD neste modelo de dados. O Azure AD é o "sistema de verdade" para dados compartilhados, que normalmente são pequenos e estáticos usados por todos os serviços. O modelo federado usado no Microsoft 365 e no Azure AD fornece a exibição compartilhada dos dados.

O Microsoft 365 usa o armazenamento físico e o armazenamento em nuvem do Azure. O Exchange Online (incluindo o Exchange Online Protection) e o Skype for Business usam seu próprio armazenamento para dados do cliente. O SharePoint Online usa o armazenamento do SQL Server e o armazenamento do Azure, portanto, a necessidade de isolamento adicional dos dados do cliente no nível de armazenamento.

## <a name="exchange-online"></a>Exchange Online

O Exchange Online armazena dados do cliente em caixas de correio. As caixas de correio são hospedadas em bancos de dados ESE (Extensible Storage Engine) chamados de bancos de dados de caixa de correio. Isso inclui caixas de correio de usuário, caixas de correio vinculadas, caixas de correio compartilhadas e caixas de correio de pasta pública. As caixas de correio de usuários incluem o conteúdo salvo do Skype for Business, como históricos de conversas.

O conteúdo da caixa de correio do usuário inclui:

- Emails e anexos de email
- Informações de calendário e disponibilidade
- Contatos
- Tarefas
- Observações
- Grupos
- Dados de inferência

Cada banco de dados de caixa de correio no Exchange Online contém caixas de correio de vários locatários. Um código de autorização protege cada caixa de correio, incluindo dentro de uma locação. Por padrão, somente o usuário atribuído tem acesso a uma caixa de correio. A lista de controle de acesso (ACL) que protege uma caixa de correio contém uma identidade autenticada pelo Azure AD no nível do locatário. As caixas de correio de cada locatário estão limitadas às identidades autenticadas no provedor de autenticação do locatário, que inclui apenas os usuários desse locatário. O conteúdo no locatário A não pode ser obtido por usuários no locatário B, a menos que explicitamente aprovado pelo locatário A.

## <a name="skype-for-business"></a>Skype for Business

O Skype for Business armazena dados em vários locais:

- As informações de usuário e conta, que incluem pontos de extremidade de conexão, IDs de locatário, planos de discagem, configurações de roaming, estado de presença, listas de contatos, etc., são armazenadas nos servidores do Active Directory do Skype for Business e em vários servidores de banco de dados do Skype for Business. As listas de contatos são armazenadas na caixa de correio do Exchange Online do usuário se o usuário estiver habilitado para ambos os produtos ou nos servidores do Skype for Business se o usuário não for. Os servidores de banco de dados do Skype for Business não são particionados por locatário, mas o isolamento de vários associados é imposto por meio do controle de acesso baseado em função (RBAC).
- O conteúdo da reunião e os dados carregados são armazenados em compartilhamentos do sistema de arquivos distribuídos (DFS). Esse conteúdo também pode ser arquivado no Exchange Online, se estiver habilitado. Os compartilhamentos DFS não são particionados por locatário. o conteúdo é protegido com ACLs e a multilocação é imposta por meio de RBAC.
- Os registros de detalhes da chamada, que são o histórico de atividades, como histórico de chamadas, sessões de IM, compartilhamento de aplicativos, histórico de IM, etc., também podem ser armazenados no Exchange Online, mas a maioria dos registros de detalhes das chamadas são temporariamente armazenados em servidores de CDR (registro de detalhes de chamadas). O conteúdo não é particionado por locatário, mas a multilocação é imposta por meio de RBAC.

## <a name="sharepoint-online"></a>SharePoint Online

O SharePoint Online tem vários mecanismos independentes que oferecem isolamento de dados. Ele armazena objetos como código abstrato em bancos de dados de aplicativo. Por exemplo, quando um usuário carrega um arquivo para o SharePoint Online, o arquivo é desmontado, convertido em código do aplicativo e armazenado em várias tabelas em vários bancos de dados.

Se um usuário puder obter acesso direto ao armazenamento que contém os dados, o conteúdo não poderá ser interpretado por um humano ou qualquer sistema que não seja o SharePoint Online. Esses mecanismos incluem controle de acesso de segurança e propriedades. Todos os recursos do SharePoint Online são protegidos pelo código de autorização e pela política RBAC, incluindo dentro de um locatário. A lista de controle de acesso (ACL) que protege um recurso contém uma identidade autenticada no nível do locatário. Os dados do SharePoint Online para um locatário são limitados às identidades autenticadas pelo provedor de autenticação para o locatário.

Além das ACLs, uma propriedade de nível de locatário que especifica o provedor de autenticação (que é o Azure AD específico do locatário), é escrita uma vez e não pode ser alterada depois de definida. Depois que a propriedade locatário do provedor de autenticação tiver sido definida para um locatário, ela não poderá ser alterada usando as APIs expostas a um locatário.

Um *SubscriptionId* exclusivo é usado para cada locatário. Todos os sites de clientes pertencem a um locatário e recebem uma *assinatura* exclusiva para o locatário. A propriedade *SubscriptionId* em um site é escrita uma vez e é permanente. Uma vez atribuída a um locatário, um site não pode ser movido para outro locatário. *SubscriptionId* é a chave usada para criar o escopo de segurança para o provedor de autenticação e está vinculada ao locatário.

O SharePoint Online usa o SQL Server e o armazenamento do Azure para armazenamento de metadados de conteúdo. A chave de partição para o repositório de conteúdo é *SiteId* no SQL. Ao executar uma consulta SQL, o SharePoint Online usa um *SiteId* verificado como parte de uma verificação de *SubscriptionId* no nível do locatário.

O SharePoint Online armazena conteúdo de arquivo criptografado em BLOBs do Microsoft Azure. Cada farm do SharePoint Online tem sua própria conta do Microsoft Azure e todos os BLOBs salvos no Azure são criptografados individualmente com uma chave armazenada no repositório de conteúdo do SQL. A chave de criptografia protegida no código pela camada de autorização e não exposta diretamente ao usuário final. O SharePoint Online tem monitoramento em tempo real para detectar quando uma solicitação HTTP lê ou grava dados para mais de um locatário. A identidade da solicitação *SubscriptionId* é controlada em relação à *SubscriptionId* do recurso acessado. As solicitações para acessar recursos de mais de um locatário nunca devem acontecer por usuários finais. As solicitações de serviço em um ambiente de vários locatários são a única exceção. Por exemplo, o rastreador de pesquisa recebe alterações de conteúdo para todo o banco de dados de uma só vez. Isso geralmente envolve a consulta de sites de mais de um locatário em uma única solicitação de serviço, que é feita por motivos de eficiência.

## <a name="teams"></a>Teams

Seus dados do teams são armazenados de forma diferente, dependendo do tipo de conteúdo. 

Confira a [sessão de debates do Ignite na arquitetura do Microsoft Teams](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) para uma discussão aprofundada.

### <a name="core-teams-customer-data"></a>Dados do cliente de Teams principais

Se seu locatário estiver provisionado na Austrália, no Canadá, na União Européia, na França, na Alemanha, na Índia, no Japão, na África do Sul, na Coréia do Sul, na Suíça (que inclui o Liechtenstein), os Emirados Árabes Unidos, o Reino Unido ou os Estados Unidos, a Microsoft armazena os seguintes dados do cliente em repouso apenas dentro desse local:

- Chats de equipes, conversas de canal e de equipe, imagens, mensagens de caixa postal e contatos.
- O conteúdo do site do SharePoint Online e os arquivos armazenados neste site.
- Arquivos carregados no OneDrive para trabalho ou escola.

#### <a name="chat-channel-messages-team-structure"></a>Chat, mensagens de canal, estrutura da equipe

Cada equipe do teams tem o respaldo de um grupo do Microsoft 365 e do seu site do SharePoint e da caixa de correio do Exchange. Chats privados (incluindo chats de grupo), mensagens enviadas como parte de uma conversa em um canal e a estrutura de equipes e canais são armazenadas em um serviço de chat em execução no Azure. Os dados também são armazenados em uma pasta oculta nas caixas de correio de usuário e de grupo para habilitar recursos de proteção de informações.

#### <a name="voicemail-and-contacts"></a>Caixa postal e contatos

As caixa postal são armazenadas no Exchange. Os contatos são armazenados no armazenamento de dados de nuvem baseado no Exchange. O Exchange e o armazenamento em nuvem baseado no Exchange já fornecem residências de dados em cada um dos GEOS de datacenter mundiais. Para todas as equipes, a caixa postal e os contatos são armazenados no país da Austrália, Canadá, França, Alemanha, Índia, Japão, Emirados Árabes Unidos, Reino Unido, África do Sul, Coréia do Sul, Suíça (que inclui o Liechtenstein) e os Estados Unidos. Para todos os outros países, os arquivos são armazenados no local US, Europe ou Ásia-Pacífico com base na afinidade de locatários.

#### <a name="images-and-media"></a>Imagens e mídia

Mídia usada em chats (exceto GIFs Giphy que não são armazenadas, mas que são um link de referência para a URL de serviço do Giphy original, Giphy é um serviço não-Microsoft) é armazenada em um serviço de mídia baseado no Azure implantado nos mesmos locais que o serviço de chat.

#### <a name="files"></a>Arquivos

Arquivos (incluindo o OneNote e o wiki) que alguém compartilha em um canal é armazenado no site do SharePoint da equipe. Arquivos compartilhados em um chat privado ou chat durante uma reunião ou chamada são carregados e armazenados na conta do OneDrive for Work ou School do usuário que compartilha o arquivo. O Exchange, o SharePoint e o OneDrive já fornecem residências de dados em cada um dos GEOS de datacenter mundiais. Portanto, para clientes existentes, todos os arquivos, blocos de anotações do OneNote, conteúdo wiki do Teams e caixas de correio que fazem parte da experiência do teams já estão armazenados no local com base em sua afinidade de locatário. Os arquivos são armazenados no país da Austrália, do Canadá, da França, da Alemanha, da Índia, do Japão, dos Emirados Árabes Unidos, do Reino Unido, da África do Sul, da Coréia do Sul e da Suíça (que inclui o Liechtenstein). Para todos os outros países, os arquivos são armazenados no local US, Europe ou Ásia Pacífico com base na afinidade de locatários.
