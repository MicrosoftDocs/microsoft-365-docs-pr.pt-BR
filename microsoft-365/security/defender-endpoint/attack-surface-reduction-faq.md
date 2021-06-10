---
title: Redução de superfície de ataque perguntas frequentes (perguntas frequentes)
description: Encontre respostas para perguntas frequentes sobre o Microsoft Defender para as regras de redução de superfície de ataque do Endpoint.
keywords: Regras de redução de superfície de ataque, asr, quadris, sistema de prevenção contra invasões de host, regras de proteção, antiexploit, exploração, prevenção de infecção, microsoft defender para ponto de extremidade
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: martyav
ms.author: v-maave
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 56d4ac95ab49310cc5fc74168158672e7a0d65d1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843217"
---
# <a name="attack-surface-reduction-frequently-asked-questions-faq"></a>Redução de superfície de ataque perguntas frequentes (perguntas frequentes)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="is-attack-surface-reduction-asr-part-of-windows"></a>A redução de superfície de ataque (ASR) faz parte Windows?

O ASR era originalmente um recurso do pacote de recursos do exploit guard introduzido como uma grande atualização para Microsoft Defender Antivírus, Windows 10 versão 1709. Microsoft Defender Antivírus é o componente antimalware nativo do Windows. No entanto, o conjunto de recursos ASR completo só está disponível com uma Windows corporativa. Observe também que as exclusões de regra ASR são gerenciadas separadamente Microsoft Defender Antivírus exclusões.

## <a name="do-i-need-to-have-an-enterprise-license-to-run-asr-rules"></a>Preciso ter uma licença corporativa para executar regras ASR?

O conjunto completo de regras e recursos ASR só é suportado se você tiver uma licença corporativa para Windows 10. Um número limitado de regras pode funcionar sem uma licença corporativa. Se você tiver Microsoft 365 Business, desem conjunto Microsoft Defender Antivírus como sua solução de segurança principal e habilita as regras por meio do PowerShell. O uso do ASR sem uma licença corporativa não tem suporte oficial e você não poderá usar os recursos completos do ASR.

Para saber mais sobre Windows licenciamento, consulte [Windows 10 Licenciamento](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) e obter o [guia licenciamento por volume para Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).

## <a name="is-asr-supported-if-i-have-an-e3-license"></a>O ASR tem suporte se eu tiver uma licença E3?

Sim. O ASR é suportado para Windows Enterprise E3 e acima. 

## <a name="which-features-are-supported-with-an-e5-license"></a>Quais recursos são suportados com uma licença E5?

Todas as regras suportadas com o E3 também são suportadas com o E5.

O E5 adiciona maior integração com o Defender para Ponto de Extremidade. Com o E5, você pode exibir alertas em tempo real, ajustar exclusões de regras, configurar regras ASR e exibir listas de relatórios de eventos.

## <a name="what-are-the-currently-supported-asr-rules"></a>Quais são as regras ASR atualmente suportadas?
Atualmente, o ASR dá suporte a todas as regras abaixo.

## <a name="what-rules-to-enable-all-or-can-i-turn-on-individual-rules"></a>Quais regras habilitar? Tudo ou posso ativar regras individuais?
Para ajudá-lo a descobrir o que é melhor para seu ambiente, recomendamos que você habilita as regras ASR no [modo de auditoria.](audit-windows-defender.md) Com essa abordagem, você determinará o possível afeta a sua organização. Por exemplo, seus aplicativos de linha de negócios.

## <a name="how-do-asr-rules-exclusions-work"></a>Como funcionam as exclusões de regras ASR?
Para regras ASR, se você adicionar uma exclusão, ela afetará cada regra ASR.
As duas regras específicas a seguir não suportam exclusões:

|Nome da regra|GUID|Exclusões & de pastas de arquivo|
|:--|:--|:--|
|Bloquear JavaScript ou VBScript de iniciar conteúdo executável baixado|D3E037E1-3EB8-44C8-A917-57927947596D|Sem suporte|
|Bloquear a persistência por meio da assinatura de evento WMI|e6db77e5-3df2-4cf1-b95a-636979351e5b|Sem suporte|

As exclusões de regras ASR suportam curingas, caminhos e variáveis ambientais. Para obter mais informações sobre como usar caracteres curinga em regras ASR, consulte [configure and validate exclusions based on file extension and folder location](/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus).

Esteja ciente dos itens a seguir sobre exclusões de regras ASR (incluindo curingas e env. variables):

- As exclusões de regras ASR são independentes das exclusões do Defender AV
- Caracteres curinga não podem ser usados para definir uma letra de unidade
- Se você quiser excluir mais de uma pasta, em um caminho, use várias instâncias de \ para indicar várias pastas \* aninhadas (por exemplo, c:\Folder \* \* \Test)
- Microsoft Endpoint Configuration Manager não *suporta* caracteres curinga (* ou ?)
- Se você quiser excluir um arquivo que contém caracteres aleatórios (geração de arquivos automatizados), você pode usar o símbolo '?' (por exemplo, C:\Folder\fileversion?.docx)
- As exclusões de ASR na Política de Grupo não suportam aspas (o mecanismo tratará, na verdade, caminho longo, espaços etc., para que não haja necessidade de usar aspas)
- As regras ASR são executados em conta NT AUTHORITY\SYSTEM, portanto, as variáveis ambientais são limitadas às variáveis do computador.

## <a name="how-do-i-know-what-i-need-to-exclude"></a>Como faço para saber o que preciso excluir?
Regras ASR diferentes terão fluxos de proteção diferentes. Pense sempre em qual regra ASR você está configurando protege e como o fluxo de execução real se destaca.

Exemplo **Windows:** Bloquear o roubo de credenciais do subsistema de autoridade de segurança local A leitura diretamente do processo LSASS (Local Security Authority Subsystem) pode ser um risco de segurança, pois pode expor credenciais corporativas.

Essa regra impede que os processos nãotrudos tenham acesso direto à memória LSASS. Sempre que um processo tentar usar a função OpenProcess() para acessar o LSASS, com um direito de acesso de PROCESS_VM_READ, a regra bloqueará especificamente esse direito de acesso.

:::image type="content" source="images/asrfaq1.png" alt-text="bloquear o roubo de credenciais LSASS":::

Ao ver o exemplo acima, se você realmente tivesse que criar uma exceção para o processo em que o direito de acesso foi bloqueado, adicionar o nome do arquivo juntamente com o caminho completo o excluiria de ser bloqueado e, depois de ter permissão para acessar a memória do processo LSASS. O valor de 0 significa que as regras ASR ignorarão esse arquivo/processo e não o bloquearão/auditarão.

:::image type="content" source="images/asrfaq2.png" alt-text="excluir arquivos asr":::

## <a name="what-are-the-rules-microsoft-recommends-enabling"></a>Quais são as regras que a Microsoft recomenda ativar?

Recomendamos habilenciar todas as regras possíveis. No entanto, há alguns casos em que você não deve habilitar uma regra. Por exemplo, não recomendamos a habilitação da regra de comandos Bloquear criações de processo provenientes de comandos PSExec e WMI, se você estiver usando o Microsoft Endpoint Configuration Manager (ou, System Center Configuration Manager - SCCM) para gerenciar seus pontos de extremidade.

É altamente recomendável que você leia cada informação específica de regra e/ou avisos, que estão disponíveis em nossa [documentação pública.](/microsoft-365/security/defender-endpoint/attack-surface-reduction.md)
abrangendo vários pilares de proteção, como Office, Credenciais, Scripts, Email, etc. Todas as regras ASR, exceto a persistência de bloqueio por meio da assinatura de evento WMI, são suportadas no Windows 1709 e posterior:

* [Bloquear conteúdo executável do cliente de email e do webmail](attack-surface-reduction.md#block-executable-content-from-email-client-and-webmail)
* [Bloquear todos os Office aplicativos da criação de processos filho](attack-surface-reduction.md#block-all-office-applications-from-creating-child-processes)
* [Impedir Office aplicativos de criação de conteúdo executável](attack-surface-reduction.md#block-office-applications-from-creating-executable-content)
* [Impedir Office aplicativos de injetar código em outros processos](attack-surface-reduction.md#block-office-applications-from-injecting-code-into-other-processes)
* [Bloquear JavaScript ou VBScript de iniciar conteúdo executável baixado](attack-surface-reduction.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content)
* [Bloquear a execução de scripts potencialmente ofuscados](attack-surface-reduction.md#block-execution-of-potentially-obfuscated-scripts)
* [Bloquear chamadas de API Win32 de Office macro](attack-surface-reduction.md#block-win32-api-calls-from-office-macros)
* [Usar proteção avançada contra ransomware](attack-surface-reduction.md#use-advanced-protection-against-ransomware)
* [Bloquear o roubo de credenciais do subsistema Windows autoridade de segurança local](attack-surface-reduction.md#block-credential-stealing-from-the-windows-local-security-authority-subsystem) (lsass.exe)
* [Bloquear criações de processo provenientes de comandos PSExec e WMI](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)
* [Bloquear processos não assinados e não assinados que são executados a partir do USB](attack-surface-reduction.md#block-untrusted-and-unsigned-processes-that-run-from-usb)
* [Impedir a execução de arquivos executáveis, a menos que eles atendem a uma prevalência, idade ou critérios de lista confiáveis](attack-surface-reduction.md#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)
* [Bloquear Office de comunicação da criação de processos filho](attack-surface-reduction.md#block-office-communication-application-from-creating-child-processes)
* [Impedir o Adobe Reader de criar processos filho](attack-surface-reduction.md#block-adobe-reader-from-creating-child-processes)
* [Bloquear a persistência por meio da assinatura de evento WMI](attack-surface-reduction.md#block-persistence-through-wmi-event-subscription)

## <a name="what-are-some-good-recommendations-for-getting-started-with-asr"></a>Quais são algumas boas recomendações para começar com o ASR?

Teste como as regras ASR afetarão sua organização antes de habilita-las executando regras ASR no modo de auditoria por um breve período de tempo. Enquanto estiver executando as regras no modo de auditoria, você pode identificar todos os aplicativos de linha de negócios que possam ser bloqueados erroneamente e excluí-las do ASR.

As organizações maiores devem considerar a implantação de regras ASR em "anéis", auditando e habilitando regras em subconjuntos cada vez mais amplos de dispositivos. Você pode organizar os dispositivos da sua organização em anéis usando o Intune ou uma ferramenta de gerenciamento de Política de Grupo.

## <a name="how-long-should-i-test-an-asr-rule-in-audit-mode-before-enabling-it"></a>Por quanto tempo devo testar uma regra ASR no modo de auditoria antes de habilita-la?

Mantenha a regra no modo de auditoria por cerca de 30 dias para obter uma boa linha de base de como a regra funcionará depois que ela for ao vivo em toda a sua organização. Durante o período de auditoria, você pode identificar todos os aplicativos de linha de negócios que podem ser bloqueados pela regra e configurar a regra para exclui-los.

## <a name="im-making-the-switch-from-a-third-party-security-solution-to-defender-for-endpoint-is-there-an-easy-way-to-export-rules-from-another-security-solution-to-asr"></a>Estou fazendo a troca de uma solução de segurança de terceiros para o Defender para o Ponto de Extremidade. Existe uma maneira "fácil" de exportar regras de outra solução de segurança para o ASR?

Na maioria dos casos, é mais fácil e melhor começar com as recomendações de linha de base sugeridas pelo [Defender para](/windows/security/threat-protection) Ponto de Extremidade do que tentar importar regras de outra solução de segurança. Em seguida, use ferramentas como modo de auditoria, monitoramento e análise para configurar sua nova solução para atender às suas necessidades exclusivas. 

A configuração padrão para a maioria das regras ASR, combinada com o Defender para proteção em tempo real do Endpoint, protegerá contra um grande número de explorações e vulnerabilidades.

De dentro do Defender para Ponto de Extremidade, você pode atualizar suas defesas com indicadores personalizados, para permitir e bloquear determinados comportamentos de software. O ASR também permite alguma personalização de regras, na forma de exclusões de arquivo e pasta. Como regra geral, é melhor auditar uma regra por um período de tempo e configurar exclusões para todos os aplicativos de linha de negócios que podem ser bloqueados.

## <a name="does-asr-support-file-or-folder-exclusions-that-include-system-variables-and-wildcards-in-the-path"></a>O ASR dá suporte a exclusões de arquivo ou pasta que incluem variáveis do sistema e caracteres curinga no caminho?

Sim. Consulte Excluindo arquivos e pastas de regras [ASR](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) para obter mais detalhes sobre como excluir arquivos ou pastas de regras ASR e Configurar e validar exclusões com base na extensão de arquivo e no local da pasta para obter mais informações sobre como usar variáveis do sistema e curingas em caminhos de arquivo [excluídos.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

## <a name="do-asr-rules-cover-all-applications-by-default"></a>As regras ASR abrangem todos os aplicativos por padrão?

Depende da regra. A maioria das regras asR abrange o comportamento de Microsoft Office e serviços, como Word, Excel, PowerPoint e OneNote ou Outlook. Determinadas regras ASR, como Bloquear a execução de scripts potencialmente *ofuscados,* são mais gerais no escopo.

## <a name="does-asr-support-third-party-security-solutions"></a>O ASR oferece suporte a soluções de segurança de terceiros?

ASR usa Microsoft Defender Antivírus para bloquear aplicativos. Não é possível configurar o ASR para usar outra solução de segurança para bloqueio no momento.

## <a name="i-have-an-e5-license-and-enabled-some-asr-rules-in-conjunction-with-defender-for-endpoint-is-it-possible-for-an-asr-event-to-not-show-up-at-all-in-defender-for-endpoints-event-timeline"></a>Tenho uma licença E5 e habilitadas algumas regras ASR em conjunto com o Defender para Ponto de Extremidade. É possível um evento ASR não aparecer na linha do tempo do evento do Defender for Endpoint?

Sempre que uma notificação é disparada localmente por uma regra ASR, um relatório sobre o evento também é enviado para o portal do Defender para Ponto de Extremidade. Se você estiver com problemas para encontrar o evento, poderá filtrar a linha do tempo de eventos usando a caixa de pesquisa. Você também pode exibir eventos ASR visitando **Ir**  para o gerenciamento de superfície de ataque , a partir do ícone de gerenciamento de configuração na barra de tarefas do Centro de Segurança. A página de gerenciamento de superfície de ataque inclui uma guia para detecções de relatório, que inclui uma lista completa de eventos de regra ASR relatados ao Defender for Endpoint.

## <a name="i-applied-a-rule-using-gpo-now-when-i-try-to-check-the-indexing-options-for-the-rule-in-microsoft-outlook-i-get-a-message-stating-access-denied"></a>Apliquei uma regra usando GPO. Agora, quando tento verificar as opções de indexação da regra no Microsoft Outlook, eu receber uma mensagem informando: "Acesso negado".

Tente abrir as opções de indexação diretamente Windows 10.

1. Selecione o **ícone Pesquisar** na barra de Windows de tarefas.

1. Insira **opções de indexação** na caixa de pesquisa.

## <a name="are-the-criteria-used-by-the-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-configurable-by-an-admin"></a>Os critérios usados pela regra são "Impedir a execução de arquivos executáveis, a menos que eles atendem a um critério de lista de prevalência, idade ou lista confiável", configurável por um administrador?

Não. Os critérios usados por essa regra são mantidos pela proteção de nuvem da Microsoft, para manter a lista confiável constantemente atualizada com dados coletados de todo o mundo. Os administradores locais não têm acesso a gravação para alterar esses dados. Se você estiver procurando configurar essa regra para adaptá-la para sua empresa, você pode adicionar determinados aplicativos à lista de exclusões para impedir que a regra seja disparada.

## <a name="i-enabled-the-asr-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-after-some-time-i-updated-a-piece-of-software-and-the-rule-is-now-blocking-it-even-though-it-didnt-before-did-something-go-wrong"></a>Habilitada a regra ASR, bloquei a execução de arquivos *executáveis, a* menos que eles atendem a uma prevalência, idade ou critério de lista confiável. Depois de algum tempo, atualizei um software, e a regra agora o está bloqueando, mesmo que não tenha passado. Algo deu errado?

Essa regra se baseia em cada aplicativo com uma reputação conhecida, medida por prevalência, idade ou inclusão em uma lista de aplicativos confiáveis. A decisão da regra de bloquear ou permitir um aplicativo é determinada, em última análise, pela avaliação desses critérios pela Proteção de Nuvem da Microsoft.

Normalmente, a proteção na nuvem pode determinar que uma nova versão de um aplicativo é semelhante o suficiente às versões anteriores que não precisam ser reavaliadas com comprimento. No entanto, pode levar algum tempo para o aplicativo criar reputação depois de alternar versões, especialmente após uma atualização importante. Enquanto isso, você pode adicionar o aplicativo à lista de exclusões, para impedir que essa regra bloquee aplicativos importantes. Se você estiver atualizando com frequência e trabalhando com novas versões de aplicativos, pode optar por executar essa regra no modo de auditoria.

## <a name="i-recently-enabled-the-asr-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-and-i-am-getting-a-large-number-of-notifications-what-is-going-on"></a>Habilitada recentemente a regra ASR Windows, bloquei o roubo de credenciais do subsistema de autoridade de segurança *local (lsass.exe)* e estou recebendo um grande número de notificações. O que está acontecendo?

Uma notificação gerada por essa regra não indica necessariamente atividade mal-intencionada; no entanto, essa regra ainda é útil para bloquear atividades mal-intencionadas, já que o malware geralmente lsass.exe para obter acesso ilícito a contas. O lsass.exe armazena credenciais de usuário na memória depois que um usuário faz logove. Windows usa essas credenciais para validar usuários e aplicar políticas de segurança locais.

Como muitos processos legítimos ao longo de um dia típico estarão chamando no lsass.exe para credenciais, essa regra pode ser especialmente barulhento. Se um aplicativo legítimo conhecido faz com que essa regra gere um número excessivo de notificações, você pode adicioná-la à lista de exclusão. A maioria das outras regras ASR gerará um número relativamente menor de notificações, em comparação com essa, já que chamar o lsass.exe é típico do funcionamento normal de muitos aplicativos.

## <a name="is-it-a-good-idea-to-enable-the-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-alongside-lsa-protection"></a>É uma boa ideia habilitar a regra, bloquear o roubo de credenciais do subsistema Windows autoridade de segurança *local (lsass.exe),* juntamente com a proteção LSA?

Habilitar essa regra não fornecerá proteção adicional se você também tiver a [proteção LSA](/windows-server/security/credentials-protection-and-management/configuring-additional-lsa-protection#BKMK_HowToConfigure) habilitada. Tanto a regra quanto a proteção LSA funcionam da mesma maneira, portanto, ter ambos em execução ao mesmo tempo seria redundante. No entanto, às vezes, talvez você não consiga habilitar a proteção LSA. Nesses casos, você pode habilitar essa regra para fornecer proteção equivalente contra malwares destinados lsass.exe.

## <a name="see-also"></a>Confira também

* [Visão geral da redução de superfície de ataque](attack-surface-reduction.md)
* [Avaliar as regras da redução da superfície de ataque](evaluate-attack-surface-reduction.md)
* [Personalizar regras da redução da superfície de ataque](customize-attack-surface-reduction.md)
* [Habilitar regras da redução da superfície de ataque](enable-attack-surface-reduction.md)
* [Compatibilidade do Microsoft Defender com outro antivírus/antimalware](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)


