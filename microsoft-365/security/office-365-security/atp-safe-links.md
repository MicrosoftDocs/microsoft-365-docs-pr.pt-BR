---
title: Links seguros da ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: Neste artigo, você aprenderá a usar os links seguros para proteger sua organização contra phishing e outros ataques.
ms.openlocfilehash: 3dfa4016b34f430a260c9af4be2ed0c4126dea34
ms.sourcegitcommit: 4ce28ad4d17d336106c1720d65349f19f9e90e04
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44294224"
---
# <a name="atp-safe-links"></a>Links seguros da ATP

## <a name="overview-of-office-365-atp-safe-links"></a>Visão geral dos links seguros de ATP do Office 365

> [!IMPORTANT]
> Este artigo destina-se aos clientes corporativos que têm a [Proteção Avançada contra Ameaças do Office 365](office-365-atp.md). Se você estiver usando o Outlook.com, a família Microsoft 365 ou o Microsoft 365 Personal e estiver procurando informações sobre links seguros no Outlook, consulte [Advanced Outlook.com Security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).

O Office 365 ATP Safe links (parte do [office 365 proteção avançada contra ameaças](office-365-atp.md)) pode ajudar a proteger sua organização fornecendo a verificação de horário de clique de endereços da Web (URLs) em [mensagens de email](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-email) e [documentos do Office](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-office-documents). A proteção é definida por meio das [políticas de links seguros de ATP](set-up-atp-safe-links-policies.md) definidas pela equipe de segurança do Microsoft 365.
  
Depois que as políticas de links seguros de ATP estiverem vigentes, administradores globais, administradores de segurança e leitores de segurança poderão [exibir relatórios de proteção avançada contra ameaças](view-reports-for-atp.md). As informações nesses relatórios podem ajudar sua equipe de segurança a realizar mais etapas para proteger sua organização ou Pesquisar incidentes de segurança.

À medida que [novos recursos são adicionados à ATP](office-365-atp.md#new-features-in-office-365-atp), a equipe de segurança do Microsoft 365 pode adicionar ou editar [as políticas de links seguros de ATP](set-up-atp-safe-links-policies.md)da sua organização. Além disso, você pode notar alterações e melhorias, como nossas [páginas de aviso](atp-safe-links-warning-pages.md) recentemente revisadas e renderização de link nativo no Outlook (introduzidos no Microsoft 365 Apps for enterprise versão 1809).
         
## <a name="how-to-get-atp-safe-links-protection"></a>Como obter proteção de links de segurança ATP

**Primeiro, certifique-se de que sua assinatura inclua a [proteção avançada contra ameaças do Office 365](office-365-atp.md) ** Plano 1 ou plano 2. O Office 365 ATP está incluído em inscrições, como [o microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [o Microsoft 365 Business Premium](https://www.microsoft.com/microsoft-365/business), o Office 365 Enterprise E5, o Office 365 Education a5, etc. Se sua organização tiver uma assinatura do Microsoft 365 que não inclua o Office 365 ATP, você poderá comprar ATP como um complemento. Para saber mais, veja os seguintes recursos: 

- [Preços e planos para proteção avançada contra ameaças do Office 365](https://products.office.com/exchange/advance-threat-protection)

- [Descrição do Serviço da Proteção Avançada contra Ameaças do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 
  
**Em seguida, verifique se as políticas de links seguros de ATP estão definidas**. (Confira [configurar as políticas de links seguros de ATP do Office 365](set-up-atp-safe-links-policies.md).) Os recursos de links seguros de ATP estão ativos quando:
  
- As políticas de links seguros de ATP são configuradas para email e documentos do Office. (Confira [Configurar políticas de links seguros de ATP](set-up-atp-safe-links-policies.md).)

- Os aplicativos cliente do Microsoft 365 estão configurados para usar a autenticação moderna (isso é para proteção de links de segurança ATP em documentos do Office). (Consulte [autenticação moderna do Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).) 
    
- Os usuários entraram usando sua conta corporativa ou de estudante. (Consulte [entrar no Office ou no office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)
    
- O email da sua organização passa pela proteção do Exchange Online.  

**Verifique também se você tem as permissões necessárias**. Para definir (ou editar) políticas ATP, você deve ter uma função apropriada atribuída. Alguns exemplos são descritos na tabela a seguir:

|Role  |Onde/como a atribuição  |
|---------|---------|
|administrador global |Por padrão, a pessoa que se inscreve para comprar a Microsoft 365 é um administrador global. (Consulte [about Microsoft 365 admin Roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para saber mais.)         |
|Administrador de Segurança |Centro de administração do Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Gerenciamento de Organização do Exchange Online |Centro de administração do Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>ou <br>  Cmdlets do PowerShell (consulte [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>Como garantir que a proteção de links seguros de ATP esteja em vigor

Como administrador global ou administrador de segurança, revise regularmente as [políticas de links seguros de ATP](set-up-atp-safe-links-policies.md) . As políticas de links seguros de ATP determinam se a proteção se aplica somente aos hiperlinks em mensagens de email ou também às URLs em documentos do Office.

Após as políticas de links seguros de ATP serem aplicadas, a equipe de segurança da sua organização pode ver como a proteção de links de segurança ATP está funcionando para sua organização é [exibindo os relatórios de proteção avançada contra ameaças](view-reports-for-atp.md). 

## <a name="example-scenarios"></a>Exemplos de cenários
  
A tabela a seguir descreve alguns exemplos de cenários em que a proteção de links de segurança ATP pode ou não estar em vigor. (Em todos esses casos, supomos que a organização tem o Office 365 Enterprise e5.)
  
|**Cenário de exemplo**|**A proteção de links de segurança ATP é aplicada neste caso?**|
|:-----|:-----|
|Jean é membro de um grupo que tem políticas de links seguros de ATP abrangendo URLs em email e documentos do Office. Jean abre uma apresentação do PowerPoint que alguém enviou e, em seguida, clica em uma URL na apresentação.  <br/> |Sim. As políticas de links seguros de ATP definidas aplicam-se ao grupo de Jean, emails de Jean e documentos do Word, Excel, PowerPoint ou Visio que Jean abre, contanto que Jean esteja conectado e usando o Microsoft 365 aplicativos para empresas em dispositivos Windows, iOS ou Android.  <br/> |
|Na organização de Carla, nenhum administrador global ou de segurança definiu nenhuma política de links seguros de ATP ainda. Chris recebe um email que contém uma URL para um site mal-intencionado. Carla não está ciente de que a URL é mal-intencionada e clica no link.  <br/> |Não. A política padrão que cobre URLs para todas as pessoas na organização deve ser definida para que a proteção seja estabelecida.  <br/> |
|Na organização do Luigi, nenhum administrador global ou de segurança definiu ou editou nenhuma política de links seguros de ATP. Pat abre um documento do Word e clica em uma URL no arquivo.  <br/> |Não. Uma política que inclui documentos do Office deve ser definida para que a proteção seja realizada. Confira [Configurar políticas de links seguros de ATP no Office 365](set-up-atp-safe-links-policies.md).  <br/> |
|A organização de Lee tem uma política de links seguros ATP que está `https://tailspintoys.com` listada como um site bloqueado. Lee recebe uma mensagem de email que contém uma URL para `https://tailspintoys.com/aboutus/trythispage` . Lee clica na URL.  <br/> |Ele depende se todo o site e todas as suas subpáginas estão incluídos na lista de URLs bloqueadas. Confira [Configurar uma lista de URLs bloqueadas personalizada usando os links seguros de ATP](set-up-a-custom-blocked-urls-list-atp.md).  <br/> |
|Jaime, colega de Jean, envia um email para Jean, não sabendo que o email contém uma URL mal-intencionada.  <br/> |Isso depende se as políticas de links seguros de ATP estão definidas para emails enviados dentro da organização. Confira [Configurar políticas de links seguros de ATP no Office 365](set-up-atp-safe-links-policies.md).  <br/> |


  

