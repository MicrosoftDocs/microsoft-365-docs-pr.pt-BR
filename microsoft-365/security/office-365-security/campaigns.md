---
title: Exibições de campanha no plano do Microsoft Defender para Office 365
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
ms.openlocfilehash: e3b9c1a9a19e38ea83b13d9028af1a6ba042b900
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165914"
---
# <a name="campaign-views-in-microsoft-defender-for-office-365"></a>Exibições de campanha no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Microsoft Defender para Office 365 plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)

Exibições de Campanha é um recurso do Microsoft Defender para Office 365 Plano 2 (por exemplo, Microsoft 365 E5 ou organizações com um complemento do Defender para Office 365 Plano 2). Exibições de campanha no Centro de Conformidade & segurança identifica e categoriza ataques de phishing no serviço. Os Modos de Exibição de Campanhas podem ajudá-lo a:

- Investigar e responder de forma eficiente os ataques de phishing.
- Entender melhor o escopo do ataque.
- Mostrar valor aos tomadores de decisões.

Os Modos de Exibição de Campanhas permitem que você veja o panorama de um ataque de forma mais rápida e completa do que qualquer pessoa.

## <a name="what-is-a-campaign"></a>O que é uma campanha?

Uma campanha é um ataque coordenado por email contra uma ou várias organizações. Os ataques de email que roubarem credenciais e dados da empresa são um setor grande e lucrativo. À medida que as tecnologias aumentam em um esforço para interromper os ataques, os invasores modificam seus métodos em um esforço para garantir o sucesso contínuo.

A Microsoft aproveita as grandes quantidades de dados anti-phishing, anti-spam e anti-malware em todo o serviço para ajudar a identificar campanhas. Analisamos e classificamos as informações de ataque de acordo com vários fatores. Por exemplo:

- **Fonte de ataque:** os endereços IP de origem e domínios de email do remetente.
- **Propriedades da** mensagem: o conteúdo, o estilo e o tom das mensagens.
- **Destinatários da mensagem:** como os destinatários estão relacionados. Por exemplo, domínios de destinatário, funções de trabalho de destinatário (administradores, executivos, etc.), tipos de empresa (grandes, pequenas, públicas, privadas, etc.) e setores.
- **Carga de ataque:** links mal-intencionados, anexos ou outras cargas nas mensagens.

Uma campanha pode ter curta duração ou pode abranger vários dias, semanas ou meses com períodos ativos e inativos. Uma campanha pode ser lançada em sua organização específica ou sua organização pode fazer parte de uma campanha maior em várias empresas.

## <a name="campaign-views-in-the-security--compliance-center"></a>Exibições de Campanha no Centro de Conformidade & segurança

Os Visualizações de Campanhas estão disponíveis no Centro [de Conformidade & segurança](https://protection.office.com) em  \> **campanhas** de gerenciamento de ameaças ou diretamente em <https://protection.office.com/campaigns> .

![Visão geral das campanhas no Centro de Conformidade e Segurança](../../media/campaigns-overview.png)

Você também pode obter os Visualizações de Campanha em:

- **Gerenciamento de ameaças** \> **Explorer** \> **Exibir** \> **Campanhas**
- **Gerenciamento de ameaças** \> **Explorer** \> **Exibir** \> **Todos os emails** \> **Guia Campanha**
- **Gerenciamento de ameaças** \> **Explorer** \> **Exibir** \> **Phish** \> **Guia Campanha**
- **Gerenciamento de ameaças** \> **Explorer** \> **Exibir** \> **Malware** \> **Guia Campanha**

Para acessar as Exibições de Campanha, você precisa ser  membro dos grupos de funções Gerenciamento da **Organização,** Administrador de Segurança ou Leitor de Segurança no Centro de Conformidade e Segurança & Segurança. Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

## <a name="campaigns-overview"></a>Visão geral de campanhas

A página de visão geral mostra informações sobre todas as campanhas.

Na guia **Campanha** padrão, a área **Tipo de** campanha mostra um gráfico de barras que mostra o número de destinatários por dia. Por padrão, o gráfico mostra dados **de phishing** **e malware.**

> [!TIP]
> Se você não vir dados de campanha, tente alterar o intervalo de datas ou [filtros.](#filters-and-settings)

O restante da página de visão geral mostra as seguintes informações na **guia Campanha:**

- **Nome**

- **Exemplo de assunto**: a linha de assunto de uma das mensagens na campanha. Observe que todas as mensagens na campanha não terão necessariamente o mesmo assunto.

- **Direcionado**: a porcentagem conforme calculado por: (o número de destinatários da campanha em sua organização) / (o número total de destinatários na campanha em todas as organizações no serviço). Esse valor indica o grau até o qual a campanha é direcionada somente à sua organização (um valor mais alto) versus também direcionada a outras organizações no serviço (um valor menor).

- **Tipo:** esse valor é **phishing** ou **malware.**

- **Subtipo:** esse valor contém mais detalhes sobre a campanha. Por exemplo:
  - **Phish**: quando disponível, a marca que está sendo phished por esta campanha. Por exemplo, `Microsoft` , `365` , ou `Unknown` `Outlook` `DocuSign` .
  - **Malware:** por exemplo, `HTML/PHISH` ou `HTML/<MalwareFamilyName>` .

  Quando disponível, a marca que está sendo phished por essa campanha. Quando a detecção é controlada pelo Defender para a tecnologia do Office 365, o prefixo **ATP é** adicionado ao valor do subtipo.

- **Destinatários**: o número de usuários que foram alvos desta campanha.

- **Caixa de Entrada:** o número de usuários que receberam mensagens dessa campanha em sua Caixa de Entrada (não entregues na pasta Lixo Eletrônico).

- **Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.

- **Taxa de** cliques : a porcentagem conforme calculado por "  /  **Clicked Inboxed**". Esse valor é um indicador da eficácia da campanha. Em outras palavras, se os destinatários foram capazes de identificar a mensagem como phishing e se eles não clicaram na URL de carga.

  Observe que **a taxa de cliques** não é usada em campanhas de malware.

- **Visitada:** quantos usuários realmente passaram pelo site de conteúdo. Se houver valores **clicados,** mas links seguros bloquearem o acesso ao site, esse valor será zero.

A **guia Origem** da campanha mostra as fontes de mensagem em um mapa do mundo.

### <a name="filters-and-settings"></a>Filtros e configurações

Na parte superior da página Exibições de Campanha, há várias configurações de filtro e consulta para ajudá-lo a encontrar e isolar campanhas específicas.

![Filtros de campanha](../../media/campaign-filters-and-settings.png)

A filtragem mais básica que você pode fazer é a data/hora de início e a data/hora de término.

Para filtrar ainda mais a exibição, você pode fazer  uma única propriedade com vários valores filtrando clicando no botão tipo campanha, fazendo sua seleção e clicando em **Atualizar**.

As propriedades de campanha filtáveis que estão disponíveis no botão **Tipo** de campanha são descritas na lista a seguir:

- **Básico:**
  - **Tipo de campanha:** Selecione **Malware** ou **Phishing**. Limpar as seleções tem o mesmo resultado que selecionar ambas.
  - **Nome da campanha**
  - **Subtipo de campanha**
  - **Sender**
  - **Destinatários**
  - **Domínio do remetente**
  - **Assunto**
  - **Nome do arquivo anexo**
  - **Família de malware**
  - **Marcas**: usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias). Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário.](user-tags.md)
  - **Substituições do sistema**
  - **Ação de entrega**
  - **Ação adicional**
  - **Directionality**
  - **Tecnologia de detecção**
  - **Local de entrega original**
  - **Local de entrega mais recente**
  - **Substituições do sistema**

- **Avançado:**
  - **ID da mensagem** da Internet: Disponível no campo de header **Message-ID** no header da mensagem. Um valor de exemplo `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` é (observe os colchetes angulares).
  - **ID** da mensagem de rede : um valor GUID disponível no campo de header **X-MS-Exchange-Organization-Network-Message-Id** no header da mensagem.
  - **IP do remetente**
  - **Anexo SHA256**: Para encontrar o valor de hash SHA256 de um arquivo no Windows, execute o seguinte comando em um Prompt de Comando: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .
  - **Cluster ID**
  - **ID da Política de Alerta**
  - **Sinal de URL da ZAP**

- **URLs**:
  - **Domínio da URL**
  - **Domínio e caminho da URL**
  - **URL**
  - **Caminho da URL**
  - **Click verdict**

Para uma filtragem mais avançada, incluindo a filtragem por várias propriedades, você pode clicar no botão Filtro Avançado para criar uma consulta.  As mesmas propriedades de campanha estão disponíveis, mas com os seguintes aprimoramentos:

- Você pode clicar **em Adicionar uma condição** para selecionar várias condições.
- Você pode escolher o **operador And** ou **Or** entre condições.
- Você pode selecionar o item **de grupo** Condição na parte inferior da lista de condições para formar condições compostas complexas.

Quando terminar, clique no **botão Consulta.**

Depois de criar um filtro básico ou avançado, você pode salvá-lo usando a consulta Salvar ou **Salvar como**.  Mais tarde, quando você retornar aos Exibições de Campanha, poderá carregar um filtro salvo clicando nas configurações de consulta **Salvas.**

Para exportar o gráfico ou a lista de campanhas, clique em **Exportar** e selecionar Exportar dados **do gráfico** ou Exportar lista **de campanhas.**

Se você tiver uma assinatura do Microsoft Defender para Ponto de Extremidade, poderá clicar em Configurações **MDE** para conectar ou desconectar as informações de campanhas com o Microsoft Defender para o Ponto de Extremidade. Para obter mais informações, consulte [Integrar o Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade.](integrate-office-365-ti-with-wdatp.md)

## <a name="campaign-details"></a>Detalhes da campanha

Quando você clica no nome de uma campanha, os detalhes da campanha aparecem em um flyout.

### <a name="campaign-information"></a>Informações da campanha

Na parte superior da exibição de detalhes da campanha, as seguintes informações da campanha estão disponíveis:

- **ID**: o identificador de campanha exclusivo.

- **Iniciado** e **encerrado:** a data de início e a data de término da campanha. Observe que essas datas podem se estender além das datas de filtro selecionadas na página de visão geral.

- **Impacto:** esta seção contém os seguintes dados para o filtro de intervalo de datas selecionado (ou selecionado na linha do tempo):
  - O número total de destinatários.
  - O número de mensagens que foram "Caixas de Entrada" (ou seja, entregues na Caixa de Entrada, não na pasta Lixo Eletrônico).
  - Quantos usuários clicaram na carga da URL na mensagem de phishing.
  - Como muitos usuários visitaram a URL.

- **Direcionado**: a porcentagem conforme calculado por: (o número de destinatários da campanha em sua organização) / (o número total de destinatários na campanha em todas as organizações no serviço). Observe que esse valor é calculado durante todo o tempo de vida da campanha e não muda com base nos filtros de data.

- Uma linha do tempo interativa da atividade da campanha: a linha do tempo mostra a atividade durante todo o tempo de vida da campanha. Por padrão, a área sombreada inclui o filtro de intervalo de datas selecionado na visão geral. Você pode clicar e arrastar para selecionar um ponto inicial e um ponto de extremidade específicos, o que alterará os dados exibidos na área de Impacto e no restante da página, conforme descrito nas <u>próximas seções.  </u>

Na barra de título, você pode clicar no botão Baixar o **write-up** da campanha Baixar o ícone de gravação da campanha para baixar os detalhes da campanha em um documento do ![ ](../../media/download-campaign-write-up-button.png) Word (por padrão, chamado CampaignReport.docx). Observe que o download contém detalhes durante todo o tempo de vida da campanha (não apenas as datas de filtro que você selecionou).

![Informações da campanha](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a>Fluxo de campanha

No meio da exibição de detalhes da campanha, detalhes importantes sobre a campanha são apresentados na seção **Fluxo** em um diagrama de fluxo horizontal (conhecido como diagrama _Sankey)._ Esses detalhes ajudarão você a entender os elementos da campanha e o impacto potencial na sua organização.

> [!TIP]
> As informações exibidas no diagrama **Flow** são controladas pelo intervalo de datas sombreado na linha do tempo, conforme descrito na seção anterior.

![Detalhes da campanha que não contêm cliques de usuários na URL](../../media/campaign-details-no-recipient-actions.png)

Se passar o mouse sobre uma faixa horizontal no diagrama, você verá o número de mensagens relacionadas (por exemplo, mensagens de um determinado IP de origem, mensagens do IP de origem usando o domínio do remetente especificado, etc.).

O diagrama contém as seguintes informações:

- **IPs do remetente**
- **Domínios do remetente**
- **Vereditos de filtro:** Os valores de veredito estão relacionados aos vereditos disponíveis de filtragem de phishing e spam, conforme descrito nos headers de mensagens [anti-spam.](anti-spam-message-headers.md) Os valores disponíveis são descritos na tabela a seguir:

  ****

  |Valor|Veredito do filtro de spam|Descrição|
  |---|---|---|
  |**Permitido**|`SFV:SKN` <p> `SFV:SKI`|A mensagem foi marcada como não spam e/ou ignorada pela filtragem antes de ser avaliada pela filtragem de spam. Por exemplo, a mensagem foi marcada como não spam por uma regra de fluxo de emails (também conhecida como regra de transporte). <p> A mensagem ignorou a filtragem de spam por outros motivos. Por exemplo, o remetente e o destinatário parecem estar na mesma organização.|
  |**Bloqueado**|`SFV:SKS`|A mensagem foi marcada como spam antes de ser avaliada pela filtragem de spam. Por exemplo, por uma regra de fluxo de emails.|
  |**Detectado**|`SFV:SPM`|A mensagem foi marcada como spam pela filtragem de spam.|
  |**Não detectado**|`SFV:NSPM`|A mensagem foi marcada como não sendo spam pela filtragem de spam.|
  |**Lançado**|`SFV:SKQ`|A mensagem ignorou a filtragem de spam porque foi liberada da quarentena.|
  |**Permitir Locatário**<sup>\*</sup>|`SFV:SKA`|A mensagem ignorou a filtragem de spam devido às configurações em uma política anti-spam. Por exemplo, o remetente estava na lista de remetentes permitidos ou na lista de domínios permitidos.|
  |**Bloqueio de Locatário**<sup>\*\*</sup>|`SFV:SKA`|A mensagem foi bloqueada pela filtragem de spam devido às configurações em uma política anti-spam. Por exemplo, o remetente estava na lista de remetentes permitidos ou na lista de domínios permitidos.|
  |**Permitir Usuário**<sup>\*</sup>|`SFV:SFE`|A mensagem ignorou a filtragem de spam porque o remetente estava na lista de Remetentes Seguros de um usuário.|
  |**Bloqueio de Usuário**<sup>\*\*</sup>|`SFV:BLK`|A mensagem foi bloqueada pela filtragem de spam porque o remetente estava na lista de Remetentes Bloqueados de um usuário.|
  |**ZAP**|n/d|[A ZAP (Limpeza Automática Zero Hora)](zero-hour-auto-purge.md) moveu a mensagem entregue para a pasta Lixo Eletrônico ou quarentena. Você configura a ação em sua política anti-spam.|
  |

  <sup>\*</sup> Revise suas políticas anti-spam, pois a mensagem permitida provavelmente seria bloqueada pelo serviço.

  <sup>\*\*</sup> Revise suas políticas anti-spam, pois essas mensagens devem ser colocadas em quarentena, não entregues.

- **Locais** de entrega: você provavelmente vai querer investigar mensagens que foram entregues aos destinatários (na caixa de entrada ou na pasta Lixo Eletrônico), mesmo que os usuários não clicaram na URL de carga na mensagem. Você também pode remover as mensagens em quarentena. Para obter mais informações, consulte [Mensagens de email em quarentena no EOP.](quarantine-email-messages.md)
  - **Pasta excluída**
  - **Dropped**
  - **Externo**: o destinatário está localizado em sua organização de email local em ambientes híbridos.
  - **Falhou**
  - **Encaminhado**
  - **Caixa de Entrada**
  - **Pasta Lixo Eletrônico**
  - **Quarentena**
  - **Unknown**

- **Cliques de URL:** esses valores são descritos na próxima seção.

> [!NOTE]
> Em todas as camadas que contêm mais de 10 itens, os 10 principais itens são mostrados, enquanto o restante é agrupado em **Outros**.

#### <a name="url-clicks"></a>Cliques na URL

Quando uma mensagem de phishing é entregue na pasta Caixa de Entrada ou Lixo Eletrônico de um destinatário, sempre há uma chance de o usuário clicar na URL do conteúdo. Não clicar na URL é uma pequena medida de sucesso, mas você precisa determinar por que a mensagem de phishing foi até mesmo entregue à caixa de correio.

Se um usuário clicou na URL de carga na mensagem de phishing, as ações serão exibidas na área de **cliques** de URL do diagrama na exibição de detalhes da campanha.

- **Permitido**
- **BlockPage**: o destinatário clicou na URL do conteúdo, mas o acesso ao site mal-intencionado foi bloqueado por uma política de [Links](atp-safe-links.md) seguros em sua organização.
- **BlockPageOverride**: o destinatário clicou na URL da carga na mensagem, Os Links Seguros tentaram interdulá-los, mas eles tiveram permissão para substituir o bloco. Inspecione [suas políticas de Links](set-up-atp-safe-links-policies.md) seguros para ver por que os usuários têm permissão para substituir o veredito de Links seguros e continuar para o site mal-intencionado.
- **PendingDetonationPage**: Anexos seguros no Microsoft Defender para Office 365 está em processo de abertura e investigação da URL de carga em um ambiente de computador virtual.
- **PendingDetonationPageOverride**: O destinatário teve permissão para substituir o processo de ativação de carga e abrir a URL sem esperar pelos resultados.

### <a name="tabs"></a>Guias

As guias na exibição de detalhes da campanha permitem que você investigue ainda mais a campanha.

> [!TIP]
> As informações exibidas nas guias são controladas pelo intervalo de datas sombreado na linha do tempo, conforme descrito na [seção Informações da](#campaign-information) campanha.

- **Cliques de** URL: se os usuários não clicaram na URL de carga na mensagem, esta seção ficará em branco. Se um usuário conseguir clicar na URL, os seguintes valores serão preenchidos:
  - **Usuário**<sup>\*</sup>
  - **URL**<sup>\*</sup>
  - **Hora do clique**
  - **Click verdict**

- **IPs do remetente**
  - **IP do remetente**<sup>\*</sup>
  - **Contagem total**
  - **Caixa de Entrada**
  - **Não Na Caixa de Entrada**
  - **SPF aprovado:** O remetente foi autenticado pela [Sender Policy Framework (SPF).](how-office-365-uses-spf-to-prevent-spoofing.md) Um remetente que não passa na validação SPF indica um remetente não autenticado ou se a mensagem está falsando um remetente legítimo.

- **Remetentes**
  - **Remetente**: este é o endereço do remetente real no comando SMTP MAIL FROM, que não é necessariamente o endereço de email De: que os usuários veem em seus clientes de email.
  - **Contagem total**
  - **Caixa de Entrada**
  - **Não Na Caixa de Entrada**
  - **DKIM passado:** o remetente foi autenticado pelo [Domain Keys Identified Mail (DKIM).](support-for-validation-of-dkim-signed-messages.md) Um remetente que não passa na validação do DKIM indica um remetente não autenticado ou se a mensagem está falsando um remetente legítimo.
  - **DMARC aprovado:** O remetente foi autenticado pela Autenticação de Mensagens, Relatórios e [Conformidade (DMARC)](use-dmarc-to-validate-email.md)baseada em domínio. Um remetente que não passa na validação do DMARC indica um remetente não autenticado ou se a mensagem está falsando um remetente legítimo.

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
- **Explorar mensagens na Caixa de** Entrada: abre uma nova guia de pesquisa do Explorador de Ameaças usando a **ID** da campanha e o local de **entrega:** Caixa de Entrada como filtro de pesquisa.
