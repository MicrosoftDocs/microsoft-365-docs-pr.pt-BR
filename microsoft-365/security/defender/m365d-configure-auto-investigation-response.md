---
title: Configurar recursos automatizados de investigação e resposta no Microsoft 365 Defender
description: Configurar investigação e resposta automatizadas com auto-recuperação no Microsoft 365 Defender
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
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
ms.openlocfilehash: 164d4f52f5769d48249c1f4afcdf4be624f6aef7
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592043"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Configurar recursos automatizados de investigação e resposta no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

O Microsoft 365 [](m365d-autoir.md) Defender inclui poderosos recursos automatizados de investigação e resposta que podem economizar muito tempo e esforço à sua equipe de operações de segurança. Com [a auto-recuperação,](m365d-autoir.md#how-automated-investigation-and-self-healing-works)esses recursos imitam as etapas que um analista de segurança tomaria para investigar e responder a ameaças, apenas mais rápidas e com mais capacidade de escala. Este artigo descreve como configurar a investigação e a resposta automatizadas no Microsoft 365 Defender.

Para configurar recursos automatizados de investigação e resposta, siga estas etapas:

1. [Revise os pré-requisitos](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).
2. [Revise ou altere o nível de automação para grupos de dispositivos.](#review-or-change-the-automation-level-for-device-groups)
3. [Revise suas políticas de segurança e alerta no Office 365](#review-your-security-and-alert-policies-in-office-365).
4. [Certifique-se de que o Microsoft 365 Defender está ligado.](#make-sure-microsoft-365-defender-is-turned-on)

Em seguida, após a configuração, [exibir e gerenciar ações no Centro de Ações.](m365d-autoir-actions.md)

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Pré-requisitos para investigação e resposta automatizadas no Microsoft 365 Defender

|Requisito |Detalhes |
|:----|:----|
|Requisitos de assinatura |Uma dessas assinaturas: <br/>- Microsoft 365 E5<br/>- Microsoft 365 A5<br/>– Segurança do Microsoft 365 E5<br/>– Segurança do Microsoft 365 A5<br/>- Office 365 E5 mais Enterprise Mobility + Security E5 mais Windows E5<p> Consulte Requisitos de licenciamento [do Microsoft 365 Defender](./prerequisites.md#licensing-requirements).|
|Requisitos de rede |- [Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp) habilitado<br/>- [Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) configurado<br/>- [Integração do Microsoft Defender para Identidade](/cloud-app-security/mdi-integration) |
|Requisitos de máquina do Windows |- Windows 10, versão 1709 ou posterior instalado (Confira[Informações sobre a versão do Windows 10](/windows/release-information/)) <br/>- Os seguintes serviços de proteção contra ameaças configurados:<br/>- [Microsoft Defender para Ponto de Extremidade](../defender-endpoint/configure-endpoints.md)<br/>- [Microsoft Defender Antivírus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Proteção para conteúdo de email e arquivos do Office |[Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) configurado |
|Permissões | Para configurar recursos automatizados de investigação e resposta, você deve ter a função Administrador Global ou Administrador de Segurança atribuída no Azure Active Directory ( ) ou no Centro de administração do [https://portal.azure.com](https://portal.azure.com) Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ).<p>Para obter as permissões necessárias para trabalhar com recursos automatizados de investigação e resposta, como revisão, aprovação ou rejeição de ações [pendentes,](m365d-action-center.md#required-permissions-for-action-center-tasks)consulte Permissões necessárias para tarefas do Centro de Ações. |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Revisar ou alterar o nível de automação para grupos de dispositivos

Se as investigações automatizadas são realizadas e se as ações de correção são realizadas automaticamente ou somente após a aprovação de seus dispositivos dependem de determinadas configurações, como as políticas de grupo de dispositivos da sua organização. Revise o nível de automação definido para as políticas de grupo de dispositivos.

1. Vá para o Centro de Segurança do Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) e entre.
2. Vá para **Configurações**  >  **Permissões Grupos** de  >  **dispositivos**.
3. Revise as políticas de grupo de dispositivos. Em particular, veja a **coluna Nível de Correção.** Recomendamos usar **Full - correção de ameaças automaticamente**.  Talvez seja necessário criar ou editar seus grupos de dispositivos para obter o nível de automação que deseja. Para obter ajuda com essa tarefa, consulte os seguintes artigos:
   - [Como as ameaças são remediadas](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Criar e gerenciar grupos de dispositivos](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Revise suas políticas de segurança e alerta no Office 365

A Microsoft fornece políticas de alerta [internas](../../compliance/alert-policies.md) que ajudam a identificar determinados riscos. Esses riscos incluem abuso de permissões de administrador do Exchange, atividade de malware, possíveis ameaças externas e internas e riscos de governança de informações. Alguns alertas podem disparar [investigação e resposta automatizadas no Office 365](../office-365-security/office-365-air.md). Certifique-se [de que os recursos do Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) estão configurados corretamente.

Embora determinados alertas e políticas de segurança possam disparar investigações automatizadas, nenhuma ação de correção é realizada automaticamente para email e conteúdo. Em vez disso, todas as ações de correção para conteúdo de email e email aguardam aprovação pela sua equipe de operações de segurança no [Centro de Ações.](m365d-action-center.md)

As configurações de segurança no Office 365 ajudam a proteger email e conteúdo. Para exibir ou alterar essas configurações, siga as diretrizes em [Proteger contra ameaças](../office-365-security/protect-against-threats.md).

1. No Centro de segurança do Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ), acesse **Políticas** de proteção  >  **contra ameaças.**
2. Certifique-se de que todas as políticas a seguir estão configuradas. Para obter ajuda e recomendações, consulte [Protect against threats](/microsoft-365/security/office-365-security/protect-against-threats).
   - [Anti-malware (Office 365)](../office-365-security/protect-against-threats.md#part-1---anti-malware-protection)
   - [Anti-phishing no Defender para Office 365)](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection)
   - [Anexos Seguros (Office 365)](../office-365-security/protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)
   - [Links seguros (Office 365)](../office-365-security/protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)
   - [Anti-spam (Office 365)](../office-365-security/protect-against-threats.md#part-3---anti-spam-protection)
3. [Certifique-se de que o Microsoft Defender para Office 365 para SharePoint, OneDrive e Microsoft Teams](../office-365-security/protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on) está ligado.
4. Certifique-se [de que a limpeza automática](../office-365-security/protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop) zero hora para proteção de email está em vigor.
5. (Esta etapa é opcional.) Revise suas políticas de alerta do [Office 365](../../compliance/alert-policies.md) no centro de conformidade do Microsoft 365 ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Várias políticas de alerta padrão estão na categoria Gerenciamento de ameaças. Alguns desses alertas podem disparar investigação e resposta automatizadas. Para saber mais, confira [Políticas de alerta padrão](../../compliance/alert-policies.md#default-alert-policies).

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Certifique-se de que o Microsoft 365 Defender está ligado

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP on":::

1. Vá para o Centro de Segurança do Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ) e entre.
2. No painel de navegação, procure **Incidentes,** **Centro** de Ações e **Busca,** conforme mostrado na imagem anterior.
   - Se você vir **Incidentes,** **Centro de** Ações e **Busca**, o Microsoft 365 Defender está ligado. Consulte o procedimento, [Revise ou altere o nível de automação para grupos de dispositivos](#review-or-change-the-automation-level-for-device-groups) (neste artigo).
   - Se você não *vir* **Incidentes,** **Centro de** Ações ou **Busca**, o Microsoft 365 Defender pode não estar ligado. Nesse caso, prossiga para [Visitar a Central de Ações](m365d-action-center.md)).
3. No painel de navegação, escolha **Configurações**  >  **do Microsoft 365 Defender**. Confirme se o Microsoft 365 Defender está ligado. 

> [!TIP]
> Precisa de ajuda? Consulte [Ativar o Microsoft 365 Defender](m365d-enable.md).

## <a name="next-steps"></a>Próximas etapas

- [Ações de correção no Microsoft 365 Defender](m365d-remediation-actions.md)
- [Visite a Central de Ações](m365d-action-center.md)
