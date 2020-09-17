---
title: Mudanças de serviço e comunicação
description: ''
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 753ad703a7949b7901ddd76d0d8c966b170461ea
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950313"
---
# <a name="service-changes-and-communication"></a>Mudanças de serviço e comunicação

Às vezes, a Microsoft pode precisar alterar detalhes sobre a maneira como o Microsoft Managed Desktop funciona. Da mesma forma, talvez seja necessário fazer alterações que também afetem o serviço. Tratamos essas alterações de forma diferente, dependendo do quão significativas elas estão. Este tópico define as alterações que consideramos principal e explica como lidar com elas em comparação com outras alterações.



## <a name="changes-made-by-microsoft"></a>Alterações feitas pelo Microsoft

Você receberá um aviso pelo menos 30 dias antes do momento para qualquer alteração principal que exija a ação. Vamos informá-lo usando o sistema de mensagens do portal de administração de área de trabalho gerenciada da Microsoft.

**Alterações principais** são aquelas que podem afetar qualquer uma destas áreas:
- Alterações que afetam a produtividade diária
- Alterações em recursos e aplicativos personalizados
- Aumento ou redução da capacidade visível
- Alterações na identidade visual do produto que podem causar confusão ou alterações nos processos da assistência técnica e material de referência ou URLs
- Alterações que exigem permissões além daquelas exigidas pelo serviço para operações diárias, excluindo ações que impedem ou corrim problemas
- Alterações no local onde seus dados estão armazenados
- Adicionar um novo serviço de componente ou aplicativo ao escopo do serviço
- Remoção de um serviço de componente ou aplicativo do escopo do serviço
- Adicionando novo recurso ao serviço

> [!NOTE]
> Talvez seja necessário fazer alterações para atenuar incidentes ou problemas de segurança que seriam excluídos da política de notificação de 30 dias.

Faremos uma rotina com outras alterações no serviço para melhorar a experiência, segurança, confiabilidade e relatórios do usuário. Alguns exemplos dessas alterações incluem:

- Instalação de atualizações do Windows e do Office
- Atualizações para a linha de base de segurança aplicada a dispositivos
- [Supported devices](device-list.md)

Comunicaremos essas alterações usando canais estabelecidos. Em caso de dúvidas sobre qualquer alteração, entre em contato com a [equipe de operações](../working-with-managed-desktop/admin-support.md)de área de trabalho gerenciada da Microsoft. As alterações no serviço também são documentadas conforme necessário no [histórico de alterações](../change-history-managed-desktop.md).

As alterações e comunicações de área de trabalho gerenciada da Microsoft são regidas por duas políticas da Microsoft:
- [Política de ciclo de vida moderno](https://support.microsoft.com/help/30881/modern-lifecycle-policy)
- [Política de comunicação de alteração da Microsoft 365](https://docs.microsoft.com/office365/admin/manage/message-center?redirectSourcePath=%252fen-us%252farticle%252fMessage-center-in-Office-365-38FB3333-BFCC-4340-A37B-DEDA509C2093&view=o365-worldwide)

## <a name="changes-you-make"></a>Alterações feitas

Algumas alterações que você pode fazer em seu ambiente podem afetar a área de trabalho gerenciada da Microsoft. Para essas alterações principais, pedimos que você nos dê pelo menos 30 dias ' para o envio de uma solicitação de serviço no portal de administração de área de trabalho gerenciada da Microsoft. Consulte [admin support for Microsoft Managed desktop](../working-with-managed-desktop/admin-support.md) para obter instruções. Isso nos permite um tempo adequado para planejar e preparar a alteração, para evitar interrupções.

Alterações principais são aquelas que podem afetar qualquer uma destas áreas:

- Sistemas e grupos de identidade
- Controles de rede e rede, como firewalls, proxy ou cache e sistemas VPN
- Controles para acessar configurações de serviços de nuvem
- Certificados de usuário ou de dispositivo usados para identidade ou proteção de serviços de rede
- Sistemas de gerenciamento que interagem com o serviço
- Sistemas de segurança ou agentes que interagem com o serviço
- Configuração de qualquer um dos serviços de nuvem do Microsoft 365 associados ao ou usado pelo, o serviço

Essas alterações provavelmente não causarão interrupções, portanto, você não precisa nos informar sobre elas antes do tempo:

- Limpeza de objeto órfão
- Adicionando ou removendo usuários do serviço
- Configuração do sistema que não tem um impacto material na entrega da área de trabalho gerenciada da Microsoft
- Atualizações da versão do aplicativo, com exceção de aplicativos de VPN ou proxy


