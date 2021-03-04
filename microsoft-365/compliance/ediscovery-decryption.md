---
title: Descriptografia na Descoberta e
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
description: Saiba como as ferramentas de Descoberta Eletrônico do Microsoft 365 lidam com documentos criptografados anexados a mensagens de email e armazenados no SharePoint Online e no OneDrive for Business.
ms.openlocfilehash: 4ddc66d595b9d2129a7ba1b75e69586ccbd130f7
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423814"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Descriptografia em ferramentas de Descoberta Online do Microsoft 365

A criptografia é uma parte importante da sua estratégia de proteção de arquivos e proteção de informações. Organizações de todos os tipos usam tecnologia de criptografia para proteger conteúdos confidenciais em sua organização e garantir que somente as pessoas certas tenham acesso a esse conteúdo.

Para executar tarefas comuns de Descoberta Eletrônico em conteúdo criptografado, os gerentes de Descoberta Eletrônico eram necessários para descriptografar o conteúdo da mensagem de email à medida que ele era exportado de pesquisas de conteúdo, principais casos de Descoberta Eletrônico e Casos avançados de Descoberta Eletrônico. O conteúdo criptografado com tecnologias de criptografia da Microsoft não estava disponível para revisão até ser exportado.

Para facilitar o gerenciamento de conteúdo criptografado no fluxo de trabalho de Descoberta Eletrônico, as ferramentas de Descoberta Eletrônico do Microsoft 365 agora incorporam a descriptografia de arquivos criptografados anexados a mensagens de email e enviadas no Exchange Online. Além disso, documentos criptografados armazenados no SharePoint Online e no OneDrive for Business são descriptografados em Descoberta Avançada. 

Antes desse novo recurso, apenas o conteúdo de uma mensagem de email protegida pelo gerenciamento de direitos (e arquivos não anexados) eram descriptografados. Os documentos criptografados no SharePoint e no OneDrive não puderam ser descriptografados durante o fluxo de trabalho de Descoberta Eletrônico. Agora, se um arquivo criptografado com uma tecnologia de criptografia da Microsoft estiver anexado a uma mensagem de email ou localizado em uma conta do SharePoint ou do OneDrive, esses itens criptografados serão descriptografados quando os resultados da pesquisa são preparados para visualização, adicionados a um conjunto de revisão na Descoberta Avançada e exportados. Isso permite que os gerentes de Descoberta Eletrônico visualizem o conteúdo de anexos de email criptografados e documentos de site ao visualizar os resultados da pesquisa e revisá-los depois que eles foram adicionados a um conjunto de revisão na Descoberta Avançada.

## <a name="supported-encryption-technologies"></a>Tecnologias de criptografia com suporte

As ferramentas de Descoberta Online da Microsoft suportam itens criptografados com tecnologias de criptografia da Microsoft. Essas tecnologias são o Gerenciamento de Direitos do Azure e a Proteção de Informações da Microsoft (especificamente rótulos de sensibilidade). Para obter mais informações sobre as tecnologias de criptografia da Microsoft, consulte [Encryption](encryption.md). Não há suporte para conteúdo criptografado por tecnologias de criptografia de terceiros. Por exemplo, não há suporte para visualização ou exportação de conteúdo criptografado com tecnologias que não são da Microsoft.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>Atividades de Descoberta Livre que suportam itens criptografados

A tabela a seguir identifica as tarefas com suporte que podem ser executadas nas ferramentas de Descoberta Eletrônico do Microsoft 365 em arquivos criptografados anexados a massagens de email e documentos criptografados no SharePoint e no OneDrive. Essas tarefas com suporte podem ser executadas em arquivos criptografados que corresponderem aos critérios de uma pesquisa. Um valor indica que a funcionalidade não está disponível na `N/A` ferramenta de Descoberta Digital correspondente.

|Tarefa de Descoberta Desdiscovery  |Pesquisa de conteúdo  |Descoberta Eletrônica Central  |Descoberta Eletrônica Avançada  |
|:---------|:---------|:---------|:---------|
|Pesquisar conteúdo em arquivos criptografados em emails e sites     |Sim      |Sim      |Sim      |
|Visualizar arquivos criptografados anexados ao email     |Sim      |Sim     |Sim       |
|Visualizar documentos criptografados no SharePoint e no OneDrive|Não      |Não    |Sim       |
|Revisar arquivos criptografados em um conjunto de revisão    |N/D      |N/D        | Sim        |
|Exportar arquivos criptografados anexados ao email    |Sim       |Sim  |Sim    |
|Exportar documentos criptografados no SharePoint e no OneDrive    |Não       |Não  |Sim    |
|||||

**Observação:** a Descoberta EDiscovery não dá suporte a arquivos criptografados no SharePoint e no OneDrive quando um rótulo de sensibilidade que aplicou a criptografia é configurado com uma das seguintes configurações:

- Os usuários podem atribuir permissões quando aplicam manualmente o rótulo a um documento. Às vezes, isso é chamado de *permissões definidas pelo usuário.*<br/>

- O acesso do usuário ao documento tem uma configuração de expiração definida como um valor diferente de **Nunca**.

Para obter mais informações sobre essas configurações, consulte a seção "Configurar configurações de criptografia" em Restringir o acesso ao conteúdo usando rótulos de sensibilidade para [aplicar criptografia](encryption-sensitivity-labels.md#configure-encryption-settings).

Os documentos criptografados com as configurações anteriores ainda podem ser retornados por uma pesquisa de Descobertas Digitais. Isso pode acontecer quando uma propriedade de documento (como o título, o autor ou a data modificada) corresponde aos critérios de pesquisa. Embora esses documentos possam ser incluídos nos resultados da pesquisa, eles não podem ser visualizados ou revisados. Esses documentos também permanecerão criptografados quando eles são exportados em Descoberta Avançada.

## <a name="requirements-for-decryption-in-ediscovery"></a>Requisitos para descriptografia na Descoberta e

Você precisa ter a função de descriptografia RMS para visualizar, revisar e exportar arquivos criptografados com tecnologias de criptografia da Microsoft. Você também precisa ser atribuído a essa função para revisar e consultar arquivos criptografados adicionados a um conjunto de revisão na Descoberta Avançada.

Essa função é atribuída por padrão ao grupo de  funções do Gerenciador de Descobertas e na página Permissões no Centro de Conformidade & Segurança do Office 365. Para obter mais informações sobre a função Descriptografar RMS, consulte [Assign eDiscovery permissions](assign-ediscovery-permissions.md#rms-decrypt).
