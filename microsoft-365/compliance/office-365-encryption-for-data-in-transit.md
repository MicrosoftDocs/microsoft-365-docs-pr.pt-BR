---
title: Criptografia para dados em trânsito
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Uma breve explicação sobre como a Microsoft criptografa dados em trânsito em seus data centers.
ms.openlocfilehash: 645294522185a631012c1654fbad96ba0a21b33e
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943300"
---
# <a name="encryption-for-data-in-transit"></a>Criptografia para dados em trânsito

Além de proteger os dados do cliente em repouso, a Microsoft usa tecnologias de criptografia para proteger os dados do cliente em trânsito. 

Os dados estão em trânsito:

- Quando uma máquina cliente se comunica com um servidor Microsoft;
- Quando um servidor Microsoft se comunica com outro servidor Microsoft; e
- Quando um servidor Microsoft se comunica com um servidor não-Microsoft (por exemplo, o Exchange Online que entrega emails para um servidor de email de terceiros).

Comunicações entre data centers entre servidores da Microsoft ocorrem sobre TLS ou IPsec, e todos os servidores voltados ao cliente negociam uma sessão segura usando TLS com máquinas clientes (por exemplo, o Exchange Online usa o TLS 1,2 com intensidade de codificação de 256 bits é usado (FIPS 140-2 Level 2 validado). (Veja [detalhes técnicos de referência sobre criptografia](technical-reference-details-about-encryption.md) para obter uma lista de conjuntos de codificação TLS compatíveis com o Office 365.) Isso se aplica aos protocolos usados por clientes como o Outlook, Skype for Business, Microsoft Teams e Outlook na Web (por exemplo, HTTP, POP3, etc.).

Os certificados públicos são emitidos pelo SSL de ti da Microsoft usando o SSLAdmin, uma ferramenta interna da Microsoft para proteger a confidencialidade das informações transmitidas. Todos os certificados emitidos pela TI da Microsoft têm um mínimo de 2048 bits de duração, e a conformidade do WebTrust requer o SSLAdmin para garantir que os certificados sejam emitidos apenas para endereços IP públicos pertencentes à Microsoft. Qualquer endereço IP que não atenda a esse critério é roteado por meio de um processo de exceção.

Todos os detalhes de implementação, como a versão do TLS que está sendo usada, se o sigilo total (FS) está habilitado, a ordem de pacotes de codificação, etc., estão disponíveis publicamente. Uma maneira de ver esses detalhes é usar um site de terceiros, como [laboratórios de Qualys SSL](https://www.ssllabs.com). Veja a seguir os links para páginas de teste automatizadas do Qualys que exibem informações sobre os seguintes serviços:

- [Portal do Office 365](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [Exchange Online](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [SharePoint Online](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [Skype for Business (SIP)](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [Skype for Business (Web)](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [Proteção do Exchange Online](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [Microsoft Teams](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

Para o Exchange Online Protection, as URLs variam de acordo com nomes de locatários; no entanto, todos os clientes podem testar o Microsoft 365 usando o **Microsoft-com.mail.Protection.Outlook.com**.
