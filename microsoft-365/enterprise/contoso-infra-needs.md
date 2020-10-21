---
title: Infraestrutura de ti e necessidades de negócios da contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda a estrutura básica da infraestrutura de ti local da Contoso e como as necessidades de negócios da empresa são atendidas pela Microsoft 365 para empresas.
ms.openlocfilehash: bc2b34254da01a3d49085082ab8ee8632df2d434
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637170"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a>Infraestrutura de ti e necessidades de negócios da contoso

A Contoso está fazendo a transição de uma infraestrutura de ti centralizada e local para uma configuração inclusiva de nuvem que incorpora cargas de trabalho e aplicativos de produtividade pessoal baseados em nuvem.

## <a name="existing-contoso-it-infrastructure"></a>Infraestrutura existente de ti da contoso

A Contoso usa principalmente a infraestrutura de TI local centralizada, com datacenters de aplicativo na sede de Paris.

A Figura 1 mostra o escritório da sede com datacenters de aplicativo, uma DMZ e a Internet.

![Infraestrutura existente de ti da contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

**Figura 1: infraestrutura de ti existente da contoso**
 
Os datacenters de aplicativo locais hospedam: 

- Aplicativos de linha de negócios personalizados que usam o SQL Server e outros bancos de dados Linux.
- Um conjunto de servidores herdados do SharePoint.
- Servidores de organização e nível de equipe para armazenamento de arquivos.

Além disso, cada escritório central regional tem suporte para um conjunto de servidores com um conjunto semelhante de aplicativos. Esses servidores estão sob o controle dos departamentos regionais de TI.

A capacidade de pesquisa entre os aplicativos e dados desses datacenters multigeográficos continua sendo um desafio.

Na matriz da Contoso DMZ, diferentes conjuntos de servidores fornecem:

- Hospedagem para o site público da Contoso, de onde os clientes podem solicitar produtos, peças, suprimentos e serviços.
- Hospedagem para a extranet do parceiro da Contoso para comunicação e colaboração do parceiro.
- Acesso remoto baseado em rede privada virtual (VPN) à intranet da Contoso e proxy da Web para funcionários na sede de Paris.

## <a name="contoso-business-needs"></a>Necessidades comerciais da contoso

As necessidades corporativas da Contoso se enquadram em cinco categorias principais:

**Produtividade**

- Facilitar a colaboração

  Substitua o email e a colaboração baseada em compartilhamento de arquivos por um modelo online que permita alterações em tempo real em documentos, reuniões online mais fáceis e threads de conversa capturados.
- Aumentar a produtividade de trabalhadores remotos e móveis

  Com muitos funcionários trabalhando de casa ou no campo, substitua a solução de VPN com gargalo por acesso de desempenho a dados e recursos da Contoso na nuvem.
- Aumentar a criatividade e a inovação

  Aproveite os métodos mais recentes de aprendizado visual e desenvolvimento de ideias, incluindo tinta e visualização 3D.

**Segurança**

- Gerenciamento de identidades e acesso

  Impor multifator e outras formas de autenticação e proteger credenciais de conta de administrador e de usuário.

- Proteção contra Ameaças

  Proteção contra ameaças externas, incluindo emails e malware com base no sistema operacional.

- Proteção de informações

  Bloqueie o acesso e criptografe ativos digitais de alto valor, como dados de clientes, especificações de design e fabricação e informações de funcionários.

- Gerenciamento de segurança

  Monitorar a postura de segurança e detectar e responder a ameaças em tempo real.

**Acesso remoto e móvel e parceiros de negócios**

- Melhorar a segurança de funcionários remotos e móveis

  Implemente o seu próprio dispositivo (BYOD) e o gerenciamento de dispositivos pertencentes à empresa para garantir acesso seguro, comportamento de aplicativo correto e proteção de dados da empresa.

- Reduzir a infraestrutura de acesso remoto para os trabalhadores

  Reduza os custos de manutenção e suporte e aprimore o desempenho da solução de acesso remoto movendo recursos comumente acessados para a nuvem.

- Fornecer conectividade melhor e sobrecarga mais baixa para transações B2B (Business-to-susiness)

  Substitua uma extranet de envelhecimento e de parceiro caro por uma solução baseada em nuvem que usa autenticação federada.

**Conformidade**

- Cumprir os requisitos regulamentares regionais

  Garantir a conformidade com normas do setor e regionais para o armazenamento de dados, criptografia, privacidade de dados e regulamentações de dados pessoais, como a regulamentação geral de proteção de dados (RGPD) para a União Européia.

**Gerenciamento**

- Reduzir a sobrecarga de ti para gerenciar o software executado em computadores clientes e dispositivos

  Automatizar a instalação de atualizações no sistema operacional Windows e nos aplicativos do Microsoft 365 para empresas em toda a organização.

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a>Mapear as necessidades de negócios da Contoso para a Microsoft 365 para empresas

O departamento de ti da Contoso determinou o seguinte mapeamento das necessidades de negócios para os recursos do Microsoft 365 E5 antes da implantação:


| Categoria | Necessidade comercial | Microsoft 365 para produtos ou recursos corporativos |
|:-------|:-----|:-----|
| Produtividade |  |  |
|  | Facilitar a colaboração | Microsoft Teams, SharePoint, OneDrive |
|  | Aumentar a produtividade de trabalhadores remotos e móveis | Cargas de trabalho do Microsoft 365 e dados baseados em nuvem |
|  | Aumentar a criatividade e a inovação | Windows Ink, Cortana at Work, PowerPoint |
| Segurança |  |  |
|  | Gerenciamento de identidades e acesso | Contas de administrador global dedicadas com a MFA (autenticação multifator do Azure) e o gerenciamento de identidades (PIM) do Azure Active Directory <BR> Autenticação Multifator para todas as contas de usuário <BR> Acesso Condicional <BR> Windows Hello <BR> Windows Credential Guard |
|  | Proteção contra Ameaças | Advanced Threat Analytics <BR> Windows Defender <BR> Proteção Avançada contra Ameaças <BR> Proteção Avançada contra Ameaças do Office 365 <BR> Investigação e resposta de ameaças da Microsoft 365 <BR> |
|  | Proteção de informações | Proteção de Informações do Azure <BR> Prevenção de Perda de Dados (DLP) <BR> Proteção de Informações do Windows (WIP) <BR> Microsoft Cloud App Security <BR> Microsoft Intune |
|  | Gerenciamento de segurança | Central de Segurança do Azure  <BR> Central de Segurança do Windows Defender |
| Acesso remoto e móvel e parceiros de negócios |  |  |
|  | Aumentar a segurança de trabalhadores remotos e móveis | Microsoft Intune |
|  | Reduzir a infraestrutura de acesso remoto para os trabalhadores | Cargas de trabalho do Microsoft 365 e dados baseados em nuvem |
|  | Melhorar a conectividade e reduzir a sobrecarga de transações B2B | Autenticação federada e recursos baseados em nuvem |
| Conformidade |  |  |
|  | Cumprir os requisitos regulamentares regionais | Recursos do RGPD no Microsoft 365 |
| Gerenciamento |  |  |
|  | Reduzir a sobrecarga de ti para instalar as atualizações do cliente | Anéis de implantação <BR> Atualizações do Windows 10 Enterprise <BR> Atualizações de Aplicativos do Microsoft 365 Apps para empresas |
||||

## <a name="next-step"></a>Próxima etapa

[Saiba mais](contoso-networking.md) sobre a rede local da Contoso Corporation e como ela foi otimizada para acesso e latência a recursos baseados em nuvem da Microsoft 365.

## <a name="see-also"></a>Confira também

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)
