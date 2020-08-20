---
title: Proteção de informações da Microsoft no Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: High
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Implementar recursos de proteção de informações da Microsoft (MIP) usando o Microsoft 365 Compliance para ajudá-lo a descobrir, classificar e proteger informações confidenciais onde quer que elas se envidam ou se encontram.
ms.openlocfilehash: 96082bc70b093e763be00c847bb6a68ce302c8a9
ms.sourcegitcommit: 22fd8517707ed3ab6ef996247ad2aa372535ee56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46815194"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Proteção de informações da Microsoft no Microsoft 365

>*[Licenciamento para conformidade com o Microsoft 365 Security &](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Use a proteção de informações da Microsoft (MIP) para ajudá-lo a descobrir, classificar e proteger informações confidenciais onde elas residem ou viajam.

Os recursos de MIP estão incluídos no Microsoft 365 Compliance e oferecem as ferramentas para [conhecer seus dados](#know-your-data), [proteger seus dados](#protect-your-data)e [evitar a perda de dados](#prevent-data-loss).

![Saiba seus dados, proteja seus dados, evite a perda de dados, administre seus dados](../media/powered-by-intelligent-platform.png)

Para obter informações sobre como governar seus dados, consulte [Microsoft Information Governance in microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Conheça seus dados

Para entender seu cenário de dados e identificar dados importantes em seu ambiente híbrido, use os seguintes recursos:
 
|Recursos|Que problemas ele resolve?|Introdução|
|:------|:------------|:--------------------|:-----------------------------|
|[Tipos de informações confidenciais](sensitive-information-type-entity-definitions.md)| Identifica dados confidenciais usando expressões regulares internas ou personalizadas ou uma função, junto com a evidência corroborativas que inclui palavras-chave, níveis de confiança e proximidade.| [Personalizar um tipo de informação confidencial interno](customize-a-built-in-sensitive-information-type.md)|
|[Classificadores estagiários (visualização)](classifier-getting-started-with.md)| Classifica dados para você, usando um dos classificadores internos ou treina um classier com seu próprio conteúdo | [Criar um classificador treinado (visualização)](classifier-creating-a-trainable-classifier.md) |
|[Classificação de dados](data-classification-overview.md) | Identifica itens que têm um rótulo de confidencialidade, um rótulo de retenção ou foram classificados como um tipo de informação confidencial em sua organização e as ações que os usuários estão assumindo neles  | [Introdução ao gerenciador de conteúdo ](data-classification-content-explorer.md)<br /><br /> [Começar a usar o gerenciador de atividades](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>Proteja seus dados

Para aplicar ações de proteção flexíveis que incluem criptografia, restrições de acesso e marcações visuais, use os seguintes recursos:

|Recursos|Que problemas ele resolve?|Introdução|
|:------|:------------|---------------------|:----------------------------|
|[Rótulos de confidencialidade ](sensitivity-labels.md)| Uma única solução entre aplicativos, serviços e dispositivos para rotular e proteger seus dados conforme eles trafegam dentro e fora da sua organização <br /><br />Cenário de exemplo: [aplicar e exibir rótulos de confidencialidade no Power bi e proteger dados quando ele é exportado](https://docs.microsoft.com/power-bi/admin/service-security-data-protection-overview)|[ Introdução aos rótulos de confidencialidade](get-started-with-sensitivity-labels.md) |
|[Cliente de rotulação unificada de proteção de informações do Azure](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| Para computadores com Windows, estende os rótulos de confidencialidade para recursos adicionais e funcionalidade que inclui o rótulo e a proteção de todos os tipos de arquivo do explorador de arquivos e do PowerShell<br /><br /> Exemplos de recursos adicionais: [configurações personalizadas para o cliente de rotulação unificado de proteção de informações do Azure](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Guia do administrador do cliente de rótulo unificado de proteção de informações do Azure](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[Criptografia de Chave Dupla](double-key-encryption.md)| Em todas as circunstâncias, apenas você pode descriptografar o conteúdo protegido, ou para requisitos normativos, você deve manter chaves de criptografia dentro de um limite geográfico | [Implantar a criptografia de chave dupla](double-key-encryption.md#deploy-double-key-encryption)|
|[Criptografia de mensagem do Office 365](ome.md) (ome)| Criptografa mensagens de email e documentos anexados que são enviados para qualquer usuário em qualquer dispositivo, de modo que somente os destinatários autorizados possam ler informações enviadas por email  <br /><br />Cenário de exemplo: [revogar emails criptografados por criptografia de mensagem avançada](revoke-ome-encrypted-mail.md) | [Introdução à criptografia de mensagem do Office 365](set-up-new-message-encryption-capabilities.md)|
|[Criptografia de serviço com a chave do cliente](customer-key-overview.md) | Protege contra a exibição de dados por um pessoal ou sistemas não autorizados e complementa a criptografia de disco BitLocker nos datacenters da Microsoft | [Configurar a Chave de Cliente do Office 365](customer-key-set-up.md)|
|[IRM (gerenciamento de direitos de informação) do SharePoint](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|Protege listas e bibliotecas do SharePoint para que, quando um usuário faz check-out de um documento, o arquivo baixado seja protegido de modo que somente as pessoas autorizadas possam exibir e usar o arquivo de acordo com as políticas que você especificar | [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)|
[Conector de gerenciamento de direitos](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |Proteção: somente para implantações locais existentes que usam o Exchange ou o SharePoint Server ou servidores de arquivos que executam o Windows Server e a infraestrutura de classificação de arquivo (FCI) | [Etapas para implantar o conector RMS](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Verificador de rótulo unificado de proteção de informações do Azure](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| Descobre, rotula e protege informações confidenciais que residem em repositórios de dados que estão no local | [Configurando e instalando o verificador de rótulo unificado proteção de informações do Azure](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Segurança no Aplicativo da Nuvem da Microsoft](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| Descobre, rotula e protege informações confidenciais que residem em repositórios de dados que estão na nuvem | [Descobrir, classificar, rotular e proteger dados regulamentados e confidenciais armazenados na nuvem](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[SDK de Proteção de Informações da Microsoft](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|Estende os rótulos de confidencialidade para aplicativos e serviços de terceiros  <br /><br /> Cenário de exemplo: [set e obter um rótulo de confidencialidade (C++)](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[Instalação e configuração do SDK do Microsoft Information Protection (MIP)](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|

## <a name="prevent-data-loss"></a>Evita a perda de dados

Para ajudar a evitar o compartilhamento acidental de informações confidenciais, use os seguintes recursos:


|Recursos|Que problemas ele resolve?|Introdução|
|:------|:------------|:---------------------|:-----------------------------|
|[Prevenção de perda de dados](data-loss-prevention-policies.md) (DLP)| Ajuda a evitar o compartilhamento não intencional de itens confidenciais <br /><br />Cenário de exemplo: [proteger informações confidenciais em mensagens de chat e de canal do Microsoft Teams](dlp-microsoft-teams.md) | [Introdução à política DLP padrão](get-started-with-the-default-dlp-policy.md)|
|[Prevenção de perda de dados de ponto de extremidade (prévia)](endpoint-dlp-learn-about.md)| Estende os recursos de DLP para itens que são usados e compartilhados em computadores com Windows 10 | [Introdução à prevenção contra perda de dados do Endpoint (visualização)](endpoint-dlp-getting-started.md)|
