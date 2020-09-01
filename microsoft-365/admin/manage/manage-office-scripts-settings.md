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
description: Saiba como gerenciar as configurações de scripts do Office para usuários em sua organização.
ms.openlocfilehash: 44e2a5c0e0577db344fdbb00a110674df3e71bdc
ms.sourcegitcommit: 04f196528a7a91b404478553433af3fa94d7eee7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2020
ms.locfileid: "47317488"
---
# <a name="manage-office-scripts-settings"></a>Gerenciar configurações dos Scripts do Office

Os scripts do Office permitem que os usuários automatizem tarefas gravando, editando e executando scripts no Excel na Web. Os scripts do Office funcionam com a automatização de energia, e os usuários executam scripts em pastas de trabalho usando o conector do Excel online (Business). Os administradores do Microsoft 365 podem gerenciar as configurações de scripts do Office no centro de administração do Microsoft 365.

## <a name="before-you-begin"></a>Antes de começar

- Para gerenciar as configurações de scripts do Office, você deve ser um administrador global. Para obter mais informações, consulte [sobre funções de administrador](../add-users/about-admin-roles.md).

- Verifique se os usuários da sua organização têm uma licença válida para um plano comercial ou EDU do Microsoft 365 ou do Office 365 que inclui acesso aos aplicativos da área de trabalho do Office, como um dos seguintes planos:

    - Microsoft 365 Business Standard
    - Aplicativos do Microsoft 365 para empresas
    - Microsoft 365 Apps para empresas
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Gerenciar a disponibilidade de scripts do Office e compartilhamento de scripts

1. No centro de administração do Microsoft 365, vá para **Settings** a \> Guia serviços de configurações da **organização** configurações \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> .

2. Selecione **scripts do Office**.

3. Os scripts do Office são ativados por padrão, e todos em sua organização podem acessar e usar o recurso e compartilhar scripts. Para desativar os scripts do Office para sua organização, desmarque a caixa de seleção **permitir que os usuários automatizem suas tarefas no Excel na Web** .

4. Se você desativou anteriormente os scripts do Office para sua organização e deseja ativá-lo novamente, selecione **permitir que os usuários automatizem suas tarefas no Excel na Web**e especifique quem pode acessar e usar o recurso:

    - Para permitir que todos os usuários em sua organização acessem e usem scripts do Office, deixe **todos** (o padrão) selecionado. 

    - Para permitir que apenas membros de um grupo específico acessem e usem scripts do Office, selecione **grupo específico**e, em seguida, insira o nome ou o alias de email do grupo para adicioná-lo à lista de permissões. Você pode adicionar apenas um grupo à lista de permissões e deve ser um dos seguintes tipos:
        - Grupo do Microsoft 365
        - Grupo de distribuição
        - Grupo de segurança
        - Grupo de segurança habilitado para email
    
        Para saber mais sobre os diferentes tipos de grupos, consulte [Compare groups](../create-groups/compare-groups.md).

5. Para permitir que usuários com acesso a scripts do Office compartilhem seus scripts com outras pessoas em sua organização, selecione **permitir que os usuários com acesso a scripts do Office compartilhem seus scripts com outras pessoas na organização**. Não é permitido compartilhar scripts fora de uma organização.
 
    > [!NOTE]
    > Se posteriormente você desativar o compartilhamento de script para sua organização, os usuários ainda poderão executar scripts compartilhados anteriormente.
 
6. Especifique quais usuários com acesso a scripts do Office podem compartilhar seus scripts:
    
    - Para permitir que todos os usuários tenham acesso a scripts do Office para compartilhar seus scripts, deixe **todos** (o padrão) selecionado.

    - Para permitir que somente os membros de um grupo específico com acesso a scripts do Office compartilhem seus scripts, selecione **grupo específico**e, em seguida, insira o nome ou o alias de email do grupo para adicioná-lo à lista de permissões. Você pode adicionar apenas um grupo à lista de permissões e deve ser um dos seguintes tipos:
        - Grupo do Microsoft 365
        - Grupo de distribuição
        - Grupo de segurança
        - Grupo de segurança habilitado para email
    
        Para saber mais sobre os diferentes tipos de grupos, consulte [Compare groups](../create-groups/compare-groups.md).

7. Selecione **Salvar**.

    Pode levar até 48 horas para que as alterações nas configurações de scripts do Office entrem em vigor.

## <a name="next-steps"></a>Próximas etapas

Como os scripts do Office funcionam com a automatização de energia, recomendamos que você analise suas políticas de DLP (prevenção de perda de dados) existentes para garantir que os dados da sua organização permaneçam protegidos enquanto os usuários usam scripts do Office. Para obter mais informações, consulte [políticas de prevenção de perda de dados (DLP)](/power-automate/prevent-data-loss).

## <a name="related-content"></a>Conteúdo relacionado

[Scripts do Office documentação técnica](/office/dev/scripts/) (página link) \
[Introdução aos scripts do Office no Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artigo) \
[Compartilhamento de scripts do Office no Excel para a Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artigo) \
[Gravar, editar e criar scripts do Office no Excel na Web](/office/dev/scripts/tutorials/excel-tutorial) (artigo)