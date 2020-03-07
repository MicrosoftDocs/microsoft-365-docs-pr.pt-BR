---
title: Usar rótulos de confidencialidade em aplicativos do Office
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Saiba mais sobre como os usuários trabalham com rótulos de confidencialidade nos aplicativos do Office para a área de trabalho, aplicativos do Office para dispositivos móveis e aplicativos do Office para a Web. Descubra quais aplicativos dão suporte a rótulos de confidencialidade.
ms.openlocfilehash: 759c944bc72c39d1fd118dcb1b3515b5ede79687
ms.sourcegitcommit: 41c0bc5cf50f4ca63b4286d1ea0f58ab82984b7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2020
ms.locfileid: "42548183"
---
# <a name="use-sensitivity-labels-in-office-apps"></a>Usar rótulos de confidencialidade em aplicativos do Office

Quando você [publicou](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) rótulos de sensibilidade do centro de conformidade da Microsoft 365 ou do centro de rotulação equivalente, eles começarão a aparecer em aplicativos do Office para que os usuários classifiquem e protejam os dados à medida que são criados ou editados.

Use as informações deste artigo para ajudá-lo a gerenciar com êxito os rótulos de confidencialidade nos aplicativos do Office. Por exemplo, identifique as versões mínimas dos aplicativos necessários para dar suporte ao rotulamento interno e entenda as interações com o cliente de rotulação unificado de proteção de informações do Azure e a compatibilidade com outros aplicativos e serviços.

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>Requisitos de assinatura e licenciamento para rótulos de confidencialidade

Os usuários devem ter pelo menos uma das seguintes licenças atribuídas:

- [Microsoft 365 E3](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) ou superior

- [Office 365 E3](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e3-business-software) ou superior

- [Proteção de informações do Azure Premium P1](https://azure.microsoft.com/pricing/details/information-protection/) ou superior

O cliente de rotulagem interno do Office oferece suporte a rótulos de confidencialidade com uma edição de assinatura do Office. Este cliente de rótulo não dá suporte a edições autônomas do Office, como o Office 2016 ou o Office 2019. Para usar rótulos de confidencialidade com essas edições do Office em computadores com Windows, instale o cliente de rotulação unificado de proteção de informações do Azure.

Para usar o rótulo de confidencialidade automático ou recomendado, seus usuários precisam de uma das seguintes licenças:

- [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) ou superior

- [Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software) ou superior

- [Proteção de Informações do Azure Premium P2](https://azure.microsoft.com/pricing/details/information-protection/)

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Suporte para recursos de rótulo de confidencialidade em aplicativos

Para cada capacidade, as tabelas a seguir listam a versão mínima necessária para esse aplicativo suportar rótulos de sensibilidade usando rotulação interna. Ou, se o recurso de rótulo estiver em visualização pública ou em revisão para uma versão futura.

Novas versões dos aplicativos são disponibilizadas em momentos diferentes para diferentes canais de atualização. Para obter mais informações, incluindo como configurar seu canal de atualização para que você possa testar um novo recurso de rotulação em que está interessado, consulte [Overview of Update Channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus). Os novos recursos que estão na visualização privada não estão incluídos na tabela, mas você pode participar dessas visualizações, especificando sua organização para o [programa de visualização privada da proteção de informações da Microsoft](https://aka.ms/mip-preview).

Recursos adicionais estão disponíveis quando você instala o cliente de rotulação unificado de proteção de informações do Azure, que é executado somente em computadores Windows. Para obter esses detalhes, consulte [Compare the Labeling clients for Windows Computers](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers).

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Recursos de rótulo de confidencialidade no Word, Excel e PowerPoint

|Funcionalidade                                                                                                        |Windows Desktop |Área de trabalho Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Aplicar, alterar ou remover manualmente o rótulo](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Aplicar um rótulo padrão](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | Em revisão                                                        |
|[Exigir uma justificativa para alterar um rótulo](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Fornecer ajuda para um link para uma página de ajuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcar o conteúdo](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Atribuir permissões agora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Permitir que usuários atribuam permissões](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | Visualização: no [canal mensal (direcionado)](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus#monthly-channel-for-office-365-proplus)            | Visualização: no [Office Insider](https://office.com/insider)        | Em revisão   | Em revisão         | Em revisão                                                        |
|[Exibir o uso de rótulo com o rótulo Analytics](label-analytics.md) e enviar dados para administradores                      | Em revisão            | Em revisão        | Em revisão   | Em revisão         | Em revisão                                                        |
|[Exigir que os usuários apliquem um rótulo aos seus emails e documentos](sensitivity-labels.md#what-label-policies-can-do)   | Em revisão            | Em revisão        | Em revisão   | Em revisão         | Em revisão                                                        |
|[Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](apply-sensitivity-label-automatically.md)                    | Visualização: no [Office Insider](https://office.com/insider)                                  | Em revisão | Em revisão | Em revisão | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|Suporte para [salvamento automático](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) e [coautoria](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) em documentos rotulados e protegidos | Em revisão | Em revisão | Em revisão | Em revisão | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|

### <a name="sensitivity-label-capabilities-in-outlook"></a>Recursos de rótulo de confidencialidade no Outlook

|Funcionalidade                                                                                                        |Outlook na área de trabalho do Windows |Área de trabalho do Outlook no Mac  |Outlook no iOS |Outlook no Android |Outlook na Web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Aplicar, alterar ou remover manualmente o rótulo](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Aplicar um rótulo padrão](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Exigir uma justificativa para alterar um rótulo](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Fornecer ajuda para um link para uma página de ajuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Marcar o conteúdo](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Atribuir permissões agora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Permitir que usuários atribuam permissões](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Exibir o uso de rótulo com o rótulo Analytics](label-analytics.md) e enviar dados para administradores                      | Em revisão                       | Em revisão                    | Em revisão           | Em revisão               | Em revisão               |
|[Exigir que os usuários apliquem um rótulo aos seus emails e documentos](sensitivity-labels.md#what-label-policies-can-do)   | Em revisão                       | Em revisão                    | Em revisão           | Em revisão               | Em revisão               |
|[Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](apply-sensitivity-label-automatically.md)                    | Visualização: distribuição para o [Office Insider](https://office.com/insider)                       | Em revisão                    | Em revisão           | Em revisão               | Sim |
|

## <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Cliente de rotulamento interno do Office e o cliente de proteção de informações do Azure

O cliente de rotulagem de rótulo do Office faz o download de rótulos de confidencialidade e definições de política de rótulo de confidencialidade dos seguintes centros de administração:

- Centro de conformidade do Microsoft 365
- Centro de segurança do Microsoft 365
- Centro de Conformidade e Segurança do Office 365

Para usar o cliente de rotulagem interno do Office, você deve ter uma ou mais [políticas de rótulo publicadas](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) para os usuários de um dos centros de administração listados.

No entanto, se os usuários tiverem um dos clientes de proteção de informações do Azure instalados ([Unificação de nome de cliente](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) ou [cliente clássico](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)), por padrão, o cliente de rotulação interno será desativado em seus aplicativos do Office. Para usar o rotulamento interno, em vez do cliente de proteção de informações do Azure para aplicativos do Office, desative ou desinstale o suplemento do Office para proteção de informações do Azure:

1. Execute uma destas opções:
    
    - **Para vários computadores:** Configurar a configuração de diretiva de grupo **usar o recurso de confidencialidade no Office para aplicar e exibir rótulos de confidencialidade** . Encontre essa configuração em **configuração do usuário/Modelos Administrativos/Microsoft Office 2016/configurações de segurança**. Implante essa configuração por meio da política de grupo ou usando o [serviço política de nuvem do Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).
    
    - **Para um único computador:** Consulte "Exibir, gerenciar e instalar suplementos nos programas do Office" para obter informações sobre como [desabilitar ou remover permanentemente](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d) o suplemento de proteção de informações do Azure em um único computador.

2. Reinicie todos os aplicativos do Office.

Quando você desabilita ou desinstala este suplemento do Office, o cliente de proteção de informações do Azure permanece instalado para que você possa continuar a rotular arquivos fora de seus aplicativos do Office. Por exemplo, usando o explorador de arquivos ou o PowerShell.

Para obter informações sobre quais recursos são compatíveis com os clientes de proteção de informações do Azure e para o cliente de rotulagem interno do Office, consulte [escolher qual rotulação de cliente usar para computadores Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) a partir da documentação de proteção de informações do Azure.

## <a name="protection-templates-and-sensitivity-labels"></a>Modelos de proteção e rótulos de confidencialidade

[Modelos de proteção](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)definidos pelo administrador, como aqueles que você define para a criptografia de mensagem do Office 365, não são visíveis em aplicativos do Office quando você está usando rotulação interna. Essa experiência simplificada reflete que não é necessário selecionar um modelo de proteção, porque as mesmas configurações estão incluídas com rótulos de confidencialidade com criptografia habilitada.

Se você precisar converter modelos de proteção existentes para rótulos, use o portal do Azure e as seguintes instruções: [para converter modelos em rótulos](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels).

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Aplicar rótulos de confidencialidade a arquivos, emails e anexos

Os usuários podem aplicar apenas um rótulo por vez para cada documento ou email.

Quando você rotula uma mensagem de email que tem anexos, os anexos não herdam o rótulo com uma exceção:

- O anexo é um documento do Office com um rótulo que não aplica criptografia e o rótulo que você aplica à mensagem de email aplica criptografia. Nesse caso, o documento do Office enviado por email herda o rótulo do email com suas configurações de criptografia.

Caso contrário: 

- Se os anexos tiverem um rótulo, eles manterão o rótulo aplicado originalmente.
- Se os anexos forem criptografados sem um rótulo, a criptografia permanecerá mas não serão rotuladas.
- Se os anexos não tiverem um rótulo, eles permanecerão sem rótulo.

## <a name="sensitivity-label-compatibility"></a>Compatibilidade de rótulo de confidencialidade

**Com aplicativos habilitados para RMS**: se você abrir um documento ou email rotulado e criptografado em um [aplicativo habilitado para RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) que não ofereça suporte a rótulos de sensibilidade, o aplicativo ainda forçará a criptografia e o gerenciamento de direitos.

**Com o cliente de proteção de informações do Azure**: você pode exibir e alterar os rótulos de sensibilidade que você aplica aos documentos e emails com o cliente de rotulagem interno do Office usando o cliente de proteção de informações do Azure e o contrário.

**Com outras versões do Office**: qualquer usuário autorizado pode abrir documentos e emails rotulados em outras versões do Office. No entanto, você só pode exibir ou alterar o rótulo nas versões compatíveis do Office ou usando o cliente de proteção de informações do Azure. As versões do aplicativo do Office com suporte estão listadas na [seção anterior](#support-for-sensitivity-label-capabilities-in-apps).

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Suporte para arquivos do SharePoint e do OneDrive protegidos por rótulos de confidencialidade

Para usar o cliente de rotulagem interno do Office com o Office na Web para documentos no OneDrive for Business ou no SharePoint Online, certifique-se de que você tenha optado pela visualização para [habilitar os rótulos de confidencialidade dos arquivos do Office no SharePoint e no onedrive](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="when-office-365-applies-content-marking-and-encryption"></a>Quando o Office 365 aplica a marcação e a criptografia de conteúdo

O Office 365 aplica a marcação e a criptografia de conteúdo com um rótulo de confidencialidade de forma diferente, dependendo do aplicativo usado.

| App | Marcação de conteúdo | Criptografia |
| --- | --- | --- |
| Word, Excel, PowerPoint em todas as plataformas | Imediatamente | Imediatamente |
| Outlook para PC e Mac | Após o Exchange Online enviar o email | Imediatamente |
| Outlook na Web, iOS e Android | Após o Exchange Online enviar o email | Após o Exchange Online enviar o email |
|

## <a name="end-user-documentation"></a>Documentação do usuário final

- [Aplicar rótulos de confidencialidade aos seus documentos e email no Office](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Problemas conhecidos ao aplicar rótulos de confidencialidade aos arquivos do Office](https://support.office.com/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)
