---
title: Usar regras de redução de superfície de ataque para evitar infecção por malware
description: As regras de redução de superfície de ataque podem ajudar a impedir que explorações usem aplicativos e scripts para infectar dispositivos com malware.
keywords: Regras de redução de superfície de ataque, asr, quadris, sistema de prevenção contra invasões de host, regras de proteção, antiexploit, exploração, prevenção de infecção, Microsoft Defender para Ponto de Extremidade, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.openlocfilehash: d88da04e91875e24b13478b17d6a1e3862e1062e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197656"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a>Usar regras de redução de superfície de ataque para evitar infecção por malware

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="why-attack-surface-reduction-rules-are-important"></a>Por que as regras de redução de superfície de ataque são importantes

A superfície de ataque da sua organização inclui todos os locais onde um invasor pode comprometer os dispositivos ou redes da sua organização. Reduzir sua superfície de ataque significa proteger os dispositivos e a rede da sua organização, o que deixa os invasores com menos maneiras de executar ataques. Configurar regras de redução de superfície de ataque no Microsoft Defender para Ponto de Extremidade pode ajudar!

As regras de redução de superfície de ataque visam determinados comportamentos de software, como:

- Iniciando arquivos executáveis e scripts que tentam baixar ou executar arquivos;
- Executando scripts ofuscados ou suspeitos; e 
- Executando comportamentos que os aplicativos geralmente não iniciam durante o trabalho normal do dia a dia.

Esses comportamentos de software às vezes são vistos em aplicativos legítimos; no entanto, esses comportamentos geralmente são considerados arriscados porque são comumente abusadas por invasores por meio de malware. As regras de redução de superfície de ataque podem restringir comportamentos de risco e ajudar a manter sua organização segura.

Para obter mais informações sobre como configurar regras de redução de superfície de ataque, consulte [Enable attack surface reduction rules](enable-attack-surface-reduction.md).

## <a name="assess-rule-impact-before-deployment"></a>Avaliar o impacto da regra antes da implantação  

Você pode avaliar como uma regra de redução de superfície de ataque pode afetar sua rede abrindo a recomendação de segurança para essa regra no gerenciamento de ameaças [e vulnerabilidades.](https://docs.microsoft.com/windows/security/threat-protection/#tvm) 

:::image type="content" source="images/asrrecommendation.png" alt-text="Reco de segurança para regra de redução de superfície de ataque":::

No painel de detalhes de recomendação, verifique se há impacto do usuário para determinar qual porcentagem de seus dispositivos pode aceitar uma nova política habilitando a regra no modo de bloqueio sem afetar adversamente a produtividade.

## <a name="audit-mode-for-evaluation"></a>Modo de auditoria para avaliação

Use [o modo de auditoria](audit-windows-defender.md) para avaliar como as regras de redução de superfície de ataque afetariam sua organização se elas fossem habilitadas. Execute todas as regras no modo de auditoria primeiro para que você possa entender como elas afetam seus aplicativos de linha de negócios. Muitos aplicativos de linha de negócios são escritos com preocupações de segurança limitadas e podem executar tarefas de maneiras semelhantes ao malware. Monitorando dados de auditoria e adicionando exclusões para [aplicativos necessários,](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) você pode implantar regras de redução de superfície de ataque sem reduzir a produtividade.

## <a name="warn-mode-for-users"></a>Modo de aviso para usuários

(**NOVO**!) Antes de avisar os recursos do modo, as regras de redução de superfície de ataque que estão habilitadas podem ser definidas para o modo de auditoria ou modo de bloqueio. Com o novo modo de aviso, sempre que o conteúdo é bloqueado por uma regra de redução de superfície de ataque, os usuários veem uma caixa de diálogo que indica que o conteúdo está bloqueado. A caixa de diálogo também oferece ao usuário uma opção para desbloquear o conteúdo. Em seguida, o usuário pode repetir sua ação e a operação é concluída. Quando um usuário desbloqueia o conteúdo, o conteúdo permanece desbloqueado por 24 horas e, em seguida, o bloqueio é retomado.

O modo de aviso ajuda sua organização a ter regras de redução de superfície de ataque em vigor sem impedir que os usuários acessem o conteúdo necessário para executar suas tarefas. 

### <a name="requirements-for-warn-mode-to-work"></a>Requisitos para que o modo de aviso funcione

O modo de aviso é suportado em dispositivos que executam as seguintes versões do Windows:
- [Windows 10, versão 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) ou posterior
- [Windows Server, versão 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809) ou posterior
 
O Microsoft Defender Antivírus deve estar em execução com proteção em tempo real no [modo Ativo.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)

Além disso, certifique-se de que as atualizações do [Microsoft Defender Antivírus e antimalware](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) estão instaladas.
- Requisito mínimo de lançamento da plataforma: `4.18.2008.9`  
- Requisito mínimo de versão do mecanismo: `1.1.17400.5`

Para obter mais informações e obter suas atualizações, consulte [Update for Microsoft Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).

### <a name="cases-where-warn-mode-is-not-supported"></a>Casos em que o modo de aviso não é suportado

O modo de aviso não é suportado para as seguintes regras de redução de superfície de ataque:

- [Bloquear JavaScript ou VBScript de iniciar conteúdo executável baixado](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d` )
- [Bloquear a persistência por meio da assinatura de evento WMI](#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b` )
- [Usar proteção avançada contra ransomware](#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35` )

Além disso, o modo de aviso não é suportado em dispositivos que executam versões mais antigas do Windows. Nesses casos, as regras de redução de superfície de ataque configuradas para executar no modo de aviso serão executados no modo de bloqueio.

## <a name="notifications-and-alerts"></a>Notificações e alertas

Sempre que uma regra de redução de superfície de ataque é disparada, uma notificação é exibida no dispositivo. Você pode [personalizar a notificação com](customize-attack-surface-reduction.md#customize-the-notification) os detalhes da empresa e informações de contato.

Além disso, quando determinadas regras de redução de superfície de ataque são disparadas, alertas são gerados. 

As notificações e os alertas gerados podem ser exibidos no Centro de Segurança do Microsoft Defender ( ) e no Centro de segurança [https://securitycenter.windows.com](https://securitycenter.windows.com) do Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ).

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a>Eventos avançados de busca e redução de superfície de ataque

Você pode usar a busca avançada para exibir eventos de redução de superfície de ataque. Para simplificar o volume de dados de entrada, somente processos exclusivos para cada hora podem ser visualizados com busca avançada. O tempo de um evento de redução de superfície de ataque é a primeira vez que esse evento é visto dentro de uma hora.

Por exemplo, suponha que um evento de redução de superfície de ataque ocorra em 10 dispositivos durante a hora das 14:00. Suponha que o primeiro evento ocorreu às 14:15 e o último às 14:45. Com a busca avançada, você verá uma instância desse evento (mesmo que tenha realmente ocorrido em 10 dispositivos) e seu data/hora será 14:15. 

Para obter mais informações sobre a busca avançada, consulte [Proativamente procurar ameaças com a busca avançada.](advanced-hunting-overview.md)

## <a name="attack-surface-reduction-features-across-windows-versions"></a>Recursos de redução de superfície de ataque em versões do Windows

Você pode definir regras de redução de superfície de ataque para dispositivos que estão executando qualquer uma das seguintes edições e versões do Windows:
- Windows 10 Pro, [versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) ou posterior
- Windows 10 Enterprise, [versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) ou posterior
- Windows Server, [versão 1803 (Canal Semesanuais)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) ou posterior
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Embora as regras de redução de superfície de ataque não exigem uma licença do [Windows E5](https://docs.microsoft.com/windows/deployment/deploy-enterprise-licenses), se você tiver o Windows E5, você obterá recursos avançados de gerenciamento. Esses recursos disponíveis apenas no Windows E5 incluem monitoramento, análise e fluxos de trabalho disponíveis no [Defender para](microsoft-defender-endpoint.md)Ponto de Extremidade, bem como recursos de relatórios e configuração no centro de segurança do [Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/defender/overview-security-center) Esses recursos avançados não estão disponíveis com uma licença do Windows Professional ou do Windows E3; no entanto, se você tiver essas licenças, poderá usar logs do Visualizador de Eventos e do Microsoft Defender Antivírus para revisar seus eventos de regra de redução de superfície de ataque.

## <a name="review-attack-surface-reduction-events-in-the-microsoft-defender-security-center"></a>Revisar eventos de redução de superfície de ataque no Centro de Segurança do Microsoft Defender

O Defender for Endpoint fornece relatórios detalhados de eventos e bloqueios como parte dos cenários de investigação de alerta.

Você pode consultar dados do Defender para o Ponto de Extremidade usando [a busca avançada](advanced-hunting-query-language.md). Se você estiver executando o modo [de](audit-windows-defender.md)auditoria, poderá usar a busca avançada para entender como as regras de redução de superfície de ataque podem afetar seu ambiente.

Aqui está uma consulta de exemplo:

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Revisar eventos de redução de superfície de ataque no Visualizador de Eventos do Windows

Você pode revisar o log de eventos do Windows para exibir eventos gerados por regras de redução de superfície de ataque:

1. Baixe o [Pacote de Avaliação](https://aka.ms/mp7z2w) e extraia o arquivo *cfa-events.xml* para um local facilmente acessível no dispositivo.
2. Insira as palavras, *Visualizador de Eventos*, no menu Iniciar para abrir o Visualizador de Eventos do Windows.
3. Em **Ações,** selecione **Importar exibição personalizada...**.
4. Selecione o arquivo *cfa-events.xml* de onde ele foi extraído. Como alternativa, [copie o XML diretamente](event-views.md).
5. Selecione **OK**.

Você pode criar uma exibição personalizada que filtra eventos para mostrar apenas os seguintes eventos, todos relacionados ao acesso controlado a pastas:

|ID de evento | Descrição |
|:---|:---|
|5007 | Evento quando as configurações são alteradas |
|1121 | Evento quando a regra é a disparar no modo de bloqueio |
|1122 | Evento quando a regra é a disparar no modo de auditoria |

A "versão do mecanismo" listada para eventos de redução de superfície de ataque no log de eventos é gerada pelo Defender para Ponto de Extremidade, não pelo sistema operacional. O Defender para Ponto de Extremidade é integrado ao Windows 10, portanto, esse recurso funciona em todos os dispositivos com o Windows 10 instalado.

## <a name="attack-surface-reduction-rules"></a>Regras de redução de superfície de ataque

A tabela e as subseções a seguir descrevem cada uma das 15 regras de redução de superfície de ataque. As regras de redução de superfície de ataque são listadas em ordem alfabética, pelo nome da regra. 

Se você estiver configurando regras de redução de superfície de ataque usando a Política de Grupo ou o PowerShell, precisará dos GUIDs. Por outro lado, se você usar o Microsoft Endpoint Manager ou o Microsoft Intune, não precisará dos GUIDs.


| Nome da regra | GUID | Exclusões & de pastas de arquivo | Sistema operacional mínimo suportado |
|:-----|:-----:|:-----|:-----|
|[Impedir o Adobe Reader de criar processos filho](#block-adobe-reader-from-creating-child-processes) | `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c` | Com suporte | [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior |
|[Bloquear todos os aplicativos do Office da criação de processos filho](#block-all-office-applications-from-creating-child-processes) | `D4F940AB-401B-4EFC-AADC-AD5F3C50688A` | Com suporte | [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior |
|[Bloquear o roubo de credenciais do subsistema de autoridade de segurança local do Windows (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2` | Com suporte | [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior |
|[Bloquear conteúdo executável do cliente de email e do webmail](#block-executable-content-from-email-client-and-webmail) | `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550` | Com suporte | [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior |
|[Impedir a execução de arquivos executáveis, a menos que eles atendem a uma prevalência, idade ou critério de lista confiável](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | `01443614-cd74-433a-b99e-2ecdc07bfc25` | Com suporte | [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior |
|[Bloquear a execução de scripts potencialmente ofuscados](#block-execution-of-potentially-obfuscated-scripts) | `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC` | Com suporte | [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior |
|[Bloquear JavaScript ou VBScript de iniciar conteúdo executável baixado](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | `D3E037E1-3EB8-44C8-A917-57927947596D` | Com suporte | [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior |
|[Impedir aplicativos do Office de criar conteúdo executável](#block-office-applications-from-creating-executable-content) | `3B576869-A4EC-4529-8536-B80A7769E899` | Com suporte | [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior |
|[Impedir que aplicativos do Office injetem código em outros processos](#block-office-applications-from-injecting-code-into-other-processes) | `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84` | Com suporte | [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior |
|[Bloquear o aplicativo de comunicação do Office da criação de processos filho](#block-office-communication-application-from-creating-child-processes) |`26190899-1602-49e8-8b27-eb1d0a1ce869` |Com suporte |[Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior  |
|[Bloquear a persistência por meio da assinatura de evento WMI](#block-persistence-through-wmi-event-subscription) | `e6db77e5-3df2-4cf1-b95a-636979351e5b` | Sem suporte | [Windows 10, versão 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) (build 18362) ou superior |
|[Bloquear criações de processo provenientes de comandos PSExec e WMI](#block-process-creations-originating-from-psexec-and-wmi-commands) | `d1e49aac-8f56-4280-b9ba-993a6d77406c` | Com suporte | [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior |
|[Bloquear processos não assinados e não assinados que são executados a partir do USB](#block-untrusted-and-unsigned-processes-that-run-from-usb) | `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4` | Com suporte | [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior |
|[Bloquear chamadas de API Win32 de macros do Office](#block-win32-api-calls-from-office-macros) | `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B` | Com suporte | [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior |
|[Usar proteção avançada contra ransomware](#use-advanced-protection-against-ransomware) | `c1db55ab-c21a-4637-bb3f-a12568109d35` | Com suporte | [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) ou superior |

### <a name="block-adobe-reader-from-creating-child-processes"></a>Impedir o Adobe Reader de criar processos filho

Essa regra impede ataques bloqueando o Adobe Reader de criar processos.

Por meio de engenharia social ou explorações, o malware pode baixar e iniciar cargas e sair do Adobe Reader. Ao impedir que processos filho sejam gerados pelo Adobe Reader, o malware que tenta usá-lo como vetor é impedido de se propagar.

Esta regra foi introduzida em: 
- [Windows 10, versão 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Server, versão 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Nome do Intune: `Process creation from Adobe Reader (beta)`

Nome do Gerenciador de Configurações: Ainda não disponível

GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

### <a name="block-all-office-applications-from-creating-child-processes"></a>Bloquear todos os aplicativos do Office da criação de processos filho

Essa regra impede que os aplicativos do Office criam processos filho. Os aplicativos do Office incluem Word, Excel, PowerPoint, OneNote e Access.

Criar processos filho mal-intencionados é uma estratégia comum de malware. Malwares que abusam do Office como vetor geralmente executem macros do VBA e exploram o código para baixar e tentar executar mais cargas. No entanto, alguns aplicativos de linha de negócios legítimos também podem gerar processos filho para fins benignos, como gerar um prompt de comando ou usar o PowerShell para definir as configurações do Registro.

Esta regra foi introduzida em: 
- [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versão 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nome do Intune: `Office apps launching child processes`

Nome do Gerenciador de Configurações: `Block Office application from creating child processes`

GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>Bloquear o roubo de credenciais do subsistema da autoridade de segurança local do Windows

Essa regra ajuda a impedir o roubo de credenciais, ao bloquear o Serviço de Subsistema de Autoridade de Segurança Local (LSASS).

O LSASS autentica os usuários que fazem login em um computador Windows. O Microsoft Defender Credential Guard no Windows 10 normalmente impede tentativas de extrair credenciais do LSASS. No entanto, algumas organizações não podem habilitar o Credential Guard em todos os seus computadores devido a problemas de compatibilidade com drivers de cartão inteligente personalizados ou outros programas que carregam na LSA (Autoridade de Segurança Local). Nesses casos, os invasores podem usar ferramentas de hack como Mimikatz para limpar senhas de texto e hashs NTLM do LSASS.

> [!NOTE]
> Em alguns aplicativos, o código enumera todos os processos em execução e tenta abri-los com permissões exaustivas. Essa regra nega a ação de abertura do processo do aplicativo e registra os detalhes no log de eventos de segurança. Essa regra pode gerar muito ruído. Se você tiver um aplicativo que simplesmente enumera o LSASS, mas não tem impacto real na funcionalidade, não é necessário adicioná-lo à lista de exclusão. Por si só, essa entrada de log de eventos não indica necessariamente uma ameaça mal-intencionada.

Esta regra foi introduzida em:
- [Windows 10, versão 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, versão 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nome do Intune: `Flag credential stealing from the Windows local security authority subsystem`

Nome do Gerenciador de Configurações: `Block credential stealing from the Windows local security authority subsystem`

GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

### <a name="block-executable-content-from-email-client-and-webmail"></a>Bloquear conteúdo executável do cliente de email e do webmail

Essa regra impede o início dos seguintes tipos de arquivo a partir de emails abertos no aplicativo Microsoft Outlook ou Outlook.com e outros provedores de webmail populares:

- Arquivos executáveis (como .exe, .dll ou .scr)
- Arquivos de script (como um arquivo .ps do PowerShell, Visual Basic .vbs ou JavaScript .js)

Esta regra foi introduzida em: 
- [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versão 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Microsoft Endpoint Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nome do Intune: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Nome do Microsoft Endpoint Manager: `Block executable content from email client and webmail`

GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`

> [!NOTE]
> A regra **Bloquear conteúdo executável do cliente de email** e do webmail tem as seguintes descrições alternativas, dependendo de qual aplicativo você usa:
> - Intune (Perfis de Configuração): a execução de conteúdo executável (exe, dll, ps, js, vbs, etc.) foi retirada do email (cliente webmail/email) (sem exceções).
> - Endpoint Manager: Bloquear o download de conteúdo executável de clientes de email e webmail.
> - Política de Grupo: Bloquear conteúdo executável do cliente de email e do webmail.

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>Impedir a execução de arquivos executáveis, a menos que eles atendem a uma prevalência, idade ou critério de lista confiável

Esta regra impede que os seguintes tipos de arquivo seja lançado, a menos que eles atendem aos critérios de prevalência ou idade, ou que estão em uma lista confiável ou em uma lista de exclusão:

- Arquivos executáveis (como .exe, .dll ou .scr)

A inicialização de arquivos executáveis não confirmados ou desconhecidos pode ser arriscada, pois pode não ser inicialmente claro se os arquivos são mal-intencionados.

> [!IMPORTANT]
> Você deve [habilitar a proteção entregue na nuvem](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) para usar essa regra. <br/><br/> A regra Bloquear a execução de arquivos executáveis, a menos que eles atendem a um critério de **prevalência,** idade ou lista confiável com GUID é propriedade da Microsoft e não é especificada `01443614-cd74-433a-b99e-2ecdc07bfc25` pelos administradores. Essa regra usa a proteção entregue na nuvem para atualizar sua lista confiável regularmente.
>
>Você pode especificar arquivos ou pastas individuais (usando caminhos de pasta ou nomes de recursos totalmente qualificados), mas não pode especificar a quais regras ou exclusões se aplicam.

Esta regra foi introduzida em: 
- [Windows 10, versão 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, versão 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nome do Intune: `Executables that don't meet a prevalence, age, or trusted list criteria`

Nome do Gerenciador de Configurações: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>Bloquear a execução de scripts potencialmente ofuscados

Esta regra detecta propriedades suspeitas em um script ofuscado.

A ofuscação de script é uma técnica comum que tanto os autores de malware quanto os aplicativos legítimos usam para ocultar a propriedade intelectual ou diminuir os tempos de carregamento de scripts. Os autores de malware também usam ofuscação para tornar o código mal-intencionado mais difícil de ler, o que impede a análise detalhada por humanos e software de segurança.

Esta regra foi introduzida em:
- [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versão 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nome do Intune: `Obfuscated js/vbs/ps/macro code`

Nome do Gerenciador de Configurações: `Block execution of potentially obfuscated scripts`

GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>Bloquear JavaScript ou VBScript de iniciar conteúdo executável baixado

Essa regra impede que os scripts iniciam conteúdo baixado potencialmente mal-intencionado. Malware escrito em JavaScript ou VBScript geralmente age como um downloader para buscar e iniciar outro malware da Internet.

Embora não seja comum, os aplicativos de linha de negócios às vezes usam scripts para baixar e iniciar instaladores.

Esta regra foi introduzida em:  
- [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versão 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nome do Intune: `js/vbs executing payload downloaded from Internet (no exceptions)`

Nome do Gerenciador de Configurações: `Block JavaScript or VBScript from launching downloaded executable content`

GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`

### <a name="block-office-applications-from-creating-executable-content"></a>Impedir aplicativos do Office de criar conteúdo executável

Essa regra impede que aplicativos do Office, incluindo Word, Excel e PowerPoint, de criar conteúdo executável potencialmente mal-intencionado, bloqueando o código mal-intencionado de ser gravado em disco.

Malware que abusa do Office como vetor pode tentar sair do Office e salvar componentes mal-intencionados no disco. Esses componentes mal-intencionados sobreviveriam a uma reinicialização do computador e persistiam no sistema. Portanto, essa regra se defende contra uma técnica de persistência comum.

Esta regra foi introduzida em: 
- [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versão 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [System Center Configuration Manager](https://docs.microsoft.com/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM agora é o Microsoft Endpoint Configuration Manager)

Nome do Intune: `Office apps/macros creating executable content`

Nome do SCCM: `Block Office applications from creating executable content`

GUID: `3B576869-A4EC-4529-8536-B80A7769E899`

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>Impedir que aplicativos do Office injetem código em outros processos

Essa regra bloqueia tentativas de injeção de código de aplicativos do Office em outros processos.

Os invasores podem tentar usar aplicativos do Office para migrar código mal-intencionado para outros processos por meio da injeção de código, para que o código possa mascarar como um processo limpo.

Não há finalidades comerciais legítimas conhecidas para usar a injeção de código.

Esta regra se aplica ao Word, Excel e PowerPoint.

Esta regra foi introduzida em: 
- [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versão 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nome do Intune: `Office apps injecting code into other processes (no exceptions)`

Nome do Gerenciador de Configurações: `Block Office applications from injecting code into other processes`

GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`

### <a name="block-office-communication-application-from-creating-child-processes"></a>Bloquear o aplicativo de comunicação do Office da criação de processos filho

Essa regra impede o Outlook de criar processos filho, enquanto ainda permite funções legítimas do Outlook.

Essa regra protege contra ataques de engenharia social e impede a exploração de código contra vulnerabilidades no Outlook. Ele também protege contra as explorações de formulários e regras do [Outlook](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) que os invasores podem usar quando as credenciais de um usuário são comprometidas.

> [!NOTE]
> Essa regra se aplica somente ao Outlook Outlook.com.

Esta regra foi introduzida em: 
- [Windows 10, versão 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Server, versão 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Nome do Intune: `Process creation from Office communication products (beta)`

Nome do Gerenciador de Configurações: Não disponível

GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`

### <a name="block-persistence-through-wmi-event-subscription"></a>Bloquear a persistência por meio da assinatura de evento WMI

Essa regra impede que o malware abuse o WMI para atingir persistência em um dispositivo.

> [!IMPORTANT]
> As exclusões de arquivos e pastas não se aplicam a essa regra de redução de superfície de ataque.

As ameaças sem arquivo empregam várias táticas para permanecer ocultas, para evitar serem vistas no sistema de arquivos e para obter controle de execução periódica. Algumas ameaças podem usar o repositório WMI e o modelo de evento para permanecer oculto.

Esta regra foi introduzida em: 
- [Windows 10, versão 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903)
- [Windows Server 1903](https://docs.microsoft.com/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

Nome do Intune: Não disponível

Nome do Gerenciador de Configurações: Não disponível

GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>Bloquear criações de processo provenientes de comandos PSExec e WMI

Essa regra bloqueia a execução de processos criados [por meio do PsExec](https://docs.microsoft.com/sysinternals/downloads/psexec) e [do WMI.](https://docs.microsoft.com/windows/win32/wmisdk/about-wmi) Tanto o PsExec quanto o WMI podem executar o código remotamente, portanto, há um risco de malware abusando dessa funcionalidade para fins de comando e controle ou para propagar uma infecção em toda a rede de uma organização.

> [!WARNING]
> Use essa regra somente se você estiver gerenciando seus dispositivos com [o Intune](https://docs.microsoft.com/intune) ou outra solução MDM. Essa regra é incompatível com o gerenciamento por meio do [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr) porque essa regra bloqueia comandos WMI que o cliente configuration Manager usa para funcionar corretamente.

Esta regra foi introduzida em: 
- [Windows 10, versão 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, versão 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Nome do Intune: `Process creation from PSExec and WMI commands`

Nome do Gerenciador de Configurações: Não aplicável

GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>Bloquear processos não assinados e não assinados que são executados a partir do USB

Com essa regra, os administradores podem impedir a execução de arquivos executáveis não assinados ou não-não-assinados de unidades removíveis USB, incluindo cartões SD. Os tipos de arquivo bloqueados incluem arquivos executáveis (como .exe, .dll ou .scr)

Esta regra foi introduzida em: 
- [Windows 10, versão 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, versão 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nome do Intune: `Untrusted and unsigned processes that run from USB`

Nome do Gerenciador de Configurações: `Block untrusted and unsigned processes that run from USB`

GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

### <a name="block-win32-api-calls-from-office-macros"></a>Bloquear chamadas de API Win32 de macros do Office

Essa regra impede que as macros do VBA chamando APIs win32.

O Office VBA habilita chamadas de API Win32. O malware pode usar esse recurso, como chamar [APIs do Win32](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) para iniciar o shellcode mal-intencionado sem escrever nada diretamente no disco. A maioria das organizações não depende da capacidade de chamar APIs win32 em seu funcionamento do dia a dia, mesmo que elas usem macros de outras maneiras.

Esta regra foi introduzida em:
- [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versão 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nome do Intune: `Win32 imports from Office macro code`

Nome do Gerenciador de Configurações: `Block Win32 API calls from Office macros`

GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`

### <a name="use-advanced-protection-against-ransomware"></a>Usar proteção avançada contra ransomware

Essa regra fornece uma camada extra de proteção contra ransomware. Ele verifica os arquivos executáveis que entram no sistema para determinar se eles são confiáveis. Se os arquivos se parecem muito com ransomware, essa regra os impede de ser executados, a menos que eles estão em uma lista confiável ou em uma lista de exclusão.

> [!NOTE]
> Você deve [habilitar a proteção entregue na nuvem](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) para usar essa regra.

Esta regra foi introduzida em: 
- [Windows 10, versão 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, versão 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

Nome do Intune: `Advanced ransomware protection`

Nome do Gerenciador de Configurações: `Use advanced protection against ransomware`

GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`

## <a name="see-also"></a>Confira também

- [Perguntas frequentes sobre redução de superfície de ataque](attack-surface-reduction-faq.md)
- [Habilitar regras de redução de superfície de ataque](enable-attack-surface-reduction.md)
- [Avaliar regras de redução de superfície de ataque](evaluate-attack-surface-reduction.md)
- [Compatibilidade do Microsoft Defender Antivírus com outras soluções antivírus/antimalware](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
