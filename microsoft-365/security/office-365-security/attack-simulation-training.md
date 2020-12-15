---
title: Simular um ataque de phishing com o Microsoft defender para Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Os administradores podem aprender a simular ataques de phishing e treinar seus usuários sobre prevenção de phishing usando o treinamento de simulação de ataque no Microsoft defender para Office 365.
ms.openlocfilehash: 3707041067fd76ee9535d0dccf5cdfcb9d74fbd7
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667498"
---
# <a name="simulate-a-phishing-attack"></a>Simular um ataque de phishing

O treinamento do simulador de ataque no Microsoft defender para Office 365 permite executar simulações benignas do cyberattack em sua organização para testar suas práticas e políticas de segurança, bem como treinar seus funcionários para aumentar a conscientização e reduzir o susceptibility a ataques. Este artigo orienta você durante a criação de um ataque de phishing simulado usando o treinamento do Attack Simulator.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Para iniciar um ataque de phishing simulado, abra o [centro de segurança do Microsoft 365](https://security.microsoft.com/), acesse **e-mail & Collaboration** Attack disparation \> **Simulator** e alterne para a guia [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) .

Em **simulações**, selecione **+ iniciar uma simulação**.

![Iniciar um botão de simulação no centro de segurança do Microsoft 365](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> A qualquer momento durante a criação da simulação, você pode salvar e fechar para continuar Configurando a simulação mais tarde.

## <a name="selecting-a-social-engineering-technique"></a>Selecionar uma técnica de engenharia social

Selecione dentre 4 técnicas diferentes, organizadas da [estrutura Mitre ATT&CK®](https://attack.mitre.org/techniques/enterprise/). Cargas diferentes estão disponíveis para diferentes técnicas:

- A **coleta de credenciais** tenta coletar credenciais levando os usuários a um site de aparência conhecido com caixas de entrada para enviar um nome de usuário e senha.
- O **anexo de malware** adiciona um anexo mal-intencionado a uma mensagem. Quando o usuário abre o anexo, o código arbitrário é executado e ajudará o invasor a comprometer o dispositivo de destino.
- **Link no anexo** é um tipo de coleta de credenciais híbrido. Um invasor insere uma URL em um anexo de email. A URL no anexo segue a mesma técnica que a coleta de credenciais.
- O **link para malware** executará um código arbitrário de um arquivo hospedado em um serviço de compartilhamento de arquivos conhecido. A mensagem enviada para o usuário conterá um link para este arquivo mal-intencionado. Abrir o arquivo e ajudar o atacante a comprometer o dispositivo de destino.

> [!TIP]
> Ao clicar em **Exibir detalhes** dentro da descrição de cada técnica, serão exibidas mais informações e as etapas de simulação da técnica.
>
> ![Etapas de simulação para coleta de credenciais no treinamento de simulação de ataque no centro de segurança do Microsoft 365](../../media/attack-sim-preview-sim-steps.png)

Depois de selecionar a técnica e clicar em **Avançar**, dê um nome à sua simulação e, opcionalmente, uma descrição.

## <a name="selecting-a-payload"></a>Selecionar uma carga

Em seguida, você precisará selecionar uma carga no catálogo de carga pré-existente.

As cargas têm vários pontos de dados para ajudá-lo a escolher:

- A **taxa de clique** considera quantas pessoas clicaram nesta carga.
- A **taxa de comprometimento prevista** prevê a porcentagem de pessoas que serão comprometidas por essa carga com base em dados históricos para a carga nos clientes do Microsoft defender para Office 365.
- **Simulações iniciadas** conta o número de vezes que essa carga foi usada em outras simulações.
- A **complexidade**, disponível através de **filtros**, é calculada com base no número de indicadores dentro da carga que apontam os destinos em que eles estão sendo um ataque. Mais indicadores levam a uma complexidade mais baixa.
- **Fonte**, disponível através de **filtros**, indica se a carga foi criada em seu locatário ou faz parte do catálogo de carga (global) da Microsoft.

![Carga selecionada dentro do treinamento de simulação de ataque no centro de segurança do Microsoft 365](../../media/attack-sim-preview-select-payload.png)

Selecione uma carga na lista para ver uma visualização da carga com informações adicionais sobre ela.

Se quiser criar sua própria carga, leia [criar uma carga de treinamento de simulação de ataque](attack-simulation-training-payloads.md).

## <a name="audience-targeting"></a>Segmentação por público-alvo

Agora é hora de selecionar o público da simulação. Você pode optar por **incluir todos os usuários em sua organização** ou **incluir apenas usuários e grupos específicos**.

Ao optar por **incluir apenas usuários e grupos específicos** , você pode:

- **Adicione usuários**, que permite que você aproveite a pesquisa para seu locatário, bem como recursos avançados de pesquisa e filtragem, como direcionar os usuários que não foram direcionados a uma simulação nos últimos 3 meses.
  ![Filtragem de usuário no treinamento de simulação de ataque no centro de segurança do Microsoft 365](../../media/attack-sim-preview-user-targeting.png)
- **Import from CSV** permite que você importe um conjunto predefinido de usuários para esta simulação.

## <a name="assigning-training"></a>Atribuindo treinamento

Recomendamos que você atribua treinamento para cada simulação, pois os funcionários que passam pelo treinamento são menos suscetíveis a ataques semelhantes.

Você pode optar por ter o treinamento atribuído ou selecionar cursos e módulos de treinamento por conta própria.

Selecione a **data de conclusão de treinamento** para garantir que os funcionários concluam o treinamento em tempo hábil.

> [!NOTE]
> Se você optar por selecionar cursos e módulos por conta própria, ainda poderá ver o conteúdo recomendado, bem como todos os cursos e módulos disponíveis.
>
> ![Adição de treinamento recomendado ao treinamento de simulação de ataque no centro de segurança do Microsoft 365](../../media/attack-sim-preview-add-training.png)

Nas próximas etapas, você precisará **Adicionar treinamentos** se optar por selecioná-lo e personalizar sua página inicial de treinamento. Você poderá visualizar a página de aterrissagem de treinamento, bem como alterar o cabeçalho e o corpo do mesmo.

## <a name="launch-details-and-review"></a>Detalhes e análise do lançamento

Agora que tudo está configurado, você pode iniciar essa simulação imediatamente ou agendá-la para uma data posterior. Você também precisará escolher quando terminar esta simulação. Vamos parar a captura da interação com essa simulação após o horário selecionado.

**Habilitar a entrega de fuso horário que reconhece a região** para entregar mensagens de ataque simuladas a seus funcionários durante as horas de trabalho com base em sua região.

Após concluir, clique em **Avançar** e revise os detalhes de sua simulação. Clique em **Editar** em qualquer uma das partes para voltar e alterar os detalhes que precisam ser alterados. Após concluir, clique em **Enviar**.
