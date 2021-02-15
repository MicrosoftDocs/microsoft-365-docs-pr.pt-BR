---
title: Descriptografia no eDiscovery
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
ms.openlocfilehash: aeb1d927a5da24c55838fe3379451956949d8b4f
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044763"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Descriptografia nas ferramentas de Descoberta Online do Microsoft 365

A criptografia é uma parte importante da estratégia de proteção de arquivos e informações. As organizações de todos os tipos usam tecnologia de criptografia para proteger conteúdos confidenciais em sua organização e garantir que apenas as pessoas certas tenham acesso a esse conteúdo.

Para executar tarefas comuns de Descoberta Eletrônico em conteúdo criptografado, os gerentes de Descoberta eDiscovery foram obrigados a descriptografar o conteúdo da mensagem de email à medida que ele era exportado de pesquisas de conteúdo, casos de Descoberta Eletrônico Principal e ocorrências de Descoberta Eletrônico Avançada. O conteúdo criptografado com tecnologias de criptografia da Microsoft não estava disponível para revisão até ser exportado.

Para facilitar o gerenciamento de conteúdo criptografado no fluxo de trabalho de Descoberta Eletrônico, as ferramentas de Descoberta Eletrônico do Microsoft 365 agora incorporam a descriptografia de arquivos criptografados anexados a mensagens de email e enviadas no Exchange Online. Além disso, os documentos criptografados armazenados no SharePoint Online e no OneDrive for Business são descriptografados na Descoberta Avançada. 

Antes desse novo recurso, apenas o conteúdo de uma mensagem de email protegida pelo gerenciamento de direitos (e arquivos não anexados) eram descriptografados. Documentos criptografados no SharePoint e no OneDrive não puderam ser descriptografados durante o fluxo de trabalho de Descoberta Eletrônico. Agora, se um arquivo criptografado com uma tecnologia de criptografia da Microsoft estiver anexado a uma mensagem de email ou localizado em uma conta do SharePoint ou do OneDrive, esses itens criptografados serão descriptografados quando os resultados da pesquisa são preparados para visualização, adicionados a um conjunto de revisão na Descoberta Eletrônico Avançada e exportados. Isso permite que os gerentes de Descoberta eDiscovery visualizem o conteúdo de anexos de email criptografados e documentos do site ao visualizar os resultados da pesquisa e revisá-los depois que eles foram adicionados a um conjunto de revisão na Descoberta Avançada.

## <a name="supported-encryption-technologies"></a>Tecnologias de criptografia suportadas

As ferramentas de Descoberta Online da Microsoft suportam itens criptografados com tecnologias de criptografia da Microsoft. Essas tecnologias incluem a Criptografia de Mensagens do Office, o Azure Rights Management e a Proteção de Informações da Microsoft (especificamente rótulos de sensibilidade). Para obter mais informações sobre as tecnologias de criptografia da Microsoft, consulte [Criptografia.](encryption.md) Não há suporte para conteúdo criptografado por tecnologias de criptografia de terceiros. Por exemplo, não há suporte para visualização ou exportação de conteúdo criptografado com tecnologias que não são da Microsoft.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>Atividades de Descoberta e que suportam itens criptografados

A tabela a seguir identifica as tarefas com suporte que podem ser executadas nas ferramentas de Descoberta Eletrônico do Microsoft 365 em arquivos criptografados anexados a emails e documentos criptografados no SharePoint e no OneDrive. Essas tarefas com suporte podem ser executadas em arquivos criptografados que corresponderem aos critérios de uma pesquisa. Um valor indica `N/A` que a funcionalidade não está disponível na ferramenta de Descoberta eDiscovery correspondente.

|Tarefa de Descoberta eDiscovery  |Pesquisa de conteúdo  |Descoberta Eletrônica Central  |Descoberta Eletrônica Avançada  |
|:---------|:---------|:---------|:---------|
|Pesquisar conteúdo em arquivos criptografados em emails e sites     |Sim      |Sim      |Sim      |
|Visualizar arquivos criptografados anexados ao email     |Sim      |Sim     |Sim       |
|Visualizar documentos criptografados no SharePoint e no OneDrive|Não      |Não    |Sim       |
|Revisar arquivos criptografados em um conjunto de revisão    |N/D      |N/D        | Sim        |
|Exportar arquivos criptografados anexados ao email    |Sim       |Sim  |Sim    |
|Exportar documentos criptografados no SharePoint e no OneDrive    |Não       |Não  |Sim    |
|||||

**Observação:** a Descoberta eDiscovery não dá suporte a arquivos criptografados no SharePoint e no OneDrive quando um rótulo de sensibilidade que aplicou a criptografia é configurado com uma das seguintes configurações:

- Os usuários podem atribuir permissões quando aplicam manualmente o rótulo a um documento. Às vezes, isso é conhecido como *permissões definidas pelo usuário.*<br/>

- O acesso do usuário ao documento tem uma configuração de expiração que é definida para um valor diferente de **Never**.

Para obter mais informações sobre essas configurações, consulte a seção "Definir configurações de criptografia" em Restringir o acesso ao conteúdo usando rótulos de sensibilidade para [aplicar criptografia.](encryption-sensitivity-labels.md#configure-encryption-settings)

Os documentos criptografados com as configurações anteriores ainda podem ser retornados por uma pesquisa de Descoberta eDiscovery. Isso pode acontecer quando uma propriedade de documento (como título, autor ou data de modificação) corresponde aos critérios de pesquisa. Embora esses documentos possam ser incluídos nos resultados da pesquisa, eles não podem ser visualizados ou revisados. Esses documentos também permanecerão criptografados quando são exportados na Descoberta Avançada.

## <a name="requirements-for-decryption-in-ediscovery"></a>Requisitos para descriptografia na Descoberta e

Você precisa ter a função de descriptografar RMS para visualizar, revisar e exportar arquivos criptografados com tecnologias de criptografia da Microsoft. Você também precisa ter essa função atribuída para revisar e consultar arquivos criptografados que são adicionados a um conjunto de revisão na Descoberta Avançada.

Essa função é atribuída por padrão ao grupo de funções Gerente de Descobertas eDiscovery na página **Permissões** no Centro de Conformidade e Segurança & Office 365. Para obter mais informações sobre a função Descriptografar RMS, consulte [Atribuir permissões de Descoberta eDiscovery](assign-ediscovery-permissions.md#rms-decrypt).
