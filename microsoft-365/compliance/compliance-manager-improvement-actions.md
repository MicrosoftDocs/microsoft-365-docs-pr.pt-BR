---
title: Atribuir e concluir ações de melhoria no Microsoft Compliance Manager
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
description: Saiba como executar a implementação e o teste em controles no Microsoft Compliance Manager. Atribua relatórios de trabalho, de armazenamento e de exportação.
ms.openlocfilehash: e761d8d4410f1c52bb79d4a225eec407f1fd6a6e
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570380"
---
# <a name="assign-and-complete-improvement-actions-in-compliance-manager"></a>Atribuir e concluir ações de aperfeiçoamento no Gerenciador de Conformidade

**Neste artigo:** Este artigo explica como gerenciar **seu fluxo de trabalho de conformidade com** ações de melhoria. Saiba como atribuir ações **de melhoria para** implementação e teste, gerenciar **atualizações** e exportar **relatórios.**

## <a name="manage-compliance-workflows-with-improvement-actions"></a>Gerenciar fluxos de trabalho de conformidade com ações de melhoria

Ações de aperfeiçoamento centralizam suas atividades de conformidade. Cada ação de aperfeiçoamento fornece orientações detalhadas de implementação para ajudá-lo a se alinhar com os regulamentos e padrões de proteção de dados. Ações podem ser atribuídas aos usuários em sua organização para executar o trabalho de implementação e teste. Você também pode armazenar as atualizações de status de documentação, anotações e registros dentro da ação.

Todas as suas ações de melhoria estão listadas na página ações de melhoria. Saiba mais sobre [como exibir suas ações de melhoria.](compliance-manager-setup.md#improvement-actions-page)

## <a name="improvement-actions-details-page"></a>Página detalhes das ações de melhoria

Cada ação de melhoria tem uma página de detalhes mostrando seu status atual, os padrões relacionados e requisitos regulatórios e diretrizes de implementação recomendadas. [As ações técnicas](compliance-score-calculation.md#technical-and-non-technical-actions) **incluem** um link Iniciar agora que o leva à solução apropriada para implementação. Você pode anexar a documentação de implementação e teste diretamente na página de detalhes de uma ação de melhoria.

Para exibir a página de detalhes de uma ação de melhoria:

1. Vá para a página ações de melhoria.
2. Selecione a linha da ação de aperfeiçoamento pretendido, que abre sua página de detalhes.

Você pode exibir facilmente a próxima ou anterior ação de melhoria na lista selecionando a seta para cima ou para baixo no canto superior direito da tela. Se você filtreu sua lista na página ações de melhoria, mover para cima ou para baixo o leva para o próximo item dentro dessa lista filtrada.

## <a name="assign-improvement-actions"></a>Atribuir ações de melhoria

Para iniciar o trabalho de implementação em uma ação de melhoria, você pode fazer o trabalho por conta própria ou atribuí-lo a outro usuário. A pessoa atribuída pode ser:

- Um proprietário de política da empresa
- Um implementador de TI
- Outro funcionário com responsabilidade para executar a tarefa

Depois de identificar o destinatário apropriado, certifique-se de que ele tenha uma função de Gerente de [Conformidade suficiente](compliance-manager-setup.md#set-user-permissions-and-assign-roles) para executar o trabalho. Em seguida, siga as etapas abaixo para atribuir a ação de melhoria:

1. Na página detalhes das ações de melhoria, selecione **Editar status** próximo à seção superior esquerda da tela.

2. No painel de texto explicativos de status de edição, selecione a caixa **Atribuído** a para mostrar uma **lista de pessoas** sugeridas de usuários. Você pode selecionar o usuário na lista ou digitar o endereço de email da pessoa à qual deseja atribuí-lo.

3. Selecione **Salvar e fechar**. O usuário atribuído receberá um email explicando que a ação de melhoria foi atribuída a ele, com um link direto para a ação de melhoria. 
> [!NOTE]
> Os clientes do Us Government Community (GCC) High e Department of Defense (DoD) não receberão um email quando as ações de melhoria são atribuídas a eles.

Em seguida, o usuário atribuído pode executar as ações recomendadas.

#### <a name="assign-multiple-improvement-actions-to-a-single-user"></a>Atribuir várias ações de melhoria a um único usuário

Você pode atribuir várias ações de melhoria a um usuário seguindo estas etapas:

1. Vá para a página Ações de Aperfeiçoamento.
2. Selecione a área à esquerda do nome da ação de melhoria. Um ícone de verificação redonda será exibido indicando que você selecionou essa ação. Verifique todas as ações que você deseja atribuir.
3. Selecione o **link Atribuir ao** usuário na parte superior da tabela ações de melhoria.
4. Uma janela pop-up será exibida. No campo **Atribuir a,** comece a digitar o nome da pessoa à quem você deseja atribuir as ações. Você também pode selecionar na lista de pessoas sugeridas.
5. Depois de preencher o campo **Atribuir ao** nome do destinatário, selecione **Atribuir**.
6. Em seguida, você verá a página Ações de Aperfeiçoamento com o novo destinatário listado para as ações que você acabou de atribuir.

## <a name="perform-work-and-store-documentation"></a>Executar documentação de trabalho e armazenamento

Você pode carregar arquivos e anotações relacionados à implementação e testes funcionam diretamente na seção **Notas e documentação.** Esse ambiente é um repositório centralizado e seguro para ajudá-lo a demonstrar a satisfação dos controles para atender aos padrões e aos regulamentos de conformidade. Qualquer usuário com acesso somente leitura pode ler conteúdo nesta seção. Somente usuários com direitos de edição podem carregar e baixar arquivos e inserir ou editar anotações.

A **seção Notas e documentação** contém campos para documentos carregados, notas de implementação, notas de teste e anotações adicionais.

#### <a name="uploaded-documents"></a>Documentos carregados

- Selecione **Gerenciar documentos** para carregar arquivos relevantes.
- Quando o painel de controle de gerenciamento de documentos for aberto, selecione **Adicionar documento** e selecione seu arquivo no sistema. Tipos de arquivo aceitos:
    - Documentos (.doc, .xls, .ppt, .txt, .pdf)
    - Imagens (.jpg, .png)
    - Vídeo (.mkv)
    - Arquivos compactados (.zip, .rar)
- Depois que o arquivo é resolvido no painel, selecione **Fechar**, que salva automaticamente o anexo do arquivo. Em seguida, você verá o arquivo listado abaixo **Documentos carregados.**
- Para baixar ou excluir o documento, selecione **Gerenciar documentos** abaixo da lista de documentos. No painel de sobrevoos, selecione a linha do documento para realça-la e selecione **Baixar** ou **Excluir**.

#### <a name="implementation-notes-test-notes-and-additional-notes"></a>Notas de implementação, notas de teste e notas adicionais

- Para adicionar anotações em qualquer um desses três campos, selecione Editar notas **de implementação** abaixo de qualquer um desses campos.
- Quando o painel de sobrevoo for aberto, insira anotações no campo de texto e selecione **Salvar e fechar**.
- Para editar anotações, selecione **Editar notas de implementação,** fazer suas edições e, em seguida, **selecione Salvar e fechar**.

Não há limite de caracteres nos campos de anotações. Recomendamos manter as anotações breves para que você possa exibi-las e editá-las facilmente na página detalhes das ações de melhoria.

## <a name="change-improvement-action-status"></a>Status da ação de melhoria de alteração

Você pode registrar o status e a data da implementação e o status e a data do teste para cada ação de melhoria. Os **campos de** status de **implementação** e teste podem ser editados por qualquer usuário com permissões de edição, não apenas pela pessoa atribuída.

Para editar o status de uma ação de melhoria, selecione **Editar status** na seção superior esquerda da página de detalhes. Abaixo estão os campos disponíveis e as opções de status:

- **Status da implementação**
    - **Não implementada** - ação ainda não implementada
    - **Implementado** - ação implementada
    - **Implementação alternativa** - selecione essa opção se você usou outras ferramentas de terceiros ou fez outras ações não incluídas nas recomendações da Microsoft
    - **Planejado -** a ação está planejada para implementação
    - **Fora do escopo** – a ação não é relevante para sua organização e não contribui para sua pontuação
- **Data da implementação**: disponível para selecionar quando o status da implementação é "implementado" ou "implementação alternativa"
- **Status do** teste : disponível para selecionar quando o status da implementação for "implementado" ou "implementação alternativa":
    - **Não avaliado** – a ação não foi testada
    - **Aprovado** - a implementação foi verificada por um assessor
    - **Baixo risco com falha** - falha no teste, baixo risco
    - **Risco médio com falha** - falha no teste, risco médio
    - **Falha de alto risco** – falha no teste, alto risco
    - **Fora do escopo** – a ação está fora do escopo da avaliação e não contribui para sua pontuação
- **Data do** teste : alterne o pop-up do calendário para selecionar a data

Ações comuns sincronizam entre grupos. Quando duas avaliações diferentes nas mesmas ações de melhoria de compartilhamento de grupo gerenciadas por você, todas as atualizações feitas para os detalhes ou status de implementação de uma ação serão sincronizadas automaticamente com a mesma ação em qualquer outra avaliação no grupo. Essa sincronização permite implementar uma ação de melhoria e atender a vários requisitos em vários regulamentos.

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Atribuir ação de aperfeiçoamento ao assessor para conclusão

Depois de concluir o trabalho, conduzir testes e carregar evidências, a próxima etapa é atribuir a ação de melhoria a um avaliador para validação. O avaliador valida o trabalho e examina a documentação e seleciona o status de teste apropriado.

**Se o status do teste for definido como "Passado":** a ação será concluída e os pontos atingidos mostrarão os pontos máximos atingidos. Os pontos são contados em direção à pontuação geral de conformidade.

Se o status do teste for definido como **"Falha":** a ação não atenderá aos requisitos e o avaliador poderá atribuí-lo de volta ao usuário apropriado para trabalho adicional.

## <a name="accepting-updates-to-improvement-actions"></a>Aceitar atualizações para ações de melhoria

Quando uma atualização estiver disponível para uma ação de melhoria, você verá uma notificação ao lado de seu nome. Você pode aceitar a atualização ou adiá-la posteriormente.

#### <a name="what-causes-an-update"></a>O que causa uma atualização

Uma atualização ocorre quando há alterações relacionadas à pontuação, automação ou escopo. As alterações podem envolver novas diretrizes para ações de melhoria com base em alterações regulatórias ou podem ser devido a alterações do produto. Somente as ações de aperfeiçoamento gerenciadas por suas organizações recebem notificações de atualização.

#### <a name="where-youll-see-assessment-update-notifications"></a>Onde você verá notificações de atualização de avaliação

Quando uma ação de melhoria é  atualizada, você verá um rótulo de atualização pendente ao lado de seu nome na página ações de melhoria e na página de detalhes de suas avaliações relacionadas.

Vá até a página de detalhes da  ação de aperfeiçoamento e selecione o botão Revisar atualização na faixa superior para revisar detalhes sobre as alterações e aceitar ou adiar a atualização.

#### <a name="review-update-to-accept-or-defer"></a>Revisar a atualização para aceitar ou adiar

Depois de **selecionar Revisar atualização** na página detalhes da ação de melhoria, um painel de sobremenu aparece no lado direito da tela. O painel de sobrevoos fornece detalhes importantes sobre a atualização, como as avaliações impactadas e as alterações na pontuação e no escopo.

Selecione **Aceitar atualização** para aceitar todas as alterações na ação de melhoria. **As alterações aceitas são permanentes**.

> [!NOTE]
> Quando você aceita uma atualização para uma ação, também está aceitando atualizações para quaisquer outras versões ou instâncias dessa ação. As atualizações propagam todo o locatário para ações técnicas e propagam todo o grupo para ações não técnicas.

Se você selecionar **Cancelar**, a atualização não será aplicada à ação de melhoria. No entanto, você continuará a ver a notificação **de** atualização pendente até aceitar a atualização.

**Por que recomendamos aceitar atualizações**

Aceitar atualizações ajuda a garantir que você tenha as diretrizes mais atualizadas sobre como usar soluções e tomar as ações de melhoria apropriadas para ajudá-lo a atender aos requisitos da certificação em mãos.

**Por que você pode querer adiar uma atualização**

Se você estiver no meio da conclusão de uma avaliação que inclui a ação de melhoria, talvez você queira garantir que você terminou de trabalhar nele antes de aceitar a atualização. Você pode adiar a atualização posteriormente selecionando **Cancelar** no painel do flyout de atualização de revisão.

#### <a name="accept-all-updates-at-once"></a>Aceitar todas as atualizações de uma só vez

Se você tiver várias atualizações e quiser aceitá-las todas ao mesmo tempo, selecione o **link** Aceitar todas as atualizações na parte superior da tabela ações de melhoria. Um painel de sobrevoo aparecerá que lista o número de ações a serem atualizadas. Selecione o **botão Aceitar atualizações** para aplicar todas as atualizações.

Observe que, ao retornar à página ações de melhoria, você poderá ver uma mensagem na parte superior da página solicitando que você atualize a página para que as atualizações sejam concluídas.

## <a name="export-a-report"></a>Exportar um relatório

Selecione **Exportar** no canto superior esquerdo da tela para baixar uma planilha do Excel contendo todas as suas ações de melhoria e as categorias de filtro mostradas na página ações de melhoria.