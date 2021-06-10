---
title: Criar e gerenciar funções para controle de acesso baseado em função
description: Crie funções e defina as permissões atribuídas à função como parte da implementação do controle de acesso baseado em função no Central de Segurança do Microsoft Defender
keywords: funções de usuário, funções, rbac de acesso
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
ms.openlocfilehash: 932fd6ecd7dca66f4cb587b226474109c788c341
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053832"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a>Criar e gerenciar funções para controle de acesso baseado em função

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a>Criar funções e atribuir a função a um Azure Active Directory grupo

As etapas a seguir orientam você sobre como criar funções em Central de Segurança do Microsoft Defender. Ele supõe que você já tenha criado Azure Active Directory grupos de usuários.

1. Faça logoff [Central de Segurança do Microsoft Defender](https://securitycenter.windows.com/) conta usando uma função de administrador de segurança ou administrador global atribuída.

2. No painel de navegação, selecione Configurações > **Funções**.

3. Selecione **Adicionar item**.

4. Insira o nome da função, a descrição e as permissões que você gostaria de atribuir à função.

5. Selecione **Próximo** para atribuir a função a um grupo de Segurança do Azure AD.

6. Use o filtro para selecionar o grupo do Azure AD ao que você gostaria de adicionar a essa função.

7. **Salvar e fechar**.

8. Aplique as configurações.

> [!IMPORTANT]
> Depois de criar funções, você precisará criar um grupo de dispositivos e fornecer acesso ao grupo de dispositivos atribuindo-o a uma função que você acabou de criar.

### <a name="permission-options"></a>Opções de permissão

- **Exibir dados**
    - **Operações de segurança** - Exibir todos os dados de operações de segurança no portal
    - **Ameaça e Gerenciamento de Vulnerabilidades** - Exibir Gerenciamento de Ameaças e Vulnerabilidades dados no portal

- **Ações de correção ativas**
    - **Operações de segurança** - Realizar ações de resposta, aprovar ou descartar ações pendentes de correção, gerenciar listas permitidas/bloqueadas para automação e indicadores
    - **Ameaça e Gerenciamento de Vulnerabilidades - Tratamento de exceções** - Criar novas exceções e gerenciar exceções ativas
    - **Ameaças e Gerenciamento de Vulnerabilidades - Tratamento de** correção - Enviar novas solicitações de correção, criar tíquetes e gerenciar atividades de correção existentes

- **Investigação de alertas** - Gerenciar alertas, iniciar investigações automatizadas, executar verificações, coletar pacotes de investigação, gerenciar marcas de dispositivo e baixar somente arquivos executáveis portáteis (PE) 

- **Gerenciar configurações** do sistema de portal - Configurar configurações de armazenamento, siem e configurações da API intel de ameaças (aplica-se globalmente), configurações avançadas, carregamentos automatizados de arquivos, funções e grupos de dispositivos

    > [!NOTE]
    > Essa configuração só está disponível na função administrador do Microsoft Defender for Endpoint (padrão).

- **Gerenciar configurações de segurança** no Centro de Segurança - Configurar configurações de supressão de alerta, gerenciar exclusões de pastas para automação, dispositivos de integração e offboard e gerenciar notificações de email, gerenciar laboratório de avaliação

- **Recursos de resposta ao vivo**
    - **Comandos** básicos:
        - Iniciar uma sessão de resposta ao vivo
        - Executar comandos de resposta somente leitura ao vivo em dispositivo remoto (excluindo a cópia e a execução de arquivos
    - **Comandos** avançados:
        - Baixar um arquivo do dispositivo remoto por meio de resposta ao vivo
        - Baixar arquivos PE e não-PE da página de arquivo
        - Upload um arquivo para o dispositivo remoto
        - Exibir um script da biblioteca de arquivos
        - Executar um script no dispositivo remoto da biblioteca de arquivos

Para obter mais informações sobre os comandos disponíveis, consulte [Investigate devices using Live response](live-response.md).
  
## <a name="edit-roles"></a>Editar funções

1. Faça [logoff](https://securitycenter.windows.com/) Central de Segurança do Microsoft Defender conta usando a função administrador de segurança ou administrador global atribuída.

2. No painel de navegação, selecione Configurações > **Funções**.

3. Selecione a função que você gostaria de editar.

4. Clique em **Editar**.

5. Modifique os detalhes ou os grupos atribuídos à função. 

6. Clique **em Salvar e fechar**.

## <a name="delete-roles"></a>Excluir funções

1. Faça [logoff](https://securitycenter.windows.com/) Central de Segurança do Microsoft Defender conta usando a função administrador de segurança ou administrador global atribuída.

2. No painel de navegação, selecione Configurações > **Funções**.

3. Selecione a função que você gostaria de excluir.

4. Clique no botão drop-down e selecione **Excluir função**.

## <a name="related-topic"></a>Tópicos relacionados

- [Permissões básicas do usuário para acessar o portal](basic-permissions.md)
- [Criar e gerenciar grupos de dispositivos](machine-groups.md)
