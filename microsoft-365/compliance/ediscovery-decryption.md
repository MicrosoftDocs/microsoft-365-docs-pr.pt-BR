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
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba como as ferramentas de descoberta eletrônica da Microsoft 365 tratam documentos criptografados anexados a mensagens de email.
ms.openlocfilehash: 89e6457015289055c56278f5f8650ce022ecf081
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920685"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Descriptografia nas ferramentas de eDiscovery da Microsoft 365

As organizações usam a tecnologia de criptografia para proteger o conteúdo confidencial dentro de sua organização e garantir que apenas as pessoas certas tenham acesso a esse conteúdo. As organizações usam vários tipos de criptografia, tanto as tecnologias de criptografia da Microsoft quanto as tecnologias de terceiros para atender aos requisitos de segurança e proteger suas informações confidenciais.

Até hoje, gerenciar o conteúdo criptografado no fluxo de trabalho de descoberta eletrônica no Microsoft 365 requer manipulação especial de itens criptografados, dependendo do tipo de criptografia usada e do estágio específico no fluxo de trabalho. Isso foi obtido principalmente com a descriptografia do conteúdo da mensagem de email quando ele foi exportado de pesquisas de conteúdo, casos de descoberta eletrônica principais e casos de descoberta eletrônica avançada. O conteúdo criptografado com tecnologias de criptografia da Microsoft não pôde ser visualizado até ser exportado. Na descoberta eletrônica avançada, o conteúdo criptografado foi sinalizado com um erro de processamento, o que exigia que você baixe o item criptografado, descriptografe-o e, em seguida, carregue o arquivo descriptografado para um conjunto de revisão.

Para facilitar o gerenciamento de conteúdo criptografado no fluxo de trabalho de descoberta eletrônica, as ferramentas do Microsoft 365 eDiscovery podem descriptografar arquivos criptografados anexados a mensagens de email e enviados no Exchange Online. Antes desse novo recurso, somente o conteúdo de uma mensagem de email protegida pelo gerenciamento de direitos (e arquivos não anexados) foi descriptografado. Agora, se um arquivo criptografado com uma tecnologia de criptografia da Microsoft estiver anexado a uma mensagem de email que corresponda aos critérios de pesquisa, o arquivo criptografado será descriptografado quando os resultados da pesquisa forem preparados para visualização. Isso permite que os gerentes de descoberta eletrônica exibam o conteúdo de anexos de email criptografados ao visualizar os resultados da pesquisa.

> [!NOTE]
> A partir de janeiro de 2021, as ferramentas de descoberta eletrônica da Microsoft 365 suportarão documentos criptografados armazenados no SharePoint Online e no OneDrive for Business.

## <a name="supported-encryption-technologies"></a>Tecnologias de criptografia suportadas

As ferramentas do Microsoft eDiscovery dão suporte a itens criptografados com tecnologias de criptografia da Microsoft. Essas tecnologias incluem a criptografia de mensagem do Office, a proteção de informações da Microsoft (rótulos de confidencialidade) e o Azure Rights Management. Para obter mais informações sobre as tecnologias de criptografia da Microsoft, consulte [Encryption](encryption.md). Não há suporte para o conteúdo criptografado por tecnologias de criptografia de terceiros. Isso não inclui nenhum suporte ao visualizar ou exportar conteúdo criptografado com tecnologias que não sejam da Microsoft.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>atividades de descoberta eletrônica que dão suporte a itens criptografados

A tabela a seguir identifica as tarefas executadas nas ferramentas de descoberta eletrônica do Microsoft 365 que dão suporte à descriptografia de arquivos criptografados anexados a email massages. As tarefas de suporte podem ser executadas em um arquivo criptografado anexado a uma mensagem de email que corresponda aos critérios de uma pesquisa. Um valor de "N/A" indica que a função não está disponível na ferramenta de descoberta eletrônica correspondente.

|tarefa de descoberta eletrônica  |Pesquisa de Conteúdo  |Descoberta Eletrônica Central  |Descoberta Eletrônica Avançada  |
|:---------|:---------|:---------|:---------|
|Pesquisar conteúdo em arquivos criptografados     |Não      |Não      |Não      |
|Visualizar arquivos criptografados     |Sim      |Sim     |Sim       |
|Revisar arquivos criptografados em um conjunto de revisão    |Não disponível      |Não disponível        | Sim        |
|Exportar arquivos criptografados    |Sim       |Sim  |Sim    |

## <a name="requirements-for-decryption-in-ediscovery"></a>Requisitos de descriptografia na descoberta eletrônica

Você precisa ter a função de descriptografia do RMS para visualizar, revisar e exportar arquivos anexados criptografados com tecnologias de criptografia da Microsoft. Você também precisa ter atribuído a essa função para revisar e consultar anexos de email criptografados que são adicionados a uma revisão definida na descoberta eletrônica avançada.

Essa função é atribuída por padrão ao grupo de funções Gerenciador de descoberta eletrônica no centro de conformidade & segurança do Office 365. Para obter mais informações sobre a função de descriptografia do RMS, consulte [atribuir permissões de descoberta eletrônica](assign-ediscovery-permissions.md#rms-decrypt).
