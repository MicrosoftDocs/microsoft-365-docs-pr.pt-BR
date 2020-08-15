---
title: Saiba mais sobre os registros
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Saiba mais sobre os registros para ajudá-lo na implementação de uma solução de gerenciamento de registros no Microsoft 365.
ms.openlocfilehash: e64e91aeef307d05f23c47987a84baaf386324df
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685437"
---
# <a name="learn-about-records"></a>Saiba mais sobre os registros

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

O gerenciamento de registros no Microsoft 365 ajuda a organização a cumprir políticas corporativas, e obrigações legais ou regulamentares, além de reduzir riscos e responsabilidades legais.

Quando o conteúdo é marcado como registro:

- Restrições são colocadas nos itens em termos de quais [ações são permitidas ou bloqueadas](#compare-restrictions-for-what-actions-are-allowed-or-blocked).

- Atividades adicionais sobre o item são registradas.

- Você tem prova de disposição quando os itens são excluídos no final do período de retenção.

Você usa [rótulos de retenção](retention.md#retention-labels) para marcar conteúdos como registros. É possível publicar esses rótulos para que usuários e administradores possam aplicá-los manualmente ou automaticamente ao conteúdo que você deseja classificar como registro.

Usando rótulos de retenção para marcar o conteúdo como registro, você pode implementar uma estratégia única e consistente para gerenciar registros no ambiente do Microsoft 365.

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>Comparar restrições para quais ações são permitidas ou bloqueadas

Use a tabela a seguir para identificar quais restrições são impostas ao conteúdo como resultado da aplicação de um rótulo de retenção padrão e rótulos de retenção que marcam o conteúdo como registro. 

Um rótulo de retenção padrão tem a configuração de retenção de dados sem marcar o conteúdo como registro.

>[!NOTE] 
> Para garantir a integridade, a tabela inclui colunas para um registro bloqueado e desbloqueado, aplicável ao SharePoint e OneDrive, mas não ao Exchange. A capacidade de bloquear e desbloquear um registro usa o [controle de versão do registro](record-versioning.md) que não tem suporte para itens do Exchange. Portanto, para todos os itens do Exchange marcados como registro, o comportamento é mapeado para a coluna **Registro - bloqueado** e a coluna **Registro - desbloqueado** não é relevante.


|Action| Rótulo de retenção |Registro - bloqueado| Registro - desbloqueado|
|:-----|:-----|:-----|:-----|:-----|
|Editar conteúdo|Permitido | **Bloqueado** | Permitido|
|Editar propriedades, incluindo renomear|Permitido |Permitido | Permitido|
|Excluir|Permitido <sup>1</sup> |**Bloqueado** | **Bloqueado**|
|Copiar|Permitido |Permitido | Permitido|
|Mover dentro do contêiner <sup>2</sup>|Permitido |Permitido | Permitido|
|Mover entre contêineres <sup>2</sup>|Permitido |Permitido se nunca desbloqueado | Permitido|
|Abrir/Ler|Permitido |Permitido | Permitido|
|Alterar rótulo|Permitido |Permitido - somente administrador do contêiner | Permitido - somente administrador do contêiner|
|Remover rótulo|Permitido |Permitido - somente administrador do contêiner | Permitido - somente administrador do contêiner|

Notas de rodapé:

<sup>1</sup> Com suporte do OneDrive e Exchange, mantendo uma cópia em um local seguro, mas bloqueado pelo SharePoint.

Mensagem que um usuário vê se tentar excluir um documento rotulado no SharePoint:

![Mensagem informando que o item não foi excluído do SharePoint](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<sup>2</sup> Os contêineres incluem bibliotecas de documentos do SharePoint e caixas de correio do Exchange.

## <a name="next-steps"></a>Próximas etapas

Se você ainda não tiver rótulos de retenção para usar o gerenciamento de registros, confira [Introdução aos rótulos de retenção e políticas de retenção](get-started-with-retention.md).

Para marcar o conteúdo como registro, confira [Declarar registros usando rótulos de retenção](declare-records.md).
