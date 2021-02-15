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
description: Saiba como gerenciar as configurações de Scripts do Office para usuários em sua organização.
ms.openlocfilehash: 75d0a9d9e98652fc11eab7e8a7d6c826be031f6e
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058418"
---
# <a name="manage-office-scripts-settings"></a>Gerenciar configurações dos Scripts do Office

Os scripts do Office permitem que os usuários automatizem tarefas gravando, editando e executando scripts no Excel na Web. Os scripts do Office funcionam com o Power Automate, e os usuários executarão scripts em planilhas usando o conector do Excel Online (Negócios). Os administradores do Microsoft 365 podem gerenciar as configurações de Scripts do Office no Centro de administração do Microsoft 365.

## <a name="before-you-begin"></a>Antes de começar

- Para gerenciar as configurações de Scripts do Office, você deve ser um administrador global. Para obter mais informações, consulte [Sobre funções de administrador.](../add-users/about-admin-roles.md)

- Certifique-se de que os usuários em sua organização tenham uma licença válida para um plano comercial ou EDU do Microsoft 365 ou Office 365 que inclua acesso a aplicativos da área de trabalho do Office, como um dos seguintes planos:

    - Microsoft 365 Business Standard
    - Microsoft 365 Apps para Pequenos e Médios negócios
    - Microsoft 365 Apps para empresas
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Gerenciar a disponibilidade de scripts do Office e o compartilhamento de scripts

1. No Centro de administração do Microsoft 365, vá para a guia **Serviços** de Configurações da Organização \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">de Configurações.</a>

2. Selecione **Scripts do Office.**

3. Os Scripts do Office estão ligado por padrão, e todos em sua organização podem acessar e usar o recurso e compartilhar scripts. Para desativar os Scripts do Office para sua organização, des limpe a caixa de seleção Permitir que os usuários automatizem suas tarefas no **Excel na Web.**

4. Se você tiver desligado anteriormente os Scripts do Office para sua organização e quiser acioná-los novamente, selecione Permitir que os usuários automatizem suas tarefas no **Excel na Web** e especifique quem pode acessar e usar o recurso:

    - Para permitir que todos os usuários em sua organização acessem e usem scripts do Office, deixe **Todos** (o padrão) selecionado.

    - Para permitir que apenas membros de um grupo específico acessem e usem scripts do Office, selecione Grupo específico e insira o nome ou alias de email do grupo para adicioná-lo à lista de autorizações. Você pode adicionar apenas um grupo à lista de autorizações, e ele deve ser um dos seguintes tipos:
        - Grupo do Microsoft 365
        - Grupo de distribuição
        - Grupo de segurança
        - Grupo de segurança habilitado para email
    
        Para saber mais sobre os diferentes tipos de grupos, consulte [Comparar grupos.](../create-groups/compare-groups.md)

5. Para permitir que os usuários com acesso aos Scripts do Office compartilhem seus scripts com outras pessoas em sua organização, selecione Permitir que os usuários com acesso aos scripts do Office compartilhem seus scripts com outras pessoas na **organização.** O compartilhamento de scripts fora de uma organização não é permitido.
 
    > [!NOTE]
    > Se você posteriormente desativar o compartilhamento de scripts para sua organização, os usuários ainda poderão executar scripts compartilhados anteriormente.
 
6. Especifique quais usuários com acesso aos scripts do Office podem compartilhar seus scripts:
    
    - Para permitir que todos os usuários com acesso aos Scripts do Office compartilhem seus scripts, deixe **Todos** (o padrão) selecionado.

    - Para permitir que apenas membros de um grupo específico com acesso aos Scripts do Office compartilhem seus scripts, selecione Grupo específico e insira o nome ou alias de email do grupo para adicioná-lo à lista de autorizações. Você pode adicionar apenas um grupo à lista de autorizações, e ele deve ser um dos seguintes tipos:
        - Grupo do Microsoft 365
        - Grupo de distribuição
        - Grupo de segurança
        - Grupo de segurança habilitado para email
    
        Para saber mais sobre os diferentes tipos de grupos, consulte [Comparar grupos.](../create-groups/compare-groups.md)

7. Para permitir que os usuários executem seus scripts do Office dentro de fluxos do Power Automate, selecione Permitir que os usuários com acesso aos scripts do Office executem **seus scripts com o Power Automate.** Isso permite que os usuários adicionem etapas de fluxo com a opção de **script Executar** do Conector do Excel [Online (Business).](/connectors/excelonlinebusiness)

    - Para permitir que todos os usuários com acesso aos scripts do Office usem seus scripts em fluxos, deixe **Todos** (o padrão) selecionado.

    - Para permitir que apenas membros de um grupo específico com acesso aos scripts do Office usem seus scripts em fluxos, selecione Grupo específico e insira o nome ou alias de email do grupo para adicioná-lo à lista de autorizações. Você pode adicionar apenas um grupo à lista de autorizações, e ele deve ser um dos seguintes tipos:
        - Grupo do Microsoft 365
        - Grupo de distribuição
        - Grupo de segurança
        - Grupo de segurança habilitado para email

        Para saber mais sobre os diferentes tipos de grupos, consulte [Comparar grupos.](../create-groups/compare-groups.md)

    - Para saber mais sobre como usar scripts do Office com o Power Automate, incluindo como suas políticas de prevenção contra perda de dados podem ser impactadas, confira Executar scripts do Office com [o Power Automate.](/office/dev/scripts/develop/power-automate-integration)

8. Selecione **Salvar**.

    Pode levar até 48 horas para que as alterações nas configurações de Scripts do Office entre em vigor.

## <a name="next-steps"></a>Próximas etapas

Como os Scripts do Office funcionam com o Power Automate, recomendamos que você revise suas políticas de prevenção contra perda de dados (DLP) existentes para garantir que os dados da sua organização permaneçam protegidos enquanto os usuários usam scripts do Office. Para obter mais informações, consulte [Políticas de prevenção contra perda de dados (DLP).](/power-automate/prevent-data-loss)

## <a name="related-content"></a>Conteúdo relacionado

[Documentação técnica de Scripts do Office](/office/dev/scripts/) (página de link)\
[Introdução aos scripts do Office no Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artigo)\
[Compartilhando scripts do Office no Excel para a Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artigo)\
[Gravar, editar e criar scripts do Office no Excel na Web](/office/dev/scripts/tutorials/excel-tutorial) (artigo)
