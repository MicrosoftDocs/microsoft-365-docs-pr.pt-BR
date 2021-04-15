---
title: Microsoft Defender Antivírus no aplicativo segurança do Windows
description: Com o Microsoft Defender Antivírus agora incluído no aplicativo segurança do Windows, você pode revisar, comparar e executar tarefas comuns.
keywords: wdav, antivírus, firewall, segurança, windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7635209c03dfc0367df16bfb650a4e52d2b2b3f8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765318"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a>Microsoft Defender Antivírus no aplicativo segurança do Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

No Windows 10, versão 1703 e posterior, o aplicativo Windows Defender faz parte da Segurança do Windows.

As configurações que antes eram parte do cliente Windows Defender e das configurações principais do Windows foram combinadas e movidas para o novo aplicativo, que é instalado por padrão como parte do Windows 10, versão 1703.

> [!IMPORTANT]
> Desabilitar o serviço da Central de Segurança do Windows não desabilita o Microsoft Defender Antivírus [ou Windows Defender Firewall.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) Eles são desabilitados automaticamente quando um produto antivírus ou firewall de terceiros é instalado e mantido atualizado.
>
> Se você desabilitar o serviço da Central de Segurança do Windows ou configurar suas configurações de Política de Grupo associadas para impedir que ele seja acionada ou em execução, o aplicativo de Segurança do Windows poderá exibir informações desproportivas ou imprecisas sobre qualquer antivírus ou produtos de firewall que você instalou no dispositivo.
> Ele também pode impedir que o Microsoft Defender Antivírus se habilita se você tiver um antivírus de terceiros antigo ou desatualizado ou se você desinstalar qualquer produto antivírus de terceiros que você possa ter instalado anteriormente.
> Isso diminuirá significativamente a proteção do dispositivo e poderá levar a infecção por malware.

Consulte o [artigo segurança do Windows](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) para obter mais informações sobre outros recursos de segurança do Windows que podem ser monitorados no aplicativo.

O aplicativo segurança do Windows é uma interface do cliente no Windows 10, versão 1703 e posterior. Não é o portal da Central de Segurança do Microsoft Defender que é usado para revisar e gerenciar [o Microsoft Defender para o Ponto de Extremidade.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a>Revisar configurações de proteção contra vírus e ameaças no aplicativo segurança do Windows

![Captura de tela do rótulo de configurações de proteção contra & vírus no aplicativo segurança do Windows](images/defender/wdav-protection-settings-wdsc.png)

1. Abra o aplicativo segurança do Windows clicando no ícone de escudo na barra de tarefas ou pesquisando o menu inicial do **Defender**.

2. Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).
   
As seções a seguir descrevem como executar algumas das tarefas mais comuns ao revisar ou interagir com a proteção contra ameaças fornecida pelo Microsoft Defender Antivírus no aplicativo segurança do Windows.

> [!NOTE]
> Se essas configurações são configuradas e implantadas usando a Política de Grupo, as configurações descritas nesta seção serão acinzenadas e indisponíveis para uso em pontos de extremidade individuais. As alterações feitas por meio de um Objeto de Política de Grupo devem primeiro ser implantadas em pontos de extremidade individuais antes que a configuração seja atualizada nas Configurações do Windows. O [tópico Configurar interação do usuário final com o Microsoft Defender Antivírus](configure-end-user-interaction-microsoft-defender-antivirus.md) descreve como as configurações de substituição de política local podem ser configuradas.

## <a name="run-a-scan-with-the-windows-security-app"></a>Executar uma verificação com o aplicativo segurança do Windows

1. Abra o aplicativo segurança do Windows pesquisando o menu iniciar para **Segurança** e, em seguida, selecionando **Segurança do Windows**.

2. Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).

3. Selecione **Verificação rápida**. Ou, para executar uma verificação completa, selecione **Opções de** verificação e selecione uma opção, como **Verificação completa**.

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a>Revise a versão de atualização de inteligência de segurança e baixe as atualizações mais recentes no aplicativo segurança do Windows

![Informações sobre o número da versão de inteligência de segurança](images/defender/wdav-wdsc-defs.png)

1. Abra o aplicativo segurança do Windows pesquisando o menu iniciar para *Segurança* e, em seguida, selecionando **Segurança do Windows**.

2. Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).

3. Selecione **Atualizações & proteção contra ameaças de vírus.** A versão instalada no momento é exibida juntamente com algumas informações sobre quando ela foi baixada. Você pode verificar o seu atual em relação à versão mais recente disponível para download manual ou revisar o log de alterações para essa versão. Consulte [Atualizações de inteligência de segurança para o Microsoft Defender Antivírus e outros antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)da Microsoft.

4. Selecione **Verificar se há atualizações para** baixar novas atualizações de proteção (se houver alguma).

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a>Verifique se o Microsoft Defender Antivírus está habilitado no aplicativo segurança do Windows

1. Abra o aplicativo segurança do Windows pesquisando o menu iniciar para *Segurança* e, em seguida, selecionando **Segurança do Windows**.

2. Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).

3. Selecione **Configurações & proteção contra ameaças.**

4. Alterne a **opção de proteção em** tempo real para **On**.

    > [!NOTE]
    > Se você desativar **a proteção em tempo real,** ela retornará automaticamente após um curto atraso. Isso é para garantir que você está protegido contra malware e ameaças.
    > Se você instalar outro produto antivírus, o Microsoft Defender Antivírus se desabilitará automaticamente e será indicado como tal no aplicativo segurança do Windows. Aparecerá uma configuração que permitirá que você habilita a [verificação periódica limitada.](limited-periodic-scanning-microsoft-defender-antivirus.md)

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a>Adicionar exclusões para o Microsoft Defender Antivírus no aplicativo segurança do Windows

1. Abra o aplicativo segurança do Windows pesquisando o menu iniciar para *Segurança* e, em seguida, selecionando **Segurança do Windows**.

2. Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).

3. Em Gerenciar **configurações,** selecione **Configurações & proteção** contra ameaças.

4. Na **configuração Exclusões,** selecione **Adicionar ou remover exclusões**. 

5. Selecione o ícone de a mais ( **+** ) para escolher o tipo e definir as opções para cada exclusão. 

A tabela a seguir resume os tipos de exclusão e o que acontece:

|Tipo de exclusão  |Definido por  |O que acontece  |
|---------|---------|---------|
|**Arquivo** |Local <br/>Exemplo: `c:\sample\sample.test` |O arquivo específico é ignorado pelo Microsoft Defender Antivírus. |
|**Folder**    |Local <br/>Exemplo: `c:\test\sample`       |Todos os itens na pasta especificada são ignorados pelo Microsoft Defender Antivírus.         |
|**Tipo de arquivo**   |Extensão de arquivo <br/>Exemplo: `.test` |Todos os arquivos com `.test` a extensão em qualquer lugar do dispositivo são ignorados pelo Microsoft Defender Antivírus.         |
|**Processo**     |Caminho do arquivo executável <br>Exemplo: `c:\test\process.exe`         |O processo específico e todos os arquivos abertos por esse processo são ignorados pelo Microsoft Defender Antivírus.         |

Para saber mais, confira os seguintes recursos:
- [Configurar e validar exclusões com base na extensão de arquivo e no local da pasta](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [Configurar exclusões para arquivos abertos por processos](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a>Revisar o histórico de detecção de ameaças no aplicativo Windows Defender Centro de Segurança

1. Abra o aplicativo segurança do Windows pesquisando o menu iniciar para *Segurança* e, em seguida, selecionando **Segurança do Windows**.

2. Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).

3. Selecione **Histórico de proteção**. Todos os itens recentes estão listados.

## <a name="set-ransomware-protection-and-recovery-options"></a>Definir opções de proteção e recuperação de ransomware

1. Abra o aplicativo segurança do Windows pesquisando o menu iniciar para *Segurança* e, em seguida, selecionando **Segurança do Windows**.

2. Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).

3. Em **Proteção contra ransomware,** selecione **Gerenciar proteção de ransomware**.

4. Para alterar **as configurações de** acesso controlado a pastas, consulte [Protect important folders with Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).

5. Para configurar opções de recuperação de ransomware, selecione Configurar em Recuperação de dados do Ransomware e siga as instruções para vincular ou configurar sua conta do OneDrive para que você possa se recuperar facilmente de um ataque de **ransomware.** 

## <a name="see-also"></a>Confira também
- [Microsoft Defender Antivírus](microsoft-defender-antivirus-in-windows-10.md)