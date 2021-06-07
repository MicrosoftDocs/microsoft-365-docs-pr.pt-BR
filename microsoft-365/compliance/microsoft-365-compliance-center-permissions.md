---
title: Permissões no Microsoft 365 de conformidade
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Saiba mais sobre como gerenciar permissões no Microsoft 365 de conformidade.
ms.collection: M365-security-compliance
ms.openlocfilehash: 72575fce5f7d43354715c77016a8f444e539887f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772411"
---
# <a name="permissions-in-the-microsoft-365-compliance-center"></a>Permissões no Microsoft 365 de conformidade

O Microsoft 365 de conformidade foi atualizado recentemente e agora oferece suporte ao gerenciamento direto de permissões para usuários que executam tarefas de conformidade Microsoft 365. Essa atualização significa que você não precisa mais usar o Centro de Conformidade Office 365 Segurança & para gerenciar permissões para soluções de conformidade. Usando a nova página **Permissões** no centro de conformidade do Microsoft 365, você pode gerenciar permissões para os usuários para tarefas de conformidade em recursos como gerenciamento de dispositivos, prevenção contra perda de dados, Descoberta Eletrônico, gerenciamento de risco interno, retenção e muitos outros. Os usuários podem executar apenas as tarefas de conformidade às que você explicitamente concede acesso a eles.

Para exibir a guia Permissões no centro de conformidade do Microsoft 365, os usuários precisam  ser um administrador global ou precisam  ser **atribuídos** à função de Gerenciamento de Função (uma função é atribuída apenas ao grupo de função Gerenciamento da Organização). A *função Gerenciamento de* Função permite que os usuários exibirem, criem e modifiquem grupos de funções.

![Página Permissões no Microsoft 365 de conformidade](../media/m365-compliance-center-permissions.png)

As permissões no Microsoft 365 de conformidade se baseiam no modelo de permissões de controle de acesso baseado em função (RBAC). O RBAC é o mesmo modelo de permissões usado pela maioria dos serviços Microsoft 365, portanto, se você estiver familiarizado com a estrutura de permissão nesses serviços, conceder permissões no centro de conformidade Microsoft 365 será familiar. É importante lembrar que as permissões gerenciadas no centro de conformidade Microsoft 365 não abrangem o gerenciamento de todas as permissões necessárias em cada serviço individual. Você ainda precisará gerenciar determinadas permissões específicas do serviço no centro de administração para o serviço específico. Por exemplo, se você precisar atribuir permissões para políticas de arquivamento, auditoria e retenção, você precisará gerenciar essas permissões no centro de administração Exchange.

## <a name="relationship-of-members-roles-and-role-groups"></a>Relação de membros, funções e grupos de função

Uma função concede permissões para realizar um conjunto de tarefas; por exemplo, a função Gerenciamento de Caso permite que os usuários trabalhem com casos de Descoberta e.

Um grupo de funções é um conjunto de funções que permitem que os usuários façam seus trabalhos em soluções de conformidade Microsoft 365 centro de conformidade. Por exemplo, adicionando usuários ao grupo de função Gerenciamento de Riscos do *Insider,* administradores, analistas, investigadores e auditores designados são configurados para as permissões necessárias de gerenciamento de risco interno em um único grupo. O Microsoft 365 de conformidade inclui grupos de funções padrão para tarefas e funções para cada solução de conformidade à que você precisará atribuir pessoas. Geralmente, recomendamos simplesmente adicionar usuários individuais como membros aos grupos de função de conformidade padrão, conforme necessário.

![Diagrama que mostra a relação de grupos de funções para membros e funções](../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-microsoft-365-compliance-center"></a>Permissões necessárias para usar recursos no Microsoft 365 de conformidade

Para exibir todos os grupos de função padrão que estão disponíveis no centro de conformidade Microsoft 365 e as funções [atribuídas aos](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)grupos de funções por padrão, consulte As Permissões no Centro de Conformidade & Segurança.

Gerenciar permissões no centro de conformidade Microsoft 365 fornece aos usuários acesso aos recursos de conformidade disponíveis no centro de conformidade Microsoft 365 de conformidade. Se você quiser conceder permissões a outros recursos que não estão no centro de conformidade do Microsoft 365, como regras de fluxo de emails do Exchange (também conhecidas como regras de transporte), você precisará usar o centro de administração do Exchange.

## <a name="azure-roles-in-the-microsoft-365-compliance-center"></a>Funções do Azure no Microsoft 365 de conformidade

As funções que aparecem na seção Funções do **Azure AD** da página Permissões do centro de conformidade Microsoft 365 são Azure Active Directory  >   funções.  Essas funções foram projetadas para se alinharem com funções de trabalho no grupo de TI da sua organização, tornando mais fácil dar a uma pessoa todas as permissões necessárias para realizar o trabalho. Você pode exibir os usuários atualmente atribuídos a cada função selecionando uma função de Administrador e exibindo os detalhes do painel de funções. Para gerenciar membros de uma função do Azure AD, selecione Gerenciar membros no Azure AD. Essa opção redireciona você para o portal de gerenciamento do Azure.

|Função|Descrição|
|:---|:----------|
|**Administrador global**|Acesso a todos os recursos administrativos em todos os serviços do Microsoft 365. Somente os administradores globais podem atribuir outras funções de administrador. Para saber mais, confira [administrador global/administrador da empresa](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).|
|**Administrador de dados de conformidade**|Acompanhe os dados da sua organização no Microsoft 365, certifique-se de que estejam protegidos e obtenha insights sobre quaisquer problemas para ajudar a atenuar os riscos. Para obter mais informações, confira o [Administrador de Dados de Conformidade](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).|
|**Administrador de conformidade**|Ajude sua organização a se manter em conformidade com quaisquer requisitos regulatórios, gerenciar casos de descoberta eletrônica e manter políticas de governança de dados em locais, identidades e aplicativos do Microsoft 365. Para saber mais, confira o [Administrador de Conformidade](/azure/active-directory/roles/permissions-reference#compliance-administrator).|
|**Operador de segurança**|Exibir, investigar e responder a ameaças ativas a seus usuários, dispositivos e conteúdo da Microsoft 365. Para obter mais informações, confira [Operador de Segurança](/azure/active-directory/roles/permissions-reference#security-operator).|
|**Leitor de segurança**|Exibir e investigar ameaças ativas a seus usuários, dispositivos e conteúdo da Microsoft 365, mas (diferentemente do Operador de segurança) não têm permissões para responder executando uma ação. Para obter mais informações, confira o [Leitor de Segurança](/azure/active-directory/roles/permissions-reference#security-reader).|
|**Administrador de segurança**|Controle a segurança global da sua organização, gerenciando políticas de segurança, analisando análises e relatórios de segurança em produtos da Microsoft 365 e ficando sempre atualizado sobre o panorama das ameaças. Para obter mais informações, confira a[Segurança do Administrador](/azure/active-directory/roles/permissions-reference#security-administrator).|
|**Leitor global**|A versão somente leitura do **Administrador Global**. Exibir todas as configurações e informações administrativas no Microsoft 365. Para saber mais, confira [Leitor Global](/azure/active-directory/roles/permissions-reference#global-reader)..|
|**Administrador de simulação de ataque**|Crie e gerencie todos os aspectos da criação de simulação de ataque, início/agendamento de uma simulação e a revisão dos resultados da simulação. Para obter mais informações, consulte [Administrador de Simulação de Ataque](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator).|
|**Autor da carga de ataque**|Crie cargas de ataque, mas não as iniciará ou agende. Para obter mais informações, consulte [Attack Payload Author](/azure/active-directory/roles/permissions-reference#attack-payload-author).|
|

## <a name="add-users-to-a-compliance-role-group"></a>Adicionar usuários a um grupo de função de conformidade

Conclua as etapas a seguir para adicionar usuários a um grupo de função de conformidade:

1. Entre na área de permissões do centro de conformidade [Microsoft 365 usando](https://compliance.microsoft.com/permissions) credenciais para uma conta de administrador em sua Microsoft 365 organização.
2. No centro Microsoft 365 de conformidade, vá para **Permissões**. Selecione o link para exibir e gerenciar funções de conformidade Microsoft 365.
3. Expanda **a seção Centro de Conformidade** e selecione **Funções**.
4. Na página **Funções do Centro** de Conformidade, selecione um grupo de função de conformidade ao que você deseja adicionar usuários e selecione **Editar** grupo de funções no painel de detalhes.
5. Selecione **Escolher membros** no painel de navegação esquerdo e selecione **Editar**.
6. Selecione **Adicionar** e selecione a caixa de seleção para todos os usuários que você deseja adicionar ao grupo de funções.
7. Selecione **Adicionar** e, em seguida, **a**.
8. Selecione **Salvar** para adicionar os usuários ao grupo de funções. Selecione **Fechar** para concluir as etapas.

## <a name="remove-users-from-a-compliance-role-group"></a>Remover usuários de um grupo de função de conformidade

Conclua as etapas a seguir para remover usuários de um grupo de função de conformidade:

1. Entre na área de permissões do centro de conformidade [Microsoft 365 usando](https://compliance.microsoft.com/permissions) credenciais para uma conta de administrador em sua Microsoft 365 organização.
2. No centro Microsoft 365 de conformidade, vá para **Permissões**. Selecione o link para exibir e gerenciar funções de conformidade Microsoft 365.
3. Expanda a seção Centro de Conformidade e selecione **Funções**.
4. Na página **Funções do Centro** de Conformidade, selecione um grupo de função de conformidade de onde você deseja remover os usuários e selecione **Editar** grupo de funções no painel de detalhes.
5. Selecione **Escolher membros** no painel de navegação esquerdo e selecione **Editar**.
6. Selecione **Remover** e selecione a caixa de seleção para todos os usuários que você deseja remover do grupo de funções.
7. Selecione **Remover**, em seguida, selecione **Feito**.
8. Selecione **Salvar** para remover os usuários do grupo de funções. Selecione **Fechar** para concluir as etapas.
