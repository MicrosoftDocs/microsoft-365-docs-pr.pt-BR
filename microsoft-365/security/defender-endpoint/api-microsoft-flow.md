---
title: Conector de fluxo do Microsoft Defender ATP
ms.reviewer: ''
description: Use o Conector de Fluxo do Microsoft Defender ATP para automatizar a segurança e criar um fluxo que será disparado sempre que um novo alerta ocorrer em seu locatário.
keywords: fluxo, apis com suporte, api, fluxo da Microsoft, consulta, automação
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6fd210ddfb8e3ab6e4f1f4ffc0635c8b813e3a07
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163382"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a>Microsoft Power Automate (anteriormente Microsoft Flow) e Funções do Azure

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Automatizar procedimentos de segurança é um requisito padrão para cada Centro de Operações de Segurança moderno. A falta de defensores cibernéticos profissionais força o SOC a trabalhar da maneira mais eficiente e a automação é uma tarefa. O Microsoft Power Automate oferece suporte a conectores diferentes que foram construídos exatamente para isso. Você pode criar uma automação de procedimento de ponta a ponta em alguns minutos.

A API do Microsoft Defender tem um Conector de Fluxo oficial com muitos recursos.

![Imagem de credenciais de edição1](images/api-flow-0.png)

> [!NOTE]
> Para obter mais detalhes sobre os pré-requisitos de licenciamento de conectores premium, consulte [Licensing for premium connectors](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors).


## <a name="usage-example"></a>Exemplo de uso

O exemplo a seguir demonstra como criar um Fluxo que é acionado sempre que um novo Alerta ocorre em seu locatário.

1. Faça logoff no [Microsoft Power Automate](https://flow.microsoft.com).

2. Vá para **Meus fluxos**  >    >  **New Automated-from em branco**.

    ![Imagem de credenciais de edição2](images/api-flow-1.png)

3. Escolha um nome para o seu Fluxo, procure "Gatilhos do Microsoft Defender ATP" como o gatilho e selecione o novo gatilho Alertas.

    ![Imagem de credenciais de edição3](images/api-flow-2.png)

Agora você tem um Fluxo que é disparado sempre que um novo Alerta ocorre.

![Imagem de credenciais de edição4](images/api-flow-3.png)

Tudo o que você precisa fazer agora é escolher suas próximas etapas.
Por exemplo, você pode isolar o dispositivo se a Gravidade do Alerta for Alta e enviar um email sobre ele.
O gatilho Alerta fornece apenas a ID do Alerta e a ID do Computador. Você pode usar o conector para expandir essas entidades.

### <a name="get-the-alert-entity-using-the-connector"></a>Obter a entidade Alert usando o conector

1. Escolha **o Microsoft Defender ATP** para a nova etapa.

2. Escolha **Alertas - Obter API de alerta único.**

3. De definir **a ID do Alerta** da última etapa como **Entrada**.

    ![Imagem de credenciais de edição5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a>Isolar o dispositivo se a gravidade do Alerta for Alta

1. Adicionar **Condição** como uma nova etapa.

2. Verifique se a gravidade do alerta **é igual a** Alta.

   Se sim, adicione o **Microsoft Defender ATP - Isolar** a ação do computador com a ID do computador e um comentário.

    ![Imagem de credenciais de edição6](images/api-flow-5.png)

3. Adicione uma nova etapa para enviar emails sobre o Alerta e o Isolamento. Há vários conectores de email que são muito fáceis de usar, como o Outlook ou o Gmail.

4. Salve o fluxo.

Você também pode criar um **fluxo agendado** que executa consultas de Busca Avançada e muito mais!

## <a name="related-topic"></a>Tópicos relacionados
- [APIs do Microsoft Defender para Ponto de Extremidade](apis-intro.md)
