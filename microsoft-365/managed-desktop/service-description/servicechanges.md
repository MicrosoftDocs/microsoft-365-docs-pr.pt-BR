---
title: Mudanças de serviço e comunicação
description: ''
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 879e5dc96cf19c8070769b62f59cca0e409bf1df
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917753"
---
# <a name="service-changes-and-communication"></a>Mudanças de serviço e comunicação

Às vezes, a Microsoft pode precisar alterar detalhes sobre como a Área de Trabalho Gerenciada da Microsoft funciona. Da mesma forma, talvez seja necessário fazer alterações que também afetariam o serviço. Tratamos essas alterações de forma diferente, dependendo do quão significativas elas são. Este tópico define as alterações que consideramos importantes e explica como lidar com elas em relação a outras alterações.



## <a name="changes-made-by-microsoft"></a>Alterações feitas pela Microsoft

Notificação de pelo menos 30 dias antes do tempo para qualquer alteração importante que exija ação. Vamos deixá-lo saber usando o sistema de mensagens do portal de Administração da Área de Trabalho Gerenciada da Microsoft.

**As principais alterações** são aquelas que podem afetar qualquer uma dessas áreas:
- Alterações que afetam a produtividade diária
- Alterações em recursos e aplicativos personalizados
- Aumento ou diminuição da capacidade visível
- Alterações na identidade visual do produto que podem causar confusão ou alteração nos processos de assistência médica e material de referência ou URLs
- Alterações que exigem permissões além das exigidas pelo serviço para operações diárias, excluindo ações que impedem ou corriam problemas
- Alterações no local onde seus dados são armazenados
- Adicionar um novo serviço ou aplicativo de componente ao escopo do serviço
- Remoção de um serviço ou aplicativo de componente do escopo do serviço
- Adicionando novo recurso ao serviço

> [!NOTE]
> Talvez seja preciso fazer alterações para atenuar incidentes ou problemas de segurança que seriam excluídos da política de notificação de 30 dias.

Faremos outras alterações rotineiramente no serviço para melhorar a experiência do usuário, a segurança, a confiabilidade e o relatório. Alguns exemplos dessas alterações incluem:

- Instalação de atualizações do Windows e do Office
- Atualizações para a linha de base de segurança aplicada a dispositivos
- [Supported devices](device-list.md)

Comunicaremos essas alterações usando canais estabelecidos. Se você tiver dúvidas sobre quaisquer alterações, contate a equipe de Operações de Área [de Trabalho Gerenciada da](../working-with-managed-desktop/admin-support.md)Microsoft. As alterações no serviço também são documentadas conforme necessário no histórico [de alterações.](../change-history-managed-desktop.md)

As alterações e comunicações da Área de Trabalho Gerenciada da Microsoft são governadas por duas políticas da Microsoft:
- [Política de Ciclo de Vida Moderna](https://support.microsoft.com/help/30881/modern-lifecycle-policy)
- [Política de Comunicação de Alteração do Microsoft 365](/office365/admin/manage/message-center?view=o365-worldwide)

## <a name="changes-you-make"></a>Alterações feitas

Algumas alterações que você pode fazer em seu ambiente podem afetar a Área de Trabalho Gerenciada da Microsoft. Para essas principais alterações, pedimos que você nos dê pelo menos 30 dias de aviso enviando uma solicitação de serviço no portal de Administração da Área de Trabalho Gerenciada da Microsoft. Consulte [Suporte de administrador para Área de Trabalho Gerenciada](../working-with-managed-desktop/admin-support.md) da Microsoft para obter instruções. Isso nos permite um tempo adequado para planejar e se preparar para a alteração para evitar interrupções.

As principais alterações são aquelas que podem afetar qualquer uma dessas áreas:

- Sistemas e grupos de identidade
- Controles de rede e rede, como firewalls, proxy ou cache, e sistemas VPN
- Controles para acessar configurações de serviços de nuvem
- Certificados de usuário ou dispositivo usados para identidade ou proteção de serviços de rede
- Sistemas de gerenciamento que interagem com o serviço
- Sistemas de segurança ou agentes que interagem com o serviço
- Configuração de qualquer um dos serviços de nuvem do Microsoft 365 associados ou usados pelo serviço

Essas alterações provavelmente não serão disruptivas, portanto, você não precisa nos dizer sobre elas com antecedência:

- Limpeza de objeto órfão
- Adicionar ou remover usuários do serviço
- Configuração do sistema que não tem um impacto material na entrega da Área de Trabalho Gerenciada da Microsoft
- Atualizações de versão do aplicativo, com exceção de aplicativos VPN ou proxy