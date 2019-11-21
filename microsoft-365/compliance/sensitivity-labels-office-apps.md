---
title: Rótulos de sensibilidade em aplicativos do Office
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/20/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Saiba mais sobre como os usuários trabalham com rótulos de confidencialidade nos aplicativos do Office para a área de trabalho, aplicativos do Office para dispositivos móveis e aplicativos do Office para a Web. Descubra quais aplicativos dão suporte a rótulos de confidencialidade.
ms.openlocfilehash: 1b472185df2d45717cba6cfca30176768bf9cd4e
ms.sourcegitcommit: 5f96fa472cbdca30c2cfe24d66c9c6fcaedb1a6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2019
ms.locfileid: "38755589"
---
# <a name="sensitivity-labels-in-office-apps"></a>Rótulos de sensibilidade em aplicativos do Office

Este artigo descreve:

- Requisitos para seu ambiente antes de aplicar rótulos de sensibilidade a emails, arquivos e anexos.
- Quais recursos de rótulo de confidencialidade são compatíveis com cada aplicativo do Office.
- O que acontece quando você combina rótulos de confidencialidade com outras tecnologias de conformidade e segurança da Microsoft que funcionam com os aplicativos do Office.
- Como as pessoas em sua organização podem usar rótulos de confidencialidade quando trabalharem com aplicativos do Office para Windows e aplicativos do Office para a Web.
- Onde ir para obter pessoas em sua organização iniciadas com rótulos de confidencialidade.

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>Requisitos de assinatura e licenciamento para rótulos de confidencialidade

Os usuários devem ter pelo menos uma das seguintes licenças atribuídas:

- [Microsoft 365 E3](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) ou superior

- [Office 365 E3](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e3-business-software) ou superior

- [Proteção de informações do Azure Premium P1](https://azure.microsoft.com/pricing/details/information-protection/) ou superior

O cliente de rotulagem interno do Office oferece suporte a rótulos de sensibilidade com uma versão de assinatura do Office. O cliente não oferece suporte a versões autônomas, por exemplo, o Office 2016 ou o Office 2019.

Para usar o rótulo de confidencialidade automático ou recomendado, seus usuários precisam de uma das seguintes licenças:

- [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) ou superior

- [Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software) ou superior

- [Proteção de informações do Azure P2](https://azure.microsoft.com/pricing/details/information-protection/) ou superior

## <a name="support-for-sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Suporte para recursos de rótulo de confidencialidade no Word, Excel e PowerPoint

Para cada capacidade, a tabela a seguir lista a versão mínima necessária para esse aplicativo. TBD significa que você não pode usar esse recurso nessa plataforma.

|Funcionalidade                                                                                                        |Windows Desktop |Área de trabalho Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Aplicar, alterar ou remover manualmente o rótulo](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Aplicar um rótulo padrão](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | A definir                                                        |
|[Exigir uma justificativa para alterar um rótulo](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Fornecer um link de ajuda para uma página de ajuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcar o conteúdo](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Atribuir permissões agora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Permitir que usuários atribuam permissões](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | TBD            | TBD        | TBD   | TBD         | TBD                                                        |
|[Exibir o uso de rótulo com o rótulo Analytics](label-analytics.md) e enviar dados para administradores                      | TBD            | TBD        | TBD   | TBD         | TBD                                                        |
|
  [Exigir que os usuários apliquem um rótulo a seus emails e documentos](sensitivity-labels.md#what-label-policies-can-do)   | TBD            | TBD        | TBD   | TBD         | TBD                                                        |
|[Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](apply-sensitivity-label-automatically.md)                    | Visualização: na implantação do [Office Insider](https://office.com/insider)                                  | TBD | TBD | TBD | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|Suporte para [salvamento automático](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) e [coautoria](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) em documentos rotulados e protegidos | TBD | TBD | TBD | TBD | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|

## <a name="support-for-sensitivity-label-capabilities-in-outlook"></a>Suporte para recursos de rótulo de confidencialidade no Outlook

Para cada capacidade, a tabela a seguir lista a versão mínima necessária para esse aplicativo. TBD significa que você não pode usar esse recurso nessa plataforma.

|Funcionalidade                                                                                                        |Outlook na área de trabalho do Windows |Área de trabalho do Outlook no Mac  |Outlook no iOS |Outlook no Android |Outlook Online |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Aplicar, alterar ou remover manualmente o rótulo](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sim               |
|[Aplicar um rótulo padrão](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sim               |
|[Exigir uma justificativa para alterar um rótulo](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sim               |
|[Fornecer um link de ajuda para uma página de ajuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sim               |
|[Marcar o conteúdo](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sim               |
|[Atribuir permissões agora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sim               |
|[Permitir que usuários atribuam permissões](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sim               |
|[Exibir o uso de rótulo com o rótulo Analytics](label-analytics.md) e enviar dados para administradores                      | TBD                       | TBD                    | TBD           | TBD               | TBD               |
|
  [Exigir que os usuários apliquem um rótulo a seus emails e documentos](sensitivity-labels.md#what-label-policies-can-do)   | TBD                       | TBD                    | TBD           | TBD               | TBD               |
|[Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](apply-sensitivity-label-automatically.md)                    | TBD                       | TBD                    | TBD           | TBD               | Visualização: na distribuição para [lançamento direcionado](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide) |
|

## <a name="about-the-office-built-in-labeling-client"></a>Sobre o cliente de rotulação interno do Office

O cliente de rotulagem interno do Office baixa as configurações de política e rótulos dos seguintes centros de administração:

- Centro de Conformidade e Segurança do Office 365

- Centro de segurança do Microsoft 365

- Centro de conformidade do Microsoft 365

O cliente de rotulagem interno do Office é habilitado automaticamente para usuários que tenham uma ou mais [políticas de etiqueta publicadas](sensitivity-labels.md#what-label-policies-can-do) .

Para usar o cliente de rotulagem interno no Office no Windows, não é possível executar o suplemento do Azure Information Protection ao mesmo tempo no Office. Você pode desinstalar temporária ou permanentemente o cliente de proteção de informações do Azure ou pode deixá-lo instalado e configurar o Office para impedir sua execução.

1. Execute uma destas opções:

    **Para vários computadores:** Configurar a configuração de diretiva de grupo **usar o recurso de confidencialidade no Office para aplicar e exibir rótulos de confidencialidade** . Encontre essa configuração em **configuração do usuário/Modelos Administrativos/Microsoft Office 2016/configurações de segurança**. Implante essa configuração por meio da política de grupo ou usando o [serviço política de nuvem do Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).

    **Para um único computador:** Consulte "Exibir, gerenciar e instalar suplementos nos programas do Office" e [desabilitar permanentemente ou remover](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d) o suplemento de proteção de informações do Azure em um único computador.

2. Reinicie todos os aplicativos do Office.

Para obter mais informações sobre aplicativos cliente para proteção de informações, consulte [o lado do cliente da proteção de informações do Azure](https://docs.microsoft.com/azure/information-protection/rms-client/use-client).

## <a name="protection-templates-and-sensitivity-labels"></a>Modelos de proteção e rótulos de confidencialidade

[Modelos de proteção](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)definidos pelo administrador, como aqueles que você define para a criptografia de mensagem do Office 365, estão ocultos na experiência do usuário do Office quando os rótulos de confidencialidade estão habilitados porque são redundantes com rótulos de sensibilidade que têm criptografia habilitada.

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Aplicar rótulos de confidencialidade a arquivos, emails e anexos

Os usuários podem aplicar apenas um rótulo por vez para cada documento ou email.

Quando você rotula uma mensagem de email que tem anexos, os anexos não herdam o rótulo. Se os anexos possuírem um rótulo, eles manterão o rótulo aplicado separadamente. Se os anexos não possuírem um rótulo, os anexos permanecerão sem um rótulo. No entanto, se o rótulo do email aplicar proteção, essa proteção será aplicada aos anexos do Office.

## <a name="sensitivity-label-compatibility"></a>Compatibilidade de rótulo de confidencialidade

**Com aplicativos habilitados para RMS**. Se você abrir um documento ou email rotulado _e criptografado_ em um [aplicativo habilitado para RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) que não ofereça suporte a rótulos de sensibilidade, o aplicativo ainda forçará a criptografia e o gerenciamento de direitos.

**Com o cliente de proteção de informações do Azure**. Você pode exibir e alterar os rótulos de sensibilidade que você aplica aos documentos e emails com o cliente de etiquetagem interno do Office com o cliente de proteção de informações do Azure e o contrário.

**Com outras versões do Office**. Qualquer usuário autorizado pode abrir documentos e emails rotulados em outras versões do Office. No entanto, você só pode exibir ou alterar o rótulo nas versões compatíveis do Office ou no cliente de proteção de informações do Azure. As versões do aplicativo do Office com suporte estão listadas nas tabelas deste artigo.

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Suporte para arquivos do SharePoint e do OneDrive protegidos por rótulos de confidencialidade

Para usar o cliente de rotulamento interno do Office no Office na Web, o documento deve estar localizado em uma instância do OneDrive for Business ou do SharePoint Online que tenha optado por usar os [Rótulos de confidencialidade para arquivos do Office no SharePoint e no onedrive](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="when-office-365-applies-marks-and-encryption-to-content"></a>Quando o Office 365 aplica marcas e criptografia ao conteúdo

O Office 365 aplica marcas de conteúdo ou criptografia com um rótulo de confidencialidade de forma diferente, dependendo do aplicativo que você usa.

| Aplicativo | Marcação de conteúdo | Criptografia |
| --- | --- | --- |
| Word, Excel, PowerPoint em todas as plataformas | Imediatamente | Imediatamente |
| Outlook para PC e Mac | Após o Exchange Online enviar o email | Imediatamente |
| Outlook na Web, iOS e Android | Após o Exchange Online enviar o email | Após o Exchange Online enviar o email |
|

## <a name="more-resources"></a>Mais recursos

[Perguntas frequentes sobre classificação e rotulagem na Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)

[Aplicar rótulos de confidencialidade aos seus documentos e email no Office](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
