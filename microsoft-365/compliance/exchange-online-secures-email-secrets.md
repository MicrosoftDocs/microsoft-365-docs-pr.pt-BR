---
title: Como o Exchange Online protege seus segredos de email
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Além da central de confiabilidade do Office 365, que fornece informações de segurança, privacidade e conformidade do Office 365, você pode querer saber como o Office 365 ajuda a proteger os segredos que você fornece em seus datacenters. Usamos uma tecnologia chamada DKM (Distributed Key Manager).
ms.openlocfilehash: 6ba60616ee72a4457d81f3f9c2049007afdcbb1d
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800071"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Como o Exchange Online protege seus segredos de email

Este artigo descreve como a Microsoft protege seus segredos de email em seus datacenters.
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>Como protegemos as informações secretas fornecidas por você?

Além da central de confiabilidade do Office 365, que fornece [informações de segurança, privacidade e conformidade do office 365](https://go.microsoft.com/fwlink/?linkid=874644), você pode querer saber como o Office 365 ajuda a proteger os segredos que você fornece em seus datacenters. Usamos uma tecnologia chamada DKM (Distributed Key Manager).
  
O [Gerenciador de chaves distribuídas](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) é uma funcionalidade do lado do cliente que usa um conjunto de chaves secretas para criptografar e descriptografar informações. Somente os membros de um grupo de segurança específico nos Serviços de Domínio Active Directory podem acessar essas chaves para descriptografar os dados criptografados pelo DKM. No Exchange Online, apenas certas contas de serviço, sob as quais os processos do Exchange são executados, fazem parte do grupo de segurança. Como parte do procedimento operacional padrão no datacenter, nenhum humano recebe credenciais que fazem parte deste grupo de segurança e, portanto, nenhuma pessoa tem acesso às chaves que podem descriptografar esses segredos.
  
Para fins de depuração, solução de problemas ou auditoria, um administrador de datacenter deve solicitar acesso elevado para obter credenciais temporárias que fazem parte do grupo de segurança. Esse processo requer vários níveis de aprovação legal. Se o acesso for concedido, toda as atividades são registradas e auditadas. Além disso, o acesso é concedido apenas por um tempo definido, expirando automaticamente após esse período.
  
Para maior proteção, a tecnologia do DKM inclui a sobreposição de chave e o arquivamento automatizados. Isso também garante que você pode continuar acessando seu conteúdo antigo sem depender da mesma chave indefinidamente.
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>Em que circunstâncias o Exchange Online usa o DKM?

A Microsoft usa o [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) para criptografar seus segredos nos datacenters do Exchange Online. Por exemplo:
  
- Credenciais da conta de email para contas conectadas. As contas conectadas são contas de terceiros, como hotmail, Gmail e Yahoo! contas de email.

- Chave do cliente. Se você estiver usando [a criptografia de serviço com a chave do cliente no Office 365](customer-key-overview.md), você usará o [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) para proteger seus segredos.

## <a name="related-topics"></a>Tópicos relacionados

[Criptografia no Office 365](encryption.md)
  
[Detalhes de referências técnicas sobre a criptografia no Office 365](technical-reference-details-about-encryption.md)
  
[Garantia de serviço no centro de conformidade &amp; de segurança do Office 365](https://go.microsoft.com/fwlink/?linkid=874645)
  

