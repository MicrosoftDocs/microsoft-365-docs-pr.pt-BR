---
title: Perguntas frequentes gerais sobre migração de dados
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 1f01bc6f-5d37-4d14-bdd3-9d94a1e23e14
f1.keywords:
- NOCSH
description: Encontre respostas para perguntas frequentes (FAQs) sobre a movimentação de dados principais para uma nova Geografia do Office 365 datacenter.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 77d30778ae11865e5d773be4fa64db9b64480e76
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687291"
---
# <a name="data-move-general-faq"></a>Perguntas frequentes gerais sobre migração de dados

Veja a seguir respostas para perguntas gerais sobre a movimentação de dados principais para uma nova Geografia de datacenter.
  
## <a name="what-customers-are-eligible-to-request-a-move"></a>Quais clientes estão qualificados para solicitar uma mudança?
  
Os clientes comerciais da Microsoft 365 existentes que selecionaram um país qualificado para a nova Geografia do datacenter poderão solicitar uma movimentação.  O programa existe somente para locatários com um código de país qualificado atribuído ao locatário do Microsoft 365 para migrar os dados principais do cliente em repouso para cargas de trabalho qualificadas para a geografia do datacenter do Microsoft 365 correspondente.  Confira a página [como solicitar sua movimentação de dados](request-your-data-move.md) para confirmar a elegibilidade do país.   

## <a name="how-do-we-define-core-customer-data"></a>Como definir os dados principais do cliente?
 
Principais dados do cliente é um termo que se refere a um subconjunto de dados do cliente definido nos [termos do Microsoft Online Services](https://aka.ms/ost): 
- Conteúdo de caixa de correio do Exchange Online (corpo de email, entradas de calendário e conteúdo de anexos de email)
- Conteúdo do site do SharePoint Online e os arquivos armazenados nesse site
- Arquivos carregados no OneDrive for Business 

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a>Em que ponto a minha migração foi concluída para que os dados principais do cliente do meu locatário estejam armazenados em repouso em minha nova Geografia?

Devido às dependências compartilhadas entre o Exchange Online e o SharePoint Online/OneDrive for Business, qualquer migração não poderá ser considerada concluída até que os dois serviços sejam migrados.  O Exchange Online e o SharePoint Online/OneDrive for Business costumam migrar em horários separados e independentemente uns dos outros.  Os administradores de locatários recebem a confirmação no centro de mensagens quando cada migração de serviço é concluída e podem exibir o cartão de local de dados no centro de administração a qualquer momento para confirmar os dados principais do cliente no local restante de cada serviço.

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a>Como certificar-se de que os dados do cliente estão seguros durante a movimentação e que eu não experimentaria tempo de inatividade?
  
Movimentação de dados é uma operação de serviço de back-end com impacto mínimo para os usuários finais. Os recursos que podem ser afetados são listados [durante e após a movimentação dos dados](during-and-after-your-data-move.md). Respeitamos o contrato de [nível de serviço (SLA) dos serviços online da Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=523897) para disponibilidade, portanto, não há nada que os clientes precisem preparar ou monitorar durante a movimentação. 
  
Todos os serviços da Microsoft 365 executam as mesmas versões nos datacenters, para que você possa ter a funcionalidade consistente. Seu serviço é totalmente suportado durante todo o processo.

## <a name="what-is-in-scope-for-teams-migration"></a>Qual é o escopo da migração do teams?

Além do Exchange Online, do SharePoint Online e do OneDrive for Business; A Microsoft migrará os dados do teams para o datacenter local.  
- Mensagens de chat de equipes, incluindo mensagens privadas e mensagens de canal. 
- Imagens de equipes usadas em chats. 

Os arquivos do teams são armazenados no SharePoint Online e os arquivos de chat do Microsoft Teams são armazenados no OneDrive for Business.  Correio de voz, calendário, histórico de chat e contatos são armazenados no Exchange Online.  Em muitos casos, o Exchange Online, o SharePoint Online e o OneDrive for Business já são usados pelo cliente na geografia do datacenter local e também fazem parte do programa de migração do Microsoft 365 para países qualificados do cliente.
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a>Qual é o impacto de ter diferentes serviços localizados em diferentes GEOS?

Alguns dos serviços do Microsoft 365 podem estar localizados em diferentes GEOS para alguns clientes existentes e para clientes que estão no meio do processo de movimentação. Nossos serviços são executados independentemente uns dos outros e não há impacto na experiência do usuário se esse for o caso.No entanto, para fins de residência de dados, uma migração de locatário não pode ser considerada concluída até que o Exchange Online e o SharePoint Online/OneDrive for Business sejam migrados para a mesma Geografia do datacenter.
  
## <a name="will-new-microsoft-365-customers-be-automatically-provisioned-in-the-new-datacenter-geos"></a>Novos clientes do Microsoft 365 serão automaticamente provisionados no novo GEOS de datacenter?
  
Sim. Depois que uma nova Geografia do datacenter estiver disponível, os novos clientes do Microsoft 365 que selecionam um país qualificado para a nova geografia como o país durante a inscrição terão seus dados principais do cliente armazenados em repouso na nova Geografia do datacenter.
  
 ## <a name="where-is-my-core-customer-data-located"></a>Onde estão localizados os dados principais do cliente?

Os administradores de locatários podem exibir o cartão de local de dados no centro de administração a qualquer momento para confirmar os dados principais do cliente no local restante de cada serviço, especificamente para o locatário.Também publicamos o local do datacenter GEOS, datacenters e local dos dados do cliente do Office 365 nos [mapas de datacenters do office 365 Interactive ](https://office.com/datamaps) como uma referência para os dados de cliente principais padrão atuais em locais REST para novos locatários.  Você pode verificar o local dos dados do cliente em repouso por meio da seção local de dados em seu perfil de organização no centro de administração do Microsoft 365.  
 
## <a name="when-will-i-be-able-to-request-a-move"></a>Quando poderei solicitar uma movimentação?
  
Confira a página [como solicitar sua movimentação de dados](request-your-data-move.md) para obter os prazos suportados para sua geografia do datacenter.
  
## <a name="how-can-i-request-to-be-moved"></a>Como posso solicitar que eu possa ser movido?
  
Os clientes qualificados verão uma página em seu [centro de administração do Microsoft 365](https://admin.microsoft.com/). Confira [como solicitar a movimentação de dados](request-your-data-move.md) para obter instruções sobre como solicitar uma movimentação. 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a>Posso alterar minha seleção depois de solicitar uma movimentação?
  
Não é possível removê-lo do processo depois de enviar sua solicitação.
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a>O que acontece se eu não solicitar uma movimentação antes do prazo?
  
Podemos aceitar solicitações em uma base de exceção para conceder ao locatário um prazo de confirmação para concluir a movimentação.  Entre em contato com o [suporte da Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkID=522459) para fazer a solicitação.

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a>E se eu quiser mover meus dados para obter melhor desempenho da rede?
  
A proximidade física para um datacenter da Microsoft 365 não é uma garantia para um melhor desempenho de rede. Há vários fatores e componentes que afetam o desempenho da rede entre o usuário final e o serviço do Microsoft 365. Para obter mais informações sobre esse e ajuste de desempenho, consulte [planejamento de rede e ajuste de desempenho para o Microsoft 365](network-planning-and-performance.md).
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a>Todos os serviços transferem os dados no mesmo dia?
 
Cada serviço é movido de forma independente e provavelmente moverá seus dados em momentos diferentes.
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a>Posso escolher quando desejo mover meus dados?
 
Os clientes não podem selecionar uma data específica, eles não podem atrasar a movimentação, e não é possível compartilhar uma data ou um intervalo de tempo específico para as movimentações.
  
 ## <a name="can-you-share-when-my-data-will-be-be-moved"></a>Você pode compartilhar quando meus dados serão movidos?
  
Movimentação de dados é uma operação de back-end com impacto mínimo para os usuários finais. A complexidade, a precisão e a escala em que precisamos realizar movimentações de dados dentro de um ambiente operado globalmente e automatizado proíbem o compartilhamento quando uma movimentação de dados é esperada para concluir o locatário ou qualquer outro locatário único. Os clientes receberão uma confirmação no centro de mensagens por serviço participante quando sua movimentação de dados tiver sido concluída. 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a>O que acontece quando os usuários acessam os serviços enquanto os dados estão sendo movidos?

Consulte [durante e após a movimentação de dados](during-and-after-your-data-move.md) para obter uma lista completa dos recursos que podem ser limitados durante partes da movimentação de dados para cada serviço. 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a>Como saber se a movimentação está concluída?
  
Assista ao centro de mensagens do Microsoft 365 para confirmar que a mudança dos dados de cada serviço está concluída. Quando os dados de cada serviço são movidos, publicaremos um aviso de conclusão para que você receba três avisos de conclusão: um para o Exchange Online, o SharePoint Online e o Skype for Business online.  Você também pode verificar o local dos dados do cliente em repouso por meio da seção local de dados em seu perfil de organização no centro de administração do Microsoft 365.  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a>Sou um cliente da Microsoft 365 em um dos novos GEOS de datacenter, mas quando eu me conectei, selecionei outro país. Como posso ser movido para a nova Geografia do datacenter?

Não é possível alterar o país de inscrição associado ao seu locatário. Em vez disso, você precisa criar um novo locatário do Microsoft 365 com uma nova assinatura e mover manualmente seus usuários e dados para o novo locatário.
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a>O que acontece se estivermos em processo de migração de dados de email para o Microsoft 365 durante a movimentação do Exchange Online?

Este é um cenário muito comum e é totalmente compatível.  A migração em nuvem entre o GEOS do datacenter não interfere em todas as migrações de caixa de correio do premisis para nuvem.
  
 ## <a name="can-i-pilot-some-users"></a>Posso fazer um piloto de alguns usuários?
  
Você pode criar um locatário de avaliação separado para testar a conectividade, mas o locatário de avaliação não pode ser combinado de qualquer forma com seu locatário existente.

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a>Não desejo esperar que a Microsoft mova meus dados. Posso apenas criar um novo locatário e movê-lo?
  
Sim, no entanto, o processo não será tão direto quanto se a Microsoft fosse realizar a movimentação de dados.
  
Se você criar um novo locatário após a disponibilidade da nova Geografia do datacenter, o novo locatário será hospedado na nova geografia. Este novo locatário é completamente separado do seu locatário anterior e você é responsável por mover todas as caixas de correio do usuário, conteúdo do site, nomes de domínio e outros dados. Observe que não é possível mover o nome do locatário de um locatário para outro. Recomendamos que você aguarde o programa de movimentação fornecido pela Microsoft à medida que cuidaremos da movimentação de todas as configurações, dados e assinaturas de seus usuários.
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a>Meus dados do cliente já foram movidos para uma nova Geografia do datacenter. Posso mudar de volta?
 
Não, isso não é possível. Os clientes que foram movidos para novos datacenters geográficos não podem ser movidos de volta. Como cliente em qualquer geografia, você terá os mesmos controles de qualidade de serviço, desempenho e segurança que fazia antes.  [O Microsoft 365 multigeográfico](https://aka.ms/multi-geo) está disponível para alguns clientes como um complemento e permite que um único locatário crie vários GEOS de satélite e mova os dados do usuário para esses GEOS com compromissos de residência de dados.
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a>Os locatários da Microsoft 365 hospedados nos novos datacenters estarão disponíveis para usuários fora do país?
  
Sim. A Microsoft mantém uma grande rede global com conexões de Internet pública em mais de 130 locais em 35 países em todo o mundo com contratos de emparelhamento com mais de 2.700 provedores de serviços de Internet (ISPs). Os usuários poderão acessar os datacenters a partir de onde estiverem na Internet.

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a>Meu locatário configurou o [complemento multigeográfico](https://aka.ms/multi-geo). Ainda posso se inscrever no meu locatário no programa Microsoft 365 move para alterar minha geografia padrão e mover qualquer usuário que não esteja em uma região de satélite para a nova geografia padrão?

Sim, seu locatário está qualificado para se inscrever. Moveremos todas as caixas de correio do EXO da sua geografia padrão atual para sua nova geografia local de datacenter.  Não moveremos nenhuma caixa de correio do EXO configurada em várias regiões de satélite geográficos para continuar a respeitar a residência de dados da região satélite, conforme você pretendia.  

O SharePoint Online e o OneDrive for Business não podem migrar para a nova Geografia do datacenter como parte do programa mover, embora você possa configurar os compartilhamentos do OneDrive for Business para mudar para qualquer região que desejar via programa multigeográfico.

## <a name="related-topics"></a>Tópicos relacionados

[Movendo dados principais para o novo Microsoft 365 datacenter GEOS](moving-data-to-new-datacenter-geos.md)

[Como solicitar a migração dos dados](request-your-data-move.md)

[Microsoft 365 multigeográfico](https://aka.ms/multi-geo)

[Mapa de datacenter interativo Microsoft 365](https://office.com/datamaps)

[Suporte do Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkID=522459)

[Nova GEOS de datacenter do Microsoft Dynamics CRM Online](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Serviços do Azure por região](https://azure.microsoft.com/regions/)
