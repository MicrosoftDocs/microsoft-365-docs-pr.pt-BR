---
title: Arquiteturas do Microsoft Azure para o SharePoint 2013
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
- seo-marvel-apr2020
ms.assetid: 98fc1006-9399-4ff0-a216-c7c05820d822
description: Saiba quais tipos de soluções do SharePoint 2013 podem ser hospedadas em máquinas virtuais do Microsoft Azure e como configurar o Azure para hospedar uma.
ms.openlocfilehash: eed74e2dcbe383f0f63e7f6ea2fc70fe7b51b1b3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924171"
---
# <a name="microsoft-azure-architectures-for-sharepoint-2013"></a>Arquiteturas do Microsoft Azure para o SharePoint 2013

O Azure é um bom ambiente para hospedar uma solução do SharePoint Server 2013. Na maioria dos casos, recomendamos o Microsoft 365, mas um farm do SharePoint Server hospedado no Azure pode ser uma boa opção para soluções específicas. Este artigo descreve como arquitetar soluções do SharePoint para que elas sejam um bom ajuste na plataforma do Azure. As duas soluções específicas a seguir são usadas como exemplos:
  
- [Recuperação de Desastre do SharePoint Server 2013 no Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)
    
- [Sites da Internet no Microsoft Azure usando o SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
    
## <a name="recommended-sharepoint-solutions-for-azure-infrastructure-services"></a>Soluções recomendadas do SharePoint para serviços de infraestrutura do Azure

Os serviços de infraestrutura do Azure são uma opção atraente para hospedar soluções do SharePoint. Algumas soluções são mais adequadas para essa plataforma do que outras. A tabela a seguir mostra soluções recomendadas.
  
|**Solução**|**Por que essa solução é recomendada para o Azure**|
|:-----|:-----|
|Ambientes de desenvolvimento e teste  <br/> |É fácil criar e gerenciar esses ambientes.  <br/> |
|Recuperação de desastre de farms locais do SharePoint para o Azure  <br/> |**Datacenter secundário hospedado** Use o Azure em vez de investir em um datacenter secundário em uma região diferente. <br/> **Ambientes de recuperação de desastres de** menor custo Manter e pagar por menos recursos do que um ambiente de recuperação de desastres local. O número de recursos depende do ambiente de recuperação de desastres escolhido: espera a frio, espera a frio ou espera a quente. <br/> **Plataforma mais elástica** Em caso de desastre, dimensione facilmente seu farm de recuperação do SharePoint para atender aos requisitos de carga. Dimensione quando você não precisar mais dos recursos. <br/> Consulte Recuperação de Desastre [do SharePoint Server 2013 no Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md).  <br/> |
|Sites voltados para a Internet que usam recursos e escala não estão disponíveis no Microsoft 365  <br/> |**Concentre seus esforços** Concentre-se na criação de um site excelente em vez de criar infraestrutura. <br/> **Tirar proveito da elasticidade no Azure** Size the farm for the demand by adding new servers, and pay only for resources you need. Não há suporte para alocação dinâmica de máquina (escala automática). <br/> **Usar o Azure Active Directory (AD)** Aproveite o Azure AD para contas de clientes. <br/> **Adicionar funcionalidade do SharePoint não disponível no Microsoft 365** Adicione relatórios profundos e análise da Web. <br/> Consulte [Sites da Internet no Microsoft Azure usando o SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md).  <br/> |
|Farms de aplicativos para dar suporte ao Microsoft 365 ou ambientes locais  <br/> |**Criar, testar e hospedar aplicativos** no Azure para dar suporte a ambientes locais e de nuvem. <br/> **Hospede essa função** no Azure em vez de comprar um novo hardware para ambientes locais. <br/> |
   
Para soluções e cargas de trabalho de intranet e colaboração, considere as seguintes opções:
  
- Determine se o Microsoft 365 atende aos requisitos de negócios ou pode fazer parte da solução. O Microsoft 365 fornece um conjunto de recursos rich que está sempre atualizado.
    
- Se o Microsoft 365 não atender a todos os seus requisitos de negócios, considere uma implementação padrão do SharePoint 2013 no local do Microsoft Consulting Services (MCS). Uma arquitetura padrão pode ser uma solução mais rápida, mais barata e mais fácil para você suportar do que uma solução personalizada. 
    
- Se uma implementação padrão não atender aos seus requisitos de negócios, considere uma solução local personalizada.
    
- Se usar uma plataforma de nuvem for importante para seus requisitos de negócios, considere uma implementação padrão ou personalizada do SharePoint 2013 hospedado nos serviços de infraestrutura do Azure. As soluções do SharePoint são muito mais fáceis de suportar no Azure do que em outras plataformas de nuvem pública não nativas da Microsoft.
    
## <a name="before-you-design-the-azure-environment"></a>Antes de projetar o ambiente do Azure

Embora este artigo use topologias do SharePoint de exemplo, você pode usar esses conceitos de design com qualquer topologia de farm do SharePoint. Antes de projetar o ambiente do Azure, use as seguintes diretrizes de topologia, arquitetura, capacidade e desempenho para projetar o farm do SharePoint:
  
- [Design de arquitetura para profissionais de TI do SharePoint 2013](/SharePoint/technical-reference/technical-diagrams)
    
- [Planejar o gerenciamento de desempenho e capacidade no SharePoint Server 2013](/SharePoint/administration/performance-planning-in-sharepoint-server-2013)
    
## <a name="determine-the-active-directory-domain-type"></a>Determinar o tipo de domínio do Active Directory

Cada farm do SharePoint Server depende do Active Directory para fornecer contas administrativas para a instalação do farm. No momento, há duas opções para soluções do SharePoint no Azure. Eles são descritos na tabela a seguir.
  
|**Opção**|**Descrição**|
|:-----|:-----|
|Domínio dedicado  <br/> |Você pode implantar um domínio do Active Directory dedicado e isolado no Azure para dar suporte ao farm do SharePoint. Essa é uma boa opção para sites de Internet voltados para o público.  <br/> |
|Estender o domínio local por meio de uma conexão entre locais  <br/> |Quando você estende o domínio local por meio de uma conexão entre locais, os usuários acessam o farm do SharePoint por meio da intranet como se ele estivesse hospedado no local. Você pode tirar proveito da implementação local do Active Directory e DNS.  <br/> Uma conexão entre locais é necessária para a criação de um ambiente de recuperação de desastres no Azure para fazer fail over do farm local.  <br/> |
   
Este artigo inclui conceitos de design para estender o domínio local por meio de uma conexão entre locais. Se sua solução usa um domínio dedicado, você não precisa de uma conexão entre locais.
  
## <a name="design-the-virtual-network"></a>Projetar a rede virtual

Primeiro, você precisa de uma rede virtual no Azure, que inclui sub-redes nas quais você colocará suas máquinas virtuais. A rede virtual precisa de um espaço de endereço IP privado, partes das quais você atribui às sub-redes.
  
Se você estiver estendendo sua rede local para o Azure por meio de uma conexão entre locais (necessária para um ambiente de recuperação de desastres), você deve escolher um espaço de endereço privado que ainda não está em uso em outro lugar na rede da organização, o que pode incluir seu ambiente local e outras redes virtuais do Azure. 
  
**Figura 1: Ambiente local com uma rede virtual no Azure**

![Design de rede virtual do Microsoft Azure para uma solução do SharePoint. Uma sub-rede para o gateway do Azure. Uma sub-rede para máquinas virtuais.](../media/OPrrasconWA-AZarch.png)
  
Neste diagrama:
  
- Uma rede virtual no Azure é ilustrada lado a lado no ambiente local. Os dois ambientes ainda não estão conectados por uma conexão entre locais, que pode ser uma conexão VPN site a site ou ExpressRoute.
    
- Neste ponto, a rede virtual só inclui as sub-redes e nenhum outro elemento arquitetônico. Uma sub-rede hospedará o gateway do Azure e outras sub-redes hospedarão as camadas do farm do SharePoint, com uma adicional para Active Directory e DNS.
    
## <a name="add-cross-premises-connectivity"></a>Adicionar conectividade entre locais

A próxima etapa de implantação é criar a conexão entre locais (se isso se aplicar à sua solução). Para conexões entre locais, um gateway do Azure reside em uma sub-rede de gateway separada, que você deve criar e atribuir um espaço de endereço. 
  
Quando você planeja uma conexão entre locais, define e cria um gateway do Azure e uma conexão com um dispositivo de gateway local.
  
**Figura 2: Usando um gateway do Azure e um dispositivo de gateway local para fornecer conectividade site a site entre o ambiente local e o Azure**

![Ambiente local conectado a uma rede virtual do Azure por meio de uma conexão entre locais, que pode ser uma conexão VPN site a site ou ExpressRoute](../media/AZarch-VPNgtwyconnct.png)
  
Neste diagrama:
  
- Adicionando ao diagrama anterior, o ambiente local é conectado à rede virtual do Azure por uma conexão entre locais, que pode ser uma conexão VPN site a site ou ExpressRoute.
    
- Um gateway do Azure está em uma sub-rede de gateway.
    
- O ambiente local inclui um dispositivo de gateway, como um roteador ou servidor VPN.
    
Para obter informações adicionais para planejar e criar uma rede virtual entre locais, consulte Conectar uma rede local a uma rede virtual do [Microsoft Azure.](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)
  
## <a name="add-active-directory-domain-services-ad-ds-and-dns"></a>Adicionar Serviços de Domínio do Active Directory (AD DS) e DNS

Para recuperação de desastres no Azure, você implanta o AD do Windows Server e o DNS em um cenário híbrido em que o AD do Windows Server é implantado no local e em máquinas virtuais do Azure.
  
**Figura 3: Configuração de domínio híbrido do Active Directory**

![As duas máquinas virtuais STwo implantadas na rede virtual do Azure e a sub-rede do Farm do SharePoint são controladores de domínio de réplica e servidores DNS](../media/AZarch-HyADdomainConfig.png)
  
Este diagrama se baseia nos diagramas anteriores adicionando duas máquinas virtuais a uma sub-rede do Windows Server AD e DNS. Essas máquinas virtuais são controladores de domínio de réplica e servidores DNS. Eles são uma extensão do ambiente local do AD do Windows Server. 
  
A tabela a seguir fornece recomendações de configuração para essas máquinas virtuais no Azure. Use-os como ponto de partida para projetar seu próprio ambiente, mesmo para um domínio dedicado em que seu ambiente do Azure não se comunica com seu ambiente local.
  
|**Item**|**Configuração**|
|:-----|:-----|
|Tamanho da máquina virtual no Azure  <br/> |Tamanho A1 ou A2 na camada Standard  <br/> |
|Sistema operacional  <br/> |Windows Server 2012 R2  <br/> |
|Função do Active Directory  <br/> |Controlador de domínio do AD DS designado como um servidor de catálogo global. Essa configuração reduz o tráfego de saída na conexão entre locais.  <br/> Em um ambiente de multidomain com altas taxas de alteração (isso não é comum), configure os controladores de domínio no local para não sincronizar com os servidores de catálogo global no Azure, para reduzir o tráfego de replicação.  <br/> |
|Função DNS  <br/> |Instale e configure o serviço de Servidor DNS nos controladores de domínio.  <br/> |
|Discos de dados  <br/> |Coloque o banco de dados, logs e SYSVOL do Active Directory em discos de dados adicionais do Azure. Não coloque-os no disco do sistema operacional ou nos discos temporários fornecidos pelo Azure.  <br/> |
|Endereços IP  <br/> |Use endereços IP estáticos e configure a rede virtual para atribuir esses endereços às máquinas virtuais na rede virtual depois que os controladores de domínio foram configurados.  <br/> |
   
> [!IMPORTANT]
> Antes de implantar o Active Directory no Azure, leia Diretrizes para Implantar o [Windows Server Active Directory em Máquinas Virtuais do Azure.](/windows-server/identity/ad-ds/introduction-to-active-directory-domain-services-ad-ds-virtualization-level-100) Isso ajuda a determinar se uma arquitetura diferente ou configurações diferentes são necessárias para sua solução. 
  
## <a name="add-the-sharepoint-farm"></a>Adicionar o farm do SharePoint

Coloque as máquinas virtuais do farm do SharePoint em camadas nas sub-redes apropriadas.
  
**Figura 4: Posicionamento de máquinas virtuais do SharePoint**

![Servidores de banco de dados e funções de servidor do SharePoint adicionadas à rede virtual do Azure na sub-rede do Farm do SharePoint](../media/AZarch-SPVMsinCloudSer.png)
  
Este diagrama se constrói nos diagramas anteriores adicionando as funções de servidor do farm do SharePoint em suas respectivas camadas.
  
- Duas máquinas virtuais de banco de dados SQL Server criar a camada de banco de dados.
    
- Duas máquinas virtuais executando o SharePoint Server 2013 para cada uma das seguintes camadas: servidores front-end, servidores de cache distribuídos e servidores back-end.
    
## <a name="design-and-fine-tune-server-roles-for-availability-sets-and-fault-domains"></a>Projetar e ajustar funções de servidor para conjuntos de disponibilidade e domínios de falha

Um domínio de falha é um grupo de hardware no qual as instâncias de função são executados. As máquinas virtuais no mesmo domínio de falha podem ser atualizadas pela infraestrutura do Azure ao mesmo tempo. Ou podem falhar ao mesmo tempo porque compartilham o mesmo rack. Para evitar o risco de ter duas máquinas virtuais no mesmo domínio de falha, você pode configurar suas máquinas virtuais como um conjunto de disponibilidade, o que garante que cada máquina virtual está em um domínio de falha diferente. Se três máquinas virtuais estão configuradas como um conjunto de disponibilidade, o Azure garante que não mais de duas das máquinas virtuais estão localizadas no mesmo domínio de falha.
  
Ao projetar a arquitetura do Azure para um farm do SharePoint, configure funções de servidor idênticas para fazer parte de um conjunto de disponibilidade. Isso garante que suas máquinas virtuais sejam espalhadas por vários domínios de falha.
  
**Figura 5: Usar conjuntos de disponibilidade do Azure para fornecer alta disponibilidade para as camadas do farm do SharePoint**

![Configuração de conjuntos de disponibilidade na infraestrutura do Azure para uma solução do SharePoint 2013](../media/AZenv-WinAzureAvailSetsHA.png)
  
Este diagrama chama a configuração de conjuntos de disponibilidade dentro da infraestrutura do Azure. Cada uma das seguintes funções compartilham um conjunto de disponibilidade separado:
  
- Active Directory e DNS
    
- Database
    
- Back-end
    
- Distribuir cache
    
- Front-end
    
O farm do SharePoint pode precisar ser ajustado na plataforma do Azure. Para garantir a alta disponibilidade de todos os componentes, verifique se as funções de servidor estão configuradas de forma idêntica.
  
Aqui está um exemplo que mostra uma arquitetura padrão de Sites da Internet que atende a metas específicas de capacidade e desempenho. Este exemplo é apresentado no seguinte modelo de arquitetura: Arquiteturas de Pesquisa de Sites da [Internet para SharePoint Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=261519).
  
**Figura 6: Exemplo de planejamento para metas de capacidade e desempenho em um farm de três camadas**

![Arquitetura padrão de Sites da Internet do SharePoint 2013 com alocações de componentes que atendem a metas específicas de capacidade e desempenho](../media/AZarch-CapPerfexmpArch.png)
  
Neste diagrama:
  
- Um farm de três camadas é representado: servidores Web, servidores de aplicativos e servidores de banco de dados.
    
- Os três servidores Web são configurados de forma idêntica com vários componentes.
    
- Os dois servidores de banco de dados são configurados de forma idêntica.
    
- Os três servidores de aplicativos não são configurados de forma idêntica. Essas funções de servidor exigem ajuste fino para conjuntos de disponibilidade no Azure.
    
Vamos ver mais de perto a camada do servidor de aplicativos.
  
**Figura 7: Camada do servidor de aplicativos antes do ajuste fino**

![Exemplo da camada de servidor de aplicativos do SharePoint Server 2013 antes de ajustar os conjuntos de disponibilidade do Microsoft Azure](../media/AZarch-AppServtierBefore.png)
  
Neste diagrama:
  
- Três servidores estão incluídos na camada de aplicativos.
    
- O primeiro servidor inclui quatro componentes.
    
- O segundo servidor inclui três componentes.
    
- O terceiro servidor inclui dois componentes.
    
Você determina o número de componentes pelas metas de desempenho e capacidade do farm. Para adaptar essa arquitetura para o Azure, replicamos os quatro componentes em todos os três servidores. Isso aumenta o número de componentes além do necessário para o desempenho e a capacidade. A tradeoff é que esse design garante alta disponibilidade de todos os quatro componentes na plataforma do Azure quando essas três máquinas virtuais são atribuídas a um conjunto de disponibilidade.
  
**Figura 8: Camada de servidor de aplicativos após ajuste fino**

![Exemplo da camada de servidor de aplicativos do SharePoint Server 2013 após ajustar os conjuntos de disponibilidade do Microsoft Azure](../media/AZarch-AppServtierAfter.png)
  
Este diagrama mostra todos os três servidores de aplicativos configurados de forma idêntica com os mesmos quatro componentes.
  
Quando adicionamos conjuntos de disponibilidade às camadas do farm do SharePoint, a implementação é concluída.
  
**Figura 9: o farm do SharePoint concluído nos serviços de infraestrutura do Azure**

![Exemplo do farm do SharePoint 2013 nos serviços de infraestrutura do Azure com rede virtual, conectividade entre locais, sub-redes, VMs e conjuntos de disponibilidade](../media/7256292f-bf11-485b-8917-41ba206153ee.png)
  
Este diagrama mostra o farm do SharePoint implementado nos serviços de infraestrutura do Azure, com conjuntos de disponibilidade para fornecer domínios de falha para os servidores em cada camada.
  
## <a name="see-also"></a>Confira também

[Centro de soluções e arquitetura do Microsoft 365](../solutions/index.yml)
  
[Sites da Internet no Microsoft Azure usando o SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
  
[Recuperação de Desastre do SharePoint Server 2013 no Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)