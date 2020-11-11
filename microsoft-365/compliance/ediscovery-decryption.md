---
title: Descriptografia na descoberta eletrônica
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Saiba como as ferramentas de descoberta eletrônica da Microsoft 365 tratam documentos criptografados anexados a mensagens de email.
ms.openlocfilehash: 91d5689bfb64d272c896c0e92422ce1f45fd5f72
ms.sourcegitcommit: 89f56c3e0b619a4700a75a21927d9ffc90658632
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "48984895"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Descriptografia nas ferramentas de eDiscovery da Microsoft 365

A criptografia é uma parte importante da estratégia de proteção de arquivos e proteção de informações. As organizações de todos os tipos usam a tecnologia de criptografia para proteger o conteúdo confidencial dentro de sua organização e garantir que apenas as pessoas certas tenham acesso a esse conteúdo.

Para executar tarefas comuns de descoberta eletrônica em conteúdo criptografado, os gerentes de descoberta eletrônica precisavam descriptografar o conteúdo da mensagem de email quando ele foi exportado de pesquisas de conteúdo, casos de descoberta eletrônica principais e casos de descoberta eletrônica O conteúdo criptografado com tecnologias de criptografia da Microsoft não estava disponível para revisão até depois de ser exportado.

Para facilitar o gerenciamento de conteúdo criptografado no fluxo de trabalho de descoberta eletrônica, as ferramentas de eDiscovery da Microsoft 365 agora incorporam a descriptografia de arquivos criptografados anexados a mensagens de email e enviados no Exchange Online. Antes desse novo recurso, somente o conteúdo de uma mensagem de email protegida pelo gerenciamento de direitos (e arquivos não anexados) foi descriptografado. Agora, se um arquivo criptografado com uma tecnologia de criptografia da Microsoft estiver anexado a uma mensagem de email que corresponda aos critérios de pesquisa, o arquivo criptografado será descriptografado quando os resultados da pesquisa forem preparados para revisão. Isso permite que os gerentes de descoberta eletrônica exibam o conteúdo de anexos de email criptografados ao visualizar os resultados da pesquisa e examiná-los assim que forem adicionados a uma análise definida na descoberta eletrônica avançada.

> [!NOTE]
> A partir de então, as ferramentas de eDiscovery da Microsoft 365 suportarão documentos criptografados armazenados no SharePoint Online e no OneDrive for Business. Isso incluirá documentos que são criptografados como resultado de rótulos de confidencialidade aplicados a eles.

## <a name="supported-encryption-technologies"></a>Tecnologias de criptografia suportadas

As ferramentas do Microsoft eDiscovery dão suporte a itens criptografados com tecnologias de criptografia da Microsoft. Essas tecnologias incluem a criptografia de mensagens do Office e o Azure Rights Management. Para obter mais informações sobre as tecnologias de criptografia da Microsoft, consulte [Encryption](encryption.md). Não há suporte para o conteúdo criptografado por tecnologias de criptografia de terceiros. Isso não inclui nenhum suporte ao visualizar ou exportar conteúdo criptografado com tecnologias que não sejam da Microsoft.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>atividades de descoberta eletrônica que dão suporte a itens criptografados

A tabela a seguir identifica as tarefas executadas nas ferramentas de descoberta eletrônica do Microsoft 365 que dão suporte à descriptografia de arquivos criptografados anexados a email massages. As tarefas de suporte podem ser executadas em um arquivo criptografado anexado a uma mensagem de email que corresponda aos critérios de uma pesquisa. Um valor de "N/A" indica que a função não está disponível na ferramenta de descoberta eletrônica correspondente.

|tarefa de descoberta eletrônica  |Pesquisa de conteúdo  |Descoberta Eletrônica Central  |Descoberta Eletrônica Avançada  |
|:---------|:---------|:---------|:---------|
|Pesquisar conteúdo em arquivos criptografados     |Sim      |Sim      |Sim      |
|Visualizar arquivos criptografados     |Sim      |Sim     |Sim       |
|Revisar arquivos criptografados em um conjunto de revisão    |Não disponível      |Não disponível        | Sim        |
|Exportar arquivos criptografados    |Sim       |Sim  |Sim    |

## <a name="requirements-for-decryption-in-ediscovery"></a>Requisitos de descriptografia na descoberta eletrônica

Você precisa ter a função de descriptografia do RMS para visualizar, revisar e exportar arquivos anexados criptografados com tecnologias de criptografia da Microsoft. Você também precisa ter atribuído a essa função para revisar e consultar anexos de email criptografados que são adicionados a uma revisão definida na descoberta eletrônica avançada.

Essa função é atribuída por padrão ao grupo de funções Gerenciador de descoberta eletrônica no centro de conformidade & segurança do Office 365. Para obter mais informações sobre a função de descriptografia do RMS, consulte [atribuir permissões de descoberta eletrônica](assign-ediscovery-permissions.md#rms-decrypt).
