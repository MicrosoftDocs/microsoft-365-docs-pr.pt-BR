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
description: Saiba como as ferramentas de descoberta eletrônica da Microsoft 365 tratam documentos criptografados anexados a mensagens de email e armazenados no SharePoint Online e no OneDrive for Business.
ms.openlocfilehash: df2ff218e5c62e103661889fc8c66950a4d25cab
ms.sourcegitcommit: 6759e619c45a5f8e775ad456a5dfb18c08f13f8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/18/2020
ms.locfileid: "49713262"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Descriptografia nas ferramentas de eDiscovery da Microsoft 365

A criptografia é uma parte importante da estratégia de proteção de arquivos e proteção de informações. As organizações de todos os tipos usam a tecnologia de criptografia para proteger o conteúdo confidencial dentro de sua organização e garantir que apenas as pessoas certas tenham acesso a esse conteúdo.

Para executar tarefas comuns de descoberta eletrônica em conteúdo criptografado, os gerentes de descoberta eletrônica precisavam descriptografar o conteúdo da mensagem de email quando ele foi exportado de pesquisas de conteúdo, casos de descoberta eletrônica principais e casos de descoberta eletrônica O conteúdo criptografado com tecnologias de criptografia da Microsoft não estava disponível para revisão até depois de ser exportado.

Para facilitar o gerenciamento de conteúdo criptografado no fluxo de trabalho de descoberta eletrônica, as ferramentas de eDiscovery da Microsoft 365 agora incorporam a descriptografia de arquivos criptografados anexados a mensagens de email e enviados no Exchange Online. Além disso, os documentos criptografados armazenados no SharePoint Online e no OneDrive for Business são descriptografados na descoberta eletrônica avançada. 

Antes desse novo recurso, somente o conteúdo de uma mensagem de email protegida pelo gerenciamento de direitos (e arquivos não anexados) foi descriptografado. Não foi possível descriptografar documentos criptografados no SharePoint e no OneDrive durante o fluxo de trabalho de descoberta eletrônica. Agora, se um arquivo criptografado com uma tecnologia de criptografia da Microsoft estiver anexado a uma mensagem de email ou localizado em uma conta do SharePoint ou do OneDrive, esses itens criptografados serão descriptografados quando os resultados da pesquisa forem preparados para visualização, adicionados a uma revisão definida em descoberta eletrônica avançada e exportados. Isso permite que os gerentes de descoberta eletrônica exibam o conteúdo de anexos de email criptografados e documentos de site ao visualizar os resultados da pesquisa e examiná-los após terem sido adicionados a uma análise definida na descoberta eletrônica avançada.

## <a name="supported-encryption-technologies"></a>Tecnologias de criptografia suportadas

As ferramentas do Microsoft eDiscovery dão suporte a itens criptografados com tecnologias de criptografia da Microsoft. Essas tecnologias incluem criptografia de mensagem do Office, gerenciamento de direitos do Azure e proteção de informações da Microsoft (especificamente rótulos de sensibilidade). Para obter mais informações sobre as tecnologias de criptografia da Microsoft, consulte [Encryption](encryption.md). Não há suporte para o conteúdo criptografado por tecnologias de criptografia de terceiros. Por exemplo, a visualização ou exportação de conteúdo criptografado com tecnologias não Microsoft não é suportada.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>atividades de descoberta eletrônica que dão suporte a itens criptografados

A tabela a seguir identifica as tarefas suportadas que podem ser executadas nas ferramentas de eDiscovery da Microsoft 365 em arquivos criptografados anexados a massages de email e documentos criptografados no SharePoint e no OneDrive. Essas tarefas suportadas podem ser realizadas em arquivos criptografados que correspondam aos critérios de uma pesquisa. Um valor de "N/A" indica que a funcionalidade não está disponível na ferramenta de descoberta eletrônica correspondente.

|tarefa de descoberta eletrônica  |Pesquisa de conteúdo  |Descoberta Eletrônica Central  |Descoberta Eletrônica Avançada  |
|:---------|:---------|:---------|:---------|
|Pesquisar conteúdo em arquivos criptografados em emails e sites     |Sim      |Sim      |Sim      |
|Visualizar arquivos criptografados anexados a emails     |Sim      |Sim     |Sim       |
|Visualizar documentos criptografados no SharePoint e no OneDrive|Não      |Não    |Sim       |
|Revisar arquivos criptografados em um conjunto de revisão    |N/D      |N/D        | Sim        |
|Exportar arquivos criptografados anexados a emails    |Sim       |Sim  |Sim    |
|Exportar documentos criptografados no SharePoint e no OneDrive    |Não       |Não  |Sim    |
|||||

## <a name="requirements-for-decryption-in-ediscovery"></a>Requisitos de descriptografia na descoberta eletrônica

Você precisa receber a função de descriptografia do RMS para visualizar, revisar e exportar arquivos criptografados com tecnologias de criptografia da Microsoft. Você também precisa ter atribuído a essa função para revisar e consultar arquivos criptografados que são adicionados a uma revisão definida em descoberta eletrônica avançada.

Essa função é atribuída por padrão ao grupo de funções Gerenciador de descoberta eletrônica na página **permissões** no centro de conformidade & segurança do Office 365. Para obter mais informações sobre a função de descriptografia do RMS, consulte [atribuir permissões de descoberta eletrônica](assign-ediscovery-permissions.md#rms-decrypt).
