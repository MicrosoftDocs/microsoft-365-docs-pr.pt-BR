---
title: 'Migrar arquivos do Google para o Microsoft 365 para empresas '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como migrar arquivos do Google para o Microsoft 365 para empresas usando o Mover.
ms.openlocfilehash: 72ea81ad86a20e01b4650915fef96a713b207c3b
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166154"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>Migrar arquivos do Google para o Microsoft 365 para empresas 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

Ao migrar para o Microsoft 365 para empresas, você vai querer migrar seus arquivos do Google Drive. Você pode usar o aplicativo Mover para mover arquivos de Unidades pessoais e compartilhadas. Para obter mais informações, consulte [Mover Migração de Nuvem.](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)

> [!NOTE]
> O Mover fará uma cópia dos arquivos e move as cópias para o Microsoft 365 para empresas. Os arquivos originais também permanecerão no Google Drives.

## <a name="before-you-start"></a>Antes de começar

Todos os usuários devem ter feito o acesso ao Microsoft 365 para empresas e configurar o OneDrive for Business. Para fazer isso, acesse [office.com,](https://office.com)entre com suas credenciais do Microsoft 365 para empresas e escolha o OneDrive.

## <a name="try-it"></a>Experimente!

### <a name="install-mover"></a>Instalar o Mover

1. Entre no console de administração do Espaço de Trabalho do Google [admin.google.com.](https://admin.google.com)

1. Choose **Apps**  >  **Google Workspace Marketplace apps** Add app to Domain Install  >  **list**.

1. Procure o Mover e selecione-o.

1. Choose **Domain Install**, then **Continue**.

1. Revise as permissões, marque a caixa de seleção para concordar com os termos, em seguida, selecione **Permitir**, escolher **Próximo**, em **seguida, Feito**.

### <a name="create-connectors-and-run-the-migration"></a>Criar conectores e executar a migração

1. Retorne aos **aplicativos do Google Workspace Marketplace.**
1. Atualize o navegador e selecione o **aplicativo Mover.**
1. Role para baixo e escolha o link de navegação universal.
1. Selecione **Autorizar Novo Conector,** **localize G Suite (Administrador)** e escolha **Autorizar.**
1. Altere **o Nome de Exibição,** se quiser, selecione **Autorizar.**
1. Escolha uma conta de administrador do Google, revise as permissões e selecione **Permitir.**

    O Mover exibe o número de unidades de equipe e unidades de usuário descobertas por ele. 

1. Em **Selecionar destino,** escolha **Autorizar Novo Conector,** **localize o Office 365** e selecione **Autorizar.**
1. Para conceder permissões ao aplicativo Mover no Azure Active Directory, navegue até [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).
1. Selecione **Office 365 Mover**, **Permissões,** **Conceder consentimento de administrador para sua empresa**.
1. Escolha sua conta, revise as permissões e selecione **Aceitar**.
1. Choose **Properties** and verify that **User assignment required?** is turned on.
1. Retorne ao aplicativo Mover, altere o **Nome** para Exibição, se quiser, escolha **Autorizar** e selecione uma conta de administrador da Microsoft.

    O Mover informará sobre o número de sites e usuários do SharePoint Online (ou SPO) descobertos.
1. Choose **Continue Migration Setup**, select Add **Users**, then Automatically Discover and **Add Users**.

    O aplicativo Mover tentará mapear unidades do Caminho de Origem no Google para o Caminho de Destino no Microsoft 365. 

    Se uma unidade não for mapeado automaticamente, adicione seu caminho de destino a um arquivo CSV, que será usado posteriormente para migrar a unidade compartilhada para uma biblioteca de documentos do SharePoint. 

1. Nesse caso, adicionamos um site do SharePoint chamado Arquivos migrados e anotamos a URL da página de documentos. 
1. Em seguida, criamos um arquivo CSV usando o formato de Caminho de Origem, Caminho de Destino e Marcas. 

    Para obter [detalhes, consulte aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).

    Ao adicionar a URL do Caminho de Destino, remova tudo após Documentos Compartilhados. Por exemplo, esta URL completa não funcionará: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    Altere-o para: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. Quando o arquivo CSV estiver pronto, selecione **Ações** de Migração, **Adicionar** à Migração, **Escolher um arquivo para carregar.**
1. Navegue até o arquivo CSV, selecione-o e escolha **Abrir.**
1. Selecione as unidades de usuário cujos arquivos você deseja migrar e escolha **Iniciar Migração de Usuários.**
1. Revise as informações de migração, escolha quando iniciar a migração, concorde com os Termos e **Condições** e selecione **Continuar**.

O aplicativo Mover informará quando o processo de migração for concluído.
