---
title: Faça ações de resposta em um dispositivo no Microsoft Defender para endpoint
description: Tome ações de resposta em um dispositivo, como isolar dispositivos, coletar um pacote de investigação, gerenciar tags, executar a varredura av e restringir a execução de aplicativos.
keywords: responder, isolar, isolar dispositivo, coletar pacote de investigação, centro de ação, restringir, gerenciar tags, av scan, restringir aplicativo
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
ms.openlocfilehash: ae8b08ce3d5bcc34e91f031223108fca053348ce
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572388"
---
# <a name="take-response-actions-on-a-device"></a>Executar ações de resposta em um dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

>Quer experimentar o Defender for Endpoint? [Inscreva-se para um teste gratuito.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-respondmachine-abovefoldlink) 

Responda rapidamente aos ataques detectados isolando dispositivos ou coletando um pacote de investigação. Depois de agir em dispositivos, você pode verificar detalhes de atividade no centro de Ação.

As ações de resposta são executadas ao longo da parte superior de uma página específica do dispositivo e incluem:

- Gerenciar marcas
- Iniciar investigação automatizada
- Inicie a sessão de resposta ao vivo
- Coletar pacote de investigação
- Executar verificação de antivírus
- Restringir execução de aplicativo
- Dispositivo de isolamento
- Consultar um especialista em ameaças
- Central de ações

[![Imagem de ações ](images/response-actions.png) de resposta](images/response-actions.png#lightbox)

 Você pode encontrar páginas de dispositivos de qualquer uma das seguintes visualizações:

- **Painel de operações** de segurança - Selecione um nome do dispositivo no cartão de risco.
- **Fila de alertas** - Selecione o nome do dispositivo ao lado do ícone do dispositivo na fila de alertas.
- **Lista de dispositivos** - Selecione o título do nome do dispositivo na lista de dispositivos.
- **Caixa de** pesquisa - Selecione Dispositivo no menu suspenso e digite o nome do dispositivo.

>[!IMPORTANT]
> - Essas ações de resposta só estão disponíveis para dispositivos em Windows 10, versão 1703 ou posterior. 
> - Para plataformas não Windows, os recursos de resposta (como o isolamento do dispositivo) dependem dos recursos de terceiros.

## <a name="manage-tags"></a>Gerenciar marcas

Adicione ou gerencie tags para criar uma afiliação lógico em grupo. As tags do dispositivo suportam o mapeamento adequado da rede, permitindo que você conecte diferentes tags para capturar o contexto e para permitir a criação de listas dinâmicas como parte de um incidente.

Para obter mais informações sobre a marcação do dispositivo, consulte [Criar e gerenciar tags de dispositivo](machine-tags.md).

## <a name="initiate-automated-investigation"></a>Iniciar investigação automatizada

Você pode iniciar uma nova investigação automatizada de propósito geral no dispositivo, se necessário. Enquanto uma investigação estiver em andamento, qualquer outro alerta gerado a partir do dispositivo será adicionado a uma investigação automatizada em andamento até que essa investigação seja concluída. Além disso, se a mesma ameaça for vista em outros dispositivos, esses dispositivos são adicionados à investigação.

Para obter mais informações sobre investigações automatizadas, consulte [Visão geral das investigações automatizadas](automated-investigations.md).

## <a name="initiate-live-response-session"></a>Inicie a sessão de resposta ao vivo

A resposta ao vivo é um recurso que lhe dá acesso instantâneo a um dispositivo usando uma conexão remota de shell. Isso lhe dá o poder de fazer um trabalho investigativo aprofundado e tomar ações de resposta imediata para conter prontamente ameaças identificadas — em tempo real.

A resposta ao vivo foi projetada para melhorar as investigações, permitindo que você colete dados forenses, execute scripts, envie entidades suspeitas para análise, remediar ameaças e caçar proativamente ameaças emergentes.

Para obter mais informações sobre resposta ao vivo, consulte [Investigar entidades em dispositivos que usam resposta ao vivo](live-response.md).

## <a name="collect-investigation-package-from-devices"></a>Coletar pacote de investigação de dispositivos

Como parte do processo de investigação ou resposta, você pode coletar um pacote de investigação de um dispositivo. Ao coletar o pacote de investigação, você pode identificar o estado atual do dispositivo e entender melhor as ferramentas e técnicas utilizadas pelo invasor.

Para baixar o pacote (arquivo Zip) e investigar os eventos ocorridos em um dispositivo

1. Selecione Coletar pacote de **investigação** da linha de ações de resposta na parte superior da página do dispositivo.
2. Especifique na caixa de texto por que deseja executar essa ação. Selecione **Confirmar**.
3. O arquivo zip será baixado

Forma alternativa:

1. Selecione O centro de **ação** na seção ações de resposta da página do dispositivo.

    ![Imagem do botão central de ação](images/action-center-package-collection.png)

3. No fly-out do centro de ação, selecione **Pacote de coleta disponível** para baixar o arquivo zip.
  
    ![Imagem do botão do pacote de download](images/collect-package.png)

O pacote contém as seguintes pastas:

| Pasta | Descrição |
|:---|:---------|
|Autoruns | Contém um conjunto de arquivos que representam o conteúdo do registro de um ponto de entrada de início automático conhecido (ASEP) para ajudar a identificar a persistência do invasor no dispositivo. </br></br> <div class="alert"><b>NOTA:</b> Se a chave de registro não for encontrada, o arquivo conterá a seguinte mensagem: "ERRO: O sistema não conseguiu encontrar a chave ou o valor do registro especificado."</div>                                                                                                                                |
|Programas instalados | Este arquivo .CSV contém a lista de programas instalados que podem ajudar a identificar o que está instalado atualmente no dispositivo. Para obter mais informações, consulte [Win32_Product classe](https://go.microsoft.com/fwlink/?linkid=841509).                                                                                  |
|Conexões de rede | Esta pasta contém um conjunto de pontos de dados relacionados às informações de conectividade que podem ajudar na identificação da conectividade com URLs suspeitos, infraestrutura de comando e controle do atacante (C&C), qualquer movimento lateral ou conexões remotas.</br></br> - ActiveNetConnections.txt – Exibe estatísticas de protocolo e conexões atuais de rede TCP/IP. Fornece a capacidade de procurar conectividade suspeita feita por um processo. </br></br> - Arp.txt – Exibe as tabelas de cache ARP (Resolution Protocol) atual do protocolo de resolução de endereços para todas as interfaces. </br></br> O cache ARP pode revelar hosts adicionais em uma rede que foram comprometidas ou sistemas suspeitos na rede que podem ter sido usados para executar um ataque interno.</br></br> - DnsCache.txt - Exibe o conteúdo do cache de resolução do cliente DNS, que inclui tanto entradas pré-carregadas do arquivo hosts local quanto quaisquer registros de recursos obtidos recentemente para consultas de nome resolvidas pelo computador. Isso pode ajudar na identificação de conexões suspeitas. </br></br> - IpConfig.txt – Exibe a configuração TCP/IP completa para todos os adaptadores. Os adaptadores podem representar interfaces físicas, como adaptadores de rede instalados ou interfaces lógicas, como conexões dial-up. </br></br> - FirewallExecutionLog.txt e pfirewall.log                                                                                  |
| Arquivos pré-detch| Windows Os arquivos Prefetch são projetados para acelerar o processo de inicialização do aplicativo. Ele pode ser usado para rastrear todos os arquivos usados recentemente no sistema e encontrar traços para aplicativos que podem ter sido excluídos, mas ainda podem ser encontrados na lista de arquivos pré-dispositivos. </br></br> - Pasta Pré-fer – Contém uma cópia dos arquivos pré-detch de `%SystemRoot%\Prefetch` . NOTA: Sugere-se baixar um visualizador de arquivos pré-visualização para visualizar os arquivos pré-visualização. </br></br> - PrefetchFilesList.txt – Contém a lista de todos os arquivos copiados que podem ser usados para rastrear se houver alguma falha de cópia na pasta pré-inicial.                                                                                                      |
| Processos| Contém um arquivo .CSV listando os processos em execução, o que fornece a capacidade de identificar processos atuais em execução no dispositivo. Isso pode ser útil ao identificar um processo suspeito e seu estado.                                                                                                                                                                                                       |
| Tarefas programadas| Contém um arquivo .CSV listando as tarefas programadas, que podem ser usadas para identificar rotinas executadas automaticamente em um dispositivo escolhido para procurar um código suspeito que foi definido para ser executado automaticamente.                                                                                                                                                                                                      |
| Registro de eventos de segurança| Contém o registro de eventos de segurança, que contém registros de atividades de login ou logout, ou outros eventos relacionados à segurança especificados pela política de auditoria do sistema. </br></br><div class="alert"><b>NOTA:</b> Abra o arquivo de registro de eventos usando o visualizador de eventos.</div>                                                                                    |
| Serviços| Contém um arquivo .CSV que lista serviços e seus estados.                                                                                      |
| Windows Sessões de SMB (Server Message Block, bloco de mensagens do servidor) | Listas de acesso compartilhado a arquivos, impressoras e portas seriais e comunicações diversas entre nós em uma rede. Isso pode ajudar a identificar exfiltração de dados ou movimento lateral. </br></br> Contém arquivos para Sessões SMBInbound e SMBOutboundSession. </br></br> <div class="alert"><b>NOTA:</b> Se não houver sessões (entrada ou saída), você receberá um arquivo de texto que lhe diz que não há sessões SMB encontradas.</div>                                                                                                                          |
| Informações do Sistema| Contém um arquivo SystemInformation.txt que lista informações do sistema, como versão do sistema e cartões de rede.                                                                                     |
| Diretórios temporários| Contém um conjunto de arquivos de texto que lista os arquivos localizados em %Temp% para cada usuário no sistema. </br></br> Isso pode ajudar a rastrear arquivos suspeitos que um invasor pode ter deixado cair no sistema. </br></br> <div class="alert"><b>NOTA:</b> Se o arquivo contiver a seguinte mensagem: "O sistema não pode encontrar o caminho especificado", significa que não há diretório temporário para este usuário, e pode ser porque o usuário não fez login no sistema.</div>                                                                                                                                         |
| Usuários e grupos| Fornece uma lista de arquivos que cada um representa um grupo e seus membros.                                                                                                                   |
|WdSupportLogs| Fornece o MpCmdRunLog.txt e MPSupportFiles.cab  </br></br> <div class="alert"><b>NOTA:</b> Esta pasta só será criada em Windows 10, versão 1709 ou posterior com o rollup de atualização de fevereiro de 2020 ou mais recente instalado:</br> Win10 1709 (RS3) Build 16299.1717 : [KB4537816](https://support.microsoft.com/en-us/help/4537816/windows-10-update-kb4537816) </br> Win10 1803 (RS4) Build 17134.1345 : [KB4537795](https://support.microsoft.com/en-us/help/4537795/windows-10-update-kb4537795) </br> Win10 1809 (RS5) Build 17763.1075 : [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818) </br> Win10 1903/1909 (19h1/19h2) Construa 18362.693 e 18363.693 : [KB4535996](https://support.microsoft.com/en-us/help/4535996/windows-10-update-kb4535996) </div>                                                                                                                    |
| CollectionSummaryReport.xls| Este arquivo é um resumo da coleta do pacote de investigação, contém a lista de pontos de dados, o comando usado para extrair os dados, o status de execução e o código de erro em caso de falha. Você pode usar este relatório para rastrear se o pacote incluir todos os dados esperados e identificar se houve algum erro. |

## <a name="run-microsoft-defender-antivirus-scan-on-devices"></a>Executar Microsoft Defender Antivírus digitalização em dispositivos

Como parte do processo de investigação ou resposta, você pode iniciar remotamente uma varredura antivírus para ajudar a identificar e remediar malwares que podem estar presentes em um dispositivo comprometido.

>[!IMPORTANT]
>- Esta ação está disponível para dispositivos em Windows 10, versão 1709 ou posterior.
>- Uma varredura Microsoft Defender Antivírus (Microsoft Defender AV) pode ser executada juntamente com outras soluções antivírus, quer o Microsoft Defender AV seja a solução antivírus ativa ou não. O Microsoft Defender AV pode estar no modo Passivo. Para obter mais informações, consulte [Microsoft Defender Antivírus compatibilidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility.md).

Uma que você selecionou **Executar a varredura antivírus,** selecione o tipo de varredura que você gostaria de executar (rápida ou completa) e adicione um comentário antes de confirmar a varredura.

![Imagem de notificação para selecionar varredura rápida ou varredura completa e adicionar comentário](images/run-antivirus.png)

O centro de ação mostrará as informações de digitalização e a linha do tempo do dispositivo incluirá um novo evento, refletindo que uma ação de varredura foi submetida no dispositivo. Os alertas do Microsoft Defender AV refletirão quaisquer detecções que vieram à tona durante a varredura.

>[!NOTE]
>Ao acionar uma varredura usando a ação de resposta do Defender para endpoint, o valor do antivírus 'ScanAvgCPULoadFactor' do Microsoft Defender ainda se aplica e limita o impacto da CPU da varredura.<br> Se o ScanAvgCPULoadFactor não estiver configurado, o valor padrão será um limite de carga máxima de CPU de 50% durante uma varredura.<br>
>Para obter mais informações, consulte [configuração-advanced-scan-types-microsoft-defender-antivírus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-advanced-scan-types-microsoft-defender-antivirus).

## <a name="restrict-app-execution"></a>Restringir execução de aplicativo

Além de conter um ataque parando processos maliciosos, você também pode bloquear um dispositivo e impedir que tentativas subsequentes de programas potencialmente maliciosos sejam executados.

>[!IMPORTANT]
> - Esta ação está disponível para dispositivos em Windows 10, versão 1709 ou posterior.
> - Esse recurso estará disponível se sua organização usar Microsoft Defender Antivírus.
> - Essa ação precisa atender aos formatos de política de integridade do código de controle de aplicativos Windows Defender e aos requisitos de assinatura. Para obter mais informações, consulte [formatos de política de integridade do Código e assinatura](https://docs.microsoft.com/windows/device-security/device-guard/requirements-and-deployment-planning-guidelines-for-device-guard#code-integrity-policy-formats-and-signing).

Para restringir a execução de um aplicativo, é aplicada uma política de integridade de código que só permite que os arquivos sejam executados se forem assinados por um certificado emitido pela Microsoft. Esse método de restrição pode ajudar a impedir que um invasor controle dispositivos comprometidos e realize outras atividades maliciosas.

>[!NOTE]
>Você poderá reverter a restrição de aplicações de execução a qualquer momento. O botão na página do dispositivo mudará para dizer **Remover restrições** de aplicativos, e então você tomará as mesmas medidas que restringir a execução do aplicativo.

Depois de selecionar Restringir a **execução** do aplicativo na página do dispositivo, digite um comentário e selecione **Confirmar**. O centro de ação mostrará as informações de digitalização e a linha do tempo do dispositivo incluirá um novo evento.

![Imagem da notificação de restrição de aplicativos](images/restrict-app-execution.png)

**Notificação no usuário do dispositivo:**</br>
Quando um aplicativo é restrito, a seguinte notificação é exibida para informar o usuário que um aplicativo está sendo impedido de ser executado:

![Imagem de restrição de aplicativos](images/atp-app-restriction.png)

## <a name="isolate-devices-from-the-network"></a>Isolar dispositivos da rede

Dependendo da gravidade do ataque e da sensibilidade do dispositivo, você pode querer isolar o dispositivo da rede. Essa ação pode ajudar a impedir que o invasor controle o dispositivo comprometido e realize outras atividades, como exfiltração de dados e movimento lateral.

>[!IMPORTANT]
>- Isolamento total está disponível para dispositivos em Windows 10, versão 1703.
>- Isolamento seletivo está disponível para dispositivos em Windows 10, versão 1709 ou posterior.
>- Ao isolar um dispositivo, apenas certos processos e destinos são permitidos. Portanto, os dispositivos que estão por trás de um túnel VPN completo não serão capazes de alcançar o serviço de nuvem Microsoft Defender para Endpoint depois que o dispositivo for isolado. Recomendamos o uso de uma VPN de tunelamento dividido para o Microsoft Defender para endpoint e Microsoft Defender Antivírus tráfego relacionado à proteção baseado em nuvem.

Este recurso de isolamento do dispositivo desconecta o dispositivo comprometido da rede, mantendo a conectividade com o serviço Defender for Endpoint, que continua monitorando o dispositivo.

No Windows 10, versão 1709 ou posterior, você terá controle adicional sobre o nível de isolamento da rede. Você também pode optar por habilitar Outlook, Microsoft Teams e Skype for Business conectividade (também conhecido como 'Isolamento Seletivo').

>[!NOTE]
>Você poderá reconectar o dispositivo de volta à rede a qualquer momento. O botão na página do dispositivo será trocado para dizer **Liberar do isolamento**, e então você tomará os mesmos passos que isolar o dispositivo.

Depois de selecionar **o dispositivo Isolado** na página do dispositivo, digite um comentário e selecione **Confirmar**. O centro de ação mostrará as informações de digitalização e a linha do tempo do dispositivo incluirá um novo evento.

![Imagem do dispositivo isolado](images/isolate-device.png)

>[!NOTE]
>O dispositivo permanecerá conectado ao serviço Defender for Endpoint mesmo que esteja isolado da rede. Se você optou por ativar Outlook e Skype for Business comunicação, então você poderá se comunicar com o usuário enquanto o dispositivo estiver isolado.

**Notificação no usuário do dispositivo:**</br>
Quando um dispositivo está sendo isolado, a seguinte notificação é exibida para informar o usuário que o dispositivo está sendo isolado da rede:

![Imagem sem conexão de rede](images/atp-notification-isolate.png)

## <a name="consult-a-threat-expert"></a>Consultar um especialista em ameaças

Você pode consultar um especialista em ameaças da Microsoft para obter mais informações sobre um dispositivo potencialmente comprometido ou já comprometido. Especialistas em Ameaças da Microsoft podem ser contratados diretamente de dentro do Central de Segurança do Microsoft Defender para uma resposta oportuna e precisa. Os especialistas fornecem insights não apenas sobre um dispositivo potencialmente comprometido, mas também para entender melhor ameaças complexas, notificações de ataque direcionadas que você recebe ou se você precisa de mais informações sobre os alertas ou um contexto de inteligência de ameaças que você vê no painel do portal.

Consulte [consulte consultar um especialista em ameaças da Microsoft](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) para obter detalhes.


## <a name="check-activity-details-in-action-center"></a>Verificar detalhes de atividade na Central de ações

O **Centro de Ação** fornece informações sobre ações que foram tomadas em um dispositivo ou arquivo. Você poderá visualizar os seguintes detalhes:

- Coleta de pacotes de investigação
- Varredura antivírus
- Restrição de aplicativos
- Isolamento do dispositivo

Todos os outros detalhes relacionados também são mostrados, por exemplo, data/hora de envio, envio do usuário e se a ação foi bem sucedida ou falhada.

![Imagem do centro de ação com informações](images/action-center-details.png)

## <a name="related-topic"></a>Tópicos relacionados
- [Executar ações de resposta em um arquivo](respond-file-alerts.md)
- [Relatar imprecisão](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation#report-inaccuracy)
