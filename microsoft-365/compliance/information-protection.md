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
ms.openlocfilehash: 4c8f4af11779cd8b3df043bc92187625c41f4ac9
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519806"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Proteção de Informações da Microsoft no Microsoft 365

>*[Licenciamento para Segurança e Conformidade do Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Implemente a Proteção de Informações da Microsoft (MIP) para ajudá-lo a descobrir, classificar e proteger informações confidenciais onde elas ficam ou trafegam.

Os recursos de MIP estão incluídos na Conformidade do Microsoft 365 e fornecem as ferramentas para [conhecer seus dados](#know-your-data), [proteger seus dados](#protect-your-data)e [evitar a perda de dados](#prevent-data-loss).

![Imagem de como o MIP ajuda a descobrir, classificar e proteger dados confidenciais](../media/powered-by-intelligent-platform.png)

Para obter informações sobre como controlar seus dados, confira [Governança de Informações da Microsoft no Microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Conheça seus dados

Para entender o panorama de dados e identificar dados importantes em ambiente híbrido, use os seguintes recursos:
 
|Recursos|Que problemas ela resolve?|Introdução|
|:------|:------------|:--------------------|:-----------------------------|
|[Tipos de informações confidenciais](sensitive-information-type-entity-definitions.md)| Identifica dados confidenciais usando expressões regulares internas ou personalizadas, ou uma função, juntamente com evidências corroborativas que incluem palavras-chave, níveis de confiança e proximidade.| [Personalizar um tipo de informação confidencial interno](customize-a-built-in-sensitive-information-type.md)|
|[Classificadores de treinamento (visualização)](classifier-learn-about.md)| Classifica os dados por você, usando um dos classificadores internos ou treinando um classificador com seu próprio conteúdo | [Introdução aos classificadores de treinamento (visualização)](classifier-get-started-with.md) |
|[Classificação de dados](data-classification-overview.md) | Identifica itens que têm um rótulo de confidencialidade, um rótulo de retenção ou foram classificados como um tipo de informação confidencial em sua organização, e as ações que seus usuários estão tomando.  | [Introdução ao gerenciador de conteúdo ](data-classification-content-explorer.md)<br /><br /> [Introdução ao gerenciador de atividades](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>Proteja seus dados

Para aplicar ações de proteção flexíveis que incluem criptografia, restrições de acesso e marcações visuais, use os seguintes recursos:

|Recursos|Que problemas ela resolve?|Introdução|
|:------|:------------|---------------------|:----------------------------|
|[Rótulos de confidencialidade](sensitivity-labels.md)| Uma solução única em aplicativos, serviços e dispositivos para rotular e proteger seus dados enquanto eles trafegam dentro e fora da organização <br /><br />Cenário de exemplo: [aplicar e exibir rótulos de confidencialidade no Power BI e proteger dados ao exportá-los](https://docs.microsoft.com/power-bi/admin/service-security-apply-data-sensitivity-labels)|[Introdução ao rótulos de confidencialidade](get-started-with-sensitivity-labels.md) |
|[Cliente de rotulagem unificada da Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| Para computadores Windows, estende os rótulos de confidencialidade aos recursos e funcionalidades adicionais que incluem rotulagem e proteção de todos os tipos de arquivos do Explorador de Arquivos e do PowerShell<br /><br /> Exemplos de recursos adicionais: [configurações personalizadas do cliente de rotulagem unificada da Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Guia do administrador para o cliente de rotulagem unificada da Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[Criptografia de Chave Dupla](double-key-encryption.md)| Em todas as circunstâncias, somente você pode descriptografar o conteúdo protegido; ou mantenha as chaves de criptografia dentro de um limite geográfico quando se tratar de requisitos normativos | [Implantar a Criptografia de Chave Dupla](double-key-encryption.md#deploy-dke)|
|[Criptografia de Mensagens do Office 365 (OME)](ome.md)| Criptografa mensagens de email e documentos anexos enviados a qualquer usuário em qualquer dispositivo, de modo que somente destinatários autorizados podem ler as informações enviadas por email  <br /><br />Cenário de exemplo: [revogar email criptografado por Criptografia Avançada de Mensagem](revoke-ome-encrypted-mail.md) | [Configurar novos recursos de Criptografia de Mensagem](set-up-new-message-encryption-capabilities.md)|
|[Criptografia do serviço com a Chave de Cliente](customer-key-overview.md) | Protege contra a visualização de dados por sistemas ou pessoal não autorizado, e complementa a criptografia de disco BitLocker em datacenters da Microsoft | [Configurar a Chave de Cliente do Office 365](customer-key-set-up.md)|
|[IRM (Gerenciamento de Direitos de Informação do SharePoint)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|Protege listas e bibliotecas do SharePoint para que, quando um usuário verifique um documento, o arquivo baixado seja protegido para que somente pessoas autorizadas possam visualizar e usar o arquivo de acordo com as políticas que você especificar | [Configurar o IRM (Gerenciamento de Direitos de Informação) no centro de administração do SharePoint](set-up-irm-in-sp-admin-center.md)|
[Conector do Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |Proteção somente para implantações existentes no local que usam o Exchange ou SharePoint Server, ou servidores de arquivos que executam o Windows Server e a FCI (Infraestrutura de Classificação de Arquivos) | [Etapas para implantar o conector RMS](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Verificação de rotulagem unificada da Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| Descobre, rotula e protege informações confidenciais que estão em repositórios de dados locais | [Configurar e instalar a verificação de rotulagem unificada da Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| Descobre, rotula e protege informações confidenciais que estão em repositórios de dados na nuvem | [Descobrir, classificar, rotular e proteger dados regulamentados e confidenciais armazenados na nuvem](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[SDK de Proteção de Informações da Microsoft](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|Estender os rótulos de confidencialidade a aplicativos e serviços de terceiros  <br /><br /> Cenário de exemplo: [definir e obter um rótulo de confidencialidade (C++ )](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[Instalação e configuração do SDK MIP (Proteção de Informações da Microsoft)](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|

## <a name="prevent-data-loss"></a>Evita a perda de dados

Para ajudar a evitar o compartilhamento acidental de informações confidenciais, use os seguintes recursos:


|Recursos|Que problemas ela resolve?|Introdução|
|:------|:------------|:---------------------|:-----------------------------|
|[DLP (Prevenção contra perda de dados)](data-loss-prevention-policies.md)| Ajuda a evitar o compartilhamento não intencional de itens confidenciais <br /><br />Cenário de exemplo: [proteger informações confidenciais nas mensagens de chat e de canal do Microsoft Teams](dlp-microsoft-teams.md) | [Introdução à política DLP padrão](get-started-with-the-default-dlp-policy.md)|
|[Saiba mais sobre a Prevenção contra perda de dados do ponto de extremidade](endpoint-dlp-learn-about.md)| Estende os recursos DLP para itens que são usados e compartilhados em computadores Windows 10 | [Introdução à Prevenção contra perda de dados do ponto de extremidade](endpoint-dlp-getting-started.md)|
