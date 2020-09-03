---
title: Isolamento de locatário no Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Este artigo contém um resumo de como a Microsoft impõe o isolamento de locatário em serviços de nuvem, como o Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7aca35fc61d03e94225375fcf67970e13dd691c9
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332683"
---
# <a name="tenant-isolation-in-microsoft-365"></a>Isolamento de locatário no Microsoft 365

Um dos principais benefícios da computação em nuvem é o conceito de uma infraestrutura comum e compartilhada em vários clientes ao mesmo tempo, levando em economia de escala. Esse conceito é chamado *de multilocação*. A Microsoft trabalha continuamente para garantir que as arquiteturas de vários locatários de nossos serviços de nuvem suportam padrões de segurança, confidencialidade, privacidade, integridade e disponibilidade de nível empresarial.

Com base nos investimentos e na experiência significativos coletados da [computação confiável](https://www.microsoft.com/trust-center) e do [ciclo de vida de desenvolvimento de segurança](https://www.microsoft.com/securityengineering/sdl/), os serviços de nuvem da Microsoft foram criados com a suposição de que todos os locatários sejam hosts potencialmente hostil para todos os outros locatários, e implementamos medidas de segurança para impedir que as ações de um locatário afetem a segurança ou o serviço de outro locatário

As duas metas principais para manter o isolamento de locatário em um ambiente de vários locatários são:

1.    Impedir o vazamento ou o acesso não autorizado ao conteúdo do cliente nos locatários; e
2.    Impedir que as ações de um locatário afetem adversamente o serviço para outro locatário

Várias formas de proteção foram implementadas em todo o Microsoft 365 para impedir que os clientes comprometam serviços ou aplicativos da Microsoft 365 ou obtenham acesso não autorizado às informações de outros locatários ou ao próprio sistema Microsoft 365, incluindo:

- O isolamento lógico do conteúdo do cliente dentro de cada locatário para serviços do Microsoft 365 é obtido por meio da autorização do Azure Active Directory e do controle de acesso baseado em função.
- O SharePoint Online fornece mecanismos de isolamento de dados no nível de armazenamento.
- A Microsoft usa rigorosa segurança física, a triagem de plano de fundo e uma estratégia de criptografia em várias camadas para proteger a confidencialidade e integridade do conteúdo do cliente. Todos os datacenters da Microsoft 365 têm controles de acesso biométrico, com a maioria dos que precisam de impressões Palm para obter acesso físico. Além disso, todos os funcionários da Microsoft baseados nos EUA são necessários para concluir com êxito uma verificação em segundo plano padrão como parte do processo de contratação. Para obter mais informações sobre os controles usados para acesso administrativo no Microsoft 365, consulte [controles de acesso administrativo do microsoft 365](microsoft-365-administrative-access-controls-overview.md).
- A Microsoft 365 usa tecnologias do lado do serviço que criptografam o conteúdo do cliente em repouso e em trânsito, incluindo BitLocker, criptografia por arquivo, segurança da camada de transporte (TLS) e segurança do protocolo Internet (IPsec). Para obter detalhes específicos sobre a criptografia no Microsoft 365, consulte [tecnologias de criptografia de dados no Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).

Juntos, as proteções acima listadas oferecem controles de isolamento lógicos sólidos que oferecem proteção contra ameaças e redução equivalente ao que é fornecido apenas por um isolamento físico.

## <a name="related-links"></a>Links relacionados

- [Isolamento e controle de acesso do Azure Active Directory](microsoft-365-isolation-in-azure-active-directory.md)
- [Isolamento de locatário no Office Graph e Delve](microsoft-365-isolation-in-graph-and-delve.md)
- [Isolamento de locatário no Microsoft 365 Search](microsoft-365-isolation-in-microsoft-365-search.md)
- [Isolamento de locatário no Vídeo do Office 365](microsoft-365-isolation-in-microsoft-365-video.md)
- [Limites de recurso](microsoft-365-resource-limits.md)
- [Monitorando e testando limites do locatário](microsoft-365-monitoring-and-testing.md)
- [Isolamento e controle de acesso no Microsoft 365](microsoft-365-isolation-in-microsoft-365.md)
