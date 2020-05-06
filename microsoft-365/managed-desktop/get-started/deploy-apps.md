---
title: Implantar aplicativos em dispositivos
description: Informações para adicionar e implantar aplicativos em dispositivos de área de trabalho gerenciada da Microsoft.
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação, aplicativos, aplicativos de linha de negócios, aplicativos LOB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9fd6efc56441cfbe8a05404319246c5e0bbe10ab
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046323"
---
# <a name="deploy-apps-to-devices"></a>Implantar aplicativos em dispositivos
Parte da integração com a área de trabalho gerenciada da Microsoft inclui a adição e implantação de aplicativos aos dispositivos do usuário. Quando estiver usando o portal de área de trabalho gerenciada da Microsoft, você poderá adicionar e implantar seus aplicativos. 

O processo geral tem a seguinte aparência:
1. [Adicionar aplicativos ao Microsoft Managed desktop portal](#1) – pode ser aplicativos LOB (linha de negócios) existentes ou aplicativos da Microsoft Store para empresas que você sincronizou com o Intune. 
2. [Criar grupos do Azure Active Directory (AD) para a atribuição de aplicativos](#2) -você usará esses grupos para gerenciar a atribuição de aplicativos.
3. [Atribuir aplicativos aos usuários](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Etapa 1: adicionar aplicativos ao portal de área de trabalho gerenciada da Microsoft
Você pode adicionar [aplicativos baseados em Win32 ou Windows MSI](#lob-apps), ou [Microsoft Store para aplicativos de negócios](#msfb-apps) à área de trabalho gerenciada da Microsoft e implantá-los em dispositivos de área de trabalho gerenciada da Microsoft.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Aplicativos baseados em Win32 ou Windows MSI para a área de trabalho gerenciada da Microsoft

Você pode adicionar seus aplicativos de linha de negócios (LOB) ao portal de área de trabalho gerenciada da Microsoft. Para obter informações sobre os requisitos para aplicativos instalados em dispositivos de área de trabalho gerenciada da Microsoft, consulte [requisitos de aplicativos de área de trabalho gerenciado da Microsoft](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)

Neste procedimento, você selecionará o tipo de aplicativo que você deseja adicionar e, em seguida, configurar e carregar a origem do aplicativo. 

**Para adicionar seu aplicativo LOB ou aplicativo do Windows ao portal de área de trabalho gerenciada da Microsoft**

Você pode entrar no portal de área de trabalho gerenciada da Microsoft ou entrar no Intune e, em seguida, procurar pela área de trabalho gerenciada da Microsoft. Mostraremos a entrada no portal de área de trabalho gerenciada da Microsoft. 

1.    Entre no [portal de administração de área de trabalho gerenciada da Microsoft](https://aka.ms/mmdportal). 
2.    Em **inventário**, selecione **aplicativos**.
3.    Na carga de trabalho aplicativos, selecione **Adicionar**.
4.    Em **Adicionar aplicativo**, selecione **aplicativo de linha de negócios** ou **Windows app (Win32)**.
    - Se você selecionou o **aplicativo de linha de negócios**, consulte [Adicionar um aplicativo de linha de negócios do Windows ao Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) para obter instruções sobre como adicionar e configurar aplicativos de linha de negócios.
    - Se você tiver selecionado o **Windows app (Win32)**, confira o [Win32 app Management](https://docs.microsoft.com/intune/apps-win32-app-management) para instruções sobre como adicionar e configurar aplicativos do Windows.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Aplicativos da Microsoft Store para empresas
Se você ainda não se inscreveu na Microsoft Store para empresas, você pode se inscrever ao comprar aplicativos. Depois de ter seus aplicativos, você pode sincronizá-los com a área de trabalho gerenciada da Microsoft. 

**Comprar aplicativos da Microsoft Store para empresas**

1. Entre na [Microsoft Store para empresas](https://businessstore.microsoft.com) com sua conta de administrador do Microsoft Store para empresas.
2. Selecione **comprar para meu grupo**.
3. Use a pesquisa para encontrar o aplicativo desejado e selecione o aplicativo.
4. Nos detalhes do produto, selecione **obter o aplicativo**. A Microsoft Store adiciona o aplicativo aos **seus produtos** para sua organização.

**Para forçar uma sincronização entre o Intune e a Microsoft Store para empresas**
1. Entrar no [portal do Azure](https://portal.azure.com/) como administrador do Intune ou administrador global para o locatário
2. Selecione **todos os serviços > Intune**. O Intune está na seção monitoramento + gerenciamento.
3. No painel do Intune, selecione **aplicativos cliente**e, em seguida, selecione **Microsoft Store para empresas**.
4. Selecione **habilitar** para sincronizar seus aplicativos da Microsoft Store para empresas com o Intune.
    - Se você ainda não tiver feito isso, Inscreva-se e associe sua conta da Microsoft Store para empresas com o Intune
    - Selecione o idioma no qual os aplicativos da Microsoft Store para empresas serão exibidos no seu console do Intune
    - Selecione **sincronizar** para sincronizar seus aplicativos da Microsoft Store para empresas com o Intune.
    - Verifique se a sincronização entre a Microsoft Store para empresas e o Intune está ativa (próxima etapa). 

**Para verificar se uma sincronização entre o Intune e a Microsoft Store para empresas está ativa**
1. Entre na [Microsoft Store para empresas](https://businessstore.microsoft.com) com sua conta de administrador do Microsoft Store para empresas.
2. Selecione **gerenciar**.
3. Selecione **configurações** e, em seguida, **distribuir**.
4. Em **ferramentas de gerenciamento**, verifique se o Intune está listado e se o status está **ativo**.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Etapa 2: criar grupos do Azure AD

Crie três grupos do Azure AD para cada aplicativo. Esta tabela descreve os grupos que você precisará (disponível, obrigatório e desinstalação). 

Tipo de atribuição de aplicativo |    Uso de grupo    | Exemplo de nome do Azure AD
--- | --- | ---
Disponível |  O aplicativo estará disponível no site ou aplicativo do portal da empresa. | MMD – *nome do aplicativo* – disponível
Obrigatório |  O aplicativo é instalado em dispositivos nos grupos selecionados. | MMD – *nome do aplicativo* – obrigatório
Uninstall |  O aplicativo é desinstalado de dispositivos nos grupos selecionados. | MMD – *nome do aplicativo* – desinstalar

Adicione seus usuários a esses grupos para fazer com que o aplicativo disponibilize, instalar o aplicativo ou remover o aplicativo do dispositivo de área de trabalho gerenciado da Microsoft. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Etapa 3: atribuir aplicativos aos seus usuários

**Para atribuir o aplicativo aos seus usuários**

1. Entre no [portal de administração de área de trabalho gerenciada da Microsoft](https://aka.ms/mmdportal).
2. No painel da área de trabalho gerenciada, selecione **aplicativos**.
3. Na carga de trabalho aplicativos, selecione o aplicativo para o qual você deseja atribuir usuários e selecione **atribuir usuários grupos**.
4. Para o aplicativo específico, selecione um tipo de atribuição (disponível, obrigatório, desinstalação) e atribua o grupo apropriado.
5. No painel atribuir aplicativos, selecione **OK**.


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Etapas para começar a usar a área de trabalho gerenciada da Microsoft

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
