---
title: Modos de Exibição de Campanhas no Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Saiba mais sobre os Modos de Exibição de Campanhas na Proteção Avançada contra Ameaças do Office 365.
ms.openlocfilehash: 2d43b73a613ad6399a151a6bda39f236c7c913e8
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT + HT Review
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962756"
---
# <a name="campaign-views-in-office-365-atp"></a>Modos de Exibição de Campanha no Office 365 ATP

> [!NOTE]
> Os recursos descritos neste tópico estão atualmente em versão prévia e estão sujeitos a alterações.

Os Modos de Exibição de Campanhas é um recurso no ATP (Proteção Avançada contra Ameaças) no Centro de Conformidade e Segurança do Office 365 que identifica e categoriza os ataques de phishing no serviço. Os Modos de Exibição de Campanhas podem ajudá-lo a:

- Investigar e responder de forma eficiente os ataques de phishing.

- Entender melhor o escopo do ataque.

- Mostrar valor aos tomadores de decisões.

Os Modos de Exibição de Campanhas permitem que você veja o panorama de um ataque de forma mais rápida e completa do que qualquer pessoa.

## <a name="what-is-a-campaign"></a>O que é uma campanha?

Uma campanha é um ataque coordenado por email contra uma ou várias organizações. Hoje, os ataques por email que roubam credenciais e dados da empresa são negócios grandes e lucrativos. À medida que as tecnologias focam seus esforços para interromper os ataques, os invasores são sofisticados o suficiente para modificar seus métodos em um esforço para garantir o sucesso contínuo.

A Microsoft aproveita o vasto volume de dados e experiência de antiphishing, antispam e antimalware no serviço do Office 365 em todo o mundo para identificar as campanhas. As informações do ataque são analisadas e classificadas de acordo com vários fatores. Por exemplo:

- **Fonte de ataque**: endereços IP de origem e domínios de email do remetente.

- **Propriedades da mensagem de ataque**: o conteúdo, estilo e tom das mensagens de ataque.

- **Destinatários de um ataque**: domínios do destinatário, funções de trabalho do destinatário (administradores, executivos, etc.), tipos de empresa (grandes, pequenas, públicas, privadas etc.) e setores.

- **Payload de ataque**: links mal-intencionados, anexos ou outros payloads.

## <a name="campaign-views-the-office-365-security--compliance-center"></a>Modos de Exibição de Campanhas no Centro de Conformidade e Segurança do Office 365

Os Modos de Exibição de Campanhas estão disponíveis no [Centro de Conformidade e Segurança](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center) nos seguintes locais:

- **Gerenciamento de ameaças** \> **Explorer** \> **Exibir** \> **Phish** \> **Campanha principal (visualização)**

- **Gerenciamento de ameaças** \> **Explorer** \> **Exibir** \> **Todos os emails** \> **Campanha principal (visualização)**

![Visão geral das campanhas no Centro de Conformidade e Segurança](../media/campaigns-overview.png)

> [!TIP]
> No momento, a única filtragem disponível é o intervalo de datas. Caso não veja nenhum dado da campanha, experimente alterar o intervalo de datas.

A página Visão geral mostra as seguintes informações sobre a campanha:

- **Nome**

- **Exemplo de assunto**: a linha de assunto de uma das mensagens na campanha. Observe que _todas_ as mensagens na campanha não terão necessariamente essa mesma linha de assunto.

- **Tipo**: atualmente, esse valor será sempre **Phish**.

- **Subtipo**: quando disponível, a marca que está sendo visada por esta campanha. Quando a detecção é orientada pela tecnologia ATP, o prefixo **ATP-** é adicionado ao valor do subtipo.

- **Destinatários**: o número de usuários que foram alvos desta campanha.

- **Entregue**: o número de usuários que receberam mensagens desta campanha na caixa de entrada.

- **ID**: o identificador exclusivo da campanha.

Quando você clica no nome de uma campanha, os detalhes da campanha aparecem em um submenu.

## <a name="campaign-details"></a>Detalhes da campanha

No modo de exibição de detalhes da campanha, estão disponíveis muitas informações sobre a campanha:

- Informações da campanha:

  - **ID**: o mesmo identificador exclusivo da campanha na tela visão geral.

  - **Iniciado** e **Finalizado**: o filtro do intervalo de datas selecionado.

  - **Impacto**: o número de mensagens enviadas no intervalo de datas selecionado, quantas eram "caixa de entrada" (isto é, entregue na caixa de entrada) e quantos usuários clicaram na URL do payload na mensagem de phishing.

  - Uma linha do tempo de atividade da campanha: quando a campanha começou e terminou e o volume de mensagens neste período.

### <a name="campaign-flow"></a>Fluxo de campanha

Os detalhes importantes sobre a campanha são apresentados em um diagrama de fluxo horizontal (conhecido como diagrama _Sankey_) na seção **Fluxo**. Esses detalhes ajudarão você a entender os elementos da campanha e o impacto potencial na sua organização.

![Detalhes da campanha que não contêm cliques de usuários na URL](../media/campaign-details-no-recipient-actions.png)

Se passar o mouse sobre uma faixa horizontal no diagrama, você verá o número de mensagens relacionadas (por exemplo, mensagens de um determinado IP de origem, mensagens do IP de origem usando o domínio do remetente especificado, etc.).

O diagrama contém as seguintes informações:

- **IPs do remetente**

- **Domínios do remetente**

- **Filtrar veredictos**: os valores aqui estão relacionados aos veredictos do filtro antiphishing e antispam disponíveis, como descrito em [Cabeçalhos de mensagem antispam](anti-spam-message-headers.md). O mais importante aqui são os valores **Permissão do locatário**, que significa que uma configuração definida na organização permitiu uma mensagem que de outra forma seria bloqueada pelo serviço (por exemplo, um domínio na lista de Remetentes permitidos).

  - **Bloqueio do locatário**: esse valor indica que uma configuração na sua organização (por exemplo, uma entrada de domínio na [lista de Remetentes bloqueados](create-block-sender-lists-in-office-365.md)) detectou a mensagem e determinou onde ela foi entregue. Para mensagens que não estão em quarentena, examine as configurações de remetentes bloqueados para determinar por que a mensagem foi entregue.

  - **Detectado**

  - **Permissão do locatário**

- **Locais de entrega**: Você provavelmente desejará investigar as mensagens que foram realmente entregues aos destinatários (na pasta Caixa de Entrada ou Lixo Eletrônico), mesmo se os usuários não clicarem na URL do payload na mensagem. Você também pode remover as mensagens em quarentena em [Colocar mensagens de email em quarentena no Office 365](quarantine-email-messages.md).

  - **Pasta Lixo Eletrônico**

  - **Quarentena**

  - **Caixa de Entrada**

#### <a name="url-clicks"></a>Cliques na URL

Há sempre uma chance de que as mensagens entregues na pasta Caixa de Entrada ou Lixo Eletrônico do destinatário possam ser acionadas pelo usuário (ou seja, o usuário clicará na URL mal-intencionada da mensagem). Se eles não clicaram, isso é uma pequena vitória, embora você certamente precise determinar por que a mensagem prejudicial foi entregue à caixa de correio deles.

Se um usuário clicou na URL mal-intencionada, as ações serão exibidas na área do diagrama **Cliques na URL**.

![Detalhes da campanha que contêm cliques de usuários na URL](../media/campaign-details-with-recipient-actions.png)

- **Bloqueio de Links Seguros**: este valor indica que o destinatário clicou na URL do payload na mensagem, mas foi bloqueado pelas políticas de [Links Seguros ATP](atp-safe-links.md) da sua organização.

- **Substituir Bloqueio de Links Seguros**: esse valor também indica que o destinatário clicou na URL do payload na mensagem, os Links de Seguros do ATP tentaram pará-lo, mas eles tiveram permissão para substituir o bloqueio. É necessário investigar as suas [políticas de Links Seguros](set-up-atp-safe-links-policies.md)para ver por que os usuários têm permissão para substituir o veredicto dos Links Seguros e clicar em URLs mal-intencionadas.

### <a name="tabs"></a>Guias

Há várias guias no modo de exibição de detalhes da campanha que permitem uma investigação mais detalhada.

- **Cliques na URL**: se não houve cliques na URL do payload na mensagem de phishing, essa seção ficará em branco. Se um usuário conseguiu clicar na URL, você

  - **Usuário**<sup>\*</sup>

  - **URL**<sup>\*</sup>

  - **Hora do clique**

  - **Ação do clique**

- **IPs do remetente**

  - **IP do remetente**<sup>\*</sup>

  - **Contagem total**

  - **Contagem na caixa de entrada**

  - **Contagem bloqueado**

  - **SPF transmitido**

- **Remetentes**

  - **Remetente**

  - **Contagem total**

  - **Contagem na caixa de entrada**

  - **Contagem bloqueado**

  - **DKIM aprovado**

  - **DMARC aprovado**

- **Payloads**

  - **URL**<sup>\*</sup>

  - **Contagem total**

<sup>\*</sup> Clicar nesse valor abre um novo submenu que contém mais detalhes sobre o item especificado (usuário, URL, etc.) na parte superior do modo de exibição de detalhes da campanha. Para retornar ao modo de exibição de detalhes da campanha, clique em **Concluído** no novo submenu.

### <a name="buttons"></a>Botões

Os botões no modo de exibição de detalhes da campanha permitem usar os recursos do Explorador de Ameaças para investigar ainda mais a campanha.

- **Explorar campanhas**: abre uma nova guia de pesquisa do Explorador de Ameaças usando o valor **ID da campanha** como filtro de pesquisa.

- **Explorar mensagens da Caixa de Entrada**: abre uma nova guia de pesquisa do Explorador de Ameaças usando a **ID da campanha** e o **Local de entrega: Caixa de Entrada** como filtro da pesquisa.
