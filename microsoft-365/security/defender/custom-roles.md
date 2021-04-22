---
title: Funções personalizadas para o controle de acesso baseado em função
description: Saiba como gerenciar funções personalizadas no Centro de segurança do Microsoft 365
keywords: access, permissions, Microsoft 365 Defender, M365, security, MCAS, Cloud App Security, Microsoft Defender for Endpoint, scope, scoping, RBAC, roles-based access, custom roles-based access, roles-based auth, RBAC in MDO, roles, rolegroups, permissions inheritance, fine-grained permissions
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 9dfa9f113c0a7d57360c2da6105cbfa07fcf6a99
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935684"
---
# <a name="custom-roles-in-role-based-access-control-for-microsoft-365-defender"></a>Funções personalizadas no controle de acesso baseado em função para o Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Aplica-se a:**

- Microsoft 365 Defender
 
Há dois tipos de funções que podem ser usadas para acessar o Microsoft 365 Defender:
- **Funções do Azure Active Directory Global (AD)**
- **Funções personalizadas**

O acesso ao Microsoft 365 Defender pode ser gerenciado coletivamente usando funções [globais no Azure Active Directory (AAD)](m365d-permissions.md)

Se você precisar de maior flexibilidade e controle sobre o acesso a dados específicos do produto, o acesso ao Microsoft 365 Defender também poderá ser gerenciado com a criação de funções personalizadas por meio de cada portal de segurança respectivo.  

Por exemplo, uma função Personalizada criada por meio do Microsoft Defender para Ponto de Extremidade permitiria o acesso aos dados relevantes do produto, incluindo dados do ponto de extremidade no centro de segurança do Microsoft 365. Da mesma forma, uma função Personalizada criada por meio do Microsoft Defender para Office 365 permitiria o acesso aos dados relevantes do produto, incluindo dados de colaboração de email & no centro de segurança do Microsoft 365.

Os usuários com funções Personalizadas existentes podem acessar dados no centro de segurança do Microsoft 365 de acordo com suas permissões de carga de trabalho existentes sem nenhuma configuração adicional necessária.

## <a name="create-and-manage-custom-roles"></a>Criar e gerenciar funções personalizadas
Funções e permissões personalizadas podem ser criadas e gerenciadas individualmente por meio de cada um dos seguintes portais de segurança: 

- Microsoft Defender para Ponto de Extremidade – [Editar funções no Microsoft Defender para Ponto de Extremidade](../defender-endpoint/user-roles.md)
- Microsoft Defender para Office 365 – [Permissões no Centro](../office-365-security/permissions-in-the-security-and-compliance-center.md?preserve-view=true&view=o365-worldwide) de Conformidade & Segurança
- Microsoft Cloud App Security – [Gerenciar acesso de administrador](/cloud-app-security/manage-admins)

Cada função personalizada criada por meio de um portal individual permite o acesso aos dados do portal de produto relevante. Por exemplo, uma função personalizada criada por meio do Microsoft Defender para Ponto de Extremidade permitirá apenas o acesso ao Defender para dados do Ponto de Extremidade.

> [!TIP]
> Permissões e funções também podem ser acessadas por meio do centro de segurança do Microsoft 365 selecionando Permissões & funções no painel de navegação. O acesso ao Microsoft Cloud App Security (MCAS) é gerenciado por meio do portal do MCAS e também controla o acesso ao Microsoft Defender para Identidade.  Consulte [Microsoft Cloud App Security](/cloud-app-security/manage-admins)

> [!NOTE]
> As funções personalizadas criadas no Microsoft Cloud App Security também têm acesso aos dados do Microsoft Defender para Identidade. Os usuários com administrador de grupo de usuários ou funções de Segurança de Aplicativos do Microsoft Cloud App não podem acessar dados do Microsoft Cloud App Security por meio do Centro de segurança do Microsoft 365.

## <a name="manage-permissions-and-roles-in-the-microsoft-365-security-center"></a>Gerenciar permissões e funções no centro de segurança do Microsoft 365
Permissões e funções também podem ser gerenciadas no centro de segurança do Microsoft 365:

1. Entre no centro de segurança do Microsoft 365 security.microsoft.com.
2. No painel de navegação, selecione **Permissões & funções**.
3. No **header Permissões,** selecione **Funções**.

> [!NOTE]
> Isso só se aplica ao Defender para Office 365 e Defender para Ponto de Extremidade. O acesso a outras cargas de trabalho deve ser feito em seus portais relevantes.


## <a name="required-roles-and-permissions"></a>Funções e permissões necessárias
A tabela a seguir descreve as funções e permissões necessárias para acessar cada experiência unificada em cada carga de trabalho. As funções definidas na tabela abaixo referem-se a funções personalizadas em portais individuais e não estão conectadas a funções globais no Azure AD, mesmo que nomeados da mesma forma.

> [!NOTE]
> O gerenciamento de incidentes requer permissões de gerenciamento para todos os produtos que fazem parte do incidente.
 
| **Uma das seguintes funções são necessárias para o Microsoft 365 Defender**  | **Uma das seguintes funções são necessárias para o Defender para o Ponto de Extremidade**  | **Uma das seguintes funções são necessárias para o Defender para Office 365** | **Uma das seguintes funções são necessárias para o Cloud App Security** | 
|---------|---------|---------|---------|
| Exibindo dados de investigação: <ul><li>Página alerta</li> <li>Fila de alertas</li> <li>Incidentes</li>  <li>Fila de incidentes</li> <li>Central de ações</li></ul>| Exibir operações de segurança de dados | <ul><li>Somente exibição Gerenciar alertas </li> <li>Configuração da organização</li><li>Logs de auditoria</li> <li>Logs de auditoria somente exibição</li> <li>Leitor de segurança</li> <li>Administrador de segurança</li><li>Destinatários somente exibição</li></ul>  | <ul><li>Administrador global</li> <li>Administrador de segurança</li> <li>Administrador de conformidade</li> <li>Operador de segurança</li> <li>Leitor de segurança</li> <li>Leitor global</li></ul> |
| Exibindo dados de busca | Exibir operações de segurança de dados | <ul><li>Leitor de segurança</li> <li>Administrador de segurança</li> <li>Destinatários somente exibição</li> | <ul><li>Administrador global</li> <li>Administrador de segurança</li> <li>Administrador de conformidade</li> <li>Operador de segurança</li> <li>Leitor de segurança</li> <li>Leitor global</li></ul> |
| Gerenciando alertas e incidentes | Investigação de alertas | <ul><li>Gerenciar alertas</li> <li>Administrador de segurança</li> | <ul><li>Administrador global</li> <li>Administrador de segurança</li> <li>Administrador de conformidade</li> <li>Operador de segurança</li> <li>Leitor de segurança</li></ul> |
| Correção do Centro de Ações | Ações de correção ativas – operações de segurança | Pesquisar e limpar | |
| Definindo detecções personalizadas | Gerenciar configurações de segurança |<ul><li>Gerenciar alertas</li> <li>Administrador de segurança</li></ul> | <ul><li>Administrador global</li> <li>Administrador de segurança</li> <li>Administrador de conformidade</li> <li>Operador de segurança</li> <li>Leitor de segurança</li> <li>Leitor global</li></ul> |
| Análise de Ameaças | Dados de alertas e incidentes: <ul><li>Exibir operações de segurança de dados</li></ul>Mitigações de TVM:<ul><li>Exibir dados - Gerenciamento de ameaças e vulnerabilidades</li></ul> | Dados de alertas e incidentes:<ul> <li>Somente exibição Gerenciar alertas</li> <li>Gerenciar alertas</li> <li>Configuração da organização</li><li>Logs de auditoria</li> <li>Logs de auditoria somente exibição</li><li>Leitor de segurança</li> <li>Administrador de segurança</li><li>Destinatários somente exibição</li> </ul> Tentativas de email evitadas: <ul><li>Leitor de segurança</li> <li>Administrador de segurança</li><li>Destinatários somente exibição</li> | Não disponível para usuários MCAS ou MDI |

Por exemplo, para exibir dados de busca do Microsoft Defender para Ponto de Extremidade, é necessário exibir permissões de operações de segurança de dados.  

Da mesma forma, para exibir dados de busca do Microsoft Defender para Office 365, os usuários exigiriam uma das seguintes funções:  

- Exibir operações de segurança de dados
- Leitor de segurança
- Administrador de segurança
- Destinatários somente exibição

## <a name="related-topics"></a>Tópicos relacionados
- [Gerenciar o acesso ao Microsoft 365 Defender](m365d-permissions.md)
- [Gerenciar acesso de administrador para MCAS](/cloud-app-security/manage-admins)
