---
title: Padrão de Segurança de Dados (DSS) da Indústria de Cartões de Pagamento (PCI)
description: O Azure, o SharePoint Online e o OneDrive for Business estão em conformidade com os Padrões de Segurança de Dados da Indústria de Cartões de Pagamento Level 1 versão 3.2.
keywords: Microsoft 365, conformidade, ofertas
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 1b0e4ae933591f41c99a4b88d31eca6504322c92
ms.sourcegitcommit: b2197dbf723d11992bbad568a84df3ef3cff421d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "39218690"
---
# <a name="compliance-offering-payment-card-industry-pci-data-security-standard-dss"></a>Oferta de conformidade: Padrão de Segurança de Dados (DSS) da Indústria de Cartões de Pagamento (PCI)

## <a name="pci-dss-overview"></a>Visão geral do PCI DSS

O DSS (Padrão de Segurança de Dados) da PCI (Indústria de Cartões de Pagamento) é um padrão de segurança de informação global criado para prevenir fraudes por meio do maior controle de dados de cartões de crédito. Empresas de todos os tamanhos que aceitam cartões de pagamento das cinco principais marcas de cartão de crédito — Visa, MasterCard, American Express, Discover e JCB (Japan Credit Bureau) — devem cumprir os padrões PCI DSS. A conformidade com o PCI DSS é obrigatória para toda empresa que armazene, processe ou transmita dados de pagamento e do titular do cartão.

## <a name="microsoft-and-pci-dss"></a>Microsoft e PCI DSS

A Microsoft completou uma avaliação anual de PCI DSS por um avaliador qualificado de segurança (Qualified Security Assessor - QSA). Os auditores avaliaram os ambientes do Microsoft Azure, do Microsoft OneDrive for Business e do Microsoft SharePoint Online, que inclui validar a infraestrutura, desenvolvimento, operações, gerenciamento, suporte e serviços dentro do escopo. O PCI DSS especifica quatro níveis de conformidade de acordo com o volume de transações. O Azure, o OneDrive for Business e o SharePoint Online tem certificação de conformidade com o PCI DSS versão 3.2 como Service Provider Level 1 (o maior volume de transações — mais de 6 milhões por ano).

A avaliação resulta em um Certificado de Conformidade (Attestation of Compliance - AoC), que está disponível para clientes e um Relatório sobre Conformidade (Report on Compliance - RoC) emitidos pelo QSA. O período de vigência da conformidade tem início no momento da aprovação na auditoria e recebimento do AoC do avaliador e termina um ano após a data de assinatura do AoC. 

Os clientes que desejam desenvolver um ambiente do titular do cartão ou um serviço de processamento de cartões podem utilizar essas validações em muitas das partes subjacentes, reduzindo assim o trabalho e os custos associados à obtenção de sua própria certificação PCI DSS.

É importante entender que o status de conformidade do Azure, do OneDrive for Business e do SharePoint Online com o PCI DSS não se converte automaticamente na certificação PCI DSS para os serviços que os clientes desenvolvam ou hospedem nessas plataformas. Os clientes são responsáveis por garantir sua conformidade com os requisitos do PCI DSS.

## <a name="microsoft-in-scope-cloud-services"></a>Serviços em nuvem no escopo da Microsoft

- [Azure e Azure Governamental](https://aka.ms/AzureCompliance)
- Segurança no aplicativo na nuvem
- Serviço de nuvem do Flow como um serviço autônomo ou incluído em um plano ou pacote do Office 365 ou do Dynamics 365.
- Graph
- Intune
- Serviço de nuvem do PowerApps como um serviço autônomo ou incluído em um plano ou pacote do Office 365 ou do Dynamics 365
- Serviço de nuvem do Power BI como um serviço autônomo ou incluído em um plano ou pacote do Office 365
- OneDrive for Business e SharePoint Online (somente nos Estados Unidos)

## <a name="audit-reports-and-certificates"></a>Auditorias, relatórios e certificados

- [Atestado de Conformidade (AoC) PCI DSS do Azure](https://aka.ms/azure-pci)
- [Atestado de Conformidade ( AoC) PCI DSS do OneDrive for Business e SharePoint Online](https://aka.ms/spo-pci)

## <a name="get-your-pci-dss-solution-running-on-azure"></a>Execute sua solução PCI DSS no Azure

Crie e implante sua solução PCI DSS na nuvem ainda mais rápido com o Blueprint PCI DSS de Segurança e Conformidade do Azure. Obtenha arquiteturas de referência, diretrizes de implantação, mapeamentos de implementação de controles, scripts automáticos e mais. [Comece a usar o Blueprint PCI DSS do Azure](https://aka.ms/pciblueprint)

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Por que a página de rosto do Atestado de Conformidade (AoC) mostra “Junho de 2018”?**

A data de junho de 2018 na página de rosto é de quando o modelo de AoC foi publicado. Consulte a data da avaliação na Seção 2.

**Por que há vários Atestados de Conformidade (AoCs) do Azure?**

O pacote Azure AoC tem AoCs correspondentes à nuvem pública do Azure, da Alemanha e do Governo. Os clientes devem usar o AoC que corresponde ao seu ambiente do Azure.  

**Qual é a relação entre PA DSS e PCI DSS?**

O Padrão de Segurança de Dados em Aplicativos de Pagamento (Payment Application Data Security Standard - PA DSS) é um conjunto de requisitos que cumpre o PCI DSS e substitui as Práticas Recomendadas para Aplicativos de Pagamento do Visa (Visa’s Payment Application Best Practices) e consolida os requisitos de conformidade dos outros emissores de cartões principais. O PA DSS ajuda os fornecedores de software a desenvolver aplicativos de terceiros para armazenar, processar ou transmitir dados de pagamento do titular do cartão como parte do processo de autorização ou pagamento do cartão. Os varejistas precisam usar aplicativos com a certificação PA DSS para obter efetivamente a conformidade com o PCI DSS. O PA DSS não se aplica ao Azure.

**O que é um adquirente? O Azure usa um?**

Os adquirentes são bancos ou outras entidades que processam transações de cartões de pagamento. O Azure não oferece o serviço de processamento de cartões de pagamento e, portanto, não utiliza um adquirente.

**A quais organizações e comerciantes o PCI DSS se aplica?**

O PCI DSS se aplica a qualquer empresa, independentemente do tamanho ou do número de transações que aceite, transmita ou armazene dados de titulares de cartões. Ou seja, se qualquer cliente pagar uma empresa usando um cartão de crédito ou débito, os requisitos do PCI DSS se aplicarão. As empresas são validadas em um dos quatro níveis de acordo com o volume total de transações durante um período de 12 meses. O Level 1 engloba empresas que processam mais de 6 milhões de transações por ano; o Level 2, de 1 milhão a 6 milhões de transações; o Level 3, de 20.000 a 1 milhão de transações e o Level 4, para menos de 20.000 transações.

**Por onde inicio as iniciativas de conformidade de minha organização com o PCI DSS para uma solução implantada no Azure?**

As informações disponibilizadas pelo Conselho de Padrões de Segurança (Security Standards Council) do PCI são uma ótima fonte para conhecer os requisitos de conformidade específicos. O conselho publica o [Guia de Referência (Quick Reference Guide) do PCI DSS](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf) para comerciantes e outras pessoas envolvidas no processamento de cartões de pagamento. Esse guia explica como o PCI DSS pode ajudar a proteger um ambiente de transações de cartões de pagamento e como aplicá-lo.

A conformidade envolve diversos fatores, incluindo a avaliação de sistemas e processos não hospedados no Azure. Os requisitos individuais variam de acordo com os serviços do Azure que são usados e como eles são empregados dentro da solução.

**Há planos para que o OneDrive for Business e o SharePoint Online estejam em conformidade com o PCI DSS fora dos Estados Unidos?**

Atualmente, o OneDrive for Business e o SharePoint Online estão em conformidade com o PCI DSS somente nos Estados Unidos (EUA). A Microsoft avaliará os requisitos e as linhas do tempo em outras regiões fora dos EUA e fornecerá atualizações quando e se outras regiões forem adicionadas ao roteiro.

**O que está dentro do escopo para o OneDrive for Business e o SharePoint Online?**

Atualmente, apenas os arquivos e documentos carregados no OneDrive for Business e no SharePoint Online estarão em conformidade com o PCI DSS.

## <a name="resources"></a>Recursos

- [Conselho de Padrões de Segurança (Security Standards Council) do PCI](https://www.pcisecuritystandards.org/)
- [Padrão de Segurança de Dados (Data Security Standard) do PCI](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3-1.pdf)
- [Responsibility Matrix do Azure PCI DSS 3.2.1](https://aka.ms/pciresponsibilitymatrix)
- [Guia de Referência (Quick Reference Guide) do PCI DSS](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)
- [Conformidade no Microsoft Trust Center](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>Baixar informações de oferta

Precisa do documento informativo desta oferta? Baixe o [PDF](https://download.microsoft.com/download/3/7/7/377F1BBC-37D5-4677-AB4A-7C01D089CA67/PCI_DSS_Compliance_Backgrounder.pdf).
