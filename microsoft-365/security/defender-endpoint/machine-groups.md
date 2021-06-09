---
title: Criar e gerenciar grupos de dispositivos no Microsoft Defender para Ponto de Extremidade
description: Criar grupos de dispositivos e definir níveis automatizados de correção neles confirmando as regras que se aplicam ao grupo
keywords: grupos de dispositivos, grupos, correção, nível, regras, aad group, role, assign, rank
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d4f62acde4e7d790c7a7c8635f51c99f0823687d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842765"
---
# <a name="create-and-manage-device-groups"></a>Criar e gerenciar grupos de dispositivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- Azure Active Directory
- Office 365

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Em um cenário empresarial, as equipes de operação de segurança normalmente são atribuídas a um conjunto de dispositivos. Esses dispositivos são agrupados com base em um conjunto de atributos, como seus domínios, nomes de computador ou marcas designadas.

No Microsoft Defender para Ponto de Extremidade, você pode criar grupos de dispositivos e usá-los para:
- Limitar o acesso a alertas e dados relacionados a grupos de usuários específicos do Azure AD com [funções RBAC atribuídas](rbac.md) 
- Configurar configurações de correção automática diferentes para diferentes conjuntos de dispositivos
- Atribuir níveis de correção específicos a aplicar durante investigações automatizadas
- Em uma investigação, filtre a lista **Dispositivos** para grupos de dispositivos específicos usando o **filtro Group.**

Você pode criar grupos de dispositivos no contexto do RBAC (acesso baseado em função) para controlar quem pode tomar ações específicas ou ver informações atribuindo os grupos de dispositivos a um grupo de usuários. Para obter mais informações, consulte [Manage portal access using role-based access control](rbac.md).

>[!TIP]
> Para uma análise abrangente do aplicativo RBAC, leia: Seu SOC está sendo [executado com RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015).

Como parte do processo de criação de um grupo de dispositivos, você:
- De definir o nível de correção automatizado para esse grupo. Para obter mais informações sobre níveis de correção, consulte [Use Automated investigation to investigate and remediate threats](automated-investigations.md).
- Especifique a regra correspondente que determina qual grupo de dispositivos pertence ao grupo com base no nome do dispositivo, domínio, marcas e plataforma do sistema operacional. Se um dispositivo também for corresponder a outros grupos, ele será adicionado apenas ao grupo de dispositivos mais alto classificado.
- Selecione o grupo de usuários do Azure AD que deve ter acesso ao grupo de dispositivos.
- Rank the device group relative to other groups after it's created.

>[!NOTE]
>Um grupo de dispositivos será acessível a todos os usuários se você não atribuir nenhum grupo do Azure AD a ele.

## <a name="create-a-device-group"></a>Criar um grupo de dispositivos

1. No painel de navegação, **selecione** Configurações  >  **Grupos de dispositivos**.

2. Clique **em Adicionar grupo de dispositivos**.

3. Insira o nome do grupo e as configurações de automação e especifique a regra correspondente que determina quais dispositivos pertencem ao grupo. Veja [Como a investigação automatizada é iniciada.](automated-investigations.md#how-the-automated-investigation-starts)

    >[!TIP]
    >Se você quiser agrupar dispositivos por unidade organizacional, você pode configurar a chave do Registro para a afiliação de grupo. Para obter mais informações sobre a marcação de dispositivo, consulte [Create and manage device tags](machine-tags.md).

4. Visualize vários dispositivos que serão compatíveis com essa regra. Se você estiver satisfeito com a regra, clique na **guia Acesso do** usuário.

5. Atribua os grupos de usuários que podem acessar o grupo de dispositivos que você criou.

    >[!NOTE]
    >Você só pode conceder acesso a grupos de usuários do Azure AD atribuídos a funções RBAC.

6. Clique em **Fechar**. As alterações de configuração são aplicadas.

## <a name="manage-device-groups"></a>Gerenciar grupos de dispositivos

Você pode promover ou rebaixar a classificação de um grupo de dispositivos para que ele seja priorizado mais ou menos durante a correspondência. Quando um dispositivo é corresponder a mais de um grupo, ele é adicionado apenas ao grupo de classificação mais alto. Você também pode editar e excluir grupos.



>[!WARNING]
>Excluir um grupo de dispositivos pode afetar as regras de notificação de email. Se um grupo de dispositivos estiver configurado sob uma regra de notificação de email, ele será removido dessa regra. Se o grupo de dispositivos for o único grupo configurado para uma notificação de email, essa regra de notificação de email será excluída juntamente com o grupo de dispositivos.

Por padrão, os grupos de dispositivos são acessíveis a todos os usuários com acesso ao portal. Você pode alterar o comportamento padrão atribuindo grupos de usuários do Azure AD ao grupo de dispositivos.

Dispositivos que não são compatíveis com nenhum grupo são adicionados ao grupo Dispositivos Desagrupados (padrão). Não é possível alterar a classificação desse grupo ou excluí-lo. No entanto, você pode alterar o nível de correção desse grupo e definir os grupos de usuários do Azure AD que podem acessar esse grupo.

>[!NOTE]
> A aplicação de alterações na configuração do grupo de dispositivos pode levar até vários minutos.


### <a name="add-device-group-definitions"></a>Adicionar definições de grupo de dispositivos
As definições de grupo de dispositivos também podem incluir vários valores para cada condição. Você pode definir várias marcas, nomes de dispositivo e domínios para a definição de um único grupo de dispositivos.

1. Crie um novo grupo de dispositivos e selecione **Guia Dispositivos.**
2. Adicione o primeiro valor para uma das condições.
3. Selecione `+` para adicionar mais linhas do mesmo tipo de propriedade.

>[!TIP]
> Use o operador 'OR' entre linhas do mesmo tipo de condição, o que permite vários valores por propriedade.
> Você pode adicionar até 10 linhas (valores) para cada tipo de propriedade - marca, nome do dispositivo, domínio.

Para obter mais informações sobre como vincular a definições de grupos de dispositivos, consulte [Device groups - Microsoft 365 security](https://sip.security.microsoft.com/homepage).

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar o acesso ao portal usando o controle de acesso baseado em função](rbac.md)
- [Criar e gerenciar marcas de dispositivo](machine-tags.md)
- [Obter lista de grupos de dispositivos de locatários usando Graph API](/graph/api/device-list-memberof)
