---
title: Criar uma carga para treinamento de simulação de ataque
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Os administradores podem aprender a criar cargas personalizadas para o treinamento de simulação de ataque no Microsoft defender para Office 365.
ms.openlocfilehash: c42090634f6fa9500ae4c3e781b49b607ee928f5
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667478"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>Criar um conteúdo personalizado para treinamento de simulação de Ataque

A Microsoft oferece um catálogo de carga robusto para várias técnicas de engenharia social para emparelhar com seu treinamento de simulação de ataque. No entanto, talvez você queira criar cargas personalizadas que funcionem melhor para sua organização. Este artigo descreve como criar uma carga em treinamento de simulação de ataque no Microsoft defender para Office 365.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Você pode criar uma carga clicando em **criar uma carga** na [guia **cargas** dedicadas](https://security.microsoft.com/attacksimulator?viewid=payload) ou no [Assistente de criação de simulação](attack-simulation-training.md#selecting-a-payload).

A primeira etapa do assistente terá que você selecionar um tipo de carga. **Atualmente, somente email está disponível**.

Em seguida, selecione uma técnica associada. Veja mais detalhes sobre as técnicas na [seleção de uma técnica de engenharia social](attack-simulation-training.md#selecting-a-social-engineering-technique).

Na próxima etapa, nomeie sua carga. Opcionalmente, você pode fornecer uma descrição.

## <a name="configure-payload"></a>Configurar carga

Agora é hora de criar sua carga. Insira o nome do remetente, o endereço de email e o assunto do email na seção **detalhes do remetente** . Escolha uma URL de phishing na lista fornecida. Essa URL será incorporada posteriormente ao corpo da mensagem.

> [!TIP]
> Você pode escolher um email interno para o remetente da carga de conteúdo, que fará com que a carga apareça da mesma forma que vem de outro funcionário da empresa. Isso aumentará o susceptibility da carga e ajudará a educar os funcionários sobre o risco de ameaças internas.

Um editor de Rich Text está disponível para criar sua carga. Você também pode importar um email que você criou anteriormente. À medida que você cria o corpo do email, aproveite as **marcas dinâmicas** para personalizar o email para seus destinos. Clique em **link de phishing** para adicionar a URL de phishing selecionada anteriormente ao corpo da mensagem.

![Link de phishing e marcas dinâmicas realçadas na criação de carga para o Microsoft defender para Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> Para poupar tempo, alterne a opção para **substituir todos os links na mensagem de email pelo link de phishing**.

Após concluir a criação da carga de preferência, clique em **Avançar**.

## <a name="adding-indicators"></a>Adicionar indicadores

Os indicadores ajudarão os funcionários a passar pela simulação de ataque entendem o indício de que eles podem procurar em futuros ataques. Para começar, clique em **Adicionar indicador**.

Selecione um indicador que você gostaria de usar na lista suspensa. Essa lista é organizada para conter as dicas mais comuns que aparecem em mensagens de email de phishing. Depois de selecionado, certifique-se de que o posicionamento do indicador está definido para **o corpo do email** e clique em **selecionar texto**. Realce a parte da carga onde esse indicador aparece e clique em **selecionar**.

![Texto realçado no corpo da mensagem a ser adicionado a um indicador no treinamento de simulação de ataque](../../media/attack-sim-preview-select-text.png)

Adicione uma descrição personalizada para descrever o indicador e clique no quadro de visualização do indicador para ver uma visualização do indicador. Após concluir, clique em **Adicionar**. Repita essas etapas até que você tenha abordado todos os indicadores em sua carga.

## <a name="review-payload"></a>Examinar carga

Você terminou de criar sua carga. Agora é hora de revisar os detalhes e ver uma visualização da sua carga. A visualização incluirá todos os indicadores que você criou. Você pode editar cada parte da carga desta etapa. Depois de satisfeito, **envie** sua carga.

> [!IMPORTANT]
> As cargas que você criou terão **locatário** como fonte. Ao selecionar as cargas, certifique-se de não filtrar o **locatário**.
