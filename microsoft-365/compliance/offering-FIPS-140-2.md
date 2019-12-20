---
title: Publicação 140-2 do FIPS (Federal Information Processing Standard)
description: A Microsoft certifica que seus módulos criptográficos estão em conformidade com o padrão norte-americano de processamento de informações.
keywords: Microsoft 365, conformidade, ofertas
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: c87618648c4b34553312a91d5633164fee316e52
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40804994"
---
# <a name="federal-information-processing-standard-fips-publication-140-2"></a>Publicação 140-2 do FIPS (Federal Information Processing Standard)

## <a name="fips-140-2-standard-overview"></a>Visão geral do FIPS 140-2 Standard

A publicação 140-2 do FIPS (Federal Information Processing Standard) é um padrão do governo dos EUA que define os requisitos mínimos de segurança para módulos de criptografia em produtos de tecnologia da informação, conforme definido na seção 5131 das informações Lei de reforma da tecnologia de gerenciamento de 1996.

O CMVP ( [Cryptographic Module Validation Program](https://csrc.nist.gov/Projects/cryptographic-module-validation-program) ), um esforço conjunto do U.S. National Institute of Standards and Technology (NIST) e o centro canadense de segurança (CCCS), valida módulos criptográficos para os *requisitos de segurança para módulos de criptografia* padrão (ou seja, FIPS 140-2) e padrões de criptografia FIPS relacionados. Os requisitos de segurança do FIPS 140-2 abrangem 11 áreas relacionadas ao design e à implementação de um módulo de criptografia. O laboratório de tecnologia da informação NIST opera um programa relacionado que valida os algoritmos criptográficos aprovados pelo FIPS no módulo.

## <a name="microsofts-approach-to-fips-140-2-validation"></a>Abordagem da Microsoft para a validação do FIPS 140-2

A Microsoft mantém um compromisso ativo para atender aos requisitos 140-2, com módulos criptográficos validados desde o início do padrão em 2001. A Microsoft valida seus módulos criptográficos sob o National Institute of Standards and Technology (NIST) [Cryptographic Module Validation Program](https://csrc.nist.gov/Projects/cryptographic-module-validation-program) (CMVP). Vários produtos da Microsoft, incluindo vários serviços de nuvem, usam esses módulos de criptografia.

Para obter informações técnicas sobre módulos de criptografia do Microsoft Windows, a política de segurança para cada módulo e o catálogo de detalhes do certificado do CMVP, consulte o [Windows and Windows Server FIPS 140-2 Content](https://aka.ms/AA6ehud).

## <a name="microsoft-in-scope-cloud-services"></a>Serviços de nuvem no escopo da Microsoft

Embora a atual orientação de implementação do CMVP FIPS 140-2 impede uma validação FIPS 140-2 para um serviço de nuvem propriamente dito; os provedores de serviços de nuvem podem optar por obter e operar os módulos de criptografia validados pelo FIPS 140 para os elementos computacionais que compõem o serviço na nuvem. Os serviços online da Microsoft que incluem componentes, que foram validados pelo FIPS 140-2, entre outros:

- [Azure e Azure Governamental](https://docs.microsoft.com/azure/azure-government/documentation-government-plan-security)
- [Dynamics 365 e Dynamics 365 governamental](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-microsoft-dynamics-365)
- [Office 365, Office 365 U.S. Government e Office 365 U.S. Government Defense](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-risks-and-protections)

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Qual é a diferença entre "FIPS 140 validado" e "compatível com FIPS 140"?**

"FIPS 140 validado" significa que o módulo criptográfico ou um produto que incorpora o módulo foi validado ("certificado") pelo CMVP como atender aos requisitos FIPS 140-2. "Compatível com FIPS 140" é um termo da indústria para os produtos de ti que dependem de produtos validados pelo FIPS 140 para funcionalidade criptográfica.

**Quando a Microsoft realiza uma validação FIPS 140?**

A cadência para iniciar uma validação de módulo se alinha com as atualizações de recurso do Windows 10 e do Windows Server. À medida que o setor de software evoluiu, os sistemas operacionais são lançados com mais frequência, com atualizações de software mensais. A Microsoft efetua a validação de versões de recursos, mas entre as versões, busca minimizar as alterações nos módulos de criptografia.

**Quais computadores estão incluídos em uma validação FIPS 140?**

A Microsoft valida módulos criptográficos em um exemplo representativo de configurações de hardware executando o Windows 10 e o Windows Server. É prática da indústria comum aceitar esta validação FIPS 140-2 quando um ambiente usa hardware, que é semelhante aos exemplos usados para o processo de validação.

**Há vários módulos listados no site do NIST. Como saber o que se aplica à Agência?**

Se for necessário usar módulos de criptografia validados por meio de FIPS 140-2, você precisará verificar se a versão que você usa aparece na lista de validação. O CMVP e a Microsoft mantêm uma lista de módulos criptográficos validados, organizados por versão do produto, juntamente com instruções para identificar quais módulos estão instalados em um sistema Windows. Para obter mais informações sobre como configurar sistemas para serem compatíveis, confira o [conteúdo Windows e Windows Server FIPS 140-2](https://aka.ms/AA6ehud).

**O que o "quando operado no modo FIPS" significa um certificado?**

Essa limitação informa ao leitor que as regras de configuração e segurança necessárias devem ser seguidas para usar o módulo criptográfico de forma consistente com a política de segurança FIPS 140-2. Cada módulo tem sua própria política de segurança, uma especificação precisa das regras de segurança sob as quais funcionará — e emprega algoritmos de criptografia aprovados, gerenciamento de chaves criptográficas e técnicas de autenticação. As regras de segurança são definidas na política de segurança de cada módulo. Para obter mais informações, incluindo links para a política de segurança de cada módulo validado por meio do CMVP, consulte o [Windows and Windows Server FIPS 140-2 Content](https://aka.ms/AA6ehud).

**O FedRAMP requer a validação FIPS 140-2?**

Sim, o programa de gerenciamento de riscos e autorização federal (FedRAMP) se baseia nas linhas de base de controle definidas pelo [NIST SP 800-53 Revisão 4](https://nvd.nist.gov/800-53/Rev4/), incluindo a [proteção de criptografia SC-13](https://nvd.nist.gov/800-53/Rev4/control/SC-13) que obriga o uso de criptografia validada por FIPS ou da criptografia aprovada por NSA.

**Como o Microsoft Azure oferece suporte a FIPS 140-2?**

O Azure é criado com uma combinação de hardware, sistemas operacionais comercialmente disponíveis (Linux e Windows) e versão específica do Azure do Windows. Por meio do SDL ( [ciclo de vida do desenvolvimento de segurança](https://www.microsoft.com/securityengineering/sdl/) da Microsoft), todos os serviços do Azure usam algoritmos aprovados FIPS 140-2 para segurança de dados, pois o sistema operacional usa algoritmos aprovados FIPS 140-2 enquanto opera em uma nuvem de escala Hyper.

**Posso usar a adesão da Microsoft ao FIPS 140-2 no processo de certificação da Agência?**

Para estar em conformidade com o FIPS 140-2, o sistema deve estar configurado para ser executado em um modo de operação aprovado pelo FIPS, que inclui a garantia de que um módulo de criptografia Use apenas algoritmos aprovados pelo FIPS. Para obter mais informações sobre como configurar sistemas para serem compatíveis, confira o [conteúdo Windows e Windows Server FIPS 140-2](https://aka.ms/AA6ehud).

**Qual é a relação entre o FIPS 140-2 e o critério comum?**

Estes são dois padrões de segurança separados com finalidades diferentes, mas complementares. O FIPS 140-2 foi projetado especificamente para validar os módulos de criptografia de software e hardware, enquanto os critérios comuns foram projetados para avaliar as funções de segurança nos produtos de software e hardware de ti. As avaliações comuns de critérios geralmente dependem de validações FIPS 140-2 para garantir que a funcionalidade básica de criptografia seja implementada corretamente.

## <a name="resources"></a>Recursos

- [Requisitos de segurança do FIPS pub 140-2 para módulos de criptografia](https://csrc.nist.gov/publications/fips/fips140-2/fips1402.pdf)
- [Programa de validação do módulo de criptografia do NIST](https://csrc.nist.gov/groups/STM/cmvp/index.html)
- [Windows, Windows Server e FIPS 140-2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation)
- [Conformidade no Centro de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>Baixar informações de oferta

Precisa do documento informativo desta oferta? Baixe o [PDF](https://download.microsoft.com/download/B/7/2/B7226B91-1A56-41E4-AC01-43FCFEE50B7F/FIPS_Compliance_Backgrounder.pdf).