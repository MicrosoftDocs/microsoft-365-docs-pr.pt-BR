---
title: Transferir dados manualmente entre duas contas
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: Encontre como transferir dados manualmente entre duas contas do Microsoft 365 quando você alterou o plano ou o nome da empresa ou combinou várias assinaturas em uma.
ms.openlocfilehash: b240ffbbdbfb6ed7d20a9ead9b1ee90a3af4570d
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023828"
---
# <a name="transfer-data-manually-between-two-accounts"></a>Transferir dados manualmente entre duas contas

Prepare-se para arregaçar as mangas e bloquear uma parte do tempo em seu calendário: transferir dados entre duas contas do Microsoft 365 é um processo manual, complicado e demorado. Esse não é um processo automatizado ou suportado. Vamos começar.
  
> [!CAUTION]
> Haverá tempo inotivo durante o processo em que o email, o Skype for Business e um site público hospedado no Microsoft 365 não funcionarão. Os usuários receberão novos nomes de usuário e senhas e precisarão redefinir o Outlook.

**Somente transfira dados manualmente usando as instruções neste tópico se uma das seguintes aplica-se:**
  
- Você precisa mudar para um plano em uma família de serviços diferente.

- O nome da sua empresa foi alterado e você decidiu criar uma nova assinatura e migrar seus dados porque deseja usar nomes de domínio iniciais diferentes.

- Você precisa combinar várias assinaturas em uma nova.

> [!IMPORTANT]
> Se você [](../../commerce/subscriptions/switch-to-a-different-plan.md) precisar alterar seu plano de assinatura e pode usar o assistente de planos de Opção ou se precisar transferir para um novo plano de assinatura na mesma família de assinaturas, mesmo quando o assistente de planos de Opção não funcionar, não será necessário transferir manualmente seus dados e não haverá tempo de insuporção.

|**Tasks**|**Steps**|
|:-----|:-----|
|Compre o plano para o que você deseja mover.  <br/> |Ao se inscrever, especifique o nome da empresa  a ser usado nos nomes de domínio iniciais: sua empresa .onmicrosoft.com,  sua empresa -public.sharepoint.com e sua *empresa* .sharepoint.com. Você precisa usar um nome  *de sua empresa*  diferente de qualquer assinatura existente.  <br/> > [!NOTE]> normalmente leva um mínimo de vários meses após cancelar uma assinatura para liberar os nomes de domínio iniciais que usam sua  *empresa*  de nossos sistemas. Mesmo que você planeje salvar todos os seus dados da sua antiga assinatura  do Microsoft 365 e cancelar essa assinatura, o valor antigo da sua empresa não estará disponível imediatamente para uso em uma nova assinatura.           |
|Remova seu domínio personalizado da sua assinatura antiga do Microsoft 365.  <br/> | Siga as [etapas necessárias antes](remove-a-domain.md) de remover um domínio para remover o nome de domínio dos endereços de email do usuário e remover registros DNS para email e Lync para o domínio personalizado. Se você hospedar seu site público no Microsoft 365, também precisará remover o registro CNAME que aponta para ele.  <br/> > [!IMPORTANT]> Depois de remover o registro MX que encaminha emails para esse domínio personalizado, os emails param de funcionar até que você tenha adicionado o domínio à sua nova conta, configurar o novo registro MX e configurar seus usuários. Quando você remove os registros DNS do Lync, o Lync para de funcionar. E depois de remover o registro CNAME que aponta para seu site público, ele não estará disponível.           [Remover o domínio](remove-a-domain.md) .  <br/> |
|Configurar seu domínio personalizado para sua nova assinatura e configurar seus usuários.  <br/> | Configurar sua nova assinatura, incluindo a criação dos registros DNS necessários para seu domínio personalizado.  <br/>  Crie seus usuários com endereços de email em seu domínio personalizado.  <br/> |
|Transfira dados da sua assinatura antiga para sua nova assinatura.  <br/> | Entre em ambas as contas em janelas separadas do navegador:  <br/>  Clique com o botão direito do mouse no ícone do navegador e abra duas janelas privadas do navegador. Você pode usar credenciais diferentes nas duas janelas para entrar em ambas as contas.  <br/> [Transferir configurações administrativas entre assinaturas](#email) <br/> [Transferir dados e estrutura de site de equipe](#transfer-team-site-structure-and-data) <br/> [Transferir um site público entre assinaturas](#transfer-a-public-website-between-subscriptions) <br/> [Transferir configurações administrativas entre assinaturas](#email) <br/> |
|Cancele a assinatura do plano com o que você terminou chamando o Suporte da Microsoft para o Microsoft 365.  <br/> | Verifique se sua nova assinatura está funcionando e se todos os dados foram transferidos.  <br/>  [Contate o suporte ao cliente](../contact-support-for-business-products.md) para cancelar sua assinatura antiga.  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>Transferir configurações administrativas entre assinaturas

Vá para as páginas a seguir em cada conta e configurar a nova conta com base nas configurações da conta antiga.
  
Se você estiver transferindo dados do Microsoft 365 para o Microsoft 365 Midsize Business ou o Microsoft 365 Enterprise, as páginas de administração serão estruturadas de forma diferente. Assista a [um vídeo: apresentando o Microsoft 365 Enterprise](../index.yml)e vá para os seguintes locais para ver as configurações de administrador.
  
Para o Microsoft 365 Enterprise e o Microsoft 365 Midsize Business:
  
|**Localização**|**Objetivo**|
|:-----|:-----|
|**Admin** \> **Microsoft 365** \> **Configurações de serviço** <br/> |Selecione cada guia para configurações de email, sites, Lync, software de usuário, senhas, comunidade, gerenciamento de direitos e celular.  <br/> |
|**Admin** \> **Exchange** <br/> | Configurações do Exchange Online  <br/> |
|**Admin** \> **SharePoint** <br/> | Configurações do SharePoint Online  <br/> |
|**Admin** \> **Skype for Business** <br/> |Configurações adicionais do Skype for Business  <br/> |

Para o Microsoft 365 Small Business
  
|**Localização**|**Objetivo**|
|:-----|:-----|
|**Admin** \> **Gerenciar configurações em toda a organização** <br/> |Configurações administrativas  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>Transferir um site público entre assinaturas

Se você tiver um site público hospedado no Microsoft 365, será necessário salvá-lo e re-criar na nova assinatura.
  
> [!NOTE]
> Se seu site público estiver hospedado em um provedor de hospedagem DNS, nenhuma alteração será necessária. Ele não será afetado pela transição.
  
Para salvar uma biblioteca de documentos ou conteúdo de lista de um ambiente do SharePoint Online para compartilhamentos de arquivos ou para um computador local, consulte Migração manual do [conteúdo do SharePoint Online.](/sharepoint/troubleshoot/migration-tool/content-manual-migration)
  
> [!NOTE]
> O aplicativo de migração de site público não pode transferir dados para uma assinatura diferente.
  
## <a name="transfer-team-site-structure-and-data"></a>Transferir dados e estrutura de site de equipe

Há várias maneiras de salvar ou transferir dados do site da equipe:
  
- Você pode salvar o site antigo como um modelo e importar o modelo para o novo site.

- Para transferir documentos, primeiro recrie manualmente sua hierarquia no novo site. Em seguida, você pode abrir os dois sites de equipe do SharePoint ao mesmo tempo, abrir bibliotecas de documentos com o Windows Explorer e copiar e colar os documentos. Consulte [Vídeo: Copie ou mova arquivos de biblioteca usando Abrir com o Explorer](../../business-video/store-files.md).

- Para transferir dados de lista, salve um modelo [de](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393)lista e use o modelo salvo para criar a lista no novo site.

- Para salvar uma biblioteca de documentos ou conteúdo de lista de um ambiente do SharePoint Online (OneDrive for Business ou sites de equipe) em compartilhamentos de arquivos ou em um computador local, consulte Informações sobre a migração manual do conteúdo [do SharePoint Online.](/sharepoint/troubleshoot/migration-tool/content-manual-migration)

## <a name="transfer-users-data-between-subscriptions"></a>Transferir dados dos usuários entre assinaturas

### <a name="email"></a>Email:

Peça aos usuários [para mover seus emails, contatos,](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) tarefas e informações de calendário depois de configurar sua nova assinatura. Eles podem chegar ao email antigo usando seu nome de usuário inicial, como sue@contoso.onmicrosoft.com.
  
### <a name="onedrive-for-business-data"></a>Dados do OneDrive For Business:

Peça que os usuários copiem/sincronizem o conteúdo do [OneDrive for Business](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd)no computador e, em seguida, adicionem-no novamente à nova assinatura.

### <a name="onenote"></a>OneNote 

Peça aos usuários [para fazer backup do OneNote](https://support.microsoft.com/office/back-up-notes-f58b34b0-611d-435e-87fa-7942a1767af4?ui=en-us&rs=en-us&ad=us) e restaurar [anotações de um backup](https://support.microsoft.com/en-us/office/restore-notes-from-a-backup-5daf9cb0-6769-4998-a5de-f044fdd0d831?ui=en-us&rs=en-us&ad=us) para suas novas assinaturas.