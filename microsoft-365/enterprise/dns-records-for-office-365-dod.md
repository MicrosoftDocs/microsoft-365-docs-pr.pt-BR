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
description: 'Resumo: registros DNS para Office 365 DoD'
hideEdit: true
ms.openlocfilehash: 656fb5aff3365dfb5f975f7d3ad1c222b36e1e56
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687133"
---
# <a name="dns-records-for-office-365-dod"></a>Registros DNS para Office 365 DoD

*Este artigo se aplica ao Office 365 DoD e Microsoft 365 DoD*

Como parte da integração para Office 365 DoD, você precisará adicionar seus domínios SMTP e SIP ao seu locatário de Serviços Online.  Você fará isso usando o cmdlet New-MsolDomain no Azure AD PowerShell ou usará o Portal do Governo do [Azure](https://portal.azure.us) para iniciar o processo de adição do domínio e da prova de propriedade.

Depois de ter seus domínios adicionados ao locatário e validados, use as seguintes diretrizes para adicionar os registros DNS apropriados para os serviços abaixo.  Talvez seja necessário modificar Exchange tabela abaixo para se ajustar às necessidades da sua organização em relação aos registros MX de entrada e quaisquer registros de Descoberta Automática existentes que você tenha.  É recomendável coordenar esses registros DNS com sua equipe de mensagens para evitar paralisações ou entregas incorretamente de emails.

## <a name="exchange-online"></a>Exchange Online

| Tipo | Prioridade | Nome do host | Aponta para o endereço ou para o valor | TTL |
| --- | --- | --- | --- | --- |
| MX | 0 | @ | *tenant*.mail.protection.office365.us (consulte abaixo para obter detalhes adicionais) | 1 Hour |
| TXT | - | @ | v=spf1 include:spf.protection.office365.us -all | 1 hora |
| CNAME | - | autodiscover | autodiscover-dod.office365.us | 1 Hour |

### <a name="exchange-autodiscover-record"></a>Exchange Registro de Descoberta Automática

Se você tiver Exchange Server local, recomendamos deixar seu registro existente no local enquanto migra para Exchange Online e atualizar esse registro depois de concluir a migração.

### <a name="exchange-online-mx-record"></a>Exchange Online Registro MX

O valor do registro MX para seus domínios aceitos segue um formato padrão  conforme mencionado acima: *tenant*.mail.protection.office365.us, substituindo locatário pela primeira parte do nome de locatário padrão.

Por exemplo, se seu nome de locatário contoso.onmicrosoft.us, você usaria contoso.mail.protection.office365.us **como** o valor para seu registro MX.

## <a name="skype-for-business-online"></a>Skype for Business Online

### <a name="cname-records"></a>Registros CNAME

| Tipo | Nome do host | Aponta para o endereço ou para o valor | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.dod.skypeforbusiness.us | 1 hora |
| CNAME | lyncdiscover | webdir.online.dod.skypeforbusiness.us | 1 Hour | 

### <a name="srv-records"></a>Registros SRV

| Tipo | Serviço | Protocolo | Porta | Peso | Prioridade | Nome | Target | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_tls | 443 | 1 | 100 | @ | sipdir.online.dod.skypeforbusiness.us | 1 hora |
| SRV | \_sipfederationtls | \_tcp | 5061 | 1 | 100 | @ | sipfed.online.dod.skypeforbusiness.us | 1 Hour |

## <a name="additional-dns-records"></a>Registros DNS adicionais

> [!IMPORTANT]
> Se você tiver um registro CNAME *msoid* existente em sua zona DNS, deverá **remover** o registro do DNS neste momento.  O registro msoid é incompatível com Microsoft 365 Enterprise Apps *(anteriormente Office 365 ProPlus)* e impedirá que a ativação seja bem-sucedida.
