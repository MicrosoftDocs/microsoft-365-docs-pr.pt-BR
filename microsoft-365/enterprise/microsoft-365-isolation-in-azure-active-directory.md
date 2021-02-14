---
title: Isolamento e controle de acesso do Microsoft 365 no Azure Active Directory
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
description: Neste artigo, saiba como o Isolamento e o Controle de Acesso funcionam para manter os dados de vários locatários isolados uns dos outros no Azure Active Directory.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 198e1f37a7378d14d5a4ad28d5bce9d480b2c49e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332407"
---
# <a name="microsoft-365-isolation-and-access-control-in-azure-active-directory"></a>Isolamento e controle de acesso do Microsoft 365 no Azure Active Directory

O Azure Active Directory (Azure AD) foi projetado para hospedar vários locatários de maneira altamente segura por meio do isolamento de dados lógicos. O acesso ao Azure AD é uma camada de autorização. O Azure AD isola os clientes usando contêineres de locatário como limites de segurança para proteger o conteúdo do cliente para que o conteúdo não possa ser acessado ou comprometido por co-locatários. Três verificações são executadas pela camada de autorização do Azure AD:

- A entidade está habilitada para acessar o locatário do Azure AD?
- A entidade de segurança está habilitada para acessar dados neste locatário?
- A função da entidade de segurança neste locatário está autorizada para o tipo de acesso a dados solicitado?

Nenhum aplicativo, usuário, servidor ou serviço pode acessar o Azure AD sem a autenticação adequada e o token ou o certificado. As solicitações são rejeitadas se não são acompanhadas pelas credenciais adequadas.

Efetivamente, o Azure AD hospeda cada locatário em seu próprio contêiner protegido, com políticas e permissões para e dentro do contêiner exclusivamente de propriedade e gerenciados pelo locatário.
 
![Contêiner do Azure](../media/office-365-isolation-azure-container.png)

O conceito de contêineres de locatário está profundamente insinuado no serviço de diretório em todas as camadas, desde portais até o armazenamento persistente. Mesmo quando vários metadados de locatário do Azure AD são armazenados no mesmo disco físico, não há relação entre os contêineres além do que é definido pelo serviço de diretório, que, por sua vez, é ditado pelo administrador de locatários. Não pode haver conexões diretas com o armazenamento do Azure AD de qualquer aplicativo ou serviço solicitando sem passar primeiro pela camada de autorização.

No exemplo a seguir, Contoso e Fabrikam têm contêineres separados e dedicados, e mesmo que esses contêineres possam compartilhar parte da mesma infraestrutura subjacente, como servidores e armazenamento, eles permanecem separados e isolados uns dos outros e isolados por camadas de autorização e controle de acesso.
 
![Contêineres dedicados do Azure](../media/office-365-isolation-azure-dedicated-containers.png)

Além disso, não há componentes de aplicativo que possam ser executados no Azure AD, e não é possível que um locatário viole à força a integridade de outro locatário, acesse chaves de criptografia de outro locatário ou leia dados brutos do servidor.

Por padrão, o Azure AD não permite todas as operações emitidas por identidades em outros locatários. Cada locatário é logicamente isolado no Azure AD por meio de controles de acesso baseado em declarações. Leituras e gravações de dados de diretório são delimitadas para contêineres de locatários e delimitadas por uma camada de abstração interna e uma camada de controle de acesso baseado em função (RBAC), que juntos impõem o locatário como o limite de segurança. Cada solicitação de acesso a dados de diretório é processada por essas camadas e todas as solicitações de acesso no Microsoft 365 são controladas pela lógica acima.

O Azure AD tem partições América do Norte, Governo dos EUA, União Europeia, Alemanha e World Wide. Um locatário existe em uma única partição, e as partições podem conter vários locatários. As informações de partição são abstraídos dos usuários. Uma determinada partição (incluindo todos os locatários dentro dela) é replicada para vários datacenters. A partição para um locatário é escolhida com base nas propriedades do locatário (por exemplo, o código do país). Segredos e outras informações confidenciais em cada partição são criptografados com uma chave dedicada. As chaves são geradas automaticamente quando uma nova partição é criada.

As funcionalidades do sistema do Azure AD são uma instância exclusiva para cada sessão de usuário. Além disso, o Azure AD usa tecnologias de criptografia para fornecer isolamento de recursos de sistema compartilhados no nível da rede para evitar a transferência não autorizada e não intencional de informações.
