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
ms.openlocfilehash: 6275c6c4be9cd9631ab095f8b0e1b39683022bb2
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560834"
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

Vá para o [Gerenciador de pontos de extremidade](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) e, na página do Microsoft Intune, selecione registro de **dispositivo**e, na página **visão geral** , verifique se a **autoridade MDM** é o **Intune**.

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

## <a name="4-create-the-required-resources"></a>4. criar os recursos necessários 

A execução das tarefas necessárias para [Configurar o Azure ad Join híbrido](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) foi simplificada por meio do uso do cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) encontrado no módulo [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell. Quando você invocar este cmdlet, ele criará e configurará o ponto de conexão de serviço e a política de grupo necessários.

Você pode instalar este módulo chamando o seguinte em uma instância do PowerShell:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> É recomendável que você instale este módulo no Windows Server que executa o Azure AD Connect.

Para criar o ponto de conexão de serviço necessário e a política de grupo, você chamará o cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) . Você precisará de suas credenciais de administrador global do Microsoft 365 Business Premium ao executar essa tarefa. Quando estiver pronto para criar os recursos, chame o seguinte:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

O primeiro comando estabelecerá uma conexão com a nuvem da Microsoft e, quando for solicitado, especifique suas credenciais de administrador global do Microsoft 365 Business Premium.

## <a name="5-link-the-group-policy"></a>5. vincular a política de grupo

1. No GPMC (console de gerenciamento de política de grupo), clique com o botão direito do mouse no local onde você deseja vincular a política e selecione *vincular um GPO existente...* no menu de contexto.
2. Selecione a política criada na etapa acima e clique em **OK**.

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
