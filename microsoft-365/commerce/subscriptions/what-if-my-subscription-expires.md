---
title: O que acontecerá com os meus dados e com o meu acesso quando a assinatura terminar?
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 4436582f-211a-45ec-b72e-33647f97d8a3
description: Saiba o que acontece com seus dados quando a sua assinatura do Office 365 for Business expira, está desabilitada ou se você cancelar.
ms.openlocfilehash: 717beff94255fe669f9ce9bc733300679ffc3d53
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251495"
---
# <a name="what-happens-to-my-data-and-access-when-my-office-365-for-business-subscription-ends"></a>O que acontece com meus dados e acesso quando minha assinatura do Office 365 for Business termina?

Se sua assinatura terminar, pois ela expira ou porque você decide cancelar — seu acesso aos serviços do Office 365, aplicativos e dados do cliente passam por vários Estados antes que a assinatura seja totalmente desativada ou *desprovisionada*. Se você estiver ciente desse progresso, você ficará mais preparado para retornar sua assinatura para um estado ativo antes que seja muito tarde ou, se você estiver saindo do Office 365, faça backup dos seus dados antes que ele seja excluído.
  
## <a name="office-365-for-business-subscription-lifecycle"></a>Office 365 for Business: ciclo de vida de assinatura
- Se sua assinatura expirar, ela passará pelos seguintes estágios: expirado/desabilitado/desprovisionado. O estágio expirado é iniciado imediatamente após a assinatura atingir sua data de término.
- Se você desativar a cobrança recorrente em sua assinatura anual, ela passará pelos mesmos estágios de uma assinatura expirada. O primeiro estágio começa é o aniversário da assinatura anual, não começando na data em que você desativou a configuração de cobrança recorrente da assinatura.
- Se você cancelar sua assinatura mensal, ela será desabilitada imediatamente (na data de cancelamento). Isso significa que seus usuários perderão o acesso aos ativos do Office 365 imediatamente e apenas os administradores terão acesso aos dados pelos próximos 90 dias.

A tabela a seguir explica o que você pode esperar quando uma assinatura paga do Office 365 for Business expira.

| **Active**                                                             | **Expirado <br/>(30\*dias)**                                                | **Desabilitado <br/>(90\*dias)**                                               | **Desprovisionada**                                                                         |
|------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| *Dados acessíveis a todos*                                               | *Dados acessíveis a todos*                                                     | *Dados acessíveis somente para administradores*                                             | **Dados excluídos<br/>o Azure Active Directory foi removido, se não estiver sendo usado por outros serviços** |
| Os usuários têm acesso normal aos aplicativos do Office 365, aos dados e ao Office  | Os usuários têm acesso normal ao Office 365, arquivos e aplicativos              | Os usuários não podem acessar o Office 365, arquivos ou aplicativos                        | Os usuários não podem acessar o Office 365, arquivos ou aplicativos                                     |
| Os administradores têm acesso normal aos aplicativos do Office 365, aos dados e ao Office | Os administradores podem acessar o centro de administração                                           | Os administradores podem acessar o centro de administração, mas não podem atribuir licenças aos usuários       | Os administradores podem acessar o centro de administração para comprar e gerenciar outras assinaturas             |
|                                                                        | Administradores globais ou de cobrança podem reativar a assinatura no centro de administração | Administradores globais ou de cobrança podem reativar a assinatura no centro de administração |                                                                                           |

* Na maioria das ofertas, na maioria dos países e regiões.
  
> [!NOTE]
> **O que é "dados do cliente"?** Dados do cliente, conforme definido nos [termos do Microsoft Online Service](https://go.microsoft.com/fwlink/p/?LinkId=613649), refere-se a todos os dados, incluindo todos os arquivos de texto, som ou imagem fornecidos à Microsoft por, ou em nome de, o cliente através do uso do cliente do Office 365 Services. Para saber mais sobre a proteção de dados do cliente, confira o [introdução ao portal de confiança do serviço Microsoft](https://support.office.com/article/f30e2353-0bd6-41ed-8347-eea1fb8d2662).
  
## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a>Quais são as minhas opções se minha assinatura estiver prestes a expirar?

Enquanto uma assinatura estiver ativa, você e seus usuários finais terão acesso normal aos seus dados, serviços como email e OneDrive for Business e aplicativos do Office. Como administrador, você receberá uma série de notificações por email e no centro de administração à medida que sua assinatura se aproximar da data de vencimento.
  
Antes que a assinatura realmente alcance sua data de expiração, você tem algumas opções:

::: moniker range="o365-worldwide"
  
- **Habilitar cobrança recorrente para a assinatura.**

  - Se a **cobrança recorrente** já estiver ativada, não será necessário realizar qualquer ação. Sua assinatura será cobrada automaticamente e você será cobrado por um ano ou mês adicional, dependendo da sua frequência de pagamento atual. Se, por qualquer motivo, você tiver desativado a **cobrança recorrente** , sempre será possível [ativar novamente a cobrança recorrente](renew-your-subscription.md).

  - Se você comprou o Office 365 Business com um cartão pré-pago, é possível [ativar a cobrança recorrente](renew-your-subscription.md) para sua assinatura.

  - Se você for um cliente de licenciamento de volume aberto com uma assinatura pré-paga de um ano, entre em contato com seu parceiro para adquirir uma nova chave de produto. Você receberá instruções por email para ativar sua chave no [centro de serviços de licenciamento por volume](https://go.microsoft.com/fwlink/p/?LinkID=282016). Para saber como encontrar um novo parceiro ou o parceiro com o qual você trabalhou no passado, confira [localizar seu revendedor ou parceiro do Office 365](../../admin/manage/find-your-partner-or-reseller.md).

  - Se você tiver o Office 365 Business, confira [gerenciar a cobrança recorrente para sua assinatura](renew-your-subscription.md).

- **Deixe a assinatura expirar.**

  - Se você estiver pagando por cartão de crédito ou fatura e não quiser continuar sua assinatura, [desative a cobrança recorrente](renew-your-subscription.md). Sua assinatura expirará em sua data de expiração e você poderá ignorar todas as notificações de email relacionadas.

  - Se você for um cliente de licenciamento de volume aberto que trabalha com um parceiro, poderá deixar sua assinatura expirar não realizando nenhuma ação.

  - Se você é um cliente do Office 365 Small Business Premium e se aspagou o Office 365 e o ativou com uma chave do produto, você pode deixar que sua assinatura expire não realizando nenhuma ação.

- **Cancelar antes da expiração da assinatura.** Para obter detalhes, consulte [cancelar sua assinatura](cancel-your-subscription.md).
  
::: moniker-end

::: moniker range="o365-germany"
  
- **Gerenciar cobrança recorrente da assinatura.**

  - Se a **cobrança recorrente** já estiver ativada, não será necessário realizar qualquer ação. Sua assinatura será cobrada automaticamente e você será cobrado por um ano ou mês adicional, dependendo da sua frequência de pagamento atual. Se, por qualquer motivo, você tiver desativado a **cobrança recorrente** , sempre será possível [ativar novamente a cobrança recorrente](renew-your-subscription.md).

  - Se você comprou o Office 365 Business com um cartão pré-pago, é possível [ativar a cobrança recorrente](renew-your-subscription.md) para sua assinatura.

  - Se você for um cliente de licenciamento de volume aberto com uma assinatura pré-paga de um ano, entre em contato com seu parceiro para adquirir uma nova chave de produto. Você receberá instruções por email para ativar sua chave no [centro de serviços de licenciamento por volume](https://go.microsoft.com/fwlink/p/?LinkID=282016). Para saber como encontrar um novo parceiro ou o parceiro com o qual você trabalhou no passado, confira [localizar seu revendedor ou parceiro do Office 365](../../admin/manage/find-your-partner-or-reseller.md).

  - Se você tiver o Office 365 Business, confira [renovar o office 365 para empresas](renew-your-subscription.md).

- **Deixe a assinatura expirar.**

  - Se você estiver pagando por cartão de crédito ou fatura e não quiser continuar sua assinatura, [desative a cobrança recorrente](renew-your-subscription.md). Sua assinatura expirará em sua data de expiração e você poderá ignorar todas as notificações de email relacionadas.

  - Se você for um cliente de licenciamento de volume aberto que trabalha com um parceiro, poderá deixar sua assinatura expirar não realizando nenhuma ação.

  - Se você é um cliente do Office 365 Small Business Premium e se aspagou o Office 365 e o ativou com uma chave do produto, você pode deixar que sua assinatura expire não realizando nenhuma ação.

- **Cancelar antes da expiração da assinatura.** Para obter detalhes, consulte [cancelar sua assinatura](cancel-your-subscription.md).
  
::: moniker-end

::: moniker range="o365-21vianet"
  
- **Renove a assinatura.** Se a **cobrança recorrente** já estiver ativada, não será necessário realizar qualquer ação. Sua assinatura será cobrada automaticamente e você será cobrado por um ano ou mês adicional, dependendo da sua frequência de pagamento atual. Se, por qualquer motivo, você tiver desativado a **cobrança recorrente** , sempre será possível [ativar novamente a cobrança recorrente](renew-your-subscription.md).

- **Deixe a assinatura expirar.** Se você estiver pagando por cartão de crédito ou fatura e não quiser continuar sua assinatura, [desative a cobrança recorrente](renew-your-subscription.md). Sua assinatura expirará em sua data de expiração e você poderá ignorar todas as notificações de email relacionadas.

- **Cancelar antes da expiração da assinatura.** Para obter detalhes, consulte [cancelar sua assinatura](cancel-your-subscription.md).

::: moniker-end

## <a name="what-happens-after-my-subscription-expires"></a>O que acontece depois que minha assinatura expira?
Se você deixar a assinatura expirar, ela passará por vários Estados antes de ser excluída. Isso fornece a você, como administrador, o tempo de reativação se você quiser continuar o serviço ou fazer o backup de seus dados se decidir que não deseja mais a assinatura.
  
Veja aqui o que você pode esperar quando sua assinatura estiver em cada Estado.
  
### <a name="state-expired"></a>Estado: expirado
  
::: moniker range="o365-worldwide"

 **O que esperar:** O estado expirado dura 30 dias para a maioria das assinaturas, incluindo assinaturas adquiridas pela [Microsoft aberta](https://go.microsoft.com/fwlink/p/?LinkID=613298), na maioria dos países e regiões. Para produtos de licenciamento por volume, exceto o Microsoft Open, o estado expirado dura 90 dias.

::: moniker-end

::: moniker range="o365-germany"

 **O que esperar:** O estado expirado dura 30 dias para a maioria das assinaturas, incluindo assinaturas adquiridas pela [Microsoft aberta](https://go.microsoft.com/fwlink/p/?LinkID=613298), na maioria dos países e regiões. Para produtos de licenciamento por volume, exceto o Microsoft Open, o estado expirado dura 90 dias.

::: moniker-end

::: moniker range="o365-21vianet"

 **O que esperar:** O estado expirado é 30 dias para a maioria das assinaturas, na maioria dos países e regiões.

::: moniker-end

Nesse estado, os usuários têm acesso normal ao portal do Office 365, aplicativos do Office e serviços como email e SharePoint Online.
  
Como administrador, você ainda tem acesso ao centro de administração. Não se preocupe: os administradores globais ou de cobrança podem [reativar a assinatura](reactivate-your-subscription.md) e continuar usando o Office 365. Se você não reativar, certifique-se de [fazer backup dos dados](back-up-data-before-switching-plans.md).
  
### <a name="state-disabled"></a>Estado: desabilitado
  
::: moniker range="o365-worldwide"

 **O que esperar:** Se você não reativar sua assinatura enquanto ela estiver no estado expirado, ela será movida para um estado desabilitado, que dura 90 dias para a maioria das assinaturas, na maioria dos países e regiões. Para produtos de licenciamento por volume, o estado desabilitado dura 30 dias.

::: moniker-end

::: moniker range="o365-germany"

 **O que esperar:** Se você não reativar sua assinatura enquanto ela estiver no estado expirado, ela será movida para um estado desabilitado, que dura 90 dias para a maioria das assinaturas, na maioria dos países e regiões. Para produtos de licenciamento por volume, o estado desabilitado dura 30 dias.

::: moniker-end

::: moniker range="o365-21vianet"

 **O que esperar:** Se você não reativar sua assinatura enquanto ela estiver no estado expirado, ela será movida para um estado desabilitado, que é de 90 dias para a maioria das assinaturas, na maioria dos países e regiões.

::: moniker-end

::: moniker range="o365-worldwide"

Nesse estado, seu acesso diminui significativamente. Os usuários não podem entrar nem acessar serviços como email ou SharePoint Online. Os aplicativos do Office eventualmente são movidos para um modo de funcionalidade somente leitura e reduzido e exibem [notificações de produtos não licenciados](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx). Você ainda pode entrar e acessar o centro de administração, mas não pode atribuir licenças aos usuários. Os dados do cliente, incluindo todos os dados do usuário, emails e arquivos em sites de equipe, estão disponíveis apenas para você e outros administradores.

::: moniker-end

Como administrador global ou de cobrança, você pode [reativar a assinatura](reactivate-your-subscription.md) e continuar usando o Office 365 com todos os dados do cliente intactos. Se você optar por não reativar, certifique-se de [fazer backup dos dados](back-up-data-before-switching-plans.md).

### <a name="state-deprovisioned"></a>Estado: desprovisionado
  
 **O que esperar:** Se você não reativar sua assinatura enquanto ela estiver em cortesia ou estiver desabilitada, a assinatura será desprovisionada.
  
Administradores e usuários não têm mais acesso aos serviços ou aplicativos do Office que vieram com a assinatura. Todos os dados do cliente, de dados de usuários para documentos e emails, são excluídos permanentemente e não podem ser recuperados de nenhuma forma.
  
Neste ponto, não é possível reativar a assinatura. No entanto, como administrador global ou de cobrança, você ainda pode acessar o centro de administração para gerenciar outras assinaturas ou comprar novas assinaturas para atender às suas necessidades de negócios.
  
> [!NOTE]
> A adição de uma nova assinatura do mesmo tipo que foi desprovisionada não restaura os dados associados à assinatura desprovisionada.

### <a name="what-happens-when-my-trial-ends"></a>O que acontece quando minha avaliação termina?

Quando a avaliação terminar, você não poderá continuar usando o Office 365 gratuitamente. Você tem algumas opções:

::: moniker range="o365-worldwide"
- **Comprar o Office 365.** Quando a avaliação expira, ela é movida para um período de cortesia, dando mais 30 dias (para a maioria dos testes, na maioria dos países e regiões) para comprar o Office 365. Para saber como converter a avaliação em uma assinatura paga, confira [comprar sua versão de avaliação do Office 365 for Business](../buy-a-subscription-from-your-free-trial.md).

::: moniker-end

::: moniker range="o365-germany"
- **Comprar o Office 365.** Quando a avaliação expira, ela é movida para um período de cortesia, dando mais 30 dias (para a maioria dos testes, na maioria dos países e regiões) para comprar o Office 365. Para saber como converter a avaliação em uma assinatura paga, confira [comprar sua versão de avaliação do Office 365 for Business](../buy-a-subscription-from-your-free-trial.md).

::: moniker-end

::: moniker range="o365-21vianet"
- **Comprar o Office 365.** Quando a avaliação expira, ela é movida para um período de cortesia, dando mais 30 dias (para a maioria dos testes, na maioria dos países e regiões) para comprar o Office 365. Para saber como converter a avaliação em uma assinatura paga, consulte [comprar ou experimentar assinaturas do Office 365 operado pela 21vianet](../../admin/services-in-china/buy-or-try-subscriptions.md).

::: moniker-end

- **Estenda a avaliação.** Precisa de mais tempo para avaliar o Office 365? Em alguns casos, você poderá [estender a avaliação](../extend-your-trial.md).

- **Cancele a avaliação ou deixe-a expirar.** Se você decidir não comprar o Office 365, poderá deixar que sua avaliação expire ou [cancelá-la](cancel-your-subscription.md). Certifique-se de fazer backup de todos os dados que você deseja manter. Logo após o período de cortesia de 30 dias, as informações e os dados da conta de avaliação são apagados permanentemente.

## <a name="what-happens-if-i-cancel-a-subscription"></a>O que acontece se eu cancelar uma assinatura?

Se você cancelar sua assinatura antes da data de término do termo, a assinatura ignorará o estado expirado e passará diretamente para o estado desabilitado, que é 90 dias para a maioria das assinaturas, na maioria dos países e regiões. Recomendamos que você [faça o backup de seus dados](back-up-data-before-switching-plans.md) antes de cancelar, mas como um administrador, você ainda pode acessar e fazer o backup de dados da sua organização enquanto ele estiver no estado desabilitado. Todos os dados do cliente que você deixar atrás poderão ser excluídos após 90 dias, e não serão excluídos depois de 180 dias após o cancelamento.
  
Veja o que esperar para você e seus usuários se cancelar uma assinatura.
  
- **Acesso de administrador** Os administradores ainda podem entrar e acessar o centro de administração e comprar outras assinaturas conforme necessário. Como administrador global ou de cobrança, você tem 90 dias para [reativar a assinatura](reactivate-your-subscription.md) com todos os dados intactos.

- **Acesso de usuário** Os usuários não poderão usar serviços como o OneDrive for Business ou acessar dados do cliente, por exemplo, emails ou documentos em sites de equipe. Os aplicativos Office, como o Word e Excel entrarão em um modo de funcionalidade reduzida de somente leitura e exibirão [notificações de Produto não Licenciado](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx).

Para saber como cancelar, confira [cancelar sua assinatura](cancel-your-subscription.md).
  
> [!IMPORTANT]
> Se quiser que seus dados de assinatura sejam excluídos antes que o período normal desabilitado seja superior, você poderá solicitar um desprovisionamento expedido. Quando você solicita o desprovisionamento expresso, os dados da sua assinatura são excluídos em até três dias após o cancelamento. Para usar o desprovisionamento expresso, [ligue para o suporte](../../admin/contact-support-for-business-products.md).

> [!NOTE]
> As informações nesta página estão sujeitas ao [aviso de isenção de responsabilidade e alteração da política da Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=613651). Retorne a este site periodicamente para revisar as alterações.
