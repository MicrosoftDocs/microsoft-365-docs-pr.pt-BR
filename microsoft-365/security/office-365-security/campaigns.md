---
title: Modos de Exibição de Campanhas no Office 365 ATP
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 350f4f9007bf6f09836080af65802a9757532dcc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083530"
---
# <a name="campaign-views-in-office-365-atp"></a>Modos de Exibição de Campanha no Office 365 ATP

Os Modos de Exibição de Campanhas é um recurso no ATP (Proteção Avançada contra Ameaças) no Centro de Conformidade e Segurança do Office 365 que identifica e categoriza os ataques de phishing no serviço. Os Modos de Exibição de Campanhas podem ajudá-lo a:

- Investigar e responder de forma eficiente os ataques de phishing.

- Entender melhor o escopo do ataque.

- Mostrar valor aos tomadores de decisões.

Os Modos de Exibição de Campanhas permitem que você veja o panorama de um ataque de forma mais rápida e completa do que qualquer pessoa.

## <a name="what-is-a-campaign"></a>O que é uma campanha?

Uma campanha é um ataque coordenado por email contra uma ou várias organizações. Os ataques de email que roubam credenciais e dados da empresa são um setor grande e lucrative. À medida que as tecnologias aumentam em um esforço para interromper ataques, os invasores modificam seus métodos em um esforço para garantir o sucesso contínuo.

A Microsoft aproveita as vastas quantidades de dados anti-phishing, antispam e antimalware em todo o serviço do Office 365 para ajudar a identificar campanhas. Analisamos e classificamos as informações de ataque de acordo com vários fatores. Por exemplo:

- **Fonte de ataque**: endereços IP de origem e domínios de email do remetente.

- **Propriedades da mensagem de ataque**: o conteúdo, estilo e tom das mensagens de ataque.

- **Destinatários de um ataque**: domínios do destinatário, funções de trabalho do destinatário (administradores, executivos, etc.), tipos de empresa (grandes, pequenas, públicas, privadas etc.) e setores.

- **Carga de ataque**: links mal-intencionados, anexos ou outras cargas nas mensagens de ataque.

Uma campanha pode ser de vida curta ou pode abranger vários dias, semanas ou meses com períodos ativos e inativos. Uma campanha pode ser iniciada em sua organização específica ou sua organização pode fazer parte de uma campanha maior em várias empresas.

## <a name="campaign-views-the-office-365-security--compliance-center"></a>Modos de Exibição de Campanhas no Centro de Conformidade e Segurança do Office 365

Os modos de exibição de campanha estão disponíveis no [centro de conformidade e segurança &](https://protection.office.com) nas **campanhas**de **Gerenciamento** \> de ameaças.

![Visão geral das campanhas no Centro de Conformidade e Segurança](../../media/campaigns-overview.png)

Você também pode acessar o modo de exibição campanhas de:

- **** \> **** Gerenciador \> de gerenciamento de ameaças **Exibir** \> **campanhas**

- **** \> **** Gerenciador \> de gerenciamento de ameaças **Exibir** \> **todas as** \> **campanhas** de email

> [!TIP]
> Caso não veja nenhum dado da campanha, experimente alterar o intervalo de datas.

A página Visão geral mostra as seguintes informações sobre a campanha:

- **Nome**

- **Exemplo de assunto**: a linha de assunto de uma das mensagens na campanha. Observe que todas as mensagens na campanha não terão necessariamente o mesmo assunto.

- **Tipo**: atualmente, esse valor é sempre **Phish**.

- **Subtipo**: quando disponível, a marca que está sendo visada por esta campanha. Quando a detecção é orientada pela tecnologia ATP, o prefixo **ATP-** é adicionado ao valor de subtipo.

- **Destinatários**: o número de usuários que foram alvos desta campanha.

- **Caixa de entrada**: o número de usuários que receberam mensagens desta campanha em sua caixa de entrada (não entregue a lixo eletrônico).

- **Clicado**: o número de usuários que clicaram na URL na mensagem de phishing.

- **Taxa de clique**: a porcentagem conforme calculada por "**clicado** / em**caixa de entrada**". Esse valor é um indicador da eficácia da campanha e se os destinatários podem identificar a mensagem como phishing e evitar clicar na URL de carga.

- **Visitado**: quantos usuários realmente o fizeram no site de carga de transferência. Se houver valores **clicados** , mas os links seguros bloquearam o acesso ao site, esse valor será zero.

Quando você clica no nome de uma campanha, os detalhes da campanha aparecem em um submenu.

## <a name="campaign-details"></a>Detalhes da campanha

No modo de exibição de detalhes da campanha, estão disponíveis muitas informações sobre a campanha:

- Informações da campanha:

  - **ID**: o identificador exclusivo da campanha.

  - **Iniciado** e **Finalizado**: o filtro do intervalo de datas selecionado.

  - **Impacto**: os seguintes dados para o filtro de intervalo de datas selecionado:
  
    - O número total de destinatários.

    - O número de mensagens que foram "caixa de entrada" (isto é, entregues na caixa de entrada, não em lixo eletrônico).

    - Quantos usuários clicaram na carga da URL na mensagem de phishing.

    - Howe muitos usuários visitaram a URL.

  - Uma linha do tempo de atividade da campanha: quando a campanha começou e terminou e o volume de mensagens neste período.

### <a name="campaign-flow"></a>Fluxo de campanha

Os detalhes importantes sobre a campanha são apresentados em um diagrama de fluxo horizontal (conhecido como diagrama _Sankey_) na seção **Fluxo**. Esses detalhes ajudarão você a entender os elementos da campanha e o impacto potencial na sua organização.

![Detalhes da campanha que não contêm cliques de usuários na URL](../../media/campaign-details-no-recipient-actions.png)

Se passar o mouse sobre uma faixa horizontal no diagrama, você verá o número de mensagens relacionadas (por exemplo, mensagens de um determinado IP de origem, mensagens do IP de origem usando o domínio do remetente especificado, etc.).

O diagrama contém as seguintes informações:

- **IPs do remetente**

- **Domínios do remetente**

- **Filtrar veredictos**: os valores aqui estão relacionados aos veredictos do filtro antiphishing e antispam disponíveis, como descrito em [Cabeçalhos de mensagem antispam](anti-spam-message-headers.md). Os valores disponíveis são descritos na tabela a seguir:

  |Valor|Veredicto de filtro de spam|Descrição|
  |:-----|:-----|:-----|
  | **Permitido**|`SFV:SKN` <br/><br/> `SFV:SKI`|A mensagem foi marcada como não spam e/ou a filtragem ignorada antes de ser avaliada pelo filtro de spam (por exemplo, por uma regra de fluxo de emails, também conhecida como regra de transporte).<br/><br/>A mensagem ignorou a filtragem de spam por outros motivos (por exemplo, o remetente e o destinatário parecem estar na mesma organização).|
  |**Blocked**|`SFV:SKS`|A mensagem foi marcada como spam antes de ser avaliada pelo filtro de spam (por exemplo, por uma regra de fluxo de emails).|
  |**Detectado**|`SFV:SPM`|A mensagem foi marcada como spam pelo filtro de spam.|
  |**Não detectado**|`SFV:NSPM`|A mensagem foi marcada como não spam pelo filtro de spam.|
  |**Solta**|`SFV:SKQ`|A mensagem ignorou a filtragem de spam porque foi liberada da quarentena.|
  |**Permissão de locatário**<sup>\*</sup>|`SFV:SKA`|A mensagem ignorou a filtragem de spam devido à configuração de política de filtro de spam (por exemplo, o remetente ou domínio estava na lista de **permissões de remetente** ).|
  |**Bloco de locatário**<sup>\*\*</sup>|`SFV:SKA`|A mensagem foi bloqueada por filtragem de spam devido à configuração de política de filtro de spam (por exemplo, o remetente ou domínio estava na lista de **bloqueios de remetentes** ).|
  |**Usuário permitir**<sup>\*</sup>|`SFV:SFE`|A mensagem ignorou a filtragem de spam porque o remetente estava na lista de remetentes confiáveis do usuário no Outlook.|
  |**Bloco de usuário**<sup>\*\*</sup>|`SFV:BLK`|A mensagem foi bloqueada por filtragem de spam porque o remetente estava na lista de remetentes bloqueados de um usuário no Outlook.|
  |**ZAP**|n/d|A [limpeza automática de zero horas (zap)](zero-hour-auto-purge.md) levou à mensagem entregue de acordo com sua configuração de política de filtro de spam (movida para a pasta lixo eletrônico ou colocada em quarentena).|

  <sup>\*</sup>Revise suas definições de configuração de política de filtro de spam, pois a mensagem permitida provavelmente teria sido bloqueada pelo serviço.

  <sup>\*\*</sup>Revise suas definições de configuração de política de filtro de spam, pois essas mensagens devem ser colocadas em quarentena, não entregues.

- **Locais de entrega**: Você provavelmente desejará investigar as mensagens que foram realmente entregues aos destinatários (na pasta Caixa de Entrada ou Lixo Eletrônico), mesmo se os usuários não clicarem na URL do payload na mensagem. Você também pode remover as mensagens em quarentena da quarentena. Para obter mais informações, consulte [Quarantine Email messages in Office 365](quarantine-email-messages.md).

  - **Pasta excluída**

  - **Abandonado**

  - **Externo**: o destinatário está localizado em sua organização de email local.

  - **Falhou**

  - **Encaminhadas**

  - **Caixa de Entrada**

  - **Pasta Lixo Eletrônico**

  - **Quarentena**

  - **Unknown**

> [!NOTE]
> Em todas as camadas que contêm mais de 10 itens, os dez principais itens são mostrados, enquanto o restante é agrupado em **outros**.

#### <a name="url-clicks"></a>Cliques na URL

Quando uma mensagem de phishing é entregue a um destinatário (na caixa de entrada ou na pasta lixo eletrônico), há sempre a chance de que o usuário clique na URL de carga. Não clicar na URL em uma mensagem entregue é uma pequena medida do sucesso, mas você precisa determinar por que a mensagem de phishing foi entregue à caixa de correio em primeiro lugar.

Se um usuário clicou na URL de carga na mensagem de phishing, as ações são exibidas na área de **cliques da URL** do diagrama no modo de exibição detalhes da campanha.

- **Permitido**

- **BlockPage**: o destinatário clicou na URL de carga, mas seu acesso ao site mal-intencionado foi bloqueado pelas políticas de [links seguros de ATP](atp-safe-links.md) em sua organização.

- **BlockPageOverride**: o destinatário clicou na URL de carga da mensagem, os links seguros de ATP tentaram interrompê-los, mas eles tinham permissão para substituir o bloco. Você precisa investigar suas [políticas de links seguros](set-up-atp-safe-links-policies.md) para ver por que os usuários têm permissão para substituir os links de segurança veredicto e continuar no site mal-intencionado.

- **PendingDetonationPage**: os anexos seguros de ATP estão no processo de abertura da URL de carga em um ambiente de computador virtual e ver o que acontece.

- **PendingDetonationPageOverride**: o destinatário tinha permissão para substituir o processo de acionamento de carga e abrir a URL sem aguardar os resultados.

### <a name="tabs"></a>Guias

Há várias guias no modo de exibição de detalhes da campanha que permitem uma investigação mais detalhada.

- **Cliques de URL**: se os usuários não clicar na URL de carga na mensagem de phishing, esta seção ficará em branco. Se um usuário conseguir clicar na URL, os seguintes valores serão preenchidos:

  - **Usuário**<sup>\*</sup>

  - **URL**<sup>\*</sup>

  - **Hora do clique**

  - **Ação do clique**

- **IPs do remetente**

  - **IP do remetente**<sup>\*</sup>

  - **Contagem total**

  - **Contagem na caixa de entrada**

  - **Contagem bloqueado**

  - **SPF aprovado**: o remetente foi autenticado pela [estrutura de política de remetente (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md). Um remetente que não passa pela validação SPF indica que o remetente não está autenticado ou a mensagem está falsificando um remetente legítimo.

- **Remetentes**

  - **Remetente**: Este é o endereço do remetente real no comando mail SMTP from, que não é necessariamente o endereço de email que os usuários vêem em seus clientes de email.

  - **Contagem total**

  - **Caixa de entrada**

  - **Não caixa de entrada**

  - **DKIM passado**: o remetente foi autenticado por [chaves de domínio identificadas por email (DKIM)](support-for-validation-of-dkim-signed-messages.md). Um remetente que não passa DKIM validação indica que o remetente não está autenticado ou a mensagem está falsificando um remetente legítimo.

  - **DMARC passado**: o remetente foi autenticado por [autenticação de mensagens baseadas em domínio, relatórios e conformidade (DMARC)](use-dmarc-to-validate-email.md). Um remetente que não passa DMARC validação indica que o remetente não está autenticado ou a mensagem está falsificando um remetente legítimo.

- **Payloads**

  - **URL**<sup>\*</sup>

  - **Contagem total**

<sup>\*</sup> Clicar nesse valor abre um novo submenu que contém mais detalhes sobre o item especificado (usuário, URL, etc.) na parte superior do modo de exibição de detalhes da campanha. Para retornar ao modo de exibição de detalhes da campanha, clique em **Concluído** no novo submenu.

### <a name="buttons"></a>Botões

Os botões no modo de exibição de detalhes da campanha permitem usar os recursos do Explorador de Ameaças para investigar ainda mais a campanha.

- **Explorar campanhas**: abre uma nova guia de pesquisa do Explorador de Ameaças usando o valor **ID da campanha** como filtro de pesquisa.

- **Explorar mensagens de caixa de entrada**: abre uma nova guia de pesquisa do explorador de ameaças usando a **ID de campanha** e o **local de entrega: caixa de entrada** como o filtro de pesquisa.
