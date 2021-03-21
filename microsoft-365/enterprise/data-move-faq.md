---
title: Perguntas frequentes gerais sobre migração de dados
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 1f01bc6f-5d37-4d14-bdd3-9d94a1e23e14
f1.keywords:
- NOCSH
description: Encontre respostas para perguntas frequentes (perguntas frequentes) sobre como mover dados principais para um novo datacenter do Office 365 geo.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e66c9f29b47c3f1bc8d6e89ebf2f077eee9f4adf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919123"
---
# <a name="data-move-general-faq"></a>Perguntas frequentes gerais sobre migração de dados

Aqui estão respostas para perguntas gerais sobre como mover os dados principais do cliente em repouso para um novo datacenter geo.
  
## <a name="what-customers-are-eligible-to-request-a-move"></a>Quais clientes estão qualificados para solicitar uma movimentação?
  
Os clientes comerciais existentes do Microsoft 365 que selecionaram um país qualificado para o novo datacenter geo poderão solicitar uma movimentação. O programa existe apenas para locatários com um código de país qualificado atribuído ao locatário do Microsoft 365 para migrar os dados principais do cliente em repouso para cargas de trabalho qualificadas para o datacenter do Microsoft 365 geo correspondente. Consulte a página [Como solicitar a movimentação](request-your-data-move.md) de dados para confirmar a qualificação do país.   

## <a name="how-do-we-define-core-customer-data"></a>Como definimos Os Dados Principais do Cliente?
 
Os dados principais do cliente são um termo que se refere a um subconjunto de dados do cliente definidos no Microsoft Online Services [Termos](https://aka.ms/ost): 
- Conteúdo da caixa de correio do Exchange Online (corpo do email, entradas de calendário e o conteúdo de anexos de email)
- Conteúdo do site do SharePoint Online e os arquivos armazenados nesse site
- Arquivos carregados no OneDrive for Business 

## <a name="what-is-in-scope-for-teams-migration"></a>O que há no escopo da migração do Teams?

Além do Exchange Online, do SharePoint Online e do OneDrive for Business; A Microsoft migrará dados do Teams para o datacenter local. 
- Mensagens de chat do Teams, incluindo mensagens privadas e mensagens de canal. 
- Imagens do Teams usadas em chats. 

Os arquivos do Teams são armazenados no SharePoint Online e os arquivos de chat do Teams são armazenados no OneDrive for Business. Caixa postal, calendário e contatos são armazenados no Exchange Online. Em muitos casos, o Exchange Online, o SharePoint Online e o OneDrive for Business já são usados pelo cliente no datacenter local geo e também fazem parte do programa de migração do Microsoft 365 para países clientes qualificados.

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a>Em que ponto minha migração está concluída para que os principais dados do cliente do meu locatário estão sendo armazenados em repouso no meu novo geo?

Devido às dependências compartilhadas entre o Exchange Online e o SharePoint Online/OneDrive for Business, qualquer migração não pode ser considerada concluída até que ambos os serviços sejam migrados. O Exchange Online e o SharePoint Online/OneDrive for Business geralmente migram em horários separados e independentemente um do outro. Os administradores de locatários de clientes recebem confirmação no Centro de Mensagens quando cada migração de serviço é concluída e podem exibir o cartão de localização de dados no Centro de Administração a qualquer momento para confirmar os dados principais do cliente no local de repouso para cada serviço.

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a>Como certificar-se de que meus dados do cliente estão seguros durante a movimentação e se eu não experimentarei o tempo de inatividade?
  
As movimentações de dados são uma operação de serviço de back-end com impacto mínimo para os usuários finais. Os recursos que podem ser afetados são listados em [Durante e após a movimentação de dados.](during-and-after-your-data-move.md) Aderimos Microsoft Online Services Contrato de Nível de Serviço [(SLA)](https://go.microsoft.com/fwlink/p/?LinkId=523897) para disponibilidade, portanto, não há nada que os clientes precisem preparar ou monitorar durante a movimentação. 
  
Todos os serviços do Microsoft 365 são executados nas mesmas versões nos datacenters, para que você possa ter certeza de funcionalidade consistente. Seu serviço tem suporte total em todo o processo.
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a>Qual é o impacto de ter diferentes serviços localizados em diferentes geos?

Alguns dos serviços do Microsoft 365 podem estar localizados em diferentes geos para alguns clientes existentes e para clientes que estão no meio do processo de movimentação. Nossos serviços são executados independentemente um do outro e não há impacto na experiência do usuário, se esse for o caso. No entanto, para fins de residência de dados, uma migração de locatário não pode ser considerada como concluída até que o Exchange Online e o SharePoint Online/OneDrive for Business sejam migrados para o mesmo datacenter geo.

 ## <a name="where-is-my-core-customer-data-located"></a>Onde estão localizados meus principais dados do cliente?

Os administradores de locatários do cliente podem exibir o cartão de localização de dados no Centro de Administração a qualquer momento para confirmar os principais dados do cliente no local de repouso para cada serviço, especificamente para seu locatário.  Também publicamos o local dos geos do datacenter, datacenters e localização dos dados do cliente do Office 365 nos mapas interativos do datacenter do [Microsoft 365 ](https://office.com/datamaps) como referência para os dados principais do cliente padrão atual em locais de repouso para novos locatários. Você pode verificar a localização dos dados do cliente em repouso por meio da seção Localização de Dados em seu Perfil da Organização no Centro de administração do Microsoft 365.  
 
## <a name="when-will-i-be-able-to-request-a-move"></a>Quando posso solicitar uma movimentação?
  
Consulte a página [Como solicitar a movimentação](request-your-data-move.md) de dados para os períodos de tempo suportados para o seu datacenter geo.
  
## <a name="how-can-i-request-to-be-moved"></a>Como posso solicitar a movimentação?
  
Os clientes qualificados verão uma página no centro de administração [do Microsoft 365.](https://admin.microsoft.com/) Confira [Como solicitar a movimentação de dados](request-your-data-move.md) para obter instruções sobre como solicitar uma movimentação. 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a>Posso alterar minha seleção depois de solicitar uma movimentação?
  
Não é possível removê-lo do processo depois de enviar sua solicitação.
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a>O que acontece se eu não solicitar uma movimentação antes do prazo final?
  
Não é possível aceitar solicitações de migração após o período de registro aberto.

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a>E se eu quiser mover meus dados para obter um melhor desempenho de rede?
  
A proximidade física com um datacenter do Microsoft 365 não é uma garantia para um melhor desempenho de rede. Há muitos fatores e componentes que afetam o desempenho da rede entre o usuário final e o serviço do Microsoft 365. Para obter mais informações sobre isso e ajuste de desempenho, consulte [Network planning and performance tuning for Microsoft 365](network-planning-and-performance.md).
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a>Todos os serviços movem seus dados no mesmo dia?
 
Cada serviço se move independentemente e provavelmente move seus dados em momentos diferentes.
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a>Posso escolher quando quero que meus dados sejam movidos?
 
Os clientes não podem selecionar uma data específica, não podem atrasar a movimentação e não podemos compartilhar uma data ou um período específico para as movimentações.
  
 ## <a name="can-you-share-when-my-data-will-be-moved"></a>Você pode compartilhar quando meus dados serão movidos?
  
As movimentações de dados são uma operação de back-end com impacto mínimo para os usuários finais. A complexidade, precisão e escala na qual precisamos executar movimentações de dados em um ambiente globalmente operado e automatizado nos proíbe de compartilhar quando uma movimentação de dados deve ser concluída para seu locatário ou qualquer outro locatário. Os clientes receberão uma confirmação no Centro de Mensagens por serviço participante quando a movimentação de dados for concluída. 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a>O que acontece se os usuários acessarem serviços enquanto os dados estão sendo movidos?

Consulte [Durante e após a movimentação de](during-and-after-your-data-move.md) dados para uma lista completa de recursos que podem ser limitados durante partes da movimentação de dados para cada serviço. 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a>Como saber se a movimentação foi concluída?
  
Assista ao Centro de Mensagens do Microsoft 365 para confirmar se a movimentação dos dados de cada serviço está concluída. Quando os dados de cada serviço são movidos, postaremos um aviso de conclusão para que você receba três avisos de conclusão: um para o Exchange Online, o SharePoint Online e o Skype for Business Online. Você também pode verificar a localização dos dados do cliente em repouso por meio da seção Localização de Dados em seu Perfil da Organização no Centro de administração do Microsoft 365.  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a>Sou um cliente do Microsoft 365 em uma das novas geos do datacenter, mas quando me inscreu, selecionei um país diferente. Como posso ser movido para o novo datacenter geo?

Não é possível alterar o país de assinatura associado ao seu locatário. Em vez disso, você precisa criar um novo locatário do Microsoft 365 com uma nova assinatura e mover manualmente seus usuários e dados para o novo locatário.
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a>O que acontece se estamos em processo de migração de dados de email para o Microsoft 365 durante a movimentação do Exchange Online?

Esse é um cenário muito comum e é totalmente suportado.  A migração de nuvem entre os geos do datacenter não interfere em nenhuma migração local para caixas de correio na nuvem.
  
 ## <a name="can-i-pilot-some-users"></a>Posso pilotar alguns usuários?
  
Você pode criar um locatário de avaliação separado para testar a conectividade, mas o locatário de avaliação não pode ser combinado de forma alguma com seu locatário existente.

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a>Não quero esperar que a Microsoft mova meus dados. Posso criar um novo locatário e me mover?
  
Sim, no entanto, o processo não será tão contínuo quanto se a Microsoft fosse executar a movimentação de dados.
  
Se você criar um novo locatário depois que o novo datacenter geo estiver disponível, o novo locatário será hospedado na nova geo. Esse novo locatário é completamente separado do seu locatário anterior e você seria responsável por mover todas as caixas de correio de usuário, conteúdo do site, nomes de domínio e quaisquer outros dados. Observe que você não pode mover o nome do locatário de um locatário para outro. Recomendamos que você aguarde o programa de movimentação fornecido pela Microsoft, pois cuidaremos de mover todas as configurações, dados e assinaturas para seus usuários.
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a>Meus dados do cliente já foram movidos para um novo datacenter geo. Posso voltar?
 
Não, isso não é possível. Os clientes que foram movidos para novos datacenters geo-geo não podem ser movidos de volta. Como cliente em qualquer geo, você experimentará a mesma qualidade de controles de serviço, desempenho e segurança que você tinha antes. [O Microsoft 365 Multi Geo](https://aka.ms/multi-geo) está disponível para alguns clientes como complemento e permite que um único locatário crie várias geos de satélite e mova os dados do usuário para essas geos com compromissos de residência de dados.
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a>Os locatários do Microsoft 365 hospedados nos novos datacenters estarão disponíveis para usuários fora do país?
  
Sim. A Microsoft mantém uma grande rede global com conexões públicas com a Internet em mais de 130 locais em 35 países ao redor do mundo com acordos de paridade com mais de 2.700 Provedores de Serviços da Internet (ISPs). Os usuários poderão acessar os datacenters de onde quer que estejam na Internet.

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a>Meu locatário configurou o [complemento Multi Geo](https://aka.ms/multi-geo). Ainda posso me inscrever no meu locatário no Programa de Movimentação do Microsoft 365 para alterar meu geo padrão e mover qualquer usuário que não esteja em uma região de satélite para o novo geo padrão?

Sim, seu locatário está qualificado para se inscrever, mas há considerações significativas, pois a movimentação no nível do locatário não é totalmente suportada para clientes que configuraram o Multi-Geo.

O SharePoint Online e o OneDrive for Business não podem migrar para o novo datacenter geo no nível do locatário por meio deste programa. O administrador do cliente pode configurar compartilhamentos do OneDrive for Business para mover para qualquer região disponível usando Multi-Geo, mas o local padrão para o locatário não pode ser alterado depois que o Multi-Geo tiver sido configurado para um locatário.

Para clientes que optam pela migração , moveremos todas as caixas de correio do Exchange Online do seu geo padrão atual para o novo datacenter local geo e atualizaremos a região padrão do Exchange Online. Não moveremos nenhuma caixa de correio EXO configurada em regiões de satélite Multi Geo para continuar a respeitar a residência de dados de região satélite conforme você pretendia. 

## <a name="related-topics"></a>Tópicos relacionados

[Mover dados principais para novos geos do datacenter do Microsoft 365](moving-data-to-new-datacenter-geos.md)

[Como solicitar a migração dos dados](request-your-data-move.md)

[Microsoft 365 Multi Geo](https://aka.ms/multi-geo)

[Mapa interativo do datacenter do Microsoft 365](https://office.com/datamaps)

[Suporte do Microsoft 365](../admin/contact-support-for-business-products.md)

[Novos geos do datacenter para Microsoft Dynamics CRM Online](/power-platform/admin/new-datacenter-regions)
  
[Serviços do Azure por região](https://azure.microsoft.com/regions/)