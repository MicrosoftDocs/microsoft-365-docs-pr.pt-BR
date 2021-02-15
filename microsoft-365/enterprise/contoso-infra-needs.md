---
title: Infraestrutura de TI e necessidades comerciais da Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda a estrutura básica da infraestrutura de TI local da Contoso e como as necessidades comerciais da empresa são atendidas pelo Microsoft 365 para empresas.
ms.openlocfilehash: 72d502b5078a1e572eeba27832550af52907e209
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558401"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a>Infraestrutura de TI e necessidades comerciais da Contoso

A Contoso está em transição de uma infraestrutura de TI centralizada local para uma configuração inclusiva na nuvem que incorpora cargas de trabalho e aplicativos de produtividade pessoal baseados em nuvem.

## <a name="existing-contoso-it-infrastructure"></a>Infraestrutura de TI existente da Contoso

A Contoso usa principalmente a infraestrutura de TI local centralizada, com datacenters de aplicativo na sede de Paris.

Aqui está o escritório da matriz com datacenters de aplicativos, uma DMZ e a Internet.

![Infraestrutura de TI existente da Contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

Os datacenters de aplicativo locais hospedam: 

- Aplicativos de linha de negócios personalizados que usam o SQL Server e outros bancos de dados do Linux.
- Um conjunto de servidores herdados do SharePoint.
- Servidores de organização e nível de equipe para armazenamento de arquivos.

Além disso, cada escritório central regional tem suporte para um conjunto de servidores com um conjunto semelhante de aplicativos. Esses servidores estão sob o controle dos departamentos regionais de TI.

A capacidade de pesquisa entre os aplicativos e dados desses datacenters multigeográficos continua sendo um desafio.

Na DMZ da sede da Contoso, diferentes conjuntos de servidores fornecem:

- Hospedagem para o site público da Contoso, do qual os clientes podem solicitar produtos, partes, suprimentos e serviço.
- Hospedagem para a extranet do parceiro da Contoso para comunicação e colaboração do parceiro.
- Acesso remoto baseado em rede privada virtual (VPN) à intranet da Contoso e proxy da Web para funcionários na sede de Paris.

## <a name="contoso-business-needs"></a>Necessidades comerciais da Contoso

As necessidades comerciais da Contoso se enquadram em cinco categorias principais:

**Produtividade**

- Facilitar a colaboração

  Substitua a colaboração baseada em compartilhamento de emails e arquivos por um modelo online que permita alterações em tempo real em documentos, reuniões online mais fáceis e threads de conversa capturados.
- Aumentar a produtividade de trabalhadores remotos e móveis

  Com muitos funcionários trabalhando em casa ou em campo, substitua a solução VPN com gargalo pelo acesso de desempenho aos dados e recursos da Contoso na nuvem.
- Aumentar a criatividade e a inovação

  Aproveite os métodos mais recentes de aprendizado visual e desenvolvimento de ideias, incluindo tinta e visualização 3D.

**Segurança**

- Gerenciamento de identidades e acesso

  Im enforce multifactor and other forms of authentication and protect user and administrator account credentials.

- Proteção contra Ameaças

  Proteção contra ameaças externas, incluindo emails e malware com base no sistema operacional.

- Proteção de informações

  Bloqueie o acesso e criptografe ativos digitais de alto valor, como dados de clientes, especificações de design e fabricação e informações de funcionários.

- Gerenciamento de segurança

  Monitore a postura de segurança e detecte e responda a ameaças em tempo real.

**Acesso remoto e móvel e parceiros de negócios**

- Melhorar a segurança para funcionários remotos e móveis

  Implemente o BYOD (traga seu próprio dispositivo) e o gerenciamento de dispositivos de propriedade da empresa para garantir o acesso seguro, o comportamento correto do aplicativo e a proteção de dados da empresa.

- Reduzir a infraestrutura de acesso remoto para os trabalhadores

  Reduza os custos de manutenção e suporte e melhore o desempenho da solução de acesso remoto movendo recursos comumente acessados para a nuvem.

- Fornecer conectividade melhor e sobrecarga mais baixa para transações B2B (business-to-susiness)

  Substitua uma extranet de parceiros de idade e cara por uma solução baseada em nuvem que usa autenticação federada.

**Conformidade**

- Cumprir os requisitos regulamentares regionais

  Garantir a conformidade com os regulamentos regionais e do setor para armazenamento de dados, criptografia, privacidade de dados e regulamentos de dados pessoais, como o Regulamento Geral sobre a Proteção de Dados (RGPD) para a União Europeia.

**Gerenciamento**

- Menos sobrecarga de IT para gerenciar software em execução em PCs e dispositivos cliente

  Automatize a instalação de atualizações no sistema operacional Windows e no Microsoft 365 Apps para empresas em toda a organização.

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a>Mapear as necessidades comerciais da Contoso para o Microsoft 365 para empresas

O departamento de IT da Contoso determinou o seguinte mapeamento das necessidades comerciais para os recursos do Microsoft 365 E5 antes da implantação:


| Categoria | Necessidade comercial | Produtos ou recursos do Microsoft 365 para empresas |
|:-------|:-----|:-----|
| Produtividade |  |  |
|  | Facilitar a colaboração | Microsoft Teams, SharePoint, OneDrive |
|  | Aumentar a produtividade de trabalhadores remotos e móveis | Cargas de trabalho do Microsoft 365 e dados baseados em nuvem |
|  | Aumentar a criatividade e a inovação | Windows Ink, Cortana at Work, PowerPoint |
| Segurança |  |  |
|  | Gerenciamento de identidades e acesso | Contas dedicadas de administrador global com Azure AD Multi-Factor Authentication (MFA) e PIM (Azure AD Privileged Identity Management) <BR> Autenticação Multifator para todas as contas de usuário <BR> Acesso Condicional <BR> Windows Hello <BR> Windows Credential Guard |
|  | Proteção contra Ameaças | Advanced Threat Analytics <BR> Windows Defender <BR> O que é o Defender para Office 365? <BR> Obter o Microsoft Defender para Office 365 <BR> Investigação e resposta a ameaças do Microsoft 365 <BR> |
|  | Proteção de informações | Proteção de Informações do Azure <BR> Prevenção de Perda de Dados (DLP) <BR> Proteção de Informações do Windows (WIP) <BR> Microsoft Cloud App Security <BR> Microsoft Intune |
|  | Gerenciamento de segurança | Azure Defender  <BR> Central de Segurança do Windows Defender |
| Acesso remoto e móvel e parceiros de negócios |  |  |
|  | Aumentar a segurança de trabalhadores remotos e móveis | Microsoft Intune |
|  | Reduzir a infraestrutura de acesso remoto para os trabalhadores | Cargas de trabalho do Microsoft 365 e dados baseados em nuvem |
|  | Melhorar a conectividade e reduzir a sobrecarga para transações B2B | Autenticação federada e recursos baseados em nuvem |
| Conformidade |  |  |
|  | Cumprir os requisitos regulamentares regionais | Recursos de RGPD no Microsoft 365 |
| Gerenciamento |  |  |
|  | Menos sobrecarga de IT para instalar atualizações do cliente | Atualizações do Windows 10 Enterprise <BR> Atualizações de Aplicativos do Microsoft 365 Apps para empresas |
||||

## <a name="next-step"></a>Próxima etapa

Saiba mais sobre a rede local da Contoso Corporation e como ela foi otimizada para acesso e latência aos recursos [baseados](contoso-networking.md) em nuvem do Microsoft 365.

## <a name="see-also"></a>Confira também

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)
