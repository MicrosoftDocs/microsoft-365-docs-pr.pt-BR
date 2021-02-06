---
title: Configurações de gerenciamento de riscos interno
description: Saiba mais sobre as configurações de gerenciamento de risco interno no Microsoft 365
keywords: Microsoft 365, gerenciamento de riscos insider, gerenciamento de riscos, conformidade
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 1e719b03db1c6de0279606d5f46f44eb02368c7e
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126610"
---
# <a name="get-started-with-insider-risk-management-settings"></a>Começar a trabalhar com as configurações de gerenciamento de risco interno

As configurações de gerenciamento de riscos insider se aplicam a todas as políticas de gerenciamento de riscos insider, independentemente do modelo que você escolheu ao criar uma política. As configurações são configuradas usando o controle de configurações de risco do **Insider** localizado na parte superior de todas as guias de gerenciamento de riscos insider. Essas configurações controlam os componentes da política para as seguintes áreas:

- Privacidade
- Indicadores
- Linhas do tempo da política
- Detecções inteligentes
- Exportar alertas (visualização)
- Grupos de usuários prioritários (visualização)
- Ativos físicos de prioridade (visualização)
- Fluxos do Power Automate (visualização)
- Microsoft Teams (visualização)

Antes de começar e criar políticas de gerenciamento de riscos insider, é importante entender essas configurações e escolher os melhores níveis de configuração para as necessidades de conformidade da sua organização.

## <a name="privacy"></a>Privacidade

Proteger a privacidade dos usuários que têm as políticas de acordo é importante e pode ajudar a promover a o objectivity na investigação de dados e análises para alertas de risco interno. Para usuários com uma política de risco interno, você pode escolher uma das seguintes configurações:

- **Mostrar versões anônimas** de nomes de usuário: os nomes dos usuários são anonimizados para impedir que administradores, investigadores de dados e revisadores veja quem está associado aos alertas de política. Por exemplo, um usuário "Grace Ltd" apareceria com um pseudônimo aleatório, como "AnonIS8-988" em todas as áreas da experiência de gerenciamento de riscos interno. Escolher essa configuração anonimiza todos os usuários com as políticas atuais e passadas e se aplica a todas as políticas. As informações do perfil do usuário no alerta de risco interno e os detalhes do caso não estarão disponíveis quando essa opção for escolhida. No entanto, os nomes de usuário são exibidos ao adicionar novos usuários a políticas existentes ou ao atribuir usuários a novas políticas. Se você optar por desativar essa configuração, os nomes de usuário serão exibidos para todos os usuários que possuem as configurações de política atuais ou anteriores.
- **Não mostre versões anônimas** de nomes de usuário: os nomes de usuário são exibidos para todas as políticas atuais e passadas para alertas e casos. As informações de perfil de usuário (nome, título, alias e organização ou departamento) são exibidas para o usuário para todos os alertas e casos de gerenciamento de riscos insider.

![Configurações de privacidade de gerenciamento de riscos interno](../media/insider-risk-settings-privacy.png)

## <a name="indicators"></a>Indicadores

Os modelos de política de risco interno definem o tipo de atividades de risco que você deseja detectar e investigar. Cada modelo de política é baseado em indicadores específicos que correspondem a gatilhos específicos e atividades de risco. Todos os indicadores estão desabilitados por padrão, e você deve selecionar um ou mais indicadores de política antes de configurar uma política de gerenciamento de riscos interno.

Os alertas são disparados por políticas quando os usuários executam atividades relacionadas a indicadores de política que atendem a um limite necessário. O gerenciamento de riscos insider usa dois tipos de indicadores:

- **Eventos de disparo:** eventos que determinam se um usuário está ativo para uma política de gerenciamento de riscos interno. Se um usuário for adicionado a uma política de gerenciamento de risco interno não tiver um evento de disparo, a atividade do usuário não será avaliada pela política. Por exemplo, o Usuário A é  adicionado a uma política criada a partir do roubo de dados, o modelo de política de usuários departamente e a política e o conector de RH do Microsoft 365 estão configurados corretamente. Até que o Usuário A tenha uma data de término relatada pelo conector de RH, as atividades do Usuário A não serão avaliadas por esta política interna de gerenciamento de riscos quanto ao risco. Outro exemplo de um evento de disparo  é se um usuário tiver um alerta de política DLP de alta gravidade ao usar políticas *de vazamento de* dados.
- **Indicadores de** política: indicadores incluídos em políticas de gerenciamento de riscos internas usadas para determinar uma pontuação de risco para um usuário dentro do escopo. Esses indicadores de política são ativados somente depois que ocorre um evento de disparo para um usuário. Alguns exemplos de indicadores de política são quando um usuário copia dados para serviços de armazenamento em nuvem pessoais ou dispositivos de armazenamento portáteis ou se um usuário compartilha arquivos e pastas internos com terceiros externos não autorizados.

Os indicadores de política são segmentados nas áreas a seguir. Você pode escolher os indicadores para ativar e personalizar os limites de eventos do indicador para cada nível de indicador ao criar uma política de risco interno:

- **Indicadores do Office:** incluem indicadores de política para sites do SharePoint, Teams e mensagens de email.
- **Indicadores de** dispositivo: incluem indicadores de política para atividades como o compartilhamento de arquivos pela rede ou com dispositivos. Os indicadores incluem atividades envolvendo arquivos do Microsoft Office. Arquivos CSV e . Arquivos PDF. Se você selecionar **indicadores de dispositivo,** a atividade será processada somente para dispositivos com Windows 10 Build 1809 ou superior. Para obter mais informações sobre como configurar dispositivos para integração com riscos insider, consulte a seção Habilitar indicadores de dispositivo e [dispositivos integrados](insider-risk-management-settings.md#OnboardDevices) a seguir.
- **Indicador de violação de política de** segurança: incluem indicadores do Microsoft Defender para Ponto de Extremidade relacionados à instalação de software não aprovado ou mal-intencionado ou ignorar controles de segurança. Para receber alertas no gerenciamento de riscos insider, você deve ter uma licença ativa do Defender para Ponto de Extremidade e integração de risco interno habilitada. Para obter mais informações sobre como configurar o Defender para Endpoint para integração de gerenciamento de riscos insider, consulte Configurar recursos avançados no [Microsoft Defender para Ponto de Extremidade.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center)
- **Pontuação de risco**: isso inclui aumentar a pontuação de risco para atividades incomuns ou violações de políticas passadas. A habilitação de pontuações de risco aumenta as pontuações de risco e a probabilidade de alertas para esses tipos de atividades. Os indicadores de pontuação de risco só poderão ser selecionados se um ou mais indicadores forem selecionados.

![Configurações do indicador de gerenciamento de riscos interno](../media/insider-risk-settings-indicators.png)

Em alguns casos, talvez você queira limitar os indicadores de política de risco interno que são aplicados a políticas de risco interno em sua organização. Você pode desativar os indicadores de política para áreas específicas desabilitando-os de todas as políticas de risco interno. Eventos de disparo não podem ser modificados para modelos de política de risco interno.

Para definir os indicadores de política de risco interno **habilitados** em todas as políticas de risco internas, navegue até Indicadores de configurações de risco interno e selecione um ou mais indicadores  >   de política. Os indicadores selecionados na página De configurações de Indicadores não podem ser configurados individualmente ao criar ou editar uma política de risco interno no assistente de política.

>[!NOTE]
>Pode levar várias horas para que novos usuários adicionados manualmente apareçam no **painel Usuários.** As atividades dos 90 dias anteriores para esses usuários podem levar até 24 horas para exibição. Para exibir as atividades de usuários adicionados  manualmente,  selecione o usuário no painel Usuários e abra a guia Atividade do usuário no painel de detalhes.

### <a name="enable-device-indicators-and-onboard-devices"></a>Habilitar indicadores de dispositivos e dispositivos de integração
<a name="OnboardDevices"> </a>

Para habilitar o monitoramento de atividades de risco em dispositivos e incluir indicadores de política para essas atividades, seus dispositivos devem atender aos seguintes requisitos e você deve concluir as etapas de integração a seguir.

#### <a name="step-1-prepare-your-endpoints"></a>Etapa 1: Preparar seus pontos de extremidade

Certifique-se de que os dispositivos Windows 10 que você planeja relatar no gerenciamento de riscos insider atendem a esses requisitos.

1. Deve estar executando o Windows 10 x64 build 1809 ou posterior e deve ter instalado a atualização do [Windows 10 (OS Build 17763.1075)](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818) a partir de 20 de fevereiro de 2020.
2. Todos os dispositivos devem estar [ingressados no Azure Active Directory (AAD)](/azure/active-directory/devices/concept-azure-ad-join) ou no Azure AD híbrido.
3. Instale o navegador Microsoft Chromium Edge no dispositivo de ponto de extremidade para monitorar ações para a atividade de carregamento na nuvem. Confira, [Baixar o novo Microsoft Edge baseado em Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).

#### <a name="step-2-onboarding-devices"></a>Etapa 2: Integração de dispositivos
<a name="OnboardStep2"> </a>

Você deve habilitar o monitoramento de dispositivos e integrar seus pontos de extremidade antes de poder monitorar atividades de gerenciamento de riscos interno em um dispositivo. Estas ações estão concluídas no portal de conformidade do Microsoft 365.

Quando quiser fazer a integração de dispositivos que ainda não foram onboarded, você baixará o script apropriado e implantará conforme descrito nas etapas a seguir.

Se você já tiver dispositivos integrados na [Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/), eles já serão exibidos na lista dispositivos gerenciados. Siga [a Etapa 3: se você tiver dispositivos integrados ao Microsoft Defender para Ponto](insider-risk-management-settings.md#OnboardStep3) de Extremidade na próxima seção.

Neste cenário de implantação, você integra dispositivos que ainda não foram onboarded e só deseja monitorar atividades de risco interno em dispositivos Windows 10.

1. Abra o [Centro de conformidade do Microsoft](https://compliance.microsoft.com).
2. Abra a página de configurações do Centro de conformidade e escolha **Integrar dispositivos**.

   > [!NOTE]
   > Enquanto a integração de dispositivos geralmente leva cerca de 60 segundos para que seja habilitada, aguarde até 30 minutos antes de se envolver com o suporte da Microsoft.

3. Escolha **Gerenciamento de dispositivos** para abrir a lista **Dispositivos**. A lista estará vazia até você integrar os dispositivos.
4. Escolha **Integração** para iniciar o processo de integração.
5. Escolha a maneira como você deseja implantar  para esses dispositivos mais na lista de métodos de implantação e baixe **o pacote.**
6. Siga os procedimentos apropriados em [Ferramentas e métodos de integração dos computadores do Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Este link leva você a uma página de destino onde você pode acessar os procedimentos da Proteção Avançada contra Ameaças do Microsoft Defender que correspondem ao pacote de implantação selecionado na etapa 5:
    - Integrar computadores com Windows 10 usando uma política de grupo
    - Integrar computadores com Windows usando o Microsoft Endpoint Configuration Manager
    - Integrar computadores com Windows 10 usando ferramentas de gerenciamento de dispositivo móvel
    - Integrar computadores com Windows 10 usando um script local
    - Integrar computadores não persistentes da VDI (infraestrutura de desktop virtual).

Quando terminar e o ponto de extremidade for onboarded, ele deverá estar visível na lista de dispositivos e o ponto de extremidade começará a relatar logs de atividades de auditoria para o gerenciamento de riscos insider.

> [!NOTE]
> Esta experiência está na imposição da licença. Sem a licença necessária, os dados não estarão visíveis nem acessíveis.

#### <a name="step-3-if-you-have-devices-onboarded-into-microsoft-defender-for-endpoint"></a>Etapa 3: Se você tiver dispositivos integrados ao Microsoft Defender para Ponto de Extremidade
<a name="OnboardStep3"> </a>

Se o Microsoft Defender for Endpoint já estiver implantado e houver relatórios de pontos de extremidade, todos esses pontos de extremidade aparecerão na lista de dispositivos gerenciados. Você pode continuar a integração de novos dispositivos no gerenciamento de riscos interno para expandir a cobertura usando a [seção Etapa 2: Integração de dispositivos.](insider-risk-management-settings.md#OnboardStep2)

1. Abra o [Centro de conformidade do Microsoft](https://compliance.microsoft.com).
2. Abra a página de configurações do Centro de conformidade e escolha **Habilitar o monitoramento de dispositivos**.
3. Escolha **Gerenciamento de dispositivos** para abrir a lista **Dispositivos**. Você deverá ver a lista de dispositivos que já estão relatando para o Microsoft Defender para Ponto de Extremidade.
4. Escolha **Integração** se precisar fazer a integração de mais dispositivos.
5. Escolha a maneira como você deseja implantar  para esses dispositivos mais na lista de métodos de implantação e, em seguida, **baixe o pacote.**
6. Siga os procedimentos apropriados em [Ferramentas e métodos de integração dos computadores do Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Este link leva você a uma página de destino onde você pode acessar os procedimentos da Proteção Avançada contra Ameaças do Microsoft Defender que correspondem ao pacote de implantação selecionado na etapa 5:
    - Integrar computadores com Windows 10 usando uma política de grupo
    - Integrar computadores com Windows usando o Microsoft Endpoint Configuration Manager
    - Integrar computadores com Windows 10 usando ferramentas de gerenciamento de dispositivo móvel
    - Integrar computadores com Windows 10 usando um script local
    - Integrar computadores não persistentes da VDI (infraestrutura de desktop virtual).

Quando terminar e o ponto de extremidade for onboarded, ele deverá estar visível na tabela **Dispositivos** e o ponto de extremidade começará a relatar logs de atividades de auditoria para o gerenciamento de riscos insider.

> [!NOTE]
>Esta experiência está na imposição da licença. Sem a licença necessária, os dados não estarão visíveis nem acessíveis.

### <a name="indicator-level-settings-preview"></a>Configurações de nível do indicador (visualização)

Ao criar uma política no assistente de política, você pode configurar como o número diário de eventos de risco deve influenciar a pontuação de risco para alertas de risco interno. Essas configurações de indicador ajudam a controlar como o número de ocorrências de eventos de risco em sua organização deve afetar a pontuação de risco e, consequentemente, a gravidade de alerta associada para esses eventos. Se preferir, você também pode optar por manter os níveis de limite de eventos padrão recomendados pela Microsoft para todos os indicadores habilitados.

Por exemplo, você decide habilitar os indicadores do SharePoint nas configurações de política de risco interno e definir limites personalizados para eventos do SharePoint ao configurar indicadores para uma nova política de vazamento de dados de risco *interno.* Enquanto estiver no assistente de política de risco interno, você configura três níveis de evento diário diferentes para cada indicador do SharePoint para influenciar a pontuação de risco para alertas associados a esses eventos.

![Configurações do indicador personalizado de gerenciamento de riscos interno](../media/insider-risk-custom-indicators.png)

Para o primeiro nível de evento diário, você pode definir o limite em *10* ou mais eventos por dia para um impacto menor para a pontuação de risco para os eventos, *20* ou mais eventos por dia para um impacto médio na pontuação de risco para os eventos e *30* ou mais eventos por dia um impacto mais alto para a pontuação de risco para os eventos. Essas configurações significam efetivamente:

- Se houver 1 a 9 eventos do SharePoint que ocorrem após o acionamento do evento, as pontuações de risco são minimamente impactadas e tendem a não gerar um alerta.
- Se houver de 10 a 19 eventos do SharePoint que ocorrem após um evento de disparo, a pontuação de risco é inerentemente menor e os níveis de gravidade do alerta tendem a estar em um nível baixo.
- Se houver 20 a 29 eventos do SharePoint que ocorrem após um disparo, a pontuação de risco é inerentemente maior e os níveis de gravidade do alerta tendem a estar em um nível médio.
- Se houver 30 ou mais eventos do SharePoint que ocorrem após um disparo, a pontuação de risco é inerentemente maior e os níveis de gravidade do alerta tendem a estar em um nível alto.

## <a name="policy-timeframes"></a>Períodos de política

Os períodos de tempo da política permitem que você defina períodos de revisão anteriores e futuros que são disparados após as diretivas de acordo com eventos e atividades para os modelos de política de gerenciamento de riscos insider. Dependendo do modelo de política escolhido, os seguintes períodos de política estão disponíveis:

- **Janela de** ativação : Disponível para  todos os modelos de política, **a** janela Ativação é o número definido de dias que a janela ativa após um evento de disparo. A janela é ativada por 1 a 30 dias após um evento de disparo ocorrer para qualquer usuário atribuído à política. Por exemplo, você configurou uma política de gerenciamento de riscos interno e definiu a janela *Ativação* para 30 dias. Já se passaram vários meses desde que você configurou a política e ocorre um evento de disparo para um dos usuários incluídos na política. O evento de disparo ativa a janela *Ativação* e a política fica ativa para esse usuário por 30 dias após o evento de disparo ocorrer.
- **Detecção de atividades anteriores**: Disponível para  todos os modelos de política, **a** detecção de atividade passada é o número definido de dias que a janela ativa antes de um evento de disparo. A janela é ativada de 0 a 180 dias antes que um evento de disparo ocorra para qualquer usuário atribuído à política. Por exemplo, você configurou uma política de gerenciamento de riscos interno e definiu a detecção *de* atividades anteriores como 90 dias. Já se passaram vários meses desde que você configurou a política e ocorre um evento de disparo para um dos usuários incluídos na política. O evento de disparo  ativa a detecção de atividades anteriores e a política reúne atividades históricas para esse usuário por 90 dias antes do evento de disparo.

![Configurações de período de gerenciamento de risco interno](../media/insider-risk-settings-timeframes.png)

## <a name="intelligent-detections"></a>Detecções inteligentes

As configurações de detecção inteligente ajudam a refinar como as detecções de atividades arriscadas são processadas para alertas. Em determinadas circunstâncias, talvez seja necessário definir tipos de arquivos a ignorar ou impor um nível de detecção para os arquivos para ajudar a definir uma barra mínima para alertas. Use essas configurações para controlar o volume de alerta geral, exclusões de tipo de arquivo e limites de volume de arquivo.

### <a name="anomaly-detections"></a>Detecções de anomalias

Detecções anômalas incluem configurações para exclusões de tipo de arquivo e limites de volume de arquivo.

- **Exclusões de tipo de** arquivo: para excluir tipos de arquivo específicos de todas as correspondências de política de gerenciamento de risco interno, insira extensões de tipo de arquivo separadas por vírgulas. Por exemplo, para excluir determinados tipos de arquivos de música de diretivas que você pode inserir *aac,mp3,wav,wma* no campo **exclusões de** tipo de arquivo. Os arquivos com essas extensões seriam ignorados por todas as políticas de gerenciamento de risco interno.
- **Limite de corte de volume** de arquivo: para definir um nível mínimo de arquivo antes que os alertas de atividade sejam relatados em políticas de risco interno, insira o número de arquivos. Por exemplo, você digitaria "10" se não quisesse gerar alertas de risco interno quando um usuário baixasse 10 arquivos ou menos, mesmo que as políticas considerem essa atividade uma anomalia.

### <a name="alert-volume"></a>Volume de alertas

As atividades do usuário detectadas pelas políticas de risco interno são atribuídas a uma pontuação de risco específica, que, por sua vez, determina a gravidade do alerta (baixa, média, alta). Por padrão, geraremos uma determinada quantidade de alertas de baixa, média e alta gravidade, mas você pode aumentar ou diminuir o volume para atender às suas necessidades. Para ajustar o volume de alertas para todas as políticas de gerenciamento de riscos insider, escolha uma das seguintes configurações:

- **Menos alertas:** você verá todos os alertas de alta gravidade, menos alertas de gravidade média e nenhum alerta de gravidade baixa. Esse nível de configuração significa que você pode perder alguns verdadeiros positivos.
- **Volume padrão:** você verá todos os alertas de alta gravidade e uma quantidade balanceada de alertas de gravidade média e baixa.
- **Mais alertas:** você verá todos os alertas de gravidade média e alta e alertas de gravidade mais baixa. Esse nível de configuração pode resultar em mais falsos positivos.

### <a name="microsoft-defender-for-endpoint-preview"></a>Microsoft Defender para Ponto de Extremidade (visualização)

[O Microsoft Defender for Endpoint é](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) uma plataforma de segurança de ponto de extremidade corporativa projetada para ajudar as redes corporativas a prevenir, detectar, investigar e responder a ameaças avançadas. Para ter melhor visibilidade da violação de segurança em sua organização, você pode importar e filtrar alertas do Defender para Ponto de Extremidade para atividades usadas em políticas criadas a partir de modelos de política de violação de segurança de gerenciamento de riscos interno.

Dependendo dos tipos de sinais nos quais você está interessado, você pode optar por importar alertas para o gerenciamento de riscos insider com base no status de triagem de alerta do Defender para Ponto de Extremidade. Você pode definir um ou mais dos seguintes status de triagem de alerta nas configurações globais a importar:

- Desconhecido
- Novo
- Em andamento
- Resolvido

Os alertas do Defender para o Ponto de Extremidade são importados diariamente. Dependendo do status de triagem que você escolher, você poderá ver várias atividades de usuário para o mesmo alerta que o status de triagem muda no Defender para o ponto de extremidade.

Por exemplo, se você selecionar Novo  *,* Em andamento e Resolvido para essa configuração, quando um alerta do Microsoft Defender for Endpoint for gerado e o status for *Novo,* uma atividade de alerta inicial será importada para o usuário em risco interno. Quando o status de triagem do Defender for Endpoint muda para Em *andamento,* uma segunda atividade para esse alerta é importada para o usuário em risco interno. Quando o status final de triagem do Defender para Ponto de Extremidade de *Resolvido* é definido, uma terceira atividade para esse alerta é importada para o usuário em risco interno. Essa funcionalidade permite que os investigadores sigam a progressão dos alertas do Defender para Ponto de Extremidade e escolham o nível de visibilidade que a investigação exige.

>[!IMPORTANT]
>Você precisará ter o Microsoft Defender para Ponto de Extremidade configurado em sua organização e habilitar o Defender para Ponto de Extremidade para integração de gerenciamento de riscos insider na Central de Segurança do Defender para importar alertas de violação de segurança. Para obter mais informações sobre como configurar o Defender para Endpoint para integração de gerenciamento de riscos insider, consulte Configurar recursos avançados [no Defender para Ponto de Extremidade.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center)

### <a name="domains-preview"></a>Domínios (visualização)

As configurações de domínio ajudam a definir níveis de risco para comunicações com domínios específicos. Essas comunicações incluem o compartilhamento de arquivos, mensagens de email ou download de conteúdo. Ao especificar domínios nessas configurações, você pode aumentar ou diminuir a pontuação de risco para atividades que ocorrem com esses domínios. Por exemplo, para especificar contoso.com e sales.wingtiptoys.com como domínios permitidos, você inserirá "contoso.com sales.wingtiptoys.com" no **campo Domínios Permitidos.**

Para cada uma das seguintes configurações de domínio, você pode inserir até 500 domínios:

- **Domínios não au estertados:** Ao especificar domínios não estertados, as atividades que ocorrerem com esses domínios terão *pontuações de* risco mais altas.
- **Domínios permitidos:** Ao especificar domínios permitidos nas configurações, as atividades  que ocorrerem com esses domínios terão pontuações de risco menores e serão tratadas da mesma forma como a atividade da organização interna é tratada. Por exemplo, as atividades de email para esses domínios são analisadas da mesma forma que a atividade de email interna é analisada.
- **Domínios de terceiros:** Domínios de terceiros são domínios usados para fins comerciais em sua organização e conteúdos confidenciais podem ser armazenados nesses locais. Especificando um domínio de terceiros, você pode receber alertas para qualquer atividade arriscada nesses domínios.

## <a name="export-alerts-preview"></a>Exportar alertas (visualização)

Informações de alerta de gerenciamento de riscos insider são exportáveis para serviços de gerenciamento de eventos e informações de segurança (SIEM) por meio do esquema da API da Atividade de Gerenciamento do [Office 365.](/office/office-365-management-api/office-365-management-activity-api-schema#security-and-compliance-alerts-schema) Você pode usar as APIs da Atividade de Gerenciamento do Office 365 para exportar informações de alerta para outros aplicativos que sua organização pode usar para gerenciar ou agregar informações de risco interno.

Para usar as APIs para revisar as informações de alerta de risco interno:

1. Habilitar o suporte da API da Atividade de Gerenciamento do Office 365 na Exportação de Configurações de Gerenciamento de Riscos  >    >  **do** Insider. Por padrão, essa configuração está desabilitada para sua organização do Microsoft 365.
2. Filtrar as atividades de auditoria comuns do Office 365 *por SecurityComplianceAlerts*.
3. Filtrar *SecurityComplianceAlerts* pela *categoria InsiderRiskManagement.*

![Configurações de alerta de exportação de gerenciamento de risco interno](../media/insider-risk-settings-export.png)

As informações de alerta contêm informações do esquema de alerta de segurança e conformidade e do esquema comum da API da Atividade de Gerenciamento do Office 365.

Os campos e valores a seguir são exportados para alertas de gerenciamento de riscos insider para o esquema de alerta de segurança & conformidade:

| **Parâmetro de alerta** | **Descrição** |
|:------------------|:----------------|
| AlertType | O tipo de alerta é *Personalizado.*  |
| AlertId | O GUID do alerta. Os alertas de gerenciamento de riscos insider são mutáveis. À medida que o status do alerta muda, um novo log com o mesmo AlertID é gerado. Essa AlertID pode ser usada para correlacionar atualizações para um alerta. |
| Categoria | A categoria do alerta é *InsiderRiskManagement*. Essa categoria pode ser usada para distinguir esses alertas de outros alertas de conformidade & segurança. |
| Comments | Comentários padrão do alerta. Os valores *são Novo Alerta* (registrado quando um alerta é criado) e Alerta *Atualizado* (registrado quando há uma atualização para um alerta). Use o AlertID para correlacionar as atualizações de um alerta. |
| Dados | Os dados do alerta incluem a ID de usuário exclusiva, o nome principal do usuário e a data e hora (UTC) quando o usuário foi disparado em uma política. |
| Nome | Nome da política para a política de gerenciamento de riscos interno que gerou o alerta. |
| PolicyId | O GUID da política de gerenciamento de riscos interno que disparou o alerta. |
| Severity | A gravidade do alerta. Os valores *são Alto,* *Médio* ou *Baixo.* |
| Source | A origem do alerta. O valor é Conformidade *e Segurança do Office 365 & Segurança.* |
| Status | O status do alerta. Os valores estão *ativos* (*Precisa* de Revisão no risco *interno),* Investigando *(* Confirmado no risco interno), *Resolvido* *(* Resolvido no risco interno), *Descartado* *(* Ignorado no risco interno). |
| Versão | A versão do esquema de alerta de segurança e conformidade. |

Os campos e valores a seguir são exportados para alertas de gerenciamento de riscos interno para o esquema comum da API da Atividade de Gerenciamento do [Office 365.](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)

- UserId
- Id
- RecordType
- CreationTime
- Operation
- OrganizationId
- UserType
- UserKey

## <a name="priority-user-groups-preview"></a>Grupos de usuários prioritários (visualização)

Os usuários em sua organização podem ter níveis diferentes de risco, dependendo de sua posição, nível de acesso a informações confidenciais ou histórico de riscos. Priorizar o exame e a pontuação das atividades desses usuários pode ajudar a alertá-lo sobre possíveis riscos que podem ter consequências maiores para sua organização. Grupos de usuários prioritários no gerenciamento de riscos insider ajudam a definir os usuários em sua organização que precisam de uma inspeção mais próxima e pontuação de risco mais sensível. Juntamente com as violações da política de segurança por usuários *prioritários* e *vazamentos* de dados por modelos de política de usuários prioritários, os usuários adicionados a um grupo de usuários com prioridade têm uma maior probabilidade de alertas e alertas de risco interno com níveis de gravidade mais altos.

![Configurações de grupo de usuários com prioridade de gerenciamento de risco interno](../media/insider-risk-settings-priority-users.png)

Por exemplo, você precisa se proteger contra vazamentos de dados para um projeto altamente confidencial onde os usuários têm acesso a informações confidenciais. Você opta por criar *um grupo de* *usuários* com prioridade confidencial de Usuários do Projeto para usuários em sua organização que trabalham nesse projeto. Usando o assistente de política e os vazamentos de dados por  modelo de política de usuários *prioritários,* você cria uma nova política e atribui à política o grupo de usuários com prioridade de Usuários do Projeto Confidencial. As atividades examinadas pela política  para membros do grupo de usuários com prioridade de Usuários do Projeto Confidencial são mais sensíveis ao risco e as atividades desses usuários têm mais probabilidade de gerar um alerta e ter alertas com níveis de severidade mais altos.

### <a name="create-a-priority-user-group"></a>Criar um grupo de usuários com prioridade

Para criar um novo grupo de usuários com prioridade, você usará os controles de configuração na solução de gerenciamento de riscos do **Insider** no centro de conformidade do Microsoft 365. Para criar um grupo de usuários com prioridade, você deve ser membro do grupo de funções Gerenciamento de Riscos Do *Insider* ou Administrador de Gerenciamento de Riscos *Do Insider.*

Conclua as seguintes etapas para criar um grupo de usuários com prioridade:

1. No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com)vá para o gerenciamento de riscos do **Insider** e selecione as configurações de risco **do Insider.**
2. Selecione a **guia Grupos de usuários prioridade**
3. Na guia **Grupos de usuários prioridade,** selecione **Criar grupo de usuários de prioridade** para iniciar o assistente de criação de grupo.
4. Na página **Definir grupo,** preencha os seguintes campos:
    - **Nome (obrigatório)**: insira um nome amigável para o grupo de usuários de prioridade. Você não pode alterar o nome do grupo de usuários de prioridade depois de concluir o assistente.
    - **Descrição (opcional)**: insira uma descrição para o grupo de usuários com prioridade.
5. Selecione **Próximo** para continuar.
6. Na  página Escolher membros, selecione Escolher membros para pesquisar e selecionar quais contas de  usuário habilitadas para email estão incluídas no grupo ou marque a caixa de seleção Selecionar todas as caixas de seleção para adicionar todos os usuários em sua organização ao grupo.  Selecione **Adicionar** para continuar ou **Cancelar** para fechar sem adicionar usuários ao grupo.
7. Selecione **Próximo** para continuar.
8. Na página **Revisão,** revise as configurações escolhidas para o grupo de usuários de prioridade. Selecione **Editar** para alterar qualquer um dos valores de grupo ou **selecione Enviar** para criar e ativar o grupo de usuários de prioridade.
9. Na página de confirmação, selecione **Feito** para sair do assistente.

### <a name="update-a-priority-user-group"></a>Atualizar um grupo de usuários com prioridade

Para atualizar um grupo de usuários com prioridade existente, você usará os controles de configuração na solução de gerenciamento de riscos do **Insider** no centro de conformidade do Microsoft 365. Para atualizar um grupo de usuários com prioridade, você deve ser membro do grupo de funções Gerenciamento de Riscos Do *Insider* ou Administrador de Gerenciamento de Riscos *Do Insider.*

Conclua as seguintes etapas para editar um grupo de usuários com prioridade:

1. No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com)vá para o gerenciamento de riscos do **Insider** e selecione as configurações de risco **do Insider.**
2. Selecione a **guia Grupos de usuários prioridade**
3. Selecione o grupo de usuários de prioridade que você deseja editar e selecione **Editar grupo.**
4. Na página **Definir grupo,** atualize o campo Descrição, se necessário. Não é possível atualizar o nome do grupo de usuários de prioridade. Selecione **Próximo** para continuar.
5. Na página **Escolher membros,** adicione novos membros ao grupo usando o **controle Escolher membros.** Para remover um usuário do grupo, selecione o 'X' ao lado do usuário que você deseja remover. Selecione **Próximo** para continuar.
6. Na página **Revisão,** revise as configurações de atualização escolhidas para o grupo de usuários prioritário. Selecione **Editar** para alterar qualquer um dos valores de grupo ou **selecione Enviar** para atualizar o grupo de usuários de prioridade.
7. Na página de confirmação, selecione **Feito** para sair do assistente.

### <a name="delete-a-priority-user-group"></a>Excluir um grupo de usuários com prioridade

Para excluir um grupo de usuários com prioridade existente, você usará os controles de configuração na solução de gerenciamento de riscos do **Insider** no centro de conformidade do Microsoft 365. Para excluir um grupo de usuários com prioridade, você deve ser membro do grupo de funções Gerenciamento de Riscos Do *Insider* ou Administrador de Gerenciamento de Riscos *Do Insider.*

>[!IMPORTANT]
>Excluir um grupo de usuários com prioridade o removerá de qualquer política ativa à qual ele está atribuído. Se você excluir um grupo de usuários com prioridade atribuída a uma política ativa, a política não conterá nenhum usuário no escopo e estará efetivamente ociosa e não criará alertas.

Conclua as seguintes etapas para excluir um grupo de usuários com prioridade:

1. No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com)vá para o gerenciamento de riscos do **Insider** e selecione as configurações de risco **do Insider.**
2. Selecione a **guia Grupos de usuários prioridade**
3. Selecione o grupo de usuários de prioridade que você deseja editar e selecione **Excluir** no menu do painel.
4. Na caixa **de diálogo** Excluir, selecione **Sim** para excluir o grupo de usuários de prioridade ou selecione **Cancelar** para retornar ao painel.

## <a name="priority-physical-assets-preview"></a>Ativos físicos de prioridade (visualização)

Identificar o acesso a ativos físicos prioritários e correlacionar a atividade de acesso a eventos do usuário é um componente importante da infraestrutura de conformidade. Esses ativos físicos representam locais de prioridade em sua organização, como edifícios da empresa, data centers ou salas de servidor. Atividades de risco interno podem ser associadas a usuários trabalhando em horários incomuns, tentando acessar essas áreas confidenciais ou seguras não autorizadas e solicitações de acesso a áreas de alto nível sem necessidades legítimas.

Com os ativos físicos [](import-physical-badging-data.md) de prioridade habilitados e o conector de dados de danos físicos configurado, o gerenciamento de riscos internos integra sinais de seu controle físico e sistemas de acesso a outras atividades de risco do usuário. Examinando padrões de comportamento em sistemas de acesso físico e correlacionando essas atividades com outros eventos de risco internos, o gerenciamento de riscos internos pode ajudar os investigadores e analistas de conformidade a tomar decisões de resposta mais informadas para alertas. O acesso a ativos físicos prioritários é pontuado e identificado em informações de maneira diferente do acesso a ativos não prioritários.

Por exemplo, sua organização tem um sistema de badging para usuários que monitoram e aprovam o acesso físico a áreas normais de trabalho e projetos confidenciais. Você tem vários usuários trabalhando em um projeto sensível e esses usuários retornarão para outras áreas da sua organização quando o projeto for concluído. À medida que o projeto confidencial se aproximar da conclusão, você deve garantir que o trabalho do projeto permaneça confidencial e que o acesso às áreas do projeto seja fortemente controlado.

Você opta por habilitar o conector de dados de danos físicos no Microsoft 365 para importar informações de acesso do seu sistema de danos físicos e especificar ativos físicos prioritários no gerenciamento de riscos insider. Ao importar informações do seu sistema de danos e correlacionar informações de acesso físico com outras atividades de risco identificadas no gerenciamento de riscos insider, você perceberá que um dos usuários no projeto está acessando os escritórios do projeto após o horário de trabalho normal e também está exportando grandes quantidades de dados para um serviço de armazenamento pessoal em nuvem de sua área de trabalho normal. Essa atividade de acesso físico associada à atividade online pode apontar para um possível roubo de dados e os investigadores e analistas de conformidade podem tomar as medidas apropriadas, conforme determinado pelas circunstâncias desse usuário.

### <a name="configure-priority-physical-assets"></a>Configurar ativos físicos prioritários

Para configurar ativos físicos prioritários, você configurará o conector  de badging físico e usará os controles de configuração na solução de gerenciamento de riscos internos no centro de conformidade do Microsoft 365. Para configurar ativos físicos de prioridade, você deve ser membro do grupo de funções Gerenciamento de Risco Interno ou Administrador de Gerenciamento de Riscos Do *Insider.* 

Conclua as seguintes etapas para configurar ativos físicos prioritários:

1. Siga as etapas de configuração para o gerenciamento de riscos insider no artigo Sobre como começar a trabalhar com o [gerenciamento de riscos insider.](insider-risk-management-configure.md) Na Etapa 3, configure o conector de badging físico.

    >[!IMPORTANT]
    >Para que as políticas de gerenciamento de riscos insider usem e correlacionem dados de sinal relacionados a usuários de saída e encerrados com dados de eventos de suas plataformas de controle físico e acesso, você também deve configurar o conector de RH do Microsoft 365. Se você habilitar o conector de badging físico sem habilitar o conector de RH do Microsoft 365, as políticas de gerenciamento de riscos insider processarão apenas eventos para atividades de acesso físico para usuários em sua organização.

2. No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com)vá para o gerenciamento de riscos do **Insider** e selecione Configurações de risco **internas** Ativos físicos de  >  **prioridade.**
3. Na página **Prioridade** de ativos físicos, você pode adicionar manualmente as IDs de ativo físico que deseja monitorar para os eventos de ativo importados pelo conector de badging físico ou importar um . Arquivo CSV de todas as IDs de ativos físicos importadas pelo conector de badging físico: a) Para adicionar manualmente IDs de ativos físicos, escolha Adicionar ativos físicos de **prioridade,** insira uma ID de ativo físico e selecione **Adicionar**. Insira outras IDs de ativo físico e selecione **Adicionar ativos físicos de prioridade** para salvar todos os ativos inseridos.
    b) Para adicionar uma lista de IDs de ativo físico de um . Arquivo CSV, escolha **Importar ativos físicos de prioridade.** Na caixa de diálogo explorador de arquivos, selecione o . Arquivo CSV que você deseja importar e selecione **Abrir**. As IDs de ativo físico do . Os arquivos CSV são adicionados à lista.
4. Navegue até a **guia Indicadores de** política em Configurações.
5. Na página **Indicadores de política,** navegue até a seção Indicadores de acesso físico e marque a caixa de seleção de acesso físico após o término ou falha no acesso **ao ativo sensível.** 
6. Selecione **Salvar** para configurar e sair.

### <a name="delete-a-priority-physical-asset"></a>Excluir um ativo físico de prioridade

Para excluir um ativo físico de prioridade existente, você usará a definição de controles na solução de gerenciamento de riscos do Insider no centro de conformidade do Microsoft 365. Para excluir um ativo físico de prioridade, você deve ser membro do grupo de funções Gerenciamento de Riscos Do Insider ou Administrador de Gerenciamento de Riscos Do Insider.

>[!IMPORTANT]
>A exclusão de um ativo físico de prioridade o remove da análise por qualquer política ativa à qual ele foi incluído anteriormente. Os alertas gerados por atividades associadas ao ativo físico de prioridade não são excluídos.

Conclua as seguintes etapas para excluir um ativo físico de prioridade:

1. No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com)vá para o gerenciamento de riscos do **Insider** e selecione Configurações de risco **internas** Ativos físicos de  >  **prioridade.**
2. Na página **Prioridade de ativos físicos,** selecione o ativo que você deseja excluir.
3. Selecione **Excluir** no menu ação para excluir o ativo.

## <a name="power-automate-flows-preview"></a>Fluxos do Power Automate (visualização)

[O Microsoft Power Automate é](/power-automate/getting-started) um serviço de fluxo de trabalho que automatiza ações entre aplicativos e serviços. Usando fluxos de modelos ou criados manualmente, você pode automatizar tarefas comuns associadas a esses aplicativos e serviços. Ao habilitar fluxos do Power Automate para gerenciamento de riscos insider, você pode automatizar tarefas importantes para casos e usuários. Você pode configurar fluxos do Power Automate para recuperar informações de usuário, alerta e caso e compartilhar essas informações com participantes e outros aplicativos, bem como automatizar ações no gerenciamento de riscos insider, como postar em anotações de caso. Os fluxos do Power Automate são aplicáveis para casos e qualquer usuário no escopo de uma política.

Os clientes com assinaturas do Microsoft 365 que incluem o gerenciamento de riscos insider não precisam de licenças adicionais do Power Automate para usar os modelos do Power Automate de gerenciamento de risco interno recomendados. Esses modelos podem ser personalizados para dar suporte à sua organização e abranger os principais cenários de gerenciamento de riscos insider. Se você optar por usar recursos premium do Power Automate nesses modelos, crie um modelo personalizado usando o conector de conformidade do Microsoft 365 ou use modelos do Power Automate para outras áreas de conformidade no Microsoft 365, talvez seja necessário mais licenças do Power Automate.

Os seguintes modelos do Power Automate são fornecidos aos clientes para dar suporte à automação de processos para usuários e casos de gerenciamento de riscos insider:

- **Notificar** os usuários quando eles são adicionados a uma política de risco interno: esse modelo é para organizações que têm políticas internas, privacidade ou requisitos regulatórios que os usuários devem ser notificados quando estão sujeitos a políticas de gerenciamento de riscos internos. Quando esse fluxo é configurado e selecionado para um usuário na página usuários, os usuários e seus gerentes são enviados uma mensagem de email quando o usuário é adicionado a uma política de gerenciamento de riscos interno. Esse modelo também oferece suporte à atualização de uma lista do SharePoint hospedada em um site do SharePoint para ajudar a controlar detalhes da mensagem de notificação, como data/hora e o destinatário da mensagem. Se você optou por tornar os usuários anônimos nas configurações de Privacidade, os **fluxos** criados a partir desse modelo não funcionarão conforme o esperado para que a privacidade do usuário seja mantida. Os fluxos do Power Automate usando esse modelo estão disponíveis no **painel Usuários.**
- Solicite informações do **RH** ou de negócios sobre um usuário em um caso de risco interno: ao atuar em um caso, os analistas e investigadores de riscos insider talvez precisem consultar o RH ou outros participantes para entender o contexto das atividades do caso. Quando esse fluxo é configurado e selecionado para um caso, analistas e investigadores enviam uma mensagem de email para o RH e os participantes de negócios configurados para esse fluxo. Cada destinatário recebe uma mensagem com opções de resposta pré-configuradas ou personalizáveis. Quando os destinatários selecionam uma opção de resposta, a resposta é registrada como uma anotação de caso e inclui informações de destinatário e data/hora. Se você optou por tornar os usuários anônimos nas configurações de Privacidade, os **fluxos** criados a partir desse modelo não funcionarão conforme o esperado para que a privacidade do usuário seja mantida. Fluxos do Power Automate usando esse modelo estão disponíveis no painel **Casos.**
- **Notificar o gerente quando um** usuário tiver um alerta de risco interno: algumas organizações talvez precisem ter uma notificação de gerenciamento imediata quando um usuário tiver um alerta de gerenciamento de riscos interno. Quando esse fluxo é configurado e selecionado, o gerente do usuário da ocorrência recebe uma mensagem de email com as seguintes informações sobre todos os alertas de caso:
    - Política aplicável para o alerta
    - Data/hora do alerta
    - Nível de gravidade do alerta

    O fluxo atualiza automaticamente as anotações de caso em que a mensagem foi enviada e que o fluxo foi ativado. Se você optou por tornar os usuários anônimos nas configurações de Privacidade, os **fluxos** criados a partir desse modelo não funcionarão conforme o esperado para que a privacidade do usuário seja mantida. Fluxos do Power Automate usando esse modelo estão disponíveis no painel **Casos.**

- **Adicione um** lembrete de calendário para acompanhar um caso de risco interno: este modelo permite que os investigadores e analistas de risco adicionem lembretes de calendário para casos ao calendário do Office 365 Outlook. Esse fluxo elimina a necessidade de os usuários saírem ou saírem do fluxo de trabalho de gerenciamento de riscos interno ao processar casos e triar alertas. Quando esse fluxo é configurado e selecionado, um lembrete é adicionado ao calendário do Outlook do Office 365 para o usuário que está executando o fluxo. Fluxos do Power Automate usando esse modelo estão disponíveis no painel **Casos.**
- Crie um registro para o caso de risco interno no **ServiceNow:** esse modelo é para organizações que querem usar sua solução ServiceNow para rastrear casos de gerenciamento de riscos insider.  Quando, em um caso, analistas e investigadores de risco interno podem criar um registro para o caso no ServiceNow. Você pode personalizar esse modelo para preencher campos selecionados no ServiceNow com base nos requisitos da sua organização. Fluxos do Power Automate usando esse modelo estão disponíveis no painel **Casos.** Para obter mais informações sobre os campos disponíveis do ServiceNow, consulte o artigo de referência do [Conector do ServiceNow.](/connectors/service-now/)

### <a name="create-a-power-automate-flow-from-insider-risk-management-template"></a>Criar um fluxo do Power Automate a partir do modelo de gerenciamento de riscos interno

Para criar um fluxo do Power Automate a partir de um modelo de gerenciamento de riscos internos recomendado, você usará os controles de configurações na solução de  gerenciamento de riscos do **Insider** no centro de conformidade do Microsoft 365 ou na opção Gerenciar **fluxos** do **Power Automate** do controle **Automate** ao trabalhar diretamente nos painéis Casos ou Usuários.

Para criar um fluxo do Power Automate na área de  configurações,  você deve ser membro do grupo de funções Gerenciamento de Risco Interno ou Administrador de Gerenciamento de Risco Interno. Para criar um fluxo do Power Automate com a opção Gerenciar fluxos do **Power Automate,** você deve ser membro de pelo menos um grupo de função de gerenciamento de risco interno.

Conclua as seguintes etapas para criar um fluxo do Power Automate a partir de um modelo de gerenciamento de risco interno recomendado:

1. No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com/)vá para o gerenciamento de riscos do Insider e selecione configurações de risco do **Insider** **fluxos**  >  **do Power Automate.** Você também pode acessar a partir das **páginas de** painéis Casos ou Usuários escolhendo **Automatizar o** gerenciamento de   >  **fluxos do Power Automate.**
2. Na página **fluxos do Power Automate,** selecione um modelo recomendado dos modelos de gerenciamento de riscos do **Insider que** você talvez adoe a seção na página.
3. O fluxo lista as conexões incorporadas necessárias para o fluxo e observará se os status da conexão estão disponíveis. Se necessário, atualize as conexões que não são exibidas como disponíveis. Selecione **Continuar**.
4. Por padrão, os fluxos recomendados são pré-configurados com o gerenciamento de risco interno recomendado e os campos de dados de serviço do Microsoft 365 necessários para concluir a tarefa atribuída para o fluxo. Se necessário, personalize os componentes de fluxo usando o controle Mostrar opções **avançadas** e configurando as propriedades disponíveis para o componente de fluxo.
5. Se necessário, adicione outras etapas ao fluxo selecionando o **botão Nova etapa.** Na maioria dos casos, isso não deve ser necessário para os modelos padrão recomendados.
6. Selecione **Salvar rascunho para** salvar o fluxo para configuração posterior ou selecione **Salvar** para concluir a configuração do fluxo.
7. Selecione **Fechar** para retornar à página de **fluxo do Power Automate.** O novo modelo será listado como  um fluxo nas guias Meus fluxos e estará **automaticamente** disponível no controle de lista suspenso Automatizar ao trabalhar com casos de gerenciamento de riscos insider para o usuário que está criando o fluxo.

>[!IMPORTANT]
>Se outros usuários em sua organização precisam acessar o fluxo, o fluxo deve ser compartilhado.

### <a name="create-a-custom-power-automate-flow-for-insider-risk-management"></a>Criar um fluxo personalizado do Power Automate para gerenciamento de riscos insider

Alguns processos e fluxos de trabalho para sua organização podem estar fora dos modelos de fluxo de gerenciamento de riscos internos recomendados e você pode ter a necessidade de criar fluxos personalizados do Power Automate para áreas de gerenciamento de riscos internos. Os fluxos do Power Automate são flexíveis e suportam personalização extensa, mas há etapas que precisam ser realizadas para integrar-se aos recursos de gerenciamento de riscos insider.

Conclua as seguintes etapas para criar um modelo personalizado do Power Automate para gerenciamento de riscos insider:

1. Verifique sua licença de fluxo do **Power Automate:** para criar fluxos personalizados do Power Automate que usam gatilhos de gerenciamento de riscos insider, você precisará de uma licença do Power Automate. Os modelos de fluxo de gerenciamento de riscos insider recomendados não exigem licenciamento extra e são incluídos como parte da sua licença de gerenciamento de riscos insider.
2. **Crie um fluxo automatizado:** crie um fluxo que execute uma ou mais tarefas depois que ele é disparado por um evento de gerenciamento de riscos interno. Para obter detalhes sobre como criar um fluxo automatizado, consulte [Criar um fluxo no Power Automate](/power-automate/get-started-logic-flow).
3. Selecione o conector de conformidade do **Microsoft 365:** procure e selecione o conector de conformidade do Microsoft 365. Esse conector habilita gatilhos e ações de gerenciamento de riscos insider. Para obter mais informações sobre conectores, consulte o [artigo de visão geral de referência do](/connectors/connector-reference/) Conector.
4. **Escolha gatilhos de gerenciamento de** riscos insider para seu fluxo: o gerenciamento de riscos do Insider tem dois gatilhos disponíveis para fluxos personalizados do Power Automate:
    - **Para um caso de gerenciamento de risco** interno selecionado: fluxos com esse gatilho podem ser selecionados na página de painel Casos de gerenciamento de riscos insider.
    - Para um usuário selecionado de gerenciamento de **riscos insider:** fluxos com esse gatilho podem ser selecionados na página de painel Usuários de gerenciamento de riscos insider.
5. Escolha ações de gerenciamento de riscos internas para seu fluxo: você pode escolher entre várias ações para o gerenciamento de riscos insider incluir em seu fluxo personalizado:
    - Obter alerta de gerenciamento de riscos interno
    - Obter caso de gerenciamento de riscos interno
    - Obter usuário de gerenciamento de riscos insider
    - Obter alertas de gerenciamento de riscos interno para uma ocorrência
    - Add insider risk management case note

### <a name="share-a-power-automate-flow"></a>Compartilhar um fluxo do Power Automate

Por padrão, os fluxos do Power Automate criados por um usuário estão disponíveis apenas para esse usuário. Para que outros usuários de gerenciamento de riscos insider tenham acesso e usem um fluxo, o fluxo deve ser compartilhado pelo criador do fluxo. Para compartilhar um fluxo, você usará os controles de configurações na solução de gerenciamento de riscos do **Insider** no centro de conformidade  do  Microsoft 365 ou na opção Gerenciar fluxos do **Power Automate** do controle automatizado ao trabalhar diretamente nas páginas de painel Casos ou Usuários. Depois de compartilhar um fluxo, todas as pessoas com quem  ele foi compartilhado  podem acessar o fluxo no menu suspenso Automatizar controles nos painéis Caso **e Usuário.**

Para compartilhar um fluxo do Power Automate na área de  configurações,  você deve ser membro do grupo de funções Gerenciamento de Risco Interno ou Administrador de Gerenciamento de Risco Interno. Para compartilhar um fluxo do Power Automate com a opção Gerenciar fluxos do **Power Automate,** você deve ser membro de pelo menos um grupo de função de gerenciamento de risco interno.

Conclua as seguintes etapas para compartilhar um fluxo do Power Automate:

1. No centro [de conformidade do Microsoft 365,](htttps://compliance.microsoft.com)vá para o gerenciamento de riscos do Insider e selecione as configurações de risco do **Insider** **fluxos**  >  **do Power Automate.** Você também pode acessar a partir das **páginas de** painéis Casos ou Usuários escolhendo **Automatizar o** gerenciamento de   >  **fluxos do Power Automate.**
2. Na página **Fluxos do Power Automate,** selecione a **guia Meus fluxos** ou **Fluxos de** equipe.
3. Selecione o fluxo a ser compartilhá-lo e, em seguida, **selecione Compartilhar** no menu opções de fluxo.
4. Na página de compartilhamento de fluxo, insira o nome do usuário ou grupo que você deseja adicionar como proprietário do fluxo.
5. Na caixa **de diálogo Conexão Usada,** selecione **OK** para confirmar que o usuário ou grupo adicionado terá acesso total ao fluxo.

### <a name="edit-a-power-automate-flow"></a>Editar um fluxo do Power Automate

Para editar um fluxo, você usará os controles de configurações na solução de gerenciamento de riscos do **Insider** no centro de conformidade  do Microsoft 365 ou na opção Gerenciar **fluxos** do **Power Automate** do controle Automatizado ao trabalhar diretamente nos painéis Casos ou Usuários. 

Para editar um fluxo do Power Automate na área de configurações, você deve ser membro do grupo de função Gerenciamento de Riscos Do *Insider* ou Do *Insider Risk Management Admin.* Para editar um fluxo do Power Automate com a opção Gerenciar fluxos do **Power Automate,** você deve ser membro de pelo menos um grupo de funções de gerenciamento de risco interno.

Conclua as seguintes etapas para editar um fluxo do Power Automate:

1. No centro [de conformidade do Microsoft 365,](htttps://compliance.microsoft.com)vá para o gerenciamento de riscos do Insider e selecione as configurações de risco do **Insider** **fluxos**  >  **do Power Automate.** Você também pode acessar a partir das **páginas de** painéis Casos ou Usuários escolhendo **Automatizar o** gerenciamento de   >  **fluxos do Power Automate.**
2. Na página **fluxos do Power Automate,** selecione um fluxo para editar e selecionar **Editar** no menu de controle de fluxo.
3. Selecione as **configurações de re**  >  **elipses para** alterar uma configuração de componente de fluxo ou **re elipses** Excluir para excluir um componente de  >   fluxo.
4. Selecione **Salvar** e **Feche para** concluir a edição do fluxo.

### <a name="delete-a-power-automate-flow"></a>Excluir um fluxo do Power Automate

Para excluir um fluxo, você usará os controles de configurações na solução de gerenciamento de riscos do **Insider** no centro de conformidade  do Microsoft 365 ou na opção Gerenciar **fluxos** do **Power Automate** do controle Automatizado ao trabalhar diretamente nos painéis Casos ou Usuários.  Quando um fluxo é excluído, ele é removido como uma opção para todos os usuários.

Para excluir um fluxo do Power Automate na área de configurações, você deve ser membro do grupo de função Gerenciamento de Riscos Do *Insider* ou Do *Insider Risk Management Admin.* Para excluir um fluxo do Power Automate com a opção Gerenciar fluxos do **Power Automate,** você deve ser membro de pelo menos um grupo de função de gerenciamento de risco interno.

Conclua as seguintes etapas para excluir um fluxo do Power Automate:

1. No centro [de conformidade do Microsoft 365,](htttps://compliance.microsoft.com)vá para o gerenciamento de riscos do Insider e selecione configurações de risco do **Insider** **fluxos**  >  **do Power Automate.** Você também pode acessar a partir das **páginas de** painéis Casos ou Usuários escolhendo **Automatizar o** gerenciamento de   >  **fluxos do Power Automate.**
2. Na página **fluxos do Power Automate,** selecione um fluxo para excluir e selecionar **Excluir** no menu de controle de fluxo.
3. Na caixa de diálogo de confirmação de exclusão, selecione **Excluir** para remover o fluxo ou selecione **Cancelar** para sair da ação de exclusão.

## <a name="microsoft-teams-preview"></a>Microsoft Teams (visualização)

Analistas e investigadores de conformidade podem facilmente usar o Microsoft Teams para colaboração em casos de gerenciamento de riscos insider. Eles podem coordenar e se comunicar com outros participantes no Microsoft Teams para:

- Coordenar e revisar as atividades de resposta para casos em canais privados do Teams
- Compartilhar e armazenar arquivos e evidências com segurança relacionados a casos individuais
- Acompanhar e analisar as atividades de resposta de analistas e investigadores

Depois que o Microsoft Teams é habilitado para gerenciamento de riscos insider, uma equipe dedicada do Microsoft Teams é criada sempre que um alerta é confirmado e um caso é criado. Por padrão, a equipe inclui automaticamente todos os membros dos grupos de funções *Insider Risk Management*, *Insider Risk Management Analysts* e *Insider Risk Management Investigators* (até 100 usuários iniciais). Colaboradores adicionais da organização podem ser adicionados à equipe após sua criação e conforme apropriado. Para casos existentes criados antes da habilitação do Microsoft Teams, analistas e investigadores podem optar por criar uma nova equipe do Microsoft Teams ao trabalhar em um caso, se necessário.  Depois de resolver o caso associado no gerenciamento de riscos insider, a equipe é automaticamente arquivada (movida para oculto e somente leitura).

Para obter mais informações sobre como usar equipes e canais no Microsoft Teams, consulte Visão geral de equipes e [canais no Microsoft Teams.](/MicrosoftTeams/teams-channels-overview)

A habilitação do suporte do Microsoft Teams para casos é rápida e fácil de configurar. Para habilitar o Microsoft Teams para gerenciamento de riscos insider, conclua as seguintes etapas:

1. No centro [de conformidade do Microsoft 365,](htttps://compliance.microsoft.com)vá para As configurações de risco do **Insider management**  >  **Insider.**
2. Selecione a **guia Microsoft Teams.**
3. Habilitar a integração do Microsoft Teams para o gerenciamento de riscos interno.
4. Selecione **Salvar** para configurar e sair.

### <a name="create-a-microsoft-teams-team-for-existing-cases"></a>Criar uma equipe do Microsoft Teams para casos existentes

Se você habilitar o suporte do Microsoft Teams para gerenciamento de riscos insider após ter casos existentes, precisará criar manualmente uma equipe para cada caso, conforme necessário. Depois de habilear o suporte do Microsoft Teams nas configurações de gerenciamento de riscos, os novos casos criarão automaticamente uma nova equipe do Microsoft Teams.

Os usuários precisam de permissão para criar grupos do Microsoft 365 em sua organização para criar uma equipe do Microsoft Teams a partir de uma ocorrência. Para obter mais informações sobre como gerenciar permissões para Grupos do Microsoft 365, confira [Gerenciar quem pode criar Grupos do Microsoft 365.](/microsoft-365/solutions/manage-creation-of-groups)

Para criar uma equipe para uma ocorrência, você usará o controle Criar Equipe da Microsoft ao trabalhar diretamente em um caso existente. Conclua as seguintes etapas para criar uma nova equipe:

1. No centro [de conformidade do Microsoft 365,](htttps://compliance.microsoft.com)vá para Casos de gerenciamento de riscos do **Insider**  >   e selecione um caso existente.
2. No menu de ação de caso, selecione **Criar Equipe da Microsoft.**
3. No campo **Nome da** Equipe, insira um nome para a nova equipe do Microsoft Teams.
4. Selecione **Criar equipe da Microsoft** e, em seguida, **Fechar.**

Dependendo do número de usuários atribuídos a grupos de função de gerenciamento de riscos insider, pode levar 15 minutos para que todos os investigadores e analistas sejam adicionados à equipe do Microsoft Teams para um caso.
