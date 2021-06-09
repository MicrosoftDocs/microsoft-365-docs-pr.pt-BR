---
title: Saiba mais sobre a prevenção contra perda de dados do ponto de extremidade
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Saiba como proteger suas informações confidenciais usando Microsoft 365 e ferramentas de prevenção contra perda de dados e fazer um tour pelo ciclo de vida da DLP.
ms.openlocfilehash: 88cf913f62d28c89bce7054473eb577217de9489
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244607"
---
# <a name="learn-about-data-loss-prevention"></a>Saiba mais sobre a prevenção contra perda de dados do ponto de extremidade

As organizações têm informações confidenciais sob seu controle, como dados financeiros, dados proprietários, números de cartão de crédito, registros de saúde ou números de segurança social. Para ajudar a proteger esses dados confidenciais e reduzir o risco, eles precisam de uma maneira de impedir que seus usuários os compartilhem inadequadamente com pessoas que não devem ter. Essa prática é chamada de prevenção contra perda de dados (DLP).

Em Microsoft 365, você implementa a prevenção contra perda de dados definindo e aplicando políticas de DLP. Com uma política de DLP, você pode identificar, monitorar e proteger automaticamente itens confidenciais em:

- Microsoft 365 serviços como Teams, Exchange, SharePoint e OneDrive
- Office aplicativos como Word, Excel e PowerPoint
- Windows 10 pontos de extremidade
- aplicativos de nuvem que não são da Microsoft
- Compartilhamentos de arquivos locais e SharePoint.

Microsoft 365 detecta itens confidenciais usando análise de conteúdo profundo, não apenas por uma verificação de texto simples. O conteúdo é analisado para dados primários corresponde a palavras-chave, pela avaliação de expressões regulares, pela validação de função interna e por matchs de dados secundários que estão próximos da combinação de dados primários. Além disso, a DLP também usa algoritmos de aprendizado de máquina e outros métodos para detectar conteúdo que corresponde às suas políticas de DLP.
  
## <a name="dlp-is-part-of-the-larger-microsoft-365-compliance-offering"></a>A DLP faz parte da oferta de conformidade Microsoft 365 maior

Microsoft 365 A DLP é apenas uma das Microsoft 365 de Conformidade que você usará para ajudar a proteger seus itens confidenciais onde quer que eles vivam ou viajem. Você deve entender as outras ferramentas no Microsoft 365 de Conformidade definidas, como elas se relacionam e funcionam melhor juntas.  Consulte, [Microsoft 365 ferramentas de conformidade](protect-information.md) para saber mais sobre o processo de proteção de informações.

## <a name="protective-actions-of-dlp-policies"></a>Ações de proteção de políticas DLP

Microsoft 365 As políticas de DLP são como você monitora as atividades que os usuários fazem em itens confidenciais em repouso, itens confidenciais em trânsito ou itens confidenciais em uso e fazem ações de proteção. Por exemplo, quando um usuário tenta tomar uma ação proibida, como copiar um item sensível para um local não aprovado ou compartilhar informações médicas em um email ou outras condições estabelecidas em uma política, a DLP pode:

- mostrar uma dica de política pop-up para o usuário que o avisa que ele pode estar tentando compartilhar um item sensível de forma inadequada
- bloquear o compartilhamento e, por meio de uma dica de política, permitir que o usuário substitua o bloco e capture a justificativa dos usuários
- bloquear o compartilhamento sem a opção de substituição
- para dados em repouso, itens confidenciais podem ser bloqueados e movidos para um local de quarentena seguro
- para Teams chat, as informações confidenciais não serão exibidas

Todas as atividades monitoradas de DLP são gravadas no [log Microsoft 365 Auditoria](search-the-audit-log-in-security-and-compliance.md) por padrão e roteadas para o Explorador de [Atividades.](data-classification-activity-explorer.md) Quando um usuário executa uma ação que atende aos critérios de uma política DLP e você tem alertas configurados, a DLP fornece alertas no painel de gerenciamento de alertas [DLP.](dlp-configure-view-alerts-policies.md)

## <a name="dlp-lifecycle"></a>Ciclo de vida de DLP

Uma implementação DLP normalmente segue essas fases principais.

- [Plano de Prevenção Contra Perda de Dados](#plan-for-dlp)
- [Preparar para DLP](#prepare-for-dlp)
- [Implantar suas políticas na produção](#deploy-your-policies-in-production)


<!--ADD DIAGRAM OF THE DLP LIFECYCLE WORK ON WITH MAS-->

### <a name="plan-for-dlp"></a>Plano de Prevenção Contra Perda de Dados

Microsoft 365 O monitoramento e a proteção DLP são nativos dos aplicativos que os usuários usam todos os dias. Isso ajuda a proteger os itens confidenciais de suas organizações contra atividades arriscadas, mesmo que seus usuários não sejam acostumados a pensar e práticas de prevenção contra perda de dados. Se sua organização e seus usuários são novos em práticas de prevenção contra perda de dados, a adoção de DLP pode exigir uma alteração nos processos de negócios e haverá uma mudança de cultura para seus usuários. Porém, com planejamento, teste e ajuste adequados, suas políticas de DLP protegerão seus itens confidenciais enquanto minimizam possíveis interrupções do processo de negócios.

**Planejamento de tecnologia para DLP**

Lembre-se de que a DLP como tecnologia pode monitorar e proteger seus dados em repouso, dados em uso e dados em movimento nos serviços Microsoft 365, dispositivos Windows 10, compartilhamentos de arquivos locais e SharePoint. Há implicações de planejamento para os diferentes locais, o tipo de dados que você deseja monitorar e proteger e as ações a serem tomadas quando ocorrer uma combinação de política.  

**Planejamento de processos de negócios para DLP**

As políticas de DLP podem bloquear atividades proibidas, como o compartilhamento inadequado de informações confidenciais por email. Ao planejar suas políticas de DLP, você deve identificar os processos de negócios que tocam seus itens confidenciais. Os proprietários do processo de negócios podem ajudá-lo a identificar comportamentos de usuário apropriados que devem ser permitidos e comportamentos de usuário inadequados que devem ser protegidos. Você deve planejar suas políticas e implantá-las [](data-classification-activity-explorer.md) no modo de teste e avaliar seu impacto por meio do explorador de atividades primeiro, antes de aplicá-las em modos mais restritivos.

**Planejamento de cultura organizacional para DLP**

Uma implementação de DLP bem-sucedida depende tanto da capacitação dos usuários quanto das práticas de prevenção contra perda de dados, como em políticas bem planejadas e ajustadas. Como seus usuários estão fortemente envolvidos, não se esqueça de planejar o treinamento para eles também. Você pode usar dicas de política estrategicamente para conscientizar os usuários antes de alterar a imposição de política do modo de teste para modos mais restritivos.

<!--For more information on planning for DLP, including suggestions for deployment based on your needs and resources, see [Planning for Microsoft 365 data loss prevention](dlp-plan-for-dlp.md).-->

### <a name="prepare-for-dlp"></a>Preparar para DLP

Você pode aplicar políticas de DLP a dados em repouso, dados em uso e dados em movimento em locais, como:

- Exchange Online email
- Sites do SharePoint Online
- Contas OneDrive
- Bater papo e canal de mensagens do Teams
- Microsoft Cloud App Security
- Dispositivos Windows 10
- Repositórios locais

Cada um deles tem pré-requisitos diferentes. Itens confidenciais em alguns locais, como Exchange online, podem ser trazidos para o guarda-chuva DLP apenas configurando uma política que se aplica a eles. Outros, como repositórios de arquivos locais, exigem uma implantação do scanner AIP (Proteção de Informações do Azure). Você precisará preparar seu ambiente, codificar políticas de rascunho e testá-las completamente antes de ativar qualquer ação de bloqueio.

### <a name="deploy-your-policies-in-production"></a>Implantar suas políticas na produção

#### <a name="design-your-policies"></a>Projetar suas políticas

Comece definindo seus objetivos de controle e como eles se aplicam em cada carga de trabalho respectiva. Esboça uma política que incorpora seus objetivos. Sinta-se à vontade para começar com uma carga de trabalho por vez ou em todas as cargas de trabalho - ainda não há impacto.

#### <a name="implement-policy-in-test-mode"></a>Implementar política no modo de teste

Avalie o impacto dos controles implementando-os com uma política DLP no modo de teste. Não há problema em aplicar a política a todas as cargas de trabalho no modo de teste, para que você possa obter a amplitude completa dos resultados, mas você pode começar com uma carga de trabalho se precisar.

#### <a name="monitor-outcomes-and-fine-tune-the-policy"></a>Monitorar resultados e ajustar a política

Enquanto estiver no modo de teste, monitore os resultados da política e ajuste-a de forma que ela atenda aos seus objetivos de controle, garantindo que você não está afetando adversamente ou inadvertidamente fluxos de trabalho e produtividade válidos do usuário. Aqui estão alguns exemplos de coisas para ajustar:

- ajustando os locais e as pessoas/locais que estão dentro ou fora do escopo
- ajustar as condições e exceções que são usadas para determinar se um item e o que está sendo feito com ele corresponde à política
- as definições/s de informações confidenciais
- as ações
- o nível de restrições
- adicionar novos controles
- adicionar novas pessoas
- adicionar novos aplicativos restritos
- adicionar novos sites restritos

#### <a name="enable-the-control-and-tune-your-policies"></a>Habilitar o controle e ajustar suas políticas

Depois que a política atender a todos os seus objetivos, a a ligue. Continue a monitorar os resultados do aplicativo de política e ajuste conforme necessário. Em geral, as políticas entrarão em vigor cerca de uma hora depois de serem ativas. <!--See, tópico LINK TO para SLAs para detalhes específicos do local, >

## <a name="dlp-policy-configuration-overview"></a>Visão geral da configuração da política de DLP

Você tem flexibilidade na forma como cria e configura suas políticas de DLP. Você pode começar a partir de um modelo predefinido e criar uma política em apenas alguns cliques ou pode projetar sua própria do zero. Não importa qual você escolher, todas as políticas de DLP exigem as mesmas informações de você.

1. **Escolha o que você deseja monitorar** - Microsoft 365 vem com muitos modelos de política predefinidos para ajudá-lo a começar ou você pode criar uma política personalizada.
    - Um modelo de política predefinido: dados financeiros, dados médicos e de saúde, dados de privacidade para vários países e regiões.
    - Uma política personalizada que usa os tipos de informações confidenciais disponíveis, rótulos de retenção e rótulos de sensibilidade.
2. **Escolha onde você deseja monitorar** - Escolha um ou mais locais que deseja que a DLP monitore para obter informações confidenciais. Você pode monitorar:
    
localização | incluir/excluir por|
|---------|---------|
|Email do Exchange| grupos de distribuição|
|Sites do Microsoft Office SharePoint Online |sites |
|Contas do OneDrive |contas ou grupos de distribuição |
|Bater papo e canal de mensagens do Teams |contas |
|Dispositivos Windows 10 |usuário ou grupo |
|Microsoft Cloud App Security |instância |
|Repositórios locais| caminho do arquivo de repositório|

3. **Escolha as condições que devem ser** corresponder a uma política a ser aplicada a um item - você pode aceitar condições pré-configuradas ou definir condições personalizadas. Alguns exemplos:

- contém um tipo especificado de informações confidenciais que estão sendo usadas em um determinado contexto. Por exemplo, 95 números de segurança social sendo enviado por email para destinatários fora da sua organização.
- item tem um rótulo de sensibilidade especificado
- item com informações confidenciais é compartilhado internamente ou externamente

4. **Escolha a ação a ser tomada quando as** condições de política são atendidas - As ações dependem do local onde a atividade está acontecendo.  Alguns exemplos:

- SharePoint/Exchange/OneDrive: Bloquear pessoas que estão fora do formulário da organização acessando o conteúdo. Mostre uma dica ao usuário e envie uma notificação por email de que ele está tomando uma ação que é proibida pela política DLP.
- Teams Chat e Canal: Impedir que informações confidenciais são compartilhadas no chat ou no canal
- Windows 10 Dispositivos: auditar ou restringir a cópia de um item sensível a um dispositivo USB removêvel 
- Office Aplicativos: mostrar um pop-up notificando o usuário de que ele está envolvido em um comportamento arriscado e bloquear ou bloquear, mas permitir substituição.
- Compartilhamentos de arquivos locais: mova o arquivo de onde ele está armazenado para uma pasta de quarentena

> [!NOTE]
> As condições e as ações a tomar são definidas em um objeto chamado Rule.

<!--## Create a DLP policy

All DLP policies are created and maintained in the Microsoft 365 Compliance center. See, INSERT LINK TO ARTICLE THAT WILL START WALKING THEM THROUGH THE POLICY CREATION PROCEDURES for more information.-->

Depois de criar uma política de DLP no Centro de Conformidade, ela será armazenada em um armazenamento de política central e sincronizada com as várias fontes de conteúdo, incluindo:
  
- Exchange Online, e de lá para o Outlook na Web e o Outlook.
- Sites do OneDrive for Business.
- Sites do SharePoint Online.
- Programas da área de trabalho do Office (Excel, PowerPoint e Word)
- Mensagens de canais e de chats do Microsoft Teams.
    
Após a sincronização da política com os locais corretos, ela começa avaliar o conteúdo e aplicar as ações.

## <a name="viewing-policy-application-results"></a>Exibindo os resultados do aplicativo de política

A DLP relata uma grande quantidade de informações em Microsoft 365 de monitoramento, de diretivas e ações e atividades do usuário. Você precisará consumir e agir sobre essas informações para ajustar suas políticas e ações de triagem realizadas em itens confidenciais. A telemetria entra primeiro [nos](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log-in-the-compliance-center) Logs de Auditoria Microsoft 365 Centro de Conformidade, é processada e segue para diferentes ferramentas de relatório. Cada ferramenta de relatório tem uma finalidade diferente.  

### <a name="dlp-alerts-dashboard"></a>Painel de Alertas DLP

Quando a DLP faz uma ação em um item sensível, você pode ser notificado dessa ação por meio de um alerta configurável. Em vez de ter esses alertas empilhados em uma caixa de correio para você passar, o Centro de Conformidade os disponibiliza no Painel de Gerenciamento de [Alertas de DLP.](dlp-configure-view-alerts-policies.md) Use o painel Alertas de DLP para configurar alertas, revisá-los, triá-los e controlar a resolução de Alertas DLP. Veja um exemplo de alertas gerados por diretivas e atividades de Windows 10 dispositivos.

> [!div class="mx-imgBorder"]
> ![Informações sobre alertas](../media/Alert-info-1.png)

Você também pode exibir os detalhes do evento associado com metadados ricos no mesmo painel

> [!div class="mx-imgBorder"]
> ![informações do evento](../media/Event-info-1.png)

### <a name="reports"></a>Relatórios

Os [relatórios de DLP](view-the-dlp-reports.md#view-the-reports-for-data-loss-prevention) mostram tendências amplas ao longo do tempo e dão informações específicas sobre:

- **Política de DLP Corresponde** ao longo do tempo e filtrar por intervalo de datas, local, política ou ação
- **As combinações de incidente de DLP** também mostram as corresponde ao longo do tempo, mas gira nos itens em vez das regras de política.
- **As substituições** e falsos positivos de DLP mostram a contagem de falsos positivos e, se configuradas, substitui o usuário juntamente com a justificativa do usuário.

### <a name="dlp-activity-explorer"></a>Explorador de Atividades DLP

A guia Explorador de atividades na página DLP tem o filtro *Atividade* predefinido como *DLPRuleMatch*. Use esta ferramenta para revisar as atividades relacionadas ao conteúdo que contém informações confidenciais ou que tenha rótulos aplicados, como quais rótulos foram alterados, arquivos foram modificados e corresponderam a uma regra.

![captura de tela do explorador de atividades com escopo DLPRuleMatch ](../media/dlp-activity-explorer.png)

Para obter mais informações, consulte [Get started with activity explorer](data-classification-activity-explorer.md)

Para saber mais sobre Microsoft 365 DLP, consulte:

- [Saiba mais sobre a prevenção contra Perda de Dados de Ponto de Extremidade do Microsoft 365](endpoint-dlp-learn-about.md)
- [Saiba mais sobre a política de prevenção de perda de dados padrão no Microsoft Teams (visualização)](dlp-teams-default-policy.md)
- [Saiba mais sobre a verificação local de prevenção contra perda de dados do Microsoft 365 (visualização)](dlp-on-premises-scanner-learn.md)
- [Saiba mais sobre a extensão de conformidade da Microsoft (visualização)](dlp-chrome-learn-about.md)
- [Saiba mais sobre o painel de alertas de prevenção contra perda de dados](dlp-alerts-dashboard-learn.md)

Para saber como usar a prevenção contra perda de dados para estar em conformidade com os regulamentos de privacidade de dados, consulte [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).