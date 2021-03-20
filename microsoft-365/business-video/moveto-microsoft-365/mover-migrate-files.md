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
ms.openlocfilehash: 6feabff7e36e84f7dba56e74333648325cf43920
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913569"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>Migrar arquivos do Google para o Microsoft 365 para empresas 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

Ao mudar para o Microsoft 365 para empresas, você vai querer migrar seus arquivos do Google Drive. Você pode usar o aplicativo Mover para mover arquivos de unidades pessoais e compartilhadas. Para obter mais informações, consulte [Mover Migração de Nuvem](/sharepointmigration/mover-plan-migration).

> [!NOTE]
> Mover fará uma cópia dos arquivos e moverá as cópias para o Microsoft 365 para empresas. Os arquivos originais também permanecerão no Google Drives.

## <a name="before-you-start"></a>Antes de começar

Todos os usuários devem ter se assinado no Microsoft 365 para empresas e configurar o OneDrive for Business. Para fazer isso, vá para [office.com](https://office.com), entre com suas credenciais do Microsoft 365 para empresas e escolha OneDrive.

## <a name="try-it"></a>Experimente!

### <a name="install-mover"></a>Instalar o Mover

1. Entre no console de administração do Google Workspace [em](https://admin.google.com)admin.google.com .

1. Escolha   >  **Aplicativos Google Workspace Marketplace**  >  **aplicativos Adicionar aplicativo à lista instalação de domínio**.

1. Pesquise Mover e selecione-o.

1. Escolha **Instalação de Domínio,** em **seguida, Continue**.

1. Revise as permissões, marque a caixa de seleção para concordar com os termos e selecione **Permitir**, escolha **Próximo** e **Pronto.**

### <a name="create-connectors-and-run-the-migration"></a>Criar Conectores e executar a migração

1. Retorne aos **aplicativos do Google Workspace Marketplace.**
1. Atualize seu navegador e selecione o **aplicativo Mover.**
1. Role para baixo e escolha o link de navegação universal.
1. Selecione **Autorizar Novo Conector,** **localize G Suite (Admin)** e escolha **Autorizar**.
1. Altere **o Nome de Exibição**, se quiser, em seguida, selecione **Autorizar**.
1. Escolha uma conta de administrador do Google, revise as permissões e selecione **Permitir**.

    Mover exibe o número de unidades de equipe e unidades de usuário descobertas. 

1. Em **Selecionar destino,** escolha **Autorizar Novo Conector,** localize **o Office 365** e selecione **Autorizar**.
1. Para conceder permissões ao aplicativo Mover em seu Azure Active Directory, navegue até [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).
1. Selecione **Office 365 Mover**, **Permissões,** **Conceder consentimento de administrador para sua empresa**.
1. Escolha sua conta, revise as permissões e selecione **Aceitar**.
1. Escolha **Propriedades** e verifique se **a atribuição de usuário é necessária?** está ativas.
1. Retorne ao aplicativo Mover, altere o **Nome** de Exibição , se quiser, escolha **Autorizar** e selecione uma conta de administrador da Microsoft.

    O Mover informará sobre o número de sites do SharePoint Online (ou SPO) e dos usuários descobertos.
1. Escolha **Continuar a Instalação de Migração,** selecione Adicionar **Usuários** e, em **seguida, Descobrir e Adicionar Usuários automaticamente.**

    O aplicativo Mover tentará mapear unidades do Caminho de Origem no Google, para o Caminho de Destino no Microsoft 365. 

    Se uma unidade não mapear automaticamente, adicione seu caminho de destino a um arquivo CSV, que vamos usar mais tarde para migrar a unidade compartilhada para uma biblioteca de documentos do SharePoint. 

1. Nesse caso, adicionamos um site do SharePoint chamado Arquivos Migrados e anotamos a URL da página de documentos. 
1. Em seguida, criamos um arquivo CSV usando o formato de Caminho de Origem, Caminho de Destino e Marcas. 

    Para obter detalhes, [consulte aka.ms/movercsv](/sharepointmigration/mover-create-migration-csv).

    Ao adicionar a URL do Caminho de Destino, remova tudo depois de Documentos Compartilhados. Por exemplo, esta URL completa não funcionará: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    Altere-o para: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. Depois que o arquivo CSV estiver pronto, selecione **Ações** de Migração , **Adicionar** à Migração, **Escolha um arquivo para carregar**.
1. Navegue até o arquivo CSV, selecione-o e escolha **Abrir**.
1. Selecione as unidades de usuário cujos arquivos você deseja migrar e, em seguida, **escolha Iniciar Migração de Usuários**.
1. Revise as informações de migração, escolha quando iniciar a migração, concorde com os Termos e **Condições** e selecione **Continuar**.

O aplicativo Mover informará quando o processo de migração for concluído.