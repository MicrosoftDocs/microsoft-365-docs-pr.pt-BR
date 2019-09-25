---
title: Mitigações de Gerenciamento de Continuidade de Negócios do Microsoft 365 Enterprise
author: chrfox
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Alguns exemplos de mitigações para cenários de incidentes de serviço do Microsoft 365.
ms.openlocfilehash: 830d8c3ac9993185bbb60ff15c08903e298b9b78
ms.sourcegitcommit: 7690c8bfdea6e6d245cfa7c5b09b913b092cde0a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2019
ms.locfileid: "37122261"
---
# <a name="service-incident-mitigation-strategies"></a>Estratégias de mitigação de incidentes de serviço

Aqui estão algumas estratégias e cenários que mostram como minimizar o impacto de um incidente de serviço do Microsoft 365 em seu processo de negócios.

## <a name="service-incident-scenarios-and-potential-mitigations"></a>Cenários de incidentes de serviço e possíveis mitigações

|Dependência do Microsoft 365|possíveis mitigações|
|---------|---------|
|O sistema de gerenciamento de incidentes se baseia no Exchange Online para envolver engenheiros e gerenciadores de incidentes em chamada.|Certifique-se de que seu sistema de gerenciamento de incidentes proporciona suporte para as comunicações multicanais, como email paralelo, chamada telefônica e notificações por SMS; caso a pessoa principal em chamada não responda, o sistema acionará automaticamente as hierarquias da árvore de chamadas, envolvendo a pessoa em backup. Também inclui métodos de contato de backup em todas as notificações, assim os métodos de comunicação de backup são inseridos a fim de facilitar a referência. É possível usar métodos de comunicação alternativos, como o Yammer, em colaborações de emergência, se o serviço de gerenciamento de incidentes não estiver disponível.|
|O Microsoft Teams é usado para armazenar arquivos acessados pelo cliente.|O Teams armazena arquivos carregados no cliente em uma biblioteca de documentos do SharePoint Online. Os arquivos ainda podem ser acessados por meio do SharePoint Online. Treine os usuários em locais de arquivos no SharePoint Online.|
|A chamada de conferências do Microsoft Teams é utilizada nas comunicações em geral e na triagem de gerenciamento de incidentes.|Estabeleça uma solução de conferência de backup com um provedor terceirizado.|
|Os telefones VoIP são usados como um método secundário de comunicação.|Implemente telefones que não sejam VoIP e que possam executar chamadas PSTN, especialmente para centros de operações de rede e serviço durante incidentes. Adicione os telefones celulares dos funcionários ao diretório da empresa para permitir o contato com funcionários essenciais.|
|É possível utilizar o OneDrive for Business no armazenamento de arquivos e na produtividade do usuário. Os [Arquivos Sob Demanda](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/OneDrive-Files-On-Demand-For-The-Enterprise/ba-p/117234) estão configurados para liberar espaço nas unidades locais de usuários.|As políticas para sincronização de grupos de suprimentos do OneDrive permitem que os administradores exijam a sincronização local de conteúdo específico ou a liberação de espaço quando necessário. Para reduzir o risco da inacessibilidade de documentos, configure essa política para sincronizar documentos críticos no local. Treine os usuários para aplicar manualmente a configuração "sempre manter neste dispositivo" no caso de documentos importantes.|
|A comunicação de interrupções de negócios com clientes e fornecedores depende do Exchange Online.|É possível usar as redes sociais públicas de terceiros como uma alternativa no caso de comunicações em massa.

## <a name="leveraging-mobile-app-access"></a>Aproveitando o acesso de aplicativos móveis

À medida que a mobilidade se proliferou, há novos meios para se manter conectado e os aplicativos móveis do Microsoft 365 podem ser um componente fundamental em sua estratégia de resiliência. Como eles se conectam aos serviços de nuvem pela rede do provedor de telefonia celular, não dependem da infraestrutura de rede de sua organização.

Vamos usar o Outlook como exemplo. Os usuários podem se conectar a suas caixas de correio do Exchange Online por diferentes protocolos de rede (HTTPS ou MAPI), dependendo do aplicativo de email em uso. Se houver um incidente de serviço que envolva um dos protocolos do MAPI, por exemplo, para uma instância que o cliente da área de trabalho usa, os usuários ainda poderão acessar a caixa de correio por meio do aplicativo móvel do Outlook ou do Outlook na Web.
  
Caso você decida permitir que os usuários se conectem aos serviços do Microsoft 365 por meio de seus dispositivos móveis, você pode usar o Microsoft Intune para configurar e gerenciar esses dispositivos de forma segura. Quando as contas de usuários e os dispositivos estiverem registrados na solução de gerenciamento móvel, certifique-se de que os aplicativos foram baixados e configurados.
