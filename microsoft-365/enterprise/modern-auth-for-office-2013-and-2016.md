---
title: Como funciona a autenticação moderna para aplicativos cliente do Office 2013 e do Office 2016
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/1/2017
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- GMA150
- GPA150
- GEA150
- BCS160
ms.assetid: e4c45989-4b1a-462e-a81b-2a13191cf517
ms.collection:
- M365-security-compliance
description: Saiba como os recursos modernos de autenticação do Microsoft 365 funcionam de forma diferente para aplicativos cliente do Office 2013 e 2016.
ms.openlocfilehash: 3e402f5786a72f3703ab4a1a77df688176f7de61
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921661"
---
# <a name="how-modern-authentication-works-for-office-2013-office-2016-and-office-2019-client-apps"></a>Como funciona a autenticação moderna para aplicativos cliente do Office 2013, Office 2016 e Office 2019

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Leia este artigo para saber como aplicativos cliente do Office 2013, Office 2016 e Office 2019 usam recursos modernos de autenticação com base na configuração de autenticação no locatário do Microsoft 365 para Exchange Online, SharePoint Online e Skype for Business Online.

> [!NOTE]
> Aplicativos cliente herddos, como o Office 2010 e o Office para Mac 2011, não suportam autenticação moderna e só podem ser usados com autenticação básica.

## <a name="availability-of-modern-authentication-for-microsoft-365-services"></a>Disponibilidade de autenticação moderna para serviços do Microsoft 365

Para os serviços do Microsoft 365, o estado padrão da autenticação moderna é:
  
- Ligado **para** o Exchange Online por padrão. Consulte [Habilitar ou desabilitar a autenticação moderna no Exchange Online](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) para desativá-la ou ativar. 
    
- Ligado **para** o SharePoint Online por padrão. 
    
- Ligado **para** o Skype for Business Online por padrão. Consulte [Enable Skype for Business Online for modern authentication ](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)to turn it off or on.

> [!NOTE]
> Para locatários criados **antes** 1º de agosto de 2017, a autenticação moderna é **desativada** por padrão para o Exchange Online e o Skype for Business Online.
    
## <a name="sign-in-behavior-of-office-client-apps"></a>Comportamento de entrada de aplicativos cliente do Office

Os aplicativos cliente do Office 2013 suportam a autenticação herdada por padrão. Legado significa que eles suportam o Assistente de Login do Microsoft Online ou a autenticação básica. Para que esses clientes usem recursos modernos de autenticação, o cliente Windows deve ter as chaves do Registro definidas. Para obter instruções, consulte [Enable Modern Authentication for Office 2013 on Windows devices](https://support.office.com/article/7dc1c01a-090f-4971-9677-f1b192d6c910).

Para habilitar a autenticação moderna para os dispositivos com Windows (por exemplo em laptops e tablets), que têm o Microsoft Office 2013 instalado, você precisa definir as seguintes chaves do Registro. As teclas precisam ser definidas em cada dispositivo que você deseja habilitar para autenticação moderna:
  
|**Chave do Registro**|**Tipo**|**Valor** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
  
Leia [Como usar a Autenticação Moderna (ADAL) com o Skype for Business](./hybrid-modern-auth-overview.md) para saber como funciona com o Skype for Business. 
  
Os clientes do Office 2016 e do Office 2019 suportam a autenticação moderna por padrão, e nenhuma ação é necessária para o cliente usar esses novos fluxos. No entanto, a ação explícita é necessária para usar a autenticação herdado.
  
Clique nos links abaixo para ver como a autenticação de cliente do Office 2013, Office 2016 e Office 2019 funciona com os serviços do Microsoft 365, dependendo se a autenticação moderna está ou não conexões.
  
- [Exchange Online](modern-auth-for-office-2013-and-2016.md#BK_EchangeOnline)
    
- [SharePoint Online](modern-auth-for-office-2013-and-2016.md#BK_SharePointOnline)
    
- [Skype for Business Online](modern-auth-for-office-2013-and-2016.md#BK_SFBO)
    
<a name="BK_EchangeOnline"> </a>
### <a name="exchange-online"></a>Exchange Online

A tabela a seguir descreve o comportamento de autenticação para aplicativos cliente do Office 2013, Office 2016 e Office 2019 quando eles se conectam ao Exchange Online com ou sem autenticação moderna.
  
|Versão do aplicativo cliente do Office***|Chave do Registro presente?****|Autenticação moderna em?****|Comportamento de autenticação com autenticação moderna ligado para o locatário (padrão)****|Comportamento de autenticação com autenticação moderna desligada para o locatário****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Não <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Sim  <br/> |Força a autenticação moderna no Outlook 2013, 2016 ou 2019. <br/> [Mais informações](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Força a autenticação moderna dentro do cliente do Outlook.<br/> |
|Office 2019  <br/> |Não, ou EnableADAL = 1  <br/> |Sim  <br/> |A autenticação moderna é tentada primeiro. Se o servidor recusar uma conexão de autenticação moderna, a autenticação básica será usada. O servidor recusa a autenticação moderna quando o locatário não está habilitado.  <br/> |A autenticação moderna é tentada primeiro. Se o servidor recusar uma conexão de autenticação moderna, a autenticação básica será usada. O servidor recusa a autenticação moderna quando o locatário não está habilitado.  <br/> |
|Office 2019  <br/> |Sim, EnableADAL = 1  <br/> |Sim  <br/> |A autenticação moderna é tentada primeiro. Se o servidor recusar uma conexão de autenticação moderna, a autenticação básica será usada. O servidor recusa a autenticação moderna quando o locatário não está habilitado.  <br/> |A autenticação moderna é tentada primeiro. Se o servidor recusar uma conexão de autenticação moderna, a autenticação básica será usada. O servidor recusa a autenticação moderna quando o locatário não está habilitado.  <br/> |
|Office 2019  <br/> |Sim, EnableADAL=0  <br/> |Não  <br/> |Autenticação básica  <br/> |Autenticação básica  <br/> |
|Office 2016  <br/> |Não <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Sim  <br/> |Força a autenticação moderna em 2013, 2016 ou 2019. <br/> [Mais informações](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Força a autenticação moderna dentro do cliente do Outlook.<br/> |
|Office 2016  <br/> |Não, ou EnableADAL = 1  <br/> |Sim  <br/> |A autenticação moderna é tentada primeiro. Se o servidor recusar uma conexão de autenticação moderna, a autenticação básica será usada. O servidor recusa a autenticação moderna quando o locatário não está habilitado.  <br/> |A autenticação moderna é tentada primeiro. Se o servidor recusar uma conexão de autenticação moderna, a autenticação básica será usada. O servidor recusa a autenticação moderna quando o locatário não está habilitado.  <br/> |
|Office 2016  <br/> |Sim, EnableADAL = 1  <br/> |Sim  <br/> |A autenticação moderna é tentada primeiro. Se o servidor recusar uma conexão de autenticação moderna, a autenticação básica será usada. O servidor recusa a autenticação moderna quando o locatário não está habilitado.  <br/> |A autenticação moderna é tentada primeiro. Se o servidor recusar uma conexão de autenticação moderna, a autenticação básica será usada. O servidor recusa a autenticação moderna quando o locatário não está habilitado.  <br/> |
|Office 2016  <br/> |Sim, EnableADAL=0  <br/> |Não  <br/> |Autenticação básica  <br/> |Autenticação básica  <br/> |
|Office 2013  <br/> |Não  <br/> |Não  <br/> |Autenticação básica  <br/> |Autenticação básica  <br/> |
|Office 2013  <br/> |Sim, EnableADAL = 1  <br/> |Sim  <br/> |A autenticação moderna é tentada primeiro. Se o servidor recusar uma conexão de autenticação moderna, a autenticação básica será usada. O servidor recusa a autenticação moderna quando o locatário não está habilitado.  <br/> |A autenticação moderna é tentada primeiro. Se o servidor recusar uma conexão de autenticação moderna, a autenticação básica será usada. O servidor recusa a autenticação moderna quando o locatário não está habilitado.  <br/> |
   
<a name="BK_SharePointOnline"> </a>
### <a name="sharepoint-online"></a>SharePoint Online

A tabela a seguir descreve o comportamento de autenticação para aplicativos cliente do Office 2013, Office 2016 e Office 2019 quando eles se conectam ao SharePoint Online com ou sem autenticação moderna.
  
|Versão do aplicativo cliente do Office***|Chave do Registro presente?****|Autenticação moderna em?****|Comportamento de autenticação com autenticação moderna ligado para o locatário (padrão)****|Comportamento de autenticação com autenticação moderna desligada para o locatário****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Não, ou EnableADAL = 1  <br/> |Sim  <br/> |Somente autenticação moderna.  <br/> |Falha na conexão.  <br/> |
|Office 2019  <br/> |Sim, EnableADAL = 1  <br/> |Sim  <br/> |Somente autenticação moderna.  <br/> |Falha na conexão.  <br/> |
|Office 2019  <br/> |Sim, EnableADAL = 0  <br/> |Não  <br/> |Somente Assistente de Login do Microsoft Online.  <br/> |Somente Assistente de Login do Microsoft Online.  <br/> |
|Office 2016  <br/> |Não, ou EnableADAL = 1  <br/> |Sim  <br/> |Somente autenticação moderna.  <br/> |Falha na conexão.  <br/> |
|Office 2016  <br/> |Sim, EnableADAL = 1  <br/> |Sim  <br/> |Somente autenticação moderna.  <br/> |Falha na conexão.  <br/> |
|Office 2016  <br/> |Sim, EnableADAL = 0  <br/> |Não  <br/> |Somente Assistente de Login do Microsoft Online.  <br/> |Somente Assistente de Login do Microsoft Online.  <br/> |
|Office 2013  <br/> |Não  <br/> |Não  <br/> |Somente Assistente de Login do Microsoft Online.  <br/> |Somente Assistente de Login do Microsoft Online.  <br/> |
|Office 2013  <br/> |Sim, EnableADAL = 1  <br/> |Sim  <br/> |Somente autenticação moderna.  <br/> |Falha na conexão.  <br/> |
   
### <a name="skype-for-business-online"></a>Skype for Business Online
<a name="BK_SFBO"> </a>

A tabela a seguir descreve o comportamento de autenticação para aplicativos cliente do Office 2013, Office 2016 e Office 2019 quando eles se conectam ao Skype for Business Online com ou sem autenticação moderna.
  
|Versão do aplicativo cliente do Office***|Chave do Registro presente?****|Autenticação moderna em?****|Comportamento de autenticação com autenticação moderna ligado para o locatário****|Comportamento de autenticação com autenticação moderna desligada para o locatário (padrão)****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Não, ou EnableADAL = 1  <br/> |Sim  <br/> |A autenticação moderna é tentada primeiro. Se o servidor recusar uma conexão de autenticação moderna, o Assistente de Login do Microsoft Online será usado. O servidor recusa a autenticação moderna quando os locatários do Skype for Business Online não estão habilitados.  <br/> |A autenticação moderna é tentada primeiro. Se o servidor recusar uma conexão de autenticação moderna, o Assistente de Login do Microsoft Online será usado. O servidor recusa a autenticação moderna quando os locatários do Skype for Business Online não estão habilitados.  <br/> |
|Office 2019  <br/> |Sim, EnableADAL = 1  <br/> |Sim  <br/> |A autenticação moderna é tentada primeiro. Se o servidor recusar uma conexão de autenticação moderna, o Assistente de Login do Microsoft Online será usado. O servidor recusa a autenticação moderna quando os locatários do Skype for Business Online não estão habilitados.  <br/> |A autenticação moderna é tentada primeiro. Se o servidor recusar uma conexão de autenticação moderna, o Assistente de Login do Microsoft Online será usado. O servidor recusa a autenticação moderna quando os locatários do Skype for Business Online não estão habilitados.  <br/> |
|Office 2019  <br/> |Sim, EnableADAL = 0  <br/> |Não  <br/> |Somente Assistente de Login do Microsoft Online.  <br/> |Somente Assistente de Login do Microsoft Online.  <br/> |
|Office 2016  <br/> |Não, ou EnableADAL = 1  <br/> |Sim  <br/> |A autenticação moderna é tentada primeiro. Se o servidor recusar uma conexão de autenticação moderna, o Assistente de Login do Microsoft Online será usado. O servidor recusa a autenticação moderna quando os locatários do Skype for Business Online não estão habilitados.  <br/> |A autenticação moderna é tentada primeiro. Se o servidor recusar uma conexão de autenticação moderna, o Assistente de Login do Microsoft Online será usado. O servidor recusa a autenticação moderna quando os locatários do Skype for Business Online não estão habilitados.  <br/> |
|Office 2016  <br/> |Sim, EnableADAL = 1  <br/> |Sim  <br/> |A autenticação moderna é tentada primeiro. Se o servidor recusar uma conexão de autenticação moderna, o Assistente de Login do Microsoft Online será usado. O servidor recusa a autenticação moderna quando os locatários do Skype for Business Online não estão habilitados.  <br/> |A autenticação moderna é tentada primeiro. Se o servidor recusar uma conexão de autenticação moderna, o Assistente de Login do Microsoft Online será usado. O servidor recusa a autenticação moderna quando os locatários do Skype for Business Online não estão habilitados.  <br/> |
|Office 2016  <br/> |Sim, EnableADAL = 0  <br/> |Não  <br/> |Somente Assistente de Login do Microsoft Online.  <br/> |Somente Assistente de Login do Microsoft Online.  <br/> |
|Office 2013  <br/> |Não  <br/> |Não  <br/> |Somente Assistente de Login do Microsoft Online.  <br/> |Somente Assistente de Login do Microsoft Online.  <br/> |
|Office 2013  <br/> |Sim, EnableADAL = 1  <br/> |Sim  <br/> |A autenticação moderna é tentada primeiro. Se o servidor recusar uma conexão de autenticação moderna, o Assistente de Login do Microsoft Online será usado. O servidor recusa a autenticação moderna quando os locatários do Skype for Business Online não estão habilitados.  <br/> |Somente Assistente de Login do Microsoft Online.  <br/> |
   
## <a name="see-also"></a>Confira também

[Habilitar a Autenticação Moderna do Office 2013 em dispositivos Windows.](../admin/security-and-compliance/enable-modern-authentication.md)

[Autenticação multifator para Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)

[Entrar no Microsoft 365 com autenticação multifa factor](https://support.microsoft.com/office/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)