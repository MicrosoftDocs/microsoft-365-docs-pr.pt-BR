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
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informações para administradores de IT gerenciarem rótulos de sensibilidade em aplicativos do Office para área de trabalho, dispositivos móveis e a Web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 959fb0371ab50d4132cacbae38d979a9a75d2aab
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261352"
---
# <a name="manage-sensitivity-labels-in-office-apps"></a>Gerenciar rótulos de confidencialidade em aplicativos do Office

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

Quando você [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) publica rótulos de sensibilidade do centro de conformidade do Microsoft 365 ou centro de rotulagem equivalente, eles começam a aparecer nos aplicativos do Office para que os usuários classifiquem e protejam os dados à medida que são criados ou editados.

Use as informações neste artigo para ajudá-lo a gerenciar rótulos de sensibilidade com êxito em aplicativos do Office. Por exemplo, identifique as versões mínimas de aplicativos que você precisa para dar suporte à rotulagem integrado e entenda as interações com o cliente de rotulagem unificada da Proteção de Informações do Azure e a compatibilidade com outros aplicativos e serviços.

## <a name="labeling-client-for-desktop-apps"></a>Cliente de rotulagem para aplicativos da área de trabalho

Para usar rótulos de sensibilidade integrados aos aplicativos da área de trabalho do Office para Windows e Mac, você deve usar uma edição de assinatura do Office. Esse cliente de rotulagem não dá suporte a edições autônomas do Office, como o Office 2016 ou o Office 2019.

Para usar rótulos de sensibilidade com essas edições autônomas do Office em computadores Windows, instale o cliente de rotulagem unificada da Proteção de Informações do [Azure.](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Suporte para recursos de rótulo de sensibilidade em aplicativos

Para cada recurso, as tabelas a seguir listam a versão mínima do Office que você precisa para dar suporte a rótulos de sensibilidade usando rotulagem. Ou, se o recurso de rótulo estiver em visualização pública ou em revisão para uma versão futura. Use o [mapa do Microsoft 365](https://aka.ms/MIPC/Roadmap) para obter detalhes sobre versões futuras.

Novas versões de aplicativos do Office são disponibilizadas em momentos diferentes para diferentes canais de atualização. Para obter mais informações, incluindo como configurar seu canal de atualização para que você possa testar um novo recurso de rotulagem de seu interesse, consulte Visão geral dos canais de atualização para Aplicativos do [Microsoft 365.](https://docs.microsoft.com/DeployOffice/overview-update-channels) Novos recursos que estão na visualização privada não estão incluídos na tabela, mas você pode ser capaz de ingressar nessas visualizações ao nomear sua organização para o programa de visualização privada de Proteção de Informações da [Microsoft.](https://aka.ms/mip-preview)

> [!NOTE]
> Os nomes dos canais de atualização para aplicativos do Office foram alterados recentemente. Por exemplo, o Canal Mensal agora é o Canal Atual e o Office Insider agora é o Canal Beta. Para obter mais informações, consulte [Alterações nos canais de atualização dos Aplicativos do Microsoft 365.](https://docs.microsoft.com/deployoffice/update-channels-changes)

Office para iOS e Office para Android: os rótulos de sensibilidade são integrados ao [aplicativo do Office.](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/)

Recursos adicionais estão disponíveis quando você instala o cliente de rotulagem unificada da Proteção de Informações do Azure, que é executado somente em computadores Windows. Para obter esses detalhes, [consulte Comparar os clientes de rotulagem para computadores Windows.](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Recursos de rótulo de sensibilidade no Word, Excel e PowerPoint

Os números listados são a versão mínima do aplicativo do Office necessária para cada recurso.

|Funcionalidade                                                                                                        |Windows |Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Aplicar, alterar ou remover rótulo manualmente](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16,21+     | 2.21+ | 16.0.11231+ | [Sim - aceitação](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Aplicar um rótulo padrão](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16,21+     | 2.21+ | 16.0.11231+ | [Sim - aceitação](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[Exigir uma justificativa para alterar um rótulo](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16,21+     | 2.21+ | 16.0.11231+ | [Sim - aceitação](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Fornecer um link de ajuda para uma página de ajuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16,21+     | 2.21+ | 16.0.11231+ | [Sim - aceitação](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcar o conteúdo](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16,21+     | 2.21+ | 16.0.11231+ | [Sim - aceitação](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcações dinâmicas com variáveis](#dynamic-markings-with-variables)                                              | 2010+           | 16,42+     | 2,42+ | 16.0.13328+ | Sob revisão |
|[Atribuir permissões agora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16,21+     | 2.21+ | 16.0.11231+ | [Sim - aceitação](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Permitir que usuários atribuam permissões](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004+ | 16,35+   | Sob revisão   | Sob revisão         | Sob revisão                                                        |
|[Começar a trabalhar com a classificação de dados](data-classification-overview.md) e enviar dados para administradores                      | 2011+ | 16,43+ | Visualização: [Canal Atual (Visualização)](https://office.com/insider) | Visualização: [Canal Atual (Visualização)](https://office.com/insider) | Sim <sup>\*</sup>                                                        |
|[Exigir que os usuários apliquem um rótulo a seus emails e documentos](#require-users-to-apply-a-label-to-their-email-and-documents)   | Visualização: [Canal Atual (Visualização)](https://office.com/insider)             | Visualização: [Canal Atual (Visualização)](https://office.com/insider)         | Sob revisão   | Implantação: 16.0.13628+ | Sob revisão                                            
|[Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](apply-sensitivity-label-automatically.md)                    | 2009+                                  | Implantação: 16,44+ | Sob revisão | Sob revisão | [Sim - aceitação](sensitivity-labels-sharepoint-onedrive-files.md) |
|Suporte [ao AutoSave](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) e [coautor](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) em documentos rotulados e criptografados | Sob revisão | Sob revisão | Sob revisão | Sob revisão | [Sim - aceitação](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**Nota de rodapé:**

<sup>\*</sup> Atualmente, não inclui texto de justificativa para remover um rótulo ou diminuir o nível de classificação

### <a name="sensitivity-label-capabilities-in-outlook"></a>Recursos de rótulo de sensibilidade no Outlook

Os números listados são a versão mínima do aplicativo do Office necessária para cada recurso.

|Funcionalidade                                                                                                        |Outlook para Windows |Outlook para Mac |Outlook no iOS |Outlook no Android |Outlook na Web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Aplicar, alterar ou remover rótulo manualmente](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Aplicar um rótulo padrão](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Exigir uma justificativa para alterar um rótulo](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Fornecer um link de ajuda para uma página de ajuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Marcar o conteúdo](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Marcações dinâmicas com variáveis](#dynamic-markings-with-variables)                                              | Sob revisão                     | Sob revisão                 | Sob revisão         | Sob revisão           | Sob revisão               |
|[Atribuir permissões agora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Permitir que usuários atribuam permissões](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Exigir que os usuários apliquem um rótulo a seus emails e documentos](#require-users-to-apply-a-label-to-their-email-and-documents)   | Visualização: [Canal Atual (Visualização)](https://office.com/insider)                        | 16,43+                     | Sob revisão            | Sob revisão                | Sim                |
|[Começar a trabalhar com a classificação de dados](data-classification-overview.md) e enviar dados para administradores                      | 2011+ | Sob revisão | Sob revisão           | Sob revisão               | Sob revisão |
|[Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](apply-sensitivity-label-automatically.md)                    | 2009+                      | 16,44+                    | Sob revisão           | Sob revisão               | Sim |
|


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Cliente de rotulagem integrado do Office e outras soluções de rotulagem

O cliente de rotulagem interna do Office baixa rótulos de sensibilidade e configurações de política de rótulo de sensibilidade dos seguintes centros de administração:

- Centro de conformidade do Microsoft 365
- Centro de segurança do Microsoft 365
- Centro de Segurança e Conformidade do Office 365

Para usar o cliente de rotulagem interna do [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) Office, você deve ter uma ou mais políticas de rótulo publicadas para usuários de um dos centros de administração listados e uma versão com suporte [do Office.](#support-for-sensitivity-label-capabilities-in-apps)

Se ambas as condições são atendidas, mas você precisa desativar o cliente de rotulagem interna do Office, use a seguinte configuração de Política de Grupo:

1. Navegue **até Configuração do Usuário/Modelos Administrativos/Microsoft Office 2016/Configurações de Segurança.**

2. Set **Use the Sensitivity feature in Office to apply and view sensitivity labels** to **0**. 
 
Implante essa configuração usando a Política de Grupo ou o serviço de política [de nuvem do Office.](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service) A configuração entra em vigor quando os aplicativos do Office são reiniciados.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Cliente de rotulagem integrado do Office e o cliente da Proteção de Informações do Azure

Se os usuários têm um dos clientes da Proteção de Informações do Azure[instalados](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) (cliente de rotulagem unificada ou cliente [clássico),](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)por padrão, o cliente de rotulagem interna é desligado em seus aplicativos do Office. 

Para usar a rotulagem interna em vez do cliente da Proteção de Informações do Azure para aplicativos do Office, use as instruções da seção anterior, mas de acordo com a configuração de Política de Grupo. Use o recurso Sensibilidade no **Office** para aplicar e exibir rótulos de sensibilidade como **1.** 

Como alternativa, desabilite ou remova o Complemento do Office, a Proteção **de Informações do Azure.** Esse método é adequado para um único computador e testes ad hoc. Para obter instruções, [confira Exibir, gerenciar e instalar os complementos em programas do Office.](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d) 

Quando você desabilita ou remove esse Complemento do Office, o cliente da Proteção de Informações do Azure permanece instalado para que você possa continuar rotular arquivos fora de seus aplicativos do Office. Por exemplo, usando o Explorador de Arquivos ou o PowerShell.

Para saber mais sobre quais recursos são suportados pelos clientes da Proteção de Informações do Azure e o cliente de rotulagem integrado do Office, confira Escolher qual cliente de rotulagem usar para computadores [Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) na documentação da Proteção de Informações do Azure.

## <a name="office-file-types-supported"></a>Tipos de arquivo do Office com suporte

Os aplicativos do Office que têm rótulos integrados para arquivos do Word, Excel e PowerPoint são suportados no formato Open XML (como .docx e .xlsx), mas não no formato Microsoft Office 97-2003 (como .doc e .xls). Quando um tipo de arquivo não tem suporte  para rotulagem integrado, o botão Confidencialidade não está disponível no aplicativo do Office.

O cliente de rotulagem unificada da Proteção de Informações do Azure dá suporte aos formatos Open XML e Microsoft Office 97-2003. Para saber mais, confira Tipos de arquivo suportados pelo cliente de rotulagem unificada da Proteção de Informações do [Azure](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-file-types) no guia de administração desse cliente.

Para outras soluções de rotulagem, verifique sua documentação para tipos de arquivo suportados.

## <a name="protection-templates-and-sensitivity-labels"></a>Modelos de proteção e rótulos de sensibilidade

Os modelos de proteção definidos pelo administrador, como aqueles que você define para a Criptografia de Mensagens do Office 365, não são visíveis nos [aplicativos](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)do Office quando você usa a rotulagem. Essa experiência simplificada reflete que não há necessidade de selecionar um modelo de proteção, pois as mesmas configurações são incluídas com rótulos de sensibilidade com criptografia habilitada.

Se você precisar converter modelos de proteção existentes em rótulos, use o portal do Azure e as seguintes instruções: para converter modelos [em rótulos.](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels)

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Opções de Gerenciamento de Direitos de Informação (IRM) e rótulos de sensibilidade

Os rótulos de sensibilidade que você configura para aplicar criptografia removem a complexidade dos usuários para especificar suas próprias configurações de criptografia. Em muitos aplicativos do Office, essas configurações de criptografia individuais ainda podem ser configuradas manualmente pelos usuários usando opções de Gerenciamento de Direitos de Informação (IRM). Por exemplo, para aplicativos do Windows:

- Para um documento: Informações **do arquivo**  >    >  **proteger o acesso** restrito do  >  **documento**
- para um email: na guia **Opções >** **Criptografar** 
  
Quando os usuários rotulam inicialmente um documento ou email, eles sempre podem substituir as definições de configuração do rótulo com suas próprias configurações de criptografia. Por exemplo:

- Um usuário aplica o rótulo **Confidencial \ Todos** os Funcionários a um documento e esse rótulo é configurado para aplicar configurações de criptografia para todos os usuários na organização. Em seguida, esse usuário define manualmente as configurações do IRM para restringir o acesso a um usuário fora da sua organização. O resultado final é um documento rotulado como **Confidencial \** Todos os Funcionários e criptografado, mas os usuários em sua organização não podem abri-lo conforme o esperado.

- Um usuário aplica o rótulo **Confidencial \ Destinatários Somente** a um email e esse email é configurado para aplicar a configuração de criptografia de Não **Encaminhar.** Em seguida, esse usuário define manualmente as configurações do IRM para que o email seja irrestrito. O resultado final é que o email pode ser encaminhado por destinatários, apesar de ter o rótulo **Confidencial \ Somente Destinatários.**

- Um usuário aplica o **rótulo Geral** a um documento, e esse rótulo não está configurado para aplicar criptografia. Em seguida, esse usuário define manualmente as configurações do IRM para restringir o acesso ao documento. O resultado final é um documento  rotulado como Geral, mas que também aplica criptografia para que alguns usuários não possam abri-la conforme o esperado.

Se o documento ou email já estiver rotulado, um usuário poderá fazer qualquer uma dessas ações se o conteúdo ainda não estiver criptografado ou tiver o direito de uso [Exportar](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) ou Controle Total. 

Para obter uma experiência de rótulo mais consistente com relatórios significativos, forneça rótulos e diretrizes apropriados para que os usuários apliquem apenas rótulos para proteger documentos. Por exemplo:

- Para casos de exceção em que os usuários devem atribuir suas próprias permissões, forneça rótulos que permitem que os usuários [atribuam suas próprias permissões.](encryption-sensitivity-labels.md#let-users-assign-permissions) 

- Em vez de remover a criptografia manualmente após selecionar um rótulo que aplica criptografia, forneça um sub-rótulo alternativo quando os usuários precisam de um rótulo com a mesma classificação, mas sem criptografia. Como:
    - **Confidencial \ Todos os Funcionários**
    - **Confidencial \ Qualquer Pessoa (sem criptografia)**

> [!NOTE]
> Se os usuários removerem manualmente a criptografia de um documento rotulado armazenado no SharePoint ou no OneDrive e você tiver habilitado os rótulos de sensibilidade para arquivos do Office no SharePoint e no [OneDrive,](sensitivity-labels-sharepoint-onedrive-files.md)a criptografia de rótulo será restaurada automaticamente na próxima vez que o documento for acessado ou baixado. 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Aplicar rótulos de sensibilidade a arquivos, emails e anexos

Os usuários podem aplicar apenas um rótulo por vez para cada documento ou email.

Quando você rotula uma mensagem de email com anexos, os anexos herdam o rótulo somente se o rótulo que você aplicar à mensagem de email aplicar criptografia e o anexo for um documento do Office ainda não estiver criptografado. Como o rótulo herdado aplica criptografia, o anexo se torna recentemente criptografado.

Um anexo não herda os rótulos da mensagem de email quando o rótulo aplicado à mensagem de email não aplica criptografia ou o anexo já está criptografado.

Exemplos de herança de rótulo, em que o rótulo **Confidencial** aplica criptografia e o rótulo **Geral** não aplica criptografia:

- Um usuário cria uma nova mensagem de email e aplica o **rótulo Confidencial** a essa mensagem. Em seguida, eles adicionam um documento do Word que não está rotulado ou criptografado. Como resultado da herança, o documento é recentemente rotulado como **Confidencial** e agora tem criptografia aplicada a partir desse rótulo.

- Um usuário cria uma nova mensagem de email e aplica o **rótulo Confidencial** a essa mensagem. Em seguida, eles adicionam um documento do Word rotulado como **Geral** e esse arquivo não é criptografado. Como resultado da herança, o documento é  rotulado como Confidencial e agora tem a criptografia aplicada a partir desse rótulo.

## <a name="sensitivity-label-compatibility"></a>Compatibilidade de rótulos de sensibilidade

Com aplicativos avançados do **RMS:** se você abrir um documento ou email rotulado e criptografado em um aplicativo com a tecnologia [RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) que não dá suporte a rótulos de sensibilidade, o aplicativo ainda impõe o gerenciamento de criptografia e direitos.

Com o cliente de Proteção de Informações do **Azure:** você pode exibir e alterar os rótulos de sensibilidade aplicados a documentos e emails com o cliente de rotulagem integrado do Office usando o cliente de Proteção de Informações do Azure e o contrário.

**Com outras versões do Office:** qualquer usuário autorizado pode abrir documentos rotulados e emails em outras versões do Office. No entanto, você só pode exibir ou alterar o rótulo em versões do Office com suporte ou usando o cliente de Proteção de Informações do Azure. As versões de aplicativos do Office com suporte estão listadas na [seção anterior.](#support-for-sensitivity-label-capabilities-in-apps)

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Suporte para arquivos do SharePoint e do OneDrive protegidos por rótulos de sensibilidade

Para usar o cliente de rotulagem interna do Office com o Office na Web para documentos no SharePoint ou no OneDrive, certifique-se de ter habilitado os rótulos de sensibilidade para arquivos do Office no SharePoint e [no OneDrive.](sensitivity-labels-sharepoint-onedrive-files.md)

## <a name="support-for-external-users-and-labeled-content"></a>Suporte para usuários externos e conteúdo rotulado

Quando você rotula um documento ou email, o rótulo é armazenado como metadados que incluem seu locatário e um GUID de rótulo. Quando um documento ou email rotulado é aberto por um aplicativo do Office que dá suporte a rótulos de sensibilidade, esse metadados são lidos e somente se o usuário pertence ao mesmo locatário, o rótulo é exibido em seu aplicativo. Por exemplo, para rotulagem integrado para Word, PowerPoint e Excel, o nome do rótulo é exibido na barra de status. 

Isso significa que, se você compartilhar documentos com outra organização que usa nomes de rótulos diferentes, cada organização poderá aplicar e ver seu próprio rótulo aplicado ao documento. No entanto, os seguintes elementos de um rótulo aplicado são visíveis para usuários de fora da sua organização:

- Marcações de conteúdo. Quando um rótulo aplica um título, rodapé ou marca d'água, eles são adicionados diretamente ao conteúdo e permanecem visíveis até que alguém os modifica ou exclua.

- O nome e a descrição do modelo de proteção subjacente de um rótulo que aplicou criptografia. Essas informações são exibidas em uma barra de mensagens na parte superior do documento, para fornecer informações sobre quem está autorizado a abrir o documento e seus direitos de uso para esse documento.

### <a name="sharing-encrypted-documents-with-external-users"></a>Compartilhar documentos criptografados com usuários externos

Além de restringir o acesso a usuários em sua própria organização, você pode estender o acesso a qualquer outro usuário que tenha uma conta no Azure Active Directory. No entanto, se sua organização usa políticas de Acesso Condicional, consulte a [próxima seção para](#conditional-access-policies) obter considerações adicionais.

Todos os aplicativos do Office e [outros aplicativos com](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) autenticação rmS podem abrir documentos criptografados após a autenticação bem-sucedida do usuário. 

Se os usuários externos não têm uma conta no Azure Active Directory, eles podem autenticar usando contas de convidado em seu locatário. Essas contas de convidado também podem ser usadas para acessar documentos compartilhados no SharePoint ou no OneDrive quando você habilitar rótulos de sensibilidade para arquivos do Office no SharePoint e [no OneDrive:](sensitivity-labels-sharepoint-onedrive-files.md)

- Uma opção é criar essas contas de convidado por conta própria. Você pode especificar qualquer endereço de email que esses usuários já usam. Por exemplo, seu endereço do Gmail.
    
    A vantagem dessa opção é que você pode restringir o acesso e os direitos a usuários específicos especificando seu endereço de email nas configurações de criptografia. A desvantagem é a sobrecarga administrativa para a criação e coordenação da conta com a configuração de rótulos.

- Outra opção é usar a integração do SharePoint e do OneDrive com o [Azure AD B2B (Visualização)](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) para que as contas de convidado sejam criadas automaticamente quando os usuários compartilharem links.
    
    A vantagem dessa opção é a sobrecarga administrativa mínima porque as contas são criadas automaticamente e a configuração de rótulo mais simples. Para esse cenário, você deve [](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users) selecionar a opção de criptografia Adicionar qualquer usuário autenticado porque não conhecerá os endereços de email antecipadamente. A desvantagem é que essa configuração não permite que você restrinja os direitos de acesso e uso a usuários específicos.

Os usuários externos também podem usar uma conta da Microsoft para documentos criptografados quando usam o Microsoft 365 Apps (anteriormente aplicativos do[Office 365)](https://docs.microsoft.com/deployoffice/name-change)no Windows e com suporte recente no macOS (versão 16.42+), Android (versão 16.0.13029+) e iOS (versão 2.42+). Por exemplo, alguém compartilha um documento criptografado com ela e as configurações de criptografia especificam seu endereço de email do Gmail. Esse usuário pode criar sua própria conta da Microsoft que usa seu endereço de email do Gmail. Em seguida, depois de entrar com essa conta, eles poderão abrir o documento e editá-lo, de acordo com as restrições de uso especificadas para esse usuário. Para ver um exemplo passo a passo desse cenário, consulte [Abrindo e editando o documento protegido.](https://docs.microsoft.com/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document)

> [!NOTE]
> O endereço de email da conta da Microsoft deve corresponder ao endereço de email especificado para restringir o acesso às configurações de criptografia.

Quando um usuário com uma conta da Microsoft abre um documento criptografado dessa forma, ele cria automaticamente uma conta de convidado para o locatário se uma conta de convidado com o mesmo nome ainda não existir. Quando a conta de convidado existe, ela pode ser usada para abrir documentos no SharePoint e no OneDrive usando um navegador (Office na Web), além de abrir documentos criptografados do aplicativo da área de trabalho do Windows. 

No entanto, a conta de convidado automática não é criada imediatamente nesse cenário, devido à latência de replicação. Se você especificar endereços de email pessoais como parte das configurações de criptografia de rótulo, recomendamos criar contas de convidado correspondentes no Azure Active Directory. Em seguida, avise esses usuários que eles devem usar essa conta para abrir um documento criptografado da sua organização.

> [!TIP]
> Como você não pode ter certeza de que usuários externos usarão um aplicativo cliente do Office com suporte, compartilhar links do SharePoint e do OneDrive depois de criar contas de convidado (para usuários específicos) ou quando você usar a integração do SharePoint e do OneDrive com o [Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) (para qualquer usuário autenticado) é um método mais confiável para dar suporte à colaboração segura com usuários externos.

### <a name="conditional-access-policies"></a>Políticas de Acesso Condicional

Se sua organização implementou políticas de Acesso Condicional do [Azure Active Directory,](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)verifique a configuração dessas políticas. Se as políticas incluem a Proteção de Informações do Azure e a política se estende para usuários externos, esses usuários externos devem ter uma conta de convidado em seu locatário, mesmo que tenham uma conta do Azure AD em seu próprio locatário.

Sem essa conta de convidado, eles não podem abrir o documento criptografado e ver uma mensagem de erro. O texto da mensagem pode informá-los de que sua conta precisa ser adicionada como um usuário externo no locatário, com a instrução incorreta para este cenário de sair e entrar novamente com uma conta de usuário diferente do **Azure Active Directory.**

Se não for possível criar e configurar contas de convidado em seu locatário para usuários externos que precisam abrir documentos criptografados por seus rótulos, você deve remover a Proteção de Informações do Azure das políticas de Acesso Condicional ou excluir usuários externos das políticas.

Para obter mais informações sobre o Acesso Condicional e a Proteção de Informações do Azure, o serviço de criptografia usado por rótulos de sensibilidade, consulte a pergunta frequente, vejo que a Proteção de Informações do [Azure](https://docs.microsoft.com/azure/information-protection/faqs#i-see-azure-information-protection-is-listed-as-an-available-cloud-app-for-conditional-accesshow-does-this-work) está listada como um aplicativo de nuvem disponível para acesso condicional— como isso funciona?

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Quando os aplicativos do Office aplicam marcação de conteúdo e criptografia

Os aplicativos do Office aplicam a marcação de conteúdo e a criptografia com um rótulo de sensibilidade de maneira diferente, dependendo do aplicativo usado.

| App | Marcação de conteúdo | Criptografia |
| --- | --- | --- |
| Word, Excel, PowerPoint em todas as plataformas | Imediatamente | Imediatamente |
| Outlook para PC e Mac | Depois que o Exchange Online envia o email | Imediatamente |
| Outlook na Web, iOS e Android | Depois que o Exchange Online envia o email | Depois que o Exchange Online envia o email |
|

As soluções que aplicam rótulos de confidencialidade a arquivos fora dos aplicativos do Office fazem isso aplicando metadados de rotulagem ao arquivo. Nesse cenário, a marcação de conteúdo da configuração do rótulo não é inserida no arquivo, mas a criptografia é aplicada. 

Quando esses arquivos são abertos em um aplicativo da área de trabalho do Office, as marcações de conteúdo são aplicadas automaticamente pelo cliente de rotulagem unificada da Proteção de Informações do Azure. As marcações de conteúdo não são aplicadas automaticamente quando você usa rotulagem interna para aplicativos da Web, móveis ou da área de trabalho.

Cenários que incluem a aplicação de um rótulo de sensibilidade fora dos aplicativos do Office incluem:

- O scanner, o Explorador de Arquivos e o PowerShell do cliente de rotulagem unificada da Proteção de Informações do Azure 

- Políticas de rotulagem automática para o SharePoint e o OneDrive

- Dados rotulados e criptografados exportados do Power BI

- Microsoft Cloud App Security

Para esses cenários, usando seus aplicativos do Office, um usuário com rotulagem interna pode aplicar as marcações de conteúdo do rótulo removendo ou substituindo temporariamente o rótulo atual e, em seguida, aplicando o rótulo original.

### <a name="dynamic-markings-with-variables"></a>Marcações dinâmicas com variáveis

> [!IMPORTANT]
> Atualmente, nem todos os aplicativos em todas as plataformas suportam marcações de conteúdo dinâmico que você pode especificar para seus títulos, rodapés e marcas d'água. Para aplicativos que não suportam esse recurso, eles aplicam as marcações como o texto original especificado na configuração do rótulo, em vez de resolver as variáveis.
> 
> O cliente de rotulagem unificada da Proteção de Informações do Azure oferece suporte a marcações dinâmicas. Para rotular o Office, confira as tabelas na seção [recursos](#support-for-sensitivity-label-capabilities-in-apps) desta página.

Ao configurar um rótulo de sensibilidade para marcações de conteúdo, você pode usar as seguintes variáveis na cadeia de caracteres de texto para seu título, rodapé ou marca d'água:

| Variável | Descrição | Exemplo de quando o rótulo foi aplicado |
| -------- | ----------- | ------- |
| `${Item.Label}` | Nome de exibição do rótulo aplicado| **Geral**|
| `${Item.Name}` | Nome do arquivo ou assunto do email do conteúdo que está sendo rotulado | **Sales.docx** |
| `${Item.Location}` | Caminho e nome de arquivo do documento que está sendo rotulado ou o assunto do email de um email que está sendo rotulado | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | Nome de exibição do usuário aplicando o rótulo| **Ricardo Dias** |
| `${User.PrincipalName}` | Nome UPN do usuário do Azure AD do usuário que está aplicando o rótulo | **rsimone \@ contoso.com** |
| `${Event.DateTime}` | Data e hora em que o conteúdo é rotulado, no fuso horário local do usuário que está aplicando o rótulo | **10/8/2020 13:30** |

> [!NOTE]
> A sintaxe para essas variáveis faz a resiência entre minúsculas.

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>Definindo marcações visuais diferentes para Word, Excel, PowerPoint e Outlook

Como uma variável adicional, você pode configurar marcações visuais por tipo de aplicativo do Office usando uma instrução de variável "If.App" na cadeia de caracteres de texto e identificar o tipo de aplicativo usando os valores **Word**, **Excel**, **PowerPoint** ou **Outlook**. Você também pode abreviar esses valores, o que é necessário se você quiser especificar mais de um na mesma instrução If.App.

> [!NOTE]
> Para completar, as instruções para o Outlook estão incluídas, embora atualmente só tenham suporte do cliente de rotulagem unificada da Proteção de Informações do Azure.

Use a seguinte sintaxe:

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

Assim como acontece com as outras marcações visuais dinâmicas, a sintaxe faz a intermediação por minúsculas.

Exemplos:

- **De definir o texto do header somente para documentos do Word:**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    Somente nos headers de documento do Word, o rótulo aplica o texto do header "Este documento do Word é sensível". Nenhum texto de header é aplicado a outros aplicativos do Office.

- **Definir texto de rodapé para Word, Excel e Outlook e texto de rodapé diferente para o PowerPoint:**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    No Word, Excel e Outlook, o rótulo aplica o texto do rodapé "Este conteúdo é confidencial". No PowerPoint, o rótulo aplica o texto do rodapé "Esta apresentação é confidencial".

- **Definir texto de marca d'água específico para Word e PowerPoint e, em seguida, texto de marca d'água para Word, Excel e PowerPoint:**

    `${If.App.WP}This content is ${If.End}Confidential`

    No Word e no PowerPoint, o rótulo aplica o texto da marca d'água "Este conteúdo é confidencial". No Excel, o rótulo aplica o texto da marca d'água "Confidencial". No Outlook, o rótulo não aplica nenhum texto de marca d'água porque não há suporte para marcas d'água como marcações visuais no Outlook.

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>Exigir que os usuários apliquem um rótulo a seus emails e documentos

> [!IMPORTANT]
> Também conhecido como rotulagem obrigatória, nem todos os aplicativos em todas as plataformas atualmente suportam a configuração de política de Exigir que os usuários apliquem um rótulo **a seus emails e documentos.**
> 
> O cliente de rotulagem unificada da Proteção de Informações do [Azure](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app) dá suporte [](#support-for-sensitivity-label-capabilities-in-apps) à rotulagem obrigatória e à rotulagem criada nos aplicativos do Office, consulte as tabelas na seção recursos nesta página.

Quando essa configuração de política é selecionada, os usuários atribuídos à política devem selecionar e aplicar um rótulo de sensibilidade nos seguintes cenários:

- Para o cliente de rotulagem unificada da Proteção de Informações do Azure:
    - Para documentos (Word, Excel, PowerPoint): quando um documento não rotulado é salvo ou os usuários fecham o documento.
    - Para emails (Outlook): no momento em que os usuários enviam uma mensagem não rotulada.

- Para rotular os aplicativos do Office integrados:
    - Para documentos (Word, Excel, PowerPoint): quando um documento não rotulado é aberto ou salvo.
    - Para emails (Outlook): no momento em que os usuários enviam uma mensagem de email não rotulada.

Informações adicionais para rotulagem embutida:

- Quando os usuários são solicitados a adicionar um rótulo de sensibilidade porque abrem um documento sem rótulo, eles podem adicionar um rótulo ou optar por abrir o documento no modo somente leitura.

- Quando a rotulagem obrigatória está em vigor, os usuários não podem remover rótulos de sensibilidade dos documentos, mas podem alterar um rótulo existente.

Para obter orientações sobre quando usar essa configuração, consulte as informações sobre [configurações de política.](sensitivity-labels.md#what-label-policies-can-do)

## <a name="end-user-documentation"></a>Documentação do usuário final

- [Aplicar rótulos de confidencialidade aos seus documentos e email no Office](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Problemas conhecidos ao aplicar rótulos de confidencialidade aos arquivos do Office](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)
