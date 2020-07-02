---
title: Trabalhar com ações de melhoria na pontuação de conformidade da Microsoft (visualização)
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
description: Saiba como gerenciar suas atividades de conformidade na pontuação de conformidade da Microsoft trabalhando com ações de melhoria.
ms.openlocfilehash: d10e04f144595e1976f4b20e894ccbc299aade7b
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016561"
---
# <a name="work-with-improvement-actions-in-compliance-score-preview"></a>Trabalhar com ações de melhorias na pontuação de conformidade (visualização)

**Neste artigo:** Este artigo explica como **gerenciar seu fluxo de trabalho de conformidade** com ações aprimoradas. Saiba como **atribuir ações de melhoria** para implementação e teste, atribuí-las aos avaliadores de conclusão e exportar **relatórios**.

## <a name="manage-compliance-workflows-with-improvement-actions"></a>Gerenciar fluxos de trabalho de conformidade com ações de melhoria

As ações de melhoria centralizam suas atividades de conformidade. Cada ação de melhoria fornece orientações detalhadas de implementação para ajudá-lo a se alinhar com regulamentos e padrões de proteção de dados. As ações podem ser atribuídas aos usuários em sua organização para executar o trabalho de implementação e teste. Você também pode armazenar documentação, anotações e registrar as atualizações de status na ação de melhoria.

Todas as suas melhorias estão listadas na página ações de melhoria. Saiba mais sobre [como filtrar a exibição de suas ações de aprimoramento e interpretar Estados de status](compliance-score-setup.md#improvement-actions-page).

## <a name="improvement-actions-details-page"></a>Página de detalhes de ações de melhoria

Cada ação de melhoria tem uma página de detalhes mostrando seu status atual e os padrões relacionados e os requisitos normativos. Diretrizes detalhadas de implementação inclui um link **Iniciar agora** levando você para a solução apropriada para implementação. Você pode anexar a documentação de implementação e teste diretamente à página de detalhes de uma ação de aprimoramento.

Para exibir a página de detalhes de uma ação de aprimoramento:

1. Vá para a página ações de aprimoramento.
2. Selecione a linha da ação de aprimoramento pretendida, que abre sua página de detalhes.

Você pode facilmente exibir a ação de aperfeiçoamento seguinte ou anterior na lista selecionando a seta para cima ou para baixo no canto superior direito da tela. Se você tiver filtrado sua lista na página ações de melhoria, a movimentação para cima ou para baixo levará você para o próximo item dentro da lista filtrada.

## <a name="assign-improvement-actions"></a>Atribuir ações de melhoria

Para iniciar o trabalho de implementação em uma ação de melhoria, você pode fazer o próprio trabalho ou atribuí-lo a outro usuário. A pessoa atribuída pode ser:

- Um proprietário de política da empresa
- Um implementador de TI
- Outro funcionário com responsabilidade de realizar a tarefa

Depois de identificar o destinatário apropriado, certifique-se de que ele tenha uma [função suficiente na pontuação de conformidade](compliance-score-setup.md#set-user-permissions-and-assign-roles) (administrador de conformidade, administrador de dados de conformidade, administrador de segurança ou administrador global) para executar o trabalho e siga estas etapas:

1. Na página detalhes das ações de melhoria, selecione **Editar o status** próximo da seção superior esquerda da tela.

2. No painel de atalho editar status, selecione a caixa **atribuído a** para mostrar uma lista de **pessoas sugerida** dos usuários. Você pode selecionar o usuário na lista ou digitar o endereço de email da pessoa à qual deseja atribuí-lo.

3. Selecione **salvar e fechar**. O usuário atribuído receberá um email informando que a ação de aprimoramento foi atribuída a eles e, em seguida, poderá abrir a ação de aperfeiçoamento no painel.

O usuário atribuído pode então executar as ações recomendadas.

## <a name="perform-work-and-store-documentation"></a>Executar documentação de trabalho e armazenamento

Você pode carregar arquivos e notas relacionados à implementação e ao trabalho de teste diretamente na seção **observações e documentação** . Esse ambiente é um repositório seguro e centralizado para ajudá-lo a demonstrar a satisfação dos controles para atender aos padrões e às normas de conformidade. Qualquer usuário com acesso somente leitura pode ler o conteúdo desta seção. Somente os usuários com direitos de edição podem carregar e baixar arquivos e inserir ou editar anotações.

Os campos da seção **notas e documentação** incluem:

### <a name="uploaded-documents"></a>Documentos carregados

- Selecione **gerenciar documentos** para carregar qualquer arquivo relevante.
- Quando o painel gerenciar documentos for aberto, selecione **Adicionar documento**e, em seguida, selecione o arquivo do seu sistema. Tipos de arquivo aceitos:
    - Documentos (. doc,. xls,. ppt,. txt,. pdf)
    - Imagens (. jpg,. png)
    - Vídeo (. mkv)
    - Arquivos compactados (. zip,. rar)
- Depois que o arquivo resolver no painel, selecione **fechar**, que salva automaticamente o anexo de arquivo. Em seguida, você verá o arquivo listado em **documentos carregados**.
- Para baixar ou excluir o documento, selecione **gerenciar documentos** abaixo da lista de documentos. No painel de submenu, clique ou toque na linha de documento para realçá-lo e, em seguida, selecione **baixar** ou **excluir**.

### <a name="implementation-notes-test-notes-and-additional-notes"></a>Notas de implementação, notas de teste e notas adicionais

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
    - **Não está no escopo** – a ação não é relevante para sua organização e não contribui para sua pontuação
- **Data de implementação**: disponível para selecionar quando o status da implementação for "implementado" ou "implementação alternativa"
- **Status do teste**: disponível para selecionar quando o status da implementação for "implementado" ou "implementação alternativa":
    - **Não avaliado** – a ação não foi testada
    - **Passed**-a implementação foi verificada por um consultor
    - Falha nos testes de **baixo risco** , baixo risco
    - Falha no teste de **risco médio** , risco médio
    - **Alto risco com falha** – falha no teste, alto risco
    - **Não está no escopo** – a ação está fora do escopo da avaliação e não contribui para a sua pontuação
- **Data do teste**: alternar o pop-up calendário para selecionar a data

Ações comuns sincronizam entre grupos. Quando duas avaliações diferentes no mesmo grupo ações de melhorias de compartilhamento são gerenciadas por você, todas as atualizações feitas nos detalhes ou no status da implementação da ação serão automaticamente sincronizadas com a mesma ação em qualquer outra avaliação do grupo. Essa sincronização permite implementar uma ação de melhoria e atender a vários requisitos em várias regulamentações.

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Atribuir ação de aprimoramento a consultor para conclusão

Depois de concluir o trabalho, realizar testes e carregar evidências, a próxima etapa é atribuir a ação de aprimoramento a um consultor para validação.

Os tipos de avaliadores incluem:

- Avaliadores internos que executam a validação de controles dentro da sua organização
- Avaliadores externos que examinam, verificam e certificam a conformidade, como organizações independentes de terceiros que auditam os serviços de nuvem da Microsoft

O consultor valida o trabalho e examina a documentação e seleciona o status de teste apropriado.

**Se o status do teste for definido como "Passed"**: a ação será concluída e os pontos obtidos mostrarão o máximo de pontos alcançado. Os pontos são então contados em relação à pontuação de conformidade geral.

**Se o status do teste for definido como "failed"**: a ação não atende aos requisitos, e o consultor pode atribuí-lo de volta para o usuário apropriado para trabalho adicional.

## <a name="export-a-report"></a>Exportar um relatório

Selecione **Exportar** no canto superior esquerdo da tela para baixar uma planilha do Excel que contenha todas as ações de aperfeiçoamento e as categorias de filtro mostradas na página ações de aprimoramento.