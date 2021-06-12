---
title: Microsoft Defender Antivírus Virtual Desktop Infrastructure guia de implantação
description: Saiba como implantar o Microsoft Defender Antivírus em um ambiente de área de trabalho virtual para o melhor equilíbrio entre proteção e desempenho.
keywords: vdi, hyper-v, vm, máquina virtual, windows defender, antivírus, av, área de trabalho virtual, rds, área de trabalho remota
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/11/2021
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ce200ca12bacc3ae8d9f7b48d36274ca54322586
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908024"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Guia de implantação do Microsoft Defender Antivírus em um ambiente virtual de área de trabalho (VDI)

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Além das configurações locais ou de hardware padrão, você também pode usar o Microsoft Defender Antivírus em um ambiente de infraestrutura de área de trabalho remota (RDS) ou de área de trabalho virtual (VDI).

Consulte [Windows Documentação da Área de Trabalho Virtual](/azure/virtual-desktop) para obter mais detalhes sobre Área de Trabalho Remota da Microsoft Serviços e suporte À VDI.

Para máquinas virtuais baseadas no Azure, consulte [Install Endpoint Protection in Azure Defender](/azure/security-center/security-center-install-endpoint-protection).

Com a capacidade de implantar atualizações facilmente em VMs em execução em VDIs, reduzimos este guia para se concentrar em como você pode obter atualizações em seus máquinas de forma rápida e fácil. Você não precisa mais criar e selar imagens douradas periodicamente, pois as atualizações são expandidas para seus bits de componente no servidor host e baixadas diretamente para a VM quando ela estiver ligada.

Este guia descreve como configurar suas VMs para proteção e desempenho ideais, incluindo como:

- [Configurar um compartilhamento de arquivos VDI dedicado para atualizações de inteligência de segurança](#set-up-a-dedicated-vdi-file-share)
- [Randomizar verificações agendadas](#randomize-scheduled-scans)
- [Usar verificações rápidas](#use-quick-scans)
- [Impedir notificações](#prevent-notifications)
- [Desabilitar verificações de ocorrência após cada atualização](#disable-scans-after-an-update)
- [Examinar máquinas ou máquinas desatentas que estão offline há algum tempo](#scan-vms-that-have-been-offline)
- [Aplicar exclusões](#exclusions)

Você também pode baixar o whitepaper Microsoft Defender Antivírus no [Virtual Desktop Infrastructure](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf), que analisa o novo recurso de atualização de inteligência de segurança compartilhada, além de testes de desempenho e orientações sobre como testar o desempenho do antivírus em sua própria VDI.

> [!IMPORTANT]
> Embora a VDI possa ser hospedada no Windows Server 2012 ou Windows Server 2016, as máquinas virtuais (VMs) devem estar executando o Windows 10, 1607 no mínimo, devido a tecnologias e recursos de proteção maiores que não estão disponíveis em versões anteriores do Windows.<br/>Há melhorias de desempenho e recursos na forma como o Microsoft Defender AV opera em máquinas virtuais no Windows 10 Insider Preview, build 18323 (e posterior). Identificaremos neste guia se você precisar usar uma com build do Insider Preview; se não for especificado, a versão mínima necessária para a melhor proteção e desempenho será Windows 10 1607.

## <a name="set-up-a-dedicated-vdi-file-share"></a>Configurar um compartilhamento de arquivos VDI dedicado

No Windows 10, versão 1903, introduzimos o recurso de inteligência de segurança compartilhada, que descarrega a descompactação de atualizações de inteligência de segurança baixadas em uma máquina host, salvando recursos de CPU, disco e memória anteriores em máquinas individuais. Esse recurso foi reportado e agora funciona Windows 10 versão 1703 ou superior. Você pode definir esse recurso com uma Política de Grupo ou o PowerShell.

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a>Use a Política de Grupo para habilitar o recurso de inteligência de segurança compartilhada:

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de Grupo, clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

3. Clique **em Modelos Administrativos**.

4. Expanda a árvore para **Windows componentes**  >  **Microsoft Defender Antivírus**  >  **Atualizações de Inteligência de Segurança.**

5. Clique duas vezes em Definir local de inteligência de segurança para **clientes VDI** e defina a opção **como Habilitado**. Um campo é exibido automaticamente.

6. Insira `\\<sharedlocation\>\wdav-update` (para ajudar com esse valor, consulte [Baixar e descompactar](#download-and-unpackage-the-latest-updates)).

7. Clique em **OK**.

8. Implante o GPO nas VMs que você deseja testar.

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a>Usar o PowerShell para habilitar o recurso de inteligência de segurança compartilhada

Use o cmdlet a seguir para habilitar o recurso. Em seguida, você precisará pressionar isso, pois normalmente empurraria as políticas de configuração baseadas no PowerShell para as VMs:

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

Consulte a [seção Baixar e descompactar](#download-and-unpackage-the-latest-updates) o \<shared location\> que será.

## <a name="download-and-unpackage-the-latest-updates"></a>Baixar e descompactar as atualizações mais recentes

Agora você pode começar a baixar e instalar novas atualizações. Criamos um exemplo de script do PowerShell para você abaixo. Esse script é a maneira mais fácil de baixar novas atualizações e preparar as VMs. Em seguida, você deve definir o script para ser executado em um determinado momento na máquina de gerenciamento usando uma tarefa agendada (ou, se você estiver familiarizado com o uso de scripts do PowerShell no Azure, Intune ou SCCM, também poderá usar esses scripts).

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

Você pode definir uma tarefa agendada para ser executado uma vez por dia para que sempre que o pacote for baixado e descompactado, as VMs receberão a nova atualização. Sugerimos começar uma vez por dia, mas você deve experimentar aumentar ou diminuir a frequência para entender o impacto. 

Normalmente, os pacotes de inteligência de segurança são publicados uma vez a cada três a quatro horas. A configuração de uma frequência menor que quatro horas não é aconselhada porque aumentará a sobrecarga de rede em sua máquina de gerenciamento sem benefícios.

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a>Definir uma tarefa agendada para executar o script do PowerShell

1. Na máquina de gerenciamento, abra o menu Iniciar e digite **Agendador de Tarefas.** Abra-o e selecione **Criar tarefa...** no painel lateral.

2. Insira o nome como **desempacotar inteligência de segurança.** Vá para a **guia Gatilho.** Selecione **Novo...** > **Diariamente** e selecione **OK**.

3. Vá para a **guia Ações.** Selecione **Novo...** Insira **o PowerShell** no **campo Programa/Script.** Insira `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` no campo Adicionar **argumentos.** Selecione **OK**.

4. Você pode optar por configurar configurações adicionais, se desejar.

5. Selecione **OK** para salvar a tarefa agendada.
 
Você pode iniciar a atualização manualmente clicando com o botão direito do mouse na tarefa e clicando em **Executar**.

### <a name="download-and-unpackage-manually"></a>Baixar e descompactar manualmente

Se você preferir fazer tudo manualmente, veja o que fazer para replicar o comportamento do script:

1. Crie uma nova pasta na raiz do sistema chamada para armazenar atualizações de `wdav_update` inteligência, por exemplo, crie a pasta `c:\wdav_update` .

2. Criar uma subpasta em *wdav_update* com um nome GUID, como `{00000000-0000-0000-0000-000000000000}`

Veja um exemplo: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`

   > [!NOTE]
   > No script, definimos-o para que os últimos 12 dígitos do GUID sejam o ano, mês, dia e hora em que o arquivo foi baixado para que uma nova pasta seja criada sempre. Você pode alterar isso para que o arquivo seja baixado para a mesma pasta sempre.

3. Baixe um pacote de inteligência de segurança [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  na pasta GUID. O arquivo deve ser nomeado `mpam-fe.exe` .

4. Abra uma janela de prompt de cmd e navegue até a pasta GUID criada. Use o **comando de extração /X** para extrair os arquivos, por exemplo `mpam-fe.exe /X` .

   > [!NOTE]
   > As VMs receberão o pacote atualizado sempre que uma nova pasta GUID for criada com um pacote de atualização extraído ou sempre que uma pasta existente for atualizada com um novo pacote extraído.

## <a name="randomize-scheduled-scans"></a>Randomizar verificações agendadas

Verificações agendadas são executados além da proteção e verificação em tempo [real.](configure-real-time-protection-microsoft-defender-antivirus.md)

A hora de início da verificação em si ainda é baseada na política de verificação agendada (**ScheduleDay**, **ScheduleTime** e **ScheduleQuickScanTime**). A randomização fará Microsoft Defender Antivírus iniciar uma verificação em cada máquina dentro de uma janela de 4 horas a partir do tempo definido para a verificação agendada.

Consulte [Agendar verificações](scheduled-catch-up-scans-microsoft-defender-antivirus.md) para outras opções de configuração disponíveis para verificações agendadas.

## <a name="use-quick-scans"></a>Usar verificações rápidas

Você pode especificar o tipo de verificação que deve ser executada durante uma verificação agendada. As verificações rápidas são a abordagem preferencial, pois foram projetadas para procurar em todos os locais onde o malware precisa residir para estar ativo. O procedimento a seguir descreve como configurar verificações rápidas usando a Política de Grupo.

1. No Editor de Política de Grupo, vá para **Modelos administrativos**  >  **Windows componentes**  >  **Microsoft Defender Antivírus**  >  **Verificar**.

2. Selecione **Especificar o tipo de verificação a ser usado para uma verificação agendada** e edite a configuração de política.

3. De definir a política **como Habilitado** e, em Seguida, em **Opções,** selecione  **Verificação rápida**.

4. Selecione **OK**. 

5. Implante seu objeto de Política de Grupo como de costume.

## <a name="prevent-notifications"></a>Impedir notificações

Às vezes, Microsoft Defender Antivírus as notificações podem ser enviadas ou persistir em várias sessões. Para minimizar esse problema, você pode bloquear a interface Microsoft Defender Antivírus usuário. O procedimento a seguir descreve como suprimir notificações com a Política de Grupo.

1. No Editor de Política de Grupo, vá para Windows **componentes**  >  **Microsoft Defender Antivírus**  >  **Interface do Cliente.**

2. Selecione **Suprimir todas as notificações** e edite as configurações de política. 

3. De definir a política **como Habilitado** e, em seguida, selecione **OK**.

4. Implante seu objeto de Política de Grupo como de costume.

A supressão de notificações impede que as notificações Microsoft Defender Antivírus sejam aparecendo no Centro de Ações no Windows 10 quando as verificações são feitas ou ações de correção são tomadas. No entanto, sua equipe de operações de segurança verá os resultados da verificação no portal [Microsoft 365 Defender.](microsoft-defender-security-center.md)

> [!TIP]
> Para abrir o Centro de Ações Windows 10, dê uma das seguintes etapas:
> - Na extremidade direita da barra de tarefas, selecione o ícone centro de ações.
> - Pressione o botão Windows tecla de logotipo + A.
> - Em um dispositivo touchscreen, passe o dedo da borda direita da tela.

## <a name="disable-scans-after-an-update"></a>Desabilitar verificações após uma atualização

Desabilitar uma verificação após uma atualização impedirá que uma verificação ocorra depois de receber uma atualização. Você pode aplicar essa configuração ao criar a imagem base se também tiver executado uma verificação rápida. Dessa forma, você pode impedir que a VM recém-atualizada faça uma verificação novamente (como você já a examinou ao criar a imagem base).

> [!IMPORTANT]
> Executar verificações após uma atualização ajudará a garantir que suas VMs sejam protegidas com as atualizações mais recentes de Inteligência de Segurança. Desabilitar essa opção reduzirá o nível de proteção de suas VMs e só deve ser usado ao criar ou implantar a imagem base pela primeira vez.

1. No Editor de Política de Grupo, acesse Windows **componentes**  >  **Microsoft Defender Antivírus**  >  **Atualizações de Inteligência de Segurança.**

2. Selecione **Ativar a verificação após a atualização de inteligência de** segurança e edite a configuração de política.

3. De definir a política como **Desabilitada**.

4. Selecione **OK**.

5. Implante seu objeto de Política de Grupo como de costume.

Essa política impede que uma verificação seja executado imediatamente após uma atualização.

## <a name="scan-vms-that-have-been-offline"></a>Examinar VMs que tenham sido offline

1. No Editor de Política de Grupo, vá para Windows **componentes**  >  **Microsoft Defender Antivírus**  >  **Scan**.

2. Selecione **Ativar a verificação rápida de catch-up** e edite a configuração de política.

3. De definir a política como **Enabled**.

4. Selecione **OK**.

5. Implante seu Objeto de Política de Grupo como normalmente faz.

Essa política força uma verificação se a VM tiver perdido duas ou mais verificações agendadas consecutivas.

## <a name="enable-headless-ui-mode"></a>Habilitar o modo de interface do usuário sem cabeça

1. No Editor de Política de Grupo, vá para Windows **componentes**  >  **Microsoft Defender Antivírus**  >  **Interface do Cliente.**

2. Selecione **Habilitar o modo de interface do usuário sem** cabeça e edite a política.

3. De definir a política como **Enabled**.

4. Clique em **OK**.

5. Implante seu Objeto de Política de Grupo como normalmente faz.
 
Essa política oculta toda a interface do Microsoft Defender Antivírus de usuários finais em sua organização.

## <a name="exclusions"></a>Exclusões

As exclusões podem ser adicionadas, removidas ou personalizadas para atender às suas necessidades.

Para obter mais informações, consulte [Configure Microsoft Defender Antivírus exclusões no Windows Server](configure-exclusions-microsoft-defender-antivirus.md).

## <a name="additional-resources"></a>Recursos adicionais

- [Blog Community de tecnologia: configurando Microsoft Defender Antivírus para máquinas VDI não persistentes](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [Fóruns do TechNet em Serviços de Área de Trabalho Remota e VDI](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [Script signatureDownloadCustomTask PowerShell](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)