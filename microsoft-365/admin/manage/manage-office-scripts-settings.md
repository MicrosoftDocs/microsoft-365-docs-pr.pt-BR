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
description: Saiba como gerenciar as configurações Office scripts para usuários em sua organização.
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572304"
---
# <a name="manage-office-scripts-settings"></a>Gerenciar configurações dos Scripts do Office

[Office scripts](/office/dev/scripts)permite que os usuários automatizem tarefas gravando, editando e executando scripts Excel na Web. Office Os scripts funcionam com Power Automate, e os usuários executarão scripts em guias de trabalho usando o conector Excel Online (Business). Microsoft 365 os administradores podem gerenciar Office scripts do centro de Microsoft 365 de administração.

## <a name="before-you-begin"></a>Antes de começar

- Para gerenciar Office scripts, você deve ser um administrador global. Para obter mais informações, consulte [Sobre funções de administrador](../add-users/about-admin-roles.md).

- Certifique-se de que os usuários em sua organização tenham uma licença válida para um plano comercial Microsoft 365 ou Office 365 EDU que inclua o acesso Office aplicativos de área de trabalho, como um dos seguintes planos:

    - Microsoft 365 Business Standard
    - Aplicativos do Microsoft 365 para empresas
    - Microsoft 365 Apps para empresas
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Gerenciar a disponibilidade de Office Scripts e o compartilhamento de scripts

1. No centro Microsoft 365 de administração, vá para a **guia** Serviços de configurações Configurações \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Org.</a>

2. Selecione **Office Scripts**.

3. Office Os scripts são ativas por padrão, e todos em sua organização podem acessar e usar o recurso e compartilhar scripts. Para desativar Office scripts para sua organização, desempure a caixa de seleção Permitir que os usuários **automatizem** suas tarefas Excel na Web caixa de seleção.

4. Se você tiver desligado anteriormente Office scripts para sua organização e quiser acioná-los novamente, selecione Permitir que os usuários automatizem suas tarefas no **Excel na Web** e especifique quem pode acessar e usar o recurso:

    - Para permitir que todos os usuários em sua organização acessem e usem Office Scripts, deixe **Todos** (o padrão) selecionados.

    - Para permitir que apenas membros de um grupo específico acessem e usem scripts Office, selecione **Grupo** específico e insira o nome ou o alias de email do grupo para adicioná-lo à lista de permitir. Você pode adicionar apenas um grupo à lista de permitir e deve ser um dos seguintes tipos:
        - Microsoft 365 grupo
        - Grupo de distribuição
        - Grupo de segurança
        - Grupo de segurança habilitado para email
    
        Para saber mais sobre os diferentes tipos de grupos, consulte [Comparar grupos](../create-groups/compare-groups.md).

5. Para permitir que os usuários com acesso Office scripts compartilhem seus scripts com outras pessoas em sua organização, selecione Permitir que os usuários com acesso Office scripts compartilhem seus **scripts** com outras pessoas na organização. Não é permitido compartilhar scripts fora de uma organização.
 
    > [!NOTE]
    > Se você mais tarde desativar o compartilhamento de scripts para sua organização, os usuários ainda poderão executar scripts compartilhados anteriormente.
 
6. Especifique quais usuários com acesso Office scripts podem compartilhar seus scripts:
    
    - Para permitir que todos os usuários com acesso Office scripts compartilhem seus scripts, deixe **Todos** (o padrão) selecionados.

    - Para permitir que apenas membros de um grupo específico com acesso Office Scripts compartilhem seus scripts, selecione Grupo específico **e** insira o nome ou alias de email do grupo para adicioná-lo à lista de permitir. Você pode adicionar apenas um grupo à lista de permitir e deve ser um dos seguintes tipos:
        - Microsoft 365 grupo
        - Grupo de distribuição
        - Grupo de segurança
        - Grupo de segurança habilitado para email
    
        Para saber mais sobre os diferentes tipos de grupos, consulte [Comparar grupos](../create-groups/compare-groups.md).

7. Para permitir que os usuários executem seus scripts Office dentro de fluxos de Power Automate, selecione Permitir que os usuários com acesso Office Scripts executem seus **scripts** com Power Automate . Isso permite que os usuários adicionem etapas de fluxo com a opção executar do [conector Excel Online (Negócios).](/connectors/excelonlinebusiness) 

    - Para permitir que todos os usuários com acesso Office scripts usem seus scripts em fluxos, deixe **Todos** (o padrão) selecionados.

    - Para permitir que apenas membros de um grupo específico com acesso a scripts Office usem seus scripts em fluxos, selecione **Grupo** específico e insira o nome ou alias de email do grupo para adicioná-lo à lista de permitir. Você pode adicionar apenas um grupo à lista de permitir e deve ser um dos seguintes tipos:
        - Microsoft 365 grupo
        - Grupo de distribuição
        - Grupo de segurança
        - Grupo de segurança habilitado para email

        Para saber mais sobre os diferentes tipos de grupos, consulte [Comparar grupos](../create-groups/compare-groups.md).

    - Para saber mais sobre como usar Office scripts com Power Automate, consulte [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).

8. Selecione **Salvar**.

    Pode levar até 48 horas para que as alterações nas configurações Office Scripts entre em vigor.

## <a name="next-steps"></a>Próximas etapas

Como Office Scripts funciona com Power Automate, recomendamos que você revise suas políticas de prevenção contra perda de dados (DLP) existentes para garantir que os dados da sua organização permaneçam protegidos enquanto os usuários usam Office Scripts. Para obter mais informações, consulte Políticas de prevenção contra perda de [dados (DLP).](/power-automate/prevent-data-loss)

## <a name="related-content"></a>Conteúdo relacionado

[Office documentação técnica de Scripts](/office/dev/scripts/) (página de link)\
[Introdução Office scripts no Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artigo)\
[Compartilhamento Office scripts em Excel para a Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artigo)\
[Gravar, editar e criar Office scripts no Excel na Web](/office/dev/scripts/tutorials/excel-tutorial) (artigo)
