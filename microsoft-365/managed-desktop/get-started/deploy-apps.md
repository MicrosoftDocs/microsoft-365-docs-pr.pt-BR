---
title: Implantar aplicativos em dispositivos
description: Informações para adicionar e implantar aplicativos em dispositivos da Área de Trabalho Gerenciada da Microsoft.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação, aplicativos, aplicativos de linha de negócios, aplicativos LOB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eb8b984550f301af9d99e738f6db4623aa2cc86
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769101"
---
# <a name="deploy-apps-to-devices"></a>Implantar aplicativos em dispositivos
Parte da integração à Área de Trabalho Gerenciada da Microsoft inclui adicionar e implantar aplicativos aos dispositivos do usuário. Depois de usar o portal da Área de Trabalho Gerenciada da Microsoft, você pode adicionar e implantar seus aplicativos. 

O processo geral tem esta aparência:
1. [Adicionar](#1) aplicativos ao portal da Área de Trabalho Gerenciada da Microsoft – Podem ser aplicativos de linha de negócios (LOB) existentes ou aplicativos da Microsoft Store para Empresas que você sincronize com o Intune. 
2. [Crie grupos do Azure Active Directory (AD)](#2) para atribuição de aplicativos – você usará esses grupos para gerenciar a atribuição do aplicativo.
3. [Atribuir aplicativos aos usuários](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Etapa 1: Adicionar aplicativos ao portal da Área de Trabalho Gerenciada da Microsoft
Você pode adicionar [aplicativos baseados em Win32 ou Windows MSI](#lob-apps)ou aplicativos da [Microsoft Store para](#msfb-apps) Empresas à Área de Trabalho Gerenciada da Microsoft e implantá-los em dispositivos da Área de Trabalho Gerenciada da Microsoft.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Aplicativos baseados em Win32 ou Windows MSI para a Área de Trabalho Gerenciada da Microsoft

Você pode adicionar seus aplicativos de linha de negócios (LOB) ao portal da Área de Trabalho Gerenciada da Microsoft. Para obter informações sobre os requisitos para aplicativos instalados em dispositivos da Área de Trabalho Gerenciada da Microsoft, consulte os requisitos do [aplicativo da Área de Trabalho Gerenciada da Microsoft.](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)

Neste procedimento, você selecionará o tipo de aplicativo que deseja adicionar e, em seguida, configurará e carregará a origem do aplicativo. 

**Para adicionar seu aplicativo LOB ou aplicativo do Windows ao portal da Área de Trabalho Gerenciada da Microsoft**

Você pode entrar no portal da Área de Trabalho Gerenciada da Microsoft ou entrar no Intune e procurar a Área de Trabalho Gerenciada da Microsoft. Mostraremos como entrar no portal da Área de Trabalho Gerenciada da Microsoft. 

1.    Entre no Portal [de Administração da Área de Trabalho Gerenciada da Microsoft.](https://aka.ms/mmdportal) 
2.    Em **Inventário,** selecione **Aplicativos**.
3.    Na carga de trabalho aplicativos, selecione **Adicionar**.
4.    In **Add app**, select **Line-of-business app** or Windows app **(Win32)**.
    - Se você selecionou o aplicativo de linha de **negócios,** confira Adicionar um aplicativo de linha de negócios do Windows ao [Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) para instruções sobre como adicionar e configurar aplicativos de linha de negócios.
    - Se você **selecionou o aplicativo do Windows (Win32),** consulte o gerenciamento de [aplicativos Win32](https://docs.microsoft.com/intune/apps-win32-app-management) para instruções sobre como adicionar e configurar aplicativos do Windows.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Aplicativos da Microsoft Store para Empresas
Se você ainda não se inscreveu na Microsoft Store para Empresas, inscreva-se quando comprar aplicativos. Depois de ter seus aplicativos, você pode sincronize-os com a Área de Trabalho Gerenciada da Microsoft. 

**Para comprar aplicativos da Microsoft Store para Empresas**

1. Entre na [Microsoft Store para Empresas com](https://businessstore.microsoft.com) sua conta de Administrador da Microsoft Store para Empresas.
2. Selecione **Comprar para meu grupo.**
3. Use a Pesquisa para descobrir o aplicativo que você deseja e selecione o aplicativo.
4. Nos detalhes do produto, selecione **Obter o aplicativo.** A Microsoft Store adiciona o aplicativo **aos Seus produtos** para sua organização.

**Para forçar uma sincronização entre o Intune e a Microsoft Store para Empresas**
1. Entre no centro [de administração do Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)
2. Selecione **Conectores de administração** de  >  **locatários e tokens** da Microsoft Store para  >  **Empresas.**
3. Selecione **Sincronizar** para obter os aplicativos que você comprou da Microsoft Store para o Intune.

**Para verificar se uma sincronização entre o Intune e a Microsoft Store para Empresas está ativa**
1. Entre na [Microsoft Store para Empresas com](https://businessstore.microsoft.com) sua conta de Administrador da Microsoft Store para Empresas.
2. Selecione **Gerenciar**.
3. Selecione **Configurações e,** em seguida, **distribuir**.
4. Em **Ferramentas de Gerenciamento,** verifique se o Intune está listado e se o status está **Ativo.**  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Etapa 2: Criar grupos do Azure AD

Crie três grupos do Azure AD para cada aplicativo. Esta tabela descreve os grupos de que você precisará (disponível, obrigatório e desinstalação). 

Tipo de atribuição do aplicativo |    Uso em grupo    | Nome do Azure AD de exemplo
--- | --- | ---
Disponível |  O aplicativo estará disponível no site ou aplicativo do Portal da Empresa. | MMD – *nome do aplicativo* – Disponível
Obrigatório |  O aplicativo é instalado em dispositivos nos grupos selecionados. | MMD – *nome do aplicativo* – Obrigatório
Uninstall |  O aplicativo é desinstalado de dispositivos nos grupos selecionados. | MMD – *nome do aplicativo* – Desinstalar

Adicione seus usuários a esses grupos para disponibilizar o aplicativo, instalar o aplicativo ou remover o aplicativo do dispositivo da Área de Trabalho Gerenciada da Microsoft. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Etapa 3: Atribuir aplicativos aos usuários

**Para atribuir o aplicativo aos usuários**

1. Entre no Portal [de Administração da Área de Trabalho Gerenciada da Microsoft.](https://aka.ms/mmdportal)
2. No painel Área de Trabalho Gerenciada, selecione **Aplicativos.**
3. Na carga de trabalho Aplicativos, selecione o aplicativo ao que você deseja atribuir usuários e selecione Atribuir **grupos de usuários.**
4. Para o aplicativo específico, selecione um tipo de atribuição (Disponível, Obrigatório, Desinstalar) e atribua o grupo apropriado.
5. No painel Atribuir Aplicativos, selecione **OK**.


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Etapas para começar a trabalhar com a Área de Trabalho Gerenciada da Microsoft

1. [Adicionar e verificar contatos do administrador no portal de Administração](add-admin-contacts.md)
2. [Ajustar o acesso condicional](conditional-access.md)
3. [Atribuir licenças](assign-licenses.md)
4. [Implantar o Portal da Empresa do Intune](company-portal.md)
5. [Habilitar Roaming de Estado da Empresa](enterprise-state-roaming.md)
6. [Configurar dispositivos](set-up-devices.md)
7. [Preparar usuários para o uso dos dispositivos](get-started-devices.md)
8. Implantar aplicativos (este tópico)


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
