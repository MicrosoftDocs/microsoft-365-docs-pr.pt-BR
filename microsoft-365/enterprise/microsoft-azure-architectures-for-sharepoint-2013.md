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
description: Saiba quais tipos de soluções do SharePoint 2013 podem ser hospedados em máquinas virtuais do Microsoft Azure e como configurar o Azure para o host um.
ms.openlocfilehash: 37d7eb2a746e30ad560949a933783beb6b971a08
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695403"
---
# <a name="microsoft-azure-architectures-for-sharepoint-2013"></a>Arquiteturas do Microsoft Azure para o SharePoint 2013

O Azure é um bom ambiente para hospedar uma solução do SharePoint Server 2013. Na maioria dos casos, recomendamos o Microsoft 365, mas um farm do SharePoint Server hospedado no Azure pode ser uma boa opção para soluções específicas. Este artigo descreve como arquitetar soluções do SharePoint para que eles sejam adequados para a plataforma do Azure. As duas soluções específicas a seguir são usadas como exemplos:
  
- [Recuperação de Desastre do SharePoint Server 2013 no Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)
    
- [Sites da Internet no Microsoft Azure usando o SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
    
## <a name="recommended-sharepoint-solutions-for-azure-infrastructure-services"></a>Soluções do SharePoint recomendadas para os serviços de infraestrutura do Azure

Os serviços de infraestrutura do Azure são uma opção atraente para hospedar soluções do SharePoint. Algumas soluções são mais adequadas para esta plataforma do que outras. A tabela a seguir mostra as soluções recomendadas.
  
|**Solução**|**Por que esta solução é recomendada para o Azure**|
|:-----|:-----|
|Ambientes de desenvolvimento e teste  <br/> |É fácil criar e gerenciar esses ambientes.  <br/> |
|Recuperação de desastres de farms locais do SharePoint para o Azure  <br/> |**Data center secundário hospedado** Use o Azure em vez de investir em um data center secundário em uma região diferente. <br/> **Ambientes de recuperação de desastres de baixo custo** Mantenha e pague por menos recursos do que um ambiente de recuperação de desastres local. O número de recursos depende do ambiente de recuperação de desastres que você escolhe: espera Cold, espera passiva ou espera ativa. <br/> **Mais plataforma elástica** No caso de um desastre, dimensione facilmente seu farm do SharePoint de recuperação para atender aos requisitos de carga. Expanda quando não precisar mais dos recursos. <br/> Confira [recuperação de desastre do SharePoint Server 2013 no Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md).  <br/> |
|Sites voltados para a Internet que usam recursos e escala não estão disponíveis no Microsoft 365  <br/> |**Concentrar seus esforços** Concentre-se em criar um ótimo site, em vez de criar uma infraestrutura. <br/> Aproveite a **elasticidade no Azure** Dimensione o farm para a demanda adicionando novos servidores e pague apenas os recursos de que você precisa. Não há suporte para a alocação de máquina dinâmica (escala automática). <br/> **Usar o Azure Active Directory (AD)** Aproveite o Azure AD para contas de cliente. <br/> **Adicionar funcionalidade do SharePoint não disponível no Microsoft 365** Adicione relatórios detalhados e análises da Web. <br/> Confira [sites da Internet no Microsoft Azure usando o SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md).  <br/> |
|Farms de aplicativos compatíveis com o Microsoft 365 ou ambientes locais  <br/> |**Crie, teste e hospede aplicativos** no Azure para dar suporte a ambientes locais e de nuvem. <br/> **Hospede essa função** no Azure, em vez de comprar novo hardware para ambientes locais. <br/> |
   
Para soluções de intranet e colaboração e cargas de trabalho, considere as seguintes opções:
  
- Determine se o Microsoft 365 atende aos seus requisitos de negócios ou pode fazer parte da solução. O Microsoft 365 fornece um conjunto de recursos avançado que está sempre atualizado.
    
- Se o Microsoft 365 não atender a todos os seus requisitos de negócios, considere uma implementação padrão do SharePoint 2013 no local dos serviços de consultoria da Microsoft (MCS). Uma arquitetura padrão pode ser uma solução mais rápida, mais barata e mais fácil para você dar suporte do que um personalizado. 
    
- Se uma implementação padrão não atender aos requisitos de negócios, considere uma solução local personalizada.
    
- Se usar uma plataforma de nuvem for importante para seus requisitos de negócios, considere uma implementação padrão ou personalizada do SharePoint 2013 hospedado nos serviços de infraestrutura do Azure. As soluções do SharePoint são muito mais fáceis de suportar no Azure do que outras plataformas de nuvem pública da Microsoft não nativas.
    
## <a name="before-you-design-the-azure-environment"></a>Antes de projetar o ambiente do Azure

Embora este artigo use topologias de exemplo do SharePoint, você pode usar esses conceitos de design com qualquer topologia de farm do SharePoint. Antes de projetar o ambiente do Azure, use as seguintes orientações de topologia, arquitetura, capacidade e desempenho para projetar o farm do SharePoint:
  
- [Design de arquitetura para profissionais de ti do SharePoint 2013](https://technet.microsoft.com/sharepoint/fp123594.aspx)
    
- [Planejar o gerenciamento de desempenho e capacidade no SharePoint Server 2013](https://technet.microsoft.com/library/8dd52916-f77d-4444-b593-1f7d6f330e5f.aspx)
    
## <a name="determine-the-active-directory-domain-type"></a>Determinar o tipo de domínio do Active Directory

Cada farm do SharePoint Server se baseia no Active Directory para fornecer contas administrativas para a configuração do farm. No momento, há duas opções para soluções do SharePoint no Azure. Eles são descritos na tabela a seguir.
  
|**Opção**|**Descrição**|
|:-----|:-----|
|Domínio dedicado  <br/> |Você pode implantar um domínio do Active Directory dedicado e isolado no Azure para dar suporte ao seu farm do SharePoint. Essa é uma boa opção para sites de Internet voltados para o público.  <br/> |
|Estender o domínio local por meio de uma conexão entre locais  <br/> |Quando você estende o domínio local por meio de uma conexão entre locais, os usuários acessam o farm do SharePoint através da intranet como se estivessem hospedados no local. Você pode aproveitar o Active Directory local e a implementação de DNS.  <br/> Uma conexão entre locais é necessária para criar um ambiente de recuperação de desastres no Azure para fazer o failover do seu farm local.  <br/> |
   
Este artigo inclui conceitos de design para estender o domínio local por meio de uma conexão entre locais. Se sua solução usa um domínio dedicado, você não precisa de uma conexão entre locais.
  
## <a name="design-the-virtual-network"></a>Projetar a rede virtual

Primeiro, você precisa de uma rede virtual no Azure, que inclui sub-redes nas quais as máquinas virtuais serão colocadas. A rede virtual precisa de um espaço de endereço IP privado, partes das quais você atribui às sub-redes.
  
Se você estiver estendendo sua rede local para o Azure por meio de uma conexão entre locais (necessária para um ambiente de recuperação de desastres), deverá escolher um espaço de endereçamento privado que ainda não esteja em uso em outro lugar na rede da sua organização, que pode incluir seu ambiente local e outras redes virtuais do Azure. 
  
**Figura 1: ambiente local com uma rede virtual no Azure**

![Design de rede virtual do Microsoft Azure para uma solução do SharePoint. Uma sub-rede para o gateway do Azure. Uma sub-rede para as máquinas virtuais.](../media/OPrrasconWA-AZarch.png)
  
Neste diagrama:
  
- Uma rede virtual no Azure é ilustrada lado a lado para o ambiente local. Os dois ambientes ainda não estão conectados por uma conexão entre locais, que pode ser uma conexão VPN de site a site ou ExpressRoute.
    
- Neste ponto, a rede virtual inclui apenas as sub-redes e nenhum outro elemento estrutural. Uma sub-rede hospedará o gateway do Azure e outras sub-redes hospedam as camadas do farm do SharePoint, com uma adicional para o Active Directory e o DNS.
    
## <a name="add-cross-premises-connectivity"></a>Adicionar conectividade entre locais

A próxima etapa de implantação é criar a conexão entre locais (se isso se aplicar à sua solução). Para conexões entre locais, um gateway do Azure reside em uma sub-rede de gateway separada, que você deve criar e atribuir um espaço de endereçamento. 
  
Ao planejar uma conexão entre locais, você define e cria um gateway do Azure e uma conexão com um dispositivo de gateway local.
  
**Figura 2: usando um gateway do Azure e um dispositivo de gateway local para fornecer conectividade de site para site entre o ambiente local e o Azure**

![Ambiente local conectado a uma rede virtual do Azure por uma conexão entre locais, que pode ser uma conexão VPN de site a site ou ExpressRoute](../media/AZarch-VPNgtwyconnct.png)
  
Neste diagrama:
  
- Adicionando ao diagrama anterior, o ambiente local é conectado à rede virtual do Azure por uma conexão entre locais, que pode ser uma conexão VPN de site a site ou ExpressRoute.
    
- Um gateway do Azure está em uma sub-rede de gateway.
    
- O ambiente local inclui um dispositivo de gateway, como um roteador ou servidor VPN.
    
Para obter informações adicionais sobre como planejar e criar uma rede virtual entre locais, consulte [conectar uma rede local a uma rede virtual do Microsoft Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).
  
## <a name="add-active-directory-domain-services-ad-ds-and-dns"></a>Adicionar os serviços de domínio do Active Directory (AD DS) e o DNS

Para recuperação de desastre no Azure, você implanta o Windows Server AD e o DNS em um cenário híbrido onde o Windows Server AD é implantado tanto no local quanto em máquinas virtuais do Azure.
  
**Figura 3: configuração de domínio híbrida do Active Directory**

![STwo máquinas virtuais implantadas para a rede virtual do Azure e a sub-rede do farm do SharePoint são controladores de domínio de réplica e servidores DNS](../media/AZarch-HyADdomainConfig.png)
  
Este diagrama cria os diagramas anteriores adicionando duas máquinas virtuais a um Windows Server AD e a uma sub-rede de DNS. Essas máquinas virtuais são controladores de domínio de réplica e servidores DNS. Eles são uma extensão do ambiente local do AD do Windows Server. 
  
A tabela a seguir fornece recomendações de configuração para essas máquinas virtuais no Azure. Use-os como ponto de partida para projetar seu próprio ambiente, mesmo para um domínio dedicado onde seu ambiente do Azure não se comunica com seu ambiente local.
  
|**Item**|**Configuração**|
|:-----|:-----|
|Tamanho da máquina virtual no Azure  <br/> |Tamanho a1 ou a2 na camada padrão  <br/> |
|Sistema operacional  <br/> |Windows Server 2012 R2  <br/> |
|Função do Active Directory  <br/> |Controlador de domínio do AD DS designado como um servidor de catálogo global. Essa configuração reduz o tráfego de egresso na conexão entre locais.  <br/> Em um ambiente de multidomínio com altas taxas de alteração (isso não é comum), configure os controladores de domínio no local para não sincronizar com os servidores de catálogo global no Azure, para reduzir o tráfego de replicação.  <br/> |
|Função DNS  <br/> |Instale e configure o serviço de servidor DNS nos controladores de domínio.  <br/> |
|Discos de dados  <br/> |Coloque o banco de dados do Active Directory, os logs e o SYSVOL em discos de dados adicionais do Azure. Não coloque esses no disco do sistema operacional ou nos discos temporários fornecidos pelo Azure.  <br/> |
|Endereços IP  <br/> |Use endereços IP estáticos e configure a rede virtual para atribuir esses endereços às máquinas virtuais na rede virtual após os controladores de domínio terem sido configurados.  <br/> |
   
> [!IMPORTANT]
> Antes de implantar o Active Directory no Azure, leia as [diretrizes para implantar o Windows Server Active Directory nas máquinas virtuais do Azure](https://go.microsoft.com/fwlink/p/?linkid=392681). Eles ajudam a determinar se uma arquitetura diferente ou definições de configuração diferentes são necessárias para sua solução. 
  
## <a name="add-the-sharepoint-farm"></a>Adicionar o farm do SharePoint

Coloque as máquinas virtuais do farm do SharePoint em camadas nas sub-redes apropriadas.
  
**Figura 4: posicionamento de máquinas virtuais do SharePoint**

![Servidores de banco de dados e funções do SharePoint Server adicionados à rede virtual do Azure dentro da sub-rede do farm do SharePoint](../media/AZarch-SPVMsinCloudSer.png)
  
Este diagrama cria os diagramas anteriores adicionando as funções de servidor do farm do SharePoint em suas respectivas camadas.
  
- Duas máquinas virtuais de banco de dados executando o SQL Server criam a camada de banco de dados.
    
- Duas máquinas virtuais executando o SharePoint Server 2013 para cada uma das seguintes camadas: servidores front-end, servidores de cache distribuído e servidores de back-end.
    
## <a name="design-and-fine-tune-server-roles-for-availability-sets-and-fault-domains"></a>Projetar e ajustar funções de servidor para conjuntos de disponibilidade e domínios de falha

Um domínio de falha é um agrupamento de hardware no qual as instâncias de função são executadas. As máquinas virtuais dentro do mesmo domínio de falha podem ser atualizadas pela infraestrutura do Azure ao mesmo tempo. Ou, eles podem falhar ao mesmo tempo, pois compartilham o mesmo rack. Para evitar o risco de ter duas máquinas virtuais no mesmo domínio de falha, você pode configurar suas máquinas virtuais como um conjunto de disponibilidade, o que garante que cada máquina virtual esteja em um domínio de falha diferente. Se três máquinas virtuais forem configuradas como um conjunto de disponibilidade, o Azure garante que não mais de duas máquinas virtuais estejam localizadas no mesmo domínio de falha.
  
Ao projetar a arquitetura do Azure para um farm do SharePoint, configure funções de servidor idênticas para fazer parte de um conjunto de disponibilidade. Isso garante que suas máquinas virtuais estejam espalhadas por vários domínios de falha.
  
**Figura 5: usar conjuntos de disponibilidade do Azure para fornecer alta disponibilidade para as camadas de farm do SharePoint**

![Configuração de conjuntos de disponibilidade na infraestrutura do Azure para uma solução do SharePoint 2013](../media/AZenv-WinAzureAvailSetsHA.png)
  
Este diagrama chama a configuração de conjuntos de disponibilidade na infraestrutura do Azure. Cada uma das seguintes funções compartilham um conjunto de disponibilidade separado:
  
- Active Directory e DNS
    
- Banco de dados
    
- Back-end
    
- Distribuir cache
    
- Front-end
    
Talvez seja necessário ajustar o farm do SharePoint na plataforma Azure. Para garantir a alta disponibilidade de todos os componentes, certifique-se de que as funções de servidor estejam configuradas de forma idêntica.
  
Veja a seguir um exemplo que mostra uma arquitetura padrão de sites da Internet que atende às metas específicas de capacidade e desempenho. Este exemplo é apresentado no seguinte modelo de arquitetura: [arquiteturas de pesquisa de sites da Internet para o SharePoint Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=261519).
  
**Figura 6: exemplo de planejamento para metas de capacidade e desempenho em um farm de três camadas**

![Arquitetura de sites da Internet do SharePoint 2013 padrão com alocações de componentes que atendem às metas específicas de capacidade e desempenho](../media/AZarch-CapPerfexmpArch.png)
  
Neste diagrama:
  
- Um farm de três camadas é representado: servidores Web, servidores de aplicativos e servidores de banco de dados.
    
- Os três servidores Web são configurados de forma idêntica com vários componentes.
    
- Os dois servidores de banco de dados são configurados de forma idêntica.
    
- Os três servidores de aplicativos não são configurados de forma idêntica. Essas funções de servidor exigem ajuste fino para os conjuntos de disponibilidade no Azure.
    
Vamos examinar mais de perto a camada do servidor de aplicativos.
  
**Figura 7: camada do servidor de aplicativos antes do ajuste fino**

![Exemplo de camada de servidor de aplicativos do SharePoint Server 2013 antes do ajuste para os conjuntos de disponibilidade do Microsoft Azure](../media/AZarch-AppServtierBefore.png)
  
Neste diagrama:
  
- Três servidores estão incluídos na camada de aplicativo.
    
- O primeiro servidor inclui quatro componentes.
    
- O segundo servidor inclui três componentes.
    
- O terceiro servidor inclui dois componentes.
    
Você determina o número de componentes pelos objetivos de desempenho e capacidade para o farm. Para adaptar essa arquitetura para o Azure, replicaremos os quatro componentes em todos os três servidores. Isso aumenta o número de componentes além do que é necessário para desempenho e capacidade. A compensação é que esse design garante alta disponibilidade de todos os quatro componentes da plataforma do Azure quando essas três máquinas virtuais são atribuídas a um conjunto de disponibilidade.
  
**Figura 8: camada do servidor de aplicativos após ajuste fino**

![Exemplo de camada de servidor de aplicativos do SharePoint Server 2013 após o ajuste para os conjuntos de disponibilidade do Microsoft Azure](../media/AZarch-AppServtierAfter.png)
  
Este diagrama mostra todos os três servidores de aplicativos configurados de forma idêntica com os mesmos quatro componentes.
  
Quando adicionamos conjuntos de disponibilidade às camadas do farm do SharePoint, a implementação é concluída.
  
**Figura 9: o farm do SharePoint concluído nos serviços de infraestrutura do Azure**

![Exemplo de farm do SharePoint 2013 nos serviços de infraestrutura do Azure com rede virtual, conectividade entre locais, sub-redes, VMs e conjuntos de disponibilidade](../media/7256292f-bf11-485b-8917-41ba206153ee.png)
  
Este diagrama mostra o farm do SharePoint implementado nos serviços de infraestrutura do Azure, com conjuntos de disponibilidade para fornecer domínios de falha para os servidores em cada camada.
  
## <a name="see-also"></a>Confira também

[Centro de soluções e arquitetura do Microsoft 365](../solutions/solution-architecture-center.md)
  
[Sites da Internet no Microsoft Azure usando o SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
  
[Recuperação de Desastre do SharePoint Server 2013 no Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)


