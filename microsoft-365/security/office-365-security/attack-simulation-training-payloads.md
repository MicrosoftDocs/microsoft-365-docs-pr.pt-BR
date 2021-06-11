---
title: Criar uma carga para treinamento de simulação de ataque
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Os administradores podem aprender a criar cargas personalizadas para treinamento de simulação de ataque no Microsoft Defender para Office 365.
ms.technology: mdo
ms.openlocfilehash: ac7963b71c466e8dfdc513a2563776cd4e10af95
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878755"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>Criar um conteúdo personalizado para treinamento de simulação de Ataque

**Aplica-se ao** [Microsoft Defender para Office 365 plano 2](defender-for-office-365.md)

A Microsoft oferece um catálogo de carga robusto para várias técnicas de engenharia social para emparelhar com seu treinamento de simulação de ataque. No entanto, talvez você queira criar cargas personalizadas que funcionarão melhor para sua organização. Este artigo descreve como criar uma carga no treinamento de simulação de ataque no Microsoft Defender para Office 365.

Você pode criar uma carga clicando em **Criar** uma carga na guia Carga [ **dedicada**](https://security.microsoft.com/attacksimulator?viewid=payload) ou no assistente de criação [de simulação.](attack-simulation-training.md#selecting-a-payload)

A primeira etapa do assistente fará com que você selecione um tipo de carga. **Atualmente, somente o email está disponível**.

Em seguida, selecione uma técnica associada. Confira mais detalhes sobre técnicas em [Selecionar uma técnica de engenharia social.](attack-simulation-training.md#selecting-a-social-engineering-technique)

Na próxima etapa, nomee sua carga. Opcionalmente, você pode dar uma descrição.

## <a name="configure-payload"></a>Configurar carga

Agora é hora de criar sua carga. Input the sender's name, email address, and the email's subject in the **Sender details** section. Escolha uma URL de phishing na lista fornecida. Essa URL será inserida posteriormente no corpo da mensagem.

> [!TIP]
> Você pode escolher um email interno para o remetente da carga, o que fará com que a carga apareça como proveniente de outro funcionário da empresa. Isso aumentará a suscetibilidade à carga e ajudará a instruir os funcionários sobre o risco de ameaças internas.

Um editor de texto rico está disponível para criar sua carga. Você também pode importar um email que você criou antecipadamente. Ao criar o corpo do email, aproveite as **marcas** dinâmicas para personalizar o email para seus destinos. Clique **em Link de phishing** para adicionar a URL de phishing selecionada anteriormente ao corpo da mensagem.

![Link de phishing e marcas dinâmicas realçadas na criação de carga para o Microsoft Defender para Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> Para economizar tempo, alterne a opção para substituir todos os links na mensagem **de email pelo link de phishing**.

Depois de terminar de criar a carga ao seu gosto, clique em **Próximo**.

## <a name="adding-indicators"></a>Adicionando indicadores

Os indicadores ajudarão os funcionários que passam pela simulação de ataque a entender a dica que podem procurar em ataques futuros. Para iniciar, clique em **Adicionar indicador**.

Selecione um indicador que você gostaria de usar na listada. Essa lista é curada para conter as pistas mais comuns que aparecem em mensagens de email de phishing. Depois de selecionado, certifique-se de que o posicionamento do indicador está definido como Do corpo do **email e** clique em Selecionar **texto**. Realça a parte da carga em que esse indicador aparece e clique em **Selecionar**.

![Texto realçado no corpo da mensagem para adicionar a um indicador no treinamento de simulação de ataque](../../media/attack-sim-preview-select-text.png)

Adicione uma descrição personalizada para descrever o indicador e clique no quadro de visualização do indicador para ver uma visualização do indicador. Depois de terminar, clique em **Adicionar**. Repita estas etapas até que você tenha abordado todos os indicadores em sua carga.

## <a name="review-payload"></a>Analisar carga

Você terminou de criar sua carga. Agora é hora de revisar os detalhes e ver uma visualização de sua carga. A visualização incluirá todos os indicadores que você criou. Você pode editar cada parte da carga nesta etapa. Depois de satisfeito, você pode **Enviar** sua carga.

> [!IMPORTANT]
> As cargas que você criou terão **Tenant** como fonte. Ao selecionar cargas, certifique-se de não filtrar **Tenant**.

## <a name="related-links"></a>Links relacionados

[Começar a usar o Treinamento de simulação de ataque](attack-simulation-training-get-started.md)

[Criar uma simulação de ataque de phishing](attack-simulation-training.md)

[Obter insights por meio do treinamento de simulação de Ataque](attack-simulation-training-insights.md)
