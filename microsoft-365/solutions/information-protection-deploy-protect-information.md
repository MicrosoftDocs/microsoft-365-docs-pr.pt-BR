---
title: Proteger informações sujeitas à regulamentação de privacidade de dados
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Implante os recursos de segurança e conformidade do Microsoft 365 e proteja suas informações pessoais.
ms.openlocfilehash: f17568c5a19446644cfb7ee64aac3e0f9eae5793
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988477"
---
# <a name="protect-information-subject-to-data-privacy-regulation"></a>Proteger informações sujeitas à regulamentação de privacidade de dados

Vários controles de proteção de informações podem ser empregados em sua assinatura para ajudar a atender às necessidades e regulamentos de conformidade de privacidade de dados. Elas incluem o RGPD (Regulamento Geral sobre a Proteção de Dados), HIPAA-HITECH (lei de privacidade da saúde dos Estados Unidos), a Lei de Proteção do Consumidor da Califórnia (CCPA) e a LGPD (Lei de Proteção de Dados do Brasil).

Esses controles estão nas seguintes áreas de solução:

- Rótulos de confidencialidade
- Prevenção de perda de dados (DLP)
- Criptografia de Mensagem do Office (OME)
- Controles de acesso a equipes e sites

![Principais serviços para proteger informações pessoais sujeitas à regulamentação de privacidade de dados](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-grid.png)

>[!Note]
>Esta solução descreve os recursos de segurança e conformidade para proteger as informações sujeitas às regulamentações de privacidade de dados. Para ver uma lista completa dos recursos de segurança no Microsoft 365, confira a documentação de [segurança do Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/) Para ver uma lista completa dos recursos de conformidade no Microsoft 365, confira a [documentação de conformidade do Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/)
>

## <a name="data-privacy-regulations-that-impact-information-protection-controls"></a>Regulamentos de privacidade de dados que impactam os controles de proteção de informações

Aqui está uma lista de exemplos de regulamentações de privacidade de dados que podem estar relacionadas a controles de proteção de informações:

- Artigo RGPD 5(1)(f))
- Artigo RGPD (32)(1)(a)
- Artigo 46 do LGPD
- HIPAA-HITECH (45 CFR 164.312(e)(1))
- HIPAA-HITECH (45 C.F.R. 164.312(e)(2)(ii))

Consulte o [artigo avaliar os riscos de privacidade de dados](information-protection-deploy-assess.md) e identificar itens confidenciais para obter mais informações sobre cada um dos itens acima.

As regulamentações de privacidade de dados para proteção de informações recomendam:

- Proteção contra perda ou acesso, uso e/ou transmissão não autorizados.
- Aplicação baseada em risco de mecanismos de proteção.
- Uso de criptografia quando apropriado.

Sua organização também pode querer proteger o conteúdo do Microsoft 365 para outros fins, como outras necessidades de conformidade ou por motivos comerciais. O estabelecimento de seu esquema de proteção de informações para privacidade de dados deve ser feito como parte do planejamento, implementação e gerenciamento da proteção geral de informações.

Para ajudá-lo a começar a trabalhar com um esquema de proteção de informações no Microsoft 365, a seção a seguir inclui uma pequena lista de recursos relacionados e ações de melhoria do Microsoft 365. A lista inclui recursos e ações de aperfeiçoamento aplicáveis às regulamentações de privacidade de dados. No entanto, a lista não inclui tecnologias mais antigas se houver um recurso mais novo que superseda amplamente o mais antigo. Por exemplo, o Gerenciamento de Direitos de Informação (IRM) para SharePoint e OneDrive não está incluído na lista, mas os rótulos de sensibilidade estão incluídos.

## <a name="managing-information-protection-in-microsoft-365"></a>Gerenciando a proteção de informações no Microsoft 365

As [soluções de proteção](../compliance/information-protection.md) de informações da Microsoft incluem vários recursos integrados no Microsoft 365, Microsoft Azure e Microsoft Windows. No Microsoft 365, as soluções de proteção de informações incluem:

- [Criptografia do serviço com a Chave de Cliente](../compliance/customer-key-overview.md)
- [Tipos de informações confidenciais](../compliance/what-the-sensitive-information-types-look-for.md) (descrito no artigo avaliar os riscos de privacidade de dados e [identificar itens confidenciais)](information-protection-deploy-assess.md)
- [Rótulos de confidencialidade](../compliance/sensitivity-labels.md) 
  - Nível de serviço/contêiner
  - Nível de conteúdo/do lado do cliente
  - Automatizado para dados em repouso no SharePoint e no OneDrive
- Prevenção de Perda de Dados (DLP)
- [Prevenção contra perda de dados do ponto de extremidade do Microsoft 365 (visualização)](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide)
- Novos recursos de Criptografia de Mensagem [do Office 365 (OME)](../compliance/ome.md) e Criptografia de [Mensagem Avançada](../compliance/ome-advanced-message-encryption.md) OME

Além disso, a proteção no nível do site e da biblioteca são mecanismos importantes para incluir em qualquer esquema de proteção.

Para saber mais sobre outros recursos de proteção de informações fora do Microsoft 365, confira:

- [Microsoft Cloud Application Security (MCAS)](https://docs.microsoft.com/cloud-app-security/)
- [Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)
- [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)
- [Proteção de Informações do Windows](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)

## <a name="sensitivity-labels"></a>Rótulos de confidencialidade

Os rótulos de sensibilidade da estrutura de Proteção de Informações da Microsoft permitem classificar e proteger os dados da sua organização sem prejudicar a produtividade dos usuários e sua capacidade de colaboração.

![Rótulos de sensibilidade no Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-labels.png)

### <a name="prerequisites-for-sensitivity-labels"></a>Pré-requisitos para rótulos de sensibilidade

Conclua essas atividades antes de implementar qualquer um dos recursos baseados em rótulos de sensibilidade destacados abaixo:

1. Entenda o seguinte:
   - **Requisitos de negócios.** Estabeleça os motivos comerciais para a aplicação de rótulos de sensibilidade em sua empresa. Por exemplo, seus requisitos de privacidade de dados para proteção de informações.
   - **Recursos de rótulo de sensibilidade.** A rotulagem de sensibilidade pode ficar complexa, portanto, leia a [documentação](../compliance/sensitivity-labels.md) dos rótulos de sensibilidade antes de começar.
   - **Principais coisas a lembrar** Os rótulos de sensibilidade são gerenciados no centro de administração de Conformidade da Microsoft, mas as opções de direcionamento e aplicativo variam significativamente.
      - Há rótulos de sensibilidade para sites, grupos e Equipes no nível do contêiner (as configurações não se aplicam ao conteúdo dentro do contêiner). Eles são publicados para usuários e grupos que os aplicam quando um site, grupo ou Equipe é provisionado.
      - Há rótulos de sensibilidade para conteúdo ativo. Eles também são publicados para usuários ou grupos, que os aplicam manualmente ou são aplicados automaticamente quando:
        - O arquivo é aberto/editado/salvo, na área de trabalho do usuário ou em um site do SharePoint.
        - Um email é rascunho e enviado.
      - Há rótulos de sensibilidade para aplicativo automático para arquivos em repouso no SharePoint e no OneDrive, além de emails em trânsito pelo Exchange. Eles são direcionados a todos os sites ou a sites específicos e se aplicam automaticamente aos arquivos em repouso nesses ambientes.

2. Racionalizar a rotulagem de sensibilidade atual com métodos anteriores ou alternativos

   - Proteção de Informações do Azure

      O esquema de rotulagem de sensibilidade atual pode precisar ser reconciliado com qualquer implementação de rotulagem existente da Proteção de Informações do [Azure.](../compliance/sensitivity-labels.md#sensitivity-labels-and-azure-information-protection)
   - OME

      Se você planeja usar a rotulagem de sensibilidade moderna para proteção de email e métodos de criptografia de email existentes, como o OME, eles podem existir, mas você deve entender os cenários em que ambos devem ser aplicados. Confira os novos recursos da Criptografia de Mensagens [do Office 365 (OME),](#office-365-message-encryption-ome-new-capabilities)que inclui uma tabela comparando a proteção moderna do tipo rótulo de sensibilidade com a proteção baseada em OME.

3. Planeje a integração em um esquema de proteção de informações mais amplo. Além da coexistência com o OME, os rótulos de sensibilidade atuais podem ser usados lado a lado, como a prevenção contra perda de dados (DLP) do Microsoft 365 e o Microsoft Cloud App Security. Consulte [Rótulos de Sensibilidade e o Microsoft Cloud App Security](../compliance/sensitivity-labels.md#sensitivity-labels-and-microsoft-cloud-app-security) para atingir suas metas de proteção de informações relacionadas à privacidade de dados.

4. Desenvolva um esquema de controle e classificação de rótulos de sensibilidade. Consulte [Taxonomia de Rótulo de Sensibilidade e](https://aka.ms/dataclassificationwhitepaper)Classificação de Dados.

### <a name="general-guidance"></a>Diretrizes gerais

1. **Definição de esquema.** Antes de usar recursos técnicos para aplicar rótulos e proteção, trabalhe em toda a organização para definir um esquema de classificação. Talvez você já tenha um esquema de classificação, o que facilita adicionar dados pessoais. 
2. **Getting started.** Comece decidindo o número e os nomes dos rótulos a implementar. Faça essa atividade sem se preocupar com qual tecnologia usar e como os rótulos serão aplicados. Aplique esse esquema universalmente em toda a organização, incluindo dados que residem no local e em outros serviços de nuvem.
3. **Recomendações adicionais** Ao projetar e implementar políticas, rótulos e condições, considere estas recomendações:

   - **Use o esquema de classificação existente (se existir).** Muitas organizações já estão usando a classificação de dados de alguma forma. Avalie cuidadosamente o esquema de rótulo existente e, se possível, use-o como está. Usar rótulos familiares reconhecíveis para seus usuários finais impulsiona a adoção.
   - **Comece pequeno.** Praticamente não há limite para o número de rótulos que você pode criar. No entanto, um grande número de rótulos e sub-rótulos pode retardar a adoção.
   - **Use cenários e casos de uso.** Identifique casos de uso comuns em sua organização e use cenários derivados das regulamentações de privacidade de dados aos quais você está sujeito. Verifique se a configuração prevista de rótulo e classificação funcionará na prática.
   - **Questione cada solicitação de um novo rótulo.** Cada cenário ou caso de uso realmente precisa de um novo rótulo ou você pode usar o que já tem? Manter o número mínimo de rótulos melhora a adoção.
   - **Use sub-rótulos para os principais departamentos.** Alguns departamentos terão necessidades específicas que exigem rótulos específicos. Defina esses rótulos como sub-rótulos para um rótulo existente e considere usar políticas com escopo atribuídas a grupos de usuários em vez de globalmente.
   - **Considere políticas com escopo.** As políticas direcionadas a subconjuntos de usuários impedirão a sobrecarga de rótulos. Uma política com escopo permite atribuir rótulos ou sub-rótulos específicos de função ou departamento a apenas funcionários que trabalham para esse departamento específico. 
   - **Use nomes de rótulo significativos.** Tente não usar jargão, padrões ou acrônimos como nomes de rótulos. Tente usar nomes que resonatem com o usuário final para melhorar a adoção. Em vez de usar rótulos como PII, PCI, HIPAA, LBI, MBI e HBI, considere nomes como Não Comercial, Público, Geral, Confidencial e Altamente Confidencial.

### <a name="create-and-deploy-sensitivity-labels-for-sites-groups-and-teams"></a>Criar e implantar rótulos de sensibilidade para sites, grupos e equipes

Ao criar [rótulos de sensibilidade](../compliance/sensitivity-labels-teams-groups-sites.md) no centro de conformidade do Microsoft 365, você pode aplicá-los a estes contêineres:

- Sites do Microsoft Teams
- Grupos do Microsoft 365 (anteriormente grupos do Office 365)
- Sites do Microsoft Office SharePoint Online

Use as configurações de rótulo a seguir para ajudar a proteger o conteúdo desses contêineres:

- Privacidade (pública ou privada) dos sites do Teams conectados ao grupo do Microsoft 365
- Acesso de usuários externos
- Acesso de dispositivos não gerenciados

Para privacidade de dados, para evitar o compartilhamento externo de contêineres que serão usados para armazenar conteúdo com dados pessoais confidenciais, marque os arquivos que contêm os dados como privados e exigem dispositivos gerenciados.

### <a name="create-and-deploy-sensitivity-labels-for-content"></a>Criar e implantar rótulos de sensibilidade para conteúdo

Os rótulos de sensibilidade aplicados aos arquivos permitem criptografar o conteúdo, marcar d'água o conteúdo e definir outros controles para o conteúdo de aplicativos do Office, incluindo o Outlook e o Office na Web.

Quando você estiver pronto para começar a proteger os dados da sua organização com rótulos de sensibilidade:

1. **Crie os rótulos.** Crie e nomeie seus rótulos de confidencialidade de acordo com a taxonomia de classificação da sua organização para diferentes níveis de confidencialidade de conteúdo. Para obter mais informações sobre como desenvolver uma taxonomia de classificação, consulte o white paper de [Taxonomia](https://aka.ms/dataclassificationwhitepaper)de Rótulo de Sensibilidade e Classificação de Dados.
2. **Defina o que cada rótulo pode fazer.** Defina as configurações de proteção desejadas associadas a cada rótulo. Por exemplo, você pode querer que o conteúdo de menor confidencialidade (como um rótulo "Geral" ) tenha apenas um título ou rodapé aplicado, enquanto conteúdo de maior confidencialidade (como um rótulo "Confidencial" ) deve ter uma marca d'água e ter criptografia habilitada.
3. **Publique os rótulos.** Quando os rótulos de confidencialidade estiverem configurados, publique-os usando uma política de rótulo. Decida quais usuários e grupos devem ter os rótulos e quais configurações de política utilizar. Um único rótulo é reutilizável. Você o define uma vez e, em seguida, pode incluí-lo em várias políticas de rótulo atribuídas a usuários diferentes.

Depois que você publica rótulos de sensibilidade do centro de conformidade do Microsoft 365, eles começam a aparecer nos aplicativos do [Office](../compliance/sensitivity-labels-office-apps.md) para que os usuários classifiquem e protejam o conteúdo à medida que ele é criado ou editado.

![Fluxo de implantação de rótulos de sensibilidade no Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-label-flow.png)

Para privacidade de dados, você aplica manualmente um rótulo de sensibilidade com criptografia e outras regras a emails ou conteúdo que contenha informações pessoais confidenciais.

>[!Note]
>Os rótulos de sensibilidade com criptografia habilitada aplicada ao email têm algumas funcionalidades sobrepostas com o OME. Consulte [a comparação de cenários de email seguro com OME e rótulos de sensibilidade.](#secure-email-scenarios-comparison-with-ome-and-sensitivity-labels)

### <a name="client-side-auto-labeling-when-users-edit-documents-or-compose-emails"></a>Rotulagem automática do lado do cliente quando os usuários editam documentos ou redação de emails

Ao criar um rótulo de [](../compliance/apply-sensitivity-label-automatically.md) sensibilidade, você pode atribuir automaticamente esse rótulo ao conteúdo, incluindo emails, quando ele corresponde às condições especificadas.

A capacidade de aplicar rótulos de confidencialidade automaticamente ao conteúdo é importante porque:

- Você não precisa treinar seus usuários quando usar cada uma de suas classificações.
- Você não precisa depender dos usuários para classificar corretamente o conteúdo.
- Os usuários não precisam mais conhecer as suas políticas. Em vez disso, eles podem se concentrar no próprio trabalho.

A rotulagem automática dá suporte à recomendação de um rótulo aos usuários, bem como à aplicação automática de um rótulo. Mas em ambos os casos, o usuário decide se aceita ou rejeita o rótulo, para ajudar a garantir a rotulagem correta do conteúdo.

Essa rotulagem do lado do cliente possui um atraso mínimo para os documentos, pois o rótulo pode ser aplicado mesmo antes de o documento ser salvo. No entanto, nem todos os aplicativos cliente oferecem suporte à rotulagem automática. Esse recurso é suportado pelo cliente de rotulagem unificada da Proteção de Informações do Azure e algumas [versões de aplicativos do Office.](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)

Para obter instruções de [configuração, confira Como configurar a rotulagem automática para aplicativos do Office.](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)

Para privacidade de dados, você aplica automaticamente rótulos de sensibilidade ao conteúdo que contém informações pessoais confidenciais.

### <a name="service-side-auto-labeling-when-content-is-already-saved"></a>Rotulagem automática do lado do serviço quando o conteúdo já estiver salvo

Esse método é chamado de classificação automática com rótulos de confidencialidade. Você também pode ouvir isso chamado de rotulagem automática para dados em repouso (para documentos no SharePoint e no OneDrive) e dados em trânsito (para emails enviados ou recebidos pelo Exchange). Para o Exchange, ele não inclui emails em caixas de correio em repouso.
 
Como essa rotulagem é aplicada pelo serviço em si, e não pelo aplicativo do usuário, você não precisa se preocupar com quais aplicativos os usuários têm e qual versão. Como resultado, esse recurso está imediatamente disponível em toda a organização e apropriado para rotular em escala. As políticas de rotulagem automática não oferecem suporte à rotulagem recomendada porque o usuário não interage com o processo de rotulagem. Em vez disso, o administrador executa as políticas no modo de simulação para ajudar a garantir a rotulagem correta do conteúdo antes de aplicar o rótulo.

Para obter instruções de configuração, consulte Como configurar políticas de rotulagem automática para [o SharePoint, o OneDrive e o Exchange.](../compliance/apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)

Para privacidade de dados em sites de preocupação, push rótulos de sensibilidade para criptografia automática de conteúdo que contém informações pessoais confidenciais.

## <a name="data-loss-prevention"></a>Prevenção contra perda de dados 

Você pode usar a prevenção contra perda de dados [(DLP)](../compliance/data-loss-prevention-policies.md) no Microsoft 365 para detectar, avisar e bloquear o compartilhamento arriscado, inadvertido ou inadequado, como o compartilhamento de dados contendo informações pessoais, interna e externamente.

A DLP permite que você:

- Identificar e monitorar atividades de compartilhamento arriscadas.
- Instrua os usuários com orientação no contexto para tomar as decisões certas.
- Impor políticas de uso de dados no conteúdo sem inibir a produtividade.
- Integração com classificação e rotulagem para detectar e proteger dados quando eles são compartilhados.

### <a name="supported-workloads-for-dlp"></a>Cargas de trabalho suportadas para DLP

Com uma política de DLP no centro de conformidade do Microsoft 365, você pode identificar, monitorar e proteger automaticamente itens confidenciais em vários locais no Microsoft 365, como Exchange Online, SharePoint, OneDrive e Microsoft Teams.

Por exemplo, você pode identificar qualquer documento que contenha um número de cartão de crédito armazenado em qualquer site do OneDrive ou pode monitorar apenas os sites do OneDrive de pessoas específicas.

Você também pode monitorar e proteger itens confidenciais nas versões instaladas localmente do Excel, PowerPoint e Word, que incluem a capacidade de identificar itens confidenciais e aplicar políticas de DLP. A DLP fornece monitoramento contínuo quando as pessoas compartilham conteúdo desses aplicativos do Office.

![Cargas de trabalho suportadas para DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-supported-workloads.png)

Esta figura mostra um exemplo de DLP que protege dados pessoais.

![Exemplo de proteção de dados pessoais usando DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-use.png)

A DLP é usada para identificar um documento ou email que contém um registro de saúde e, em seguida, bloqueia automaticamente o acesso a esse documento ou impede que o email seja enviado. A DLP notifica o destinatário com uma dica de política e envia um alerta para o usuário final e o administrador.

### <a name="planning-for-dlp"></a>Planejamento para DLP

Planeje suas políticas de DLP para: 

- Seus requisitos de negócios.

- Uma avaliação baseada em risco da organização, conforme descrito no artigo avaliar os riscos de privacidade de dados e [identificar itens confidenciais.](information-protection-deploy-assess.md)

- Outros mecanismos de governança e proteção de informações no local ou no planejamento da privacidade de dados.

- Os tipos de informações confidenciais que você identificou para dados pessoais com base em sua avaliação funcionam conforme descrito no artigo avaliar os riscos de privacidade de dados e identificar itens [confidenciais.](information-protection-deploy-assess.md) As condições de política de DLP podem ser baseadas em tipos de informações confidenciais e rótulos de retenção.

- Os rótulos de retenção que você precisará para especificar condições DLP. Consulte as [informações de governança sujeitas à regulamentação de](information-protection-deploy-govern.md) privacidade de dados no artigo da sua organização para obter mais informações.

- Gerenciamento contínuo de políticas de DLP, que exige que alguém na organização opere e ajuste políticas para alterações em tipos de informações confidenciais, rótulos de retenção, regulamentos e políticas de conformidade.

Embora os rótulos de sensibilidade não possam ser usados em condições de política de DLP, determinados cenários de proteção para impedir o acesso podem ser alcançados apenas com rótulos de sensibilidade que podem ser aplicados automaticamente com base em tipos de informações confidenciais. Se a rotulagem de sensibilidade robusta estiver em vigor, considere se a DLP deve ser usada para aumentar a proteção porque:

  - A DLP pode impedir o compartilhamento de arquivos. Os rótulos de sensibilidade podem apenas impedir o acesso.

  - A DLP tem níveis de controle mais granulares em termos de regras, condições e ações.

  - As políticas de DLP podem ser aplicadas a mensagens de canal e chat do Teams. Os rótulos de sensibilidade só podem ser aplicados a documentos e emails.


### <a name="dlp-policies"></a>Políticas DLP

As políticas de DLP são configuradas no centro de administração de Conformidade da Microsoft e especificam o nível de proteção, o tipo de informação sensível que a política está procurando e as cargas de trabalho de destino. Seus componentes básicos consistem em identificar a proteção e os tipos de dados.

![Configuração de política de DLP no Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-config.png)

Aqui está um exemplo de política DLP para reconhecimento do RGPD.

![Exemplo de política DLP para reconhecimento de RGPD](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-policy.png)

Consulte [este artigo para](../compliance/create-test-tune-dlp-policy.md) obter mais informações sobre como criar e aplicar políticas DLP.

### <a name="protection-levels-for-data-privacy"></a>Níveis de proteção para privacidade de dados

A tabela a seguir lista três configurações de aumento de proteção usando DLP.

![Níveis de proteção de privacidade de dados com DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-protection-levels.png)

A primeira configuração, Reconhecimento, pode ser usada como ponto de partida e nível mínimo de proteção para atender às necessidades de conformidade das regulamentações de privacidade de dados.

>[!Note]
>À medida que os níveis de proteção aumentam, a capacidade dos usuários de compartilhar e acessar informações diminuirá em alguns casos e poderá afetar sua produtividade ou capacidade de concluir tarefas diárias.
>

Para ajudar seus funcionários a continuarem a ser produtivos em um ambiente mais seguro ao aumentar os níveis de proteção, aproveite o tempo para treinar e instrui-los em novas políticas e procedimentos de segurança.

### <a name="example-of-using-sensitivity-labels-with-dlp"></a>Exemplo de uso de rótulos de sensibilidade com DLP

Os rótulos de sensibilidade podem trabalhar em conjunto com a DLP para fornecer privacidade de dados em um ambiente altamente regulamentado. Aqui estão as principais etapas da implantação integrada:

1. Os requisitos regulatórios e de outros negócios para privacidade de dados são documentados.
2. Fontes de dados de destino, tipos e propriedade são caracterizados em relação a preocupações de privacidade de dados.
3. Uma estratégia geral para atender aos requisitos e proteger e reger hotspots de privacidade de dados é estabelecida.
4. Um plano de ação em fases para abordar a estratégia de controle de privacidade de dados é colocado em vigor.

Depois que esses elementos são determinados, você pode usar tipos de informações confidenciais, sua taxonomia de rotulagem de sensibilidade e políticas DLP em conjunto. Esta figura mostra um exemplo.

![Exemplo de rótulos de sensibilidade trabalhando com DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

[Ver uma versão maior desta imagem](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

Aqui estão alguns cenários de proteção de dados usando DLP e rótulos de sensibilidade juntos, conforme mostrado na figura.

| Cenário | Processo |
|:-------|:-----|
| A | <ol><li>Os rótulos de sensibilidade para conteúdo são publicados por um administrador para usuários e grupos para aplicativos manuais ou automáticos para conteúdo e email. </li><li>O Usuário A aplica os rótulos manual ou automaticamente ao interagir com o conteúdo, com criptografia ou outras configurações aplicadas. </li><li>O Usuário A envia um email ou arquivo protegido para o Usuário B, um usuário convidado. </li></ol> |
| B | A política de DLP publicada por um administrador para o Usuário A impede que o Usuário A envie o email e/ou o arquivo para o Usuário B. |
| C |  O rótulo de sensibilidade com a configuração "o proprietário não pode convidar convidados" é publicado no Usuário A, que provisiona uma equipe do Teams ou um site do SharePoint. Outro usuário do site tenta seletivamente compartilhar um arquivo com o Usuário B, mas a DLP o bloqueia. |
| D | O rótulo de sensibilidade para aplicação automática ao conteúdo do site é publicado em um ou mais sites, fornecendo outra camada de proteção, resultando em um site protegido. |
|||

## <a name="office-365-message-encryption-ome-new-capabilities"></a>Novos recursos de Criptografia de Mensagens do Office 365 (OME)

As pessoas geralmente usam email para trocar itens confidenciais, como informações de saúde dos pacientes ou informações de clientes e funcionários. A criptografia de mensagem de email ajuda a garantir que apenas os destinatários pretendido possam exibir o conteúdo da mensagem.

Com [o OME,](../compliance/ome.md)você pode enviar e receber mensagens criptografadas entre pessoas dentro e fora da sua organização. O OME funciona com Outlook.com, Yahoo!, Gmail e outros serviços de email. O OME ajuda a garantir que apenas os destinatários pretendido possam exibir o conteúdo da mensagem.

Para privacidade de dados, você usa o OME para proteger mensagens internas que contêm itens confidenciais. A Criptografia de Mensagens do Office 365 é um serviço online criado com base no Microsoft Azure Rights Management (Azure RMS), que faz parte da Proteção de Informações do Azure. Isso inclui políticas de criptografia, identidade e autorização para ajudar a proteger seu email. Você pode criptografar mensagens usando modelos de gerenciamento de direitos, a opção Não Encaminhar e a opção somente criptografia.

Você também pode definir regras de fluxo de emails para aplicar essa proteção. Por exemplo, você pode criar uma regra que exija a criptografia de todas as mensagens endereçadas a um destinatário específico ou que contenha palavras-chave específicas na linha de assunto e também especifique que os destinatários não possam copiar ou imprimir o conteúdo da mensagem.

Além disso, a Criptografia Avançada de Mensagens do [OME](../compliance/ome-advanced-message-encryption.md) ajuda você a cumprir obrigações de conformidade que exigem controles mais flexíveis sobre destinatários externos e seu acesso a emails criptografados. Com a Criptografia Avançada de Mensagens do OME no Microsoft 365, você pode controlar emails confidenciais compartilhados fora da organização com políticas automáticas que detectam tipos de informações confidenciais. 

Para privacidade de dados, se você precisar compartilhar emails com uma parte externa, poderá especificar uma data de expiração e revogar mensagens. Você só pode revogar e definir uma data de expiração para mensagens enviadas a destinatários externos.

### <a name="secure-email-scenarios-comparison-with-ome-and-sensitivity-labels"></a>Comparação de cenários de email seguro com OME e rótulos de sensibilidade

Os rótulos de OME e de sensibilidade aplicados ao email com criptografia têm alguma sobreposição, portanto, é importante entender a quais cenários podem se aplicar, conforme mostrado nesta tabela.

| Cenário | Rótulos de sensibilidade | OME |
|:-------|:-----|:-------|
| Internos + parceiros <br> Comunicar e colaborar com segurança entre usuários internos e parceiros confiáveis | Recomendar – rótulos com classificação e proteção totalmente personalizadas | Sim – Criptografar somente ou Não Encaminhar proteção sem classificação |
| Terceiros externos <br> Comunicar-se e colaborar com segurança com qualquer usuário externo/consumidor | Sim – predefinir destinatários no rótulo | Recomendar – proteção just-in-time com base nos destinatários |
| Parceiros + internos, com expiração/revogação <br> Controlar o acesso de email e conteúdo com usuários internos e parceiros confiáveis com expiração e revogação | Recomendação - proteção totalmente personalizada com duração de acesso, o usuário pode rastrear e revogar arquivos manualmente | Não – nenhuma revogação ou expiração para emails internos |
| Partes externas com expiração/revogação <br> Controlar o acesso de email e conteúdo com usuários externos/consumidores com expiração e revogação | Sim – o usuário pode controlar arquivos manualmente | Recomendar (E5) – o administrador pode revogar emails do Centro de Conformidade e & Segurança |
| Rotulagem automática <br> A organização deseja proteger automaticamente emails/anexos com conteúdos confidenciais específicos e/ou destinatários específicos | Recomendação (E5) - Rotulagem automática em clientes do Exchange e do Outlook, aumenta as regras de fluxo de emails e a política DLP | Sim - regras de fluxo de emails e política DLP com criptografia somente ou não encaminhar proteção |
||||

Também haverá diferenças nas experiências de administrador e usuário final entre esses dois métodos.

## <a name="teams-with-protection-for-highly-sensitive-data"></a>Equipes com proteção para dados altamente confidenciais

Para organizações que planejam armazenar dados pessoais sujeitos [a](secure-teams-security-isolation.md)regulamentações de privacidade de dados no Teams, confira Configurar uma equipe com isolamento de segurança, que fornece orientações detalhadas e etapas de configuração para:

- Identidade e acesso ao dispositivo
- Criação de uma equipe privada
- Bloqueio de permissões subjacentes do site de equipe
- Um rótulo de sensibilidade baseado em grupo com criptografia
