---
title: Atualizações de Pontuação de conformidade da Microsoft
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
description: Detalhes sobre atualizações futuras para a pontuação de conformidade da Microsoft (visualização), um recurso no centro de conformidade do M365 que ajuda a simplificar e automatizar avaliações de risco.
ms.openlocfilehash: c46b70d0762a805e4ecfc83b70173c56d21a3933
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857745"
---
# <a name="microsoft-compliance-score-preview-updates"></a>Atualizações de Pontuação de conformidade da Microsoft (visualização)

 Este artigo fornece detalhes sobre as futuras atualizações para a [Pontuação de conformidade da Microsoft](compliance-score.md) e [o gerente de conformidade da Microsoft](compliance-manager-overview.md). Saiba mais sobre sua [relação](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager).

## <a name="improved-template-creation-and-update-processes"></a>Melhor criação de modelo e processos de atualização

Estamos simplificando o processo de importação, exportação e modificação de modelos para avaliações. A nova experiência facilitará a realização de suas próprias avaliações na pontuação de conformidade e mantê-las atualizadas.

### <a name="the-current-process"></a>O processo atual

Há duas maneiras de criar um modelo no Gerenciador de conformidade. Você pode copiar um modelo existente ou pode importar dados de modelo de uma planilha do Excel para um novo modelo. Na página de **modelos** , selecione **+ Adicionar modelo** para criar um novo modelo de marca, inserindo um nome, selecionando dimensões e carregando um arquivo do Excel com um formato e esquema específicos. Ou você pode verificar a caixa **Copiar de um modelo existente** , selecionar um modelo a ser copiado e verificar as dimensões, conforme mostrado na imagem abaixo. Personalizar o modelo requer um [processo de várias etapas](working-with-compliance-manager.md#templates) que comece selecionando **Adicionar controle personalizado** após a criação do modelo.

![Pontuação de conformidade-painel](../media/compliance-score-template-update-old.png "Processo de cópia de modelo atual")

### <a name="whats-changing"></a>O que está mudando

Estamos facilitando a criação de novos modelos. Em um processo de **extensão** de uma etapa, você pode adicionar uma planilha com suas ações e controles a um modelo existente da Microsoft para criar sua própria versão personalizada. No painel do menu suspenso **modelo** , marque a caixa de seleção **criar extensão a partir do modelo global** , conforme mostrado na imagem abaixo. Em seguida, você adicionará personalizações usando um novo formato do Excel menos complexo do que o atual. Esse novo processo substitui a **cópia atual de um modelo existente** e **adiciona funções de controle personalizadas** .

Cada vez que a avaliação original é atualizada através do processo de controle de versão descrito abaixo, sua avaliação personalizada herdará essas atualizações e manterá seus controles personalizados.

Também estamos facilitando a modificação de seus próprios modelos existentes. Você pode exportar seu modelo, fazer alterações na mesma pasta de trabalho e, em seguida, importá-lo com suas edições salvas.

![Pontuação de conformidade-painel](../media/compliance-score-template-update-new.png "Novo processo de criação de modelo")

## <a name="versioning-notice-and-control"></a>Controle e aviso de controle de versão

Sua organização receberá avaliações atualizadas na próxima versão da Pontuação de conformidade e gerente de conformidade para ajudá-lo a se adequar às atualizações de certificação e regulamentação.

No futuro, sempre que uma atualização estiver disponível para o modelo de uma avaliação ou para uma ação de melhoria, um ícone de alerta notificará que uma atualização está pronta. Quando você clica nesse ícone, uma janela pop-up explica a atualização e solicita que você aceite. Veja a seguir um exemplo do alerta de controle de versão para uma avaliação:

![Pontuação de conformidade-alerta de controle de versão](../media/compliance-score-assessment-version.png "Alerta de atualização de versão de avaliação")

Selecionar o ícone de alerta revela um painel de submenu que explica a atualização e solicita que você aceite:

![Pontuação de conformidade-submenu de controle de versão](../media/compliance-score-assessment-version-accept.png "Painel de confirmação de atualização de avaliação")

## <a name="common-actions-will-synch-status-across-groups"></a>As ações comuns irão sincronizar o status entre grupos

Se sua organização tiver vários grupos de avaliações, o comportamento das ações **técnicas** (ou seja, ações que afetam a organização inteira) será alterado. Quaisquer ações duplicadas entre grupos serão combinadas em uma única ação. Essa ação única conterá todas as anotações e evidências carregadas das versões duplicadas. Com essa alteração, as ações técnicas se comportam como fazem atualmente quando pertencem ao mesmo grupo. Todas as alterações feitas na ação em um grupo ou avaliação serão refletidas em todas as instâncias. O **status da implementação**, o **dat de implementação**, o status do **teste**e a **Data** de teste irão refletir as atualizações mais recentes.

## <a name="language-support"></a>Suporte a idiomas

A pontuação de conformidade agora estará disponível nos seguintes idiomas, além de inglês: Chinês (simplificado), chinês (tradicional), francês, alemão, italiano, japonês, coreano, Português (Brasil), russo e espanhol.
