---
title: Proteção de Informações da Microsoft no Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
description: Implemente a Proteção de Informações da Microsoft (MIP) para ajudá-lo a proteger informações confidenciais onde elas ficam ou trafegam.
ms.openlocfilehash: bf464fd4ea0314a86a10696f8bda62e85a70ea49
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099697"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Proteção de Informações da Microsoft no Microsoft 365

>*[Licenciamento para Segurança e Conformidade do Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Implemente a Proteção de Informações da Microsoft (MIP) para ajudá-lo a descobrir, classificar e proteger informações confidenciais onde elas ficam ou trafegam.

Os recursos de MIP estão incluídos na Conformidade do Microsoft 365 e fornecem as ferramentas para [conhecer seus dados](#know-your-data), [proteger seus dados](#protect-your-data)e [evitar a perda de dados](#prevent-data-loss).

![Imagem de como o MIP ajuda a descobrir, classificar e proteger dados confidenciais](../media/powered-by-intelligent-platform.png)

Para obter informações sobre como controlar seus dados, confira [Governança de Informações da Microsoft no Microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Conheça seus dados

> [!NOTE]
> Para obter informações sobre como classificar e rotular dados no Azure Purview, atualmente em pré-visualização, confira [Rotular automaticamente seu conteúdo no Azure Purview](https://docs.microsoft.com/azure/purview/create-sensitivity-label).
> 
> Para obter informações sobre este lançamento recente, confira a postagem no blog [Proteção de Informações da Microsoft e Azure Purview: Melhor Juntos](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-microsoft-azure-purview/ba-p/1957481).



Para entender o panorama de dados e identificar dados importantes em ambiente híbrido, use os seguintes recursos:
 
|Recursos|Que problemas ela resolve?|Introdução|
|:------|:------------|:--------------------|:-----------------------------|
|[Tipos de informações confidenciais](sensitive-information-type-entity-definitions.md)| Identifica dados confidenciais usando expressões regulares integradas ou personalizadas ou uma função. A evidência corroborativa inclui palavras-chave, níveis de confiança e proximidade.| [Personalizar um tipo de informação confidencial interno](customize-a-built-in-sensitive-information-type.md)|
|[Classificadores treináveis](classifier-learn-about.md)| Identifica dados confidenciais usando exemplos dos dados nos quais você está interessado, em vez de identificar elementos no item (correspondência de padrões). Você pode usar classificadores integrados ou treinar um classificador com seu próprio conteúdo.| [Comece com classificadores treináveis](classifier-get-started-with.md) |
|[Classificação de dados](data-classification-overview.md) | Uma identificação gráfica de itens em sua organização que possuem um rótulo de confidencialidade, um rótulo de retenção ou foram classificados. Você também pode usar essas informações para obter insights sobre as ações que seus usuários estão realizando nesses itens. | [Introdução ao gerenciador de conteúdo ](data-classification-content-explorer.md)<br /><br /> [Introdução ao gerenciador de atividades](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>Proteja seus dados

Para aplicar ações de proteção flexíveis que incluem criptografia, restrições de acesso e marcações visuais, use os seguintes recursos:

|Recursos|Que problemas ela resolve?|Introdução|
|:------|:------------|---------------------|:----------------------------|
|[Rótulos de confidencialidade](sensitivity-labels.md)| Uma solução única entre aplicativos, serviços e dispositivos para rotular e proteger seus dados enquanto eles viajam dentro e fora de sua organização. <br /><br />Exemplos de cenários: <br /> [Gerenciar rótulos de confidencialidade para aplicativos do Office](sensitivity-labels-office-apps.md)<br /> [Criptografar documentos e emails](encryption-sensitivity-labels.md )<br /> [Aplicar e exibir rótulos no Power BI](https://docs.microsoft.com/power-bi/admin/service-security-apply-data-sensitivity-labels) <br /><br /> Para obter uma lista abrangente de cenários para rótulos de confidencialidade, confira a documentação de introdução.|[Introdução ao rótulos de confidencialidade](get-started-with-sensitivity-labels.md) |
|[Cliente de rotulagem unificada da Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| Para computadores Windows, estende os rótulos de confidencialidade aos recursos e funcionalidades adicionais que incluem rotulagem e proteção de todos os tipos de arquivos do Explorador de Arquivos e do PowerShell<br /><br /> Exemplos de recursos adicionais: [configurações personalizadas do cliente de rotulagem unificada da Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Guia do administrador para o cliente de rotulagem unificada da Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[Criptografia de Chave Dupla](double-key-encryption.md)| Em todas as circunstâncias, apenas sua organização pode descriptografar conteúdo protegido ou, para requisitos regulamentares, você deve manter as chaves de criptografia dentro de um limite geográfico. | [Implantar a Criptografia de Chave Dupla](double-key-encryption.md#deploy-dke)|
|[Criptografia de Mensagens do Office 365 (OME)](ome.md)| Criptografa mensagens de email e documentos anexados que são enviados a qualquer usuário em qualquer dispositivo, para que apenas destinatários autorizados possam ler as informações enviadas por email.  <br /><br />Cenário de exemplo: [revogar email criptografado por Criptografia Avançada de Mensagem](revoke-ome-encrypted-mail.md) | [Configurar novos recursos de Criptografia de Mensagem](set-up-new-message-encryption-capabilities.md)|
|[Criptografia do serviço com a Chave de Cliente](customer-key-overview.md) | Protege contra a exibição de dados por sistemas ou pessoal não autorizado e complementa a criptografia de disco BitLocker nos datacenters da Microsoft. | [Configurar a Chave de Cliente do Office 365](customer-key-set-up.md)|
|[IRM (Gerenciamento de Direitos de Informação do SharePoint)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|Protege as listas e bibliotecas do Microsoft Office SharePoint Online para que, quando um usuário fizer check-out de um documento, o arquivo baixado seja protegido para que apenas pessoas autorizadas possam visualizar e usar o arquivo de acordo com as políticas que você especificar. | [Configurar o IRM (Gerenciamento de Direitos de Informação) no centro de administração do SharePoint](set-up-irm-in-sp-admin-center.md)|
[Conector do Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |Proteção apenas para implantações locais existentes que usam Exchange ou SharePoint Server, ou servidores de arquivos que executam o Windows Server e a Infraestrutura de Classificação de Arquivos (FCI). | [Etapas para implantar o conector RMS](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Verificação de rotulagem unificada da Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| Descobre, rotula e protege informações confidenciais que residem em armazenamentos de dados locais. | [Configurar e instalar a verificação de rotulagem unificada da Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| Descobre, rotula e protege informações confidenciais que residem em armazenamentos de dados que estão na nuvem. | [Descobrir, classificar, rotular e proteger dados regulamentados e confidenciais armazenados na nuvem](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[SDK de Proteção de Informações da Microsoft](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|Estende rótulos de sensibilidade para aplicativos e serviços de terceiros.  <br /><br /> Cenário de exemplo: [definir e obter um rótulo de confidencialidade (C++ )](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[Instalação e configuração do SDK MIP (Proteção de Informações da Microsoft)](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>Evita a perda de dados

Para ajudar a evitar o compartilhamento acidental de informações confidenciais, use os seguintes recursos:


|Recursos|Que problemas ela resolve?|Introdução|
|:------|:------------|:---------------------|:-----------------------------|
|[DLP (Prevenção contra perda de dados)](data-loss-prevention-policies.md)| Ajuda a prevenir o compartilhamento não intencional de itens confidenciais. <br /><br />Cenário de exemplo: [proteger informações confidenciais nas mensagens de chat e de canal do Microsoft Teams](dlp-microsoft-teams.md) | [Introdução à política DLP padrão](get-started-with-the-default-dlp-policy.md)|
|[Saiba mais sobre a Prevenção contra perda de dados do ponto de extremidade](endpoint-dlp-learn-about.md)| Estende os recursos de DLP para itens que são usados e compartilhados em computadores Windows 10. | [Introdução à Prevenção contra perda de dados do ponto de extremidade](endpoint-dlp-getting-started.md)|
