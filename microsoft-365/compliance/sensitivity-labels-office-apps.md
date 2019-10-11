---
title: Como os rótulos de confidencialidade funcionam nos aplicativos do Office
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Com os rótulos de confidencialidade, você pode classificar e ajudar a proteger seu conteúdo confidencial, garantindo ao mesmo tempo que a produtividade e a capacidade de colaboração de seu pessoal não sejam prejudicadas. Você pode usar rótulos de confidencialidade para impor configurações de proteção, como criptografia ou marcas d'água em conteúdo rotulado.
ms.openlocfilehash: f702423f0b1074b5619ef1c321cc5e9f1daef1d7
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417560"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a>Como os rótulos de confidencialidade funcionam nos aplicativos do Office

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a>Quais pré-requisitos existem para usar rótulos de confidencialidade nos aplicativos do Office?

### <a name="common-requirements"></a>Requisitos comuns 

- Rótulos de confidencialidade unificados devem ser [configurados e publicados no Centro de conformidade e segurança](https://aka.ms/managemip)
- Os usuários devem estar conectados ao Office com suas contas profissionais.
- Os usuários devem ter uma licença do Office 365 E3 ou superior atribuída.

### <a name="additional-requirements-for-office-for-windows"></a>Requisitos adicionais para o Office para Windows 

- O cliente da Proteção de Informações do Azure não deve estar em execução no Office. Confira também: [Os rótulos de confidencialidade podem ser executados juntamente com o cliente da Proteção de Informações do Azure no Office para Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).

### <a name="additional-requirements-for-outlook-on-all-platforms"></a>Requisitos adicionais para o Outlook em todas as plataformas 

- Na sua configuração de rótulo, se você ativar a marcação de conteúdo, deverá estar usando o Exchange Online para que a marcação de conteúdo seja inserida em trânsito.

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a>Quais recursos de rótulos de confidencialidade são compatíveis com o Office hoje? 

<table border="1" cellspacing="0" cellpadding="0">
<th><font size="-1">Recurso<th><font size="-1">Windows<th><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</tr>
<tr><td>

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint<br>
Outlook


<td><font size="-1"> Word<br>
Excel<br>
PowerPoint<br>
Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook </b>
</tr>

<tr>
<td><font size="-1">Aplicar, alterar ou remover rótulos manualmente<td><font size="-1"><b>Sim</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sim</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Sim</b><br><font size="-1">2.21+</font>
<td><font size="-1">Em breve<sup>3</sup>
<td><font size="-1"><b>Sim</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Em breve<sup>3</sup>
<td><font size="-1">Em breve<sup>3</sup><td><font size="-1">Em breve<sup>3</sup>

<tr>
<td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Aplicar um rótulo padrão</a>
<td><font size="-1"><b>Sim</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sim</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Sim</b><br><font size="-1">2.21+</font>
<td><font size="-1">Em breve<sup>3</sup>
<td><font size="-1"><b>Sim</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Em breve<sup>3</sup>
<td><font size="-1">Em breve<sup>3</sup>
<td><font size="-1">Em breve<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Exigir uma justificativa para alterar um rótulo</a><sup>1</sup>
<td><font size="-1"><b>Sim</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sim</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Sim</b><br><font size="-1">2.21+</font>
<td><font size="-1">Em breve<sup>3</sup>
<td><font size="-1"><b>Sim</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Em breve<sup>3</sup>
<td><font size="-1">Em breve<sup>3</sup>
<td><font size="-1">Em breve<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Fornecer um link de ajuda para uma página de ajuda personalizada</a>
<td><font size="-1"><b>Sim</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sim</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Sim</b><br><font size="-1">2.21+</font>
<td><font size="-1">Em breve<sup>3</sup>
<td><font size="-1"><b>Sim</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Em breve<sup>3</sup>
<td><font size="-1">Em breve<sup>3</sup>
<td><font size="-1">Em breve<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Marcar o conteúdo</a>
<td><font size="-1"><b>Sim</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sim</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Sim</b><br><font size="-1">2.21+</font>
<td><font size="-1">Em breve<sup>3</sup>
<td><font size="-1"><b>Sim</b><br><font size="-1">16.0.11231+</font
><td><font size="-1">Em breve<sup>3</sup>
<td><font size="-1">Em breve<sup>3</sup>
<td><font size="-1">Em breve<sup>3</sup>

<tr><td><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/encryption-sensitivity-labels#assign-permissions-now">Atribuir permissões predefinidas</a>
<td><font size="-1"><b>Sim</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sim</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>Sim</b><br><font size="-1">2.21+</font>
<td><font size="-1">Em breve<sup>3</sup>
<td><font size="-1"><b>Sim</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">Em breve<sup>3</sup>
<td><font size="-1">Em breve<sup>3</sup>
<td><font size="-1">Em breve<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Permitir que os usuários atribuam permissões</a>
<td><font size="-1"><b>Sim</b><sup>2</sup><br><font size="-1">1910+</font>

<td><font size="-1"><b>Sim</b><sup>2</sup><br><font size="-1">16.21.0+</font>

<td><font size="-1">TBD
<td><font size="-1">Em breve<sup>3</sup>
<td><font size="-1">TBD<td
><font size="-1">Em breve<sup>3</sup>
<td><font size="-1">TBD
<td><font size="-1">Em breve<sup>3</sup>

<tr><td><font size="-1">Enviar dados de <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">análise de rótulos</a> para administradores
<td><font size="-1">TBD

<td><font size="-1">TBD

<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD

<tr><td><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Exigir que os usuários apliquem um rótulo a seus emails e documentos</a>
<td><font size="-1">TBD

<td><font size="-1">TBD

<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Aplicar um rótulo de confidencialidade ao conteúdo automaticamente</a>
<td><font size="-1">TBD

<td><font size="-1">TBD

<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
</table>

<br><sup>1</sup>Se configurado, os usuários serão solicitados a justificar os downgrades de rótulos. No entanto, os dados de justificativa ainda não estão disponíveis para administradores. Eles ficarão disponíveis quando o recurso "enviar dados de análise de rótulos para administradores" for suportado.
<br><sup>2</sup>No momento, permitir que os usuários atribuam permissões está disponível apenas no Outlook para Windows e Mac. A disponibilidade para Word, Excel e PowerPoint ainda não foi definida.
<br><sup>3</sup>T4 esperado do ano civil de 2019.

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a>Quando marcas de conteúdo ou criptografia são aplicadas depois que o conteúdo recebe um rótulo de confidencialidade?

| Aplicativo | Marcação de conteúdo | Criptografia
| --- | --- | --- |
| Word, Excel, PowerPoint em todas as plataformas | Imediatamente | Imediatamente |
| Outlook para PC e Mac | Após o email ser enviado pelo Exchange Online | Imediatamente |
| Outlook na Web, iOS e Android | Após o email ser enviado pelo Exchange Online | Após o email ser enviado pelo Exchange Online |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a>Os rótulos de confidencialidade podem ser executados juntamente com o cliente da Proteção de Informações do Azure no Office para Windows?

Não. Os rótulos de confidencialidade serão desativados se o cliente da Proteção de Informações do Azure estiver carregado no Office para Windows.

Se você tiver o cliente da Proteção de Informações do Azure instalado, mas desejar usar rótulos de confidencialidade, poderá:

1. Configurar a configuração de Diretiva de Grupo  **Usar o recurso Confidencialidade no Office para aplicar e exibir rótulos de confidencialidade**, que pode ser encontrada em **Configuração do Usuário/Modelos Administrativos/Microsoft Office 2016/Configurações de Segurança**.

  >Nota: essa configuração pode ser implantada por meio de mecanismos tradicionais de implantação de política de grupo ou pelo [serviço de política de nuvem do Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service). 
 
  Como alternativa, você pode desinstalar ou  [desabilitar](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) o cliente da Proteção de Informações do Azure. 

2. Reinicie todos os aplicativos do Office.

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a>Os rótulos de confidencialidade serão compatíveis com as versões sem assinatura do Office, como o Office 2016 ou o Office 2019?

Não. Os rótulos de confidencialidade serão compatíveis apenas com a assinatura do Office 365, e não serão compatíveis com nenhuma versão que não seja de assinatura. No entanto, o cliente de rotulagem unificada da Proteção de Informações do Azure pode ser usado em versões sem assinatura do Office. 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a>Implantei anteriormente modelos de proteção antes de configurar rótulos de confidencialidade. Para onde eles foram?

Os [modelos de proteção](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) definidos pelo administrador ficam ocultos da experiência do usuário do Office quando os rótulos de confidencialidade são ativados porque são redundantes com os rótulos de confidencialidade com criptografia ativada. 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a>Um arquivo ou email pode ter mais de uma classificação?

Não. Os usuários podem selecionar apenas um rótulo de cada vez para cada documento ou email.

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a>Quando um email é rotulado, os anexos recebem automaticamente a mesma rotulagem?

Não. Quando você rotula uma mensagem de email com anexos, esses anexos não herdam o mesmo rótulo. Os anexos permanecem sem rótulo ou retêm um rótulo aplicado separadamente. No entanto, se o rótulo do email aplicar proteção, essa proteção será aplicada aos anexos do Office.

## <a name="additional-resources"></a>Recursos adicionais

[Perguntas frequentes sobre classificação e rotulagem na Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[Aplicar rótulos de confidencialidade aos seus documentos e email no Office](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
