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
ms.openlocfilehash: 5b9484826f0d3a297dae47c7d140d93297473023
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259256"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Proteção de Informações da Microsoft no Microsoft 365

>*[Licenciamento para Segurança e Conformidade do Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Implemente a Proteção de Informações da Microsoft (MIP) para ajudá-lo a descobrir, classificar e proteger informações confidenciais onde elas ficam ou trafegam.

Os recursos de MIP estão incluídos na Conformidade do Microsoft 365 e fornecem as ferramentas para [conhecer seus dados](#know-your-data), [proteger seus dados](#protect-your-data)e [evitar a perda de dados](#prevent-data-loss).

![Imagem de como o MIP ajuda a descobrir, classificar e proteger dados confidenciais](../media/powered-by-intelligent-platform.png)

:::image type="content" source="../media/data-table1-4638524-new.png" alt-text="Conheça seus dados":::

Para obter informações sobre como controlar seus dados, confira [Governança de Informações da Microsoft no Microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Conheça seus dados

> [!NOTE]
> Para obter informações sobre como classificar e rotular dados no Azure Purview, atualmente em pré-visualização, confira [Rotular automaticamente seu conteúdo no Azure Purview](/azure/purview/create-sensitivity-label).
> 
> Para comunicados de lançamento do Azure Purview, confira as seguintes postagens de blog: [Proteção de Informações da Microsoft e Microsoft Azure Purview: Melhor juntos](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-microsoft-azure-purview/ba-p/1957481) e [Azure Purview na Primavera do Ignite 2021](https://techcommunity.microsoft.com/t5/azure-purview/azure-purview-at-spring-ignite-2021/ba-p/2175919).

Para entender o panorama de dados e identificar dados importantes em ambiente híbrido, use os seguintes recursos:

:::image type="content" source="../media/knowyourdata-new.png" alt-text="conheça seus dados"::: 


|**Funcionalidade**|**Que problemas ela resolve?**|**Introdução**|**Licenciamento**|
|--|--|--|--|
|[Tipos de informações confidenciais](sensitive-information-type-entity-definitions.md)| Identifica dados confidenciais usando expressões regulares internas ou personalizadas, ou uma função, juntamente com evidências corroborativas que incluem palavras-chave, níveis de confiança e proximidade. Use tipos de informações confidenciais para identificar tipos específicos de dados em sua organização. Use os tipos de informações confidenciais prontos para uso para encontrar tipos de dados padrão, tais como números de passaporte. Crie um tipo de informação personalizada para identificar informações exclusivas de seu ambiente, como números de peças. | [Personalizar um tipo de informação confidencial interno](customize-a-built-in-sensitive-information-type.md)| |
|[Classificadores de treinamento (visualização)](classifier-learn-about.md)| Classifica os dados por você, usando um dos classificadores internos ou treinando um classificador com seu próprio conteúdo | [Introdução aos classificadores de treinamento (visualização)](classifier-get-started-with.md)| |
|[Classificação de dados](data-classification-overview.md) | Identifica itens que têm um rótulo de confidencialidade, um rótulo de retenção ou foram classificados como um tipo de informação confidencial em sua organização, e as ações que seus usuários estão tomando.  | [Introdução ao gerenciador de conteúdo ](data-classification-content-explorer.md)<br /><br /> [Introdução ao gerenciador de atividades](data-classification-activity-explorer.md)| |



## <a name="protect-your-data"></a>Proteja seus dados

Para aplicar ações de proteção flexíveis que incluem criptografia, restrições de acesso e marcações visuais, use os seguintes recursos:


:::image type="content" source="../media/protectyourdata-4638524-new.png" alt-text="Proteja seus dados":::

|**Funcionalidade**|**Que problemas ela resolve?**|**Introdução**|**Licenciamento**|
|--|--|--|--|
|[Rótulos de confidencialidade](sensitivity-labels.md)| Uma solução única em aplicativos, serviços e dispositivos para rotular e proteger seus dados enquanto eles trafegam dentro e fora da organização <br /><br />Cenário de exemplo: [aplicar e exibir rótulos de confidencialidade no Power BI e proteger dados ao exportá-los](/power-bi/admin/service-security-apply-data-sensitivity-labels)|[Introdução ao rótulos de confidencialidade](get-started-with-sensitivity-labels.md) |
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)| Descobrir, rotular e proteger informações confidenciais que residem em armazenamentos de dados que estão na nuvem | [Descobrir, classificar, rotular e proteger dados regulamentados e confidenciais armazenados na nuvem](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Verificação de rotulagem unificada da Proteção de Informações do Azure](/azure/information-protection/deploy-aip-scanner)| Descobre, rotula e protege informações confidenciais que estão em repositórios de dados locais | [Configurar e instalar a verificação de rotulagem unificada da Proteção de Informações do Azure](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Explorador de Atividade]()||||


## <a name="transition-from-aip-to-mip"></a>Transição de AIP para MIP
A clássica experiência administrativa e cliente da Proteção de Informações do Azure está sendo desvalorizada no início do próximo ano. É recomendável mover para a Proteção de Informações da Microsoft.Isso implica a migração de todos os seus rótulos e políticas existentes. 

:::image type="content" source="../media/transition-aip2mip-4638524-new.png" alt-text="Transição de AIP para MIP":::

## <a name="additional-capabilities"></a>Recursos adicionais
O Microsoft 365 inclui estes recursos para ajudar a proteger os dados:

|**Funcionalidade**|**Que problemas ela resolve?**|**Introdução**|
|--|--|--|
| OME(Criptografia de Mensagem do Office 365) | Criptografa mensagens de email e documentos anexados que são enviados a qualquer usuário em qualquer dispositivo, para que apenas destinatários autorizados possam ler as informações enviadas por email. <br /><br /> Cenário de exemplo: Revogar email criptografado por Criptografia Avançada de Mensagem | Configurar novos recursos de Criptografia de Mensagens |
| Criptografia de Chave Dupla | Em todas as circunstâncias, somente você pode decifrar o conteúdo protegido ou, por exigências regulatórias, você deve manter chaves de criptografia dentro de um limite geográfico. | Implantar a Criptografia de Chave Dupla |  
| Criptografia do serviço com a Chave de Cliente | Protege contra visualização de dados por sistemas ou pessoal não autorizado, e complementa a criptografia de disco Bitlocker nos centros de dados Microsoft | Configurar a Chave de Cliente do Office 365 |
| IRM(Gerenciamento de Direitos de Informação do Microsoft Office SharePoint Online) | Protege listas e bibliotecas do Microsoft Office SharePoint Online para que quando um usuário verifica um documento, o arquivo baixado seja protegido para que apenas os autorizados possam visualizar e usar o arquivo de acordo com as políticas que você especificar | Configurar o IRM (Gerenciamento de Direitos de Informação) no Centro de Administração do SharePoint Online |
| Conector de Gerenciamento de Direitos | Proteção apenas para implantações existentes no local que utilizam Exchange Online ou Servidor do Microsoft Office SharePoint Online e FCI (Infraestrutura de Classificação de Arquivos) | Etapas para implantar o Conector RMS |



## <a name="prevent-data-loss"></a>Evita a perda de dados

Para ajudar a evitar o compartilhamento acidental de informações confidenciais, use os seguintes recursos:

:::image type="content" source="../media/dlp-4638524-new.png" alt-text="Evita a perda de dados":::

|**Etapa**|**Descrição**|**Mais informações**|
|--|--|--|
|[Políticas de DLP de Design](data-loss-prevention-policies.md)| Plano para o modo de identificação de informações(tipo de informações confidenciais, rótulo, outros) <br /><br /> Plano onde as políticas serão direcionadas(serviços, cliente, aplicações de terceiros.) <br /><br /> Dicas de política de planos, outros||
||||




|**Funcionalidade**|**Que problemas ela resolve?**|**Introdução**|
|--|--|--|
|[Saiba mais sobre prevenção contra perda de dados](dlp-learn-about-dlp.md)| Ajuda a prevenir o compartilhamento não intencional de itens confidenciais. | [Introdução à política DLP padrão](get-started-with-the-default-dlp-policy.md)|
|[Saiba mais sobre a Prevenção contra perda de dados do ponto de extremidade](endpoint-dlp-learn-about.md)| Estende os recursos de DLP para itens que são usados e compartilhados em computadores Windows 10. | [Introdução à Prevenção contra perda de dados do ponto de extremidade](endpoint-dlp-getting-started.md)|
|[Saiba mais sobre a extensão de conformidade da Microsoft (visualização)](dlp-chrome-learn-about.md) | Estende os recursos de DLP para o navegador Chrome | [Comece com a extensão de conformidade da Microsoft (visualização)](dlp-chrome-get-started.md)|
|[Saiba mais sobre o scanner local de prevenção contra perda de dados do Microsoft 365 (visualização)](dlp-on-premises-scanner-learn.md)|Estende o monitoramento DLP de atividades de arquivo e ações de proteção para esses arquivos para compartilhamentos de arquivos locais e pastas do SharePoint e bibliotecas de documentos.|[Comece a usar o scanner local de prevenção contra perda de dados do Microsoft 365 (visualização)](dlp-on-premises-scanner-get-started.md)|
|[Proteja informações confidenciais no bate-papo do Microsoft Teams e nas mensagens do canal](dlp-microsoft-teams.md) | Estende algumas funcionalidades do DLP para o bate-papo do Teams e as mensagens do canal | [Saiba mais sobre a política de prevenção de perda de dados padrão no Microsoft Teams (visualização)](dlp-teams-default-policy.md)| 


## <a name="additional-resources"></a>Recursos adicionais

Muitas organizações estão usando esses recursos de proteção de informações para cumprir os regulamentos de privacidade de dados. Para ajudar, projetamos um fluxo de trabalho para guiá-lo por um processo de ponta a ponta para planejar e implementar recursos no Microsoft 365, incluindo acesso seguro, proteção contra ameaças, proteção de informações e governança de dados. Para obter mais informações, consulte [Implantar a proteção de informações para conformidade com as regulamentações de privacidade de dados com o Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).. 

Além disso, para ajudá-lo a planejar uma estratégia integrada para a implementação de recursos de proteção de informações, baixe o conjunto de ilustrações *Recursos de proteção de Informações e conformidade do Microsoft 365*.  Sinta-se à vontade para adaptar essas ilustrações para seu próprio uso.

| Item | Descrição |
|:-----|:------------|
|[![Pôster do modelo: recursos de conformidade e proteção de informações do Microsoft 365](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/> [Baixar como um PDF](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf)  \| [Baixar como um Visio](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) <br/> Japonês: [Baixar como PDF](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf)  \| [Baixar como Visio](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx) <br/> Atualizado em outubro de 2020|Contém: <ul><li>  Proteção de informações e prevenção contra perda de dados da Microsoft</li><li>Políticas de retenção e rótulos de retenção </li><li>Barreiras de informações</li><li>Conformidade em comunicações</li><li>Gerenciamento de risco interno</li><li>Inclusão de dados de terceiros</li>|

