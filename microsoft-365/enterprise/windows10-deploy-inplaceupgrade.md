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
ms.openlocfilehash: f7dfa5c72a98dacc7a772ea034df6696621a8ef6
ms.sourcegitcommit: 9083036e787cf997fbceb19c66af594d0fa81d0f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "38302928"
---
# <a name="step-2-deploy-windows-10-enterprise-for-existing-devices-as-an-in-place-upgrade"></a>Etapa 2: implantar o Windows 10 Enterprise para dispositivos existentes como uma atualização in-loco

*Este artigo aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*

![Fase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

O caminho mais simples para atualizar os computadores que estão executando o Windows 7 ou o Windows 8,1 para o Windows 10 é por meio de uma atualização in-loco. Você pode usar uma sequência de tarefas do System Center Configuration Manager (Configuration Manager) para automatizar completamente o processo. 

Se você tiver computadores que executam o Windows 7 ou o Windows 8,1, recomendamos esse caminho se sua organização estiver implantando o Windows 10. Isso utiliza o programa de instalação do Windows (Setup. exe) para executar uma atualização in-loco, que preserva automaticamente todos os dados, configurações, aplicativos e drivers da versão do sistema operacional existente. Isso requer o menor esforço de ti, porque não há necessidade de nenhuma infraestrutura de implantação complexa.

Siga estas etapas para configurar e implantar uma imagem do Windows 10 Enterprise usando o Configuration Manager como uma atualização in-loco.

## <a name="the-windows-10-deployment-with-system-center-configuration-manager-poster"></a>Pôster de implantação do Windows 10 com o System Center Configuration Manager

O pôster do Gerenciador de configurações é uma página no modo paisagem (17x11). Clique na imagem abaixo para exibir um PDF no navegador. 

[![Implantar o Windows 10 com o cartaz do Configuration Manager](./media/windows10-deploy-inplaceupgrade/windows10-deployment-config-manager.png)](https://opdhsblobprod04.blob.core.windows.net/contents/d0d41f25ce48460387a79ace64acad6b/810b475c713ebb3ad65d13746940ef91?sv=2015-04-05&sr=b&sig=jjP0k8Y9ClANZptzS5IPwxs61kocwCg6bLUBdjZp6lY%3D&st=2019-11-12T23%3A51%3A28Z&se=2019-11-14T00%3A01%3A28Z&sp=r)

Você também pode fazer o download deste pôster em formato [PDF](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.pdf) ou do [Visio](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.vsdx).

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
