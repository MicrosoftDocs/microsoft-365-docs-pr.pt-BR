---
title: Durante e após a migração dos dados
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.collection: SPO_Content
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: f47e3e09-b1dc-4b80-b6ea-fd6e0933407f
f1.keywords:
- NOCSH
description: As movimentações de dados são operações de back-end que ocorrem quando a Microsoft move serviços e dados associados para seu locatário para um novo datacenter geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d3d44ffc1650989e5c39f5f79cb6a07065f9e9f1
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625252"
---
# <a name="during-and-after-your-data-move"></a>Durante e após a migração dos dados

As movimentações de dados são uma operação de back-end com impacto mínimo para os usuários finais. Nenhuma ação é necessária enquanto a Microsoft move cada serviço e dados associados para seu locatário para um novo datacenter geo. A transferência e validação de dados ocorrem em segundo plano antecipadamente, com impacto mínimo para os usuários.
  
> [!NOTE]
> As movimentações ocorrem em horários diferentes para cada serviço. Como resultado, você verá a funcionalidade reduzida descrita para cada serviço em um momento diferente. 
  
Assista ao Microsoft 365 de Mensagens para confirmação quando as movimentações para cada um dos Exchange Online, SharePoint Online e Teams de chat concluídas. Conforme mostrado na tabela abaixo, pode levar até 24 meses após o final do período de registro para concluir os dados principais do cliente em repouso move-se para o novo datacenter geo.   

|**Clientes com país de assinatura no**|**Todas as movimentações concluídas por**|
|:-----|:-----|
|Austrália, Nova Zelândia, Fiji  <br/> |1º de julho de 2022  <br/> |
|Japão  <br/> |1º de julho de 2022  <br/> |
|Índia  <br/> |1º de julho de 2022  <br/> |
|Canadá  <br/> |1º de julho de 2022  <br/> |
|Coreia do Sul  <br/> |1º de julho de 2022  <br/> |
|Reino Unido  <br/> |1º de julho de 2022  <br/> |
|França  <br/> |1º de julho de 2022  <br/> |
|Emirados Árabes Unidos  <br/> |1º de julho de 2022  <br/> |
|África do Sul  <br/> |1º de julho de 2022  <br/> |
|Suíça, Liechtenstein  <br/> |1º de julho de 2022  <br/> |
|Noruega  <br/> |1º de novembro de 2022  <br/> |
|Alemanha  <br/> |1º de maio de 2023  <br/> |
|Brasil  <br/> |1º de junho de 2023  <br/> |

## <a name="exchange-online"></a>Exchange Online

Como leva tempo para mover cada usuário para o novo datacenter geo para um único locatário, alguns usuários ainda estarão no antigo datacenter geo durante a movimentação, enquanto outros estarão no novo datacenter geo. Isso significa que alguns recursos que envolvem o acesso a várias caixas de correio podem não funcionar totalmente durante um período do processo de movimentação, que pode durar semanas. Esses recursos são descritos nas seções a seguir.
  
### <a name="open-shared-folder-in-outlook-web-access"></a>Abra "Pasta Compartilhada" no Outlook Web Access

Alguns usuários abrem uma pasta de email compartilhada de outra caixa de correio (para a onde o usuário tem permissões de leitura ou gravação) no Outlook Web Access usando o recurso "Pasta Compartilhada". A tabela a seguir descreve como o acesso a pastas compartilhadas funciona durante uma movimentação de caixa de correio. Observe que os usuários com permissões completas para uma caixa de correio compartilhada podem abrir a caixa de correio usando Outlook Web Access durante a movimentação. 
  
|**Configuração**|**Descrição**|
|:-----|:-----|
|O usuário tem permissão de pasta de caixa de correio para outra caixa de correio  <br/> |Potencialmente limitado.  <br/> Se o Usuário A e a Caixa de Correio B não estão na mesma geo durante a movimentação do locatário, o Usuário A não poderá abrir a pasta da Caixa de Correio B no Outlook Web Access se o Usuário A tiver permissão apenas para uma pasta específica na Caixa de Correio B.  <br/> Para adicionar uma pasta compartilhada, clique com o botão direito do mouse no nome do usuário no painel de navegação esquerdo e selecione **Adicionar pasta compartilhada**.  <br/> |
|Usuário com permissão de caixa de correio completa para outra caixa de correio  <br/> |Totalmente suportado.  <br/> Se o Usuário A tiver permissão de "Acesso Total" para a Caixa de Correio B, o Usuário A poderá clicar na pasta compartilhada no painel de navegação esquerdo no Outlook Web Access para abrir uma janela mostrando a Caixa de Correio B.  Um usuário pode abrir uma caixa de correio compartilhada usando Outlook Web Access durante a movimentação sem qualquer impacto adverso. A limitação só se aplica ao compartilhamento no nível de pasta em uma caixa de correio.           |
  
## <a name="sharepoint-online"></a>SharePoint Online

Quando SharePoint Online é movido, os dados dos seguintes serviços também são movidos:
  
- One Drive for Business
    
- Microsoft 365 Serviços de vídeo
    
- Office em um navegador
    
- Microsoft 365 Apps para empresas
    
- Visio Pro para Microsoft 365
    
Após concluirmos a movimentação dos dados SharePoint online, você poderá ver alguns dos seguintes efeitos.
  
### <a name="microsoft-365-video-services"></a>Microsoft 365 Serviços de vídeo

- A movimentação de dados para vídeo leva mais tempo do que as movimentações para o restante do conteúdo no SharePoint Online.
    
- Depois que o SharePoint online for movido, haverá um período em que os vídeos não poderão ser tocados.
    
- Estamos removendo as cópias em código trans do datacenter anterior e transcodificando-as novamente no novo datacenter.
    
### <a name="search"></a>Pesquisar

Ao mover seus dados SharePoint Online, migramos seu índice de pesquisa e configurações de pesquisa para um novo local. Até concluirmos a **movimentação** de seus dados SharePoint Online, continuaremos a atender seus usuários do índice no local original. No novo local, a pesquisa começa automaticamente a rastrear seu conteúdo após concluirmos a movimentação dos dados SharePoint Online. A partir deste ponto e em diante, atendemos seus usuários do índice migrado. As alterações no conteúdo que ocorreram após a migração não são incluídas no índice migrado até que o rastreamento os escolha. A maioria dos clientes não percebe que os resultados são menos recentes logo após concluirmos a movimentação dos dados do SharePoint Online, mas alguns clientes podem ter uma redução de frescor nas primeiras 24 a 48 horas 
  
Os seguintes recursos de pesquisa são afetados:
  
- Resultados da pesquisa e Web Parts pesquisa: os resultados não incluem alterações que ocorreram após a migração até que o rastreamento as escolha. 
    
- Delve: Delve não inclui alterações que ocorreram após a migração até que o rastreamento as escolha.
    
- Relatórios de popularidade e pesquisa para o site: contagens para relatórios de Excel no novo local incluem apenas contagens migradas e contagens de relatórios de uso executados após concluirmos a movimentação de seus dados SharePoint Online. Todas as contagens do período provisório são perdidas e não podem ser recuperadas. Esse período geralmente é de alguns dias. Alguns clientes podem ter perdas mais curtas ou mais longas.
    
- Portal de Vídeo: As contagens e estatísticas de exibição para o Portal de Vídeo dependem das estatísticas para relatórios Excel, portanto, as contagens de exibição e estatísticas do Portal de Vídeo são perdidas para o mesmo período de tempo que para os relatórios Excel de exibição.
    
- Descoberta e: os itens que foram alterados durante a migração não são mostrados até que o rastreamento atenda às alterações.
    
- Proteção contra Perda de Dados (DLP): as políticas não são impostas em itens que mudam até que o rastreamento atenda às alterações.

Como parte da migração, a região padrão será mudada e todo o novo conteúdo será armazenado em repouso na nova região padrão. O conteúdo existente será movimentado em segundo plano sem impacto para você por até 90 dias após a primeira alteração no local de dados do SharePoint Online no centro de administração.

## <a name="microsoft-teams"></a>Microsoft Teams

Além de Exchange Online, SharePoint Online e OneDrive for Business, a Microsoft migrará Teams dados do serviço de chat para o datacenter local.

- Teams mensagens de chat, incluindo mensagens privadas e mensagens de canal.
- Teams imagens usadas em chats.

Teams arquivos são armazenados no SharePoint Online e Teams de chat são armazenados em OneDrive for Business. Caixa postal, calendário, histórico de chat e contatos são armazenados Exchange Online. Em muitos casos, Exchange Online, SharePoint Online e OneDrive for Business já são usados pelo cliente no datacenter local geo e também fazem parte do programa de migração Microsoft 365 para países clientes qualificados.

## <a name="skype-for-business"></a>Skype for Business

Skype for Business movimentações não estão mais disponíveis.  [Skype for Business Online será retirada em](/lifecycle/announcements/skype-for-business-online-retirement) 31 de julho de 2021. Após esse tempo, o serviço não estará mais acessível. 
  
## <a name="related-topics"></a>Tópicos relacionados 
 
[Como solicitar a migração dos dados](request-your-data-move.md)
    
[Perguntas frequentes gerais sobre migração de dados](data-move-faq.md)
  
[Novos geos do datacenter para Microsoft Dynamics CRM Online](/power-platform/admin/new-datacenter-regions)
  
[Serviços do Azure por região](https://azure.microsoft.com/regions/)
