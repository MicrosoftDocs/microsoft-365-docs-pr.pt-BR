---
title: Exibições de campanha no Plano do Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Saiba mais sobre exibições de campanha no Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e3c84b9e6253dd813ff930314fc2c1d0a947e94e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51202935"
---
# <a name="campaign-views-in-microsoft-defender-for-office-365"></a>Exibições de campanha no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)

Exibições de campanha é um recurso no Microsoft Defender para Office 365 Plano 2 (por exemplo, Microsoft 365 E5 ou organizações com um complemento do Plano 2 do Defender para Office 365). Exibições de campanha no Centro de Conformidade & segurança identifica e categoriza ataques de phishing no serviço. Os Modos de Exibição de Campanhas podem ajudá-lo a:

- Investigar e responder de forma eficiente os ataques de phishing.
- Entender melhor o escopo do ataque.
- Mostrar valor aos tomadores de decisões.

Os Modos de Exibição de Campanhas permitem que você veja o panorama de um ataque de forma mais rápida e completa do que qualquer pessoa.

## <a name="what-is-a-campaign"></a>O que é uma campanha?

Uma campanha é um ataque coordenado por email contra uma ou várias organizações. Os ataques de email que roubam credenciais e dados da empresa são uma grande e lucrativa indústria. À medida que as tecnologias aumentam em um esforço para parar ataques, os invasores modificam seus métodos em um esforço para garantir o sucesso contínuo.

A Microsoft aproveita as grandes quantidades de dados anti-phishing, anti-spam e anti-malware em todo o serviço para ajudar a identificar campanhas. Analisamos e classificamos as informações de ataque de acordo com vários fatores. Por exemplo:

- **Fonte de ataque**: Os endereços IP de origem e domínios de email do remetente.
- **Propriedades da** mensagem: o conteúdo, o estilo e o tom das mensagens.
- **Destinatários de mensagens**: Como os destinatários estão relacionados. Por exemplo, domínios de destinatário, funções de trabalho de destinatário (administradores, executivos, etc.), tipos de empresa (grandes, pequenos, públicos, privados etc.) e setores.
- **Carga de ataque**: links mal-intencionados, anexos ou outras cargas nas mensagens.

Uma campanha pode ter curta duração ou pode abranger vários dias, semanas ou meses com períodos ativos e inativos. Uma campanha pode ser lançada contra sua organização específica, ou sua organização pode fazer parte de uma campanha maior em várias empresas.

## <a name="campaign-views-in-the-security--compliance-center"></a>Exibições de campanha no Centro de Conformidade & Segurança

Exibições de campanha estão disponíveis no Centro de [Conformidade & segurança](https://protection.office.com) em  \> **Campanhas** de Gerenciamento de Ameaças ou diretamente em <https://protection.office.com/campaigns> .

![Visão geral das campanhas no Centro de Conformidade e Segurança](../../media/campaigns-overview.png)

Você também pode chegar a Exibições de Campanha a partir de:

- **Gerenciamento de ameaças** \> **Explorer** \> **Exibir** \> **Campanhas**
- **Gerenciamento de ameaças** \> **Explorer** \> **Exibir** \> **Todos os emails** \> **Guia Campanha**
- **Gerenciamento de ameaças** \> **Explorer** \> **Exibir** \> **Phish** \> **Guia Campanha**
- **Gerenciamento de ameaças** \> **Explorer** \> **Exibir** \> **Malware** \> **Guia Campanha**

Para acessar exibições de campanha, você precisa ser membro  dos grupos de função Gerenciamento da **Organização,** Administrador de Segurança ou Leitor de Segurança no Centro de Conformidade & Segurança. Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

## <a name="campaigns-overview"></a>Visão geral das campanhas

A página de visão geral mostra informações sobre todas as campanhas.

Na guia **Campanha** padrão, a área **tipo Campanha** mostra um gráfico de barras que mostra o número de destinatários por dia. Por padrão, o gráfico mostra dados **de Phish** e **Malware.**

> [!TIP]
> Se você não vir dados de campanha, tente alterar o intervalo de datas ou [filtros](#filters-and-settings).

O restante da página de visão geral mostra as seguintes informações na **guia Campanha:**

- **Nome**

- **Exemplo de assunto**: a linha de assunto de uma das mensagens na campanha. Observe que todas as mensagens na campanha não terão necessariamente o mesmo assunto.

- **Direcionado**: a porcentagem conforme calculado por: (o número de destinatários de campanha em sua organização) / (o número total de destinatários na campanha em todas as organizações no serviço). Esse valor indica o grau para o qual a campanha é direcionada somente para sua organização (um valor mais alto) em vez de também para outras organizações no serviço (um valor menor).

- **Tipo:** esse valor é **phishing** ou **malware.**

- **Subtipo**: Esse valor contém mais detalhes sobre a campanha. Por exemplo:
  - **Phish**: onde disponível, a marca que está sendo phished por essa campanha. Por exemplo, `Microsoft` , , , ou `365` `Unknown` `Outlook` `DocuSign` .
  - **Malware**: por exemplo, `HTML/PHISH` ou `HTML/<MalwareFamilyName>` .

  Onde disponível, a marca que está sendo phished por essa campanha. Quando a detecção é controlada pela tecnologia Defender para Office 365, o prefixo **ATP é** adicionado ao valor de subtipo.

- **Destinatários**: o número de usuários que foram alvos desta campanha.

- **Caixa de entrada**: o número de usuários que receberam mensagens dessa campanha em sua Caixa de Entrada (não entregues à pasta Lixo Eletrônico).

- **Clicado**: O número de usuários que clicaram na URL ou abriram o anexo na mensagem de phishing.

- **Taxa de** cliques : A porcentagem conforme calculado por "**Caixa de** Entrada  /  **Clicada**". Esse valor é um indicador da eficácia da campanha. Em outras palavras, se os destinatários foram capazes de identificar a mensagem como phishing e se eles não clicaram na URL de carga.

  Observe que **a taxa de** clique não é usada em campanhas de malware.

- **Visitada**: quantos usuários realmente passaram pelo site de carga. Se houver valores **clicados,** mas links seguros bloquearem o acesso ao site, esse valor será zero.

A **guia Origem** da campanha mostra as fontes de mensagem em um mapa do mundo.

### <a name="filters-and-settings"></a>Filtros e configurações

Na parte superior da página Exibições de Campanha, há várias configurações de filtro e consulta para ajudá-lo a encontrar e isolar campanhas específicas.

![Filtros de campanha](../../media/campaign-filters-and-settings.png)

A filtragem mais básica que você pode fazer é a data/hora inicial e a data/hora de término.

Para filtrar ainda mais a exibição, você pode fazer uma única propriedade com filtragem de vários valores clicando no botão **Tipo** de campanha, fazendo sua seleção e clicando em **Atualizar**.

As propriedades de campanha filtáveis que estão disponíveis no botão **Tipo** de campanha são descritas na lista a seguir:

- **Básico:**
  - **Tipo de campanha**: Selecione **Malware** ou **Phish**. Limpar as seleções tem o mesmo resultado que selecionar ambas.
  - **Nome da campanha**
  - **Subtipo de campanha**
  - **Sender**
  - **Destinatários**
  - **Domínio do remetente**
  - **Assunto**
  - **Nome do arquivo anexo**
  - **Família de malware**
  - **Tags**: Usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias). Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).
  - **Substituições do sistema**
  - **Ação de entrega**
  - **Ação adicional**
  - **Directionality**
  - **Tecnologia de detecção**
  - **Local de entrega original**
  - **Local de entrega mais recente**
  - **Substituições do sistema**

- **Avançado**:
  - **ID da mensagem da Internet**: Disponível no campo de header **message-ID** no header da mensagem. Um valor de exemplo `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` é (observe os colchetes angulares).
  - **ID da** mensagem de rede : um valor GUID que está disponível no campo de header **X-MS-Exchange-Organization-Network-Message-Id** no header da mensagem.
  - **IP do remetente**
  - **Anexo SHA256**: Para encontrar o valor de hash SHA256 de um arquivo no Windows, execute o seguinte comando em um Prompt de Comando: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .
  - **Cluster ID**
  - **ID da Política de Alerta**
  - **Sinal de URL do ZAP**

- **URLs**:
  - **Domínio URL**
  - **Domínio e caminho da URL**
  - **URL**
  - **Caminho da URL**
  - **Clique em veredito**

Para filtragem mais avançada, incluindo a filtragem por várias propriedades, você pode clicar no botão **Filtro** Avançado para criar uma consulta. As mesmas propriedades de campanha estão disponíveis, mas com os seguintes aprimoramentos:

- Você pode clicar **em Adicionar uma condição para** selecionar várias condições.
- Você pode escolher o **operador And** ou **Or** entre as condições.
- Você pode selecionar o item **de** grupo Condição na parte inferior da lista de condições para formar condições complexas compostas.

Quando terminar, clique no **botão Consulta.**

Depois de criar um filtro básico ou avançado, você pode salvá-lo usando **Salvar consulta** ou **Salvar consulta como**. Mais tarde, quando você retornar a Exibições de Campanha, poderá carregar um filtro salvo clicando em Configurações de consulta **salvas.**

Para exportar o gráfico ou a lista de campanhas, clique em **Exportar** e selecione Exportar dados **do gráfico** ou Exportar lista **de campanhas**.

Se você tiver uma assinatura do Microsoft Defender para Ponto de Extremidade, poderá clicar em **Configurações do MDE** para conectar ou desconectar as informações de campanhas com o Microsoft Defender para Ponto de Extremidade. Para obter mais informações, consulte [Integrar o Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade](integrate-office-365-ti-with-mde.md).

## <a name="campaign-details"></a>Detalhes da campanha

Quando você clica no nome de uma campanha, os detalhes da campanha aparecem em um flyout.

### <a name="campaign-information"></a>Informações da campanha

Na parte superior da exibição de detalhes da campanha, as seguintes informações de campanha estão disponíveis:

- **ID**: O identificador exclusivo da campanha.

- **Iniciado** e **encerrado**: a data de início e a data de término da campanha. Observe que essas datas podem se estender além das datas de filtro selecionadas na página de visão geral.

- **Impacto**: Esta seção contém os seguintes dados para o filtro de intervalo de datas selecionado (ou que você seleciona na linha do tempo):
  - O número total de destinatários.
  - O número de mensagens que foram "Em caixa de entrada" (ou seja, entregues à Caixa de Entrada, não à pasta Lixo Eletrônico).
  - Quantos usuários clicaram na carga da URL na mensagem de phishing.
  - Quantos usuários visitaram a URL.

- **Direcionado**: a porcentagem conforme calculado por: (o número de destinatários de campanha em sua organização) / (o número total de destinatários na campanha em todas as organizações no serviço). Observe que esse valor é calculado durante todo o tempo de vida da campanha e não muda com base nos filtros de data.

- Uma linha do tempo interativa da atividade da campanha: a linha do tempo mostra atividade durante todo o tempo de vida da campanha. Por padrão, a área sombreada inclui o filtro de intervalo de datas selecionado na visão geral. Você pode clicar e arrastar para selecionar um ponto de início e ponto de extremidade específicos, que alterarão os dados exibidos na área impacto e no restante da página, conforme descrito nas <u>próximas seções  </u>.

Na barra de título, você pode clicar no botão Baixar o **write-up** da campanha Baixar ícone de gravação da campanha para baixar os detalhes da campanha em um documento do ![ ](../../media/download-campaign-write-up-button.png) Word (por padrão, chamado CampaignReport.docx). Observe que o download contém detalhes durante todo o tempo de vida da campanha (não apenas as datas de filtro selecionadas).

![Informações da campanha](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a>Fluxo de campanha

No meio da exibição de detalhes da campanha, detalhes importantes sobre a campanha são apresentados na seção **Fluxo** em um diagrama de fluxo horizontal (conhecido como diagrama _sankey)._ Esses detalhes ajudarão você a entender os elementos da campanha e o impacto potencial na sua organização.

> [!TIP]
> As informações exibidas no diagrama **Flow** são controladas pelo intervalo de datas sombreado na linha do tempo, conforme descrito na seção anterior.

![Detalhes da campanha que não contêm cliques de usuários na URL](../../media/campaign-details-no-recipient-actions.png)

Se passar o mouse sobre uma faixa horizontal no diagrama, você verá o número de mensagens relacionadas (por exemplo, mensagens de um determinado IP de origem, mensagens do IP de origem usando o domínio do remetente especificado, etc.).

O diagrama contém as seguintes informações:

- **IPs do remetente**
- **Domínios do remetente**
- **Vereditos de filtro:** os valores de veredito estão relacionados aos vereditos de filtragem de phishing e spam disponíveis, conforme descrito em Headers de mensagens [anti-spam.](anti-spam-message-headers.md) Os valores disponíveis são descritos na tabela a seguir:

  ****

  |Valor|Veredito do filtro de spam|Descrição|
  |---|---|---|
  |**Permitido**|`SFV:SKN` <p> `SFV:SKI`|A mensagem foi marcada como não spam e/ou ignorada antes de ser avaliada pela filtragem de spam. Por exemplo, a mensagem foi marcada como não spam por uma regra de fluxo de emails (também conhecida como regra de transporte). <p> A mensagem ignorou a filtragem de spam por outros motivos. Por exemplo, o remetente e o destinatário parecem estar na mesma organização.|
  |**Bloqueado**|`SFV:SKS`|A mensagem foi marcada como spam antes de ser avaliada pela filtragem de spam. Por exemplo, por uma regra de fluxo de emails.|
  |**Detectado**|`SFV:SPM`|A mensagem foi marcada como spam pela filtragem de spam.|
  |**Não Detectado**|`SFV:NSPM`|A mensagem foi marcada como não spam pela filtragem de spam.|
  |**Lançado**|`SFV:SKQ`|A mensagem ignorou a filtragem de spam porque foi liberada da quarentena.|
  |**Locatário Permitir**<sup>\*</sup>|`SFV:SKA`|A mensagem ignorou a filtragem de spam devido às configurações em uma política anti-spam. Por exemplo, o remetente estava na lista de remetentes permitidos ou na lista de domínios permitidos.|
  |**Bloqueio de locatário**<sup>\*\*</sup>|`SFV:SKA`|A mensagem foi bloqueada pela filtragem de spam devido às configurações em uma política anti-spam. Por exemplo, o remetente estava na lista de remetentes permitidos ou na lista de domínios permitidos.|
  |**User Allow**<sup>\*</sup>|`SFV:SFE`|A mensagem ignorou a filtragem de spam porque o remetente estava na lista remetentes seguros de um usuário.|
  |**Bloqueio do usuário**<sup>\*\*</sup>|`SFV:BLK`|A mensagem foi bloqueada pela filtragem de spam porque o remetente estava na lista remetentes bloqueados de um usuário.|
  |**ZAP**|n/d|[O ZAP (limpeza automática](zero-hour-auto-purge.md) de hora zero) moveu a mensagem entregue para a pasta Lixo Eletrônico ou quarentena. Configure a ação em sua política anti-spam.|
  |

  <sup>\*</sup> Revise suas políticas anti-spam, pois a mensagem permitida provavelmente teria sido bloqueada pelo serviço.

  <sup>\*\*</sup> Revise suas políticas anti-spam, pois essas mensagens devem ser colocadas em quarentena, não entregues.

- **Locais** de entrega : você provavelmente vai querer investigar mensagens que foram entregues aos destinatários (na Caixa de Entrada ou na pasta Lixo Eletrônico), mesmo se os usuários não clicarem na URL de carga na mensagem. Você também pode remover as mensagens em quarentena da quarentena. Para obter mais informações, consulte [Mensagens de email em quarentena no EOP](quarantine-email-messages.md).
  - **Pasta excluída**
  - **Descartado**
  - **Externo**: o destinatário está localizado em sua organização de email local em ambientes híbridos.
  - **Falhou**
  - **Encaminhado**
  - **Caixa de Entrada**
  - **Pasta Lixo Eletrônico**
  - **Quarentena**
  - **Unknown**

- **Cliques na URL:** esses valores são descritos na próxima seção.

> [!NOTE]
> Em todas as camadas que contêm mais de 10 itens, os 10 principais itens são mostrados, enquanto o restante é agrupado em **Outros**.

#### <a name="url-clicks"></a>Cliques na URL

Quando uma mensagem de phishing é entregue à pasta Caixa de Entrada ou Lixo Eletrônico de um destinatário, sempre há uma chance de que o usuário clique na URL de carga. Não clicar na URL é uma pequena medida de sucesso, mas você precisa determinar por que a mensagem de phishing foi até mesmo entregue à caixa de correio.

Se um usuário clicou na URL de carga na mensagem de phishing, as ações serão exibidas na área de **cliques** de URL do diagrama na exibição de detalhes da campanha.

- **Permitido**
- **BlockPage**: o destinatário clicou na URL de carga, mas o acesso ao site mal-intencionado foi bloqueado por uma política de [Links](safe-links.md) Seguros em sua organização.
- **BlockPageOverride**: o destinatário clicou na URL de carga na mensagem, Os Links Seguros tentaram impedi-los, mas eles tiveram permissão para substituir o bloco. Inspecione suas políticas [de Links](set-up-safe-links-policies.md) Seguros para ver por que os usuários têm permissão para substituir o veredito de Links Seguros e continuar para o site mal-intencionado.
- **PendingDetonationPage**: Anexos seguros no Microsoft Defender para Office 365 está em processo de abertura e investigação da URL de carga em um ambiente de computador virtual.
- **PendingDetonationPageOverride**: o destinatário teve permissão para substituir o processo de detonação de carga e abrir a URL sem aguardar os resultados.

### <a name="tabs"></a>Guias

As guias na exibição de detalhes da campanha permitem que você investigue ainda mais a campanha.

> [!TIP]
> As informações exibidas nas guias são controladas pelo intervalo de datas sombreado na linha do tempo, conforme descrito na seção [Informações da](#campaign-information) campanha.

- **Cliques na URL**: Se os usuários não clicarem na URL de carga na mensagem, esta seção ficará em branco. Se um usuário conseguir clicar na URL, os seguintes valores serão preenchidos:
  - **Usuário**<sup>\*</sup>
  - **URL**<sup>\*</sup>
  - **Clique em hora**
  - **Clique em veredito**

- **IPs do remetente**
  - **IP do remetente**<sup>\*</sup>
  - **Contagem total**
  - **Caixa de entrada**
  - **Não Em Caixa de Entrada**
  - **SPF passado**: o remetente foi autenticado pela Estrutura de Política do Remetente [(SPF)](how-office-365-uses-spf-to-prevent-spoofing.md). Um remetente que não passa na validação SPF indica um remetente não autenticado ou a mensagem está spoofando um remetente legítimo.

- **Remetentes**
  - **Remetente**: Este é o endereço de remetente real no comando SMTP MAIL FROM, que não é necessariamente o endereço de email From: que os usuários veem em seus clientes de email.
  - **Contagem total**
  - **Caixa de entrada**
  - **Não Em Caixa de Entrada**
  - **DKIM passado**: o remetente foi autenticado por [DKIM (Domain Keys Identified Mail)](support-for-validation-of-dkim-signed-messages.md). Um remetente que não passa na validação DKIM indica um remetente não autenticado ou a mensagem está spoofando um remetente legítimo.
  - **DMARC passado**: o remetente foi autenticado pela Autenticação, Relatório e [Conformidade (DMARC)](use-dmarc-to-validate-email.md)baseada em domínio. Um remetente que não passa na validação DMARC indica um remetente não autenticado ou a mensagem está spoofando um remetente legítimo.

- **Anexos**
  - **Filename**
  - **SHA256**
  - **Família de malware**
  - **Contagem total**

- **URL**
  - **URL**<sup>\*</sup>
  - **Contagem total**

<sup>\*</sup> Clicar nesse valor abre um novo submenu que contém mais detalhes sobre o item especificado (usuário, URL, etc.) na parte superior do modo de exibição de detalhes da campanha. Para retornar ao modo de exibição de detalhes da campanha, clique em **Concluído** no novo submenu.

### <a name="buttons"></a>Botões

Os botões no modo de exibição de detalhes da campanha permitem usar os recursos do Explorador de Ameaças para investigar ainda mais a campanha.

- **Explorar campanhas**: abre uma nova guia de pesquisa do Explorador de Ameaças usando o valor **ID da campanha** como filtro de pesquisa.
- **Explorar mensagens em caixa de entrada**: abre uma nova guia de pesquisa do Explorador de Ameaças usando a **ID** da campanha e o local de **entrega:** Caixa de entrada como o filtro de pesquisa.
