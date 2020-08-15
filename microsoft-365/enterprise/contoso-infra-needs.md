---
title: Infraestrutura de TI e necessidades comerciais da Contoso
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
description: Entenda a estrutura básica da infraestrutura de ti local da Contoso e como suas necessidades comerciais foram atendidas pela Microsoft 365 para empresas.
ms.openlocfilehash: 3dd744a8d936307c61303bf8ba0f2f198af59d91
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685825"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a>Infraestrutura de TI e necessidades comerciais da Contoso

A Contoso vem fazendo a transição de uma infraestrutura de TI centralizada local para uma infraestrutura incluindo nuvem que incorpora cargas de trabalho e aplicativos de produtividade pessoal baseados em nuvem.

## <a name="contosos-existing-it-infrastructure"></a>Infraestrutura de TI da Contoso

A Contoso usa principalmente a infraestrutura de TI local centralizada, com datacenters de aplicativo na sede de Paris.

A Figura 1 mostra um escritório da sede com datacenters de aplicativo, uma DMZ e a Internet.

![Infraestrutura de TI da Contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

**Figura 1: Atual infraestrutura de TI da Contoso**
 
Os datacenters de aplicativo locais hospedam: 

- Linha personalizada de aplicativos de negócios que usam o SQL Server e outros bancos de dados do Linux.
- Um conjunto de servidores herdados do SharePoint.
- Servidores de organização e nível de equipe para armazenamento de arquivos.

Além disso, cada escritório central regional tem suporte para um conjunto de servidores com um conjunto semelhante de aplicativos. Esses servidores estão sob o controle dos departamentos regionais de TI.

A capacidade de pesquisa entre os aplicativos e dados desses datacenters multigeográficos continua sendo um desafio.

Na DMZ da sede da Contoso, diferentes conjuntos de servidores oferecem:

- Hospedagem para o site público da Contoso, do qual os clientes podem solicitar produtos, peças, suprimentos ou serviço.
- Hospedagem para a extranet do parceiro da Contoso para comunicação e colaboração do parceiro.
- Acesso remoto baseado em rede privada virtual (VPN) à intranet da Contoso e proxy da Web para funcionários na sede de Paris.

## <a name="contosos-business-needs"></a>Necessidades comerciais da Contoso

As necessidades comerciais da Contoso são classificadas em cinco categorias principais.

Produtividade:

- Facilitar a colaboração

  Substitua a colaboração baseada em compartilhamento de emails e arquivos por um modelo online que permita alterações em tempo real em documentos, reuniões online simplificadas e threads de conversa capturados.
- Aumentar a produtividade de trabalhadores remotos e móveis

  Com muitos funcionários trabalhando em casa ou em campo, substitua a solução de VPN com gargalo pelo acesso de alto desempenho aos dados e recursos da Contoso na nuvem.
- Aumentar a criatividade e a inovação

  Aproveite os métodos mais recentes de aprendizado visual e desenvolvimento de ideias, incluindo tinta e visualização 3D.

Segurança:

- Gerenciamento de identidades e acesso

  Implemente a autenticação multifator e outras formas de autenticação e proteja as credenciais das contas de usuário e administrador.

- Proteção contra Ameaças

  Proteção contra ameaças externas, incluindo emails e malware com base no sistema operacional.

- Proteção de informações

  Bloqueie o acesso e criptografe ativos digitais de alto valor, como dados de clientes, especificações de design e fabricação e informações de funcionários.

- Gerenciamento de segurança

  Monitore a postura de segurança e detecte e responda a ameaças em tempo real.

Acesso remoto e móvel e parceiros de negócios:

- Aumentar a segurança de trabalhadores remotos e móveis

  Estabeleça o BYOD (Traga seu próprio dispositivo) e o gerenciamento de dispositivos da empresa para garantir o acesso seguro, o comportamento correto do aplicativo e a proteção de dados da empresa.

- Reduzir a infraestrutura de acesso remoto para os trabalhadores

  Reduza os custos de manutenção e suporte e melhore o desempenho da solução de acesso remoto, movendo recursos comumente acessados para a nuvem.

- Fornecer conectividade aprimorada e sobrecarga mais baixa para transações B2B (entre empresas)

  Substitua a extranet antiga e dispendiosa do parceiro por uma solução baseada em nuvem que use autenticação federada.

Conformidade:

- Cumprir os requisitos regulamentares regionais

  Entre e permaneça em conformidade com os regulamentos regionais e do setor de armazenamento de dados, criptografia, privacidade de dados e regulamentos de dados pessoais, como o Regulamento Geral sobre a Proteção de Dados (RGPD) da União Europeia.

Gerenciamento:

- Reduzir a sobrecarga de TI para gerenciar software executado em PCs e dispositivos de clientes

  Automatize a instalação de atualizações no sistema operacional Windows e no Microsoft 365 Apps para Grandes Empresas em toda a organização.

## <a name="mapping-contosos-business-needs-to-microsoft-365-for-enterprise"></a>Mapear as necessidades de negócios da Contoso para a Microsoft 365 para empresas

O departamento de TI da Contoso determinou o seguinte mapeamento das necessidades comerciais dos recursos do Microsoft 365 E5 antes da implantação:


| Categoria | Necessidade comercial | Microsoft 365 para produtos ou recursos corporativos |
|:-------|:-----|:-----|
| Produtividade |  |  |
|  | Facilitar a colaboração | Microsoft Teams, SharePoint, OneDrive |
|  | Aumentar a produtividade de trabalhadores remotos e móveis | Cargas de trabalho do Microsoft 365 e dados baseados em nuvem |
|  | Aumentar a criatividade e a inovação | Windows Ink, Cortana at Work, PowerPoint |
| Segurança |  |  |
|  | Gerenciamento de identidades e acesso | Contas de administrador globais dedicadas com Autenticação Multifator do Azure e Azure AD Privileged Identity Management (PIM) <BR> Autenticação Multifator para todas as contas de usuário <BR> Acesso Condicional <BR> Windows Hello <BR> Windows Credential Guard |
|  | Proteção contra Ameaças | Advanced Threat Analytics <BR> Windows Defender <BR> Proteção Avançada contra Ameaças <BR> Proteção Avançada contra Ameaças do Office 365 <BR> Investigação e resposta de ameaças da Microsoft 365 <BR> |
|  | Proteção de informações | Proteção de Informações do Azure <BR> Prevenção de Perda de Dados (DLP) <BR> Proteção de Informações do Windows (WIP) <BR> Microsoft Cloud App Security <BR> Microsoft Intune |
|  | Gerenciamento de segurança | Central de Segurança do Azure  <BR> Central de Segurança do Windows Defender |
| Acesso remoto e móvel e parceiros de negócios |  |  |
|  | Aumentar a segurança de trabalhadores remotos e móveis | Microsoft Intune |
|  | Reduzir a infraestrutura de acesso remoto para os trabalhadores | Cargas de trabalho do Microsoft 365 e dados baseados em nuvem |
|  | Fornecer conectividade aprimorada e sobrecarga mais baixa para transações B2B | Autenticação federada e recursos baseados em nuvem |
| Conformidade |  |  |
|  | Cumprir os requisitos regulamentares regionais | Recursos do RGPD no Microsoft 365 |
| Gerenciamento |  |  |
|  | Reduzir a sobrecarga da TI para instalar as atualizações do cliente | Anéis de implantação <BR> Atualizações do Windows 10 Enterprise <BR> Atualizações de Aplicativos do Microsoft 365 Apps para empresas |
||||

## <a name="next-step"></a>Próxima etapa

[Saiba mais](contoso-networking.md) sobre a rede local da Contoso Corporation e como ela foi otimizada para acesso e latência aos recursos baseados na nuvem do Microsoft 365.

## <a name="see-also"></a>Confira também

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)
