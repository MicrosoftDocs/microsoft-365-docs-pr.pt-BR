---
title: Destruição de dados do Microsoft 365
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
description: Uma visão geral das políticas da Microsoft sobre a reciclagem, a alienação ou a destruição de drives e servidores de disco do Microsoft 365 Data Center.
ms.openlocfilehash: 981903db68a79632285d7c5170aeb22014940a4a
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47331843"
---
# <a name="microsoft-365-data-destruction"></a>Destruição de dados do Microsoft 365

## <a name="physical-data-destruction"></a>Destruição de dados físicos

A Microsoft tem políticas padrão de manipulação de dados que resolvem a reciclagem e a eliminação de drives de disco e falharam ou aposentaram servidores. Antes de reutilizar quaisquer drives de disco do Microsoft 365, a Microsoft executa um processo de limpeza física consistente com o National Institute of Standards and Technology Special 800-88 publication [[diretrizes do NIST SP 800-88 para a limpeza de mídia](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf)). Como todos os drives de disco no Microsoft 365 são criptografados usando a criptografia de nível de volume do BitLocker, a eliminação compatível com o NIST SP 800-88 não é tecnicamente necessária. No entanto, a Microsoft executa esse processo.

Os discos com falha usados nos datacenters do Microsoft 365 são destruídos fisicamente e auditados por meio do processo ISO. O tipo de ativo determina os meios apropriados de alienação. Para discos rígidos que não podem ser apagados, a Microsoft usa um processo de destruição para destruir a mídia e renderizar a recuperação de informações impossível. Por exemplo, os discos são destruídos fisicamente, pulverized ou incinerated. A Microsoft mantém todos os registros da destruição e executa um processo de limpeza semelhante nos servidores reutilizados no Microsoft 365. Essas diretrizes englobam a limpeza eletrônica e física.

Cada datacenter usa um processo de destruição física local para descartar seus discos. Os compartimentos seguros para mídia de armazenamento designada para eliminação de disco estão em cada área do datacenter. Cada estação de compartimento seguro tem vigilância de monitoramento de vídeo. Depois que um compartimento de descarte atinge aproximadamente 50% de capacidade, a equipe de serviços de site contata a equipe de segurança física para coordenar a remoção. Equipe de serviços de site e um escritório de segurança remova o compartimento de descarte seguro e coloque-o em uma área de armazenamento segura designada. Políticas e procedimentos que regem o tratamento de dados que ostentam dispositivos durante o descarte são testados rotineiramente, incluindo procedimentos para garantir a condição de maquinação aprovada para destruição.

No processo de destruição de dados, os discos são apagados de uma maneira compatível com o NIST 800-88 (se possível) e, em seguida, colocados em um picador industrial e fisicamente demolished. A Microsoft mantém a responsabilidade dos ativos que saem do datacenter usando a limpeza/limpeza consistentes do NIST SP 800-88, destruição de ativos, criptografia, inventário preciso, acompanhamento e proteção da cadeia de custódia durante o transporte. Esse processo é monitorado via televisão de circuito fechado, e um certificado de destruição é emitido após a conclusão.

A Microsoft usa unidades de eliminação de dados das [soluções de protocolo extremo](https://www.enterprisedataerasure.com/) (EPS). O software EPS suporta os requisitos do NIST SP 800-88 para limpeza e limpeza/eliminação segura. Antes da limpeza ou da destruição, um inventário é criado pelo Microsoft Asset Manager. Se um fornecedor for usado para destruição, o fornecedor fornecerá um certificado de destruição para cada ativo destruído, que é validado pelo Asset Manager.

## <a name="virtual-data-destruction"></a>Destruição de dados virtuais

A Microsoft tem políticas e procedimentos de manipulação de dados que lidam com a destruição virtual efetiva de dados para proteger contra a possibilidade de dados sendo compartilhados inadequadamente entre os locatários de serviço ou podem ser acessados após a exclusão difícil no serviço. Os dados excluídos do serviço em um locatário não podem ser acessados por outro locatário de serviço, mesmo se qualquer um dos armazenamento físico subjacente for reatribuído. Este é um resultado dos efeitos compostos de várias tecnologias de virtualização e fragmentação usadas para dimensionar ambientes virtuais, os comportamentos de exclusão ativa de aplicativos dentro de cada locatário de serviço (como [anulação de página](https://docs.microsoft.com/office365/securitycompliance/office-365-exchange-online-data-deletion#page-zeroing)) e os processos de criptografia de conteúdo de aplicativos e de mídia necessários.