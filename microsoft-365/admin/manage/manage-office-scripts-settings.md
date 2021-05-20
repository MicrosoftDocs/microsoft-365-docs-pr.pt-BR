---
title: Gerenciar configurações dos Scripts do Office
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Saiba como gerenciar Office configurações de Scripts para usuários em sua organização.
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572304"
---
# <a name="manage-office-scripts-settings"></a>Gerenciar configurações dos Scripts do Office

[Office Scripts](/office/dev/scripts)permite que os usuários automatizem tarefas gravando, editando e executando scripts em Excel na web. Office Os scripts funcionam com Power Automate, e os usuários executam scripts em livros de trabalho usando o conector Excel Online (Business). Microsoft 365 administradores podem gerenciar as configurações de scripts Office a partir do centro administrativo Microsoft 365.

## <a name="before-you-begin"></a>Antes de começar

- Para gerenciar Office configurações de Scripts, você deve ser um administrador global. Para obter mais informações, consulte [Sobre papéis administrativos](../add-users/about-admin-roles.md).

- Certifique-se de que os usuários em sua organização tenham uma licença válida para um Microsoft 365 plano comercial ou Office 365 comercial ou EDU que inclua acesso a aplicativos de desktop Office, como um dos seguintes planos:

    - Microsoft 365 Business Standard
    - Microsoft 365 Apps para Pequenos e Médios negócios
    - Microsoft 365 Apps para Grandes Empresas
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Gerenciar a disponibilidade de scripts Office e compartilhamento de scripts

1. No centro administrativo Microsoft 365, vá para a guia **serviços de** configurações do Configurações \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank"></a> Org.

2. Selecione **Office Scripts**.

3. Office Os scripts são ligados por padrão, e todos na sua organização podem acessar e usar o recurso e compartilhar scripts. Para desativar Office Scripts para sua organização, limpe o **Let users automatizar suas tarefas em Excel na Web** caixa de seleção.

4. Se você desligou anteriormente Office Scripts para sua organização e deseja ligá-lo novamente, selecione **Permitir que os usuários automatizem suas tarefas em Excel na Web** e, em seguida, especifique quem pode acessar e usar o recurso:

    - Para permitir que todos os usuários da sua organização acessem e usem Office Scripts, deixe **todos** (o padrão) selecionados.

    - Para permitir que apenas membros de um grupo específico acessem e usem Office Scripts, selecione **Grupo específico** e, em seguida, digite o nome ou o codinome do grupo para adicioná-lo à lista de permissões. Você pode adicionar apenas um grupo à lista de persião, e deve ser um dos seguintes tipos:
        - Microsoft 365 grupo
        - Grupo de distribuição
        - Grupo de segurança
        - Grupo de segurança habilitado para email
    
        Para saber mais sobre os diferentes tipos de grupos, consulte [Compare grupos](../create-groups/compare-groups.md).

5. Para permitir que os usuários com acesso a scripts Office compartilhem seus scripts com outros da sua organização, selecione **Permitir que os usuários com acesso a scripts Office compartilhem seus scripts com outros da organização**. Compartilhar scripts fora de uma organização não é permitido.
 
    > [!NOTE]
    > Se mais tarde você desativar o compartilhamento de scripts para sua organização, os usuários ainda poderão executar scripts compartilhados anteriormente.
 
6. Especifique quais usuários com acesso a scripts Office podem compartilhar seus scripts:
    
    - Para permitir que todos os usuários com acesso a scripts Office compartilhem seus scripts, deixe **todos** (o padrão) selecionados.

    - Para permitir que apenas membros de um grupo específico com acesso a scripts Office compartilhem seus scripts, selecione **grupo específico** e, em seguida, digite o nome ou codinome do grupo para adicioná-lo à lista de permissões. Você pode adicionar apenas um grupo à lista de persião, e deve ser um dos seguintes tipos:
        - Microsoft 365 grupo
        - Grupo de distribuição
        - Grupo de segurança
        - Grupo de segurança habilitado para email
    
        Para saber mais sobre os diferentes tipos de grupos, consulte [Compare grupos](../create-groups/compare-groups.md).

7. Para permitir que os usuários executem seus scripts de Office dentro dos fluxos Power Automate, selecione **Permitir que os usuários com acesso a scripts Office executem seus scripts com Power Automate**. Isso permite que os usuários adicionem etapas de fluxo com a opção de **script Run** [do Connector Online (Business) Excel](/connectors/excelonlinebusiness) ..

    - Para permitir que todos os usuários com acesso a scripts Office usem seus scripts em fluxos, deixe **todos** (o padrão) selecionados.

    - Para permitir que apenas membros de um grupo específico com acesso a scripts Office usem seus scripts em fluxos, selecione **grupo específico** e, em seguida, digite o nome ou o codinome do grupo para adicioná-lo à lista de permissões. Você pode adicionar apenas um grupo à lista de persião, e deve ser um dos seguintes tipos:
        - Microsoft 365 grupo
        - Grupo de distribuição
        - Grupo de segurança
        - Grupo de segurança habilitado para email

        Para saber mais sobre os diferentes tipos de grupos, consulte [Compare grupos](../create-groups/compare-groups.md).

    - Para saber mais sobre o uso de scripts Office com Power Automate, consulte [Executar scripts Office com Power Automate](/office/dev/scripts/develop/power-automate-integration).

8. Selecione **Salvar**.

    Pode levar até 48 horas para que as alterações nas configurações de scripts Office entrem em vigor.

## <a name="next-steps"></a>Próximas etapas

Como Office Scripts trabalha com Power Automate, recomendamos que você revise suas políticas de prevenção de perda de dados (DLP) existentes para garantir que os dados da sua organização permaneçam protegidos enquanto os usuários usam scripts Office. Para obter mais informações, consulte [políticas de prevenção de perdas de dados (DLP).](/power-automate/prevent-data-loss)

## <a name="related-content"></a>Conteúdo relacionado

[Office Documentação técnica de scripts](/office/dev/scripts/) (página de link)\
[Introdução a scripts Office em Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artigo)\
[Compartilhar Office scripts em Excel para a Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artigo)\
[Grave, edite e crie scripts Office em Excel na Web](/office/dev/scripts/tutorials/excel-tutorial) (artigo)
