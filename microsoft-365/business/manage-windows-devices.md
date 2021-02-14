---
title: Permitir que dispositivos Windows 10 ingressados no domínio sejam gerenciados pelo Microsoft 365 para empresas
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
description: Saiba como habilitar o Microsoft 365 para proteger dispositivos Windows 10 ingressados no Active Directory local em apenas algumas etapas.
ms.openlocfilehash: 6275c6c4be9cd9631ab095f8b0e1b39683022bb2
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560834"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Permitir que dispositivos Windows 10 ingressados no domínio sejam gerenciados pelo Microsoft 365 Business Premium

Se sua organização usa o Windows Server Active Directory local, você pode configurar o Microsoft 365 Business Premium para proteger seus dispositivos Windows 10, enquanto ainda mantém o acesso a recursos locais que exigem autenticação local.
Para configurar essa proteção, você pode implementar dispositivos ingressados no **Azure AD híbrido.** Esses dispositivos são ingressados no Active Directory local e no Azure Active Directory.

Este vídeo descreve as etapas para configurar isso para o cenário mais comum, que também é detalhado nas etapas a seguir.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Antes de começar, certifique-se de concluir estas etapas:
- Sincronizar usuários com o Azure AD com o Azure AD Connect.
- Conclua a sincronização da Unidade Organizacional (UO) do Azure AD Connect.
- Certifique-se de que todos os usuários de domínio sincronizados tenham licenças para o Microsoft 365 Business Premium.

Consulte [Sincronizar usuários de domínio com a Microsoft](manage-domain-users.md) para ver as etapas.

## <a name="1-verify-mdm-authority-in-intune"></a>1. Verifique a autoridade MDM no Intune

Vá para o [Gerenciador de](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) Pontos de Extremidade e, na  página do Microsoft Intune, selecione Registro de dispositivo e, na página Visão geral, certifique-se de que a autoridade **MDM** seja **o Intune.**

- Se **a autoridade MDM** for **Nenhuma,** clique na autoridade **MDM** para defini-la como **Intune.**
- Se a autoridade **MDM** for o Microsoft  **Office 365,** vá para Dispositivos Registrar dispositivos e use a caixa de diálogo Adicionar autoridade MDM à direita para adicionar autoridade MDM do Intune (a caixa de diálogo Adicionar Autoridade MDM só estará disponível se a Autoridade MDM estiver definida como Microsoft Office  >   365).    

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Verifique se o Azure AD está habilitado para ingressar em computadores

- Vá para o centro de administração em e selecione <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **Azure Active Directory** (selecione Mostrar tudo se o Azure Active Directory não estiver visível) na lista **centros de** administração. 
- No centro **de administração do Azure Active Directory,** vá para **o Azure Active Directory,** **escolha** Dispositivos e, em seguida, **configurações do dispositivo.**
- Verificar **se os usuários podem ingressar dispositivos no Azure AD** está habilitado 
    1. Para habilitar todos os usuários, de definida como **Todos.**
    2. Para habilitar usuários específicos, de definida **como Selecionado** para habilitar um grupo específico de usuários.
        - Adicione os usuários de domínio desejados sincronizados no Azure AD a um grupo [de segurança.](../admin/create-groups/create-groups.md)
        - Escolha **Selecionar grupos para** habilitar o escopo de usuário do MDM para esse grupo de segurança.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Verifique se o Azure AD está habilitado para MDM

- Vá para o centro de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  e selecione **Endpoint Managemen** t (selecione **Mostrar tudo** se o **Gerenciador de** Ponto de Extremidade não estiver visível)
- No centro **de administração do Microsoft Endpoint Manager,** vá para **Dispositivos** do Registro Automático do  >    >  **Windows no**  >  **Windows.**
- Verifique se o escopo do usuário do MDM está habilitado.

    1. Para registrar todos os  computadores, de definida como Todos para registrar automaticamente todos os computadores de usuários que ingressaram no Azure AD e novos computadores quando os usuários adicionarem uma conta de trabalho ao Windows.
    2. De definida **como Alguns** para registrar os computadores de um grupo específico de usuários.
        -  Adicione os usuários de domínio desejados sincronizados no Azure AD a um grupo [de segurança.](../admin/create-groups/create-groups.md)
        -  Escolha **Selecionar grupos para** habilitar o escopo de usuário do MDM para esse grupo de segurança.

## <a name="4-create-the-required-resources"></a>4. Crie os recursos necessários 

A execução das tarefas necessárias para configurar o [Azure AD](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) híbrido foi simplificada por meio do uso do cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) encontrado no módulo [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell. Quando você invoca esse cmdlet, ele cria e configura o ponto de conexão de serviço e a política de grupo necessários.

Você pode instalar esse módulo invocando o seguinte de uma instância do PowerShell:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> É recomendável que você instale esse módulo no Windows Server que executa o Azure AD Connect.

Para criar o ponto de conexão de serviço e a política de grupo necessários, você invocará o cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) Você precisará das suas credenciais de administrador global do Microsoft 365 Business Premium ao executar essa tarefa. Quando você estiver pronto para criar os recursos, invoque o seguinte:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

O primeiro comando estabelecerá uma conexão com a nuvem da Microsoft e, quando solicitado, especifique suas credenciais de administrador global do Microsoft 365 Business Premium.

## <a name="5-link-the-group-policy"></a>5. Vincular a Política de Grupo

1. No Console de Gerenciamento de Política de Grupo (GPMC), clique com o botão direito do mouse no local onde você deseja vincular a política e selecione Vincular um *GPO existente...* no menu de contexto.
2. Selecione a política criada na etapa acima e clique em **OK.**

## <a name="get-the-latest-administrative-templates"></a>Obter os Modelos Administrativos mais recentes

Se você não vir a política Habilitar o registro automático no MDM usando credenciais padrão do **Azure AD,** pode ser porque você não tem o ADMX instalado para o Windows 10, versão 1803, versão 1809 ou versão 1903. Para corrigir o problema, siga estas etapas (Observação: o MDM.admx mais recente é compatível com versões anteriores):

1.  Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).
2.  Instale o pacote no PDC (Controlador de Domínio Principal).
3.  Navegue, dependendo da versão para a pasta: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3.**
4.  Renomeie a **pasta Definições de** Política no caminho acima para **PolicyDefinitions**.
5.  Copie **a pasta PolicyDefinitions** **para C:\Windows\SYSVOL\domain\Policies**. 
    -   Se você planeja usar um armazenamento de política central para todo o seu domínio, adicione o conteúdo de PolicyDefinitions lá.
6.  Reinicie o Controlador de Domínio Primário para que a política seja disponibilizada. Esse procedimento também funcionará para qualquer versão futura.

Neste ponto, você deverá ser capaz de ver a política Habilitar o registro automático no MDM usando as credenciais padrão do **Azure AD** disponíveis.
