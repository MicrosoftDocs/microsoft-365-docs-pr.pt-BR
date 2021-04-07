---
title: Novidades no Microsoft Defender para Ponto de Extremidade para Mac
description: Saiba mais sobre as principais alterações para versões anteriores do Microsoft Defender para Ponto de Extremidade para Mac.
keywords: microsoft, defender, atp, mac, installation, macos, whatsnew
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5cd1f64d006b5462634dd47df9083e1a89db0e8c
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615202"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-mac"></a>Novidades no Microsoft Defender para Ponto de Extremidade para Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> No macOS 11 (Big Sur), o Microsoft Defender para Endpoint requer perfis de configuração adicionais. Se você for um cliente existente atualizando de versões anteriores do macOS, certifique-se de implantar os perfis de configuração adicionais listados [nesta página](mac-sysext-policies.md).

## <a name="1012569-20121022125690"></a>101.25.69 (20.121022.12569.0)

- O Microsoft Defender para Ponto de Extremidade para Mac agora está disponível em versão prévia para clientes do Governo dos EUA. Para obter mais informações, consulte [Microsoft Defender for Endpoint for US Government customers](gov.md).
- Melhorias de desempenho (especificamente para a situação quando o aplicativo XCode Simulator é usado) & correções de bugs

## <a name="1012364-20121021123640"></a>101.23.64 (20.121021.12364.0)

- Adicionada uma nova opção à ferramenta de linha de comando para exibir informações sobre a última verificação sob demanda. Para exibir informações sobre a última verificação sob demanda, execute `mdatp health --details antivirus`
- Melhorias de desempenho & correções de bugs

## <a name="1012279-20121012122790"></a>101.22.79 (20.121012.12279.0)

- Melhorias de desempenho & correções de bugs

## <a name="1011988-20121011119880"></a>101.19.88 (20.121011.11988.0)

- Melhorias de desempenho & correções de bugs

## <a name="1011948-20120121119480"></a>101.19.48 (20.120121.11948.0)

> [!NOTE]
> A sintaxe da ferramenta de linha de comando antiga foi preterida com essa versão. Para obter informações sobre a nova sintaxe, consulte [Resources](mac-resources.md#configuring-from-the-command-line).

- Adicionada uma nova opção de linha de comando para desabilitar a extensão de rede: `mdatp system-extension network-filter disable` . Esse comando pode ser útil para solucionar problemas de rede que podem estar relacionados ao Microsoft Defender para Ponto de Extremidade para Mac
- Melhorias de desempenho & correções de bugs

## <a name="1011921-20120101119210"></a>101.19.21 (20.120101.11921.0)

- Correções de bugs

## <a name="1011526-20120102115260"></a>101.15.26 (20.120102.11526.0)

- Melhorou a confiabilidade do agente ao executar no macOS 11 Big Sur
- Adicionada uma nova opção de linha de comando ( `--ignore-exclusions` ) para ignorar exclusões av durante verificações personalizadas ( `mdatp scan custom` )
- Melhorias de desempenho & correções de bugs

## <a name="1011375-20120101113750"></a>101.13.75 (20.120101.11375.0)

- Condições removidas quando o Microsoft Defender for Endpoint estava disparando um bug do macOS 11 (Big Sur) que se manifestou em um pânico do kernel
- Correção de um vazamento de memória na extensão do sistema de Segurança do Ponto de Extremidade ao ser executado no mac 11 (Big Sur)
- Correções de bugs

## <a name="1011072"></a>101.10.72

- Correções de bugs

## <a name="1010961"></a>101.09.61

- Adicionada uma nova preferência gerenciada [para desabilitar a opção de enviar comentários](mac-preferences.md#show--hide-option-to-send-feedback)
- O ícone do menu Status agora mostra um estado ável quando as configurações do produto são gerenciadas. Anteriormente, o ícone do menu de status exibia um estado de aviso ou erro, mesmo que as configurações do produto fossem gerenciadas pelo administrador
- Melhorias de desempenho & correções de bugs

## <a name="1010950"></a>101.09.50

- Esta versão do produto foi validada no macOS Big Sur 11 beta 9

- A nova sintaxe da ferramenta `mdatp` de linha de comando agora é a padrão. Para obter mais informações sobre a nova sintaxe, consulte [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md#configuring-from-the-command-line)

  > [!NOTE]
  > A sintaxe da ferramenta de linha de comando antiga será removida do produto em 1º de janeiro de **2021**.

- Estendido com um novo parâmetro ( ) que permite que os logs de `mdatp diagnostic create` diagnóstico sejam salvos em um diretório `--path [directory]` diferente
- Melhorias de desempenho & correções de bugs

## <a name="1010949"></a>101.09.49

- Melhorias na interface do usuário para diferenciar exclusões gerenciadas pelo administrador de IT versus exclusões definidas pelo usuário local
- Utilização aprimorada da CPU durante verificações sob demanda
- Melhorias de desempenho & correções de bugs

## <a name="1010723"></a>101.07.23

- Adicionados novos campos à saída de para verificar o status do modo passivo e a `mdatp --health` ID do grupo EDR

  > [!NOTE]
  > `mdatp --health` será substituído por em `mdatp health` uma atualização futura do produto.

- Correção de um bug em que o envio automático de amostra não foi marcado como gerenciado na interface do usuário
- Adicionadas novas configurações para controlar a retenção de itens no histórico de verificação de antivírus. Agora você pode [especificar o número de dias para reter](mac-preferences.md#antivirus-scan-history-retention-in-days) itens no histórico de verificação e especificar o número máximo de itens no histórico de [verificação](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)
- Correções de bugs

## <a name="1010663"></a>101.06.63

- Abordamos uma regressão de desempenho introduzida na versão `101.05.17` . A regressão foi introduzida com a correção para eliminar os problemas de kernel que alguns clientes observaram ao acessar compartilhamentos SMB. Revertemos essa alteração de código e estamos investigando maneiras alternativas de eliminar os pânicos do kernel.

## <a name="1010517"></a>101.05.17

> [!IMPORTANT]
> Estamos trabalhando em uma sintaxe nova e aprimorada para a `mdatp` ferramenta de linha de comando. A nova sintaxe é atualmente o padrão nos canais de atualização Insider Fast e Insider Slow. Recomendamos que você famliliarize a si mesmo com essa nova sintaxe.
> 
> Continuaremos dando suporte à sintaxe antiga em paralelo com a nova sintaxe e forneceremos mais comunicação em torno do plano de prevaleção para a sintaxe antiga nos próximos meses.

- Resolvido um pânico do kernel que ocorreu às vezes ao acessar compartilhamentos de arquivos SMB
- Melhorias de desempenho & correções de bugs

## <a name="1010516"></a>101.05.16

- Melhorias na lógica de verificação rápida para reduzir significativamente o número de arquivos verificados
- Adicionado [suporte de autocompleção](mac-resources.md#how-to-enable-autocompletion) para a ferramenta de linha de comando
- Correções de bugs

## <a name="1010312"></a>101.03.12

- Melhorias de desempenho & correções de bugs

## <a name="1010154"></a>101.01.54

- Melhorias em relação à compatibilidade com o Time Machine
- Melhorias de acessibilidade
- Melhorias de desempenho & correções de bugs

## <a name="1010031"></a>101.00.31

- Experiência [aprimorada de integração de produtos para usuários do Intune](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)
- As [exclusões de antivírus agora suportam curingas](mac-exclusions.md#supported-exclusion-types)
- Adicionada a capacidade de disparar verificações antivírus do menu contextual do macOS. Agora você pode clicar com o botão direito do mouse em um arquivo ou uma pasta no Finder e selecionar **Verificar com o Microsoft Defender para Ponto de Extremidade**
- As rebaixamentos in-locar do produto agora são explicitamente não permitidos pelo instalador. Se você precisar fazer downgrade, primeiro desinstale a versão existente e reconfigure seu dispositivo
- Outras melhorias de desempenho & correções de bugs

## <a name="1009027"></a>100.90.27

- Agora você pode [definir um canal de](mac-updates.md#set-the-channel-name) atualização para o Microsoft Defender para Ponto de Extremidade para Mac diferente do canal de atualização em todo o sistema
- Novo ícone do produto
- Outras melhorias na experiência do usuário
- Correções de bugs

## <a name="1008692"></a>100.86.92

- Melhorias em relação à compatibilidade com o Time Machine
- Resolvido um problema em que o produto às vezes não limpava todos os arquivos `/Library/Application Support/Microsoft/Defender` durante a desinstalação
- Redução da utilização da CPU do produto quando os produtos Microsoft são atualizados por meio do Microsoft AutoUpdate
- Outras melhorias de desempenho & correções de bugs

## <a name="1008691"></a>100.86.91

> [!CAUTION]
> Para garantir a proteção mais completa para seus dispositivos macOS e em alinhamento com a Apple interrompendo a entrega de atualizações de segurança nativas do macOS para versões do sistema operacional anteriores [atual – 2], a implantação e as atualizações do MDATP para Mac não terão mais suporte no macOS Sierra [10.12]. As atualizações e aprimoramentos do MDATP para Mac serão entregues aos dispositivos que executam as versões Catalina [10.15], Mojave [10.14], e High Sierra [10.13]. 
>
> Se você já tiver o MDATP para Mac implantado em seus dispositivos Sierra [10.12], atualize para a versão mais recente do macOS para eliminar os riscos de perda de proteção.

- Melhorias de desempenho & correções de bugs

## <a name="1008373"></a>100.83.73

- Adicionado mais controles para [](mac-preferences.md#exclusion-merge-policy)administradores de IT em torno do gerenciamento de exclusões, [gerenciamento](mac-preferences.md#threat-type-settings-merge-policy)de configurações de tipo de ameaça e ações de ameaças [não permitidos](mac-preferences.md#disallowed-threat-actions)
- Quando o Acesso a Disco Completo não está habilitado no dispositivo, um aviso agora é exibido no menu de status
- Melhorias de desempenho & correções de bugs

## <a name="1008260"></a>100.82.60

- Resolvido um problema em que o produto não consegue começar a seguir uma atualização de definição.

## <a name="1008042"></a>100.80.42

- Correções de bugs

## <a name="1007942"></a>100.79.42

- Corrigido um problema em que o Microsoft Defender para Ponto de Extremidade para Mac estava, às vezes, interferendo com o Time Machine
- Adicionada uma nova opção ao utilitário de linha de comando para testar a conectividade com o serviço back-end
  ```bash
  mdatp connectivity test
  ```
- Adicionada a capacidade de exibir o histórico completo de ameaças na interface do usuário (pode ser acessada a partir do visualização **histórico de** proteção)
- Melhorias de desempenho & correções de bugs

## <a name="1007215"></a>100.72.15

- Correções de bugs

## <a name="1007099"></a>100.70.99

- Resolvido um problema que afeta a capacidade de alguns usuários atualizarem para o macOS Catalina quando a proteção em tempo real está habilitada. Esse problema esporádico foi causado pelo Microsoft Defender para arquivos de bloqueio de ponto de extremidade no pacote de atualização de Catalina enquanto os examinou em busca de ameaças, o que resultou em falhas na sequência de atualização.

## <a name="1006899"></a>100.68.99

- Adicionada a capacidade de configurar a funcionalidade antivírus para ser executado no [modo passivo](mac-preferences.md#enable--disable-passive-mode)
- Melhorias de desempenho & correções de bugs

## <a name="1006528"></a>100.65.28

- Adicionado suporte para macOS Catalina

  > [!CAUTION]
  > O macOS 10.15 (Catalina) contém novos aprimoramentos de segurança e privacidade. A partir dessa versão, por padrão, os aplicativos não são capazes de acessar determinados locais no disco (como Documentos, Downloads, Área de Trabalho, etc.) sem consentimento explícito. Na ausência desse consentimento, o Microsoft Defender para Ponto de Extremidade não é capaz de proteger totalmente seu dispositivo.
  >
  > O mecanismo para conceder esse consentimento depende de como você implantou o Microsoft Defender para o Ponto de Extremidade:
  >
  > - Para implantações manuais, consulte as instruções atualizadas no [tópico implantação manual.](mac-install-manually.md#how-to-allow-full-disk-access)
  > - Para implantações gerenciadas, consulte as instruções atualizadas nos tópicos de implantação baseada em [JAMF](mac-install-with-jamf.md) e implantação baseada no [Microsoft Intune.](mac-install-with-intune.md#create-system-configuration-profiles)

- Melhorias de desempenho & correções de bugs
