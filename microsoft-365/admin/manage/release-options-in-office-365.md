---
title: Configurar as opções de lançamento padrão ou direcionado
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Saiba como configurar a opção de lançamento para atualizações de novos produtos e recursos no Centro de administração do Microsoft 365.
ms.openlocfilehash: 99a2660af9d8756bf4faf1cf3eddfe142a7c87bf
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114484"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>Configurar as opções de lançamento padrão ou direcionado

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

> [!IMPORTANT]
> As atualizações do Microsoft 365 descritas neste artigo se aplicam ao Microsoft 365, SharePoint Online e Exchange Online. Essas opções de lançamento são maneiras direcionadas e de melhor esforço de lançar alterações no Microsoft 365, mas não podem ser garantidas em todos os momentos ou em todas as atualizações. Elas não se aplicam aos Aplicativos do Microsoft 365, Skype for Business, Microsoft Teams e serviços relacionados. Para saber mais sobre as opções de lançamento do Microsoft 365 Apps, confira Visão geral dos canais de atualização do [Microsoft 365 Apps.](https://docs.microsoft.com/deployoffice/overview-update-channels)

Com o Microsoft 365, você recebe novas atualizações de produto e recursos à medida que elas são disponibilizadas, em vez de fazer atualizações cara a cada alguns anos. Você pode gerenciar como sua organização recebe essas atualizações. Por exemplo, você pode se inscrever para uma versão antecipada para que sua organização receba atualizações primeiro. Você pode designar que apenas determinados indivíduos recebem as atualizações. Ou você pode permanecer no cronograma de lançamento padrão e receber as atualizações mais tarde. Este artigo explica as diferentes opções de lançamento e como você pode usá-las para sua organização.

## <a name="how-it-works---release-validation"></a>Como funciona - validação de versão

Qualquer nova versão é primeiro testada e validada pela equipe de recursos, depois por toda a equipe de recursos do Microsoft 365, seguida por toda a Microsoft. Depois de testes internos e validação, a próxima etapa é um **lançamento direcionado** (conhecido anteriormente como Primeiro Lançamento) para clientes que aceitarem. Em cada anel de lançamento, a Microsoft coleta comentários e valida mais a qualidade ao monitorar métricas de utilização importantes. Esta série de processos progressivos de validação serve para garantir que a versão mundial seja o mais robusta possível. As versões são ilustradas na figura a seguir. 
  
![Anéis de validação de versão do Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
Para atualizações significativas, os clientes são notificados inicialmente pelo [Mapa do Microsoft 365.](https://products.office.com/business/office-365-roadmap) À medida que uma atualização se aproxima da implantação, ela é comunicada por meio do centro de mensagens do [Microsoft 365.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)

> [!NOTE]
> Você precisa de uma conta do Microsoft 365 ou do Azure AD para acessar seu Centro de Mensagens por meio do [centro de administração.](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center) Os usuários do plano 365 home do Microsoft 365 não têm um centro de administração.


## <a name="standard-release"></a>Lançamento padrão

Essa é a opção padrão em que você e seus usuários recebem as atualizações mais recentes quando elas são lançadas amplamente para todos os clientes.
  
Uma boa prática é deixar a maioria dos usuários na versão  **Padrão** e os profissionais de IT e usuários avançados no Lançamento direcionado para avaliar novos recursos e preparar equipes para dar suporte a usuários e executivos de negócios. 
  
> [!NOTE]
> Caso mude do lançamento direcionado para o padrão, seus usuários podem perder o acesso aos recursos que ainda não chegaram ao lançamento padrão. 
  
## <a name="targeted-release"></a>Lançamento direcionado

Com esta opção, você e seus usuários podem ser os primeiros a conferir as atualizações mais recentes e ajudar no ajuste do produto, fornecendo comentários antecipadamente. Você pode optar que algumas pessoas ou que toda a organização receba as atualizações antecipadamente.
  
> [!IMPORTANT]
> As atualizações grandes ou complexas podem demorar mais do que as outras, portanto, nenhum usuário é afetado negativamente. Não há garantia quanto à linha do tempo exata de uma versão. 
  
### <a name="targeted-release-for-entire-organization"></a>Lançamento direcionado para toda a organização

Se você [configurar a opção de lançamento](#set-up-the-release-option-in-the-admin-center) no centro de administração para essa opção, todos os seus usuários terão a experiência de lançamento direcionado. Para organizações com mais de 300 usuários, recomendamos usar uma assinatura de teste para essa opção. Para obter informações sobre a assinatura de teste, fale com seu contato da Microsoft. 
  
### <a name="targeted-release-for-selected-users"></a>Lançamento direcionado para usuários selecionados

Se você [configurar a](#set-up-the-release-option-in-the-admin-center) opção de lançamento no centro de administração para essa opção, poderá definir usuários específicos, geralmente usuários avançados, para receber acesso antecipado aos recursos e funcionalidades. 
  
## <a name="benefits-of-targeted-release"></a>Benefícios do lançamento direcionado

O lançamento direcionado permite que administradores, gerentes de alterações ou qualquer outra pessoa responsável pelas atualizações do Microsoft 365 se preparem para as alterações futuras, permitindo que eles:
  
- Testem e validem novas atualizações antes de elas serem lançadas para todos os usuários da organização.
    
- Preparem a notificação para os usuários e a documentação antes que as atualizações sejam lançadas para todo o mundo.
    
- Preparem uma central de ajuda interna para as alterações futuras.
    
- Analisem as revisões de segurança e conformidade.
    
- Usem controles de recursos, quando aplicável, para controlar o lançamento das atualizações para os usuários finais.
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>Configurar a opção de lançamento no centro de administração

Você pode alterar como sua organização recebe atualizações do Microsoft 365 seguindo estas etapas. Você precisa ser um administrador global no Microsoft 365 para participar.
  
> [!IMPORTANT]
> Pode levar até 24 horas para que as alterações abaixo entre em vigor no Microsoft 365. Se você optar por cancelar o lançamento direcionado depois de ativá-lo, os usuários poderão perder o acesso aos recursos que ainda não chegaram ao lançamento padrão. 
  
1. In the admin center, go to the **Settings**  >  **Org Settings**, and under the **Organization profile** tab, choose Release **preferences**.

5. Para desabilitar o lançamento direcionado, selecione **Versão padrão** e, em seguida, selecione **Salvar alterações.** 
    
6. Para habilitar o lançamento direcionado para todos os usuários em sua organização, selecione **Lançamento direcionado para todos** e, em seguida, selecione Salvar **alterações.** 
    
7. Para habilitar o lançamento direcionado para algumas pessoas em sua organização, selecione Lançamento direcionado **para** usuários selecionados e, em seguida, **selecione Salvar alterações.** 
    
8. Escolha **Selecionar usuários** para adicionar usuários um de cada vez ou Carregar **usuários** para adicioná-los em massa.
    
9. Quando terminar de adicionar usuários, selecione **Salvar alterações.**


  
## <a name="learn-more"></a>Saiba mais

Descubra como gerenciar [mensagens no centro](https://docs.microsoft.com/office365/admin/manage/message-center) de mensagens do Microsoft [365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) para receber notificações sobre as próximas atualizações e versões do Microsoft 365.
