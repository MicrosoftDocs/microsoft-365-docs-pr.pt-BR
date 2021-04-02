---
title: Gerenciar rótulos de confidencialidade em aplicativos do Office
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
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
description: Informações para administradores de TI para gerenciar rótulos de confidencialidade em aplicativos do Office para área de trabalho, dispositivos móveis e Web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5a82eba3801509ed2e8ffb46ab32045466204fab
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498828"
---
# <a name="manage-sensitivity-labels-in-office-apps"></a>Gerenciar rótulos de confidencialidade em aplicativos do Office

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Ao [publicar](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) rótulos de confidencialidade do Centro de conformidade do Microsoft 365 ou de um centro de rotulagem equivalente, eles começarão a aparecer nos aplicativos do Office para que os usuários classifiquem e protejam os dados conforme eles são criados ou editados.

Use as informações neste artigo para ajudar você a gerenciar os rótulos de confidencialidade com êxito em aplicativos do Office. Por exemplo, identifique as versões mínimas dos aplicativos que você precisa para dar suporte à rotulagem interna; entenda as interações com o cliente de rotulagem unificada da Proteção de Informações do Azure e a compatibilidade com outros aplicativos e serviços.

## <a name="labeling-client-for-desktop-apps"></a>Cliente de rotulagem para aplicativos da área de trabalho

Para usar rótulos de confidencialidade integrados aos aplicativos da área de trabalho do Office para Windows e Mac, use uma edição de assinatura do Office. Esse cliente de rotulagem não dá suporte a edições autônomas do Office, como o Office 2016 ou o Office 2019.

Para usar rótulos de confidencialidade com essas edições autônomas do Office em computadores Windows, instale o cliente de rotulagem unificada da [Proteção de Informações do Azure](/azure/information-protection/rms-client/aip-clientv2).

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Suporte para recursos de rótulo de confidencialidade em aplicativos

Para cada recurso, as tabelas a seguir listam a versão mínima do Office necessária para dar suporte aos rótulos de confidencialidade usando a rotulagem interna. Ou, se o recurso de rótulo estiver em visualização pública ou em revisão para uma versão futura. Use o [roteiro do Microsoft 365](https://aka.ms/MIPC/Roadmap) para obter detalhes sobre as versões futuras.

As novas versões dos aplicativos do Office são disponibilizadas em diferentes momentos para diferentes canais de atualização. Para saber mais, incluindo como configurar seu canal de atualização para poder testar um novo recurso de rótulo no qual esteja interessado, confira[Visão geral dos canais de atualização para o Microsoft 365 Apps](/DeployOffice/overview-update-channels). Os novos recursos que estão em visualização privada não estão incluídos na tabela, mas você poderá experimentar essas visualizações nomeando sua organização ao [Programa de visualização privada da Proteção de Informações da Microsoft](https://aka.ms/mip-preview).

> [!NOTE]
> Os nomes dos canais de atualização para aplicativos do Office foram alterados recentemente. Por exemplo, o Canal Mensal agora é o Canal Atual, e o Office Insider agora é o Canal Beta. Para saber mais, confira [Mudanças em canais de atualização para o Microsoft 365 Apps](/deployoffice/update-channels-changes).

Office para iOS e Office para Android: os rótulos de confidencialidade estão integrados ao [Aplicativo do Office](https://www.microsoft.com/pt-BR/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/).

Os recursos adicionais estão disponíveis ao instalar o cliente de rotulagem unificada da Proteção de Informações do Azure, que é executado somente em computadores com Windows. Para mais informações, confira [Comparar os clientes de rotulamento para computadores com Windows](/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers).

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Recursos de rótulo de confidencialidade no Word, Excel e PowerPoint

Os números listados são as versão mínima do aplicativo do Office necessária para cada recurso.

|Recursos                                                                                                        |Windows |Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Aplicar, alterar ou remover rótulos manualmente](https://support.microsoft.com/pt-BR/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Sim – aceitar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Aplicar um rótulo padrão](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Sim – aceitar](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[Exigir uma justificativa para alterar um rótulo](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Sim – aceitar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Fornecer um link de ajuda para uma página de ajuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Sim – aceitar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcar o conteúdo](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Sim – aceitar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcações dinâmicas com variáveis](#dynamic-markings-with-variables)                                              | 2010+           | 16.42+     | 2.42+ | 16.0.13328+ | Em revisão |
|[Atribuir permissões agora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Sim – aceitar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Permitir que usuários atribuam permissões: <br /> – Solicitar aos usuários](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004+ | 16.35+   | Em revisão   | Em revisão         | Em revisão                                                        |
|[Atividade do usuário relacionada a rótulos de auditoria](data-classification-activity-explorer.md)                      | 2011+ | 16.43+ | 2.46+ | Em implantação: 16.0.13628+ | Sim <sup>\*</sup>                                                        |
|[Exigir que os usuários apliquem um rótulo a seus emails e documentos](#require-users-to-apply-a-label-to-their-email-and-documents)   | 2101+             | Em implantação: 16.45+         | Visualização: [Canal Beta](https://office.com/insider) | Em implantação: 16.0.13628+ | Em revisão                                            
|[Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](apply-sensitivity-label-automatically.md)                    | 2009+                                  | Em implantação: 16.44+ | Em revisão | Em revisão | [Sim – aceitar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Suporte a coautoria e salvamento automático](sensitivity-labels-coauthoring.md) de documentos rotulados e criptografados | Visualização: [Canal Atual (Visualização)](https://office.com/insider) | Visualização: [Canal Beta](https://office.com/insider) | Em revisão | Em revisão | [Sim – aceitar](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**Rodapé:**

<sup>\*</sup> Atualmente, não inclui texto justificado para remover um rótulo ou baixar o nível de classificação

### <a name="sensitivity-label-capabilities-in-outlook"></a>Recursos de rótulo de confidencialidade no Outlook

Os números listados são as versão mínima do aplicativo do Office necessária para cada recurso.

|Recursos                                                                                                        |Outlook para Windows |Outlook para Mac |Outlook no iOS |Outlook no Android |Outlook na Web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Aplicar, alterar ou remover rótulos manualmente](https://support.microsoft.com/pt-BR/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Aplicar um rótulo padrão](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Exigir uma justificativa para alterar um rótulo](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Fornecer um link de ajuda para uma página de ajuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Marcar o conteúdo](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Marcações dinâmicas com variáveis](#dynamic-markings-with-variables)                                              | Em revisão                     | Em revisão                 | Em revisão         | Em revisão           | Em revisão               |
|[Atribuir permissões agora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Permitir que usuários atribuam permissões: <br /> – Não Encaminhar](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Permitir que usuários atribuam permissões: <br /> – Criptografar Somente](encryption-sensitivity-labels.md#let-users-assign-permissions)  |2011+ | Em revisão | Em revisão  | Em revisão | Em implantação |
|[Exigir que os usuários apliquem um rótulo a seus emails e documentos](#require-users-to-apply-a-label-to-their-email-and-documents)   | Em implantação: 2101+                        | 16.43+ <sup>\*</sup>                    | Em revisão            | Em revisão                | Sim                |
|[Atividade do usuário relacionada a rótulos de auditoria](data-classification-activity-explorer.md) | 2011+ | Em revisão | Em revisão           | Em revisão               | Em revisão |
|[Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](apply-sensitivity-label-automatically.md)                    | 2009+                      | 16.44+ <sup>\*</sup>                    | Em revisão           | Em revisão               | Sim |
|

**Rodapé:**

<sup>\*</sup> Requer o [novo Outlook para Mac](https://support.microsoft.com/office/the-new-outlook-for-mac-6283be54-e74d-434e-babb-b70cefc77439)


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Cliente de rotulagem interna do Office e outras soluções de rotulagem

O cliente de rotulagem interna do Office baixa os rótulos de confidencialidade e as configurações da política de rótulo de confidencialidade dos seguintes centros de administração:

- Centro de conformidade do Microsoft 365
- Centro de segurança do Microsoft 365
- Centro de Segurança e Conformidade do Office 365

Para usar o cliente de rotulagem interna do Office, você deve ter uma ou mais [políticas de rótulo publicadas](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) para os usuários de um dos centros de administração listados, e uma [versão com suporte do Office](#support-for-sensitivity-label-capabilities-in-apps).

Se essas duas condições forem atendidas, mas você precisa desativar o cliente de rotulagem interna do Office, use a seguinte configuração da Política de Grupo:

1. Navegue até **Configuração do Usuário/Modelos Administrativos/Microsoft Office 2016/Configurações de Segurança**.

2. Defina **Usar o recurso Confidencialidade no Office para aplicar e exibir rótulos de confidencialidade** para **0**. 
 
Implemente este cenário usando a Política de Grupo ou usando o [Serviço de política de nuvem do Office](/DeployOffice/overview-office-cloud-policy-service). A configuração entra em vigor quando os aplicativos do Office forem reiniciados.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Cliente da rotulagem interna do Office e cliente da Proteção de Informações do Azure.

Se os usuários tiverem o [cliente da Proteção de Informações do Azure instalado](/azure/information-protection/rms-client/aip-clientv2), por padrão, o cliente de rotulagem incorporado está desativado nos seus aplicativos do Office. 

Para usar a rotulação interna em vez do cliente de Proteção de Informações do Azure para aplicativos do Office, recomendamos usar a configuração de Política de Grupo **Lista de suplementos gerenciados** como documentado em [Nenhum Suplemento carregado devido a configurações de política de grupo para os programas do Office 2013 e do Office 2016](https://support.microsoft.com/help/2733070/no-add-ins-loaded-due-to-group-policy-settings-for-office-2013-and-off).

Para Microsoft Word 2016, Excel 2016, PowerPoint 2016 e Outlook 2016, especifique os seguintes identificadores de programação (ProgID) para o cliente de Proteção de Informações do Azure e demarque a opção para **0: O suplemento sempre será desabilitado (bloqueado)**

|Aplicativo  |ProgID  |
|---------|---------|
|Word     |     `MSIP.WordAddin`    |
|Excel     |  `MSIP.ExcelAddin`       |
|PowerPoint     |   `MSIP.PowerPointAddin`      |
|Outlook | `MSIP.OutlookAddin` |
| | | 

Implemente este cenário usando a Política de Grupo ou usando o [Serviço de política de nuvem do Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).

> [!NOTE]
> Se você usar a configuração de Política de Grupo, **Usar o recurso Confidencialidade no Office para aplicar e exibir rótulos de confidencialidade** e defini-la como **1**, há algumas situações em que o cliente da Proteção de Informações do Azure ainda pode carregar nos aplicativos do Office. Bloquear o carregamento do suplemento em cada aplicativo impede que isso aconteça.

Como alternativa, você pode desabilitar ou remover interativamente o suplemento do Office **Proteção de Informações do Microsoft Azure** do Word, Excel, PowerPoint e Outlook. Esse método é adequado para um único computador e para testes ad hoc. Para obter instruções, confira [Visualizar, gerenciar e instalar suplementos em programas do Office](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d). 

Seja qual for o método escolhido, as alterações são efetivadas quando os aplicativos do Office são reiniciados. Ao desabilitar ou remover esse Suplemento do Office, o cliente da Proteção de Informações do Azure permanece instalado para que você possa continuar rotulando arquivos fora dos aplicativos do Office. Por exemplo, usando o Explorador de Arquivos ou o PowerShell.

Para obter informações sobre quais recursos são compatíveis com os clientes da Proteção de Informações do Azure e pelo cliente de rotulagem interna do Office, confira [Escolher solução de rotulagem do Windows](/azure/information-protection/rms-client/use-client#choose-your-windows-labeling-solution) na documentação da Proteção de Informações do Azure.

## <a name="office-file-types-supported"></a>Tipos de arquivos do Office compatíveis

Os aplicativos do Office que têm rotulagem interna para arquivos do Word, do Excel e do PowerPoint são compatíveis com o formato Open XML (como .docx e .xlsx), mas não com o formato do Microsoft Office 97-2003 (como .doc e .xls), do Open Document Format (como .odt e .ods) ou outros formatos. Quando um tipo de arquivo não for compatível com a rotulagem interna, o botão **Confidencialidade** não estará disponível no Aplicativo do Office.

O cliente de rotulagem unificada da Proteção de Informações do Azure dá suporte ao formato Open XML e ao formato do Microsoft Office 97-2003. Para saber mais, confira [Tipos de arquivo com suporte no cliente de rotulagem unificada da Proteção de Informações do Azure](/azure/information-protection/rms-client/clientv2-admin-guide-file-types) do guia administrativo do cliente.

Para ver outras soluções de rotulagem, verifique a documentação deles em busca dos tipos de arquivos com suporte.

## <a name="protection-templates-and-sensitivity-labels"></a>Modelos de proteção e rótulos de confidencialidade

Os [modelos de proteção](/azure/information-protection/configure-policy-templates) definidos pelo administrador, como os definidos para a Criptografia de Mensagens do Office 365, não estarão visíveis nos aplicativos do Office ao usar a rotulagem interna. Essa experiência simplificada reflete que não há necessidade de selecionar um modelo de proteção, pois as mesmas configurações estão incluídas com rótulos de confidencialidade que têm criptografia habilitada.

Se você precisar converter os modelos de proteção existentes nos rótulos, use o portal do Azure e as seguintes instruções: [Converter modelos em rótulos](/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels).

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Opções de IRM (Gerenciamento de Direitos de Informação) e de rótulos de confidencialidade

Os rótulos de confidencialidade configurados para aplicar criptografia removem a complexidade dos usuários para especificar suas próprias configurações de criptografia. Em muitos aplicativos do Office, essas configurações individuais de criptografia ainda podem ser configuradas manualmente pelos usuários usando as opções de IRM (Gerenciamento de Direitos de Informação). Por exemplo, para aplicativos do Windows:

- Para um documento:  **Arquivo** > **Informações** > **Proteger Documento** > **Restringir Acesso**
- para um email: Na guia **Opções** > **Criptografar** 
  
Quando os usuários inicialmente rotulam um documento ou email, eles sempre poderão sobrepor suas configurações de rótulos com suas próprias configurações de criptografia. Por exemplo:

- Um usuário aplica o rótulo **Confidencial \ Todos os Funcionários** a um documento e esse rótulo é configurado para aplicar configurações de criptografia para todos os usuários da organização. Em seguida, o usuário define manualmente as configurações do IRM para restringir o acesso a um usuário de fora da organização. O resultado final é um documento rotulado como **Confidencial \ Todos os Funcionários** e criptografado, mas os usuários de sua organização não conseguem abri-lo como esperado.

- Um usuário aplica o rótulo **Confidencial \ Somente Destinatários** a um email, e esse email está configurado para aplicar a configuração de criptografia de **Não Encaminhar**. Em seguida, o usuário define manualmente as configurações do IRM para que o email seja irrestrito. O resultado final é que o email poderá ser encaminhado pelos destinatários, apesar de ter o rótulo **Confidencial \ Somente Destinatários**.

- Um usuário aplica o rótulo **Geral** a um documento, e esse rótulo não está configurado para aplicar criptografia. Em seguida, o usuário define manualmente as configurações do IRM para restringir o acesso ao documento. O resultado final é um documento rotulado como **Geral**, mas que também aplica criptografia para que alguns usuários não possam abri-lo como esperado.

Se o documento ou email já estiver identificado, um usuário poderá fazer qualquer uma dessas ações se o conteúdo ainda não estiver criptografado, ou se eles tiverem o [direito de uso](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) Exportar ou Controle Total. 

Para uma experiência de rótulos mais consistente com relatórios significativos, forneça rótulos apropriados e diretrizes para que os usuários apliquem somente rótulos para proteger documentos. Por exemplo:

- Para casos de exceções em que os usuários devem atribuir suas próprias permissões, forneça rótulos que [permitam aos usuários atribuir suas próprias permissões](encryption-sensitivity-labels.md#let-users-assign-permissions). 

- Em vez de os usuários removerem manualmente a criptografia após selecionar um rótulo que aplica criptografia, forneça uma alternativa de subrótulo quando os usuários precisarem de um rótulo com a mesma classificação, mas sem criptografia. Como:
    - **Confidencial \ Todos os Funcionários**
    - **Confidencial \ Qualquer pessoa (sem criptografia)**

> [!NOTE]
> Se os usuários removerem manualmente a criptografia de um documento identificado que esteja armazenado no SharePoint ou no OneDrive, e você tiver [habilitado rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive](sensitivity-labels-sharepoint-onedrive-files.md), a criptografia do rótulo será automaticamente restaurada na próxima vez em que o documento for acessado ou baixado. 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Aplicar rótulos de confidencialidade a arquivos, emails e anexos

Os usuários podem aplicar apenas um rótulo por vez para cada documento ou email.

Quando você rotula uma mensagem de email que tem anexos, os anexos herdam o rótulo somente se o rótulo aplicado à mensagem de email aplicar criptografia, e se o anexo for um documento do Office ainda não criptografado. Como o rótulo herdado aplica a criptografia, o anexo se torna recentemente criptografado.

Um anexo não herda os rótulos da mensagem de email quando o rótulo aplicado à mensagem de email não aplica criptografia, ou quando o anexo já está criptografado.

Exemplos de herança de rótulos, onde o rótulo **Confidencial** aplica criptografia e o rótulo **Geral** não aplica criptografia:

- Um usuário cria uma nova mensagem de email e aplica o rótulo **Confidencial** a essa mensagem. Em seguida, eles adicionam um documento Word não rotulado ou criptografado. Como resultado da herança, o documento foi recentemente rotulado como **Confidencial** e agora tem criptografia aplicada a partir desse rótulo.

- Um usuário cria uma nova mensagem de email e aplica o rótulo **Confidencial** a essa mensagem. Em seguida, eles adicionam um documento Word rotulado como **Geral** e que não está criptografado. Como resultado da herança, o documento é rotulado novamente como **Confidencial**, e agora com criptografia aplicada a partir desse rótulo.

## <a name="sensitivity-label-compatibility"></a>Compatibilidade de rótulos de confidencialidade

**Com aplicativos habilitados para RMS** : se você abrir um documento ou email rotulado e criptografado em um [aplicativo habilitado para RMS](/azure/information-protection/requirements-applications#rms-enlightened-applications) não compatível com rótulos de confidencialidade, o aplicativo ainda aplicará criptografia e gerenciamento de direitos.

**Com o cliente de Proteção de Informações do Azure**: você pode exibir e alterar os rótulos de confidencialidade que aplica a documentos e emails com o cliente de rotulagem interna do Office usando o cliente da Proteção de Informações do Azure, e vice-versa.

**Em outras versões do Office**: qualquer usuário autorizado poderá abrir documentos e emails rotulados em outras versões do Office. No entanto, só será possível exibir ou alterar o rótulo nas versões com suporte do Office ou usando o cliente da Proteção de Informações do Azure. As versões do Aplicativo do Office com suporte estão listadas na [seção anterior](#support-for-sensitivity-label-capabilities-in-apps).

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Suporte para arquivos do SharePoint e do OneDrive protegidos por rótulos de confidencialidade

Para usar o cliente de rotulagem interna do Office com o Office na Web para documentos no SharePoint ou no OneDrive, certifique-se de ter [rótulos de confidencialidade habilitados para arquivos do Office no SharePoint e no OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="support-for-external-users-and-labeled-content"></a>Suporte para usuários externos e conteúdo rotulado

Ao rotular um documento ou um email, o rótulo é armazenado como metadados que incluem seu locatário e um GUID de rótulos. Quando um documento ou email rotulado for aberto por um Aplicativo do Office com suporte a rótulos de confidencialidade, esse metadados serão lidos e, somente se o usuário pertencer ao mesmo locatário, o rótulo será exibido no aplicativo. Por exemplo, para rotulagem interna do Word, do PowerPoint e do Excel, o nome do rótulo é exibido na barra de status. 

Isso significa que, se você compartilhar documentos com outra organização que usa nomes de rótulos diferentes, cada organização poderá aplicar e ver seu próprio rótulo aplicado ao documento. No entanto, os seguintes elementos de um rótulo aplicado ficarão visíveis para os usuários de fora da organização:

- Marcações de conteúdo. Quando um rótulo aplica um cabeçalho, rodapé ou marca d'água, eles são adicionados diretamente ao conteúdo e ficam visíveis até que alguém os modifique ou exclua.

- O nome e a descrição do modelo de proteção subjacente de um rótulo que aplicou a criptografia. Essa informação é exibida em uma barra de mensagens na parte superior do documento, fornecendo informações sobre quem está autorizado a abrir o documento e seus direitos de uso do documento.

### <a name="sharing-encrypted-documents-with-external-users"></a>Compartilhamento de documentos criptografados com usuários externos

Além de restringir o acesso aos usuários da própria organização, você poderá estender o acesso a qualquer outro usuário que tenha uma conta no Azure Active Directory. No entanto, se sua organização usa políticas de Acesso Condicional, confira a [próxima seção](#conditional-access-policies) para considerações adicionais.

Todos os aplicativos do Office e outros [aplicativos habilitados para RMS](/azure/information-protection/requirements-applications#rms-enlightened-applications) podem abrir documentos criptografados após o usuário ter se autenticado com êxito. 

Se os usuários externos não tiverem uma conta no Azure Active Directory, eles poderão se autenticar usando contas de convidado no locatário. Essas contas de convidado também podem ser usadas para acessar documentos compartilhados no SharePoint ou no OneDrive quando você tiver [habilitado rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive](sensitivity-labels-sharepoint-onedrive-files.md):

- Uma opção é você mesmo criar essas contas de convidado. Especifique qualquer endereço de email já usado por esses usuários. Por exemplo, o endereço do Gmail.
    
    A vantagem dessa opção é que você pode restringir o acesso e os direitos a usuários específicos, definindo o endereço de email nas configurações de criptografia. A desvantagem é a sobrecarga administrativa na criação da conta e na coordenação com a configuração do rótulo.

- Outra opção é usar a [integração do SharePoint e do OneDrive com o B2B do Azure AD (Visualização)](/sharepoint/sharepoint-azureb2b-integration-preview) para que as contas de convidado sejam criadas automaticamente quando seus usuários compartilharem links.
    
    A vantagem dessa opção é a sobrecarga administrativa mínima, pois as contas são criadas automaticamente e a configuração do rótulo é mais simples. Nesse cenário, selecione a opção de criptografia [Adicionar qualquer usuário autenticado](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users), pois você não saberá os endereços de email com antecedência. O lado negativo é que essa configuração não permite restringir o acesso e os direitos de uso a usuários específicos.

Os usuários externos também podem usar uma conta Microsoft para abrir documentos criptografados ao usar o Windows e o Microsoft 365 Apps [(anteriormente, aplicativos do Office 365](/deployoffice/name-change)) ou a edição autônoma do Office 2019. Mais recentemente com suporte para outras plataformas, as contas Microsoft também têm suporte para a abertura de documentos criptografados no macOS (Microsoft 365 Apps, versão 16.42+), no Android (versão 16.0.13029+) e no iOS (versão 2.42+). Por exemplo, um usuário na organização compartilha um documento criptografado com um usuário de fora da organização, e as configurações de criptografia especificam um endereço de email do Gmail para o usuário externo. Esse usuário externo pode criar sua própria conta Microsoft que usa seu endereço de email do Gmail. Em seguida, após entrar com essa conta, será possível abrir o documento e editá-lo, de acordo com as restrições de uso especificadas para eles. Para um exemplo passo a passo desse cenário, confira [Abrir e editar o documento protegido](/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document).

> [!NOTE]
> O endereço de email da conta Microsoft deve corresponder ao endereço de email especificado para restringir o acesso às configurações de criptografia.

Quando um usuário com uma conta Microsoft abre um documento criptografado dessa forma, ele cria automaticamente uma conta de convidado para o locatário se uma conta de convidado com o mesmo nome ainda não existir. Quando há a conta de convidado, ela poderá ser usada para abrir documentos no SharePoint e no OneDrive usando o Office na Web, além de abrir documentos criptografados a partir dos aplicativos do Office com suporte para área de trabalho e dispositivos móveis.

No entanto, a conta de convidado automática não é criada imediatamente nesse cenário, devido à latência de replicação. Se você especificar endereços de email pessoais como parte das configurações de criptografia dos rótulos, recomendamos que você crie contas de convidado correspondentes no Azure Active Directory. Em seguida, informe a esses usuários que eles devem usar essa conta para abrir um documento criptografado da organização.

> [!TIP]
> Como não é possível ter certeza de que usuários externos estarão usando um aplicativo cliente do Office com suporte, compartilhar links do SharePoint e do OneDrive depois de criar contas de convidado (para usuários específicos) ou usar a [integração do SharePoint e do OneDrive com o B2B do Azure AD ](/sharepoint/sharepoint-azureb2b-integration-preview)(para qualquer usuário autenticado) é um método mais confiável para dar suporte à colaboração segura com usuários externos.

### <a name="conditional-access-policies"></a>Políticas de Acesso Condicional

Se sua organização tiver implementado [Políticas de Acesso Condicional do Azure Active Directory](/azure/active-directory/conditional-access/overview), verifique a configuração dessas políticas. Se a política inclui a **Proteção de Informações do Microsoft Azure** e ela se estender a usuários externos, esses usuários externos deverão ter uma conta de convidado no locatário, mesmo que tenham uma conta do Azure AD em seu próprio locatário.

Sem essa conta de convidado, não será possível abrir o documento criptografado e uma mensagem de erro será exibida. O texto da mensagem poderá informá-los de que sua conta precisa ser adicionada como usuário externo no locatário, com a instrução incorreta nesse cenário para **Sair e entrar novamente com uma conta de usuário diferente do Azure Active Directory**.

Se você não puder criar e configurar contas de convidado no locatário para usuários externos que precisam abrir documentos criptografados por rótulos, remova a Proteção de Informações do Azure das políticas de Acesso Condicional, ou exclua os usuários externos das políticas.

Para saber mais sobre o Access Condicional e a Proteção de Informações do Azure, o serviço de criptografia usado por rótulos de sensibilidade, confira a pergunta frequente, [Vejo a Proteção de Informações do Azure listada como um aplicativo de nuvem disponível para acesso condicional. Como isso funciona?](/azure/information-protection/faqs#i-see-azure-information-protection-is-listed-as-an-available-cloud-app-for-conditional-accesshow-does-this-work)

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Quando os aplicativos do Office aplicam marcação e criptografia de conteúdo

Os aplicativos Office aplicam marcação e criptografia de conteúdo com um rótulo de confidencialidade de forma diferente, dependendo do aplicativo usado.

| Aplicativo | Marcação de conteúdo | Criptografia |
| --- | --- | --- |
| Word, Excel, PowerPoint em todas as plataformas | Imediatamente | Imediatamente |
| Outlook para PC e Mac | Após o Exchange Online enviar o email | Imediatamente |
| Outlook na Web, iOS e Android | Após o Exchange Online enviar o email | Após o Exchange Online enviar o email |
|

As soluções que aplicam rótulos de confidencialidade a arquivos fora dos aplicativos do Office fazem isso através da aplicação de metadados de rotulagem ao arquivo. Nesse cenário, a marcação de conteúdo da configuração do rótulo não é inserida no arquivo, mas a criptografia é aplicada. 

Quando esses arquivos são abertos em um aplicativo da área de trabalho do Office, as marcações de conteúdo são automaticamente aplicadas pelo cliente de rotulagem unificada da Proteção de Informações do Azure. As marcações de conteúdo não são aplicadas automaticamente ao usar a rotulagem interna para aplicativos Web, móveis ou de área de trabalho.

Os cenários que incluem a aplicação de um rótulo de confidencialidade fora dos aplicativos do Office incluem:

- O scanner, o Explorador de Arquivos e o PowerShell do cliente de rotulagem unificada da Proteção de Informações do Azure 

- Políticas de rotulagem automática para o SharePoint e o OneDrive:

- Dados rotulados e criptografados exportados do Power BI

- Microsoft Cloud App Security

Ao usar aplicativos do Office nesses cenários, um usuário com rotulagem interna pode aplicar as marcações de conteúdo do rótulo removendo ou substituindo temporariamente o rótulo atual e, em seguida, reaplicando o rótulo original.

### <a name="dynamic-markings-with-variables"></a>Marcações dinâmicas com variáveis

> [!IMPORTANT]
> Atualmente, nem todos os aplicativos, em todas as plataformas, dão suporte a marcações dinâmicas de conteúdo que você pode especificar para cabeçalhos, rodapés e marcas d'água. Para aplicativos que não dão suporte a esse recurso, aplicam-se as marcações como o texto original especificado na configuração de rótulo, em vez de resolver as variáveis.
> 
> O cliente de rotulagem unificada da Proteção de Informações do Azure dá suporte a marcações dinâmicas. Sobre a rotulagem interna do Office, confira as tabelas na seção [recursos](#support-for-sensitivity-label-capabilities-in-apps) desta página.

Ao configurar um rótulo de confidencialidade para marcações de conteúdo, você pode usar as seguintes variáveis na cadeia de texto do seu título, rodapé ou marca d'água:

| Variável | Descrição | Exemplo quando um rótulo é aplicado |
| -------- | ----------- | ------- |
| `${Item.Label}` | Nome de exibição de rótulo do rótulo aplicado| **Geral**|
| `${Item.Name}` | Nome do arquivo ou assunto do email do conteúdo que está sendo rotulado | **Sales.docx** |
| `${Item.Location}` | O caminho e o nome do arquivo do documento que está sendo rotulado, ou o assunto do email de um email que está sendo rotulado | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | Nome de exibição do usuário que está aplicando o rótulo| **Ricardo Cavalcanti** |
| `${User.PrincipalName}` | UPN (nome principal do usuário) do Azure AD do usuário que aplica o rótulo | **rcavalcanti\@contoso.com** |
| `${Event.DateTime}` | Data e hora em que o conteúdo é rotulado, no fuso horário local do usuário que aplica o rótulo | **10/8/2020 13:30** |

> [!NOTE]
> A sintaxe dessas variáveis diferencia maiúsculas de minúsculas.

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>Definir marcações visuais diferentes para o Word, o Excel, o PowerPoint e o Outlook

Como variável adicional, configure marcações visuais por tipo de aplicativo do Office usando uma instrução de variável "If.App" na cadeia de texto, e identifique o tipo de aplicativo usando os valores do **Word**, do **Excel**, do **PowerPoint** ou do **Outlook**. Você também pode abreviar esses valores, o que é necessário se você quiser especificar mais de um na mesma instrução If.App.

> [!NOTE]
> Para concluir, estão incluídas instruções para o Outlook, embora atualmente com suporte apenas para o cliente de rotulagem unificada da Proteção de Informações do Azure.

Use a seguinte sintaxe:

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

Assim como ocorre com as outras marcações visuais dinâmicas, a sintaxe diferencia maiúsculas de minúsculas.

Exemplos:

- **Definir texto de cabeçalho somente para documentos do Word:**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    Somente nos cabeçalhos de documentos do Word, o rótulo aplica o texto de cabeçalho "Este documento do Word diferencia maiúsculas de minúsculas". Nenhum texto de cabeçalho é aplicado a outros aplicativos do Office.

- **Definir texto de rodapé para o Word, o Excel e o Outlook, e um texto de rodapé diferente para o PowerPoint:**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    No Word, no Excel e no Outlook, o rótulo aplica o texto de rodapé "Este conteúdo é confidencial". No PowerPoint, o rótulo aplica o texto de rodapé "Esta apresentação é confidencial".

- **Definir um texto específico de marca d'água para o Word e o PowerPoint e, em seguida, um texto de marca d'água para o Word, o Excel e o PowerPoint:**

    `${If.App.WP}This content is ${If.End}Confidential`

    No Word e no PowerPoint, o rótulo aplica o texto de marca d'água "Este conteúdo é Confidencial". No Excel, o rótulo aplica o texto de marca d'água "Confidencial". No Outlook, o rótulo não aplica texto de marca d'água, pois não há suporte para marcas d'água como marcações visuais no Outlook.

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>Exigir que os usuários apliquem um rótulo a seus emails e documentos

> [!IMPORTANT]
> Também conhecido como rotulagem obrigatória, nem todos os aplicativos, em todas as plataformas, dão suporte à política de **Exigir que os usuários apliquem um rótulo a seus emails e documentos**.
> 
> O [cliente de rotulagem unificada da Proteção de Informações do Azure](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) dá suporte para rotulagem obrigatória e rotulagem interna aos aplicativos Office, confira as tabelas na seção [recursos](#support-for-sensitivity-label-capabilities-in-apps) desta página.

Quando essa configuração de política estiver selecionada, os usuários atribuídos à política deverão selecionar e aplicar um rótulo de confidencialidade nos seguintes cenários:

- Para o cliente de rotulagem unificada da Proteção de Informações do Azure:
    - Para documentos (Word, Excel, PowerPoint): quando um documento sem rótulo for salvo ou os usuários fecharem o documento.
    - Para emails (Outlook): no momento em que os usuários enviarem uma mensagem sem rótulo.

- Para rotulagem interna nos aplicativos do Office:
    - Para documentos (Word, Excel, PowerPoint): quando um documento sem rótulo for aberto ou salvo.
    - Para emails (Outlook): no momento em que os usuários enviarem uma mensagem de email sem rótulo.

Informações adicionais sobre a rotulagem interna:

- Quando os usuários são solicitados a adicionar um rótulo de confidencialidade ao abrir um documento sem rótulo, eles podem adicionar um rótulo ou optar por abrir o documento no modo somente leitura.

- Quando o rótulo obrigatório estiver em vigor, os usuários não poderão remover rótulos de confidencialidade dos documentos, mas poderão alterar um rótulo existente.

Para obter diretrizes sobre quando usar essa configuração, confira as informações sobre [configurações de política](sensitivity-labels.md#what-label-policies-can-do).

> [!NOTE]
> Se você usar a configuração de política de rótulo padrão para documentos e emails, além da rotulagem obrigatória: 
>
> O rótulo padrão sempre tem prioridade sobre a rotulagem obrigatória. No entanto, para documentos, o cliente de rotulagem unificada da Proteção de Informações do Azure aplica o rótulo padrão a todos os documentos não rotulados, enquanto que a rotulagem interna aplica o rótulo padrão aos novos documentos e não aos existentes que não estejam rotulados. Essa diferença de comportamento significa que ao usar a rotulagem obrigatória com a configuração padrão de rotulagem, os usuários serão solicitados a aplicar um rótulo de confidencialidade com mais frequência ao usar a rotulagem interna do que quando se usa o cliente de rotulagem unificada da Proteção de Informações do Azure.

## <a name="end-user-documentation"></a>Documentação do usuário final

- [Aplicar rótulos de confidencialidade aos seus documentos e email no Office](https://support.microsoft.com/pt-BR/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Problemas conhecidos ao aplicar rótulos de confidencialidade aos arquivos do Office](https://support.microsoft.com/pt-BR/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)