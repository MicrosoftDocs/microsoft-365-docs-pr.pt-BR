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
description: Movimentações de dados são operações de back-end que ocorrem quando a Microsoft transfere serviços e dados associados para seu locatário para uma nova Geografia de datacenter.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: acd2601d32617c56019ca8b4bf8688ce40f5d76a
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950267"
---
# <a name="during-and-after-your-data-move"></a>Durante e após a migração dos dados

Movimentação de dados é uma operação de back-end com impacto mínimo para os usuários finais. Nenhuma ação é necessária enquanto a Microsoft transfere cada serviço e dados associados para seu locatário para uma nova Geografia de datacenter. A transferência e a validação de dados ocorrem em segundo plano com o mínimo de impacto para os usuários.
  
> [!NOTE]
> As movimentações ocorrem em horários diferentes de cada serviço. Como resultado, você verá a funcionalidade reduzida descrita para cada serviço em um momento diferente. 
  
Assista ao centro de mensagens do Microsoft 365 para confirmação quando se move para cada um dos Exchange Online, SharePoint Online, Teams e Skype for Business concluído. Conforme mostrado na tabela abaixo, pode levar até 24 meses, após o final do período de registro, para concluir todos os dados solicitados são movidos para todos os clientes em uma geografia específica. Se você vir problemas com o seu locatário após a movimentação, entre em contato com o [suporte](https://go.microsoft.com/fwlink/p/?LinkID=522459) para obter assistência. 
  

|**Clientes com país de inscrição no**|**Todas as movimentações concluídas por**|
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
|Noruega  <br/> |1 de novembro de 2022  <br/> |
|Alemanha  <br/> |Liga  <br/> |

## <a name="exchange-online"></a>Exchange Online

Como leva tempo para mover cada usuário para a nova Geografia do datacenter para um único locatário, alguns usuários ainda estarão na região antiga do datacenter durante a movimentação, enquanto outros estarão na nova Geografia do datacenter. Isso significa que alguns recursos que envolvem o acesso a várias caixas de correio podem não funcionar totalmente durante um período do processo de movimentação, que pode durar semanas. Esses recursos são descritos nas seções a seguir.
  
### <a name="open-shared-folder-in-outlook-web-access"></a>Abrir "pasta compartilhada" no Outlook Web Access

Alguns usuários abrem uma pasta de email compartilhada de outra caixa de correio (que o usuário tem permissões de leitura ou gravação no Outlook Web Access usando o recurso "pasta compartilhada". A tabela a seguir descreve como o acesso a pastas compartilhadas funciona durante uma movimentação de caixa de correio. Observe que os usuários com permissões completas para uma caixa de correio compartilhada podem abrir a caixa de correio usando o Outlook Web Access durante a movimentação. 
  
|**Configuração**|**Descrição**|
|:-----|:-----|
|O usuário tem permissão de pasta de caixa de correio para outra caixa de correio  <br/> |Potencialmente limitado.  <br/> Se o usuário A e A caixa de correio B não estiverem na mesma Geografia durante a movimentação do locatário, o usuário A não poderá abrir a pasta da caixa de correio B no Outlook Web Access se o usuário apenas tiver permissão para uma pasta específica na caixa de correio B.  <br/> Para adicionar uma pasta compartilhada, clique com o botão direito do mouse no nome do usuário no painel de navegação esquerdo e selecione **Adicionar pasta compartilhada**.  <br/> |
|Usuário com permissão de caixa de correio completa para outra caixa de correio  <br/> |Totalmente suportado.  <br/> Se o usuário A tem permissão de "acesso total" para a caixa de correio B, o usuário A pode clicar na pasta compartilhada no painel de navegação à esquerda no Outlook Web Access para abrir uma janela mostrando a caixa de correio B.  Um usuário pode abrir uma caixa de correio compartilhada usando o Outlook Web Access durante a movimentação sem qualquer impacto adverso. A limitação só se aplica ao compartilhamento no nível de pasta em uma caixa de correio.           |
  
## <a name="sharepoint-online"></a>SharePoint Online

Quando o SharePoint Online é movido, os dados dos seguintes serviços também são movidos:
  
- One Drive for Business
    
- Project Online
    
- Project para o Microsoft 365
    
- Serviços de vídeo Microsoft 365
    
- Office no navegador s
    
- Microsoft 365 Apps para empresas
    
- Visio pro para Microsoft 365
    
Depois de concluir a movimentação de seus dados do SharePoint Online, você poderá ver alguns dos seguintes efeitos.
  
### <a name="microsoft-365-video-services"></a>Serviços de vídeo Microsoft 365

- O movimento de dados para o vídeo demora mais do que as movimentações para o restante do conteúdo no SharePoint Online.
    
- Depois que o conteúdo do SharePoint Online for movido, haverá um período em que os vídeos não poderão ser executados.
    
- Estamos removendo as cópias de trans-codificadas do datacenter anterior e as transcodificando novamente no novo datacenter.
    
### <a name="search"></a>Pesquisa

Durante a transferência dos dados do SharePoint Online, migramos o índice de pesquisa e as configurações de pesquisa para um novo local. Até que tenhamos **concluído** a movimentação de seus dados do SharePoint Online, continuamos a atender seus usuários do índice no local original. No novo local, a pesquisa inicia automaticamente o rastreamento do conteúdo após a conclusão da movimentação de seus dados do SharePoint Online. A partir deste ponto e em diante, atendemos aos seus usuários a partir do índice migrado. Alterações no conteúdo que ocorreram após a migração não estão incluídas no índice migrado até que o rastreamento as escolha. A maioria dos clientes não percebe que os resultados estão menos atualizados logo após a conclusão da movimentação de seus dados do SharePoint Online, mas alguns clientes podem ter uma atualização reduzida nas primeiras 24-48 horas 
  
Os seguintes recursos de pesquisa são afetados:
  
- Resultados de pesquisa e Web Parts de pesquisa: os resultados não incluem alterações que ocorreram após a migração até que o rastreamento as escolha. 
    
- Delve: o Delve não inclui alterações que ocorreram após a migração até que o rastreamento as escolha.
    
- Relatórios de popularidade e pesquisa para o site: contagens para relatórios do Excel no novo local incluem apenas contagens migradas e contagens dos relatórios de uso que foram executados após a conclusão da movimentação de seus dados do SharePoint Online. Qualquer conta do período provisório é perdida e não pode ser recuperada. Esse período normalmente é de alguns dias. Alguns clientes podem experimentar perdas mais curtas ou mais longas.
    
- Portal de vídeos: Exibir contagens e estatísticas para o portal de vídeo dependem das estatísticas dos relatórios do Excel, portanto, as contagens e as estatísticas do portal de vídeo são perdidas pelo mesmo período de tempo para os relatórios do Excel.
    
- Descoberta eletrônica: os itens que foram alterados durante a migração não são mostrados até que o rastreamento escolha as alterações.
    
- Proteção contra perda de dados (DLP): as políticas não são impostas em itens que são alterados até que o rastreamento escolha as alterações.

## <a name="microsoft-teams"></a>Microsoft Teams

Além do Exchange Online, do SharePoint Online e do OneDrive for Business, a Microsoft migrará os dados do teams para o datacenter local.

- Mensagens de chat de equipes, incluindo mensagens privadas e mensagens de canal.
- Imagens de equipes usadas em chats.

Os arquivos do teams são armazenados no SharePoint Online e os arquivos de chat do Microsoft Teams são armazenados no OneDrive for Business. Correio de voz, calendário, histórico de chat e contatos são armazenados no Exchange Online. Em muitos casos, o Exchange Online, o SharePoint Online e o OneDrive for Business já são usados pelo cliente na geografia do datacenter local e também fazem parte do programa de migração do Microsoft 365 para países qualificados do cliente.

## <a name="skype-for-business"></a>Skype for Business

As movimentações do Skype for Business estão disponíveis para a Austrália, Japão, Índia, Canadá, Reino Unido e Coréia do Sul.

Todos os usuários serão desconectados do software cliente Skype for Business durante o recorte. A entrada automática reconectará os usuários dentro de dois minutos.
  
|**Recursos que funcionam durante uma movimentação inteira**|**Recursos que podem ser limitados durante uma parte da movimentação**|
|:-----|:-----|
| Mensagens instantâneas e chamadas de voz  <br/>  Os usuários podem adicionar contatos, adicionar grupos de contatos, adicionar reuniões, definir seu local e alterar "o que está acontecendo hoje".  <br/>  As configurações de ACP (provedor de serviços de audioconferência) são copiadas para a geografia do datacenter de destino. Se o provedor ACP estiver presente no datacenter de destino, ele funcionará. Caso contrário, ele não será.  <br/> | Os TRPS de administração de locatários (PowerShell remoto do locatário) não estarão disponíveis para que os administradores criem sessões.  <br/>  O administrador de locatários LAC não estará disponível para que os administradores entrem e alterem as configurações do usuário.  <br/> |
   
|**Após a movimentação**|
|:-----|
| Os dados da reunião (apresentações carregadas, etc.) não serão movidos e precisarão ser carregados novamente.  <br/>  Os clientes Lync mais antigos, como o cliente Lync 2010 e o Lync para Mac 2011, são conhecidos por armazenar em cache as informações de DNS para o serviço que causa problemas de entrada. Limpar o cache DNS pode ser necessário se o usuário não estiver no cliente mais recente do Windows Skype for Business. Consulte [Solucionando problemas de configuração de DNS do Skype for Business online no Office 365](https://docs.microsoft.com/skypeforbusiness/troubleshoot/online-configuration/dns-configuration-issue). Os usuários do cliente do Lync para Mac devem seguir [estas instruções](https://support.microsoft.com/kb/2629861).  <br/> |
   
### <a name="skype-for-business-moves-that-involve-a-third-party-audio-conferencing-provider"></a>O Skype for Business se move que envolve um provedor de audioconferência de terceiros
Serviços complementares de provedor de conferência de áudio de terceiros para o Skype for Business não estão disponíveis para usuários hospedados em novos data centers específicos geográficos.  Os clientes existentes que usam um serviço de provedor de audioconferência de terceiros não devem solicitar uma movimentação para um novo data center específico em geografia.  Novos clientes implantados nos novos data centers específicos de Geografia precisarão solicitar uma mudança para um centro de dados regional para usar um provedor de audioconferência de terceiros.
  
## <a name="related-topics"></a>Tópicos relacionados 
 
[Como solicitar a migração dos dados](request-your-data-move.md)
    
[Perguntas frequentes gerais sobre migração de dados](data-move-faq.md)
  
[Nova GEOS de datacenter do Microsoft Dynamics CRM Online](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Serviços do Azure por região](https://azure.microsoft.com/regions/)
