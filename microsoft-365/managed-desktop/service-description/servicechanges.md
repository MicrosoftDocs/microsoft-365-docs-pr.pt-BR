---
title: Mudanças de serviço e comunicação
description: Como as alterações no serviço ocorrem e são comunicadas
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 20af244d14f8f29e0175fb5e8efdabff94ff9a2b
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244099"
---
# <a name="service-changes-and-communication"></a>Mudanças de serviço e comunicação

Às vezes, a Microsoft pode precisar alterar detalhes sobre como Área de Trabalho Gerenciada da Microsoft funciona. Da mesma forma, talvez seja necessário fazer alterações que também afetariam o serviço. Tratamos essas alterações de forma diferente, dependendo do quão significativas elas são. Este tópico define as alterações que consideramos importantes e explica como lidar com elas em relação a outras alterações.



## <a name="changes-made-by-microsoft"></a>Alterações feitas pela Microsoft

Notificação de pelo menos 30 dias antes do tempo para qualquer alteração importante que exija ação. Vamos deixá-lo saber usando o sistema de mensagens do portal de administração Área de Trabalho Gerenciada da Microsoft administrador.

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

- Instalação de Windows e Office atualizações
- Atualizações para a linha de base de segurança aplicada a dispositivos
- Dispositivos com suporte. Para ver os dispositivos recomendados, filtre Área de Trabalho Gerenciada da Microsoft no site de Windows 10 Pro [de negócios](https://www.microsoft.com/windowsforbusiness/view-all-devices) da Loja.

Comunicaremos essas alterações usando canais estabelecidos. Se você tiver alguma dúvida sobre quaisquer alterações, contate a equipe Área de Trabalho Gerenciada da Microsoft [Operações](../working-with-managed-desktop/admin-support.md). As alterações no serviço também são documentadas conforme necessário no histórico [de alterações.](../change-history-managed-desktop.md)

Área de Trabalho Gerenciada da Microsoft alterações e comunicações são governadas por duas políticas da Microsoft:
- [Política de ciclo de vida moderna](https://support.microsoft.com/help/30881/modern-lifecycle-policy)
- [Microsoft 365 Alterar Política de Comunicação](/office365/admin/manage/message-center)

## <a name="changes-you-make"></a>Alterações feitas

Algumas alterações que você pode fazer em seu ambiente podem afetar Área de Trabalho Gerenciada da Microsoft. Para essas principais alterações, pedimos que você nos dê pelo menos 30 dias de aviso enviando uma solicitação de serviço no portal Área de Trabalho Gerenciada da Microsoft Administrador. Consulte [Suporte de administrador para Área de Trabalho Gerenciada da Microsoft](../working-with-managed-desktop/admin-support.md) para obter instruções. Isso nos permite um tempo adequado para planejar e se preparar para a alteração para evitar interrupções.

As principais alterações são aquelas que podem afetar qualquer uma dessas áreas:

- Sistemas e grupos de identidade
- Controles de rede e rede, como firewalls, proxy ou cache, e sistemas VPN
- Controles para acessar configurações de serviços de nuvem
- Certificados de usuário ou dispositivo usados para identidade ou proteção de serviços de rede
- Sistemas de gerenciamento que interagem com o serviço
- Sistemas de segurança ou agentes que interagem com o serviço
- Configuração de qualquer um dos Microsoft 365 de nuvem associados ou usados pelo serviço

Essas alterações provavelmente não serão disruptivas, portanto, você não precisa nos dizer sobre elas com antecedência:

- Limpeza de objeto órfão
- Adicionar ou remover usuários do serviço
- Configuração do sistema que não tem um impacto material na entrega do Área de Trabalho Gerenciada da Microsoft
- Atualizações de versão do aplicativo, com exceção de aplicativos VPN ou proxy