---
title: Atribuir e concluir ações de melhoria no Gerenciador de Conformidade da Microsoft
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
description: Saiba como executar a implementação e testes em controles no Gerenciador de Conformidade da Microsoft. Atribuir trabalho, armazenar documentação e exportar relatórios.
ms.openlocfilehash: c465a574ed9c1a8ad8ef9e2bfc7f864545ae28d9
ms.sourcegitcommit: 00d231bf0100e843a5a93161695e87ceff9e1349
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49849584"
---
# <a name="assign-and-complete-improvement-actions-in-compliance-manager"></a>Atribuir e concluir ações de melhoria no Gerenciador de Conformidade

**Neste artigo:** Este artigo explica como gerenciar seu **fluxo de trabalho de conformidade** com ações de melhoria. Saiba como atribuir **ações de melhoria para** implementação e teste, gerenciar **atualizações** e exportar **relatórios.**

## <a name="manage-compliance-workflows-with-improvement-actions"></a>Gerenciar fluxos de trabalho de conformidade com ações de melhoria

As ações de melhoria centralizam suas atividades de conformidade. Cada ação de melhoria fornece orientações detalhadas de implementação para ajudá-lo a se alinhar com os regulamentos e padrões de proteção de dados. Ações podem ser atribuídas aos usuários em sua organização para executar o trabalho de implementação e teste. Você também pode armazenar a documentação, as anotações e as atualizações de status do registro dentro da ação.

Todas as suas ações de melhoria estão listadas na página de ações de melhoria. Saiba mais sobre como [exibir suas ações de melhoria.](compliance-manager-setup.md#improvement-actions-page)

## <a name="improvement-actions-details-page"></a>Página de detalhes de ações de melhoria

Cada ação de melhoria tem uma página de detalhes mostrando seu status atual, os padrões e requisitos regulatórios relacionados e orientações de implementação recomendadas. [As ações técnicas](compliance-score-calculation.md#technical-and-non-technical-actions) **incluem um** link Iniciar agora que leva você à solução apropriada para implementação. Você pode anexar a documentação de implementação e teste diretamente na página de detalhes de uma ação de aperfeiçoamento.

Para exibir a página de detalhes de uma ação de aperfeiçoamento:

1. Vá para a página de ações de melhoria.
2. Selecione a linha da ação de melhoria pretendido, que abre sua página de detalhes.

Você pode exibir facilmente a próxima ação de melhoria ou anterior na lista selecionando a seta para cima ou para baixo no canto superior direito da tela. Se você filtrou sua lista na página de ações de melhoria, mover para cima ou para baixo leva você para o próximo item dentro dessa lista filtrada.

## <a name="assign-improvement-actions"></a>Atribuir ações de melhoria

Para iniciar o trabalho de implementação em uma ação de melhoria, você pode fazer o trabalho por conta própria ou atribuí-lo a outro usuário. A pessoa atribuída poderia ser:

- Um proprietário de política da empresa
- Um implementador de TI
- Outro funcionário com responsabilidade para executar a tarefa

Depois de identificar o destinatário apropriado, certifique-se de que ele tenha uma função suficiente do Gerenciador de [Conformidade](compliance-manager-setup.md#set-user-permissions-and-assign-roles) para executar o trabalho. Em seguida, siga as etapas abaixo para atribuir a ação de melhoria:

1. Na página de detalhes das ações de melhoria, selecione **Editar status** próximo à seção superior esquerda da tela.

2. No painel editar status do flyout, selecione a caixa Atribuído a mostrar uma **lista de pessoas** sugeridas de usuários.  Você pode selecionar o usuário na lista ou digitar o endereço de email da pessoa à qual você deseja atribuí-lo.

3. Selecione **Salvar e fechar.** O usuário atribuído receberá um email explicando que a ação de melhoria foi atribuída a ele, com um link direto para a ação de melhoria. (Observação: Os clientes do Us Government Community (GCC) High não receberão um email quando ações são atribuídas a eles.)

O usuário atribuído pode executar as ações recomendadas.

#### <a name="assign-multiple-improvement-actions-to-a-single-user"></a>Atribuir várias ações de melhoria a um único usuário

Você pode atribuir várias ações de melhoria a um usuário seguindo estas etapas:

1. Vá para a página ações de aperfeiçoamento.
2. Selecione a área à esquerda do nome da ação de melhoria. Um ícone de verificação de ida e volta será exibido indicando que você selecionou essa ação. Verifique todas as ações que você deseja atribuir.
3. Selecione o **link Atribuir ao** usuário na parte superior da tabela de ações de melhoria.
4. Uma janela pop-up será exibida. In the **Assign to** field, start typing the name of the person you want to assign the actions to. Você também pode selecionar na lista de pessoas sugeridas.
5. Depois de preencher o **campo Atribuir ao** com o nome do destinatário, selecione **Atribuir**.
6. Em seguida, você verá sua página de ações de melhoria com o novo destinatário listado para as ações que você acabou de atribuir.

## <a name="perform-work-and-store-documentation"></a>Executar documentação de trabalho e armazenamento

Você pode carregar arquivos e anotações relacionados à implementação e testes de trabalho diretamente para a seção **Notas e documentação.** Este ambiente é um repositório seguro e centralizado para ajudá-lo a demonstrar a satisfação dos controles para atender aos padrões e regulamentos de conformidade. Qualquer usuário com acesso somente leitura pode ler conteúdo nesta seção. Somente usuários com direitos de edição podem carregar e baixar arquivos e inserir ou editar notas.

A **seção Notas e documentação** contém campos para documentos carregados, notas de implementação, notas de teste e notas adicionais.

#### <a name="uploaded-documents"></a>Documentos carregados

- Selecione **Gerenciar documentos** para carregar arquivos relevantes.
- Quando o painel de gerenciamento de documentos for aberto, selecione **Adicionar documento** e selecione seu arquivo no sistema. Tipos de arquivo aceitos:
    - Documentos (.doc, .xls, .ppt, .txt, .pdf)
    - Imagens (.jpg, .png)
    - Vídeo (.mkv)
    - Arquivos compactados (.zip, .rar)
- Depois que o arquivo é resolvido no painel, selecione **Fechar,** o que salva automaticamente o anexo de arquivo. Em seguida, você verá o arquivo listado abaixo **de Documentos carregados.**
- Para baixar ou excluir o documento, selecione **Gerenciar documentos** sob a lista de documentos. No painel do flyout, selecione a linha do documento para realça-la e, em seguida, selecione **Baixar** ou **Excluir.**

#### <a name="implementation-notes-test-notes-and-additional-notes"></a>Notas de implementação, notas de teste e notas adicionais

- Para adicionar anotações em qualquer um desses três campos, selecione Editar notas **de implementação** sob qualquer um desses campos.
- Quando o painel do flyout for aberto, insira anotações no campo de texto e, em seguida, **selecione Salvar e fechar.**
- Para editar notas, selecione **Editar notas de implementação,** faça suas edições e, em seguida, **selecione Salvar e fechar.**

Não há limite de caracteres nos campos de anotações. Recomendamos manter as anotações breves para que você possa facilmente exibi-las e editá-las na página de detalhes das ações de melhoria.

## <a name="change-improvement-action-status"></a>Status da ação de melhoria de alteração

Você pode registrar o status e a data de implementação e o status e a data do teste para cada ação de melhoria. Os **campos** de **status de implementação** e teste podem ser editados por qualquer usuário com permissões de edição, não apenas pela pessoa atribuída.

Para editar o status de uma ação de melhoria, selecione **Editar status** na seção superior esquerda da página de detalhes. A seguir estão os campos disponíveis e as opções de status:

- **Status da implementação**
    - **Não implementado** - ação ainda não implementada
    - **Implementado** - ação implementada
    - **Implementação alternativa** - selecione essa opção se você usou outras ferramentas de terceiros ou tomou outras ações não incluídas nas recomendações da Microsoft
    - **Planejado -** a ação está planejada para implementação
    - **Fora do escopo** – a ação não é relevante para sua organização e não contribui para sua pontuação
- **Data de implementação**: disponível para selecionar quando o status da implementação é "implementado" ou "implementação alternativa"
- **Status do** teste : disponível para selecionar quando o status da implementação é "implementado" ou "implementação alternativa":
    - **Não avaliado** – a ação não foi testada
    - **Aprovado** - a implementação foi verificada por um avaliador
    - **Falha de baixo risco** - falha no teste, baixo risco
    - **Risco médio com falha** - falha no teste, risco médio
    - **Falha de alto risco** – falha no teste, alto risco
    - **Fora do escopo** – a ação está fora do escopo da avaliação e não contribui para sua pontuação
- **Data do** teste: alterne o pop-up do calendário para selecionar a data

Ações comuns sincronizadas entre grupos. Quando duas avaliações diferentes no mesmo grupo compartilham ações de melhoria gerenciadas por você, todas as atualizações feitas nos detalhes ou status de implementação de uma ação serão sincronizadas automaticamente com a mesma ação em qualquer outra avaliação do grupo. Essa sincronização permite implementar uma ação de melhoria e atender a vários requisitos em vários regulamentos.

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Atribuir ação de melhoria ao avaliador para conclusão

Depois de concluir o trabalho, conduzir testes e carregar evidências, a próxima etapa é atribuir a ação de melhoria a um avaliador para validação. O avaliador valida o trabalho, examina a documentação e seleciona o status de teste apropriado.

Se o status do teste estiver definido como **"Passado":** a ação será concluída e os pontos alcançados mostrarão os pontos máximos alcançados. Os pontos são contados em relação à sua pontuação geral de conformidade.

Se o status do teste estiver definido como **"Falha":** a ação não atenderá aos requisitos e o avaliador poderá atribuí-lo de volta ao usuário apropriado para trabalho adicional.

## <a name="accepting-updates-to-improvement-actions"></a>Aceitando atualizações para ações de melhoria

Quando uma atualização estiver disponível para uma ação de melhoria, você verá uma notificação ao lado de seu nome. Você pode aceitar a atualização ou adiá-la mais tarde.

#### <a name="what-causes-an-update"></a>O que causa uma atualização

Uma atualização ocorre quando há alterações relacionadas à pontuação, automação ou escopo. As alterações podem envolver novas diretrizes para ações de melhoria com base em alterações regulatórias ou podem ser devido a alterações no produto. Somente as ações de melhoria gerenciadas por suas organizações recebem notificações de atualização.

#### <a name="where-youll-see-assessment-update-notifications"></a>Onde você verá as notificações de atualização de avaliação

Quando uma ação de melhoria for  atualizada, você verá um rótulo de atualização pendente ao lado de seu nome na página de ações de melhoria e na página de detalhes de suas avaliações relacionadas.

Vá para a página de detalhes da  ação de aperfeiçoamento e selecione o botão Revisar atualização na faixa superior para revisar detalhes sobre as alterações e aceitar ou adiar a atualização.

#### <a name="review-update-to-accept-or-defer"></a>Revisar a atualização para aceitar ou adiar

Depois de **selecionar Revisar atualização** na página de detalhes da ação de melhoria, um painel demenu é exibido no lado direito da tela. O painel do flyout fornece detalhes importantes sobre a atualização, como as avaliações impactadas e as alterações na pontuação e no escopo.

Selecione **Aceitar atualização** para aceitar todas as alterações na ação de melhoria. **As alterações aceitas são permanentes.**

> [!NOTE]
> Ao aceitar uma atualização para uma ação, você também está aceitando atualizações para quaisquer outras versões ou instâncias dessa ação. As atualizações propagam todo o locatário para ações técnicas e propagam todo o grupo para ações não técnicas.

Se você selecionar **Cancelar,** a atualização não será aplicada à ação de melhoria. No entanto, você continuará a ver a notificação **de** atualização pendente até aceitar a atualização.

**Por que recomendamos aceitar atualizações**

Aceitar atualizações ajuda a garantir que você tenha as orientações mais atualizadas sobre como usar soluções e tomar as ações de melhoria apropriadas para ajudá-lo a atender aos requisitos da certificação em mãos.

**Por que você talvez queira adiar uma atualização**

Se você estiver no meio da conclusão de uma avaliação que inclui a ação de melhoria, talvez você queira garantir que terminou de trabalhar nele antes de aceitar a atualização. Você pode adiar a atualização mais tarde selecionando **Cancelar** no painel do flyout de atualização de revisão.

#### <a name="accept-all-updates-at-once"></a>Aceitar todas as atualizações de uma só vez

Se você tiver várias atualizações e quiser aceitá-las todas de uma só vez, selecione o **link** Aceitar todas as atualizações na parte superior da tabela de ações de melhoria. Um painel de sobrevoo será exibido, listando o número de ações a serem atualizadas. Selecione o **botão Aceitar atualizações** para aplicar todas as atualizações.

Observe que, ao retornar à página de ações de melhoria, você poderá ver uma mensagem na parte superior da página solicitando que você atualize a página para que as atualizações sejam concluídas.

## <a name="export-a-report"></a>Exportar um relatório

Selecione **Exportar** no canto superior esquerdo da tela para baixar uma planilha do Excel que contém todas as suas ações de melhoria e as categorias de filtro mostradas na página de ações de melhoria.