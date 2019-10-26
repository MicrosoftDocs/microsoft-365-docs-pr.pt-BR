---
title: Implantar o Windows 10 Enterprise para dispositivos existentes como uma atualização in-loco
description: Fornece orientação sobre como configurar e implantar uma imagem do Windows 10 Enterprise usando o System Center Configuration Manager como uma atualização in-loco.
keywords: Microsoft 365, Microsoft 365 Enterprise, documentação do Microsoft 365, Windows 10 Enterprise, implantação, atualização in-loco, Gerenciador de configurações, System Center Configuration Manager
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
ms.author: greglin
ms.openlocfilehash: 69edcd65ada007ead9e0c0d628b96f6390e34696
ms.sourcegitcommit: 64a21c59d31a283ccbe87d16f0a174998e3aeba8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/26/2019
ms.locfileid: "37733434"
---
# <a name="step-2-deploy-windows-10-enterprise-for-existing-devices-as-an-in-place-upgrade"></a>Etapa 2: implantar o Windows 10 Enterprise para dispositivos existentes como uma atualização in-loco

*Este artigo aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*

![Fase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

O caminho mais simples para atualizar os computadores que estão executando o Windows 7 ou o Windows 8,1 para o Windows 10 é por meio de uma atualização in-loco. Você pode usar uma sequência de tarefas do System Center Configuration Manager (Configuration Manager) para automatizar completamente o processo. 

Se você tiver computadores que executam o Windows 7 ou o Windows 8,1, recomendamos esse caminho se sua organização estiver implantando o Windows 10. Isso utiliza o programa de instalação do Windows (Setup. exe) para executar uma atualização in-loco, que preserva automaticamente todos os dados, configurações, aplicativos e drivers da versão do sistema operacional existente. Isso requer o menor esforço de ti, porque não há necessidade de nenhuma infraestrutura de implantação complexa.

Siga estas etapas para configurar e implantar uma imagem do Windows 10 Enterprise usando o Configuration Manager como uma atualização in-loco.

## <a name="the-windows-10-deployment-with-system-center-configuration-manager-poster"></a>O cartaz de implantação do Windows 10 com o System Center Configuration Manager

O pôster do Gerenciador de configurações é uma página no modo paisagem (17x11). Clique na imagem abaixo para exibir um PDF no navegador. 

[![Implantar o Windows 10 com o cartaz do Configuration Manager](./media/windows10-deploy-inplaceupgrade/windows10-deployment-config-manager.png)](https://opdhsblobprod04.blob.core.windows.net/contents/d0d41f25ce48460387a79ace64acad6b/810b475c713ebb3ad65d13746940ef91?sv=2015-04-05&sr=b&sig=tKD38RgLAoOCAWJ5ppEbLevBAHk7KHtWrXldy2Jl6mY%3D&st=2019-10-24T22%3A16%3A08Z&se=2019-10-25T22%3A26%3A08Z&sp=r)

<!--

You can also download this poster in [PDF](https://github.com/MicrosoftDocs/windows-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.pdf) or [Visio](https://github.com/MicrosoftDocs/windows-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.vsdx) format.
-->

## <a name="part-1-verify-readiness-to-upgrade-windows"></a>Parte 1: verificar a preparação para atualizar o Windows

Primeiro, use o recurso de prontidão de atualização do Windows Analytics para fornecer ideias e recomendações poderosas sobre os computadores, aplicativos e drivers em sua organização, sem custo adicional e sem requisitos de infraestrutura adicionais. Este novo serviço orienta você por meio da atualização e dos projetos de atualização de recursos usando um fluxo de trabalho com base nas práticas recomendadas pela Microsoft. Os dados de inventário atualizados permitem que você equilibre custos e riscos em seus projetos de atualização.

Consulte [gerenciar atualizações do Windows com a preparação para atualização](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness) para saber mais, introdução, usar e solucionar problemas de preparação da atualização.

Em seguida, siga o guia para usar o System Center Configuration Manager (Branch atual) para atualizar o sistema operacional Windows 7 ou posterior para o Windows 10. Como em qualquer implantação de alto risco, é recomendável fazer backup dos dados do usuário antes de prosseguir. O armazenamento em nuvem do OneDrive está pronto para ser usado para usuários licenciados da Microsoft 365 e pode ser usado para armazenar com segurança seus arquivos. Para obter mais informações, consulte o [Guia de início rápido do onedrive](https://aka.ms/ODfBquickstartguide). Para acessar essa página, você deve entrar como administrador de locatário ou administrador global em um Office 365 ou Microsoft 365 locatário.

Para obter uma lista de versões do Gerenciador de configurações e as versões do cliente Windows 10 correspondentes suportadas, consulte [support for Windows 10 for System Center Configuration Manager](https://aka.ms/supportforwin10sccm).

**Para verificar a preparação para atualizar o Windows**

Revise esses requisitos antes de iniciar a implantação do Windows 10:

- **Edições do Windows qualificadas para atualização** : seus dispositivos devem estar executando edições do Windows 7 ou Windows 8,1 qualificadas para atualização para o Windows 10 Enterprise. Para obter uma lista de edições suportadas, consulte [caminhos de atualização do Windows 10](https://aka.ms/win10upgradepaths). 
- **Dispositivos suportados** : a maioria dos computadores compatíveis com o Windows 8,1 será compatível com o Windows 10. Talvez seja necessário instalar drivers atualizados no Windows 10 para que seus dispositivos funcionem corretamente. Consulte [Windows 10 Specifications](https://aka.ms/windows10specifications) para obter mais informações.
- **Preparação da implantação** : Certifique-se de ter o seguinte antes de começar a configurar a implantação:
    - Mídia de instalação do Windows 10: a mídia de instalação deve estar localizada em uma unidade separada, com o ISO já montado. Você pode obter a ISO de [downloads para assinantes do MSDN](https://aka.ms/msdn-subscriber-downloads) ou do [centro de serviços de licenciamento por volume](https://aka.ms/mvlsc).
    - Backups de dados do usuário – embora os dados do usuário sejam migrados na atualização, a prática recomendada é configurar um cenário de backup. Por exemplo, exporte todos os dados do usuário para uma conta do OneDrive, unidade flash USB criptografada no BitLocker ou servidor de arquivos de rede. Para obter mais informações, consulte [back up or Transfer Data in Windows](https://aka.ms/backuptransferdatawindows).
- **Preparação do ambiente** : você usará uma estrutura de servidor do Configuration Manager existente para se preparar para a implantação do sistema operacional. Além da configuração base, as seguintes configurações devem ser feitas no ambiente do Configuration Manager:
    1. [Estenda o esquema do Active Directory](https://aka.ms/extendadschema) e [crie um contêiner de gerenciamento do sistema](https://aka.ms/createsysmancontainer).
    2. Habilitar a descoberta de florestas do Active Directory e a descoberta de sistema do Active Directory. Para obter mais informações, consulte [Configure Discovery Methods for System Center Configuration Manager](https://aka.ms/configurediscoverymethods).
    3. Criar limites de intervalo IP e grupo de limite para a atribuição de conteúdo e de site. Para obter mais informações, consulte [definir limites do site e grupos de limite para o System Center Configuration Manager](https://aka.ms/definesiteboundaries).
    4. Adicione e configure a função de ponto do Configuration Manager Reporting Services. Para obter mais informações, consulte [Configuring Reporting in Configuration Manager](https://aka.ms/configurereporting).
    5. Criar uma estrutura de pasta do sistema de arquivos para pacotes.
    6. Criar uma estrutura de pasta do console do Configuration Manager para pacotes.
    7. Instale as atualizações do System Center Configuration Manager (Branch atual) e os pré-requisitos adicionais do Windows 10.

## <a name="part-2-add-a-windows-10-os-image-using-configuration-manager"></a>Parte 2: adicionar uma imagem do Windows 10 so usando o Configuration Manager
Agora, você precisará criar um pacote de atualização do sistema operacional que contenha a mídia de instalação completa do Windows 10. Nas etapas a seguir, você usará o Gerenciador de configurações para criar um pacote de atualização para o Windows 10 Enterprise x64.

**Para adicionar uma imagem do Windows 10 so usando o Configuration Manager**

1. Usando o console do Gerenciador de configurações, no espaço de trabalho da **biblioteca de software** , clique com o botão direito do mouse no nó pacotes de **atualização do sistema operacional** e selecione **Adicionar pacote de atualização do sistema operacional**.
2. Na página **fonte de dados** , especifique o caminho UNC para a mídia x64 do Windows 10 Enterprise e, em seguida, selecione **Avançar**.
3. Na página **geral** , especifique **atualização do Windows 10 Enterprise x64**e, em seguida, selecione **Avançar**. 
4. Na página **Resumo** , selecione **Avançar**e, em seguida, selecione **Fechar**. 
5. Clique com o botão direito do mouse no pacote de **atualização do Windows 10 Enterprise x64** criado e selecione **distribuir conteúdo**. 
6. Escolha seu ponto de distribuição.

## <a name="part-3-configure-deployment-settings"></a>Parte 3: definir configurações de implantação
Nesta etapa, você configurará uma sequência de tarefas de atualização que contém as configurações para a atualização do Windows 10. Você identificará os dispositivos a serem atualizados e, em seguida, implantará a sequência de tarefas nesses dispositivos.

### <a name="create-a-task-sequence"></a>Criar uma sequência de tarefas
Para criar uma sequência de tarefas de atualização, execute as seguintes etapas:
  
1. No console do Gerenciador de configurações, no espaço de trabalho da **biblioteca de software** , expanda **sistemas operacionais**. 
2. Clique com o botão direito do mouse no nó **sequências de tarefas** e selecione **criar sequência de tarefas**.
3. Na página **criar uma nova sequência de tarefas** , selecione **atualizar um sistema operacional do pacote de atualização**e, em seguida, selecione **Avançar**.
4. Na página **informações da sequência de tarefas** , especifique **atualização do Windows 10 Enterprise x64**e, em seguida, selecione **Avançar**.
5. Na página **atualizar o sistema operacional Windows** , selecione **procurar** e escolha o **pacote de atualização do sistema operacional de atualização do Windows 10 Enterprise x64**, selecione **OK**e, em seguida, selecione **Avançar**.
6. Continue através das páginas restantes do assistente e selecione **fechar**.

### <a name="create-a-device-collection"></a>Criar uma coleção de dispositivos
Após criar a sequência de tarefas de atualização, você precisará criar uma coleção que contenha os dispositivos que você irá atualizar.

> [!NOTE]
> Use as configurações a seguir para testar a implantação em um único dispositivo. Você pode usar regras de associação diferentes para incluir grupos de dispositivos quando estiver pronto. Para obter mais informações, consulte [como criar coleções no System Center Configuration Manager](https://aka.ms/sccm-create-collections).

1. No console do Gerenciador de configurações, no espaço de trabalho **ativos e conformidade** , clique com o botão direito do mouse em **coleções de dispositivos**e selecione **criar coleção de dispositivos**. 
2. No Assistente para criar coleção de dispositivos, na página **geral** , insira as seguintes configurações e selecione **Avançar**:
    - Name: atualização do Windows 10 Enterprise x64
    - Limitação de coleção: All Systems
3. Na página **regras de associação** , selecione **** > **regra direta** de adição de regra para iniciar o assistente de criação de regra de associação direta.
4. Na página de **boas-vindas** do assistente para criar regra de associação direta, selecione **Avançar**.
5. Na página **Pesquisar recursos** , insira as configurações a seguir, substituindo o texto do **valor** do espaço reservado pelo nome do dispositivo que você está atualizando: 
    - Classe de recurso: recurso do sistema
    - Nome do atributo: nome
    - Valor: *PC0003*
6. Na página **selecionar recursos** , selecione seu dispositivo e selecione **Avançar**.
7. Conclua o assistente de criação de regra de associação direta e o assistente para criar coleção de dispositivos.  
8. Revise o conjunto de atualização do Windows 10 Enterprise x64. Não continue até ver as máquinas que você adicionou na coleção.

### <a name="create-an-operating-system-deployment"></a>Criar uma implantação de sistema operacional
Siga estas etapas para criar uma implantação para a sequência de tarefas.

1. No console do Gerenciador de configurações, no espaço de trabalho da **biblioteca de software** , clique com o botão direito do mouse na sequência de tarefas que você criou em uma etapa anterior e selecione **implantar**.
2. Na página **geral** , selecione o conjunto de **atualização do Windows 10 Enterprise x64** e, em seguida, selecione **Avançar**.
3. Na página **conteúdo** , selecione **Avançar**.
4. Na página **configurações de implantação** , selecione as seguintes configurações e, em seguida, selecione **Avançar**:

    > [!NOTE]
    > Para esta implantação de teste, você definirá o objetivo como **disponível**, o que requer a intervenção do usuário para iniciar a implantação. Em um ambiente de produção, talvez você queira automatizar a implantação usando a finalidade necessária, que envolve a configuração de opções adicionais, como agendamento quando a implantação é executada. 

    - Ação: instalar
    - Propósito: disponível

5. Na página **agendamento** , aceite as configurações padrão e, em seguida, selecione **Avançar**.
6. Na página **experiência do usuário** , aceite as configurações padrão e, em seguida, selecione **Avançar**.
7. Na página **alertas** , aceite as configurações padrão e, em seguida, selecione **Avançar**.
8. Na página **Resumo** , selecione **Avançar**e, em seguida, selecione **Fechar**.

## <a name="part-4-start-the-windows-10-upgrade-task-sequence"></a>Parte 4: iniciar a sequência de tarefas de atualização do Windows 10
Siga estas etapas para iniciar a sequência de tarefas de atualização do Windows 10 no dispositivo que você está atualizando.
 
1. Faça logon no computador do Windows e inicie a **central de software**.
2. Selecione a sequência de tarefas que você criou em uma etapa anterior e selecione **instalar**.
3. Quando a sequência de tarefas começa, inicia automaticamente o processo de atualização in-loco invocando o programa de instalação do Windows (Setup. exe) com os parâmetros de linha de comando necessários para executar uma atualização automatizada, que preserva todos os dados, configurações, aplicativos e drivers.
4. Depois que a sequência de tarefas for concluída com êxito, o computador será totalmente atualizado para o Windows 10.

Se você tiver problemas ao usar o Windows 10 em um ambiente corporativo, poderá consultar [as principais soluções de suporte da Microsoft para obter os problemas mais comuns](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions). Esses recursos incluem artigos de KB, atualizações e artigos de biblioteca.

Durante a implantação das atualizações em sua organização, use o recurso de conformidade de atualização do Windows Analytics para fornecer uma visão holística da conformidade de atualização do sistema operacional, o progresso da implantação e a solução de problemas de falha para dispositivos Windows 10. Esse novo serviço usa dados de diagnóstico, incluindo o progresso da instalação, a configuração do Windows Update e outras informações para fornecer essas insights, sem custo adicional e sem requisitos de infraestrutura adicionais. Se ele é usado com o Windows Update para empresas ou outras ferramentas de gerenciamento, você pode ter certeza de que seus dispositivos estão atualizados corretamente.

Confira [monitorar as atualizações do Windows e o Windows Defender Antivirus com a conformidade de atualização](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor) para saber mais, começar e usar a conformidade de atualização.

Como ponto de verificação provisório, é possível conferir os [Critérios de saída](windows10-exit-criteria.md#crit-windows10-step2) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![Etapa 3](./media/stepnumbers/Step3.png)| [Implantar o Windows 10 Enterprise para novos dispositivos com o Windows AutoPilot](windows10-deploy-autopilot.md) |



<!--

| Phases | Description |
|:--- |:--- |
| [Phase 1: Consideration phase](#phase-1-consideration-phase) | TBD |
| [Phase 2: Testing phase](#phase-2-testing-phase) | TBD |
| [Phase 3: Deployment phase](#phase-3-deployment-phase) | TBD |

## Phase 1: Consideration phase
Before upgrading an OS in an enterprise environment, take the following technical aspects into account:
* [Infrastructure](#step-1-infrastructure)
* [Apps](#step-2-apps)
* [Governance and business processes](#step-3-governance-and-business-processes)

This guide is meant only to provide Microsoft's best recommendations around these assumptions by providing links to existing documentation.

### Step 1: Infrastructure
Consider your organization's collection of hardware, software, policies, networks, and other related technologies as part of the deployment process.

For in-place upgrade with Configuration Manager, these are the infrastructure you need to take into account:

#### Group Policy
Windows 10 introduces many new features and removes and changes many others in Windows 7 and 8.1, including new Group Policy settings which you need to test and implement as part of a Windows 10 migration. Use the examples from the following resources to assess current group policies for Windows, including Group Policy Objects in the Active Directory structure:
* [Manage Windows 10 with administrative templates](https://go.microsoft.com/fwlink/?linkid=860226) - Get step-by-step info on how to manage Windows 10 with administrative templates
* [Group Policy settings that apply to Windows 10](https://docs.microsoft.com/windows/client-management/group-policies-for-enterprise-and-education-editions) - Find out which Group Policy settings apply only to Windows 10 Enterprise

> [!NOTE]
> If you are considering moving to modern management by using MDM instead of Group Policy to manage device configurations, you can start by using the [MDM Migration Analysis Tool (MMAT)](https://github.com/WindowsDeviceManagement/MMAT) to determine what Group Policies are set on the device and report the corresponding settings, if available.

#### Data management
Although in-place upgrades shouldn’t affect user data and apps, a best practice is to configure a backup scenario and back up user data. For example, export all user data to a OneDrive for Business account, BitLocker To Go-encrypted USB flash drive, or network file server. For more details, see:
* [How to back up or transfer your data on a Windows-based computer](https://go.microsoft.com/fwlink/?linkid=860230) - Get step-by-step info on how to manually back up your personal files and settings.
* [Redirect known folders to OneDrive for Business](https://go.microsoft.com/fwlink/?linkid=846620) - Learn how to set a policy at the domain level to make sure users all sync to the same folder when they install the OneDrive sync client and how you can set additional policies to redirect the Documents folder to that sync location.

#### System Center Configuration Manager
This guide assumes you are following Microsoft recommendations and have one of the following versions of System Center Configuration Manager 2012 onward:
* System Center 2012 Configuration Manager with SP2
* System Center 2012, 2012 R2 Configuration Manager with SP1, Current Branch, 1706
    * [Run an in-place upgrade to the latest Configuration Manager](https://go.microsoft.com/fwlink/?linkid=839406)
    * [Updates for Configuration Manager](https://go.microsoft.com/fwlink/?linkid=620343)
* Core Configuration Manager configuration:
    * CONFIGURATION MANAGER accounts
    * Active Directory permissions
    * Source folder structure
    * Active Directory schema
* Configure the following [necessary Configuration Manager components for Windows 10 deployment](https://go.microsoft.com/fwlink/?linkid=860245):
    * **State migration point** - Stores user state migration data during computer replace scenarios
    * **Distribution point** - Stores all packages in Configuration Manager
    * **Software update point** - Updates an OS as part of the deployment process
    * **Reporting services point** - Monitors the OS deployment process
    * **Boot images** - Are Windows Preinstallation Environment (PE) images used by Configuration Manager to start deployments
    * **OS images** - Denotes the production deployment image (mounted OS)
    * **OS installers** - Creates reference images using Microsoft Deployment Toolkit (MDT) Light Touch
    * **Drivers** - Denotes a repository of managed device drivers
    * **Task Sequence** - Is delivered automatically to the client as a policy

#### Network bandwidth
This guide assumes you have enough network bandwidth to support the deployment of Windows 10 Enterprise and Office 365 ProPlus as a unit. As a bundle, network bandwidth is a significant factor.

#### Client machines and in-place upgrade scenario
* Disk encryption - Third-party disk encryption isn't supported in an in-place upgrade scenario.
* User profiles - Only the standard user profile type is supported.
* Legacy BIOS to Unified Extensible Firmware Interface (UEFI) booting - Changing from legacy BIOS to UEFI booting isn't supported.
* Dual-boot - This scenario is not covered in the guide. If you have the FastTrack Benefit, it only covers devices running a single OS.
* Virtual desktop infrastructure (VDI) environments - This scenario is not covered in the guide. If you have the FastTrack Benefit, it doesn't cover configuration or deployment on VDI environments.
* x64 and x86 - Changing from a 32-bit OS to a 64-bit isn't supported. For more info, see [Windows 10 deployment scenario > In-place upgrade](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios#in-place-upgrade).

### Step 2: Apps

#### Security
Security clients (like antivirus, anti-malware, and anti-spam) are typically found on all PCs within an organization. Because these programs hook into the deeper levels of the OS, you may need to perform a compatibility assessment before starting any Windows 10 migrations. You may need to upgrade, reconfigure, or even replace Some software. Not performing this assessment can lead to:
* Native app compatibility checks failing and preventing an in-place upgrade from starting.
* Broken functionality in the security software.
* Instability after upgrading to Windows 10 (like crashing and reduced performance)

**Antivirus**

Assess current antivirus software. Windows 10 comes with Windows Defender Antivirus to protect devices from malware, viruses, and security threats. We recommend Windows Defender Antivirus. To enable Windows Defender Antivirus, see [Windows Defender Antivirus](windows10-enable-security-features.md#windows-defender-antivirus) and [Protect devices with Windows Defender Antivirus](https://go.microsoft.com/fwlink/?linkid=860254).

To learn about antivirus solutions from other providers, see [Consumer antivirus software providers for Windows](https://go.microsoft.com/fwlink/?linkid=67345).

#### App readiness
Each Windows 10 release provides improved app compatibility. However, some apps may not be compatible. Depending on the app, you may need to only do a simple upgrade or configuration update before upgrading to Windows 10. In other circumstances, you may need to remove an app entirely.

Be sure to assess business critical apps and understand the impact of upgrading to the next OS. Prioritize the workloads that impact the least number of people during deployment. 

See the following Upgrade Readiness resources to help with app inventory, driver compatibility issues, and usage information:
* [Manage Windows Upgrades with Upgrade Readiness](https://go.microsoft.com/fwlink/?linkid=860255) - Learn about the tools to help you plan and manage the upgrade process end to end, which allow you to adopt new Windows releases more quickly.
* [Configure Windows diagnostic data](https://go.microsoft.com/fwlink/?linkid=859970) - Find out about the importance of Windows diagnostic data and how Microsoft protects that data.

> [!NOTE]
> Upgrade Readiness may not be able to assess compatibility for custom and line-of-business (LOB) apps in an organization.

#### Language packs
In-place upgrades have have limitations when it comes to language packs. The language stays consistent throughout the upgrade. Verify the language version and make sure it stays consistent. For example, Windows 7 with English as the default won’t change when upgraded to Windows 10. For more info, see:
* [Default language pack on your OS](https://go.microsoft.com/fwlink/?linkid=860282)
* [Finding language packs on each Windows 10 deployment](https://go.microsoft.com/fwlink/?linkid=860283)

For a Microsoft 365 powered device, you'll also need to download Office 365 ProPlus language packs that applies to the client. These come in 32-bit (x86) or 64-bit (x64). A specific language must be installed as the default. You can install other languages later. For more info, see:
* [Choose between 64-bit or 32-bit version of Office](https://go.microsoft.com/fwlink/?linkid=862361) - Helps you decide which version of Office is right for you.
* [Language accessory pack for Office](https://go.microsoft.com/fwlink/?linkid=860280) - Follow the steps to install the language accessory pack for Office.
* [Add an additional language pack](https://go.microsoft.com/fwlink/?linkid=860281) - Get step-by-step info on adding a language or setting language preferences in Office.

### Step 3: Governance and business processes

#### Windows as a service
Windows 10 introduced the concept of Windows as a service. This greatly changes the frequency and style of updates to Windows. Instead of new versions being released every 3-5 years, a more incremental model is used where two smaller updates (Feature Updates) are released yearly. For more info, see:
* [Windows as a service on the Windows IT Pro Center](https://www.microsoft.com/itpro/windows-10/windows-as-a-service)
* [Overview of Windows as a service](https://go.microsoft.com/fwlink/?linkid=860288)
* [Update Windows 10 in the enterprise](https://go.microsoft.com/fwlink/?linkid=860285)

#### Pilot users and deployment rings
Be sure to have a pilot group of users selected from different parts of the business. If you have Microsoft 365 powered devices, Windows 10 and Office 365 ProPlus users should be in these deployment rings. This affects future Windows updates as well (including features and quality). You need to create and edit device collections by deployment rings to help minimize the effect on network bandwidth and simplify future updates. 

For the group of pilot users, create a device collection on Configuration Manager. The list of devices should correspond to the list of the first users upgraded to Windows 10. 

**Windows 10 deployment rings**

There are three servicing channels for OS deployment rings:
* Windows Insider Program - Provides organizations with the opportunity to test and provide feedback on features that are shipped in the next feature update.
* Semi-Annual Channel - Provides new functionality with twice-per-year feature update releases. Organizations can choose when to deploy updates from the Semi-Annual Channel.
* Long-Term Servicing Channel (LTSC) - Used for specialized devices and receives new feature releases about every three years.

For more info, see:
* [Windows Insider Program, Semi-Annual Channel, and Long-Term Servicing Channel](https://go.microsoft.com/fwlink/?linkid=860293)
* [Build deployment rings for Windows 10 updates](https://go.microsoft.com/fwlink/?linkid=860294)
* [Manage software updates using Intune in Azure Portal](https://docs.microsoft.com/intune/windows-update-for-business-configure)

**Office 365 ProPlus**

For Microsoft 365 powered devices, you must also be able to support the six-month update channel for both IT and business users. One way to do so is to have three groups:
* Current Channel
* Deferred Channel
* First-release for Deferred Channel

Each group has different configuration files, as users from the Current Channel are used as a pilot to test earlier updates. For more info, see:
* [Update process for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860299)
* [Manage updates to Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860300)
* [Configure update settings for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860301)
* [Update channels for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860302)
* [Version and build numbers of update channel releases](https://go.microsoft.com/fwlink/?linkid=860304)

For more info, see [Phase 4: Office 365 ProPlus infrastructure for Microsoft 365 Enterprise](office365proplus-infrastructure.md).

## Phase 2: Testing phase
Once you've completed the scenarios and requirements in [Step 1: Consideration phase](#step-1-consideration-phase), you can move to this stage.
* [Networking](#step-1-networking)
* [Identity](#step-2-identity)
* [Client readiness](#step-3-client-readiness)
* [System Center Configuration Manager](#step-4-system-center-configuration-manager)
* [Diagnostic data](#step-5-diagnostic-data)

### Step 1: Networking
Ports to the client need to be opened for Office 365 ProPlus (for a Microsoft 365 powered device) and Configuration Manager. For more details about setting up your Microsoft 365 Enterprise networking infrastructure, see [Phase 1: Networking](networking-infrastructure.md).

When setting up your networking infrastructure as part your in-place upgrade, make sure you complete these steps:
1. Read the best practices for [network planning and improving migration performance for Office 365](http://go.microsoft.com/fwlink/?LinkId=733655).
2. [Plan for network devices that connect to Office 365 services](http://go.microsoft.com/fwlink/?LinkId=733652).
3. [Review network impact of directory synchronization](http://go.microsoft.com/fwlink/?LinkId=733652).
4. Calculate the number of clients to use per IP address and understand [Network Address Translation (NAT) support with Office 365](http://go.microsoft.com/fwlink/?LinkId=733653) and how it impacts the number of users and client devices you can serve with a single IP address.
5. If your organization restricts computers on your network from connecting to the Internet, you'll need to understand the [endpoints (fully qualified domain names (FQDNs), ports, URLs, IPv4, and IPv6 address ranges)](http://go.microsoft.com/fwlink/?LinkID=280129) that you should include in your outbound allow lists to ensure your computers can successfully use Office 365 services.
6. [Create domain name system records for Office 365 at any Domain Name System hosting provider](http://go.microsoft.com/fwlink/?LinkId=733656).
7. [Reduce mail exchange (MX) DNS record time to live (TTL) value](http://go.microsoft.com/fwlink/?LinkId=733656).

### Step 2: Identity
Intelligent security for Microsoft 365 Enterprise, in which the right users have access to the right resources with an appropriate level of access, begins with identity management. For more details about setting up your Microsoft 365 Enterprise identity infrastructure, see [Phase 2: Identity](identity-infrastructure.md).

When setting up your identity infrastructure as part of your in-place upgrade, make sure you complete these tasks:
1. [Add a domain and users to Office 365](http://go.microsoft.com/fwlink/?LinkID=526338).
2. [Install and run the Office 365 IdFix tool](http://go.microsoft.com/fwlink/?LinkId=733662), which scans your on-premises Active Directory environment and identifies problems that might impact directory synchronization and slow your migration to Office 365.
3. Configure Active Directory for directory synchronization with Office 365 and [integrate on-premises directories with Azure AD](http://go.microsoft.com/fwlink/?LinkId=733661).
4. [Prepare to provision users through directory synchronization to Office 365](http://go.microsoft.com/fwlink/?LinkId=733659).
5. Know the [prerequisites for Azure AD Connect](http://go.microsoft.com/fwlink/?LinkId=733663), then install and run the Azure AD Connect tool to synchronize your on-premises Active Directory to the Azure AD service used by Office 365.
6. Determine custom installation of Azure AD Connect (full version of SQL Server for directory synchronization, if required).
7. [Integrate your on-premises identities with Azure AD](http://go.microsoft.com/fwlink/?LinkID=733485).
8. [Sync a list of required attributes with AD Connect](https://go.microsoft.com/fwlink/?linkid=860363) to get all the features in Office 365 and Windows 10.
9. Activate Windows 10 Enterprise licenses, which are checked based on Azure AD credentials.

    This provides a systematic way to assign licenses to end users and groups in your organization. For more info, see [Windows 10 Subscription Activation](https://go.microsoft.com/fwlink/?linkid=860365) and [Deploy Windows 10 licenses](https://go.microsoft.com/fwlink/?linkid=860367).

### Step 3: Client readiness

#### System requirements for Office 365
Confirm that Windows 10 works with Office 365. Be sure you're using the latest OS version and browsers with Office 365 and have updated them with the latest service packs. For more info on Office requirements, see [System requirements for Office](http://go.microsoft.com/fwlink/?LinkID=394412).

### Step 4: System Center Configuration Manager
See [System Center Configuration Manager](#system-center-configuration-manager).

### Step 5: Diagnostic data
Microsoft uses diagnostic data to help keep Windows devices secure by identifying malware trends and other threats and to help us improve the quality of Windows and Microsoft services. You must ensure that the diagnostics service is enabled at a minimum level of Basic on all endpoints in your organization. **By default, this service is enabled and set to the Enhanced level.** However, it’s good practice to check and ensure that they are receiving sensor data. Setting levels through policies overrides device-level settings. 

**Windows 10 operating system diagnostic data levels**

You can configure your operating system diagnostic data settings using the management tools you’re already using, such as Group Policy, MDM, or Windows Provisioning. You can also manually change your settings using Registry Editor. Setting your diagnostic data levels through a management policy overrides any device level settings.

Use the appropriate value in the table below when you configure the management policy.

| Level | Data gathered | Value |
|:--- |:--- |:--- |
| Security | Security data only. | 0 |
| Basic | Security data, and basic system and quality data. | 1 |
| Enhanced | Security data, basic system and quality data, and enhanced insights and advanced reliability data. | 2 |
| Full | Security data, basic system and quality data, enhanced insights and advanced reliability data, and full diagnostics data. | 3 |

You can enable diagnostics data through these methods:
* Microsoft Intune - If you plan to use Intune to manage your devices, you can create a configuration policy to enable diagnostic data by configuring the <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> system policy. For more info on setting up configuration policies, see [Manage settings and features on your devices with Microsoft Intune policies](https://aka.ms/intuneconfigpolicies).
* Registry Editor - You can use the Registry Editor to manually enable diagnostic data on each device in your organization, or write a script to edit the registry. If a management policy already exists, such as Group Policy or MDM, it will override this registry setting.
* Group Policy - If you do not plan to enroll devices in Intune, you can use a Group Policy object to set your organization’s diagnostic data level.
* Command prompt - You can set Windows 10 diagnostics data and service to automatically start with the command prompt. This method is best if you are testing the service on only a few devices. Enabling the service to start automatically with this command will not configure the diagnostic data level. If you have not configured a diagnostic data level using management tools, the service will operate with the default Enhanced level.

See [Configure Windows diagnostic data in your organization](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) to learn more about Windows diagnostic data and how you can enable it based on the method that you choose.

## Phase 3: Deployment phase
When ready, complete these:
* [In-place upgrade to Windows 10 Enterprise](#31-in-place-upgrade-to-windows-10-enterprise)
* [Windows Defender Antivirus](#32-windows-defender-antivirus)

### Step 1: In-place upgrade to Windows 10 Enterprise
1. Integrate System Center Configuration Manager with Microsoft Deployment Tool.

    Be sure to use the Microsoft Deployment Toolkit (MDT) in conjunction with Configuration Manager when deploying an updated version of Windows 10. MDT brings Zero Touch Installation and Light Touch Installation enhancements to help with deployments at no cost to the customer. For more info, see:
    * [Download the latest MDT](https://go.microsoft.com/fwlink/?linkid=860465)
    * [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://go.microsoft.com/fwlink/?linkid=860466)

2. Prepare for zero touch installation.

    As part of zero touch installation, you are responsible for preparing the following:
    * Configuration Manager service accounts
    * Active Directory permissions
    * Source folder structure

    Then, [integrate Configuration Manager with MDT](https://go.microsoft.com/fwlink/?linkid=860035).

3. Create a custom Windows Preinstallation Environment boot image.

    Windows Preinstallation Environment (PE) is a pre-installation environment required for OS deployments. It’s used to prepare a client machine for Windows installation, to copy disk images from a network file server, and to initiate Windows Setup. It’s used for Windows 10 Enterprise editions. For more info, see:
    * [Overview of Windows PE](https://go.microsoft.com/fwlink/?linkid=860468)
    * [Windows PE features, hardware requirements, and limitations](https://go.microsoft.com/fwlink/?linkid=860469)
    * [Create a custom Windows PE boot image with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860470)

4. Add a Windows 10 OS upgrade image.

    You need to create a Windows 10 reference image with MDT (as needed). Reference images are the foundation of what each of the client machine’s OS looks like. The image should be in a separate folder located with the already-mounted ISO file. The task sequence looks for and then runs “setup.exe”. 

    Follow the steps to create and add a Windows 10 OS upgrade image on Configuration Manager:
    * [Create a Windows 10 reference image](https://go.microsoft.com/fwlink/?linkid=860500)
    * [Add a Windows 10 OS image using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860501)

5. Create an app to deploy with Windows 10.

    For a Microsoft 365 powered device, you can deploy Office 365 ProPlus with Windows 10 Enterprise using Configuration Manager. You can also add other apps as needed.

    To deploy Office 365 ProPlus, follow the steps in [Phase 4: Office 365 ProPlus infrastructure for Microsoft 365 Enterprise](office365proplus-infrastructure.md). During this phase, make sure you complete these steps:
    
    1. Download the Office 2016 Deployment Tool (ODT) in conjunction with Configuration Manager to help with Office 365 ProPlus deployments. 
    2. Edit the configuration XML file to fit specific deployment needs (like version, language, and product element). 
    
    You can then create apps with Configuration Manager. For more info, see:
    * [Configuration options for ODT](https://go.microsoft.com/fwlink/?linkid=860504)
    * [Create apps in Configuration Manager](https://go.microsoft.com/fwlink/?linkid=761079)
    * [Deploy Office 365 ProPlus with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860506)

6. Add drivers to a Windows 10 deployment using Windows PE.

    Network drivers need to be created for both Windows PE and Windows 10 to connect deployment shares and storage drivers with local storage on a client computer. Use Configuration Manager to create these drivers required for deployment. For more info, see [Add drivers to a Windows 10 deployment with Windows PE using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860036).

7. Create a task sequence.

    A task sequence (a collection of commands) is required for MDT Lite Touch Installation (LTI). You need to create and then edit the task sequence for optimal deployment experience. One of the configurations enable support for Unified Extensible Firmware Interface (UEFI). The UEFI environment is a minimal boot OS where devices are booted and the Windows 10 OS runs. For more info, see:
    * [Overview of Windows Boot Manager](https://go.microsoft.com/fwlink/?linkid=860696)
    * [Create the task sequence in Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697)

8. Finalize the OS configuration for Windows 10 deployment.

    **To finalize the OS configuration**

    1. Enable MDT monitoring
    2. Create and share the Logs folder
    3. Configure the rules
    4. Distribute content to the distribution point (a server running Configuration Manager)
    5. Create a deployment for the task sequence

   For more info, see [Finalize OS configuration with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697).

9. Deploy the Windows 10 Enterprise image to a UEFI machine.

    For more info, see [Deploy Windows 10 using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697).

10. Monitor the Windows 10 deployment.

    Use Configuration Manager and MDT to monitor your deployment. Deployment Workbench enables access to the computer remotely using the Diagnostics and Recovery Toolset (DaRT) (optional). Deployments can be monitored in Configuration Manager. For more info, see [Monitor the Windows 10 deployment with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860705).

### Step 2: Windows Defender Antivirus
See [Enable Windows 10 Enterprise security features > Windows Defender Antivirus](windows10-enable-security-features.md#windows-defender-antivirus)

-->
