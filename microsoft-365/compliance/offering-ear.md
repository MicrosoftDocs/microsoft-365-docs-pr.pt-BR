---
title: Normas de administração de exportação dos EUA (EAR)
description: Os serviços do Microsoft Cloud ajudam os clientes a lidar com as normas de administração de exportação dos EUA (EAR) atendem aos requisitos de conformidade e gerenciam o risco de controle de exportação
keywords: Microsoft 365, conformidade, ofertas
localization_priority: None
ms.prod: Microsoft-365-enterprise
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
ms.openlocfilehash: 1adf0bab35c921dd416028747b0309e5ad5f3055
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601958"
---
# <a name="us-export-administration-regulations-ear"></a>Normas de administração de exportação dos EUA (EAR)

## <a name="about-the-ear"></a>Sobre o EAR

O departamento de comércio dos EUA aplica as regulamentações de administração de exportação (EAR) ao [Bureau of Industry and Security (BIS)](https://www.bis.doc.gov/). O EAR controla amplamente os controles na exportação e a reexportação da maioria dos bens, software e tecnologia comercial, incluindo itens de "uso duplo" que podem ser usados para fins comerciais e militares e certos itens de defesa.

A orientação do BIS é que, quando os dados ou o software são carregados na nuvem ou transferidos entre os nós do usuário, o cliente, e não o provedor de nuvem, é o "exportador" que tem a responsabilidade de garantir que as transferências, o armazenamento e o acesso a esses dados ou software está em conformidade com o EAR.

De [acordo com o bis](https://www.bis.doc.gov/index.php/documents/regulation-docs/412-part-734-scope-of-the-export-administration-regulations/file), a *exportação* se refere à transferência de tecnologia protegida ou de dados técnicos para um destino externo ou sua versão para uma pessoa externa nos Estados Unidos (também conhecida como uma *exportação considerada*). O EAR regula de forma ampla:

- Exporta dos Estados Unidos.
- Reexporta ou retransfere de itens de origem americana e certos itens de origem estrangeira com mais de uma parte de *minimis* de conteúdo de US $ Origin.
- Transfere ou divulga para pessoas de outros países.

Os itens sujeitos à EAR podem ser encontrados na lista de controle de comércio (CCL), onde cada item recebe um [número de classificação de controle de exportação exclusivo (ECCN)](https://www.bis.doc.gov/index.php/licensing/commerce-control-list-classification/export-control-classification-number-eccn). Os itens não listados no CCL são designados como EAR99 e a maioria dos produtos comerciais do EAR99 não precisará de uma licença a ser exportada. No entanto, dependendo do destino, usuário final ou uso final do item, até mesmo um item EAR99 pode exigir uma licença de exportação BIS.

A [regra final](https://www.federalregister.gov/documents/2016/06/03/2016-12734/revisions-to-definitions-in-the-export-administration-regulations), publicada em junho de 2016, esclarecida que os requisitos de licenciamento Ear também não se aplicam à transmissão e ao armazenamento de dados técnicos e software não classificados, se foram criptografados de ponta a ponta usando módulos criptográficos com o FIPS 140-2 validados e não foram armazenados intencionalmente em um país com embargo ou na Federação Russa.

## <a name="microsoft-and-the-ear"></a>Microsoft e o EAR

As tecnologias, produtos e serviços da Microsoft estão sujeitos às normas de administração de exportação dos EUA (EAR). Embora não haja nenhuma certificação de conformidade para o EAR, o Microsoft Azure, o Microsoft Azure governo e o Microsoft Office 365 governo (ambientes GCCHigh e DoD) oferecem recursos e ferramentas importantes para ajudar os clientes qualificados a se depararem com o EAR gerenciar exportação controlar riscos e atender seus requisitos de conformidade.

O departamento de comércio dos EUA, que impõe o EAR, levou a posição de que os clientes, não os provedores de serviços de nuvem, como a Microsoft, são considerados exportadores de seus próprios dados de cliente. Embora a maioria dos dados do cliente não seja considerada "tecnologia" ou "dados técnicos", sujeita aos controles de exportação EAR, os serviços de nuvem em escopo da Microsoft são estruturados para ajudar os clientes a gerenciar e reduzir significativamente os riscos de controle de exportação possíveis. A Microsoft geralmente, mas não exclusivamente, recomenda o uso de seus serviços de nuvem governamental para clientes qualificados. Com o planejamento apropriado, os clientes podem usar as seguintes ferramentas e seus próprios procedimentos internos para ajudar a garantir total conformidade com os controles de exportação dos EUA.

- **Controles no local dos dados**. Os clientes têm visibilidade de onde seus dados são armazenados e acesso a ferramentas robustas para restringir o armazenamento. Portanto, eles podem garantir que seus dados sejam armazenados nos Estados Unidos e minimizar a transferência de tecnologia controlada ou de dados técnicos fora dos Estados Unidos. Além disso, os dados do cliente não são armazenados em um local de conformidade, consistentes com as proibições de EAR em que os dados são "rearmazenados intencionalmente": nenhum Datacenter do Azure está localizado em qualquer um dos 25 países D:5 do grupo ou na Federação Russa.
- **Criptografia de ponta a ponta**. Aproveitando a criptografia de ponta a ponta, o porto seguro para locais de armazenamento físico especificado na EAR, os serviços de nuvem dentro do escopo da Microsoft oferecem recursos de criptografia que podem ajudar a proteger contra riscos de controle de exportação. Eles também oferecem aos clientes uma [ampla variedade de opções de criptografia de dados](https://aka.ms/Azure-Encryption-Overview) em trânsito e em repouso, e a flexibilidade para escolher entre as opções de criptografia.
- **Ferramentas e protocolos para impedir a exportação considerada não autorizada**. O uso de criptografia também ajuda a proteger contra uma possível exportação (ou considerado reexportação) no EAR, porque, mesmo que uma pessoa que não seja a dos EUA tenha acesso a dados criptografados, nada será revelado se não puder ler ou compreender os dados enquanto estiverem criptografados; Portanto, não há "lançamento" de dados controlados.

## <a name="microsoft-in-scope-cloud-services"></a>Serviços de nuvem no escopo da Microsoft

- [Azure e Azure Governamental](https://aka.ms/AzureCompliance)
- [Governo do Office 365 (GCC-elevado e DoD)](https://aka.ms/Office-365-Export-Controls)
- Intune

## <a name="how-to-implement"></a>Como implementar

Visão geral dos controles de exportação dos EUA e orientações para os clientes que estão avaliando suas obrigações no EAR.

- [Azure](https://aka.ms/Azure-Export-Controls)
- [Office 365](https://aka.ms/Office-365-Export-Controls)

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**O que devo fazer para cumprir com os controles de exportação ao usar os serviços de nuvem da Microsoft?**

Na EAR, quando os dados são carregados para um servidor de nuvem, como a nuvem da Microsoft, o cliente que possui os dados, e não o provedor de serviços de nuvem, é considerado como o Exporter. Por esse motivo, o proprietário dos dados, ou seja, o cliente da Microsoft, deve avaliar cuidadosamente como o uso da nuvem da Microsoft pode complicar os controles de exportação e determinar se qualquer um dos dados que deseja usar ou armazenar pode estar sujeito a controles EAR e, em caso afirmativo, quais controles se aplicam. Saiba mais sobre como o [Azure](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=c24c11f2-2cd4-444a-9160-19762855ad3a&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers) e o [Office 365](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE1s5kI) Cloud Services podem ajudar os clientes a garantir sua total conformidade com os controles de exportação dos EUA.

**As tecnologias, produtos e serviços da Microsoft estão sujeitos ao EAR?**

A maioria das tecnologias, produtos e serviços da Microsoft:

- Não estão sujeitos à EAR e, portanto, não estão na lista de controle de comércio e não têm ECCN;
- Ou eles estão qualificados para o mercado de massa do EAR99 ou do 5D992 para AutoClassificação pela Microsoft e podem ser exportados para países não embargados sem uma licença como nenhuma licença necessária (NLR).

Dito isso, alguns produtos da Microsoft foram atribuídos a um ECCN que pode ou não exigir uma licença. Consulte o advogado ou o departamento jurídico para determinar o tipo de licença apropriado e os países qualificados para fins de exportação.

**Qual é a diferença entre o tráfego de EAR e o Internacional de ITAR (normas de braços)?**

Os principais controles de exportação dos EUA com o aplicativo mais amplo são os EAR, administrados pelo departamento de comércio dos EUA. O EAR é aplicável a itens de uso duplo que possuem aplicativos comerciais e militares e a itens com aplicativos puramente comerciais.

Os Estados Unidos também têm regulamentações de controle de exportação separadas e mais especializadas, como o ITAR, que controla a tecnologia e os itens mais confidenciais. Administrada pelo departamento de estado dos EUA, elas impõem controles na exportação, importação temporária, re-exportação e transferência de vários itens de militares, defesa e inteligência (também conhecidos como "artigos de defesa"), incluindo dados técnicos relacionados.

## <a name="resources"></a>Recursos

- [Exportando produtos da Microsoft: visão geral](https://www.microsoft.com/exporting/overview.aspx)
- [Exportando produtos da Microsoft: perguntas frequentes](https://www.microsoft.com/exporting/faq.aspx)
- [Exportar produtos da Microsoft: pesquisa de produto](https://www.microsoft.com/exporting/exporting-information.aspx)
- [Exportar restrições de criptografia](https://docs.microsoft.com/windows/uwp/security/export-restrictions-on-cryptography)
- [Microsoft e FIPS 140-2](offering-fips-140-2.md)
- [Microsoft e ITAR](offering-itar.md)
- [Conformidade na Central de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)
