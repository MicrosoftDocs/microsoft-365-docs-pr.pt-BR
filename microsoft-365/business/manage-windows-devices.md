---
title: Habilitar dispositivos Windows 10 de domínio a serem gerenciados pelo Microsoft 365 para empresas
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Saiba como habilitar Microsoft 365 proteger os dispositivos locais ingressados no Active-Directory Windows 10 em apenas algumas etapas.
ms.openlocfilehash: f16962dd3c33c3c228da507bc5c4a902d76a8a08
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593884"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Habilitar dispositivos Windows 10 de domínio a serem gerenciados por Microsoft 365 Business Premium

Se a sua organização usa o Windows Active Directory no local, você pode configurar um Microsoft 365 Business Premium para proteger seus dispositivos Windows 10, enquanto ainda mantém o acesso a recursos locais que exigem autenticação local.
Para configurar essa proteção, você pode implementar **dispositivos ingressados no Azure AD híbridos.** Esses dispositivos são ingressados no Active Directory local e no Azure Active Directory.

Este vídeo descreve as etapas de como configurar isso para o cenário mais comum, que também é detalhado nas etapas a seguir.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Antes de começar, certifique-se de concluir estas etapas:
- Sincronizar usuários com o Azure AD com o Azure AD Conexão.
- Conclua a sincronização da UO (Unidade Organizacional) do Azure A Conexão D.
- Certifique-se de que todos os usuários de domínio sincronizados tenham licenças para Microsoft 365 Business Premium.

Consulte [Sincronizar usuários de domínio com a Microsoft](manage-domain-users.md) para ver as etapas.

## <a name="1-verify-mdm-authority-in-intune"></a>1. Verifique a autoridade MDM no Intune

Vá para [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) e, na página Microsoft Intune, selecione Registro de  dispositivo **,** em seguida, na página Visão geral, certifique-se de que a autoridade **MDM** seja **o Intune**.

- Se **a autoridade MDM** for **None**, clique na **autoridade MDM** para defini-la como **Intune**.
- Se **a autoridade MDM** for Microsoft Office 365 ,vá para Dispositivos Registrar dispositivos e use **a** caixa de diálogo Adicionar autoridade MDM à direita para adicionar autoridade  >   MDM do **Intune** (a caixa de diálogo **Adicionar Autoridade MDM** só estará disponível se a **Autoridade MDM** estiver definida como Microsoft Office 365). 

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Verifique se o Azure AD está habilitado para ingressar em computadores

- Vá para o centro de administração em e selecione Azure Active Directory (selecione Mostrar tudo se Azure Active Directory não estiver visível) na <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> lista Centros **de** administração.  
- No centro **Azure Active Directory de administração,** vá **para Azure Active Directory,** escolha **Dispositivos** e, em seguida, **Configurações do dispositivo.**
- Verificar **se os usuários podem ingressar em dispositivos no Azure AD** está habilitado 
    1. Para habilitar todos os usuários, de acordo com **All**.
    2. Para habilitar usuários específicos, de acordo **com Selected** para habilitar um grupo específico de usuários.
        - Adicione os usuários de domínio desejados sincronizados no Azure AD a um grupo [de segurança](../admin/create-groups/create-groups.md).
        - Escolha **Selecionar grupos** para habilitar o escopo de usuário MDM para esse grupo de segurança.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Verifique se o Azure AD está habilitado para o MDM

- Vá para o centro de administração em e selecione Gerenciar Pontos de Extremidade t (selecione Mostrar tudo se Endpoint Manager <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> não estiver visível)   
- No centro **de administração Microsoft Endpoint Manager**, vá para **Dispositivos**  >  **Windows**  >  **Windows Registro** Automático de  >  **Registro.**
- Verifique se o escopo do usuário do MDM está habilitado.

    1. Para registrar todos os  computadores, desmarco como Todos para registrar automaticamente todos os computadores de usuários que estão ingressados no Azure AD e novos computadores quando os usuários adicionarem uma conta de trabalho a Windows.
    2. De definida **como Alguns** para registrar os computadores de um grupo específico de usuários.
        -  Adicione os usuários de domínio desejados sincronizados no Azure AD a um grupo [de segurança](../admin/create-groups/create-groups.md).
        -  Escolha **Selecionar grupos** para habilitar o escopo de usuário MDM para esse grupo de segurança.

## <a name="4-create-the-required-resources"></a>4. Crie os recursos necessários 

A execução das tarefas necessárias para configurar a junção híbrida do [Azure AD](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) foi simplificada por meio do uso do cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) encontrado no módulo [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell. Quando você invocar esse cmdlet, ele criará e configurará o ponto de conexão de serviço necessário e a política de grupo.

Você pode instalar este módulo invocando o seguinte de uma instância do PowerShell:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> É recomendável instalar esse módulo no servidor Windows que executa o Azure AD Conexão.

Para criar o ponto de conexão de serviço necessário e a política de grupo, você invocará o cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) Você precisará de suas Microsoft 365 Business Premium de administrador global ao executar essa tarefa. Quando estiver pronto para criar os recursos, invoque o seguinte:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

O primeiro comando estabelecerá uma conexão com a nuvem da Microsoft e, quando você for solicitado, especifique suas Microsoft 365 Business Premium de administrador global.

## <a name="5-link-the-group-policy"></a>5. Vincular a Política de Grupo

1. No Console de Gerenciamento de Política de Grupo (GPMC), clique com o botão direito do mouse no local onde você deseja vincular a política e selecione Vincular um *GPO existente...* no menu de contexto.
2. Selecione a política criada na etapa acima e clique em **OK**.

## <a name="get-the-latest-administrative-templates"></a>Obter os modelos administrativos mais recentes

Se você não vir a política Habilitar o registro automático do MDM usando credenciais padrão do **Azure AD**, pode ser porque você não tem o ADMX instalado para Windows 10, versão 1803 ou posterior. Para corrigir o problema, siga estas etapas (Observação: o MDM.admx mais recente é compatível com versões anteriores):

1.  Download: Modelos Administrativos (.admx) para Windows 10 atualização de outubro de [2020 (20H2)](https://www.microsoft.com/download/102157).
2.  Instale o pacote em um Controlador de Domínio.
3.  Navegue, dependendo da versão Modelos Administrativos para a pasta: C:\Arquivos de Programas (x86)\Política de Grupo da Microsoft\Windows 10 atualização de outubro de **2020 (20H2)**.
4.  Renomeie a **pasta Definições de** Política no caminho acima para **PolicyDefinitions**.
5.  Copie a **pasta PolicyDefinitions** para seu compartilhamento SYSVOL, por padrão localizado em **C:\Windows\SYSVOL\domain\Policies**. 
    -   Se você planeja usar um armazenamento de política central para todo o seu domínio, adicione o conteúdo de PolicyDefinitions lá.
6.  Caso você tenha vários Controladores de Domínio, aguarde que o SYSVOL replique para que as políticas sejam disponibilizadas. Este procedimento funcionará para qualquer versão futura dos Modelos Administrativos também.

Neste ponto, você deve ser capaz de ver a política Habilitar o registro automático do MDM usando credenciais padrão do **Azure AD** disponíveis.

## <a name="related-content"></a>Conteúdo relacionado

[Sincronizar usuários de domínio para Microsoft 365](manage-domain-users.md) (artigo)

[Criar um grupo no centro de administração](../admin/create-groups/create-groups.md) (artigo)

[Tutorial: Configure hybrid Azure Active Directory join for managed domains](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (article)