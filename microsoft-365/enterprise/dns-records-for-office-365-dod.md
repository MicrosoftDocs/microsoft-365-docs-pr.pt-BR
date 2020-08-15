---
title: Registros DNS para Office 365 DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Resumo: registros DNS do Office 365 DoD'
hideEdit: true
ms.openlocfilehash: 656fb5aff3365dfb5f975f7d3ad1c222b36e1e56
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687133"
---
# <a name="dns-records-for-office-365-dod"></a>Registros DNS para Office 365 DoD

*Este artigo se aplica ao Office 365 DoD e à Microsoft 365 DoD*

Como parte da integração com o Office 365 DoD, você precisará adicionar seus domínios SMTP e SIP ao seu locatário de serviços online.  Você fará isso usando o cmdlet New-MsolDomain no PowerShell do Azure AD ou usar o [portal do Azure governamental](https://portal.azure.us) para iniciar o processo de adicionar o domínio e provar a propriedade.

Depois que você tiver seus domínios adicionados ao seu locatário e validado, use as orientações a seguir para adicionar os registros DNS apropriados para os serviços abaixo.  Talvez seja necessário modificar a tabela abaixo para se adequar às necessidades da sua organização em relação ao (s) registro (s) MX de entrada e a qualquer registro de descoberta automática do Exchange existente.  É altamente recomendável coordenar esses registros DNS com sua equipe de mensagens para evitar qualquer interrupção ou entrega incorreta de emails.

## <a name="exchange-online"></a>Exchange Online

| Tipo | Prioridade | Nome do host | Aponta para o endereço ou o valor | TTL |
| --- | --- | --- | --- | --- |
| MX | ,0 | @ | *Tenant*. mail.Protection.office365.us (veja a seguir os detalhes adicionais) | 1 Hour |
| TXT | - | @ | v = spf1 inclui include. Protection. office365. us-all | 1 hora |
| CNAME | - | autodiscover | autodiscover-dod.office365.us | 1 Hour |

### <a name="exchange-autodiscover-record"></a>Registro de descoberta automática do Exchange

Se você tiver o Exchange Server local, recomendamos que você saia do registro existente enquanto migra para o Exchange Online e atualize esse registro depois de concluir a migração.

### <a name="exchange-online-mx-record"></a>Registro MX do Exchange Online

O valor do registro MX para seus domínios aceitos segue um formato padrão, conforme observado acima: *Tenant*. mail.Protection.office365.us, substituindo o *locatário* pela primeira parte do nome do locatário padrão.

Por exemplo, se o nome do seu locatário for contoso.onmicrosoft.us, você usaria **contoso.mail.Protection.office365.us** como o valor para o seu registro MX.

## <a name="skype-for-business-online"></a>Skype for Business Online

### <a name="cname-records"></a>Registros CNAME

| Tipo | Nome do host | Aponta para o endereço ou o valor | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.dod.skypeforbusiness.us | 1 hora |
| CNAME | lyncdiscover | webdir.online.dod.skypeforbusiness.us | 1 Hour | 

### <a name="srv-records"></a>Registros SRV

| Tipo | Serviço | Protocolo | Porta | Peso | Priority | Nome | Target | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_TLS | 443 | 1 | 100 | @ | sipdir.online.dod.skypeforbusiness.us | 1 hora |
| SRV | \_sipfederationtls | \_TCP | 5061 | 1 | 100 | @ | sipfed.online.dod.skypeforbusiness.us | 1 Hour |

## <a name="additional-dns-records"></a>Registros DNS adicionais

> [!IMPORTANT]
> Se você tiver um registro CNAME *msoID* existente na sua zona DNS, você deve **remover** o registro do DNS neste momento.  O registro msoID é incompatível com aplicativos corporativos da Microsoft 365 *(anteriormente chamado Office 365 ProPlus)* e impedirá a ativação do sucesso.
