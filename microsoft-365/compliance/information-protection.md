---
title: Proteção de Informações da Microsoft no Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
recommendations: false
description: Implemente a Proteção de Informações da Microsoft (MIP) para ajudá-lo a proteger informações confidenciais onde elas ficam ou trafegam.
ms.openlocfilehash: bca6ce0dabaa9db2444da374b5d3ee166154fdd8
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226534"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Proteção de Informações da Microsoft no Microsoft 365

>*[Licenciamento para Segurança e Conformidade do Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Implemente a Proteção de Informações da Microsoft (MIP) para ajudá-lo a descobrir, classificar e proteger informações confidenciais onde elas ficam ou trafegam.

Os recursos de MIP estão incluídos na Conformidade do Microsoft 365 e fornecem as ferramentas para [conhecer seus dados](#know-your-data), [proteger seus dados](#protect-your-data)e [evitar a perda de dados](#prevent-data-loss).

![Imagem de como o MIP ajuda a descobrir, classificar e proteger dados confidenciais](../media/powered-by-intelligent-platform.png)

Para obter informações sobre como controlar seus dados, confira [Governança de Informações da Microsoft no Microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Conheça seus dados

> [!NOTE]
> Para obter informações sobre como classificar e rotular dados no Azure Purview, atualmente em pré-visualização, confira [Rotular automaticamente seu conteúdo no Azure Purview](/azure/purview/create-sensitivity-label).

Para entender o panorama de dados e identificar dados importantes em ambiente híbrido, use os seguintes recursos:

|Recursos|Que problemas ela resolve?|Introdução|
|:------|:------------|:--------------------|
|[Tipos de informações confidenciais](sensitive-information-type-learn-about.md)| Identifica dados confidenciais usando expressões regulares integradas ou personalizadas ou uma função. A evidência corroborativa inclui palavras-chave, níveis de confiança e proximidade.| [Personalizar um tipo de informação confidencial interno](customize-a-built-in-sensitive-information-type.md)|
|[Classificadores treináveis](classifier-learn-about.md)| Identifica dados confidenciais usando exemplos dos dados nos quais você está interessado, em vez de identificar elementos no item (correspondência de padrões). Você pode usar classificadores integrados ou treinar um classificador com seu próprio conteúdo.| [Comece com classificadores treináveis](classifier-get-started-with.md) |
|[Classificação de dados](data-classification-overview.md) | Uma identificação gráfica de itens em sua organização que possuem um rótulo de confidencialidade, um rótulo de retenção ou foram classificados. Você também pode usar essas informações para obter insights sobre as ações que seus usuários estão realizando nesses itens. | [Introdução ao gerenciador de conteúdo ](data-classification-content-explorer.md) <p> [Introdução ao gerenciador de atividades](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>Proteja seus dados

Para aplicar ações de proteção flexíveis que incluem criptografia, restrições de acesso e marcações visuais, use os seguintes recursos:

|Recursos|Que problemas ela resolve?|Introdução|
|:------|:------------|---------------------|
|[Rótulos de confidencialidade](sensitivity-labels.md)| Uma solução única entre aplicativos, serviços e dispositivos para rotular e proteger seus dados enquanto eles viajam dentro e fora de sua organização. <p> Exemplos de cenários: <p> [Gerenciar rótulos de confidencialidade para aplicativos do Office](sensitivity-labels-office-apps.md) <p> [Criptografar documentos e emails](encryption-sensitivity-labels.md) <p> [Aplicar e exibir rótulos no Power BI](/power-bi/admin/service-security-apply-data-sensitivity-labels) <p> Para obter uma lista abrangente de cenários para rótulos de confidencialidade, confira a documentação de introdução.|[Introdução ao rótulos de confidencialidade](get-started-with-sensitivity-labels.md) |
|[Cliente de rotulagem unificada da Proteção de Informações do Azure](/azure/information-protection/rms-client/aip-clientv2)| Para computadores Windows, estende os rótulos de confidencialidade aos recursos e funcionalidades adicionais que incluem rotulagem e proteção de todos os tipos de arquivos do Explorador de Arquivos e do PowerShell <p> Exemplos de recursos adicionais: [configurações personalizadas do cliente de rotulagem unificada da Proteção de Informações do Azure](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Guia do administrador para o cliente de rotulagem unificada da Proteção de Informações do Azure](/azure/information-protection/rms-client/clientv2-admin-guide)|
|[Criptografia de Chave Dupla](double-key-encryption.md)| Em todas as circunstâncias, apenas sua organização pode descriptografar conteúdo protegido ou, para requisitos regulamentares, você deve manter as chaves de criptografia dentro de um limite geográfico. | [Implantar a Criptografia de Chave Dupla](double-key-encryption.md#deploy-dke)|
|[Criptografia de Mensagens do Office 365 (OME)](ome.md)| Criptografa mensagens de email e documentos anexados que são enviados a qualquer usuário em qualquer dispositivo, para que apenas destinatários autorizados possam ler as informações enviadas por email. <p> Cenário de exemplo: [revogar email criptografado por Criptografia Avançada de Mensagem](revoke-ome-encrypted-mail.md) | [Configurar novos recursos de Criptografia de Mensagem](set-up-new-message-encryption-capabilities.md)|
|[Criptografia do serviço com a Chave de Cliente](customer-key-overview.md) | Protege contra a exibição de dados por sistemas ou pessoal não autorizado e complementa a criptografia de disco BitLocker nos datacenters da Microsoft. | [Configurar a Chave de Cliente do Office 365](customer-key-set-up.md)|
|[IRM (Gerenciamento de Direitos de Informação do SharePoint)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|Protege as listas e bibliotecas do Microsoft Office SharePoint Online para que, quando um usuário fizer check-out de um documento, o arquivo baixado seja protegido para que apenas pessoas autorizadas possam visualizar e usar o arquivo de acordo com as políticas que você especificar. | [Configurar o IRM (Gerenciamento de Direitos de Informação) no centro de administração do SharePoint](set-up-irm-in-sp-admin-center.md)|
[Conector do Rights Management](/azure/information-protection/deploy-rms-connector) |Proteção apenas para implantações locais existentes que usam Exchange ou SharePoint Server, ou servidores de arquivos que executam o Windows Server e a Infraestrutura de Classificação de Arquivos (FCI). | [Etapas para implantar o conector RMS](/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Verificação de rotulagem unificada da Proteção de Informações do Azure](/azure/information-protection/deploy-aip-scanner)| Descobre, rotula e protege informações confidenciais que residem em armazenamentos de dados locais. | [Configurar e instalar a verificação de rotulagem unificada da Proteção de Informações do Azure](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)| Descobre, rotula e protege informações confidenciais que residem em armazenamentos de dados que estão na nuvem. | [Descobrir, classificar, rotular e proteger dados regulamentados e confidenciais armazenados na nuvem](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[SDK de Proteção de Informações da Microsoft](/information-protection/develop/overview#microsoft-information-protection-sdk)|Estende rótulos de sensibilidade para aplicativos e serviços de terceiros. <p> Cenário de exemplo: [definir e obter um rótulo de confidencialidade (C++ )](/information-protection/develop/quick-file-set-get-label-cpp) |[Instalação e configuração do SDK MIP (Proteção de Informações da Microsoft)](/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>Evita a perda de dados

Para ajudar a evitar o compartilhamento acidental de informações confidenciais, use os seguintes recursos:


|Recursos|Que problemas ela resolve?|Introdução|
|:------|:------------|:---------------------|
|[Prevenção contra perda de dados](dlp-learn-about-dlp.md)| Ajuda a prevenir o compartilhamento não intencional de itens confidenciais. | [Introdução à política DLP padrão](get-started-with-the-default-dlp-policy.md)|
|[Prevenção contra perda de dados do ponto de extremidade](endpoint-dlp-learn-about.md)| Estende os recursos de DLP para itens que são usados e compartilhados em computadores Windows 10. | [Introdução à Prevenção contra perda de dados do ponto de extremidade](endpoint-dlp-getting-started.md)|
|[Extensão de Conformidade Microsoft](dlp-chrome-learn-about.md) | Estende os recursos da DLP para o navegador Chrome | [Comece com a Extensão de Conformidade da Microsoft](dlp-chrome-get-started.md)|
|[Verificador local de prevenção contra perda de dados do Microsoft 365 (visualização)](dlp-on-premises-scanner-learn.md)|Estende o monitoramento DLP de atividades de arquivo e ações de proteção para esses arquivos para compartilhamentos de arquivos locais e pastas do SharePoint e bibliotecas de documentos.|[Comece a usar o scanner local de prevenção contra perda de dados do Microsoft 365 (visualização)](dlp-on-premises-scanner-get-started.md)|
|[Proteja informações confidenciais no bate-papo do Microsoft Teams e nas mensagens do canal](dlp-microsoft-teams.md) | Estende algumas funcionalidades do DLP para o bate-papo do Teams e as mensagens do canal | [Saiba mais sobre a política de prevenção de perda de dados padrão no Microsoft Teams (visualização)](dlp-teams-default-policy.md)|

## <a name="licensing-requirements"></a>Requisitos de licenciamento

Os requisitos de licença para a Proteção de Informações da Microsoft dependem dos cenários e dos recursos que você usa, em vez de definir os requisitos de licenciamento para cada recurso listado nesta página. Para entender suas opções e requisitos de licenciamento, confira as seções de [Proteção de Informações](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection) da documentação de licenciamento do Microsoft 365 e baixe o PDF ou o Excel relacionado.
