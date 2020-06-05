---
title: Habilitar dispositivos Windows 10 associados a um domínio para serem gerenciados pelo Microsoft 365 for Business
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Saiba como habilitar o Microsoft 365 para proteger dispositivos do Windows 10 locais associados ao Active Directory em apenas algumas etapas.
ms.openlocfilehash: 857651081fb10856d28dd419333ebef655388407
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564916"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Habilitar dispositivos Windows 10 associados ao domínio para serem gerenciados pelo Microsoft 365 Business Premium

Se sua organização usa o Windows Server Active Directory no local, você pode configurar o Microsoft 365 Business Premium para proteger seus dispositivos Windows 10, mantendo ainda a manutenção do acesso a recursos locais que exigem autenticação local.
Para configurar essa proteção, é possível implementar **dispositivos híbridos associados ao AD do Azure**. Esses dispositivos fazem parte de seu Active Directory local e do Azure Active Directory.

Este vídeo descreve as etapas para configurar isso para o cenário mais comum, que também é detalhado nas etapas a seguir.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Antes de começar, certifique-se de concluir estas etapas:
- Sincronizar os usuários com o Azure AD com o Azure AD Connect.
- Concluir a sincronização da unidade organizacional (OU) do Azure AD Connect.
- Certifique-se de que todos os usuários de domínio sincronizados têm licenças para o Microsoft 365 Business Premium.

Consulte [Synchronize Domain Users to Microsoft](manage-domain-users.md) para obter as etapas.

## <a name="1-verify-mdm-authority-in-intune"></a>1. Verifique a autoridade MDM no Intune

Vá até portal.azure.com e na parte superior da pesquisa de página do Intune.
Na página do Microsoft Intune, selecione **registro de dispositivo** e, na página **visão geral** , verifique se a **autoridade MDM** é o **Intune**.

- Se **MDM Authority** for **None**, clique na **autoridade MDM** para defini-la como **Intune**.
- Se o **MDM Authority** for o **Microsoft Office 365**, acesse **dispositivos**  >  **inscrever dispositivos** e usar a caixa de diálogo **Adicionar autoridade MDM** no direito de adicionar autoridade **MDM do Intune** (a caixa de diálogo **Adicionar autoridade MDM** só estará disponível se a **autoridade MDM** estiver definida como Microsoft Office 365).

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Verifique se o Azure AD está habilitado para ingressar em computadores

- Vá para o centro de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e selecione **Azure Active Directory** (selecione Mostrar tudo se o Azure Active Directory não estiver visível) na lista de **centros de administração** . 
- No **centro de administração do Azure Active Directory**, vá para **Azure Active Directory** , escolha **dispositivos** e **configurações de dispositivo**.
- Verifique se**os usuários podem ingressar em dispositivos no Azure ad** está habilitado 
    1. Para habilitar todos os usuários, defina como **todos**.
    2. Para habilitar usuários específicos, defina como **selecionado** para habilitar um grupo específico de usuários.
        - Adicione os usuários de domínio desejados sincronizados no Azure AD para um [grupo de segurança](../admin/create-groups/create-groups.md).
        - Escolha **Selecionar grupos** para habilitar o escopo de usuário MDM para esse grupo de segurança.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Verifique se o Azure AD está habilitado para MDM

- Vá para o centro de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e selecione Selecionar **ponto de extremidade gerenciar**o t (selecionar **Mostrar tudo** se o **Endpoint Manager** não estiver visível)
- No **centro de administração do Gerenciador de pontos de extremidade da Microsoft**, vá para **dispositivos**  >  **Windows**  >  **Windows Enrollment**  >  **registro automático**do registro do Windows do Windows.
- Verifique se o escopo de usuário MDM está habilitado.

    1. Para inscrever todos os computadores, defina como **todos** para registrar automaticamente todos os computadores de usuários que ingressaram no Azure AD e em novos computadores quando os usuários adicionam uma conta de trabalho ao Windows.
    2. Definido como **alguns** para registrar os computadores de um grupo específico de usuários.
        -  Adicione os usuários de domínio desejados sincronizados no Azure AD para um [grupo de segurança](../admin/create-groups/create-groups.md).
        -  Escolha **Selecionar grupos** para habilitar o escopo de usuário MDM para esse grupo de segurança.

## <a name="4-set-up-service-connection-point-scp"></a>4. configurar ponto de conexão de serviço (SCP)

Essas etapas são simplificadas para [Configurar a União híbrida do Azure ad](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join). Para concluir as etapas de que você precisa para usar o Azure AD Connect e suas senhas de administrador global do Microsoft 365 Business Premium e do Active Directory.

1.  Inicie o Azure AD Connect e selecione **Configurar**.
2.  Na página **tarefas adicionais** , selecione **Configurar opções de dispositivo**e, em seguida, selecione **Avançar**.
3.  Na página **visão geral** , selecione **Avançar**.
4.  Na página **conectar ao Azure ad** , insira as credenciais de um administrador global para o Microsoft 365 Business Premium.
5.  Na página **Opções de dispositivo** , selecione **Configurar ingresso híbrida do Azure ad**e selecione **Avançar**.
6.  Na página **SCP** , para cada floresta onde você deseja que o Azure ad Connect configure o SCP, conclua as seguintes etapas e selecione **Avançar**:
    - Marque a caixa ao lado do nome da floresta. A floresta deve ser o nome de domínio do AD.
    - Na coluna **serviço de autenticação** , abra o menu suspenso e selecione nome de domínio correspondente (deve haver apenas uma opção).
    - Selecione **Adicionar** para inserir as credenciais de administrador de domínio.  
7.  Na página **sistemas operacionais de dispositivos** , selecione somente dispositivos associados ao domínio Windows 10 ou posterior.
8.  Na página **pronto para configurar** , selecione **Configurar**.
9.  Na página **configuração concluída** , selecione **sair**.


## <a name="5-create-a-gpo-for-intune-enrollment--admx-method"></a>5. criar um GPO para registro do Intune – método ADMX

Use. Arquivo de modelo ADMX.

1.  Faça logon no servidor do AD, pesquise e abra o gerenciamento de política de grupo de ferramentas **do Gerenciador de servidores**  >  **Tools**  >  **Group Policy Management**.
2.  Selecione seu nome de domínio em **domínios** e clique com o botão direito do mouse em **objetos de política de grupo** para selecionar **novo**.
3.  Dê um nome ao novo GPO, por exemplo "*Cloud_Enrollment*" e, em seguida, selecione **OK**.
4.  Clique com o botão direito do mouse no novo GPO em **objetos de política de grupo** e selecione **Editar**.
5.  No **Editor de gerenciamento de política de grupo**, vá para configurações do **computador**  >  **Policies**  >  **modelos administrativos**do  >  **Windows**  >  **MDM**
6. Clique com o botão direito do mouse em **habilitar o registro MDM automático usando as credenciais padrão do Azure ad** e selecione **habilitado**  >  **OK**. Feche a janela do editor.

> [!IMPORTANT]
> Se você não vir a política **habilitar o registro MDM automático usando as credenciais padrão do Azure ad**, confira [obter os modelos administrativos mais recentes](#get-the-latest-administrative-templates).

## <a name="6-deploy-the-group-policy"></a>6. implantar a política de grupo

1.  No Gerenciador de servidores, em **domínios** > objetos de política de grupo, selecione o GPO da etapa 3 acima, por exemplo "Cloud_Enrollment".
2.  Selecione a guia **escopo** do GPO.
3.  Na guia escopo do GPO, clique com o botão direito do mouse no link para o domínio em **links**.
4.  Selecione **Enforced** para implantar o GPO e, em seguida, **OK** na tela de confirmação.

## <a name="get-the-latest-administrative-templates"></a>Obter os modelos administrativos mais recentes

Se você não vir a política **habilitar o registro MDM automático usando as credenciais padrão do Azure ad**, talvez você não tenha o ADMX instalado para o Windows 10, a versão 1803, a versão 1809 ou a versão 1903. Para corrigir o problema, siga estas etapas (Observação: o MDM. admx mais recente é compatível com versões anteriores):

1.  Download: [modelos administrativos (. admx) para Windows 10 pode 2019 atualização (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).
2.  Instale o pacote no controlador de domínio primário (PDC).
3.  Navegue, dependendo da versão para a pasta: C:\Arquivos de **programas (x86) \Microsoft Group Policy\Windows 10 de maio de 2019 Update (1903) v3**.
4.  Renomeie a pasta de **definições de política** no caminho acima para **PolicyDefinitions,**.
5.  Copie a pasta **PolicyDefinitions,** para **C:\Windows\SYSVOL\domain\Policies**. 
    -   Se você planeja usar um repositório de política central para o seu domínio inteiro, adicione o conteúdo de PolicyDefinitions, ali.
6.  Reinicie o controlador de domínio primário para que a política fique disponível. Este procedimento também funcionará para qualquer versão futura.

Neste ponto, você deve ser capaz de ver a política **habilitar o registro MDM automático usando as credenciais padrão do Azure ad** disponíveis.

