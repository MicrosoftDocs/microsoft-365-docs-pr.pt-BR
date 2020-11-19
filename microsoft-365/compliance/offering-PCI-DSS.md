---
title: Padrão de Segurança de Dados (DSS) da Indústria de Cartões de Pagamento (PCI)
description: O Azure, o SharePoint Online e o OneDrive for Business estão em conformidade com os Padrões de Segurança de Dados da Indústria de Cartões de Pagamento Level 1 versão 3.2.
keywords: Microsoft 365, conformidade, ofertas
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 57164e08128080f90cb3985b3a3f887521f4c3d5
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126594"
---
# <a name="payment-card-industry-pci-data-security-standard-dss"></a>Padrão de Segurança de Dados (DSS) da Indústria de Cartões de Pagamento (PCI)

## <a name="pci-dss-overview"></a>Visão geral do PCI DSS

O Padrão de Segurança de Dados (DSS) da Indústria de Cartões de Pagamento (PCI) é um padrão global de segurança de informações projetado para impedir fraudes por meio de um maior controle dos dados de cartão de crédito. Organizações de todos os tamanhos devem seguir os padrões PCI DSS se aceitarem cartões de pagamento das cinco principais marcas de cartão de crédito - Visa, MasterCard, American Express, Discover e Japan Credit Bureau (JCB). A conformidade com o PCI DSS é necessária para qualquer organização que armazene, processe ou transmita dados de pagamento e do titular do cartão.

## <a name="microsoft-and-pci-dss"></a>Microsoft e PCI DSS

A Microsoft concluiu uma avaliação anual do PCI DSS usando um Avaliador de Segurança Qualificado (QSA) aprovado. Os auditores examinaram ambientes do Microsoft Azure, Microsoft OneDrive for Business e Microsoft SharePoint Online, que incluem a validação da infraestrutura, desenvolvimento, operações, gerenciamento, suporte e serviços no escopo. O PCI DSS designa quatro níveis de conformidade com base no volume de transações. O Azure, o OneDrive for Business e o SharePoint Online são certificados como compatíveis com a versão 3.2 do PCI DSS no Provedor de Serviços Nível 1 (o maior volume de transações - mais de 6 milhões por ano).

A avaliação resulta em um Atestado de Conformidade (AoC), que está disponível aos clientes e um Relatório de Conformidade (RoC) emitido pelo QSA. O período efetivo para conformidade começa ao passar a auditoria e receber o AoC do avaliador e termina um ano a partir da data de assinatura do AoC. 

Os clientes que desejam desenvolver um ambiente do titular do cartão ou um serviço de processamento de cartões podem utilizar essas validações em muitas das partes subjacentes, reduzindo assim o trabalho e os custos associados à obtenção de sua própria certificação PCI DSS.

É importante entender que o status de conformidade do Azure, do OneDrive for Business e do SharePoint Online com o PCI DSS não se converte automaticamente em certificação PCI DSS para os serviços que os clientes criam ou hospedam nessas plataformas. Os clientes são responsáveis ​​pelo cumprimento dos requisitos do PCI DSS.

## <a name="microsoft-in-scope-cloud-services"></a>Serviços de nuvem no escopo da Microsoft

- [Azure e Azure Governamental](https://azure.microsoft.com/global-infrastructure/government/)
- Segurança no aplicativo na nuvem da Microsoft
- Serviço de nuvem do Flow como um serviço autônomo ou incluído em um plano ou pacote do Office 365 ou do Dynamics 365.
- Microsoft Graph
- Intune
- [Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- Serviço de nuvem do PowerApps como um serviço autônomo ou incluído em um plano ou pacote do Office 365 ou Dynamics 365
- Serviço de nuvem do Power BI como um serviço autônomo ou incluído em um plano ou pacote do Office 365
- OneDrive for Business e SharePoint Online (somente nos Estados Unidos)

## <a name="audit-reports-and-certificates"></a>Auditorias, relatórios e certificados

- [Atestado de Conformidade (AoC) PCI DSS do Azure](https://aka.ms/azure-pci)
- [Atestado de Conformidade ( AoC) PCI DSS do OneDrive for Business e SharePoint Online](https://aka.ms/spo-pci)

## <a name="get-your-pci-dss-solution-running-on-azure"></a>Execute sua solução PCI DSS no Azure

Crie e implante sua solução PCI DSS na nuvem ainda mais rápido com o Blueprint PCI DSS de Segurança e Conformidade do Azure. Obtenha arquiteturas de referência, guia de implantação, mapeamentos de implementação de controle, scripts automatizados e muito mais. [Comece a usar o Azure PCI DSS Blueprint](https://aka.ms/pciblueprint).

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Por que a página de rosto do Atestado de Conformidade (AoC) mostra “junho de 2018”?**

A data de junho de 2018 na página de rosto é de quando o modelo AoC foi publicado. Confira a data da avaliação na Seção 2.

**Por que há vários Atestados de Conformidade (AoCs) do Azure?**

O pacote Azure AoC tem AoCs correspondentes à nuvem Pública do Azure, do Azure Alemanha e do Azure Governamental. Os clientes devem usar o AoC que corresponde ao seu ambiente do Azure.  

**Qual é a relação entre PA DSS e PCI DSS?**

O Padrão de Segurança de Dados de Aplicativos de Pagamento (PA DSS) é um conjunto de requisitos em conformidade com o PCI DSS e substitui as Práticas Recomendadas para Aplicativos de Pagamento do Visa e consolida os requisitos de conformidade de outros emissores de cartão principal. O PA DSS ajuda os fornecedores de software a desenvolver aplicativos de terceiros que armazenam, processam ou transmitem dados de pagamento do titular do cartão como parte de um processo de autorização ou liquidação do cartão. Os varejistas devem usar os aplicativos com certificados PA DSS para alcançar com eficiência sua conformidade com o PCI DSS. O PA DSS não se aplica ao Azure.

**O que é um adquirente? O Azure usa um?**

Um adquirente é um banco ou outra entidade que processa transações de cartão de pagamento. O Azure não oferece processamento de cartão de pagamento como um serviço, portanto não usa um adquirente.

**A quais organizações e comerciantes o PCI DSS se aplica?**

O PCI DSS se aplica a qualquer empresa, independentemente do tamanho ou número de transações, que aceita, transmite ou armazena dados do titular do cartão. Ou seja, se algum cliente pagar a uma empresa usando um cartão de crédito ou débito, os requisitos do PCI DSS se aplicam. As empresas são validadas em um dos quatro níveis com base no volume total de transações em um período de 12 meses. O nível 1 é para empresas que processam mais de 6 milhões de transações por ano; Nível 2 para 1 milhão a 6 milhões de transações; O nível 3 é para 20.000 a 1 milhão de transações; e o nível 4 é para menos de 20.000 transações.

**Por onde inicio os esforços de conformidade da minha organização com o PCI DSS para uma solução implantada no Azure?**

As informações que o PCI Security Standards Council disponibiliza são um bom lugar para saber mais sobre os requisitos de conformidade específicos. O conselho publica o [Guia de Referência Rápida do PCI DSS](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf) para comerciantes e outros envolvidos no processamento de cartões de pagamento. O guia explica como o PCI DSS pode ajudar a proteger um ambiente de transação de cartão de pagamento e como aplicá-lo.

A conformidade envolve vários fatores, incluindo a avaliação dos sistemas e processos não hospedados no Azure. Os requisitos individuais variam com base em quais serviços do Azure são usados ​​e como eles são empregados na solução.

**Há planos para que o OneDrive for Business e o SharePoint Online estejam em conformidade com o PCI DSS fora dos Estados Unidos?**

Atualmente, o OneDrive for Business e o SharePoint Online estão em conformidade com o PCI-DSS apenas nos Estados Unidos (EUA). A Microsoft avaliará os requisitos e cronogramas para regiões fora dos EUA e fornecerá atualizações quando e se outras regiões forem adicionadas ao roteiro.

**O que está no escopo do OneDrive for Business e do SharePoint Online?**

Atualmente, apenas os arquivos e documentos carregados no OneDrive for Business e no SharePoint Online estarão em conformidade com o PCI DSS.

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a>Use o Gerenciador de Conformidade da Microsoft para avaliar o risco

O [Gerenciador de Conformidade da Microsoft](compliance-manager.md) é um recurso do [Centro de conformidade do Microsoft 365](microsoft-365-compliance-center.md) para ajudá-lo a entender a postura de conformidade da sua organização e tomar medidas para ajudar a reduzir os riscos. O Gerenciador de Conformidade oferece um modelo premium para a construção de uma avaliação desse regulamento. Encontre o modelo na página de **modelos de avaliação** no Gerenciador de Conformidade. Aprenda a criar avaliações no [Gerenciador de Conformidade](compliance-manager-assessments.md).

## <a name="resources"></a>Recursos

- [Conselho de Padrões de Segurança (Security Standards Council) do PCI](https://www.pcisecuritystandards.org/)
- [Padrão de Segurança de Dados (Data Security Standard) do PCI](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3-1.pdf)
- [Azure PCI DSS 3.2.1 Blueprint](https://docs.microsoft.com/azure/governance/blueprints/samples/pci-dss-3.2.1/)
- [Guia de Referência (Quick Reference Guide) do PCI DSS](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)
- [Conformidade na Central de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)
