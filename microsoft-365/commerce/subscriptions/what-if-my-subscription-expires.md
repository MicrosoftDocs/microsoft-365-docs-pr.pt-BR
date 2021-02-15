---
title: O que acontecerá com os meus dados e com o meu acesso quando a assinatura terminar?
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 4436582f-211a-45ec-b72e-33647f97d8a3
description: Saiba o que acontece com seus dados quando sua assinatura do Microsoft 365 para empresas expirar, estiver desabilitada ou se você cancelar.
ms.openlocfilehash: c191b2fa795614a272b28cedae8d23693933dc95
ms.sourcegitcommit: 0badd6a7af803a52c7c46a4374211cb89307eacf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49135974"
---
# <a name="what-happens-to-my-data-and-access-when-my-microsoft-365-for-business-subscription-ends"></a>O que acontece com meus dados e acesso quando minha assinatura do Microsoft 365 para empresas termina?

Se sua assinatura terminar, seja porque ela expirará ou porque você decidir cancelar, o acesso aos serviços, aplicativos e dados do cliente do Microsoft 365 passa por vários estados antes que a assinatura seja totalmente desligada ou *excluída.* Se estiver ciente dessa progressão, você estará melhor preparado para retornar sua assinatura a um estado ativo antes que seja muito tarde ou, se estiver deixando o Microsoft 365, fazer o back up dos dados antes que eles sejam excluídos.

Leia essas informações importantes antes de entrar em contato com o [suporte do Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
  
## <a name="what-happens-to-data-when-a-subscription-expires"></a>O que acontece com os dados quando uma assinatura expira?

- Se a sua assinatura expirar, ela passará pelos seguintes estágios: Expirada/ Desabilitada/ Excluída. O estágio Expirado começa imediatamente após a assinatura ter atingido sua data de término.
- Se você desativar a cobrança recorrente em sua assinatura anual, ela passará pelos mesmos estágios de uma assinatura expirada. O primeiro estágio é o aniversário da assinatura anual, não a partir da data em que você ajustou a configuração de cobrança recorrente da assinatura.
- Se você cancelar sua assinatura mensal, ela será desabilitada imediatamente (na data de cancelamento). Isso significa que os usuários perderão o acesso aos ativos do Microsoft 365 imediatamente e somente os administradores terão acesso aos dados nos próximos 90 dias.

A tabela a seguir explica o que você pode esperar quando uma assinatura paga do Microsoft 365 para empresas expirar.

| Ativo | Expirado <br/>(30 \* dias) | Desabilitado <br/>(90 \* dias) | Deleted |
|------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| *Dados acessíveis a todos*                                               | *Dados acessíveis a todos*                                                     | *Dados acessíveis somente para administradores*                                             | **Os dados excluídos <br/> do Azure Active Directory serão removidos, se não estiver sendo usado por outros serviços** |
| Os usuários têm acesso normal ao Microsoft 365, arquivos e aplicativos   | Os usuários têm acesso normal ao Microsoft 365, arquivos e aplicativos              | Os usuários não podem acessar o Microsoft 365, arquivos ou aplicativos                        | Os usuários não podem acessar o Microsoft 365, arquivos ou aplicativos                                     |
| Os administradores têm acesso normal ao Microsoft 365, dados e aplicativos do Office | Os administradores podem acessar o centro de administração                                           | Os administradores podem acessar o centro de administração, mas não podem atribuir licenças aos usuários       | Os administradores podem acessar o centro de administração para comprar e gerenciar outras assinaturas             |
|                                                                        | Os administradores globais ou de cobrança podem reativar a assinatura no centro de administração | Os administradores globais ou de cobrança podem reativar a assinatura no centro de administração |                                                                                           |

*Para a maioria das ofertas, na maioria dos países e regiões.
  
> [!NOTE]
> **O que são "dados do cliente"?** Os dados do cliente, conforme definidos nos Termos de Serviço do [Microsoft Online,](https://go.microsoft.com/fwlink/p/?LinkId=613649)referem-se a todos os dados, incluindo todos os arquivos de texto, som ou imagem fornecidos à Microsoft pelo cliente, ou em nome dele, por meio do uso dos serviços do Microsoft 365 pelo cliente. Para saber mais sobre a proteção de dados do cliente, consulte o Portal de Confiança [do Serviço da Microsoft.](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-service-trust-portal)

## <a name="what-happens-if-i-cancel-a-subscription"></a>O que acontece se eu cancelar uma assinatura?

Se você cancelar sua assinatura antes da data de término do período, a assinatura ignorará o estado expirado e será diretamente para o estado desabilitado, que é de 90 dias para a maioria das assinaturas, na maioria dos países e regiões. Recomendamos fazer [o back up](back-up-data-before-switching-plans.md) dos dados antes de cancelar, mas, como administrador, você ainda pode acessar e fazer o back up dos dados da sua organização enquanto eles estão no estado desabilitado. Quaisquer dados de cliente que você deixar para trás podem ser excluídos após 90 dias e serão excluídos no prazo de 180 dias após o cancelamento.
  
Veja o que esperar de você e seus usuários se você cancelar uma assinatura.
  
- **Acesso de administrador** Os administradores ainda podem entrar e acessar o centro de administração e comprar outras assinaturas conforme necessário. Como administrador global ou de cobrança, você tem 90 dias para [reativar](reactivate-your-subscription.md) a assinatura com todos os dados intactos.

- **Acesso de usuário** Seus usuários não poderão usar serviços como o OneDrive for Business ou acessar dados do cliente— por exemplo, emails ou documentos em sites de equipe. Os aplicativos Office, como o Word e Excel entrarão em um modo de funcionalidade reduzida de somente leitura e exibirão [notificações de Produto não Licenciado](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx).

Para saber como cancelar, confira [Cancelar sua assinatura.](cancel-your-subscription.md)
  
> [!IMPORTANT]
> Se quiser que seus dados de assinatura sejam excluídos antes que o período desabilitado típico seja final, você [pode fechar sua conta.](../close-your-account.md)
  
## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a>Quais são as minhas opções se minha assinatura estiver prestes a expirar?

Enquanto uma assinatura está ativa, você e seus usuários finais têm acesso normal aos seus dados, serviços como email, OneDrive for Business e aplicativos do Office. Como administrador, você receberá uma série de notificações por email e no centro de administração à medida que sua assinatura se aproximar da data de expiração.
  
Antes que a assinatura expire, você tem as seguintes opções:

::: moniker range="o365-worldwide"
  
- **Habilita a cobrança recorrente para a assinatura.**

  - Se **a cobrança recorrente** já estiver tiva, você não precisa tomar nenhuma ação. Sua assinatura é cobrada automaticamente e você é cobrado por um ano ou mês adicional, dependendo da frequência de pagamento atual. Se, por algum motivo, você **tiver** desligado a cobrança recorrente, sempre poderá ativar novamente a [cobrança recorrente.](renew-your-subscription.md)

  - Se você comprou o Microsoft 365 Apps para Empresas com um cartão pré-pago, poderá ativar a cobrança [recorrente](renew-your-subscription.md) da sua assinatura.

  - Se você for um cliente do Open Volume Licensing com uma assinatura pré-paga de um ano, entre em contato com seu parceiro para comprar uma nova chave do produto. Você receberá instruções por email para ativar sua chave no Centro de [Serviços de Licenciamento por Volume.](https://go.microsoft.com/fwlink/p/?LinkID=282016) Para saber como encontrar um novo parceiro ou o parceiro com o qual você trabalhou no passado, consulte Encontrar seu parceiro [ou revendedor.](../../admin/manage/find-your-partner-or-reseller.md)

  - Se você tiver o Microsoft 365 Apps para empresas, confira [Gerenciar cobranças recorrentes para sua assinatura.](renew-your-subscription.md)

- **Deixe a assinatura expirar.**

  - Se você estiver pagando por cartão de crédito ou fatura e não quiser continuar sua assinatura, desativar a [cobrança recorrente.](renew-your-subscription.md) Sua assinatura termina na data de expiração, e você pode ignorar todas as notificações de email relacionadas.

  - Se você for um cliente do Open Volume Licensing trabalhando com um parceiro, poderá deixar sua assinatura expirar sem tomar nenhuma ação.

  - Se você for um cliente do Office 365 Small Business Premium e tiver pré-pago ao Office 365 e o tiver ativado com uma chave do produto, poderá permitir que sua assinatura expire sem tomar nenhuma ação.

- **Cancelar antes que a assinatura expire.** Para obter detalhes, [consulte Cancelar sua assinatura.](cancel-your-subscription.md)
  
::: moniker-end

::: moniker range="o365-germany"
  
- **Gerencie a cobrança recorrente da assinatura.**

  - Se **a cobrança recorrente** já estiver tiva, você não precisa tomar nenhuma ação. Sua assinatura será renovada automaticamente na data de término do prazo e será cobrado um ano ou mês adicional, dependendo da sua frequência de pagamento atual. Se, por algum motivo, você **tiver** desligado a cobrança recorrente, sempre poderá ativar novamente a [cobrança recorrente.](renew-your-subscription.md)

  - Se você comprou o Microsoft 365 Apps para Empresas com um cartão pré-pago, poderá ativar a cobrança [recorrente](renew-your-subscription.md) da sua assinatura.

  - Se você for um cliente do Open Volume Licensing com uma assinatura pré-paga de um ano, entre em contato com seu parceiro para comprar uma nova chave do produto. Você receberá instruções por email para ativar sua chave no Centro de [Serviços de Licenciamento por Volume.](https://go.microsoft.com/fwlink/p/?LinkID=282016) Para saber como encontrar um novo parceiro ou o parceiro com o qual você trabalhou no passado, consulte Encontrar seu parceiro [ou revendedor.](../../admin/manage/find-your-partner-or-reseller.md)

  - Se você tiver o Microsoft 365 Apps para empresas, confira [Renovar sua assinatura.](renew-your-subscription.md)

- **Deixe a assinatura expirar.**

  - Se você estiver pagando por cartão de crédito ou fatura e não quiser continuar sua assinatura, desativar a [cobrança recorrente.](renew-your-subscription.md) Sua assinatura expirará na data de expiração e você poderá ignorar todas as notificações de email relacionadas.

  - Se você for um cliente do Open Volume Licensing trabalhando com um parceiro, poderá deixar sua assinatura expirar sem tomar nenhuma ação.

  - Se você for um cliente do Office 365 Small Business Premium e for pré-pago para o Office 365 e o tiver ativado com uma chave do produto, poderá permitir que sua assinatura expire sem tomar nenhuma ação.

- **Cancelar antes que a assinatura expire.** Para obter detalhes, [consulte Cancelar sua assinatura.](cancel-your-subscription.md)
  
::: moniker-end

::: moniker range="o365-21vianet"
  
- **Renove a assinatura.** Se **a cobrança recorrente** já estiver tiva, você não precisa tomar nenhuma ação. Sua assinatura será renovada automaticamente na data de término do prazo e será cobrado um ano ou mês adicional, dependendo da sua frequência de pagamento atual. Se, por algum motivo, você **tiver** desligado a cobrança recorrente, sempre poderá ativar novamente a [cobrança recorrente.](renew-your-subscription.md)

- **Deixe a assinatura expirar.** Se você estiver pagando por cartão de crédito ou fatura e não quiser continuar sua assinatura, desativar a [cobrança recorrente.](renew-your-subscription.md) Sua assinatura expirará na data de expiração e você poderá ignorar todas as notificações de email relacionadas.

- **Cancelar antes que a assinatura expire.** Para obter detalhes, [consulte Cancelar sua assinatura.](cancel-your-subscription.md)

::: moniker-end

## <a name="what-happens-after-my-subscription-expires"></a>O que acontece depois que minha assinatura expira?
Se você deixar sua assinatura expirar, ela passará por vários estados antes de ser excluída por fim. Isso lhe dará, como administrador, tempo para reativar se você quiser continuar o serviço ou fazer o back up de seus dados se decidir que não deseja mais a assinatura.
  
Veja o que você pode esperar quando sua assinatura estiver em cada estado.
  
### <a name="state-expired"></a>Estado: Expirado
  
::: moniker range="o365-worldwide"

 **O que esperar:** O estado expirado dura 30 dias para a maioria das assinaturas, incluindo assinaturas adquiridas por meio do [Microsoft Open,](https://go.microsoft.com/fwlink/p/?LinkID=613298)na maioria dos países e regiões. Para produtos de Licenciamento por Volume, exceto o Microsoft Open, o estado expirado dura 90 dias.

::: moniker-end

::: moniker range="o365-germany"

 **O que esperar:** O estado expirado dura 30 dias para a maioria das assinaturas, incluindo assinaturas adquiridas por meio do [Microsoft Open,](https://go.microsoft.com/fwlink/p/?LinkID=613298)na maioria dos países e regiões. Para produtos de Licenciamento por Volume, exceto o Microsoft Open, o estado expirado dura 90 dias.

::: moniker-end

::: moniker range="o365-21vianet"

 **O que esperar:** O estado expirado é de 30 dias para a maioria das assinaturas, na maioria dos países e regiões.

::: moniker-end

Nesse estado, os usuários têm acesso normal ao portal do Microsoft 365, aplicativos do Office e serviços como email e SharePoint Online.
  
Como administrador, você ainda tem acesso ao centro de administração. Não se preocupe— os administradores globais ou de cobrança podem [reativar](reactivate-your-subscription.md) a assinatura e continuar usando o Microsoft 365. Se você não reativar, [fazer o back up de seus dados.](back-up-data-before-switching-plans.md)
  
### <a name="state-disabled"></a>Estado: Desabilitado
  
::: moniker range="o365-worldwide"

 **O que esperar:** Se você não reativar sua assinatura enquanto ela estiver no estado expirado, ela se move para um estado desabilitado, que dura 90 dias para a maioria das assinaturas, na maioria dos países e regiões. Para produtos de Licenciamento por Volume, o estado desabilitado dura 30 dias.

::: moniker-end

::: moniker range="o365-germany"

 **O que esperar:** Se você não reativar sua assinatura enquanto ela estiver no estado expirado, ela se move para um estado desabilitado, que dura 90 dias para a maioria das assinaturas, na maioria dos países e regiões. Para produtos de Licenciamento por Volume, o estado desabilitado dura 30 dias.

::: moniker-end

::: moniker range="o365-21vianet"

 **O que esperar:** Se você não reativar sua assinatura enquanto ela estiver no estado expirado, ela se move para um estado desabilitado, que é de 90 dias para a maioria das assinaturas, na maioria dos países e regiões.

::: moniker-end

::: moniker range="o365-worldwide"

Nesse estado, seu acesso diminui significativamente. Os usuários não podem entrar ou acessar serviços como email ou SharePoint Online. Eventualmente, os aplicativos do Office se movem para um modo de funcionalidade reduzida e somente leitura e exibem notificações de produto [não licençada.](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx) Você ainda pode entrar e acessar o centro de administração, mas não pode atribuir licenças aos usuários. Os dados do cliente, incluindo todos os dados do usuário, email e arquivos em sites de equipe, estão disponíveis somente para você e outros administradores.

::: moniker-end

Como administrador global ou de cobrança, você pode [reativar](reactivate-your-subscription.md) a assinatura e continuar usando o Microsoft 365 com todos os dados do cliente intactos. Se você optar por não reativar, [fazer o back up de seus dados.](back-up-data-before-switching-plans.md)

### <a name="state-deleted"></a>Estado: Excluído
  
 **O que esperar:** Se você não reativar sua assinatura enquanto ela estiver na carência ou desabilitada, a assinatura será excluída.
  
Os administradores e usuários não têm mais acesso aos serviços ou aplicativos do Office que vieram com a assinatura. Todos os dados do cliente, de dados do usuário a documentos e emails, são excluídos permanentemente e irrecuperáveis.
  
Neste ponto, você não pode reativar a assinatura. No entanto, como administrador global ou de cobrança, você ainda pode acessar o centro de administração para gerenciar outras assinaturas ou comprar novas assinaturas para atender às suas necessidades de negócios.
  
> [!NOTE]
> A adição de uma nova assinatura do mesmo tipo que foi excluída não restaura os dados associados à assinatura excluída.


> [!NOTE]
> Se uma licença do CSP for suspensa, não haverá um período de carência de 30 dias e os serviços serão desabilitados imediatamente. Os dados serão excluídos após 90 dias se o locatário não for reativado adicionando uma nova licença.

### <a name="what-happens-when-my-trial-ends"></a>O que acontece quando a avaliação termina?

Quando a avaliação terminar, você não poderá continuar a usar o Microsoft 365 gratuitamente. Você tem algumas opções:

::: moniker range="o365-worldwide"

- **Compre o Microsoft 365.** Quando sua avaliação expira, ele passa para um período de carência, dando a você mais 30 dias (para a maioria das tentativas, na maioria dos países e regiões) para comprar o Microsoft 365. Para saber como converter sua avaliação em uma assinatura paga, confira Comprar sua versão de avaliação do [Microsoft 365 para empresas.](../buy-a-subscription-from-your-free-trial.md)

::: moniker-end

::: moniker range="o365-germany"

- **Compre o Microsoft 365.** Quando sua avaliação expira, ele passa para um período de carência, dando a você mais 30 dias (para a maioria das tentativas, na maioria dos países e regiões) para comprar o Microsoft 365. Para saber como converter sua avaliação em uma assinatura paga, confira Comprar sua versão de avaliação do [Microsoft 365 para empresas.](../buy-a-subscription-from-your-free-trial.md)

::: moniker-end

::: moniker range="o365-21vianet"

- **Compre o Office 365.** Quando sua avaliação expira, ele passa para um período de carência, dando a você mais 30 dias (para a maioria das tentativas, na maioria dos países e regiões) para comprar o Office 365. Para saber como converter sua avaliação em uma assinatura paga, confira Comprar ou experimentar assinaturas do Office 365 operado pela [21Vianet.](../../admin/services-in-china/buy-or-try-subscriptions.md)

::: moniker-end

- **Estenda sua avaliação.** Precisa de mais tempo para avaliar o Microsoft 365? Em determinados casos, você pode [estender sua avaliação.](../extend-your-trial.md)

- **Cancele a avaliação ou deixe-a expirar.** Se você decidir não comprar o Microsoft 365, poderá permitir que sua avaliação expire ou [cancele-a.](cancel-your-subscription.md) Fazer o back up de todos os dados que você deseja manter. Logo após o período de carência de 30 dias, as informações e os dados da sua conta de avaliação serão apagados permanentemente.

> [!NOTE]
> As informações nesta página estão sujeitas ao Aviso de [Isenção de Responsabilidade e Aviso de Alteração da Política da Microsoft.](https://go.microsoft.com/fwlink/p/?LinkId=613651) Retorne a este site periodicamente para revisar as alterações.

## <a name="related-content"></a>Conteúdo relacionado 

[Cancelar sua assinatura](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/cancel-your-subscription) (artigo)\
[Renovar o Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/renew-your-subscription) (artigo)\
[Reativar sua assinatura](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/reactivate-your-subscription) (artigo)

