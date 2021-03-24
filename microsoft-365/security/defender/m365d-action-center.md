---
title: Vá para a Central de ações para exibir e aprovar suas tarefas automatizadas de investigação e correção
description: Use a Central de ações para exibir detalhes sobre investigação automatizada e aprovar ações pendentes
keywords: Central de ações, proteção contra ameaças, investigação, alerta, pendente, automatizado, detecção
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 02/01/2021
ms.openlocfilehash: a9590ba5742bdfab9902d8168e0da2f9f3843221
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054409"
---
# <a name="the-action-center"></a>A Central de Ações

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

## <a name="a-single-pane-of-glass-experience"></a>Uma experiência de "painel único"

A Central de ações fornece uma experiência de "painel único" para tarefas, como:
- Aprovar ações de correção pendentes;
- Exibir um log de auditoria de ações de correção já aprovadas; e
- Revendo as ações de correção concluídas.

Sua equipe de operações de segurança pode operar de forma mais eficaz e eficiente, pois o Centro de Ações fornece uma visão abrangente do Microsoft 365 Defender no trabalho.

## <a name="a-new-unified-action-center"></a>Um novo centro de ações unificado

Temos o prazer de anunciar um novo Centro de Ações unificado ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) )! 

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Centro de Ações Unificadas no Microsoft 365 Defender":::

O Centro de Ações aprimorado lista ações de correção pendentes e concluídas para seus dispositivos, email & conteúdo de colaboração e identidades em um único local.
- Se você estava usando anteriormente o Centro de Conformidade e Segurança do Office 365 & ( ), experimente o novo centro de ações unificado no centro de segurança do [https://protection.office.com](https://protection.office.com) Microsoft 365 ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).
- Se você estava usando a Central de Ações no Centro de Segurança do Microsoft Defender ( ), experimente o novo centro de ações unificado no centro de segurança do [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) Microsoft 365 ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).
- Se você já estava usando o centro de segurança do Microsoft 365 ( ), você verá várias melhorias no [https://security.microsoft.com](https://security.microsoft.com) Centro de Ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).

O centro de ações unificado reúne ações de correção no Defender para Ponto de Extremidade e no Defender para Office 365. Ele define um idioma comum para todas as ações de correção e fornece uma experiência de investigação unificada. O Centro de Ações fornece à sua equipe de operações de segurança uma experiência de "painel único de vidro" para exibir e gerenciar ações de correção.  

Você pode usar o Centro de Ações unificado se tiver permissões apropriadas e uma ou mais das seguintes assinaturas:

- [Defender para Ponto de Extremidade](../defender-endpoint/microsoft-defender-advanced-threat-protection.md)
- [O que é o Defender para Office 365?](/microsoft-365/security/defender-365-security/defender-for-office-365)
- [Microsoft 365 Defender](microsoft-365-defender.md)

> [!TIP]
> Para saber mais, confira [Requisitos](./prerequisites.md).

## <a name="using-the-action-center"></a>Usando o Centro de Ações

1. Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre. 
2. No painel de navegação, escolha **Central de ações**. 

Ao visitar a Central de Ações, você verá duas guias: Ações pendentes e Histórico. A tabela a seguir resume o que você verá em cada guia:

|Guia  |Descrição  |
|---------|---------|
|**Pending**     | Exibe uma lista de ações que exigem atenção. Você pode aprovar ou rejeitar ações uma por vez ou selecionar várias ações se elas têm o mesmo tipo de ação (como arquivo de Quarentena). <p>**DICA**: Certifique-se de revisar e aprovar (ou rejeitar) ações pendentes assim que possível para que suas investigações automatizadas possam ser concluídas em tempo hábil.       |
|**Histórico**     | Serve como um log de auditoria para ações que foram realizadas, como: <br/>- Ações de correção que foram tomadas como resultado de investigações automatizadas <br/>- Ações de correção que foram tomadas em mensagens de email suspeitas ou mal-intencionadas, arquivos ou URLs<br/>- Ações de correção aprovadas pela sua equipe de operações de segurança <br/>- Comandos executados e ações de correção que foram aplicadas durante as sessões de Resposta ao Vivo<br/>- Ações de correção que foram tomadas pela proteção antivírus <p>Fornece uma maneira de desfazer determinadas ações (consulte [Desfazer ações concluídas](m365d-autoir-actions.md#undo-completed-actions)).        |

Você pode personalizar, classificar, filtrar e exportar dados no Centro de Ações.

:::image type="content" source="../../media/m3d-action-center-columnsfilters.png" alt-text="O Centro de Ações permite classificar, filtrar e personalizar sua lista de ações":::

- Selecione um título de coluna para classificar itens em ordem crescente ou decrescente.
- Use o filtro de período de tempo para exibir dados do último dia, semana, 30 dias ou 6 meses.
- Escolha as colunas que você deseja exibir.
- Especifique quantos itens devem ser incluídos em cada página de dados.
- Use filtros para exibir apenas os itens que você deseja ver.
- Selecione **Exportar** para exportar resultados para um arquivo .csv.

## <a name="actions-tracked-in-the-action-center"></a>Ações controladas no Centro de Ações

Todas as ações, sejam elas pendentes de aprovação ou já foram realizadas, são controladas no Centro de Ações. As ações disponíveis incluem o seguinte:

- Coletar pacote de investigação 
- Isolar dispositivo (essa ação pode ser desfeita) 
- Máquina de offboard 
- Execução de código de versão 
- Liberar da quarentena 
- Exemplo de solicitação 
- Restringir a execução de código (essa ação pode ser desfeita) 
- Executar verificação antivírus 
- Parar e colocar em quarentena 

Além das ações de correção que são tomadas automaticamente como resultado de [investigações automatizadas,](m365d-autoir.md)o Centro de Ações também rastreia ações que sua equipe de segurança tem feito para resolver ameaças detectadas e ações que foram tomadas como resultado de recursos de proteção contra ameaças no Microsoft 365 Defender. Para obter mais informações sobre ações de correção automáticas e manuais, consulte [Ações de correção](m365d-remediation-actions.md).

## <a name="viewing-action-source-details"></a>Exibindo detalhes da origem da ação

(**NOVO!**) O Centro de Ações aprimorado agora inclui uma coluna **de origem** action que informa de onde cada ação veio. A tabela a seguir descreve os possíveis **valores de origem action:**

| Valor de origem da ação | Descrição |
|:-----|:---|
| **Ação manual do dispositivo** | Uma ação manual realizada em um dispositivo. Exemplos [incluem isolamento de dispositivo ou](../defender-endpoint/respond-machine-alerts.md#isolate-devices-from-the-network) quarentena de [arquivo](../defender-endpoint/respond-file-alerts.md#stop-and-quarantine-files). |
| **Ação de email manual** | Uma ação manual realizada no email. Um exemplo inclui a exclusão suave de mensagens de email ou [a correção de uma mensagem de email](../defender-365-security/remediate-malicious-email-delivered-office-365.md). |
| **Ação de dispositivo automatizada** | Uma ação automatizada realizada em uma entidade, como um arquivo ou processo. Exemplos de ações automatizadas incluem o envio de um arquivo para quarentena, a interrupção de um processo e a remoção de uma chave do Registro. (Consulte [Ações de correção no Microsoft Defender para Ponto de](../defender-endpoint/manage-auto-investigation.md#remediation-actions)Extremidade .) |
| **Ação de email automatizada** | Uma ação automatizada realizada no conteúdo de email, como uma mensagem de email, anexo ou URL. Exemplos de ações automatizadas incluem a exclusão automática de mensagens de email, o bloqueio de URLs e a exclusão do encaminhamento de emails externos. (Consulte [Ações de correção no Microsoft Defender para Office 365](../defender-365-security/air-remediation-actions.md).) |
| **Ação de busca avançada** | Ações realizadas em dispositivos ou emails com [busca avançada.](./advanced-hunting-overview.md) |
| **Ação do Explorer** | Ações realizadas no conteúdo de email com [o Explorer](../defender-365-security/threat-explorer.md). |
| **Ação manual de resposta ao vivo** | Ações realizadas em um dispositivo com [resposta ao vivo](../defender-endpoint/live-response.md). Exemplos incluem a exclusão de um arquivo, a interrupção de um processo e a remoção de uma tarefa agendada. |
| **Ação de resposta ao vivo** | Ações realizadas em um dispositivo com [o Microsoft Defender para APIs do Ponto de Extremidade.](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis) Exemplos de ações incluem isolar um dispositivo, executar uma verificação antivírus e obter informações sobre um arquivo. |

## <a name="required-permissions-for-action-center-tasks"></a>Permissões necessárias para tarefas da Central de ações

Para executar tarefas, como aprovar ou rejeitar ações pendentes no Centro de Ações, você deve ter permissões atribuídas conforme listado na tabela a seguir:

|Ação de correção |Funções e permissões necessárias |
|--|----|
|Microsoft Defender para Correção de Ponto de Extremidade (dispositivos) |Função **Administrador de Segurança** atribuída no Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) ou no centro de administração do Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>---ou---<br/>**Função de ações de correção** ativa atribuídas ao Microsoft Defender para Ponto de Extremidade <br/> <br/> Para saber mais, confira os seguintes recursos: <br/>- [Permissões da função de administrador no Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Criar e gerenciar funções para controle de acesso baseado em função (Microsoft Defender para Ponto de Extremidade)](../defender-endpoint/user-roles.md)  |
|Correção do Microsoft Defender para Office 365 (conteúdo do Office e email)  |Função **Administrador de Segurança** atribuída no Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) ou no centro de administração do Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>---e--- <br/>**Função de pesquisa e** limpeza atribuída ao Centro de Conformidade & segurança ( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**IMPORTANTE**: Se  você tiver a função de Administrador de Segurança atribuída apenas no Centro de Conformidade e Segurança do Office 365 & ( ), você não poderá acessar o Centro de Ações ou os recursos do [https://protection.office.com](https://protection.office.com) Microsoft 365 Defender. Você deve ter a função **administrador de segurança** atribuída no Azure Active Directory ou no Centro de administração do Microsoft 365. <br/><br/>Para saber mais, confira os seguintes recursos: <br/>- [Permissões da função de administrador no Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Permissões no Centro de Conformidade & Segurança](/microsoft-365/security/defender-365-security/permissions-in-the-security-and-compliance-center) |

> [!TIP]
> Os usuários que têm a função **Administrador Global** atribuída no Azure Active Directory podem aprovar ou rejeitar qualquer ação pendente na Central de ações. No entanto, como prática prática, sua organização deve limitar o número de pessoas que têm a função de **Administrador Global** atribuída. Recomendamos usar as funções Administrador de **Segurança,** Correção Ativa **e** Pesquisa e Limpeza listadas na tabela anterior para permissões do Centro de Ações. 

## <a name="next-step"></a>Próxima etapa 

- [Revisar e gerenciar ações de correção](m365d-autoir-actions.md)
