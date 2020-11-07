---
title: Simular um ataque de phishing com o Microsoft defender para
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
description: Saiba como simular ataques de phishing e treine seus usuários sobre prevenção de phishing com treinamento de simulação de ataque no Microsoft defender para Office 365.
ms.openlocfilehash: b9b8a431fc28942f5e11bc7ce2e805ca082cf36b
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944414"
---
# <a name="simulate-a-phishing-attack"></a>Simular um ataque de phishing

O treinamento do simulador de ataques através do Microsoft defender para Office 365 permite que você execute simulações de ataques de Cyber benignas em sua organização para testar suas práticas e políticas de segurança, além de treinar os funcionários da sua organização para aumentar a conscientização e reduzir seu susceptibility a ataques. O procedimento a seguir orienta você na simulação de um ataque de phishing usando treinamento de simulador de ataques.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Para iniciar um ataque de phishing simulado, navegue até o [centro de segurança do Microsoft 365](https://security.microsoft.com/). Em **Email & colaboração** , clique em **simulador de ataques** e alterne para a guia [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) .

Em **simulações** , selecione **+ iniciar uma simulação**.

![Iniciar um botão de simulação no centro de segurança do Microsoft 365](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> A qualquer momento durante a criação da simulação, você pode salvar e fechar para continuar Configurando a simulação mais tarde.

## <a name="selecting-a-social-engineering-technique"></a>Selecionar uma técnica de engenharia social

Selecione dentre 4 técnicas diferentes, organizadas da [estrutura Mitre ATT&CK®](https://attack.mitre.org/techniques/enterprise/). Cargas diferentes estão disponíveis para diferentes técnicas.

- A **coleta de credenciais** tenta coletar credenciais de funcionários, levando-os a um site de aparência conhecido com caixas de entrada para enviar um nome de usuário e senha.
- O **anexo de malware** adiciona um anexo mal-intencionado a uma mensagem. Quando aberto, esse anexo executará um código arbitrário que ajudará o invasor a comprometer o dispositivo de destino.
- **Link no anexo** é um tipo de coleta de credenciais híbrido. Um invasor insere uma URL em um anexo de email. A URL no anexo segue a mesma técnica que a coleta de credenciais.
- O **link para malware** executará um código arbitrário de um arquivo hospedado em um site de compartilhamento de arquivos conhecido. Um link para este arquivo mal-intencionado é adicionado à mensagem enviada ao destino e clicar nele executará o arquivo e ajudará o invasor a comprometer o dispositivo de destino.

> [!TIP]
> Ao clicar em **Exibir detalhes** dentro da descrição de cada técnica, serão exibidas mais informações sobre a técnica, bem como as etapas de simulação dessa técnica.
>
> ![Etapas de simulação para coleta de credenciais no treinamento de simulação de ataque no centro de segurança do Microsoft 365](../../media/attack-sim-preview-sim-steps.png)

Depois de selecionar a técnica e clicar em **Avançar** , dê um nome e, opcionalmente, uma descrição à sua simulação.

## <a name="selecting-a-payload"></a>Selecionar uma carga

Em seguida, você precisará selecionar uma carga no catálogo de carga pré-existente.

As cargas têm vários pontos de dados para ajudá-lo a escolher:

- A **taxa de clique** considera quantas pessoas clicaram nesta carga.
- A **taxa de comprometimento prevista** prevê a porcentagem de pessoas que serão comprometidas por essa carga com base em dados históricos para esta carga nos clientes do Microsoft defender para Office 365.
- **Simulações iniciadas** conta o número de vezes que essa carga foi usada em outras simulações.
- A **complexidade** , disponível através de **filtros** , é calculada com base no número de indicadores dentro da carga que apontam os destinos em que eles estão sendo um ataque. Mais indicadores levam a uma complexidade mais baixa.
- **Fonte** , disponível através de **filtros** , indica se a carga foi criada em seu locatário ou faz parte do catálogo de carga (global) da Microsoft.

![Carga selecionada dentro do treinamento de simulação de ataque no centro de segurança do Microsoft 365](../../media/attack-sim-preview-select-payload.png)

Selecione uma carga na lista para ver uma visualização da carga com informações adicionais sobre ela.

Se quiser criar sua própria carga, leia [criar uma carga de treinamento de simulação de ataque](attack-simulation-training-payloads.md).

## <a name="audience-targeting"></a>Segmentação por público-alvo

Agora é hora de selecionar o público da simulação. Você pode optar por **incluir todos os usuários em sua organização** ou **incluir apenas usuários e grupos específicos**. 

Ao optar por **incluir apenas usuários e grupos específicos** , você pode:

- **Adicione usuários** , que permite que você aproveite a pesquisa para seu locatário, bem como recursos avançados de pesquisa e filtragem, como direcionar os usuários que não foram direcionados a uma simulação nos últimos 3 meses.
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
