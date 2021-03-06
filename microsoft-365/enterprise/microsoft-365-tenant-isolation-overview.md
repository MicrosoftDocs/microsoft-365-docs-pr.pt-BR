---
title: Isolamento de locatários Microsoft 365
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
description: Este artigo contém um resumo de como a Microsoft impõe isolamento de locatários em serviços de nuvem como Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b52d936bb00ac0adef0baf428cbc5f9a8f8aba49
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194644"
---
# <a name="tenant-isolation-in-microsoft-365"></a>Isolamento de locatários Microsoft 365

Um dos principais benefícios da computação em nuvem é o conceito de uma infraestrutura comum compartilhada entre vários clientes simultaneamente, levando a economias de escala. Esse conceito é chamado *de multi-enancy*. A Microsoft trabalha continuamente para garantir que as arquiteturas de vários locatários de nossos serviços de nuvem suportem padrões de segurança, confidencialidade, privacidade, integridade e disponibilidade em nível empresarial.

Com base nos investimentos [](https://www.microsoft.com/trust-center) significativos e na experiência coletadas da Computação Confiável e do Ciclo de Vida de Desenvolvimento de Segurança [,](https://www.microsoft.com/securityengineering/sdl/)os serviços de nuvem da Microsoft foram projetados com a suposição de que todos os locatários são potencialmente hostil a todos os outros locatários, e implementamos medidas de segurança para impedir que as ações de um locatário afetem a segurança ou o serviço de outro locatário ou acessem o conteúdo de outro locatário.

Os dois principais objetivos de manter o isolamento de locatários em um ambiente de vários locatários são:

1.    Impedir vazamento de conteúdo do cliente ou acesso não autorizado a locatários; e
2.    Impedir que as ações de um locatário afetem adversamente o serviço para outro locatário

Várias formas de proteção foram implementadas em todo o Microsoft 365 para impedir que os clientes comprometerem serviços ou aplicativos do Microsoft 365 ou obtenham acesso não autorizado às informações de outros locatários ou do próprio sistema Microsoft 365, incluindo:

- O isolamento lógico do conteúdo do cliente em cada locatário para serviços Microsoft 365 é obtido por meio Azure Active Directory autorização e controle de acesso baseado em função.
- SharePoint Online fornece mecanismos de isolamento de dados no nível de armazenamento.
- A Microsoft usa segurança física rigorosa, triagem em segundo plano e uma estratégia de criptografia em várias camadas para proteger a confidencialidade e a integridade do conteúdo do cliente. Todos Microsoft 365 datacenters têm controles de acesso biométrico, com a maioria exigindo impressões de palma para obter acesso físico. Além disso, todos os funcionários da Microsoft baseados nos EUA são necessários para concluir com êxito uma verificação padrão em segundo plano como parte do processo de contratação. Para obter mais informações sobre os controles usados para acesso administrativo Microsoft 365, [consulte Microsoft 365 Controles de Acesso Administrativo.](/compliance/assurance/assurance-administrative-access-controls-overview)
- Microsoft 365 usa tecnologias do lado do serviço que criptografam o conteúdo do cliente em repouso e em trânsito, incluindo o BitLocker, a criptografia por arquivo, o TLS (Transport Layer Security) e o Internet Protocol Security (IPsec). Para obter detalhes específicos sobre criptografia Microsoft 365, consulte [Tecnologias de Criptografia](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md)de Dados em Microsoft 365 .

Juntas, as proteções listadas acima fornecem controles de isolamento lógico robustos que fornecem proteção contra ameaças e mitigação equivalentes às fornecidas apenas pelo isolamento físico.

## <a name="related-links"></a>Links relacionados

- [Isolamento e controle de acesso do Azure Active Directory](microsoft-365-isolation-in-azure-active-directory.md)
- [Isolamento de locatário no Office Graph e Delve](microsoft-365-isolation-in-graph-and-delve.md)
- [Isolamento de locatário no Microsoft 365 Search](microsoft-365-isolation-in-microsoft-365-search.md)
- [Limites de recurso](/compliance/assurance/assurance-resource-limits)
- [Monitorando e testando limites do locatário](/compliance/assurance/assurance-monitoring-and-testing)
- [Isolamento e controle de acesso no Microsoft 365](microsoft-365-isolation-in-microsoft-365.md)