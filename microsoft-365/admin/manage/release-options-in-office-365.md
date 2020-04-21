---
title: Configurar as opções de lançamento padrão ou direcionadas
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Saiba como configurar a opção de lançamento para novas atualizações de produtos e recursos no centro de administração do Microsoft 365.
ms.openlocfilehash: 11672e46acb3124c8fd840ab19ee683cfd6af94f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628107"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>Configurar as opções de lançamento padrão ou direcionadas

Com o Microsoft 365, você recebe novos recursos e atualizações de produtos à medida que eles são disponibilizados em vez de realizar atualizações dispendiosas a cada ano. Você pode gerenciar como sua organização recebe essas atualizações. Por exemplo, você pode se inscrever em uma versão antecipada para que sua organização receba as atualizações primeiro. Você pode designar que apenas alguns usuários recebem as atualizações. Ou você pode permanecer no cronograma de lançamento padrão e receber as atualizações mais tarde. Este artigo explica as diferentes opções de versão e como você pode usá-las para sua organização.
  
> [!IMPORTANT]
> As atualizações 365 da Microsoft descritas neste artigo aplicam-se ao Microsoft 365, ao SharePoint Online e ao Exchange Online. Elas não se aplicam ao Skype for Business e aos serviços relacionados. Essas opções de versão são direcionadas, as melhores maneiras de lançar as alterações no Microsoft 365, mas não podem ser garantidas sempre ou para todas as atualizações. 
  
## <a name="how-it-works---release-validation"></a>Como funciona - validação de versão

Qualquer nova versão é testada e validada pela equipe de recursos e, em seguida, por toda a equipe de recursos do Microsoft 365, seguida por toda a Microsoft. Depois de testes internos e validação, a próxima etapa é um **lançamento direcionado** (conhecido anteriormente como Primeiro Lançamento) para clientes que aceitarem. Em cada anel de lançamento, a Microsoft coleta comentários e valida mais a qualidade ao monitorar métricas de utilização importantes. Esta série de processos progressivos de validação serve para garantir que a versão mundial seja o mais robusta possível. As versões são ilustradas na figura a seguir. 
  
![Liberar toques de validação para o Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
Para atualizações significativas, os clientes do Office são inicialmente notificados pelo [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap). Como uma atualização está mais próxima de ser implantada, ela é comunicada através do seu [centro de mensagens do Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).

> [!NOTE]
> Você precisa de uma conta do Microsoft 365 ou do Azure AD para acessar seu centro de mensagens por meio do [centro de administração](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center). O Microsoft 365 Home Plan Users não têm um centro de administração.


## <a name="standard-release"></a>Lançamento padrão

Esta é a opção padrão em que você e seus usuários recebem as atualizações mais recentes quando são lançadas amplamente para todos os clientes.
  
Uma boa prática é deixar a maioria dos usuários em **lançamentos padrão** e profissionais de ti e usuários avançados no **lançamento direcionado** para avaliar novos recursos e preparar o Microsoft Teams para dar suporte a usuários e executivos corporativos. 
  
> [!NOTE]
> Caso mude do lançamento direcionado para o padrão, seus usuários podem perder o acesso aos recursos que ainda não chegaram ao lançamento padrão. 
  
## <a name="targeted-release"></a>Lançamento direcionado

Com esta opção, você e seus usuários podem ser os primeiros a conferir as atualizações mais recentes e ajudar no ajuste do produto, fornecendo comentários antecipadamente. Você pode optar que algumas pessoas ou que toda a organização receba as atualizações antecipadamente.
  
> [!IMPORTANT]
> As atualizações grandes ou complexas podem demorar mais do que as outras, portanto, nenhum usuário é afetado negativamente. Não há garantia quanto à linha do tempo exata de uma versão. 
  
### <a name="targeted-release-for-entire-organization"></a>Lançamento direcionado para toda a organização

Se você [Configurar a opção de lançamento no centro de administração](#set-up-the-release-option-in-the-admin-center) para esta opção, todos os usuários receberão a experiência de lançamento direcionada. Para organizações com mais de 300 usuários, recomendamos usar uma assinatura de teste para essa opção. Para obter informações sobre a assinatura de teste, fale com seu contato da Microsoft. 
  
### <a name="targeted-release-for-selected-users"></a>Lançamento direcionado para usuários selecionados

Se você [Configurar a opção liberar no centro de administração](#set-up-the-release-option-in-the-admin-center) para esta opção, é possível definir usuários específicos, geralmente usuários avançados, para receber acesso antecipado aos recursos e funcionalidades. 
  
## <a name="benefits-of-targeted-release"></a>Benefícios do lançamento direcionado

O lançamento direcionado permite que os administradores, os gerentes de alteração ou qualquer pessoa responsável pelas atualizações da Microsoft 365 se preparam nas alterações futuras, permitindo que eles:
  
- Testem e validem novas atualizações antes de elas serem lançadas para todos os usuários da organização.
    
- Preparem a notificação para os usuários e a documentação antes que as atualizações sejam lançadas para todo o mundo.
    
- Preparem uma central de ajuda interna para as alterações futuras.
    
- Analisem as revisões de segurança e conformidade.
    
- Usem controles de recursos, quando aplicável, para controlar o lançamento das atualizações para os usuários finais.
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>Configurar a opção de lançamento no centro de administração

Você pode alterar como sua organização recebe as atualizações da Microsoft 365 seguindo estas etapas. Você precisa ser um administrador global no Microsoft 365 para aceitar o.
  
> [!IMPORTANT]
> Pode levar até 24 horas para que as alterações abaixo tenham efeito no Microsoft 365. Se você optar por cancelar o lançamento direcionado depois de ativá-lo, os usuários poderão perder o acesso aos recursos que ainda não chegaram ao lançamento padrão. 
  
1. No centro de administração, vá para a **Settings** > **configuração**configurações e, na guia **perfil da organização** , escolha **preferências de versão**.

5. Para desabilitar o lançamento direcionado, selecione **versão padrão**e, em seguida, selecione **salvar alterações**. 
    
6. Para habilitar o lançamento direcionado para todos os usuários em sua organização, selecione **lançamento direcionado para todos**e, em seguida, selecione **salvar alterações**. 
    
7. Para habilitar o lançamento direcionado para algumas pessoas em sua organização, selecione **lançamento direcionado para usuários selecionados**e, em seguida, selecione **salvar alterações**. 
    
8. Escolha **Selecionar usuários** para adicionar usuários, um de cada vez, ou **carregar usuários** para adicioná-los em massa.
    
9. Quando terminar de adicionar usuários, selecione **salvar alterações**.



## <a name="get-the-targeted-release-version-of-office"></a>Obter a versão de lançamento direcionado do Office

Para instalar um build de lançamento direcionado do Office, [siga estas etapas](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). Isso lhe dará acesso antecipado aos novos recursos do Office 2016 para área de trabalho do Windows.
  
## <a name="learn-more"></a>Saiba mais

Descubra como [gerenciar mensagens](https://docs.microsoft.com/office365/admin/manage/message-center) no seu [centro de mensagens do Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) para obter notificações sobre futuras atualizações e versões do Microsoft 365.
