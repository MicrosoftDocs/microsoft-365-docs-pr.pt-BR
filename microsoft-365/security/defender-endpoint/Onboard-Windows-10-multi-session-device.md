---
title: Dispositivos integrados com várias sessões do Windows 10 na Área de Trabalho Virtual do Windows
description: Leia mais neste artigo sobre a integração de Windows 10 de várias sessões em Windows Área de Trabalho Virtual
keywords: Windows Área de trabalho virtual, WVD, microsoft defender, ponto de extremidade, onboard
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 9114a825ad011f0b2a17cea4929ab2a09bfa2172
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339473"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a>Dispositivos integrados com várias sessões do Windows 10 na Área de Trabalho Virtual do Windows 
6 minutos para leitura 

Aplicável a: 
- Windows 10 várias sessões em execução Windows Virtual Desktop (WVD) 

O Microsoft Defender para Ponto de Extremidade oferece suporte ao monitoramento de VDI e Windows da Área de Trabalho Virtual. Dependendo das necessidades da sua organização, talvez seja necessário implementar sessões de VDI ou de área de trabalho virtual Windows para ajudar seus funcionários a acessar dados corporativos e aplicativos de um dispositivo sem gestão, localização remota ou cenário semelhante. Com o Microsoft Defender para Ponto de Extremidade, você pode monitorar essas máquinas virtuais para atividades anômalas.

 ## <a name="before-you-begin"></a>Antes de começar
Familiarize-se com as [considerações para VDI não persistente.](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1) Embora [Windows Área](/azure/virtual-desktop/overview) de Trabalho Virtual não forneça opções de não persistência, ela fornece maneiras de usar uma imagem de Windows dourada que pode ser usada para provisionar novos hosts e reimplantar computadores. Isso aumenta a volatilidade no ambiente e, portanto, afeta quais entradas são criadas e mantidas no portal do Microsoft Defender para Ponto de Extremidade, reduzindo a visibilidade para seus analistas de segurança.

> [!NOTE]
> Dependendo da escolha do método de integração, os dispositivos podem aparecer no portal do Microsoft Defender para Ponto de Extremidade como: 
> - Entrada única para cada área de trabalho virtual 
> - Várias entradas para cada área de trabalho virtual 

A Microsoft recomenda a integração Windows Área de Trabalho Virtual como uma única entrada por área de trabalho virtual. Isso garante que a experiência de investigação no portal do Ponto de Extremidade do Microsoft Defender está no contexto de um dispositivo com base no nome do computador. As organizações que frequentemente excluem e reimplantam hosts WVD devem considerar fortemente o uso desse método, pois impede que vários objetos para o mesmo computador seja criado no portal do Microsoft Defender para Ponto de Extremidade. Isso pode levar a confusão ao investigar incidentes. Para ambientes de teste ou não voláteis, você pode optar por escolher de forma diferente. 

A Microsoft recomenda adicionar o script de integração do Microsoft Defender for Endpoint à imagem dourada do WVD. Dessa forma, você pode ter certeza de que esse script de integração é executado imediatamente na primeira inicialização. Ele é executado como um script de inicialização na primeira inicialização em todos os dispositivos WVD provisionados da imagem dourada do WVD. No entanto, se você estiver usando uma das imagens da galeria sem modificação, coloque o script em um local compartilhado e chame-o de política de grupo local ou de domínio. 

> [!NOTE]
> O posicionamento e a configuração do script de inicialização de integração da VDI na imagem dourada do WVD o configura como um script de inicialização que é executado quando o WVD é iniciado. Não é recomendável a integração da imagem real de ouro WVD. Outra consideração é o método usado para executar o script. Ele deve ser executado o mais cedo possível no processo de inicialização/provisionamento para reduzir o tempo entre o computador que está disponível para receber sessões e a integração do dispositivo ao serviço. Abaixo, os cenários 1 & 2 levam isso em consideração.

### <a name="scenarios"></a>Cenários
Há várias maneiras de fazer a integração de um computador host WVD:

- Execute o script na imagem dourada (ou em um local compartilhado) durante a inicialização.
- Use uma ferramenta de gerenciamento para executar o script.

#### <a name="scenario-1-using-local-group-policy"></a>*Cenário 1: usando a política de grupo local*
Esse cenário exige colocar o script em uma imagem dourada e usa a política de grupo local para ser executado no início do processo de inicialização.

Use as instruções em [Onboard the non-persistent virtual desktop infrastructure (VDI) devices](configure-endpoints-vdi.md#onboard-the-non-persistent-virtual-desktop-infrastructure-vdi-devices).

Siga as instruções para uma única entrada para cada dispositivo.

#### <a name="scenario-2-using-domain-group-policy"></a>*Cenário 2: usando a política de grupo de domínio*
Esse cenário usa um script localizado centralmente e o executa usando uma política de grupo baseada em domínio. Você também pode colocar o script na imagem dourada e execute-o da mesma maneira.

**Baixe o WindowsDefenderATPOnboardingPackage.zip do centro de segurança Windows Defender de segurança**

1. Abra o arquivo de pacote de configuração .zip VDI (WindowsDefenderATPOnboardingPackage.zip)  

    1. No painel Central de Segurança do Microsoft Defender de navegação, selecione **Configurações**  >  **Integração**. 
    1. Selecione Windows 10 como o sistema operacional. 
    1. No campo **Método de implantação,** selecione scripts de integração VDI para pontos de extremidade não persistentes. 
    1. Clique **em Baixar pacote** e salve o .zip arquivo. 

2. Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que pode ser acessado pelo dispositivo. Você deve ter uma pasta chamada **OptionalParamsPolicy** e os arquivos **WindowsDefenderATPOnboardingScript.cmd** e **Onboard-NonPersistentMachine.ps1**.

**Usar o console de gerenciamento de Política de Grupo para executar o script quando a máquina virtual for iniciada**

1. Abra o Console de Gerenciamento de Política de Grupo (GPMC), clique com o botão direito do mouse no Objeto de Política de Grupo (GPO) que você deseja configurar e clique em **Editar**.

2. No Editor de Gerenciamento de Política de Grupo, vá até **Configuração** do computador \> **Configurações Configurações** Do painel \> **Controle de configurações**. 

3. Clique com o botão direito do mouse em **Tarefas Agendadas,** clique em **Novo** e em **Tarefa** Imediata (Pelo menos Windows 7). 

4. Na janela Tarefa aberta, vá para a **guia** Geral. Em **Opções de segurança,** **clique em Alterar Usuário ou Grupo** e digite SISTEMA. Clique **em Verificar Nomes** e clique em OK. NT AUTHORITY\SYSTEM aparece como a conta de usuário que a tarefa executará como. 

5. Selecione **Executar se o usuário está conectado ou não** e marque a caixa de seleção Executar com privilégios **mais** altos. 

6. Vá até a guia **Ações** e clique em **Novo**. Verifique se **Iniciar um programa** está selecionado no campo Ação. Insira o seguinte: 

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   Em seguida, **selecione OK** e feche qualquer janela GPMC aberta.

#### <a name="scenario-3-onboarding-using-management-tools"></a>*Cenário 3: Integração usando ferramentas de gerenciamento*

Se você planeja gerenciar seus dispositivos usando uma ferramenta de gerenciamento, poderá integrar dispositivos com Microsoft Endpoint Configuration Manager.

Para obter mais informações, consulte [Onboard Windows 10 using Configuration Manager](configure-endpoints-sccm.md).

> [!WARNING]
> Se você planeja usar As Regras de Redução de Superfície de Ataque [,](attack-surface-reduction.md)observe que a regra " Bloquear criações de processo originadas de[comandos PSExec](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)e WMI " não deve ser usada, pois essa regra é incompatível com o gerenciamento por meio de Microsoft Endpoint Configuration Manager. A regra bloqueia comandos WMI que o cliente configuration Manager usa para funcionar corretamente. 

> [!TIP]
> Após a integração do dispositivo, você pode optar por executar um teste de detecção para verificar se o dispositivo está corretamente conectado ao serviço. Para obter mais informações, [consulte Execute a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md). 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a>Marcando seus máquinas ao criar sua imagem dourada 

Como parte de sua integração, talvez você queira considerar a configuração de uma marca de máquina para diferenciar máquinas WVD com mais facilidade no Centro de Segurança da Microsoft. Para obter mais informações, [consulte Add device tags by setting a Registry key value](machine-tags.md#add-device-tags-by-setting-a-registry-key-value). 

#### <a name="other-recommended-configuration-settings"></a>Outras configurações recomendadas 

Ao criar sua imagem dourada, você também pode querer definir as configurações de proteção inicial. Para obter mais informações, consulte [Outras configurações recomendadas.](configure-endpoints-gp.md#other-recommended-configuration-settings) 

Além disso, se você estiver usando perfis de usuário FSlogix, recomendamos excluir os seguintes arquivos da proteção always-on: 

**Excluir Arquivos:** 

`%ProgramFiles%\FSLogix\Apps\frxdrv.sys`

`%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys`

`%ProgramFiles%\FSLogix\Apps\frxccd.sys`

`%TEMP%\*.VHD`

`%TEMP%\*.VHDX`

`%Windir%\TEMP\*.VHD`

`%Windir%\TEMP\*.VHDX`

`\\storageaccount.file.core.windows.net\share\*\*.VHD`

`\\storageaccount.file.core.windows.net\share\*\*.VHDX`

**Excluir processos:**

`%ProgramFiles%\FSLogix\Apps\frxccd.exe`

`%ProgramFiles%\FSLogix\Apps\frxccds.exe`

`%ProgramFiles%\FSLogix\Apps\frxsvc.exe`

#### <a name="licensing-requirements"></a>Requisitos de licenciamento 

Observação sobre licenciamento: ao usar o Windows 10 Enterprise em várias sessões, dependendo de seus requisitos, você pode optar por ter todos os usuários licenciados por meio do Microsoft Defender para Ponto de Extremidade (por usuário), Windows Enterprise E5, Microsoft 365 Security ou Microsoft 365 E5, ou ter a VM licenciada por meio do Azure Defender.
Os requisitos de licenciamento do Microsoft Defender para ponto de extremidade podem ser encontrados em: [Requisitos de licenciamento.](minimum-requirements.md#licensing-requirements)

#### <a name="related-links"></a>Links relacionados

[Adicionar exclusões para o Microsoft Defender usando o PowerShell](/azure/architecture/example-scenario/wvd/windows-virtual-desktop-fslogix#add-exclusions-for-windows-defender-by-using-powershell)
