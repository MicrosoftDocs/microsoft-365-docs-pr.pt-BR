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
description: Saiba como as Microsoft 365 de Descoberta Microsoft 365 lidam com documentos criptografados anexados a mensagens de email e armazenados no SharePoint Online e OneDrive for Business.
ms.openlocfilehash: b87d87b7b0e870d6f396d87dc693fb8f41d5826b
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51750023"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Descriptografia em Microsoft 365 ferramentas de Descoberta e

A criptografia é uma parte importante da sua estratégia de proteção de arquivos e proteção de informações. Organizações de todos os tipos usam tecnologia de criptografia para proteger conteúdos confidenciais em sua organização e garantir que somente as pessoas certas tenham acesso a esse conteúdo.

Para executar tarefas comuns de Descoberta Eletrônico em conteúdo criptografado, os gerentes de Descoberta Eletrônico eram necessários para descriptografar o conteúdo da mensagem de email à medida que ele era exportado de pesquisas de conteúdo, principais casos de Descoberta Eletrônico e Advanced eDiscovery casos. O conteúdo criptografado com tecnologias de criptografia da Microsoft não estava disponível para revisão até ser exportado.

Para facilitar o gerenciamento de conteúdo criptografado no fluxo de trabalho de Descoberta Eletrônico, as ferramentas de Descoberta Microsoft 365 agora incorporam a descriptografia de arquivos criptografados anexados a mensagens de email e enviadas Exchange Online. <sup>1</sup> Além disso, documentos criptografados armazenados no SharePoint Online e OneDrive for Business são descriptografados em Advanced eDiscovery.

Antes desse novo recurso, apenas o conteúdo de uma mensagem de email protegida pelo gerenciamento de direitos (e arquivos não anexados) eram descriptografados. Documentos criptografados SharePoint e OneDrive não puderam ser descriptografados durante o fluxo de trabalho de Descoberta Eletrônico. Agora, os arquivos criptografados com uma tecnologia de criptografia da Microsoft estão localizados em uma conta SharePoint ou OneDrive são pesquisáveis e descriptografados quando os resultados da pesquisa são preparados para visualização, adicionados a um conjunto de revisão no Advanced eDiscovery e exportados. Além disso, documentos criptografados em SharePoint e OneDrive anexados a uma mensagem de email são pesquisáveis. Essa funcionalidade de descriptografia permite que os gerentes de Descoberta Eletrônico visualizem o conteúdo de anexos de email criptografados e documentos de site ao visualizar os resultados da pesquisa e revisá-los depois que eles foram adicionados a um conjunto de revisão no Advanced eDiscovery.

## <a name="supported-encryption-technologies"></a>Tecnologias de criptografia com suporte

As ferramentas de Descoberta Online da Microsoft suportam itens criptografados com tecnologias de criptografia da Microsoft. Essas tecnologias são o Gerenciamento de Direitos do Azure e a Proteção de Informações da Microsoft (especificamente rótulos de sensibilidade). Para obter mais informações sobre as tecnologias de criptografia da Microsoft, consulte [Encryption](encryption.md). Não há suporte para conteúdo criptografado por tecnologias de criptografia de terceiros. Por exemplo, não há suporte para visualização ou exportação de conteúdo criptografado com tecnologias que não são da Microsoft.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>Atividades de Descoberta Livre que suportam itens criptografados

A tabela a seguir identifica as tarefas com suporte que podem ser executadas em ferramentas de Descoberta Microsoft 365 em arquivos criptografados anexados a mensagens de email e documentos criptografados em SharePoint e OneDrive. Essas tarefas com suporte podem ser executadas em arquivos criptografados que corresponderem aos critérios de uma pesquisa. Um valor indica que a funcionalidade não está disponível na `N/A` ferramenta de Descoberta Digital correspondente.

|Tarefa de Descoberta Desdiscovery  |Pesquisa de conteúdo  |Descoberta Eletrônica Central  |Descoberta Eletrônica Avançada  |
|:---------|:---------|:---------|:---------|
|Pesquisar conteúdo em arquivos criptografados no email e sites<sup>1</sup>     |Sim      |Sim      |Sim      |
|Visualizar arquivos criptografados anexados ao email     |Sim      |Sim     |Sim       |
|Visualizar documentos criptografados em SharePoint e OneDrive|Não      |Não    |Sim       |
|Revisar arquivos criptografados em um conjunto de revisão    |N/D      |N/D        | Sim        |
|Exportar arquivos criptografados anexados ao email    |Sim       |Sim  |Sim    |
|Exportar documentos criptografados em SharePoint e OneDrive    |Não       |Não  |Sim    |
|||||

> [!NOTE]
> <sup>1</sup> Os arquivos criptografados que estão localizados em um computador local (e não armazenados em um SharePoint ou OneDrive site) não são indexados para a Descoberta eDiscovery. Isso significa que, se um arquivo local criptografado estiver anexado a uma mensagem de email, o arquivo não será retornado por uma consulta de pesquisa de palavra-chave, mesmo que o arquivo contenha palavras-chave que corresponderem à consulta de pesquisa. No entanto, as mensagens de email com arquivo criptografado local podem ser retornadas por uma pesquisa de Descoberta Eletrônico se uma propriedade de email (como data, remetente, destinatário ou assunto enviado) corresponde à consulta de pesquisa.

### <a name="decryption-limitations-with-sensitivity-labels"></a>Limitações de descriptografia com rótulos de sensibilidade

A Descoberta eDiscovery não dá suporte a arquivos criptografados no SharePoint e OneDrive quando um rótulo de sensibilidade que aplicou a criptografia é configurado com uma das seguintes configurações:

- Os usuários podem atribuir permissões quando aplicam manualmente o rótulo a um documento. Às vezes, isso é chamado de *permissões definidas pelo usuário.*

- O acesso do usuário ao documento tem uma configuração de expiração definida como um valor diferente de **Nunca**.

Para obter mais informações sobre essas configurações, consulte a seção "Configurar configurações de criptografia" em Restringir o acesso ao conteúdo usando rótulos de sensibilidade para [aplicar criptografia](encryption-sensitivity-labels.md#configure-encryption-settings).

Os documentos criptografados com as configurações anteriores ainda podem ser retornados por uma pesquisa de Descobertas Digitais. Isso pode acontecer quando uma propriedade de documento (como o título, o autor ou a data modificada) corresponde aos critérios de pesquisa. Embora esses documentos possam ser incluídos nos resultados da pesquisa, eles não podem ser visualizados ou revisados. Esses documentos também permanecerão criptografados quando eles são exportados em Advanced eDiscovery.

## <a name="requirements-for-decryption-in-ediscovery"></a>Requisitos para descriptografia na Descoberta e

Você precisa ter a função de descriptografia RMS para visualizar, revisar e exportar arquivos criptografados com tecnologias de criptografia da Microsoft. Você também precisa ser atribuído a essa função para revisar e consultar arquivos criptografados que são adicionados a um conjunto de revisão em Advanced eDiscovery.

Essa função é atribuída por padrão ao grupo de  funções do Gerenciador de Descobertas e na página Permissões no Centro de Conformidade Office 365 Segurança & Segurança. Para obter mais informações sobre a função Descriptografar RMS, consulte [Assign eDiscovery permissions](assign-ediscovery-permissions.md#rms-decrypt).
