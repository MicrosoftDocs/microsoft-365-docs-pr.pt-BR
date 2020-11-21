---
title: Atribuir e concluir ações de aperfeiçoamento no Gerenciador de conformidade da Microsoft
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Saiba como executar a implementação e os testes nos controles do Gerenciador de conformidade da Microsoft. Atribuir trabalho, documentação de armazenamento e relatórios de exportação.
ms.openlocfilehash: 4b7ece89752a2c3e54a0a69bade2f489feacd0c3
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376522"
---
# <a name="assign-and-complete-improvement-actions-in-compliance-manager"></a>Atribuir e concluir ações de aperfeiçoamento no gerente de conformidade

**Neste artigo:** Este artigo explica como **gerenciar seu fluxo de trabalho de conformidade** com ações aprimoradas. Saiba como **atribuir ações de melhoria** para implementação e teste, **gerenciar atualizações** e exportar **relatórios**.

## <a name="manage-compliance-workflows-with-improvement-actions"></a>Gerenciar fluxos de trabalho de conformidade com ações de melhoria

As ações de melhoria centralizam suas atividades de conformidade. Cada ação de melhoria fornece orientações detalhadas de implementação para ajudá-lo a se alinhar com regulamentos e padrões de proteção de dados. As ações podem ser atribuídas aos usuários em sua organização para executar o trabalho de implementação e teste. Você também pode armazenar documentação, anotações e registrar as atualizações de status dentro da ação.

Todas as ações de aperfeiçoamento são listadas na página ações de aprimoramento. Saiba mais sobre como [exibir suas ações de aprimoramento](compliance-manager-setup.md#improvement-actions-page).

## <a name="improvement-actions-details-page"></a>Página de detalhes de ações de melhoria

Cada ação de melhoria tem uma página de detalhes mostrando seu status atual, os padrões relacionados e os requisitos normativos e a orientação de implementação recomendada. As [ações técnicas](compliance-score-calculation.md#technical-and-non-technical-actions) incluem um link **Iniciar agora** que leva você à solução apropriada para implementação. Você pode anexar a documentação de implementação e teste diretamente à página de detalhes de uma ação de aprimoramento.

Para exibir a página de detalhes de uma ação de aprimoramento:

1. Vá para a página ações de aprimoramento.
2. Selecione a linha da ação de aprimoramento pretendida, que abre sua página de detalhes.

Você pode facilmente exibir a ação de aperfeiçoamento seguinte ou anterior na lista selecionando a seta para cima ou para baixo no canto superior direito da tela. Se você tiver filtrado sua lista na página ações de melhoria, a movimentação para cima ou para baixo levará você para o próximo item dentro da lista filtrada.

## <a name="assign-improvement-actions"></a>Atribuir ações de melhoria

Para iniciar o trabalho de implementação em uma ação de melhoria, você pode fazer o próprio trabalho ou atribuí-lo a outro usuário. A pessoa atribuída pode ser:

- Um proprietário de política da empresa
- Um implementador de TI
- Outro funcionário com responsabilidade de realizar a tarefa

Depois de identificar o destinatário apropriado, certifique-se de que ele tenha uma [função de gerente de conformidade](compliance-manager-setup.md#set-user-permissions-and-assign-roles) suficiente para executar o trabalho. Siga as etapas abaixo para atribuir a ação de aprimoramento:

1. Na página detalhes das ações de melhoria, selecione **Editar o status** próximo da seção superior esquerda da tela.

2. No painel de atalho editar status, selecione a caixa **atribuído a** para mostrar uma lista de **pessoas sugerida** dos usuários. Você pode selecionar o usuário na lista ou digitar o endereço de email da pessoa à qual deseja atribuí-lo.

3. Selecione **salvar e fechar**. O usuário atribuído receberá um email explicando que a ação de aprimoramento foi atribuída a eles, com um link direto para a ação de aprimoramento. (Observação: os clientes grandes da Comunidade do governo dos EUA (GCC) não receberão um email quando as ações forem atribuídas a eles.)

O usuário atribuído pode então executar as ações recomendadas.

## <a name="perform-work-and-store-documentation"></a>Executar documentação de trabalho e armazenamento

Você pode carregar arquivos e notas relacionados à implementação e ao trabalho de teste diretamente na seção **observações e documentação** . Esse ambiente é um repositório seguro e centralizado para ajudá-lo a demonstrar a satisfação dos controles para atender aos padrões e às normas de conformidade. Qualquer usuário com acesso somente leitura pode ler o conteúdo desta seção. Somente os usuários com direitos de edição podem carregar e baixar arquivos e inserir ou editar anotações.

A seção **notas e documentação** contém campos para documentos carregados, notas de implementação, notas de teste e anotações adicionais.

#### <a name="uploaded-documents"></a>Documentos carregados

- Selecione **gerenciar documentos** para carregar qualquer arquivo relevante.
- Quando o painel gerenciar documentos for aberto, selecione **Adicionar documento** e, em seguida, selecione o arquivo do seu sistema. Tipos de arquivo aceitos:
    - Documentos (. doc,. xls,. ppt,. txt,. pdf)
    - Imagens (. jpg,. png)
    - Vídeo (. mkv)
    - Arquivos compactados (. zip,. rar)
- Depois que o arquivo resolver no painel, selecione **fechar**, que salva automaticamente o anexo de arquivo. Em seguida, você verá o arquivo listado em **documentos carregados**.
- Para baixar ou excluir o documento, selecione **gerenciar documentos** abaixo da lista de documentos. No painel de submenu, selecione a linha de documento para realçá-la e, em seguida, selecione **baixar** ou **excluir**.

#### <a name="implementation-notes-test-notes-and-additional-notes"></a>Notas de implementação, notas de teste e notas adicionais

- Para adicionar anotações em qualquer um desses três campos, selecione **editar notas de implementação** abaixo de qualquer um desses campos.
- Quando o painel de submenu abrir, insira notas no campo de texto e, em seguida, selecione **salvar e fechar**.
- Para editar anotações, selecione **editar notas de implementação**, faça suas edições e, em seguida, selecione **salvar e fechar**.

Não há um limite de caracteres nos campos anotações. Recomendamos manter o Notes Brief para que você possa exibi-los facilmente e editá-los da página de detalhes de ações de melhoria.

## <a name="change-improvement-action-status"></a>Alterar status da ação de melhoria

Você pode registrar o status e a data de implementação e o status e a data do teste para cada ação de aprimoramento. Os campos de **status** de **implementação** e teste podem ser editados por qualquer usuário com permissões de edição, não apenas pela pessoa atribuída.

Para editar o status de uma ação de aprimoramento, selecione **Editar status** na seção superior esquerda da página de detalhes. Veja a seguir os campos disponíveis e as opções de status:

- **Status de implementação**
    - **Não implementado** -ação ainda não implementada
    - **Implementado** -ação implementada
    - **Implementação alternativa** -Selecione esta opção se você usou outras ferramentas de terceiros ou executou outras ações não incluídas nas recomendações da Microsoft
    - **Planejado** -a ação é planejada para implementação
    - **Fora do escopo** – a ação não é relevante para sua organização e não contribui para sua pontuação
- **Data de implementação**: disponível para selecionar quando o status da implementação for "implementado" ou "implementação alternativa"
- **Status do teste**: disponível para selecionar quando o status da implementação for "implementado" ou "implementação alternativa":
    - **Não avaliado** – a ação não foi testada
    - **Passed** -a implementação foi verificada por um consultor
    - Falha nos testes de **baixo risco** , baixo risco
    - Falha no teste de **risco médio** , risco médio
    - **Alto risco com falha** – falha no teste, alto risco
    - **Fora do escopo** – a ação está fora do escopo da avaliação e não contribui para sua pontuação
- **Data do teste**: alternar o pop-up calendário para selecionar a data

Ações comuns sincronizam entre grupos. Quando duas avaliações diferentes no mesmo grupo ações de melhorias de compartilhamento são gerenciadas por você, todas as atualizações feitas nos detalhes ou no status da implementação da ação serão automaticamente sincronizadas com a mesma ação em qualquer outra avaliação do grupo. Essa sincronização permite implementar uma ação de melhoria e atender a vários requisitos em várias regulamentações.

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Atribuir ação de aprimoramento a consultor para conclusão

Depois de concluir o trabalho, realizar testes e carregar evidências, a próxima etapa é atribuir a ação de aprimoramento a um consultor para validação. O consultor valida o trabalho e examina a documentação e seleciona o status de teste apropriado.

**Se o status do teste for definido como "Passed"**: a ação será concluída e os pontos obtidos mostrarão o máximo de pontos alcançado. Os pontos são então contados em relação à pontuação de conformidade geral.

**Se o status do teste for definido como "failed"**: a ação não atende aos requisitos, e o consultor pode atribuí-lo de volta para o usuário apropriado para trabalho adicional.

## <a name="accepting-updates-to-improvement-actions"></a>Aceitar atualizações para ações de melhoria

Quando uma atualização estiver disponível para uma ação de melhoria, você verá uma notificação ao lado do seu nome. Você pode aceitar ou adiar a atualização para um momento posterior.

#### <a name="what-causes-an-update"></a>O que causa uma atualização

Uma atualização ocorre quando há alterações relacionadas à pontuação, automação ou escopo. As alterações podem envolver novas orientações para ações de melhoria com base nas alterações regulamentadoras ou podem ocorrer devido a alterações no produto. Somente as ações de melhoria gerenciadas por suas organizações recebem notificações de atualização.

#### <a name="where-youll-see-assessment-update-notifications"></a>Onde você verá as notificações de atualização de avaliação

Quando uma ação de melhoria for atualizada, você verá um rótulo de **atualização pendente** ao lado do seu nome na página ações de aprimoramento e na página detalhes de suas avaliações relacionadas.

Vá para a página de detalhes da ação de aprimoramento e selecione o botão **examinar atualização** na faixa superior para revisar os detalhes sobre as alterações e aceitar ou adiar a atualização.

#### <a name="review-update-to-accept-or-defer"></a>Revisar atualização para aceitar ou adiar

Após selecionar a **atualização de revisão** na página de detalhes da ação de melhoria, um painel de submenu aparece no lado direito da tela. O painel de submenus fornece detalhes importantes sobre a atualização, como as avaliações afetadas e alterações na pontuação e no escopo.

Selecione **aceitar atualização** para aceitar todas as alterações na ação de aprimoramento. **As alterações aceitas são permanentes**.

> [!NOTE]
> Quando você aceita uma atualização para uma ação, você também está aceitando atualizações para outras versões ou instâncias dessa ação. As atualizações propagarão todo o locatário para as ações técnicas e propagarão todo o grupo para ações não técnicas.

Se você selecionar **Cancelar**, a atualização não será aplicada à ação de melhoria. No entanto, você continuará a ver a notificação de **atualização pendente** até aceitar a atualização.

**Por que recomendamos aceitar atualizações**

A aceitação de atualizações ajuda a garantir que você tenha a orientação mais atualizada sobre como usar soluções e tomar as ações apropriadas de melhorias para ajudá-lo a atender aos requisitos de certificação em mãos.

**Por que você pode querer adiar uma atualização**

Se você estiver no meio da conclusão de uma avaliação que inclui a ação de melhoria, talvez seja conveniente garantir que você tenha concluído o trabalho nele antes de aceitar a atualização. Você pode adiar a atualização mais tarde selecionando **Cancelar** no painel revisar atualização de submenu.

## <a name="export-a-report"></a>Exportar um relatório

Selecione **Exportar** no canto superior esquerdo da tela para baixar uma planilha do Excel que contenha todas as ações de aperfeiçoamento e as categorias de filtro mostradas na página ações de aprimoramento.