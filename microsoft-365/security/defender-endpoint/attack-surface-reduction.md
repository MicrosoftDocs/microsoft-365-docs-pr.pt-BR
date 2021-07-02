---
title: Usar regras de redução da superfície de ataque para evitar a infecção por malware
description: As regras de redução de superfície de ataque podem ajudar a impedir que explorações usem aplicativos e scripts para infectar dispositivos com malware.
keywords: Regras de redução de superfície de ataque, asr, quadris, sistema de prevenção contra invasão de host, regras de proteção, antiexploit, antiexploit, exploração, prevenção de infecção, Microsoft Defender para Ponto de Extremidade
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ed6dc9956c3e78f8ed39dca9cd6bf0421dd28456
ms.sourcegitcommit: 8c6a5db0dab99a82a69dd8a0a7c56af1cb825931
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53276984"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a>Usar regras de redução da superfície de ataque para evitar a infecção por malware

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a>Por que as regras de redução de superfície de ataque são importantes

A superfície de ataque da sua organização inclui todos os locais onde um invasor pode comprometer os dispositivos ou redes da sua organização. Reduzir sua superfície de ataque significa proteger os dispositivos e a rede da sua organização, o que deixa os invasores com menos maneiras de executar ataques. Configurar regras de redução de superfície de ataque no Microsoft Defender para Ponto de Extremidade pode ajudar!

As regras de redução de superfície de ataque visam determinados comportamentos de software, como:

- Iniciando arquivos executáveis e scripts que tentam baixar ou executar arquivos
- Executando scripts ofuscados ou suspeitos
- Executando comportamentos que os aplicativos geralmente não iniciam durante o trabalho normal do dia a dia

Esses comportamentos de software às vezes são vistos em aplicativos legítimos. No entanto, esses comportamentos geralmente são considerados arriscados porque são comumente abusadas por invasores por meio de malware. As regras de redução de superfície de ataque podem restringir comportamentos de risco baseados em software e ajudar a manter sua organização segura.

Para obter mais informações sobre como configurar regras de redução de superfície de ataque, consulte [Enable attack surface reduction rules](enable-attack-surface-reduction.md).

## <a name="assess-rule-impact-before-deployment"></a>Avaliar o impacto da regra antes da implantação

Você pode avaliar como uma regra de redução de superfície de ataque pode afetar sua rede abrindo a recomendação de segurança para essa regra em [Gerenciamento de Ameaças e Vulnerabilidades](/windows/security/threat-protection/#tvm).

:::image type="content" source="images/asrrecommendation.png" alt-text="Reco de segurança para regra de redução de superfície de ataque":::

No painel de detalhes de recomendação, verifique se há impacto do usuário para determinar qual porcentagem de seus dispositivos pode aceitar uma nova política habilitando a regra no modo de bloqueio sem afetar adversamente a produtividade.

Consulte [Requisitos](enable-attack-surface-reduction.md#requirements) no artigo "Habilitar regras de redução de superfície de ataque" para obter informações sobre sistemas operacionais com suporte e informações adicionais sobre requisitos.

## <a name="audit-mode-for-evaluation"></a>Modo de auditoria para avaliação

Use [o modo de auditoria](audit-windows-defender.md) para avaliar como as regras de redução de superfície de ataque afetariam sua organização se habilitadas. Execute todas as regras no modo de auditoria primeiro para que você possa entender como elas afetam seus aplicativos de linha de negócios. Muitos aplicativos de linha de negócios são escritos com preocupações de segurança limitadas e podem executar tarefas de maneiras semelhantes ao malware. Monitorando dados de auditoria e adicionando exclusões para [aplicativos necessários,](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) você pode implantar regras de redução de superfície de ataque sem reduzir a produtividade.

## <a name="warn-mode-for-users"></a>Modo de aviso para usuários

(**NOVO**!) Antes de avisar os recursos do modo, as regras de redução de superfície de ataque que estão habilitadas podem ser definidas para o modo de auditoria ou modo de bloqueio. Com o novo modo de aviso, sempre que o conteúdo é bloqueado por uma regra de redução de superfície de ataque, os usuários veem uma caixa de diálogo que indica que o conteúdo está bloqueado. A caixa de diálogo também oferece ao usuário uma opção para desbloquear o conteúdo. Em seguida, o usuário pode repetir sua ação e a operação é concluída. Quando um usuário desbloqueia o conteúdo, o conteúdo permanece desbloqueado por 24 horas e, em seguida, o bloqueio é retomado.

O modo de aviso ajuda sua organização a ter regras de redução de superfície de ataque em vigor sem impedir que os usuários acessem o conteúdo necessário para executar suas tarefas.

### <a name="requirements-for-warn-mode-to-work"></a>Requisitos para que o modo de aviso funcione

O modo de aviso é suportado em dispositivos que executam as seguintes versões Windows:

- [Windows 10, versão 1809](/windows/whats-new/whats-new-windows-10-version-1809) ou posterior
- [Windows Server, versão 1809](/windows-server/get-started/whats-new-in-windows-server-1809) ou posterior

Microsoft Defender Antivírus deve ser executado com proteção em tempo real no [modo Ativo.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)

Além disso, certifique-se [Microsoft Defender Antivírus e as atualizações de antimalware](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) estão instaladas.

- Requisito mínimo de lançamento da plataforma: `4.18.2008.9`
- Requisito mínimo de versão do mecanismo: `1.1.17400.5`

Para obter mais informações e obter suas atualizações, consulte [Update for Microsoft Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).

### <a name="cases-where-warn-mode-is-not-supported"></a>Casos em que o modo de aviso não é suportado

O modo de aviso não é suportado para três regras de redução de superfície de ataque quando você as configura Microsoft Endpoint Manager. (Se você usar a Política de Grupo para configurar suas regras de redução de superfície de ataque, o modo de aviso será suportado.) As três regras que não suportam o modo de aviso quando você as configura Microsoft Endpoint Manager são as seguinte:

- [Bloquear JavaScript ou VBScript de iniciar conteúdo executável baixado](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d` )
- [Bloquear a persistência por meio da assinatura de evento WMI](#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b` )
- [Usar proteção avançada contra ransomware](#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35` )

Além disso, o modo de aviso não é suportado em dispositivos que executam versões mais antigas Windows. Nesses casos, as regras de redução de superfície de ataque configuradas para executar no modo de aviso serão executados no modo de bloqueio.

## <a name="notifications-and-alerts"></a>Notificações e alertas

Sempre que uma regra de redução de superfície de ataque é disparada, uma notificação é exibida no dispositivo. Você pode [personalizar a notificação](customize-attack-surface-reduction.md#customize-the-notification) com os detalhes da sua empresa e informações de contato.

Além disso, quando determinadas regras de redução de superfície de ataque são disparadas, alertas são gerados.

As notificações e os alertas gerados podem ser exibidos no portal Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) (anteriormente chamado de [Central de Segurança do Microsoft Defender](microsoft-defender-security-center.md)).

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a>Eventos avançados de busca e redução de superfície de ataque

Você pode usar a busca avançada para exibir eventos de redução de superfície de ataque. Para simplificar o volume de dados de entrada, somente processos exclusivos para cada hora podem ser visualizados com busca avançada. O tempo de um evento de redução de superfície de ataque é a primeira vez que esse evento é visto dentro de uma hora.

Por exemplo, suponha que um evento de redução de superfície de ataque ocorra em 10 dispositivos durante a hora das 14:00. Suponha que o primeiro evento ocorreu às 14:15 e o último às 14:45. Com a busca avançada, você verá uma instância desse evento (mesmo que tenha realmente ocorrido em 10 dispositivos) e seu data/hora será 14:15.

Para obter mais informações sobre a busca avançada, consulte [Proativamente procurar ameaças com a busca avançada.](advanced-hunting-overview.md)

## <a name="attack-surface-reduction-features-across-windows-versions"></a>Recursos de redução de superfície de ataque em Windows versões

Você pode definir regras de redução de superfície de ataque para dispositivos que estão executando qualquer uma das seguintes edições e versões de Windows:

- Windows 10 Pro, versão [1709](/windows/whats-new/whats-new-windows-10-version-1709) ou posterior
- Windows 10 Enterprise, versão [1709](/windows/whats-new/whats-new-windows-10-version-1709) ou posterior
- Windows Servidor, [versão 1803 (Canal Semesanuais)](/windows-server/get-started/whats-new-in-windows-server-1803) ou posterior
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Embora as regras de redução de superfície de ataque não exigem uma licença [Windows E5](/windows/deployment/deploy-enterprise-licenses), se você tiver Windows E5, você obterá recursos avançados de gerenciamento. Os recursos avançados - disponíveis apenas no Windows E5 - incluem:

- O monitoramento, análise e fluxos de trabalho disponíveis no [Defender para Ponto de Extremidade](microsoft-defender-endpoint.md)
- Os recursos de relatório e configuração [em Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).

Esses recursos avançados não estão disponíveis com uma licença Windows Professional ou Windows E3. No entanto, se você tiver essas licenças, poderá usar o Visualizador de Eventos e Microsoft Defender Antivírus logs para revisar seus eventos de regra de redução de superfície de ataque.

## <a name="review-attack-surface-reduction-events-in-the-microsoft-365-defender-portal"></a>Revisar eventos de redução de superfície de ataque no portal Microsoft 365 Defender de ataque

O Defender for Endpoint fornece relatórios detalhados de eventos e bloqueios como parte dos cenários de investigação de alerta.

Você pode consultar o Defender para dados de ponto de extremidade [em Microsoft 365 Defender](microsoft-defender-security-center.md) usando a [busca avançada](advanced-hunting-query-language.md). Se você estiver executando o modo [de](audit-windows-defender.md)auditoria, poderá usar a busca avançada para entender como as regras de redução de superfície de ataque podem afetar seu ambiente.

Aqui está um exemplo de consulta:

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Revisar eventos de redução de superfície de ataque Windows Visualizador de Eventos

Você pode revisar o log Windows de eventos para exibir eventos gerados por regras de redução de superfície de ataque:

1. Baixe o [Pacote de Avaliação](https://aka.ms/mp7z2w) e extraia o arquivo *cfa-events.xml* para um local facilmente acessível no dispositivo.

2. Insira as palavras, *Visualizador de* Eventos , na menu Iniciar para abrir o visualizador de eventos Windows de eventos.

3. Em **Ações,** selecione **Importar exibição personalizada...**.

4. Selecione o arquivo *cfa-events.xml* de onde ele foi extraído. Como alternativa, [copie o XML diretamente](event-views.md).

5. Selecione **OK**.

Você pode criar uma exibição personalizada que filtra eventos para mostrar apenas os seguintes eventos, todos relacionados ao acesso controlado a pastas:

|ID do Evento|Descrição|
|---|---|
|5007|Evento quando as configurações são alteradas|
|1121|Evento quando a regra é a disparar no modo de bloqueio|
|1122|Evento quando a regra é a disparar no modo de auditoria|

A "versão do mecanismo" listada para eventos de redução de superfície de ataque no log de eventos é gerada pelo Defender para Ponto de Extremidade, não pelo sistema operacional. O Defender for Endpoint é integrado ao Windows 10, portanto, esse recurso funciona em todos os dispositivos com Windows 10 instalados.

## <a name="attack-surface-reduction-rules"></a>Regras de redução de superfície de ataque

A tabela e as subseções a seguir descrevem cada uma das 16 regras de redução de superfície de ataque. As regras de redução de superfície de ataque são listadas em ordem alfabética, pelo nome da regra.

Se você estiver configurando regras de redução de superfície de ataque usando a Política de Grupo ou o PowerShell, precisará dos GUIDs. Por outro lado, se você usar Microsoft Endpoint Manager ou Microsoft Intune, não precisará dos GUIDs.

|Nome da regra|GUID|Exclusões & de pastas de arquivo|Sistema operacional mínimo suportado|
|---|:---:|---|---|
|[Bloquear o abuso de drivers assinados vulneráveis explorados](#block-abuse-of-exploited-vulnerable-signed-drivers)|`56a863a9-875e-4185-98a7-b882c64b5ce5`|Com suporte|[Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior) |
|[Impedir o Adobe Reader de criar processos filho](#block-adobe-reader-from-creating-child-processes)|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|Com suporte|[Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior|
|[Bloquear todos os Office aplicativos da criação de processos filho](#block-all-office-applications-from-creating-child-processes)|`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`|Com suporte|[Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior|
|[Bloquear o roubo de credenciais do subsistema Windows autoridade de segurança local (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|Com suporte|[Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior|
|[Bloquear conteúdo executável do cliente de email e do webmail](#block-executable-content-from-email-client-and-webmail)|`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`|Com suporte|[Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior|
|[Impedir a execução de arquivos executáveis, a menos que eles atendem a uma prevalência, idade ou critério de lista confiável](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)|`01443614-cd74-433a-b99e-2ecdc07bfc25`|Com suporte|[Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior|
|[Bloquear a execução de scripts potencialmente ofuscados](#block-execution-of-potentially-obfuscated-scripts)|`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`|Com suporte|[Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior|
|[Bloquear JavaScript ou VBScript de iniciar conteúdo executável baixado](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)|`D3E037E1-3EB8-44C8-A917-57927947596D`|Com suporte|[Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior|
|[Impedir Office aplicativos de criação de conteúdo executável](#block-office-applications-from-creating-executable-content)|`3B576869-A4EC-4529-8536-B80A7769E899`|Com suporte|[Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior|
|[Impedir Office aplicativos de injetar código em outros processos](#block-office-applications-from-injecting-code-into-other-processes)|`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`|Com suporte|[Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior|
|[Impedir Office aplicativo de comunicação da criação de processos filho](#block-office-communication-application-from-creating-child-processes)|`26190899-1602-49e8-8b27-eb1d0a1ce869`|Com suporte|[Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior|
|[Bloquear a persistência por meio da assinatura de evento WMI](#block-persistence-through-wmi-event-subscription)|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|Sem suporte|[Windows 10, versão 1903](/windows/whats-new/whats-new-windows-10-version-1903) (build 18362) ou superior|
|[Bloquear criações de processo provenientes de comandos PSExec e WMI](#block-process-creations-originating-from-psexec-and-wmi-commands)|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|Com suporte|[Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior|
|[Bloquear processos não assinados e não assinados que são executados a partir do USB](#block-untrusted-and-unsigned-processes-that-run-from-usb)|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|Com suporte|[Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior|
|[Bloquear chamadas de API Win32 de Office macros](#block-win32-api-calls-from-office-macros)|`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`|Com suporte|[Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior|
|[Usar proteção avançada contra ransomware](#use-advanced-protection-against-ransomware)|`c1db55ab-c21a-4637-bb3f-a12568109d35`|Com suporte|[Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior|

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a>Bloquear o abuso de drivers assinados vulneráveis explorados

Essa regra impede que um aplicativo descreda um driver assinado vulnerável em disco. Drivers in-the-wild e vulneráveis assinados podem ser explorados por aplicativos locais que têm privilégios suficientes para obter \-  \- acesso ao kernel. Drivers assinados vulneráveis permitem que os invasores desabilitem ou driblam soluções de segurança, eventualmente levando ao comprometimento do sistema.

A **regra Bloquear abuso de drivers** assinados vulneráveis explorados não bloqueia que um driver já existente no sistema seja carregado.

>[!NOTE]
>
> Você pode configurar essa regra usando [o OMA-URI do MEM](enable-attack-surface-reduction.md#mem) para informações de procedimento de regras personalizadas do OMA-URI do MEM.
>
> Você também pode configurar essa regra usando [o PowerShell](enable-attack-surface-reduction.md#powershell).
>
> Para ter um driver examinado, use este site para [Enviar um driver para análise.](https://www.microsoft.com/en-us/wdsi/driversubmission)

Sistemas operacionais suportados:

- [Windows 10 Pro, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709) ou posterior
- [Windows 10 Enterprise, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709) ou posterior
- [Windows Server, versão 1803 (Canal Semesanuais)](/windows-server/get-started/whats-new-in-windows-server-1803) ou posterior
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Nome do Intune: `Block abuse of exploited vulnerable signed drivers`

GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`

### <a name="block-adobe-reader-from-creating-child-processes"></a>Impedir o Adobe Reader de criar processos filho

Essa regra impede ataques bloqueando o Adobe Reader de criar processos.

Por meio de engenharia social ou explorações, o malware pode baixar e iniciar cargas e sair do Adobe Reader. Ao impedir que processos filho sejam gerados pelo Adobe Reader, o malware que tenta usá-lo como vetor é impedido de se propagar.

Sistemas operacionais suportados:

- [Windows 10, versão 1809](/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Servidor, versão 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Nome do Intune: `Process creation from Adobe Reader (beta)`

Nome do Gerenciador de Configurações: Ainda não disponível

GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

### <a name="block-all-office-applications-from-creating-child-processes"></a>Bloquear todos os Office aplicativos da criação de processos filho

Essa regra impede Office aplicativos da criação de processos filho. Office aplicativos incluem Word, Excel, PowerPoint, OneNote e Access.

Criar processos filho mal-intencionados é uma estratégia comum de malware. Malware que abusa Office como vetor geralmente executar macros VBA e explorar código para baixar e tentar executar mais cargas. No entanto, alguns aplicativos de linha de negócios legítimos também podem gerar processos filho para fins benignos; como gerar um prompt de comando ou usar o PowerShell para configurar as configurações do Registro.

Sistemas operacionais suportados:

- [Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Servidor, versão 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Nome do Intune: `Office apps launching child processes`

Nome do Gerenciador de Configurações: `Block Office application from creating child processes`

GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>Bloquear o roubo de credenciais do subsistema Windows autoridade de segurança local

Essa regra ajuda a impedir o roubo de credenciais ao bloquear o Serviço de Subsistema de Autoridade de Segurança Local (LSASS).

O LSASS autentica os usuários que fazem login em um Windows computador. O Microsoft Defender Credential Guard Windows 10 normalmente impede tentativas de extrair credenciais do LSASS. No entanto, algumas organizações não podem habilitar o Credential Guard em todos os seus computadores devido a problemas de compatibilidade com drivers de cartão inteligente personalizados ou outros programas que carregam na LSA (Autoridade de Segurança Local). Nesses casos, os invasores podem usar ferramentas de hack como Mimikatz para limpar senhas de texto e hashs NTLM do LSASS.

> [!NOTE]
> Em alguns aplicativos, o código enumera todos os processos em execução e tenta abri-los com permissões exaustivas. Essa regra nega a ação de abertura do processo do aplicativo e registra os detalhes no log de eventos de segurança. Essa regra pode gerar muito ruído. Se você tiver um aplicativo que simplesmente enumera o LSASS, mas não tem impacto real na funcionalidade, não é necessário adicioná-lo à lista de exclusão. Por si só, essa entrada de log de eventos não indica necessariamente uma ameaça mal-intencionada.

Sistemas operacionais suportados:

- [Windows 10, versão 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Servidor, versão 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Nome do Intune: `Flag credential stealing from the Windows local security authority subsystem`

Nome do Gerenciador de Configurações: `Block credential stealing from the Windows local security authority subsystem`

GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

### <a name="block-executable-content-from-email-client-and-webmail"></a>Bloquear conteúdo executável do cliente de email e do webmail

Essa regra bloqueia o início dos seguintes tipos de arquivo a partir de emails abertos no aplicativo microsoft Outlook ou Outlook.com e outros provedores de webmail populares:

- Arquivos executáveis (como .exe, .dll ou .scr)
- Arquivos de script (como um arquivo .ps do PowerShell, Visual Basic .vbs ou JavaScript .js)

Sistemas operacionais suportados:

- [Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Servidor, versão 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Microsoft Endpoint Manager CB 1710](/configmgr/core/servers/manage/updates)

Nome do Intune: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft Endpoint Manager nome:`Block executable content from email client and webmail`

GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`

> [!NOTE]
> A regra **Bloquear conteúdo executável do cliente de email** e do webmail tem as seguintes descrições alternativas, dependendo de qual aplicativo você usa:
>
> - Intune (Perfis de Configuração): a execução de conteúdo executável (exe, dll, ps, js, vbs, etc.) foi retirada do email (cliente webmail/email) (sem exceções).
> - Endpoint Manager: bloquear o download de conteúdo executável de clientes de email e webmail.
> - Política de Grupo: Bloquear conteúdo executável do cliente de email e do webmail.

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>Impedir a execução de arquivos executáveis, a menos que eles atendem a uma prevalência, idade ou critério de lista confiável

Essa regra impede que arquivos executáveis, como .exe, .dll ou .scr, sejam lançados, a menos que qualquer uma das seguintes condições seja atendida:

- Prevalência: os arquivos executáveis são encontrados em mais de 1.000 pontos de extremidade
- Idade: os arquivos executáveis foram lançados há mais de 24 horas
- Local: os arquivos executáveis estão incluídos em uma lista confiável ou em uma lista de exclusão

A inicialização de arquivos executáveis não confirmados ou desconhecidos pode ser arriscada, pois pode não ser inicialmente claro se os arquivos são mal-intencionados.

> [!IMPORTANT]
> Você deve [habilitar a proteção entregue na nuvem](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) para usar essa regra.
>
> A regra Bloquear a execução de arquivos executáveis, a menos que eles atendem a um critério de **prevalência,** idade ou lista confiável com GUID é propriedade da Microsoft e não é especificada `01443614-cd74-433a-b99e-2ecdc07bfc25` pelos administradores. Essa regra usa a proteção entregue na nuvem para atualizar sua lista confiável regularmente.
>
> Você pode especificar arquivos ou pastas individuais (usando caminhos de pasta ou nomes de recursos totalmente qualificados), mas não pode especificar a quais regras ou exclusões se aplicam.

Sistemas operacionais suportados:

- [Windows 10, versão 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Servidor, versão 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Nome do Intune: `Executables that don't meet a prevalence, age, or trusted list criteria`

Nome do Gerenciador de Configurações: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>Bloquear a execução de scripts potencialmente ofuscados

Esta regra detecta propriedades suspeitas em um script ofuscado.

A ofuscação de script é uma técnica comum que tanto os autores de malware quanto os aplicativos legítimos usam para ocultar a propriedade intelectual ou diminuir os tempos de carregamento de scripts. Os autores de malware também usam ofuscação para tornar o código mal-intencionado mais difícil de ler, o que impede a análise detalhada por humanos e software de segurança.

Sistemas operacionais suportados:

- [Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Servidor, versão 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Nome do Intune: `Obfuscated js/vbs/ps/macro code`

Nome do Gerenciador de Configurações: `Block execution of potentially obfuscated scripts`

GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>Bloquear JavaScript ou VBScript de iniciar conteúdo executável baixado

Essa regra impede que os scripts iniciam conteúdo baixado potencialmente mal-intencionado. Malware escrito em JavaScript ou VBScript geralmente age como um downloader para buscar e iniciar outro malware da Internet.

Embora não seja comum, os aplicativos de linha de negócios às vezes usam scripts para baixar e iniciar instaladores.

Sistemas operacionais suportados:

- [Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Servidor, versão 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Nome do Intune: `js/vbs executing payload downloaded from Internet (no exceptions)`

Nome do Gerenciador de Configurações: `Block JavaScript or VBScript from launching downloaded executable content`

GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`

### <a name="block-office-applications-from-creating-executable-content"></a>Impedir Office aplicativos de criação de conteúdo executável

Essa regra impede Office aplicativos, incluindo Word, Excel e PowerPoint, de criar conteúdo executável potencialmente mal-intencionado, bloqueando o código mal-intencionado de ser gravado em disco.

Malware que abusa Office como vetor pode tentar sair do Office e salvar componentes mal-intencionados no disco. Esses componentes mal-intencionados sobreviveriam a uma reinicialização do computador e persistiam no sistema. Portanto, essa regra se defende contra uma técnica de persistência comum.

Sistemas operacionais suportados:

- [Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Servidor, versão 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [System Center Configuration Manager](/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (O SCCM agora Microsoft Endpoint Configuration Manager)

Nome do Intune: `Office apps/macros creating executable content`

Nome do SCCM: `Block Office applications from creating executable content`

GUID: `3B576869-A4EC-4529-8536-B80A7769E899`

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>Impedir Office aplicativos de injetar código em outros processos

Essa regra bloqueia as tentativas de injeção de código Office aplicativos em outros processos.

Os invasores podem tentar usar Office aplicativos para migrar código mal-intencionado para outros processos por meio da injeção de código, para que o código possa mascarar como um processo limpo.

Não há finalidades comerciais legítimas conhecidas para usar a injeção de código.

Esta regra se aplica ao Word, Excel e PowerPoint.

Sistemas operacionais suportados:

- [Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Servidor, versão 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Nome do Intune: `Office apps injecting code into other processes (no exceptions)`

Nome do Gerenciador de Configurações: `Block Office applications from injecting code into other processes`

GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`

### <a name="block-office-communication-application-from-creating-child-processes"></a>Impedir Office aplicativo de comunicação da criação de processos filho

Essa regra impede Outlook criar processos filho, enquanto ainda permite funções Outlook legítimas.

Essa regra protege contra ataques de engenharia social e impede a exploração de código contra vulnerabilidades em Outlook. Ele também protege contra as Outlook [e](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) as explorações de formulários que os invasores podem usar quando as credenciais de um usuário são comprometidas.

> [!NOTE]
> Esta regra bloqueia dicas de política de DLP e Dicas de Ferramentas Outlook. Esta regra se aplica somente Outlook e Outlook.com.

Sistemas operacionais suportados:

- [Windows 10, versão 1809](/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Servidor, versão 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Nome do Intune: `Process creation from Office communication products (beta)`

Nome do Gerenciador de Configurações: Não disponível

GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`

### <a name="block-persistence-through-wmi-event-subscription"></a>Bloquear a persistência por meio da assinatura de evento WMI

Essa regra impede que o malware abuse o WMI para atingir persistência em um dispositivo.

> [!IMPORTANT]
> As exclusões de arquivos e pastas não se aplicam a essa regra de redução de superfície de ataque.

As ameaças sem arquivo empregam várias táticas para permanecer ocultas, para evitar serem vistas no sistema de arquivos e para obter controle de execução periódica. Algumas ameaças podem usar o repositório WMI e o modelo de evento para permanecer oculto.

Sistemas operacionais suportados:

- [Windows 10 versão 1903](/windows/whats-new/whats-new-windows-10-version-1903)
- [Windows Server 1903](/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

Nome do Intune: Não disponível

Nome do Gerenciador de Configurações: Não disponível

GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>Bloquear criações de processo provenientes de comandos PSExec e WMI

Essa regra bloqueia a execução de processos criados [por meio do PsExec](/sysinternals/downloads/psexec) e [do WMI.](/windows/win32/wmisdk/about-wmi) Tanto o PsExec quanto o WMI podem executar o código remotamente, portanto, há um risco de malware abusando dessa funcionalidade para fins de comando e controle ou para propagar uma infecção em toda a rede de uma organização.

> [!WARNING]
> Use essa regra somente se você estiver gerenciando seus dispositivos com [o Intune](/intune) ou outra solução MDM. Essa regra é incompatível com o gerenciamento por [Microsoft Endpoint Configuration Manager](/configmgr) porque essa regra bloqueia comandos WMI que o cliente configuration Manager usa para funcionar corretamente.

Sistemas operacionais suportados:

- [Windows 10, versão 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Servidor, versão 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Nome do Intune: `Process creation from PSExec and WMI commands`

Nome do Gerenciador de Configurações: Não aplicável

GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>Bloquear processos não assinados e não assinados que são executados a partir do USB

Com essa regra, os administradores podem impedir a execução de arquivos executáveis não assinados ou não-não-assinados de unidades removíveis USB, incluindo cartões SD. Os tipos de arquivo bloqueados incluem arquivos executáveis (como .exe, .dll ou .scr)

Sistemas operacionais suportados:

- [Windows 10, versão 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Servidor, versão 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Nome do Intune: `Untrusted and unsigned processes that run from USB`

Nome do Gerenciador de Configurações: `Block untrusted and unsigned processes that run from USB`

GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

### <a name="block-win32-api-calls-from-office-macros"></a>Bloquear chamadas de API Win32 de Office macros

Essa regra impede que as macros do VBA chamando APIs win32.

Office O VBA habilita chamadas da API Win32. O malware pode usar esse recurso, como chamar [APIs do Win32](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) para iniciar o shellcode mal-intencionado sem escrever nada diretamente no disco. A maioria das organizações não depende da capacidade de chamar APIs win32 em seu funcionamento do dia a dia, mesmo que elas usem macros de outras maneiras.

Sistemas operacionais suportados:

- [Windows 10, versão 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Servidor, versão 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Nome do Intune: `Win32 imports from Office macro code`

Nome do Gerenciador de Configurações: `Block Win32 API calls from Office macros`

GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`

### <a name="use-advanced-protection-against-ransomware"></a>Usar proteção avançada contra ransomware

Essa regra fornece uma camada extra de proteção contra ransomware. Ele usa heurísticas de cliente e nuvem para determinar se um arquivo se parece com ransomware. Esta regra não bloqueia arquivos que tenham uma ou mais das seguintes características:

- O arquivo já foi encontrado incólume na nuvem da Microsoft.
- O arquivo é um arquivo assinado válido.
- O arquivo é predominante o suficiente para não ser considerado como ransomware.

A regra tende a esmá-lo por precaução para evitar ransomware.

> [!NOTE]
> Você deve [habilitar a proteção entregue na nuvem](enable-cloud-protection-microsoft-defender-antivirus.md) para usar essa regra.

Sistemas operacionais suportados:

- [Windows 10, versão 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Servidor, versão 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Nome do Intune: `Advanced ransomware protection`

Nome do Gerenciador de Configurações: `Use advanced protection against ransomware`

GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`
