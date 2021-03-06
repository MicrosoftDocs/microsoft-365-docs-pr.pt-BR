---
title: Configurar recursos automatizados de investigação e resposta Microsoft 365 Defender
description: Configurar investigação e resposta automatizadas com auto-recuperação Microsoft 365 Defender
search.appverid: MET150
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: 4275339e048a4197590c91c5904733ce99b22f9f
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083435"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Configurar recursos automatizados de investigação e resposta Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defender inclui poderosos [recursos](m365d-autoir.md) automatizados de investigação e resposta que podem economizar muito tempo e esforço à sua equipe de operações de segurança. Com [a auto-recuperação,](m365d-autoir.md#how-automated-investigation-and-self-healing-works)esses recursos imitam as etapas que um analista de segurança tomaria para investigar e responder a ameaças, apenas mais rápidas e com mais capacidade de escala.

Este artigo descreve como configurar a investigação e a resposta automatizadas Microsoft 365 Defender estas etapas:

1. [Revise os pré-requisitos](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).
2. [Revise ou altere o nível de automação para grupos de dispositivos.](#review-or-change-the-automation-level-for-device-groups)
3. [Revise suas políticas de segurança e alerta em Office 365](#review-your-security-and-alert-policies-in-office-365).
4. [Certifique-se Microsoft 365 Defender está ligado](#make-sure-microsoft-365-defender-is-turned-on).

Em seguida, após a configuração, você pode exibir e gerenciar ações de [correção no Centro de Ações.](m365d-autoir-actions.md)

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Pré-requisitos para investigação e resposta automatizadas em Microsoft 365 Defender

<br>

****

|Requisito|Detalhes|
|---|---|
|Requisitos de assinatura|Uma dessas assinaturas: <ul><li>Microsoft 365 E5</li><li>Microsoft 365 A5</li><li>Microsoft 365 E3 com o Microsoft 365 E5 Security complemento</li><li>Microsoft 365 A3 com o complemento Microsoft 365 A5 Segurança</li><li>Office 365 E5 mais Enterprise Mobility + Security E5 mais Windows E5</li></ul> <p> Consulte [Microsoft 365 Defender requisitos de licenciamento.](./prerequisites.md#licensing-requirements)|
|Requisitos de rede|<ul><li>[Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp) habilitado</li><li>[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) configurado</li><li>[Integração do Microsoft Defender para Identidade](/cloud-app-security/mdi-integration)</li></ul>|
|Requisitos de máquina do Windows|<ul><li>Windows 10, versão 1709 ou posterior instalada (Consulte [Windows 10 informações de versão](/windows/release-information/))</li><li>Os seguintes serviços de proteção contra ameaças configurados:<ul><li>[Microsoft Defender para Ponto de Extremidade](../defender-endpoint/configure-endpoints.md)</li><li>[Microsoft Defender Antivírus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</li></ul></li></ul>|
|Proteção para conteúdo de email e Office arquivos|[Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) configurado|
|Permissões|Para configurar recursos automatizados de investigação e resposta, você deve ter a função Administrador Global ou Administrador de Segurança atribuída em Azure Active Directory ( ) ou no Centro de administração do Microsoft 365 <https://portal.azure.com> ( <https://admin.microsoft.com> ). <p> Para obter as permissões necessárias para trabalhar com recursos automatizados de investigação e resposta, como revisão, aprovação ou rejeição de ações [pendentes,](m365d-action-center.md#required-permissions-for-action-center-tasks)consulte Permissões necessárias para tarefas do Centro de Ações.|
|

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Revisar ou alterar o nível de automação para grupos de dispositivos

Se as investigações automatizadas são realizadas e se as ações de correção são realizadas automaticamente ou somente após a aprovação de seus dispositivos dependem de determinadas configurações, como as políticas de grupo de dispositivos da sua organização. Revise o nível de automação configurado para suas políticas de grupo de dispositivos.

1. Vá para o Central de Segurança do Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) e entre.

2. Vá para **Configurações**  >  **Grupos de**  >  **Dispositivos de Permissões.**

3. Revise as políticas de grupo de dispositivos. Em particular, veja a **coluna Nível de Correção.** Recomendamos usar **Full - correção de ameaças automaticamente**.  Talvez seja necessário criar ou editar seus grupos de dispositivos para obter o nível de automação que deseja. Para obter ajuda com essa tarefa, consulte os seguintes artigos:
   - [Como as ameaças são remediadas](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Criar e gerenciar grupos de dispositivos](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Revise suas políticas de segurança e alerta no Office 365

A Microsoft fornece políticas de alerta [internas](../../compliance/alert-policies.md) que ajudam a identificar determinados riscos. Esses riscos incluem abuso de Exchange de administrador, atividade de malware, possíveis ameaças externas e internas e riscos de governança de informações. Alguns alertas podem disparar [investigação e resposta automatizadas em Office 365](../office-365-security/office-365-air.md). Certifique-se [de que os recursos do Defender Office 365](../office-365-security/defender-for-office-365.md) estão configurados corretamente.

Embora determinados alertas e políticas de segurança possam disparar investigações automatizadas, nenhuma ação de correção é realizada automaticamente *para email e conteúdo.* Em vez disso, todas as ações de correção para conteúdo de email e email aguardam aprovação pela sua equipe de operações de segurança no [Centro de Ações.](m365d-action-center.md)

As configurações de segurança no Office 365 ajudam a proteger o email e o conteúdo. Para exibir ou alterar essas configurações, siga as diretrizes em [Proteger contra ameaças](../office-365-security/protect-against-threats.md).

1. No portal Microsoft 365 Defender ( <https://security.microsoft.com> ), vá para **Políticas & Políticas de** Ameaças de \> **Regras.**

2. Certifique-se de que todas as políticas a seguir estão configuradas. Para obter ajuda e recomendações, consulte [Protect against threats](/microsoft-365/security/office-365-security/protect-against-threats).
   - [Anti-malware](../office-365-security/protect-against-threats.md#part-1---anti-malware-protection-in-eop)
   - [Anti-phishing](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)
   - [Anexos Seguros](../office-365-security/protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)
   - [Links Seguros](../office-365-security/protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)
   - [Anti-spam](../office-365-security/protect-against-threats.md#part-3---anti-spam-protection-in-eop)

3. [Certifique-se Cofre anexos](../office-365-security/mdo-for-spo-odb-and-teams.md) para SharePoint, OneDrive e Microsoft Teams está ligado.

4. Certifique-se de que a limpeza automática zero hora [(ZAP) no](../office-365-security/zero-hour-auto-purge.md) Exchange Online está em vigor.

5. (Esta etapa é opcional.) Revise suas [Office 365 de alerta](../../compliance/alert-policies.md) no Centro de conformidade do Microsoft 365 ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Várias políticas de alerta padrão estão na categoria Gerenciamento de ameaças. Alguns desses alertas podem disparar investigação e resposta automatizadas. Para saber mais, confira [Políticas de alerta padrão](../../compliance/alert-policies.md#default-alert-policies).

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Certifique-se Microsoft 365 Defender está ligado

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP on":::

1. Entre no portal Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ).

2. No painel de navegação, procure Incidentes & **Alertas,**  Busca e Centro de Ações, conforme mostrado na imagem anterior. 
   - Se você vir **Incidentes & Alertas,** Busca e Centro de **Ações,** Microsoft 365 Defender está ligado.  Consulte a [seção Revisar ou alterar o nível de automação para grupos de](#review-or-change-the-automation-level-for-device-groups) dispositivos deste artigo.
   - Se você não *vir* **Incidentes,** Centro **de** Ações ou **Microsoft 365 Defender**, talvez não seja ligado. Nesse caso, [visite a Central de Ações](m365d-action-center.md)).

3. No painel de navegação, escolha **Configurações**  >  **Microsoft 365 Defender**. Confirme se Microsoft 365 Defender está ligado.

> [!TIP]
> Precisa de ajuda? Consulte [Ativar Microsoft 365 Defender](m365d-enable.md).

## <a name="next-steps"></a>Próximas etapas

- [Ações de correção em Microsoft 365 Defender](m365d-remediation-actions.md)
- [Visite a Central de Ações](m365d-action-center.md)
