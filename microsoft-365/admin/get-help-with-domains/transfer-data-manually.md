---
title: Transferir dados manualmente entre duas contas
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: Encontre como transferir dados manualmente entre duas contas do Microsoft 365 quando você alterou o plano ou o nome da empresa ou combinou várias assinaturas em uma.
ms.openlocfilehash: 69476687915024accabdce2a603ebdd7e8b653af
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399867"
---
# <a name="transfer-data-manually-between-two-accounts"></a>Transferir dados manualmente entre duas contas

Prepare-se para acumular suas mangas e bloquear um bloco de tempo no seu calendário: transferir dados entre duas contas da Microsoft 365 é um processo manual, complicado e demorado. Este não é um processo automatizado ou com suporte. Vamos começar.
  
> [!CAUTION]
> Haverá tempo de inatividade durante o processo em que o email, o Skype for Business e um site público hospedado no Microsoft 365 não funcionarão. Os usuários receberão novos nomes de usuário e senhas, e eles precisarão redefinir o Outlook.

**Transfira dados manualmente usando as instruções neste tópico se uma das seguintes opções se aplicar:**
  
- Você precisa mudar para um plano em uma família de serviços diferente.

- O nome da sua empresa mudou e você optou por criar uma nova assinatura e migrar seus dados porque deseja usar nomes de domínio iniciais diferentes.

- Você precisa combinar várias assinaturas em uma nova.

> [!IMPORTANT]
> Se você precisar [alterar seu plano de assinatura](../../commerce/subscriptions/switch-to-a-different-plan.md) e puder usar o assistente de mudança de planos, ou se precisar transferir para um novo plano de assinatura na mesma família de assinatura, mesmo quando o assistente de alternância de planos não funcionar, não será necessário transferir manualmente os dados e não há tempo de inatividade.

|**Tasks**|**Steps**|
|:-----|:-----|
|Adquira o plano para o qual você deseja mover.  <br/> |Ao se inscrever, especifique o nome da empresa a ser usado nos nomes de domínio iniciais: *yourcompany* . onmicrosoft.com, *yourcompany* -public.sharepoint.com e *yourcompany* . SharePoint.com. Você precisa usar um nome diferente do *yourcompany* do que você fazia para assinaturas existentes.  <br/> > [!NOTE]> normalmente, isso leva um mínimo de vários meses após o cancelamento de uma assinatura para liberar os nomes de domínio iniciais que usam o *yourcompany* de nossos sistemas. Mesmo que você planeje salvar todos os seus dados da assinatura antiga do Microsoft 365 e cancelar essa assinatura, o valor antigo do *yourcompany* não estará disponível imediatamente para uso em uma nova assinatura.           |
|Remova seu domínio personalizado da sua assinatura antiga do Microsoft 365.  <br/> | Siga as [etapas necessárias antes de remover um domínio](remove-a-domain.md) para remover o nome de domínio dos endereços de email do usuário e remover registros DNS para email e Lync para o domínio personalizado. Se você hospeda seu site público no Microsoft 365, você também precisa remover o registro CNAME que aponta para ele.  <br/> > [!IMPORTANT]> depois de remover o registro MX que roteia o email para este domínio personalizado, o email deixará de funcionar até que você tenha adicionado o domínio à sua nova conta, configure o novo registro MX e configure seus usuários. Quando você remover os registros DNS para o Lync, o Lync parará de funcionar. E depois de remover o registro CNAME que aponta para seu site público, ele não estará disponível.           [Remova o domínio](remove-a-domain.md) .  <br/> |
|Configure seu domínio personalizado para sua nova assinatura e configure seus usuários.  <br/> | Configure sua nova assinatura, incluindo a criação de registros DNS necessários para seu domínio personalizado.  <br/>  Crie seus usuários com endereços de email em seu domínio personalizado.  <br/> |
|Transferir dados de sua assinatura antiga para a nova assinatura.  <br/> | Entre em ambas as contas em janelas de navegador separadas:  <br/>  Clique com o botão direito do mouse no ícone do Internet Explorer e abra duas janelas do navegador InPrivate. Você pode usar credenciais diferentes nas duas janelas para entrar em ambas as contas.  <br/> [Transferir configurações administrativas entre assinaturas](#email) <br/> [Transferir dados e estrutura de site de equipe](#transfer-team-site-structure-and-data) <br/> [Transferir um site público entre assinaturas](#transfer-a-public-website-between-subscriptions) <br/> [Transferir configurações administrativas entre assinaturas](#email) <br/> |
|Cancele a assinatura para o plano que você concluiu chamando o suporte da Microsoft para o Microsoft 365.  <br/> | Verifique se a nova assinatura está funcionando e se todos os dados foram transferidos.  <br/>  [Entre em contato com o suporte ao cliente](../contact-support-for-business-products.md) para cancelar sua assinatura antiga.  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>Transferir configurações administrativas entre assinaturas

Vá para as páginas a seguir em cada conta e configure a nova conta com base nas configurações da conta antiga.
  
Se você estiver transferindo dados do Microsoft 365 para a Microsoft 365 Midsize Business ou Microsoft 365 Enterprise, as páginas de Administração serão estruturadas de forma diferente. Assista a um [vídeo: Apresentando o Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365/admin/)e vá para os seguintes locais para ver as configurações de administração.
  
Para o Microsoft 365 Enterprise e o Microsoft 365 Midsize Business:
  
|**Localização**|**Objetivo**|
|:-----|:-----|
|**Administração** \> **Microsoft 365** \> **Configurações de serviço** <br/> |Selecione cada guia para configurações de email, sites, Lync, software do usuário, senhas, Comunidade, gerenciamento de direitos e dispositivos móveis.  <br/> |
|**Administração** \> **Exchange** <br/> | Configurações do Exchange Online  <br/> |
|**Administração** \> **SharePoint** <br/> | Configurações do SharePoint Online  <br/> |
|**Administração** \> **Skype for Business** <br/> |Configurações adicionais do Skype for Business  <br/> |

Para o Microsoft 365 Small Business
  
|**Localização**|**Objetivo**|
|:-----|:-----|
|**Administração** \> **Gerenciar configurações de toda a organização** <br/> |Configurações administrativas  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>Transferir um site público entre assinaturas

Se você tiver um site público hospedado no Microsoft 365, você precisa salvá-lo e recriá-lo em sua nova assinatura.
  
> [!NOTE]
> Se seu site público estiver hospedado em um provedor de Hospedagem de DNS, nenhuma alteração será necessária. Ele não será afetado pela transição.
  
Para salvar um conteúdo de lista ou biblioteca de documentos de um ambiente do SharePoint Online para compartilhamentos de arquivos ou para um computador local, confira [migração manual do conteúdo do SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=402910).
  
> [!NOTE]
> O aplicativo de migração de site público não pode transferir dados para uma assinatura diferente.
  
## <a name="transfer-team-site-structure-and-data"></a>Transferir dados e estrutura de site de equipe

Há várias maneiras de salvar ou transferir dados de site de equipe:
  
- Você pode salvar o site antigo como um modelo e importar o modelo para o novo site.

- Para transferir documentos, primeiro recrie manualmente sua hierarquia no novo site. Em seguida, você pode abrir os dois sites de equipe do SharePoint ao mesmo tempo, abrir as bibliotecas de documentos com o Windows Explorer e copiar e colar os documentos. Veja [vídeo: copiar ou mover arquivos de biblioteca usando abrir com Explorer](https://support.office.com/article/where-to-store-files-c7c20284-bc94-47f4-9728-d28e9daf0790).

- Para transferir dados de lista, salve um [modelo de lista](https://support.microsoft.com/en-us/office/manage-list-templates-c3884ad1-bc49-44b8-b3d6-3bc6a01eb393)e use o modelo salvo para recriar a lista no novo site.

- Para salvar um conteúdo de lista ou biblioteca de documentos de um ambiente do SharePoint Online (OneDrive for Business ou sites de equipe) em compartilhamentos de arquivos ou em um computador local, confira [informações sobre a migração manual do conteúdo do SharePoint Online](https://support.microsoft.com/kb/2783484).

## <a name="transfer-users-data-between-subscriptions"></a>Transferir dados de usuários entre assinaturas

### <a name="email"></a>Email:

Solicitar que os usuários [movam seus emails, contatos, tarefas e informações de calendário](https://support.office.com/article/0996ece3-57c6-49bc-977b-0d1892e2aacc.aspx) após a configuração da nova assinatura. Eles podem acessar seus emails antigos usando o nome de usuário inicial, como sue@contoso.onmicrosoft.com.
  
### <a name="onedrive-for-business-data"></a>Dados do OneDrive for Business:

Peça aos usuários para copiar/sincronizar [o conteúdo do onedrive for Business para seu computador](https://support.office.com/article/59b1de2b-519e-4d3a-8f45-51647cf291cd.aspx)e adicioná-lo novamente à nova assinatura.
