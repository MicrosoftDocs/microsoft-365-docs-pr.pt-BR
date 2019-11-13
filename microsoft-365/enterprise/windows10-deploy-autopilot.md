---
title: Implantar o Windows 10 Enterprise para novos dispositivos com o Windows AutoPilot
description: Fornece orientação sobre como configurar e implantar o Windows 10 Enterprise com o Windows AutoPilot.
keywords: Microsoft 365, Microsoft 365 Enterprise, documentação do Microsoft 365, Windows 10 Enterprise, implantação, Windows AutoPilot
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
ms.author: greglin
ms.openlocfilehash: 244aa9a2749c41471760c5263a6df6d745e5ade6
ms.sourcegitcommit: 9083036e787cf997fbceb19c66af594d0fa81d0f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "38302938"
---
# <a name="step-3-deploy-windows-10-enterprise-for-new-devices-with-windows-autopilot"></a>Etapa 3: implantar o Windows 10 Enterprise para novos dispositivos com o Windows AutoPilot

*Este artigo aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*

![Fase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Se você tiver novos computadores com Windows 10, você pode usar o Windows AutoPilot para personalizar a experiência (OOBE) da sua organização e implantar um novo sistema com aplicativos e configurações já configurados. Não há imagens para implantar, nenhum driver a ser injetado e nenhuma infraestrutura para gerenciar. Os usuários podem passar pelo processo de implantação de forma independente, sem a necessidade de consultar o administrador de ti.

Você pode configurar e pré-configurar novos dispositivos Windows 10 e colocá-los prontos para uso produtivo usando o Windows AutoPilot. Para saber mais sobre o Windows AutoPilot, incluindo benefícios e cenários de piloto automático do Windows, confira [visão geral do Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot). Quando estiver pronto, siga estas partes para começar a configurar novos dispositivos.

## <a name="the-windows-autopilot-deployment-process-poster"></a>O cartaz do processo de implantação do AutoPilot do Windows

O pôster do Windows AutoPilot é duas páginas no modo retrato (11x17). Clique na imagem abaixo para exibir um PDF no navegador. 

[![Pôster Implantar o Windows 10 com Piloto Automático](./media/windows10-deploy-autopilot/windows10-autopilot-flowchart.png)](https://opdhsblobprod04.blob.core.windows.net/contents/d0d41f25ce48460387a79ace64acad6b/d00f8fc01db0b512e4953663c8331588?sv=2015-04-05&sr=b&sig=RWOcP%2BhJZYpYcGKMhuTUEL6lcuWdBFefqR%2BQQfmj6IM%3D&st=2019-11-12T23%3A48%3A59Z&se=2019-11-13T23%3A58%3A59Z&sp=r)

Você também pode fazer o download deste pôster em formato [PDF](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10AutopilotFlowchart.pdf) ou do [Visio](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10Autopilotflowchart.vsdx).

## <a name="part-1-start-windows-autopilot-deployment"></a>Parte 1: iniciar a implantação do piloto automático do Windows
Consulte [visão geral do Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot) para:

1. Saiba mais sobre e conclua os pré-requisitos para a implantação do piloto automático do Windows. Os pré-requisitos incluem:
    - **Registro do dispositivo e personalização da OOBE**

        Para registrar dispositivos, você precisa adquirir sua ID de hardware e registrá-lo. Estamos trabalhando ativamente com vários fornecedores de hardware para permitir que forneçam as informações necessárias para você ou carregue-o em seu nome. Você também tem a opção de capturar essas informações usando um script do PowerShell que gera um arquivo. csv com a ID de hardware do dispositivo.

        Depois que os dispositivos são registrados, há opções de personalização do OOBE que você pode configurar, incluindo ignorar as configurações de privacidade e o EULA.

    - **Identidade visual da empresa para OOBE**

        Isso permite que você adicione identidade visual a ser exibida durante o dispositivo OOBE.

    - **Registro automático do MDM do Microsoft Intune**
        
        O registro automático permite que os usuários registrem seus dispositivos Windows 10 no Intune para gerenciamento de dispositivos quando conectam seus dispositivos ao Azure AD. Para inscrever-se, os usuários adicionam sua conta de trabalho a seus dispositivos de propriedade pessoal ou participam de dispositivos corporativos para o Azure AD. Em segundo plano, o dispositivo também está inscrito para gerenciamento com o Intune.

    - **Conectividade de rede para os serviços de nuvem usados pelo Windows Autopilot**

        O programa de implantação do AutoPilot do Windows usa vários serviços de nuvem para acessar seus dispositivos em um estado produtivo e esses serviços devem estar acessíveis a partir de dispositivos registrados como dispositivos do Windows AutoPilot. 

    - **Os dispositivos devem estar pré-instalados no Windows 10, versão 1703 ou posterior**

2. Saiba mais sobre o programa de implantação do piloto automático do Windows para sua organização. Você pode selecionar estes programas de implantação:
    - **Microsoft Store para Empresas**
    - **Microsoft Intune**
    - **Centro de parceria**

## <a name="part-2-set-up-a-windows-10-device-for-microsoft-365"></a>Parte 2: configurar um dispositivo Windows 10 para o Microsoft 365
Antes de poder configurar dispositivos Windows para usuários do Microsoft 365, certifique-se de que todos os dispositivos Windows estão executando o Windows 10, versão 1703 (atualização de criadores) ou posterior.

Depois que todos os dispositivos Windows da sua organização tiverem sido atualizados para a atualização do Windows 10 Creators ou já estiverem executando a atualização do Windows 10 Creators, você poderá ingressar nesses dispositivos no Azure Active Directory da sua organização.

### <a name="set-up-a-brand-new-or-newly-upgraded-windows-10-device"></a>Configurar um dispositivo Windows 10 novo ou atualizado com uma marca
Siga estas etapas para configurar um dispositivo usando o arquivo do Windows 10 OOBE em uma marca novo dispositivo executando o Windows 10 Creators Update (ou posterior) ou em um dispositivo que tenha sido atualizado para o Windows 10 Creators Update (ou posterior), mas não tenha saído da configuração.

1. Se você não tiver uma rede sem fio configurada, verifique se conectou o dispositivo à Internet por meio de uma conexão com fio ou Ethernet.
2. Passar pela experiência de instalação do dispositivo Windows. Em um dispositivo novo ou redefinido, a experiência de instalação começa com a **região inicial. Isso é certo?** tela.
3. Execute a configuração do dispositivo Windows 10 até chegar à página **Como você deseja configurar?**. Aqui, selecione **Configurar para uma organização**.
4. Entre usando a conta e a senha do usuário do Microsoft 365. Dependendo da configuração da senha do usuário, você pode ser solicitado a atualizar a senha. 
5. Conclua a configuração do dispositivo Windows 10.

Depois que você terminar, o dispositivo será conectado ao Azure AD da sua organização.

### <a name="set-up-a-device-that-has-already-completed-out-of-box-setup"></a>Configurar um dispositivo que já tenha concluído a configuração da caixa
Se o seu dispositivo tiver o Windows 10 Creators Update (ou posterior) e já tiver saído da configuração, siga estas etapas.

1. No computador Windows do usuário que executa o Windows 10, versão 1703 (atualização de criadores), selecione o logotipo do **Windows** e, em seguida, selecione o ícone **configurações** .
2. Em **Configurações**, vá para **Contas**.
3. Na página **de informações** , selecione **acessar trabalho ou escola** > **se conectar**.
4. Na caixa de diálogo **Configurar uma conta corporativa ou de estudante** , em **ações alternativas**, selecione **Adicionar este dispositivo ao Azure Active Directory**.
5. Na página **faça** logon, insira sua conta corporativa ou de estudante e selecione **Avançar**.
6. Na página **Inserir senha** , digite sua senha e selecione **entrar**.
7. Na página **Verifique se esta é sua organização** , verifique se as informações estão corretas e selecione **ingressar**.
8. Em **tudo o que você está pronto!** , selecione **concluído**.

Depois que você terminar, o usuário será conectado ao Azure AD da sua organização.

### <a name="verify-the-device-is-connected-to-azure-ad"></a>Verifique se o dispositivo está conectado ao Azure AD
Siga estas etapas para verificar o status de sincronização do dispositivo com o Azure AD e comece a usar sua conta do Microsoft 365 no dispositivo. 

1. Abra **configurações**.
2. Na página **trabalho ou escola do Access** , selecione a **área conectado <organization name> a** para expor as **informações** dos botões e **Desconectar**.
3. Selecione **informações** para obter seu status de sincronização.
4. Na página **status da sincronização** , selecione **sincronizar** para obter as políticas de gerenciamento de dispositivos móveis mais recentes no computador.
5. Para começar a usar a conta do Microsoft 365, vá para o botão **Iniciar** do Windows, clique com o botão direito do mouse na imagem da conta atual e selecione **mudar** conta.
6. Entre com o email e a senha da sua organização.

Se você tiver problemas ao usar o Windows 10 em um ambiente corporativo, poderá consultar [as principais soluções de suporte da Microsoft para obter os problemas mais comuns](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions). Esses recursos incluem artigos de KB, atualizações e artigos de biblioteca.

Como ponto de verificação provisório, é possível conferir os [Critérios de saída](windows10-exit-criteria.md#crit-windows10-step3) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![Etapa 4](./media/stepnumbers/Step4.png)| [Monitorar a integridade e a conformidade do dispositivo](windows10-enable-windows-analytics.md) |
