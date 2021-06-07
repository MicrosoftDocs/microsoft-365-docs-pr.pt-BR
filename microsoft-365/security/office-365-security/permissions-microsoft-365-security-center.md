---
title: Permissões no Centro de segurança do Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
ms.audience: Admin
ms.topic: article
audience: Admin
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Os administradores podem aprender a gerenciar permissões no Centro de segurança do Microsoft 365 para todas as tarefas relacionadas à segurança.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9c2d28510c25290921084e6a238fa8c781c35624
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772420"
---
# <a name="permissions-in-the-microsoft-365-security-center"></a>Permissões no Centro de segurança do Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Sua organização precisa gerenciar cenários de segurança que abrangem todos os serviços do Microsoft 365. E você precisa ter flexibilidade para dar permissões de administrador para as pessoas certas na sua organização.

O Centro de segurança do Microsoft 365 na <https://security.microsoft.com> dá suporte ao gerenciamento direto das permissões para os usuários que executam tarefas de segurança no Microsoft 365. Ao usar o centro de segurança para gerenciar permissões, você pode gerenciar permissões centralmente para todas as tarefas relacionadas à segurança.

Para gerenciar permissões no Centro de segurança, acesse **Permissões e funções** ou <https://security.microsoft.com/securitypermissions>. Você precisa ser um **administrador global** ou membro do grupo de função **Gerenciamento da organização** no Centro de segurança. Especificamente, a função **Gerenciamento da função** permite que os usuários exibam, criem e modifiquem grupos de funções no Centro de segurança e, por padrão, essa função é atribuída somente ao grupo de função do **Gerenciamento da organização**.

## <a name="relationship-of-members-roles-and-role-groups"></a>Relação de membros, funções e grupos de função

As permissões no Centro de segurança se baseiam no modelo de permissões de controle de acesso baseado na função (RBAC). O RBAC é o mesmo modelo de permissões usado pela maioria dos serviços do Microsoft 365 e, portanto, se você estiver familiarizado com a estrutura de permissões desses serviços, será muito familiar conceder permissões no Centro de segurança.

Uma **função** concede as permissões para realizar um conjunto de tarefas.

Um **grupo de função** é um conjunto de funções que permite que as pessoas realizem seus trabalhos no Centro de segurança. Por exemplo, o grupo de função Administradores de Simuladores de Ataque inclui a função Administrador de Simulação de Ataque para criar e gerenciar todos os aspectos do treinamento de ataque.

O Centro de segurança inclui grupos de função padrão para as tarefas e funções mais comuns que precisam ser atribuídas às pessoas. Normalmente, recomendamos que você apenas adicione usuários individuais **membros** a grupos de função padrão.

![Diagrama que mostra a relação de grupos de função para membros e funções](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="roles-and-role-groups-in-the-security-center"></a>Funções e grupos de função no Centro de segurança

Os seguintes tipos de funções e grupos de função estão disponíveis em **Permissões e funções** no Centro de segurança:

- **Funções do Azure AD**: você pode visualizar as funções e os usuários atribuídos, mas não pode gerenciá-los diretamente no Centro de segurança. As funções do Azure AD são funções centrais que atribuem permissões para **todos** os serviços do Microsoft 365.

- **Funções de e-mail e de colaboração**: são os mesmos grupos de função que estão disponíveis no Centro de Segurança e Conformidade, mas você pode gerenciá-los diretamente no Centro de segurança. As permissões que você atribuir aqui são específicas para o Centro de segurança do Microsoft 365, o Centro de conformidade do Microsoft 365 e o Centro de Segurança e Conformidade, e não abrangem todas as permissões necessárias em outras cargas de trabalho do Microsoft 365.

![Página Permissões e funções no Centro de segurança do Microsoft 365](../../media/m365-sc-permissions-and-roles-page.png)

### <a name="azure-ad-roles-in-the-security-center"></a>Funções do Azure AD no Centro de segurança

Ao acessar **Funções de e-mail e de colaboração** \> **Permissões e funções** \> **Funções do Azure AD** \> **Funções** (ou diretamente em <https://security.microsoft.com/aadpermissions>), você visualizará as funções do Azure AD descritas nesta seção.

Quando você seleciona uma função, é exibido um informativo detalhado que contém a descrição da função e as atribuições do usuário. Mas, para gerenciar essas atribuições, você precisa clicar em **Gerenciar membros no Azure AD** no informativo de detalhes.

![Link para gerenciar permissões no Azure Active Directory](../../media/permissions-manage-in-azure-ad-link.png)

Para obter mais informações, consulte [Exibir e atribuir funções de administrador no Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

<br>

****

|Função|Descrição|
|---|---|
|**Administrador global**|Acesso a todos os recursos administrativos em todos os serviços do Microsoft 365. Somente os administradores globais podem atribuir outras funções de administrador. Para saber mais, confira [administrador global/administrador da empresa](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).|
|**Administrador de dados de conformidade**|Acompanhe os dados da sua organização no Microsoft 365, certifique-se de que estejam protegidos e obtenha insights sobre quaisquer problemas para ajudar a atenuar os riscos. Para obter mais informações, confira o [Administrador de Dados de Conformidade](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).|
|**Administrador de conformidade**|Ajude sua organização a se manter em conformidade com quaisquer requisitos regulatórios, gerenciar casos de descoberta eletrônica e manter políticas de governança de dados em locais, identidades e aplicativos do Microsoft 365. Para saber mais, confira o [Administrador de Conformidade](/azure/active-directory/roles/permissions-reference#compliance-administrator).|
|**Operador de segurança**|Exibir, investigar e responder a ameaças ativas a seus usuários, dispositivos e conteúdo da Microsoft 365. Para obter mais informações, confira [Operador de Segurança](/azure/active-directory/roles/permissions-reference#security-operator).|
|**Leitor de segurança**|Exibir e investigar ameaças ativas a seus usuários, dispositivos e conteúdo da Microsoft 365, mas (diferentemente do Operador de segurança) não têm permissões para responder executando uma ação. Para obter mais informações, confira o [Leitor de Segurança](/azure/active-directory/roles/permissions-reference#security-reader).|
|**Administrador de segurança**|Controle a segurança global da sua organização, gerenciando políticas de segurança, analisando análises e relatórios de segurança em produtos da Microsoft 365 e ficando sempre atualizado sobre o panorama das ameaças. Para obter mais informações, confira a[Segurança do Administrador](/azure/active-directory/roles/permissions-reference#security-administrator).|
|**Leitor global**|A versão somente leitura do **Administrador Global**. Exibir todas as configurações e informações administrativas no Microsoft 365. Para saber mais, confira [Leitor Global](/azure/active-directory/roles/permissions-reference#global-reader)..|
|**Administrador de ataque**|Crie e gerencie todos os aspectos de criação de [simulação de ataque](attack-simulation-training.md), lançamento/agendamento de uma simulação, e a revisão dos resultados da simulação. Para obter mais informações, consulte [Administrador de simulação de ataques](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator).|
|**Autor do conteúdo de ataque**|Crie cargas úteis de ataque mas não as inicie ou agende. Para obter mais informações, consulte [Autor do conteúdo de ataque](/azure/active-directory/roles/permissions-reference#attack-payload-author).|
|

### <a name="email--collaboration-roles-in-the-security-center"></a>Funções de e-mail e de colaboração no Centro de segurança

Ao acessar **Funções de e-mail e de colaboração** \> **Permissões e funções** \> **Funções de e-mail e de colaboração** \> **Funções** (ou diretamente em <https://security.microsoft.com/emailandcollabpermissions>), você visualizará os mesmos grupos de funções disponíveis no Centro de Segurança e de Conformidade.

Para obter mais informações sobre esses grupos de função, consulte [Permissões no Centro de Segurança e Conformidade](permissions-in-the-security-and-compliance-center.md).

#### <a name="modify-email--collaboration-role-membership-in-the-security-center"></a>Modificar o e-mail e a função de colaboração no Centro de segurança

1. No Centro de segurança, acesse **Funções de e-mail e de colaboração** \> **Permissões e funções** \> **Funções de e-mail e de colaboração** \> **Funções**.

2. Na página **Permissões** aberta, selecione o grupo de função que você quer modificar na lista. Você pode clicar no título da coluna **Nome** para classificar a lista por nome ou clicar em **Pesquisar** ![Ícone de Pesquisar](../../media/m365-cc-sc-search-icon.png) para encontrar o grupo de função.

3. No informativo de detalhes do grupo de função exibido, clique em **Editar** na seção **Membros**.

4. Na página **Editar a escolha dos membros** exibida, faça o seguinte:
   - Se não houver nenhum membro do grupo de função, clique em **Escolher membros**.
   - Se houver membros existentes do grupo de função, clique em **Editar**

5. Na página do informativo **Escolher membros** exibida, faça o seguinte:

   - Clique em **Adicionar**. Na lista de usuários exibida, selecione um ou mais usuários. Ou você pode clicar em **Pesquisar** ![Ícone Pesquisar](../../media/m365-cc-sc-search-icon.png) para encontrar e selecionar usuários.

     Depois de selecionar os usuários que você quer adicionar, clique em **Adicionar**.

   - Clique em **Remover**. Selecione uma ou mais das seguintes opções. Ou você pode clicar em **Pesquisar** ![Ícone Pesquisar](../../media/m365-cc-sc-search-icon.png) para encontrar e selecionar membros.

     Depois de selecionar os usuários que você quer remover, clique em **Adicionar**.

6. Retorne ao informativo **Escolher membros**, clique em **Feito**.

7. Retorne para **Editar a escolha dos membros**, clique em **Salvar**.

8. Retorne ao informativo de detalhes do grupo de função, clique em **Concluído**.
