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
ms.openlocfilehash: 6cdf29493a3fd95b060c52d9f9587ee34748edde
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372516"
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
> Para garantir a integridade, a tabela inclui colunas para um registro bloqueado e desbloqueado, aplicável ao SharePoint e OneDrive, mas não ao Exchange. A capacidade de bloquear e desbloquear um registro usa o [controle de versão do registro](#record-versioning) que não tem suporte para itens do Exchange. Portanto, para todos os itens do Exchange marcados como registro, o comportamento é mapeado para a coluna **Registro - bloqueado** e a coluna **Registro - desbloqueado** não é relevante.


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


## <a name="using-retention-labels-to-declare-records"></a>Usando rótulos de retenção para declarar registros

Ao criar um rótulo de retenção, você tem a opção de usá-lo para classificar o conteúdo como um registro:

1. No centro de conformidade do Microsoft 365, vá para **Gerenciamento de Registros** \> **Plano de Arquivo**. Na página **Planejamento de arquivos**, clique em **Criar um rótulo**.

2. Na página **Configurações de rótulo** no assistente, escolha a opção para classificar o conteúdo como registro.
    
   ![Clique em Usar rótulo para classificar o conteúdo como uma caixa de seleção de Registro](../media/recordversioning6.png)

3. Aplique o rótulo de retenção aos documentos do SharePoint ou OneDrive e emails do Exchange, conforme necessário. Para obter instruções:
    
    - [Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)
    
    - [Aplicar um rótulo de retenção automaticamente ao conteúdo](apply-retention-labels-automatically.md)

### <a name="applying-the-configured-retention-label-to-content"></a>Aplicando o rótulo de retenção configurado ao conteúdo

Quando os rótulos de retenção que marcam o conteúdo como registro são disponibilizados para os usuários aplicá-los nos aplicativos:

- Para o Exchange, qualquer usuário com acesso de gravação à caixa de correio pode aplicar esses rótulos. 
- Para o SharePoint e OneDrive, qualquer usuário no grupo Membros padrão (o nível de permissão de Contribuição) pode aplicar esses rótulos.

Exemplo de um documento marcado como registro usando um rótulo de retenção:

![Painel de detalhes do documento marcado como um registro](../media/recordversioning7.png)

## <a name="record-versioning"></a>Controle de versão do registro

A capacidade de marcar um documento como registro e restringir as ações que podem ser executadas no registro é uma meta essencial para qualquer solução de gerenciamento de registros. No entanto, a colaboração também pode ser necessária para as pessoas criarem versões posteriores.

Por exemplo, você pode marcar um contrato de vendas como registro, mas precisa atualizar o contrato com novos termos e marcar a versão mais recente como novo registro enquanto ainda mantém a versão do registro anterior. Para esses tipos de cenários, o SharePoint e o OneDrive oferecem suporte ao *controle de versão do registro*. As pastas do bloco de anotações do OneNote não oferecem suporte ao controle de versão do registro.

Para usar a versão do registro, primeiro rotule o documento e marque-o como registro. Nesse momento, uma propriedade do documento, chamada *Status do registro* será exibida ao lado do rótulo de retenção e o status inicial do registro será **Bloqueado**. 

Agora, você pode fazer o seguinte:

  - **Editar e reter continuamente versões individuais do documento como registros, desbloqueando e bloqueando a propriedade de Status do registro.** Somente quando a propriedade **Status do registro** é definida como **Bloqueado** será mantida uma nova versão do registro. Essa alternância entre bloqueado e desbloqueado reduz o risco de manter versões e cópias desnecessárias do documento.

  - **Ter os registros armazenados automaticamente em um repositório de registros in-loco, localizado no conjunto de sites.** Cada conjunto de sites no SharePoint e no OneDrive preserva o conteúdo em sua biblioteca de Retenção para Preservação. As versões de registro são armazenadas na pasta Registros nesta biblioteca.

  - **Manter um documento perene que contenha todas as versões.** Por padrão, cada documento do SharePoint e do OneDrive têm um histórico de versão disponível no menu do item. Nesse histórico de versão, você pode ver facilmente quais versões são registros e exibir esses documentos.

O controle de versão do registro está disponível automaticamente para qualquer documento que tenha um rótulo de retenção que marque o item como registro. Quando um usuário exibe as propriedades do documento usando o painel de detalhes, eles podem alternar o **Status do registro** de **Bloqueado** para **Desbloqueado**. Essa ação cria um registro na pasta Registros na Biblioteca de Retenção para Preservação, onde reside pelo restante do período de retenção. 

Enquanto o documento está desbloqueado, qualquer usuário com permissões de edição padrão pode editar o arquivo. No entanto, os usuários não podem excluir o arquivo, porque ele continua sendo um registro. Quando a edição estiver concluída, o usuário poderá alternar o **Status do registro** de **Desbloqueado** para **Bloqueado**, o que impede novas edições enquanto estiver nesse status.
<br/><br/>

![Propriedade do status do registro no documento marcado como um registro](../media/recordversioning8.png)

### <a name="locking-and-unlocking-a-record"></a>Bloqueando e desbloqueando um registro

Depois que um rótulo de retenção que marca o conteúdo como registro é aplicado a um documento, qualquer usuário com permissões de Contribuição ou com um nível de permissão mais restrito pode desbloquear um registro ou bloquear um registro desbloqueado.
<br/><br/>

![O status do registro mostra que o documento de registro está desbloqueado](../media/recordversioning9.png)

Quando um usuário desbloqueia um registro, as seguintes ações ocorrem:

1. Se o conjunto de sites atual não tiver uma biblioteca de Retenção para Preservação, ela será criada.

2. Se a biblioteca de Retenção para Preservação não tiver uma pasta Registros, ela será criada.

3. Uma ação de **Copiar para** copia a versão mais recente do documento para a pasta Registros. A ação **Copiar para** inclui apenas a versão mais recente e nenhuma das versões anteriores. Este documento copiado agora é considerado uma versão de registro do documento e o nome do arquivo tem o formato: \[Versão GUID Título\#\]

4. A cópia criada na pasta Registros é adicionada ao histórico da versão do documento original, e esta versão mostra a palavra **Registro** no campo de comentários.

5. O documento original é uma nova versão que pode ser editada, mas não excluída. A coluna da biblioteca de documentos **Item é um Registro** ainda mostra o valor **Sim** porque o documento continua sendo um registro, mesmo que agora possa ser editado.

Quando um usuário bloqueia um registro, o documento original não poderá ser editado novamente. Mas é a ação de desbloquear um registro que copia uma versão para a pasta Registros na biblioteca de Retenção para Preservação.

### <a name="record-versions"></a>Versões de registro

Sempre que um usuário desbloqueia um registro, a versão mais recente é copiada para a pasta Registros na biblioteca de Retenção para Preservação, e essa versão contém o valor de **Registro** no campo **Comentários** do histórico da versão.
<br/><br/>

![Registro mostrado na biblioteca de Retenção para Preservação](../media/recordversioning10.png)

Para exibir o histórico da versão, escolha um documento na biblioteca de documentos e clique em **Histórico da Versão** no menu do item.

### <a name="where-records-are-stored"></a>Onde os registros são armazenados

Os registros são armazenados na pasta Registros na biblioteca de Retenção para Preservação no site de nível superior do conjunto de sites. Na barra de navegação à esquerda no site de nível superior, escolha **Conteúdos do site** \> **Biblioteca de Retenção para Preservação**.
<br/><br/>

![Biblioteca de Retenção para Preservação](../media/recordversioning11.png)

<br/><br/>

![A pasta Registros na biblioteca de Retenção para Preservação](../media/recordversioning12.png)

A biblioteca de Retenção para Preservação está visível somente para administradores de conjuntos de sites. Além disso, a biblioteca de Retenção para Preservação não existe por padrão. Ela é criada apenas quando o conteúdo sujeito a um rótulo ou política de retenção é excluído pela primeira vez do conjunto de sites.

### <a name="searching-the-audit-log-for-record-versioning-events"></a>Pesquisando o log de auditoria para eventos de controle de versão do registro

As ações de bloqueio e desbloqueio de registros são registradas no log de auditoria. Você pode pesquisar pelas atividades específicas **Status do registro alterado para bloqueado** e **Status do registro alterado para desbloqueado**, que estão localizadas na seção **Atividades de arquivo e página** na lista suspensa de **Atividades** na página de **Pesquisa de log de auditoria** no centro de conformidade e segurança.
<br/><br/>

![Pesquisar o log de auditoria para eventos de controle de versão do registro](../media/recordversioning13.png)

Para obter mais informações sobre a pesquisa desses eventos, confira a seção "Atividades de arquivo e página" em [Pesquisar o log de auditoria no Centro de Conformidade e Segurança](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).

## <a name="next-steps"></a>Próximas etapas

Se você ainda não tiver rótulos de retenção para usar o gerenciamento de registros, confira [Introdução aos rótulos de retenção e políticas de retenção](get-started-with-retention.md).

Para saber mais sobre a disposição de registros, confira [Disposição de conteúdo](disposition.md).
