---
title: Tomar ações de resposta em um arquivo no Microsoft Defender para Ponto de Extremidade
description: Tome ações de resposta em alertas relacionados a arquivos interrompendo e quarantindo um arquivo ou bloqueando um arquivo e verificando detalhes da atividade.
keywords: responder, parar e colocar em quarentena, bloquear arquivo, análise profunda
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: ba48adcf93c5b768b2280729b33a1a7d361919cb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053893"
---
# <a name="take-response-actions-on-a-file"></a>Tomar ações de resposta em um arquivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-responddile-abovefoldlink)

Responda rapidamente a ataques detectados interrompendo e quarantindo arquivos ou bloqueando um arquivo. Depois de tomar medidas em arquivos, você pode verificar os detalhes da atividade na Central de Ações.

As ações de resposta estão disponíveis na página de perfil detalhada de um arquivo. Uma vez nesta página, você pode alternar entre os layouts de página novo e **antigo,** alternando a nova página Arquivo . O restante deste artigo descreve o layout da página mais recente.

As ações de resposta são executados ao longo da parte superior da página de arquivo e incluem:

- Arquivo Stop and Quarantine
- Adicionar Indicador
- Baixar o arquivo
- Consultar um especialista em ameaças
- Central de ações

Você também pode enviar arquivos para análise profunda, para executar o arquivo em uma área de segurança na nuvem. Quando a análise for concluída, você obterá um relatório detalhado que fornece informações sobre o comportamento do arquivo. Você pode enviar arquivos para análise profunda e ler relatórios passados selecionando a **guia Análise** Profunda. Ele está localizado abaixo dos cartões de informações de arquivo.

Algumas ações exigem certas permissões. A tabela a seguir descreve qual ação determinadas permissões podem executar em arquivos executáveis portáteis (PE) e não PE:

| Permissão             | Arquivos PE | Arquivos não PE |
| :--------------------- | :------: | :----------: |
| Exibir dados              |     X    |       X      |
| Investigação de alertas   | &#x2611; |       X      |
| Base de resposta ao vivo    |     X    |       X      |
| Resposta ao vivo avançada | &#x2611; |   &#x2611;   |

Para obter mais informações sobre funções, consulte [Create and manage roles for role-based access control](user-roles.md).

## <a name="stop-and-quarantine-files-in-your-network"></a>Parar e colocar arquivos em quarentena em sua rede

Você pode conter um ataque em sua organização interrompendo o processo mal-intencionado e colocando em quarentena o arquivo onde ele foi observado.

> [!IMPORTANT]
> Você só poderá fazer essa ação se:
>
> - O dispositivo em que você está executando a ação está executando o Windows 10, versão 1703 ou posterior
> - O arquivo não pertence a editores confiáveis de terceiros ou não assinado pela Microsoft
> - O Microsoft Defender Antivírus deve pelo menos estar em execução no modo Passivo. Para obter mais informações, consulte [compatibilidade do Microsoft Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).

A **ação Stop and Quarantine File** inclui interromper a execução de processos, colocar em quarentena os arquivos e excluir dados persistentes, como chaves do Registro.

Essa ação entra em vigor em dispositivos com Windows 10, versão 1703 ou posterior, onde o arquivo foi observado nos últimos 30 dias.

> [!NOTE]
> Você poderá restaurar o arquivo da quarentena a qualquer momento.

### <a name="stop-and-quarantine-files"></a>Arquivos de parada e quarentena

1. Selecione o arquivo que você deseja parar e colocar em quarentena. Você pode selecionar um arquivo de qualquer uma das seguintes exibições ou usar a caixa Pesquisar:

   - **Alertas** - clique nos links correspondentes da descrição ou detalhes na linha do tempo do artefato
   - **Caixa de** pesquisa - selecione **Arquivo** no menu suspenso e insira o nome do arquivo

   > [!NOTE]
   > A ação de arquivo de parada e quarentena está limitada a um máximo de 1000 dispositivos. Para parar um arquivo em um número maior de dispositivos, consulte [Adicionar indicador para bloquear ou permitir arquivo](#add-indicator-to-block-or-allow-a-file).

2. Vá para a barra superior e selecione **Parar e Quarentena Arquivo**.

   ![Imagem da ação de arquivo de parada e quarentena](images/atp-stop-quarantine-file.png)

3. Especifique um motivo e selecione **Confirmar**.

   ![Imagem da janela modal de arquivo de parada e quarentena](images/atp-stop-quarantine.png)

   O Centro de Ações mostra as informações de envio:
   
   ![Imagem do centro de ações de arquivo de parada e quarentena](images/atp-stopnquarantine-file.png)

   - **Hora do envio** - Mostra quando a ação foi enviada.
   - **Sucesso** - Mostra o número de dispositivos em que o arquivo foi interrompido e colocado em quarentena.
   - **Falha** - Mostra o número de dispositivos em que a ação falhou e detalhes sobre a falha.
   - **Pendente** - Mostra o número de dispositivos de onde o arquivo ainda deve ser interrompido e colocado em quarentena. Isso pode levar tempo para casos em que o dispositivo está offline ou não está conectado à rede.

4. Selecione qualquer um dos indicadores de status para exibir mais informações sobre a ação. Por exemplo, selecione **Falha** ao ver onde a ação falhou.

**Notificação no usuário do dispositivo**:</br>
Quando o arquivo está sendo removido de um dispositivo, a seguinte notificação é mostrada:

![Imagem de notificação no usuário do dispositivo](images/atp-notification-file.png)

Na linha do tempo do dispositivo, um novo evento é adicionado para cada dispositivo onde um arquivo foi interrompido e colocado em quarentena.

Um aviso é mostrado antes da ação ser implementada para arquivos amplamente usados em toda uma organização. É para validar se a operação se destina.

## <a name="restore-file-from-quarantine"></a>Restaurar arquivo da quarentena

Você pode reverter e remover um arquivo da quarentena se tiver determinado que ele está limpo após uma investigação. Execute o seguinte comando em cada dispositivo em que o arquivo foi colocado em quarentena.

1. Abra um prompt de linha de comando elevada no dispositivo:

   1. Vá para **Iniciar** e digite _cmd_.

   1. Clique com o botão **direito do mouse no prompt de comando** e selecione Executar como **administrador**.

2. Insira o seguinte comando e pressione **Enter**:

   ```powershell
   “%ProgramFiles%\Windows Defender\MpCmdRun.exe” –Restore –Name EUS:Win32/CustomEnterpriseBlock –All
   ```

> [!NOTE]
> Em alguns cenários, **o ThreatName** pode aparecer como: EUS:Win32/CustomEnterpriseBlock!cl.
>
> O Defender for Endpoint restaurará todos os arquivos bloqueados personalizados que foram colocados em quarentena neste dispositivo nos últimos 30 dias.

> [!IMPORTANT]
> Um arquivo que foi colocado em quarentena como uma possível ameaça de rede pode não ser recuperável. Se um usuário tentar restaurar o arquivo após a quarentena, esse arquivo pode não estar acessível. Isso pode ser devido ao sistema não ter mais credenciais de rede para acessar o arquivo. Normalmente, isso é resultado de um logoff temporário em um sistema ou pasta compartilhada e os tokens de acesso expiraram.

## <a name="download-or-collect-file"></a>Baixar ou coletar arquivo

Selecionar **Baixar arquivo** das ações de resposta permite baixar um arquivo .zip local protegido por senha que contém seu arquivo. Um flyout aparecerá onde você pode gravar um motivo para baixar o arquivo e definir uma senha.

Por padrão, você não poderá baixar arquivos que estão em quarentena.

![Imagem da ação de arquivo de download](images/atp-download-file-action.png)

### <a name="collect-files"></a>Coletar arquivos

Se um arquivo ainda não estiver armazenado pelo Microsoft Defender para Ponto de Extremidade, você não poderá baixá-lo. Em vez disso, você verá um botão **Coletar arquivo** no mesmo local. Se um arquivo não tiver sido visto na organização nos últimos 30 dias, **Coletar arquivo** será desabilitado.
> [!Important]
> Um arquivo que foi colocado em quarentena como uma possível ameaça de rede pode não ser recuperável. Se um usuário tentar restaurar o arquivo após a quarentena, esse arquivo pode não estar acessível. Isso pode ser devido ao sistema não ter mais credenciais de rede para acessar o arquivo. Normalmente, isso é resultado de um logoff temporário em um sistema ou pasta compartilhada e os tokens de acesso expiraram.

## <a name="add-indicator-to-block-or-allow-a-file"></a>Adicionar indicador para bloquear ou permitir um arquivo

Impedir a propagação de um ataque em sua organização proibindo arquivos potencialmente mal-intencionados ou malwares suspeitos. Se você conhecer um arquivo executável portátil potencialmente mal-intencionado (PE), poderá bloqueá-lo. Essa operação impedirá que ela seja lida, escrita ou executada em dispositivos em sua organização.

> [!IMPORTANT]
>
> - Esse recurso estará disponível se sua organização usar o Microsoft Defender Antivírus e a proteção entregue na nuvem estiver habilitada. Para obter mais informações, consulte [Manage cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).
>
> - A versão do cliente Antimalware deve ser 4.18.1901.x ou posterior.
> - Esse recurso foi projetado para impedir que o malware suspeito (ou arquivos potencialmente mal-intencionados) seja baixado da Web. Atualmente, ele dá suporte a arquivos executáveis portáteis (PE), incluindo _arquivos .exe_ e _.dll._ A cobertura será estendida ao longo do tempo.
> - Essa ação de resposta está disponível para dispositivos no Windows 10, versão 1703 ou posterior.
> - A função permitir ou bloquear não poderá ser feita em arquivos se a classificação do arquivo existir no cache do dispositivo antes da ação permitir ou bloquear.

> [!NOTE]
> O arquivo PE precisa estar na linha do tempo do dispositivo para que você possa tomar essa ação.
>
> Pode haver alguns minutos de latência entre o momento em que a ação é realizada e o arquivo real que está sendo bloqueado.

### <a name="enable-the-block-file-feature"></a>Habilitar o recurso de arquivo de bloqueio

Para começar a bloquear arquivos, primeiro você precisa ativar o [ **recurso Bloquear ou** permitir](advanced-features.md) em Configurações.
### <a name="allow-or-block-file"></a>Permitir ou bloquear arquivo

Quando você adiciona um hash de indicador para um arquivo, você pode optar por levantar um alerta e bloquear o arquivo sempre que um dispositivo em sua organização tentar execute-o.

Os arquivos bloqueados automaticamente por um indicador não aparecerão no Centro de Ações do arquivo, mas os alertas ainda estarão visíveis na fila alertas.

Consulte [gerenciar indicadores](manage-indicators.md) para obter mais detalhes sobre como bloquear e levantar alertas em arquivos.

Para parar de bloquear um arquivo, remova o indicador. Você pode fazer isso por meio da ação **Editar Indicador** na página de perfil do arquivo. Essa ação ficará visível na mesma posição que a ação **Adicionar Indicador,** antes de adicionar o indicador.

Você também pode editar indicadores da página **Configurações,** em **Indicadores de**  >  **Regras.** Os indicadores são listados nesta área pelo hash do arquivo.

## <a name="consult-a-threat-expert"></a>Consultar um especialista em ameaças

Consulte um especialista em ameaças da Microsoft para obter mais informações sobre um dispositivo potencialmente comprometido ou dispositivos já comprometidos. Os Especialistas em Ameaças da Microsoft são contratados diretamente de dentro do Centro de Segurança do Microsoft Defender para resposta o tempo e a precisão. Os especialistas fornecem informações sobre um dispositivo potencialmente comprometido e ajudam você a entender ameaças complexas e notificações de ataque direcionadas. Eles também podem fornecer informações sobre os alertas ou um contexto de inteligência contra ameaças que você vê no painel do portal.

Consulte [Consult a Microsoft Threat Expert](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) para obter detalhes.

## <a name="check-activity-details-in-action-center"></a>Verificar detalhes da atividade no Centro de ações

A **Central de Ações** fornece informações sobre ações que foram realizadas em um dispositivo ou arquivo. Você pode exibir os seguintes detalhes:

- Conjunto de pacotes de investigação
- Verificação de antivírus
- Restrição de aplicativo
- Isolamento de dispositivo

Todos os outros detalhes relacionados também são mostrados, como data/hora do envio, envio do usuário e se a ação foi bem-sucedida ou falhou.

![Imagem do centro de ações com informações](images/action-center-details.png)

## <a name="deep-analysis"></a>Análise profunda

As investigações de segurança cibernética geralmente são disparadas por um alerta. Os alertas estão relacionados a um ou mais arquivos observados que geralmente são novos ou desconhecidos. Selecionar um arquivo o leva ao exibição de arquivo onde você pode ver os metadados do arquivo. Para enriquecer os dados relacionados ao arquivo, você pode enviar o arquivo para análise profunda.

O recurso análise profunda executa um arquivo em um ambiente de nuvem seguro e totalmente instrumentado. Os resultados da análise profunda mostram as atividades do arquivo, comportamentos observados e artefatos associados, como arquivos descartados, modificações do registro e comunicação com IPs.
A análise profunda atualmente dá suporte à análise extensiva de arquivos executáveis portáteis (PE) (incluindo _arquivos .exe_ e _.dll)._

A análise profunda de um arquivo leva vários minutos. Depois que a análise de arquivo for concluída, a guia Análise Profunda será atualizada para exibir um resumo e a data e a hora dos resultados disponíveis mais recentes.

O resumo de análise profunda inclui uma lista de *comportamentos observados*, alguns dos quais podem indicar atividades mal-intencionadas e observáveis, incluindo IPs contatados e arquivos criados no disco. Se nada foi encontrado, essas seções exibirão uma breve mensagem.

Os resultados de uma análise profunda são coincidedos com a inteligência contra ameaças e qualquer combinação gerará alertas apropriados.

Use o recurso de análise profunda para investigar os detalhes de qualquer arquivo, geralmente durante uma investigação de um alerta ou por qualquer outro motivo em que você suspeita de comportamento mal-intencionado. Esse recurso está disponível na guia **Análise Profunda,** na página de perfil do arquivo.<br/>
<br/>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4aAYy?rel=0]

**Enviar** para análise profunda é habilitado quando o arquivo está disponível na coleção de exemplos de back-end endpoint do Defender for Endpoint ou se foi observado em um dispositivo Windows 10 que dá suporte ao envio para análise profunda.

> [!NOTE]
> Somente arquivos do Windows 10 podem ser coletados automaticamente.

Você também pode enviar um exemplo por meio do Portal da Central de Segurança da [Microsoft](https://www.microsoft.com/security/portal/submission/submit.aspx) se o arquivo não foi observado em um dispositivo Windows 10 e aguardar que o botão **Enviar** para análise profunda se torne disponível.

> [!NOTE]
> Devido aos fluxos de processamento de back-end no Portal do Centro de Segurança da Microsoft, pode haver até 10 minutos de latência entre o envio de arquivos e a disponibilidade do recurso de análise profunda no Defender para Ponto de Extremidade.

Quando o exemplo é coletado, o Defender for Endpoint executa o arquivo em um ambiente seguro. Em seguida, ele cria um relatório detalhado de comportamentos observados e artefatos associados, como arquivos descartados em dispositivos, comunicação com IPs e modificações do Registro.

### <a name="submit-files-for-deep-analysis"></a>Enviar arquivos para análise profunda

1. Selecione o arquivo que você deseja enviar para análise profunda. Você pode selecionar ou pesquisar um arquivo de qualquer uma das seguintes exibições:

    - Alertas - selecione os links de arquivo na **descrição** ou **detalhes** na linha do tempo do artefato
    - **Lista dispositivos** - selecione os links de arquivo na seção **Descrição** ou **Detalhes** na **seção Dispositivo na** organização
    - Caixa de pesquisa - selecione **Arquivo** no menu suspenso e insira o nome do arquivo

2. Na guia **Análise Profunda** do exibição de arquivo, selecione **Enviar**.

   ![Você só pode enviar arquivos PE na seção detalhes do arquivo](images/submit-file.png)

   > [!NOTE]
   > Somente arquivos PE são suportados, incluindo _arquivos .exe_ e _.dll._

Uma barra de progresso é exibida e fornece informações sobre os diferentes estágios da análise. Em seguida, você pode exibir o relatório quando a análise for feita.

> [!NOTE]
> Dependendo da disponibilidade do dispositivo, o tempo de coleta de amostras pode variar. Há um tempo de tempo de 3 horas para coleta de amostras. A coleção falhará e a operação será anulada se não houver nenhum relatório de dispositivo Windows 10 online no momento. Você pode re-enviar arquivos para análise profunda para obter dados atualizados no arquivo.

### <a name="view-deep-analysis-reports"></a>Exibir relatórios de análise profunda

Exibir o relatório de análise profunda fornecido para ver mais informações detalhadas sobre o arquivo enviado. Esse recurso está disponível no contexto de exibição de arquivo.

Você pode exibir o relatório abrangente que fornece detalhes sobre as seguintes seções:

- Behaviors
- Observables

Os detalhes fornecidos podem ajudá-lo a investigar se há indicações de um possível ataque.

1. Selecione o arquivo enviado para análise profunda.
2. Selecione a **guia Análise profunda.** Se houver relatórios anteriores, o resumo do relatório aparecerá nesta guia.

    ![O relatório de análise profunda mostra informações detalhadas em várias categorias](images/analysis-results-nothing500.png)

#### <a name="troubleshoot-deep-analysis"></a>Solucionar problemas de análise profunda

Se você encontrar um problema ao tentar enviar um arquivo, tente cada uma das etapas de solução de problemas a seguir.

1. Verifique se o arquivo em questão é um arquivo PE. Os arquivos PE geralmente têm _extensões .exe_ ou _.dll_ (programas executáveis ou aplicativos).
2. Verifique se o serviço tem acesso ao arquivo, que ele ainda existe e não foi corrompido ou modificado.
3. Aguarde um pouco e tente enviar o arquivo novamente. A fila pode estar cheia ou houve um erro temporário de conexão ou comunicação.
4. Se a política de coleta de exemplo não estiver configurada, o comportamento padrão é permitir a coleta de amostras. Se estiver configurado, verifique se a configuração de política permite a coleta de amostra antes de enviar o arquivo novamente. Quando a coleção de exemplos estiver configurada, verifique o seguinte valor do Registro:

    ```powershell
    Path: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection
    Name: AllowSampleCollection
    Type: DWORD
    Hexadecimal value :
      Value = 0 – block sample collection
      Value = 1 – allow sample collection
    ```

1. Altere a unidade organizacional por meio da Política de Grupo. Para obter mais informações, consulte [Configure with Group Policy](configure-endpoints-gp.md).
1. Se essas etapas não resolverem o problema, contate [winatp@microsoft.com](mailto:winatp@microsoft.com).

## <a name="related-topics"></a>Tópicos relacionados

- [Tomar ações de resposta em um dispositivo](respond-machine-alerts.md)
- [Investigar arquivos](investigate-files.md)
