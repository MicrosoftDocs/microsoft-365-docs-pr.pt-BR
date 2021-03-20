---
title: Recuperação de Desastre do SharePoint Server 2013 no Microsoft Azure
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 04/17/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Deployment
- seo-marvel-apr2020
ms.assetid: e9d14cb2-ff28-4a18-a444-cebf891880ea
description: Este artigo descreve como usar o Azure para criar um ambiente de recuperação de desastres para o farm local do SharePoint.
ms.openlocfilehash: 01a49cfa19711caa36190a795792635431dd7d04
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907427"
---
# <a name="sharepoint-server-2013-disaster-recovery-in-microsoft-azure"></a>Recuperação de Desastre do SharePoint Server 2013 no Microsoft Azure

 Usando o Azure, você pode criar um ambiente de recuperação de desastres para o farm local do SharePoint. Este artigo descreve como criar e implementar esta solução.

 **Assista ao vídeo de visão geral de recuperação de desastres do SharePoint Server 2013**
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1b73ec8f-29bd-44eb-aa3a-f7932784bfd9?autoplay=false]
  
 Quando o desastre atinge seu ambiente local do SharePoint, sua prioridade máxima é fazer com que o sistema seja executado novamente rapidamente. A recuperação de desastres com o SharePoint é mais rápida e fácil quando você tem um ambiente de backup já em execução no Microsoft Azure. Este vídeo explica os principais conceitos de um ambiente de failover acolhedores do SharePoint e complementa os detalhes completos disponíveis neste artigo.
  
Use este artigo com o seguinte modelo de solução: **Recuperação de Desastre do SharePoint no Microsoft Azure**.
  
[![Processo de recuperação de desastres do SharePoint para o Azure](../media/SP-DR-Azure.png)](https://go.microsoft.com/fwlink/p/?LinkId=392555)
  
 [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555) |  [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)
  
## <a name="use-azure-infrastructure-services-for-disaster-recovery"></a>Usar os Serviços de Infraestrutura do Azure para recuperação de desastres

Muitas organizações não têm um ambiente de recuperação de desastres para o SharePoint, o que pode ser caro para criar e manter no local. Os Serviços de Infraestrutura do Azure fornece opções atraentes para ambientes de recuperação de desastres mais flexíveis e menos caros do que as alternativas locais.
  
As vantagens de usar os Serviços de Infraestrutura do Azure incluem:
  
- **Menos recursos custoso** Manter e pagar por menos recursos do que ambientes locais de recuperação de desastres. O número de recursos depende de qual ambiente de recuperação de desastres você escolher: espera a frio, espera a frio ou espera a quente.
    
- **Melhor flexibilidade de recursos** Em caso de desastre, dimensione facilmente seu farm de recuperação do SharePoint para atender aos requisitos de carga. Dimensione quando você não precisar mais dos recursos.
    
- **Menor comprometimento do datacenter** Use os Serviços de Infraestrutura do Azure em vez de investir em um datacenter secundário em uma região diferente.
    
Há opções menos complexas para as organizações que estão apenas começando com a recuperação de desastres e as opções avançadas para organizações com requisitos de alta resiliência. As definições para ambientes de espera frios, quentes e quentes são um pouco diferentes quando o ambiente é hospedado em uma plataforma de nuvem. A tabela a seguir descreve esses ambientes para a criação de um farm de recuperação do SharePoint no Azure.
  
**Tabela: Ambientes de recuperação**

|**Tipo de ambiente de recuperação**|**Descrição**|
|:-----|:-----|
|Hot  <br/> |Um farm totalmente dimensionado é provisionado, atualizado e executado em espera.  <br/> |
|Warm  <br/> |O farm é criado e as máquinas virtuais estão em execução e atualizadas.  <br/> A recuperação inclui anexar bancos de dados de conteúdo, provisionar aplicativos de serviço e rastrear conteúdo.  <br/> O farm pode ser uma versão menor do farm de produção e, em seguida, dimensionado para atender à base de usuários completa.  <br/> |
|Cold  <br/> |O farm é totalmente criado, mas as máquinas virtuais são interrompidas.  <br/> A manutenção do ambiente inclui iniciar as máquinas virtuais de vez em quando, corrigir, atualizar e verificar o ambiente.  <br/> Inicie o ambiente completo em caso de desastre.  <br/> |
   
É importante avaliar os Objetivos de Tempo de Recuperação (RTOs) e RPOs (Objetivos de Ponto de Recuperação) da sua organização. Esses requisitos determinam qual ambiente é o investimento mais apropriado para sua organização.
  
As diretrizes neste artigo descrevem como implementar um ambiente de espera morno. Você também pode adaptá-lo a um ambiente de espera a frio, embora você precise seguir procedimentos adicionais para dar suporte a esse tipo de ambiente. Este artigo não descreve como implementar um ambiente de espera a quente.
  
Para obter mais informações sobre soluções de recuperação de desastres, consulte Conceitos de alta disponibilidade e recuperação de desastres no [SharePoint 2013](/SharePoint/administration/high-availability-and-disaster-recovery-concepts) e Escolha uma estratégia de recuperação de desastres para [SharePoint 2013](/SharePoint/administration/plan-for-disaster-recovery).
  
## <a name="solution-description"></a>Descrição da solução

A solução de recuperação de desastres em espera a quente requer o seguinte ambiente:
  
- Um farm de produção local do SharePoint
    
- Um farm do SharePoint de recuperação no Azure
    
- Uma conexão VPN site a site entre os dois ambientes
    
A figura a seguir ilustra esses três elementos.
  
**Figura: Elementos de uma solução de espera morna no Azure**

![Elementos de uma solução de espera morna do SharePoint no Azure](../media/AZarch-AZWarmStndby.png)
  
SQL Server envio de log com DFSR (Replicação do Sistema de Arquivos Distribuídos) é usado para copiar backups de banco de dados e logs de transação para o farm de recuperação no Azure: 
  
- DFSR transfere logs do ambiente de produção para o ambiente de recuperação. Em um cenário WAN, a DFSR é mais eficiente do que enviar os logs diretamente para o servidor secundário no Azure.
    
- Os logs são replayados para o SQL Server no ambiente de recuperação no Azure.
    
- Você não anexa bancos de dados de conteúdo do SharePoint enviados por log no ambiente de recuperação até que um exercício de recuperação seja executado.
    
Execute as seguintes etapas para recuperar o farm:
  
1. Pare o envio de log.
    
2. Pare de aceitar o tráfego para o farm principal.
    
3. Replay the final transaction logs.
    
4. Anexe os bancos de dados de conteúdo ao farm.
    
5. Restaurar aplicativos de serviço dos bancos de dados de serviços replicados.
    
6. Atualize registros DNS (Sistema de Nomes de Domínio) para apontar para o farm de recuperação.
    
7. Inicie um rastreamento completo.
    
Recomendamos que você ensaie essas etapas regularmente e documente-as para ajudar a garantir que a recuperação ao vivo seja executado sem problemas. Anexar bancos de dados de conteúdo e restaurar aplicativos de serviço pode levar algum tempo e normalmente envolve alguma configuração manual.
  
Depois que uma recuperação é executada, essa solução fornece os itens listados na tabela a seguir.
  
**Tabela: Objetivos de recuperação de soluções**

|**Item**|**Descrição**|
|:-----|:-----|
|Sites e conteúdo  <br/> |Sites e conteúdo estão disponíveis no ambiente de recuperação.  <br/> |
|Uma nova instância de pesquisa  <br/> |Nesta solução de espera morna, a pesquisa não é restaurada dos bancos de dados de pesquisa. Os componentes de pesquisa no farm de recuperação são configurados da mesma forma possível para o farm de produção. Depois que os sites e o conteúdo são restaurados, um rastreamento completo é iniciado para recriar o índice de pesquisa. Não é necessário aguardar a conclusão do rastreamento para disponibilizar os sites e o conteúdo.  <br/> |
|Serviços  <br/> | Os serviços que armazenam dados em bancos de dados são restaurados dos bancos de dados enviados pelo log. Os serviços que não armazenam dados em bancos de dados são simplesmente iniciados. <br/>  Nem todos os serviços com bancos de dados precisam ser restaurados. Os seguintes serviços não precisam ser restaurados dos bancos de dados e podem simplesmente ser iniciados após o failover: <br/>  Coleta de Dados de Uso e Integridade <br/>  Serviço de Controle de Sessão <br/>  Automação do Word <br/>  Qualquer outro serviço que não use um banco de dados <br/> |
   
Você pode trabalhar com o Microsoft Consulting Services (MCS) ou um parceiro para abordar objetivos de recuperação mais complexos. Eles são resumidos na tabela a seguir.
  
**Tabela: outros itens que podem ser abordados pelo MCS ou por um parceiro**

|**Item**|**Descrição**|
|:-----|:-----|
|Sincronizando soluções de farm personalizadas  <br/> |Idealmente, a configuração do farm de recuperação é idêntica ao farm de produção. Você pode trabalhar com um consultor ou parceiro para avaliar se as soluções de farm personalizadas são replicadas e se o processo está em uso para manter os dois ambientes sincronizados.  <br/> |
|Conexões com fontes de dados locais  <br/> |Pode não ser prático replicar conexões a sistemas de dados back-end, como conexões BDC (controlador de domínio de backup) e fontes de conteúdo de pesquisa.  <br/> |
|Cenários de restauração de pesquisa  <br/> |Como as implantações de pesquisa corporativa tendem a ser bastante exclusivas e complexas, restaurar a pesquisa de bancos de dados requer um investimento maior. Você pode trabalhar com um consultor ou parceiro para identificar e implementar cenários de restauração de pesquisa que sua organização pode exigir.  <br/> |
   
As diretrizes fornecidas neste artigo pressuem que o farm local já foi projetado e implantado.
  
## <a name="detailed-architecture"></a>Arquitetura detalhada

Idealmente, a configuração do farm de recuperação no Azure é idêntica ao farm de produção local, incluindo o seguinte:
  
- A mesma representação de funções de servidor
    
- A mesma configuração de personalizações
    
- A mesma configuração de componentes de pesquisa
    
O ambiente no Azure pode ser uma versão menor do farm de produção. Se você planeja dimensionar o farm de recuperação após o failover, é importante que cada tipo de função de servidor seja representado inicialmente.
  
Algumas configurações podem não ser práticas de replicar no ambiente de failover. Teste os procedimentos de failover e o ambiente para ajudar a garantir que o farm de failover fornece o nível de serviço esperado.
  
Essa solução não prescreve uma topologia específica para um farm do SharePoint. O foco dessa solução é usar o Azure para o farm de failover e implementar o envio de log e o DFSR entre os dois ambientes.
  
### <a name="warm-standby-environments"></a>Ambientes de espera quentes

Em um ambiente de espera morno, todas as máquinas virtuais no ambiente do Azure estão em execução. O ambiente está pronto para um exercício de failover ou evento.
  
A figura a seguir ilustra uma solução de recuperação de desastres de um farm local do SharePoint para um farm do SharePoint baseado no Azure que é configurado como um ambiente de espera morno.
  
**Figura: Topologia e elementos-chave de um farm de produção e um farm de recuperação de espera morno**

![Topologia de um farm do SharePoint e um farm de recuperação de espera morno](../media/AZarch-AZWarmStndby.png)
  
Neste diagrama:
  
- Dois ambientes são ilustrados lado a lado: o farm local do SharePoint e o farm de espera quente no Azure.
    
- Cada ambiente inclui um compartilhamento de arquivos.
    
- Cada farm inclui quatro camadas. Para obter alta disponibilidade, cada camada inclui dois servidores ou máquinas virtuais que são configurados de forma idêntica para uma função específica, como serviços front-end, cache distribuído, serviços back-end e bancos de dados. Não é importante nesta ilustração chamar componentes específicos. Os dois farms são configurados de forma idêntica.
    
- A quarta camada é a camada de banco de dados. O envio de log é usado para copiar logs do servidor de banco de dados secundário no ambiente local para o compartilhamento de arquivos no mesmo ambiente.
    
- A DFSR copia os arquivos do compartilhamento de arquivos no ambiente local para o compartilhamento de arquivos no ambiente Azure.
    
- O envio de logs reproduz os logs do compartilhamento de arquivos no ambiente Azure para a réplica primária no grupo de disponibilidade AlwaysOn do SQL Server no ambiente secundário.
    
### <a name="cold-standby-environments"></a>Ambientes de espera a frio

Em um ambiente de espera a frio, a maioria das máquinas virtuais do farm do SharePoint pode ser fechada. (Recomendamos, ocasionalmente, iniciar as máquinas virtuais, como a cada duas semanas ou uma vez por mês, para que cada máquina virtual possa sincronizar com o domínio.) As seguintes máquinas virtuais no ambiente de recuperação do Azure devem permanecer em execução para ajudar a garantir operações contínuas de envio de log e DFSR:
  
- O compartilhamento de arquivos
    
- Servidor de banco de dados principal
    
- Pelo menos uma máquina virtual executando o Windows Server Active Directory Domain Services e o DNS
    
A figura a seguir mostra um ambiente de failover do Azure no qual a máquina virtual de compartilhamento de arquivos e a máquina virtual de banco de dados principal do SharePoint estão sendo executados. Todas as outras máquinas virtuais do SharePoint são interrompidas. A máquina virtual que está executando o Windows Server Active Directory e o DNS não é mostrada.
  
**Figura: Farm de recuperação de espera a frio com máquinas virtuais em execução**

![Elementos de uma solução de espera a frio do SharePoint no Azure](../media/AZarch-AZColdStndby.png)
  
Após o failover para um ambiente de espera a frio, todas as máquinas virtuais são iniciadas, e o método para atingir a alta disponibilidade dos servidores de banco de dados deve ser configurado, como grupos de disponibilidade alwaysOn SQL Server.
  
Se vários grupos de armazenamento são implementados SQL Server (bancos de dados estão espalhados em mais de um conjunto de alta disponibilidade), o banco de dados principal de cada grupo de armazenamento deve estar sendo executado para aceitar os logs associados ao seu grupo de armazenamento.
  
### <a name="skills-and-experience"></a>Habilidades e experiência

Várias tecnologias são usadas nesta solução de recuperação de desastres. Para ajudar a garantir que essas tecnologias interajam conforme o esperado, cada componente no ambiente local e no Azure deve ser instalado e configurado corretamente. Recomendamos que a pessoa ou a equipe que configura essa solução tenha um forte conhecimento de trabalho e habilidades práticos com as tecnologias descritas nos seguintes artigos:
  
- [Serviços de Replicação do DFS (Sistema de Arquivos Distribuídos)](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11))
    
- [Cluster de Failover do Windows Server (WSFC) com SQL Server](/sql/sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server)
    
- [Grupos de Disponibilidade AlwaysOn (SQL Server)](/sql/database-engine/availability-groups/windows/always-on-availability-groups-sql-server)
    
- [Backup e restauração de bancos de dados SQL Server dados](/sql/relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases)
    
- [Instalação e implantação de farm do SharePoint Server 2013](/SharePoint/install/installation-and-configuration-overview)
    
- [Microsoft Azure](/azure/)
    
Por fim, recomendamos habilidades de script que você pode usar para automatizar tarefas associadas a essas tecnologias. É possível usar as interfaces de usuário disponíveis para concluir todas as tarefas descritas nesta solução. No entanto, uma abordagem manual pode ser demorada e propensa a erros e fornece resultados inconsistentes.
  
Além do Windows PowerShell, também há Windows PowerShell bibliotecas para SQL Server, SharePoint Server e Azure. Não se esqueça do T-SQL, que também pode ajudar a reduzir o tempo para configurar e manter seu ambiente de recuperação de desastres.
  
## <a name="disaster-recovery-roadmap"></a>Roteiro de recuperação de desastres

![Representação visual do mapa de recuperação de desastres do SharePoint.](../media/Azure-DRroadmap.png)
  
Este roteiro supõe que você já tenha um farm do SharePoint Server 2013 implantado em produção.
  
**Tabela: Roteiro para recuperação de desastres**

|**Fase**|**Descrição**|
|:-----|:-----|
|Fase 1  <br/> |Projete o ambiente de recuperação de desastres.  <br/> |
|Fase 2  <br/> |Crie a rede virtual e a conexão VPN do Azure.  <br/> |
|Fase 3  <br/> |Implante o Windows Active Directory e o Domain Name Services na rede virtual do Azure.  <br/> |
|Fase 4  <br/> |Implante o farm de recuperação do SharePoint no Azure.  <br/> |
|Fase 5  <br/> |Configurar DFSR entre os farms.  <br/> |
|Fase 6  <br/> |Configurar o envio de log para o farm de recuperação.  <br/> |
|Fase 7  <br/> | Validar soluções de failover e recuperação. Isso inclui os seguintes procedimentos e tecnologias: <br/>  Pare o envio de log. <br/>  Restaure os backups. <br/>  Conteúdo de rastreamento. <br/>  Recuperar serviços. <br/>  Gerenciar registros DNS. <br/> |
   
## <a name="phase-1-design-the-disaster-recovery-environment"></a>Fase 1: Projetar o ambiente de recuperação de desastres

Use as diretrizes no [Microsoft Azure Architectures para SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) para projetar o ambiente de recuperação de desastres, incluindo o farm de recuperação do SharePoint. Você pode usar os gráficos na Solução de Recuperação de Desastre do [SharePoint no arquivo do Azure](https://go.microsoft.com/fwlink/p/?LinkId=392554) Visio para iniciar o processo de design. Recomendamos que você projete todo o ambiente antes de iniciar qualquer trabalho no ambiente do Azure.
  
Além das diretrizes fornecidas no [Microsoft Azure Architectures para SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) para projetar a rede virtual, a conexão VPN, o Active Directory e o farm do SharePoint, certifique-se de adicionar uma função de compartilhamento de arquivos ao ambiente do Azure.
  
Para dar suporte ao envio de log em uma solução de recuperação de desastres, uma máquina virtual de compartilhamento de arquivos é adicionada à sub-rede onde residem as funções do banco de dados. O compartilhamento de arquivos também serve como o terceiro nó de uma Maioria de Nós para o grupo de disponibilidade SQL Server AlwaysOn. Essa é a configuração recomendada para um farm padrão do SharePoint que usa SQL Server grupos de disponibilidade AlwaysOn. 
  
> [!NOTE]
> É importante analisar os pré-requisitos para que um banco de dados participe de um grupo de disponibilidade SQL Server AlwaysOn. Para obter mais informações, consulte [Pré-requisitos, restrições](/sql/database-engine/availability-groups/windows/prereqs-restrictions-recommendations-always-on-availability)e recomendações para grupos de disponibilidade AlwaysOn. 
  
**Figura: Posicionamento de um servidor de arquivos usado para uma solução de recuperação de desastres**

![Mostra uma VM de compartilhamento de arquivos adicionada ao mesmo serviço de nuvem que contém as funções de servidor de banco de dados do SharePoint.](../media/AZenv-FSforDFSRandWSFC.png)
  
Neste diagrama, uma máquina virtual de compartilhamento de arquivos é adicionada à mesma sub-rede no Azure que contém as funções de servidor de banco de dados. Não adicione a máquina virtual de compartilhamento de arquivos a um conjunto de disponibilidade com outras funções de servidor, como as SQL Server funções.
  
Se você estiver preocupado com a alta disponibilidade dos logs, considere tomar uma abordagem diferente usando o backup SQL Server e a restauração com o Serviço de Armazenamento de Blob do [Azure](/sql/relational-databases/backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service). Este é um novo recurso no Azure que salva logs diretamente em uma URL de armazenamento de blob. Essa solução não inclui orientações sobre como usar esse recurso.
  
Ao projetar o farm de recuperação, lembre-se de que um ambiente de recuperação de desastres bem-sucedido reflete com precisão o farm de produção que você deseja recuperar. O tamanho do farm de recuperação não é a coisa mais importante no design, implantação e teste do farm de recuperação. A escala do farm varia de organização para organização com base nos requisitos comerciais. Pode ser possível usar um farm dimensionado para uma pequena paralisação ou até que as demandas de desempenho e capacidade exigirem que você dimensione o farm.
  
Configure o farm de recuperação da maneira mais idêntica possível ao farm de produção para que atenda aos requisitos do contrato de nível de serviço (SLA) e fornece a funcionalidade que você precisa para dar suporte à sua empresa. Ao projetar o ambiente de recuperação de desastres, também veja seu processo de gerenciamento de alterações para seu ambiente de produção. Recomendamos estender o processo de gerenciamento de alterações para o ambiente de recuperação atualizando o ambiente de recuperação no mesmo intervalo que o ambiente de produção. Como parte do processo de gerenciamento de alterações, recomendamos manter um inventário detalhado da configuração, aplicativos e usuários do farm. 
  
## <a name="phase-2-create-the-azure-virtual-network-and-vpn-connection"></a>Fase 2: Criar a rede virtual e a conexão VPN do Azure

Conectar uma rede local a uma rede virtual do [Microsoft Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md) mostra como planejar e implantar a rede virtual no Azure e como criar a conexão VPN. Siga as diretrizes no tópico para concluir os seguintes procedimentos:
  
- Planeje o espaço de endereço IP privado da Rede Virtual.
    
- Planeje as alterações de infraestrutura de roteamento para a Rede Virtual.
    
- Planeje regras de firewall para tráfego de e para o dispositivo VPN local.
    
- Crie a rede virtual entre locais no Azure.
    
- Configure o roteamento entre sua rede local e a Rede Virtual.
    
## <a name="phase-3-deploy-active-directory-and-domain-name-services-to-the-azure-virtual-network"></a>Fase 3: Implantar os Serviços de Nome de Domínio e Active Directory na rede virtual do Azure

Essa fase inclui a implantação do Windows Server Active Directory e DNS na Rede Virtual em um cenário híbrido, conforme descrito em Arquiteturas do [Microsoft Azure para SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) e, conforme ilustrado na figura a seguir.
  
**Figura: Configuração de domínio híbrido do Active Directory**

![Duas máquinas virtuais implantadas na rede virtual do Azure e a sub-rede do Farm do SharePoint são controladores de domínio de réplica e servidores DNS](../media/AZarch-HyADdomainConfig.png)
  
Na ilustração, duas máquinas virtuais são implantadas na mesma sub-rede. Essas máquinas virtuais estão hospedando duas funções: Active Directory e DNS.
  
Antes de implantar o Active Directory no Azure, leia Diretrizes para Implantar o [Windows Server Active Directory em Máquinas Virtuais do Azure.](/windows-server/identity/ad-ds/introduction-to-active-directory-domain-services-ad-ds-virtualization-level-100) Essas diretrizes ajudam a determinar se você precisa de uma arquitetura diferente ou configurações diferentes para sua solução.
  
Para obter orientações detalhadas sobre como configurar um controlador de domínio no Azure, consulte [Install a Replica Active Directory Domain Controller in Azure Virtual Networks](/windows-server/identity/ad-ds/introduction-to-active-directory-domain-services-ad-ds-virtualization-level-100).
  
Antes dessa fase, você não implantaa máquinas virtuais na Rede Virtual. As máquinas virtuais para hospedar o Active Directory e o DNS provavelmente não são as maiores máquinas virtuais de que você precisa para a solução. Antes de implantar essas máquinas virtuais, primeiro crie a maior máquina virtual que você planeja usar em sua Rede Virtual. Isso ajuda a garantir que sua solução aterre em uma marca no Azure que permita o maior tamanho de que você precisa. Você não precisa configurar essa máquina virtual no momento. Basta criar e deixar de lado. Se você não fizer isso, poderá encontrar uma limitação ao tentar criar máquinas virtuais maiores posteriormente, o que era um problema no momento em que este artigo foi escrito. 
  
## <a name="phase-4-deploy-the-sharepoint-recovery-farm-in-azure"></a>Fase 4: Implantar o farm de recuperação do SharePoint no Azure

Implante o farm do SharePoint em sua Rede Virtual de acordo com seus planos de design. Pode ser útil revisar o Planejamento do [SharePoint 2013](/previous-versions/azure/dn275958(v=azure.100)) nos Serviços de Infraestrutura do Azure antes de implantar funções do SharePoint no Azure.
  
Considere as seguintes práticas que aprendemos criando nossa prova de ambiente de conceito:
  
- Crie máquinas virtuais usando o portal do Azure ou o PowerShell.
    
- O Azure e o Hyper-V não suportam memória dinâmica. Certifique-se de que isso seja fatorado em seus planos de desempenho e capacidade.
    
- Reinicie máquinas virtuais por meio da interface do Azure, não do logon da máquina virtual em si. Usar a interface do Azure funciona melhor e é mais previsível.
    
- Se você quiser desligar uma máquina virtual para economizar custos, use a interface do Azure. Se você desligar do logon da máquina virtual, as cobranças continuarão acumulando.
    
- Use uma convenção de nomenisagem para as máquinas virtuais.
    
- Preste atenção ao local do datacenter em que as máquinas virtuais estão sendo implantadas.
    
- O recurso de dimensionamento automático no Azure não é suportado para funções do SharePoint.
    
- Não configure itens no farm que serão restaurados, como coleções de sites. 
    
## <a name="phase-5-set-up-dfsr-between-the-farms"></a>Fase 5: Configurar DFSR entre os farms

Para configurar a replicação de arquivo usando DFSR, use o snap-in gerenciamento dns. No entanto, antes da configuração do DFSR, faça logoff no servidor de arquivos local e no servidor de arquivos do Azure e habilita o serviço no Windows.
  
No Painel do Gerenciador de Servidores, conclua as seguintes etapas:
  
- Configure o servidor local.
    
- Inicie o **Assistente de Adição de Funções e Recursos**.
    
- Abra o **nó Serviços de Arquivo e Armazenamento.**
    
- Selecione **Namespaces DFS** e **replicação DFS**.
    
- Clique **em Próximo** para concluir as etapas do assistente.
    
A tabela a seguir fornece links para artigos de referência DFSR e postagens de blog.
  
**Tabela: Artigos de referência para DFSR**

|**Título**|**Descrição**|
|:-----|:-----|
|[Replicação](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770278(v=ws.11)) <br/> |Tópico do DfS Management TechNet com links para replicação  <br/> |
|[Replicação DFS: Guia de Sobrevivência](https://go.microsoft.com/fwlink/p/?LinkId=392737) <br/> |Wiki com links para informações do DFS  <br/> |
|[Replicação dfs: perguntas frequentes](/previous-versions/windows/it-pro/windows-server-2003/cc773238(v=ws.10)) <br/> |Tópico do DfS Replication TechNet  <br/> |
|[Blog de José Barreto](/archive/blogs/josebda/) <br/> |Blog escrito por um Gerente de Programa Principal na equipe do Servidor de Arquivos da Microsoft  <br/> |
|[A Equipe de Armazenamento na Microsoft - Blog do Gabinete de Arquivos](https://go.microsoft.com/fwlink/p/?LinkId=392740) <br/> |Blog sobre serviços de arquivo e recursos de armazenamento no Windows Server  <br/> |
   
## <a name="phase-6-set-up-log-shipping-to-the-recovery-farm"></a>Fase 6: Configurar o envio de log para o farm de recuperação

O envio de log é o componente essencial para configurar a recuperação de desastres neste ambiente. Você pode usar o envio de log para enviar automaticamente arquivos de log de transação para bancos de dados de uma instância de servidor de banco de dados principal para uma instância de servidor de banco de dados secundária. Para configurar o envio de log, consulte [Configure log shipping in SharePoint 2013](/sharepoint/administration/configure-log-shipping). 
  
> [!IMPORTANT]
> O suporte ao envio de log no SharePoint Server está limitado a determinados bancos de dados. Para obter mais informações, consulte Opções de recuperação de desastres e alta disponibilidade suportadas para bancos de dados do [SharePoint (SharePoint 2013)](/SharePoint/administration/supported-high-availability-and-disaster-recovery-options-for-sharepoint-databas). 
  
## <a name="phase-7-validate-failover-and-recovery"></a>Fase 7: Validar failover e recuperação

O objetivo dessa fase final é verificar se a solução de recuperação de desastres funciona conforme planejado. Para fazer isso, crie um evento de failover que fecha o farm de produção e inicia o farm de recuperação como um substituto. Você pode iniciar um cenário de failover manualmente ou usando scripts.
  
A primeira etapa é parar as solicitações de usuário de entrada para serviços de farm ou conteúdo. Você pode fazer isso desabilitando entradas DNS ou desativando os servidores Web front-end. Depois que o farm for "para baixo", você poderá fazer fail over para o farm de recuperação.
  
### <a name="stop-log-shipping"></a>Parar o envio de log

Você deve parar o envio de log antes da recuperação do farm. Pare o envio de log no servidor secundário no Azure primeiro e, em seguida, pare-o no servidor principal local. Use o seguinte script para interromper o envio de log no servidor secundário primeiro e, em seguida, no servidor principal. Os nomes de banco de dados no script podem ser diferentes, dependendo do ambiente.
  
```
-- This script removes log shipping from the server.
-- Commands must be executed on the secondary server first and then on the primary server.

SET NOCOUNT ON
DECLARE  @PriDB nvarchar(max)
,@SecDB nvarchar(250)
,@PriSrv nvarchar(250)
,@SecSrv nvarchar(250)

Set @PriDB= ''
SET @PriDB = UPPER(@PriDB)
SET @PriDB = REPLACE(@PriDB, ' ', '')
SET @PriDB = '''' + REPLACE(@PriDB, ',', ''', ''') + ''''

Set @SecDB = @PriDB

Exec ( 'Select  ''exec master..sp_delete_log_shipping_secondary_database '' + '''''''' + prm.primary_database +  ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

Exec ( 'Select  ''exec master..sp_delete_log_shipping_primary_secondary '' + '''''''' + prm.Primary_Database + '''''', '''''' + sec.Secondary_Server + '''''', '''''' + sec.Secondary_database + ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

Exec ( 'Select  ''exec master..sp_delete_log_shipping_primary_database '' + '''''''' + prm.primary_database +  ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

Exec ( 'Select  ''exec master..sp_delete_log_shipping_secondary_primary '' + '''''''' + prm.primary_server + '''''', '''''' + prm.primary_database +  ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

```

### <a name="restore-the-backups"></a>Restaurar os backups

Os backups devem ser restaurados na ordem em que foram criados. Antes de restaurar um backup de log de transação específico, você deve primeiro restaurar os seguintes backups anteriores sem reverter transações não confirmadas (ou seja, usando  `WITH NORECOVERY` ):
  
- O backup completo do banco de dados e o último backup diferencial - Restaure esses backups, se existirem, feitos antes do backup de log de transação específico. Antes da criação do backup de banco de dados completo ou diferencial mais recente, o banco de dados estava usando o modelo de recuperação completo ou o modelo de recuperação em massa.
    
- Todos os backups do log de transações - Restaure quaisquer backups de log de transação feitos após o backup completo do banco de dados ou o backup diferencial (se você restaurar um) e antes do backup de log de transação específico. Os backups de log devem ser aplicados na sequência na qual foram criados, sem quaisquer lacunas na cadeia de log.
    
Para recuperar o banco de dados de conteúdo no servidor secundário para que os sites renderizarem, remova todas as conexões de banco de dados antes da recuperação. Para restaurar o banco de dados, execute a instrução SQL seguinte.
  
```
restore database WSS_Content with recovery

```

> [!IMPORTANT]
> Ao usar o T-SQL explicitamente, especifique COM **NORECOVERY** ou **COM RECUPERAÇÃO** em cada instrução RESTORE para eliminar a ambiguidade— isso é muito importante ao escrever scripts. Depois que os backups completos e diferenciais são restaurados, os logs de transação podem ser restaurados SQL Server Management Studio. Além disso, como o envio de log já foi interrompido, o banco de dados de conteúdo está em estado de espera, portanto, você deve alterar o estado para acesso total.
  
No SQL Server Management Studio, clique com o botão direito do mouse no banco de dados **WSS_Content,** aponte para **Restaurar** Tarefas e clique em Log de Transações (se você não tiver restaurado o backup completo, isso não estará  >  disponível).  Para obter mais informações,[consulte Restore a Transaction Log Backup (SQL Server)](/sql/relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server).
  
### <a name="crawl-the-content-source"></a>Rastrear a fonte de conteúdo

Você deve iniciar um rastreamento completo para cada fonte de conteúdo para restaurar o Serviço de Pesquisa. Observe que você perde algumas informações de análise do farm local, como recomendações de pesquisa. Antes de iniciar os rastreamentos completos, use o cmdlet **Windows PowerShell Restore-SPEnterpriseSearchServiceApplication** e especifique o banco de dados de Administração de Pesquisa enviado e replicado por **log, <GUID>** Search_Service__DB_ . Este cmdlet fornece a configuração de pesquisa, esquema, propriedades gerenciadas, regras e fontes e cria um conjunto padrão dos outros componentes.
  
Para iniciar um rastreamento completo, conclua as seguintes etapas:
  
1. Na Administração Central do SharePoint 2013, vá para Aplicativos de Serviço de Gerenciamento de Aplicativos Gerenciar aplicativos de serviço e clique no aplicativo de Serviço de Pesquisa que você deseja  >    >  rastrear.
    
2. Na página **Administração da Pesquisa,** clique em Fontes de Conteúdo **,** aponte para a fonte de conteúdo que você deseja, clique na seta e clique em Iniciar **Rastreamento Completo.**
    
### <a name="recover-farm-services"></a>Recuperar serviços de farm

A tabela a seguir mostra como recuperar serviços que têm bancos de dados enviados por log, os serviços que têm bancos de dados, mas não são recomendados para restaurar com o envio de log e os serviços que não têm bancos de dados.
  
> [!IMPORTANT]
> Restaurar um banco de dados local do SharePoint no ambiente do Azure não recuperará nenhum serviço do SharePoint que você ainda não instalou no Azure manualmente. 
  
**Tabela: Referência do banco de dados do aplicativo de serviço**

|**Restaurar esses serviços de bancos de dados enviados por log**|**Esses serviços têm bancos de dados, mas recomendamos que você inicie esses serviços sem restaurar seus bancos de dados**|**Esses serviços não armazenam dados em bancos de dados; iniciar esses serviços após o failover**|
|:-----|:-----|:-----|
| Serviço de Tradução Automática <br/>  Serviço de Metadados Gerenciados <br/>  Serviço de Repositório Seguro <br/>  Perfil de Usuário. (Há suporte apenas para os bancos de dados De Perfil e Marcação Social. Não há suporte para o banco de dados de sincronização.) <br/>  Serviço de Configurações de Assinatura do Microsoft SharePoint Foundation <br/> | Coleta de Dados de Uso e Integridade <br/>  Serviço de Controle de Sessão <br/>  Automação do Word <br/> | Serviços do Excel <br/>  Serviços do PerformancePoint <br/>  Conversão do PowerPoint <br/>  Serviço de Gráficos do Visio <br/>  Gerenciamento de Trabalho <br/> |
   
O exemplo a seguir mostra como restaurar o serviço de Metadados Gerenciados de um banco de dados.
  
Isso usa o banco de dados Managed_Metadata_DB existente. Esse banco de dados é enviado por log, mas não há um aplicativo de serviço ativo no farm secundário, portanto, ele precisa ser conectado depois que o aplicativo de serviço estiver no local.
  
Primeiro, use  `New-SPMetadataServiceApplication` e especifique a  `DatabaseName` opção com o nome do banco de dados restaurado.
  
Em seguida, configure o novo Aplicativo de Serviço de Metadados Gerenciados no servidor secundário, da seguinte forma:
  
- Nome: Serviço de Metadados Gerenciados
    
- Servidor de banco de dados: o nome do banco de dados do log de transações enviado
    
- Nome do banco de dados: Managed_Metadata_DB
    
- Pool de aplicativos: Aplicativos de Serviço do SharePoint 
    
### <a name="manage-dns-records"></a>Gerenciar registros DNS

Você deve criar registros DNS manualmente para apontar para o farm do SharePoint.
  
Na maioria dos casos em que você tem vários servidores Web front-end, faz sentido aproveitar o recurso de Balanceamento de Carga de Rede no Windows Server 2012 ou um balanceador de carga de hardware para distribuir solicitações entre os servidores web front-end em seu farm. O balanceamento de carga de rede também pode ajudar a reduzir o risco distribuindo solicitações para os outros servidores se um dos servidores front-end da Web falhar. 
  
Normalmente, quando você configura o balanceamento de carga de rede, o cluster recebe um único endereço IP. Em seguida, você cria um registro de host DNS no provedor DNS para sua rede que aponta para o cluster. (Para esse projeto, colocamos um servidor DNS no Azure para resiliência em caso de falha no datacenter local.) Por exemplo, você pode criar um registro DNS, no Dns Manager no Active Directory, por exemplo, chamado , que aponta para o endereço IP do cluster  `https://sharepoint.contoso.com` balanceado por carga.
  
Para acesso externo ao farm do SharePoint, você pode criar um registro host em um servidor DNS externo com a mesma URL que os clientes usam em sua intranet (por exemplo, ) que aponta para um endereço IP externo no `https://sharepoint.contoso.com` firewall. (Uma prática prática, usando este exemplo, é configurar o DNS dividido para que o servidor DNS interno seja autoritativo e encaminhe solicitações diretamente para o cluster do farm do SharePoint, em vez de rotear solicitações DNS para o servidor `contoso.com` DNS externo.) Em seguida, você pode mapear o endereço IP externo para o endereço IP interno do cluster local para que os clientes encontrem os recursos que estão procurando.
  
A partir daqui, você pode executar alguns cenários diferentes de recuperação de desastres:
  
 **Cenário de exemplo: o farm local do SharePoint está indisponível devido a uma falha de hardware no farm local do SharePoint.** Nesse caso, depois de concluir as etapas de failover para o farm do SharePoint do Azure, você pode configurar o balanceamento de carga de rede nos servidores web-front-end do farm do SharePoint de recuperação, da mesma forma que fez com o farm local. Em seguida, você pode redirecionar o registro de host em seu provedor DNS interno para apontar para o endereço IP do cluster do farm de recuperação. Observe que pode levar algum tempo até que os registros DNS armazenados em cache em clientes sejam atualizados e apontem para o farm de recuperação.
  
 **Cenário de exemplo: o datacenter local é perdido completamente.** Esse cenário pode ocorrer devido a um desastre natural, como um incêndio ou uma inundação. Nesse caso, para uma empresa, você provavelmente teria um datacenter secundário hospedado em outra região, bem como sua sub-rede do Azure que tem seus próprios serviços de diretório e DNS. Como no cenário de desastre anterior, você pode redirecionar seus registros DNS internos e externos para apontar para o farm do SharePoint do Azure. Novamente, observe que a propagação do registro DNS pode levar algum tempo.
  
Se você estiver usando conjunto de sites nomeados por host, conforme recomendado na arquitetura e implantação do conjunto de sites nomeados pelo host [(SharePoint 2013),](/SharePoint/administration/host-named-site-collection-architecture-and-deployment)você pode ter vários conjunto de sites hospedados pelo mesmo aplicativo Web em seu farm do SharePoint, com nomes DNS exclusivos (por exemplo, e `https://sales.contoso.com` `https://marketing.contoso.com` ). Nesse caso, você pode criar registros DNS para cada conjunto de sites que apontem para o endereço IP do cluster. Depois que uma solicitação atinge seus servidores web-front-end do SharePoint, eles lidam com o roteamento de cada solicitação para o conjunto de sites apropriado.
  
## <a name="microsoft-proof-of-concept-environment"></a>Ambiente de prova de conceito da Microsoft

Projetamos e testamos um ambiente de prova de conceito para essa solução. O objetivo do design para nosso ambiente de teste era implantar e recuperar um farm do SharePoint que poderíamos encontrar em um ambiente do cliente. Fizemos várias suposições, mas sabemos que o farm precisava fornecer toda a funcionalidade inicial sem personalizações. A topologia foi projetada para alta disponibilidade usando diretrizes de práticas práticas do campo e do grupo de produtos.
  
A tabela a seguir descreve as máquinas virtuais do Hyper-V que criamos e configuramos para o ambiente de teste local.
  
**Tabela: Máquinas virtuais para teste local**

|**Nome do servidor**|**Função**|**Configuração**|
|:-----|:-----|:-----|
|DC1  <br/> |Controlador de domínio com Active Directory.  <br/> |Dois processadores  <br/> De 512 MB a 4 GB de RAM  <br/> Disco rígido de 1 x 127 GB  <br/> |
|RRAS  <br/> |Servidor configurado com a função RRAS (Serviço de Roteamento e Acesso Remoto).  <br/> |Dois processadores  <br/> 2 a 8 GB de RAM  <br/> Disco rígido de 1 x 127 GB  <br/> |
|FS1  <br/> |Servidor de arquivos com compartilhamentos para backups e um ponto de extremidade para DFSR.  <br/> |Quatro processadores  <br/> 2 a 12 GB de RAM  <br/> Disco rígido de 1 x 127 GB  <br/> SAN (disco rígido de 1 x 1 TB)  <br/> Disco rígido de 1 x 750 GB  <br/> |
|SP-WFE1, SP-WFE2  <br/> |Servidores Web front-end.  <br/> |Quatro processadores  <br/> 16 GB de RAM  <br/> |
|SP-APP1, SP-APP2, SP-APP3  <br/> |Servidores de aplicativos.  <br/> |Quatro processadores  <br/> 2 a 16 GB de RAM  <br/> |
|SP-SQL-HA1, SP-SQL-HA2  <br/> |Servidores de banco de dados, configurados com SQL Server grupos de disponibilidade AlwaysOn 2012 para fornecer alta disponibilidade. Essa configuração usa SP-SQL-HA1 e SP-SQL-HA2 como réplicas primárias e secundárias.  <br/> |Quatro processadores  <br/> 2 a 16 GB de RAM  <br/> |
   
A tabela a seguir descreve as configurações de unidade para as máquinas virtuais do Hyper-V que criamos e configuramos para os servidores web front-end e de aplicativos para o ambiente de teste local.
  
**Tabela: Requisitos de unidade de máquina virtual para os servidores Web e Aplicativo front-end para o teste local**

|**Letra da unidade**|**Tamanho**|**Nome do diretório**|**Path**|
|:-----|:-----|:-----|:-----|
|C  <br/> |80  <br/> |Unidade do sistema  <br/> |<DriveLetter>: \\ Arquivos de programas \\ Microsoft SQL Server\\  <br/> |
|E  <br/> |80  <br/> |Unidade de log (40 GB)  <br/> |<DriveLetter>: \\ Arquivos de Microsoft SQL Server \\ \\ MSSQL10_50.MSSQLSERVER \\ MSSQL \\ DATA  <br/> |
|S  <br/> |80  <br/> |Página (36 GB)  <br/> |<DriveLetter>: \\ Arquivos de programas Microsoft SQL Server dados \\ \\ MSSQL \\  <br/> |
   
A tabela a seguir descreve as configurações de unidade para as máquinas virtuais do Hyper-V criadas e configuradas para servir como servidores de banco de dados locais. Na página **Configuração do Mecanismo de** Banco de Dados, acesse a guia **Diretórios** de Dados para definir e confirmar as configurações mostradas na tabela a seguir.
  
**Tabela: Requisitos de unidade de máquina virtual para o servidor de banco de dados para o teste local**

|**Letra da unidade**|**Tamanho**|**Nome do diretório**|**Path**|
|:-----|:-----|:-----|:-----|
|C  <br/> |80  <br/> |Diretório raiz de dados  <br/> |<DriveLetter>: \\ Arquivos de programas \\ Microsoft SQL Server\\  <br/> |
|E  <br/> |500  <br/> |Diretório de banco de dados do usuário  <br/> |<DriveLetter>: \\ Arquivos de Microsoft SQL Server \\ \\ MSSQL10_50.MSSQLSERVER \\ MSSQL \\ DATA  <br/> |
|S  <br/> |500  <br/> |Diretório de log de banco de dados do usuário  <br/> |<DriveLetter>: \\ Arquivos de Microsoft SQL Server \\ \\ MSSQL10_50.MSSQLSERVER \\ MSSQL \\ DATA  <br/> |
|G  <br/> |500  <br/> |Diretório TEMP DB  <br/> |<DriveLetter>: \\ Arquivos de Microsoft SQL Server \\ \\ MSSQL10_50.MSSQLSERVER \\ MSSQL \\ DATA  <br/> |
|H  <br/> |500  <br/> |Diretório de log temp DB  <br/> |<DriveLetter>: \\ Arquivos de Microsoft SQL Server \\ \\ MSSQL10_50.MSSQLSERVER \\ MSSQL \\ DATA  <br/> |
   
### <a name="setting-up-the-test-environment"></a>Configurando o ambiente de teste

Durante as diferentes fases de implantação, a equipe de teste normalmente trabalhou na arquitetura local primeiro e, em seguida, no ambiente do Azure correspondente. Isso reflete os casos gerais do mundo real em que farms de produção locais já estão em execução. O que é ainda mais importante é que você deve saber a carga de trabalho de produção atual, a capacidade e o desempenho típico. Além de criar um modelo de recuperação de desastres que possa atender aos requisitos de negócios, você deve tamanho dos servidores do farm de recuperação para fornecer um nível mínimo de serviço. Em um ambiente de espera frio ou quente, um farm de recuperação normalmente é menor do que um farm de produção. Depois que o farm de recuperação for estável e em produção, o farm poderá ser dimensionado para cima e para fora para atender aos requisitos de carga de trabalho.
  
Implantamos nosso ambiente de teste nas três fases a seguir:
  
- Configurar a infraestrutura híbrida
    
- Provisionar os servidores
    
- Implantar os farms do SharePoint
    
#### <a name="set-up-the-hybrid-infrastructure"></a>Configurar a infraestrutura híbrida

Essa fase envolveu a configuração de um ambiente de domínio para o farm local e para o farm de recuperação no Azure. Além das tarefas normais associadas à configuração do Active Directory, a equipe de teste implementou uma solução de roteamento e uma conexão VPN entre os dois ambientes.
  
#### <a name="provision-the-servers"></a>Provisionar os servidores

Além dos servidores do farm, era necessário provisionar servidores para os controladores de domínio e configurar um servidor para manipular o RRAS, bem como a VPN site a site. Dois servidores de arquivos foram provisionados para o serviço DFSR e vários computadores cliente foram provisionados para testadores.
  
#### <a name="deploy-the-sharepoint-farms"></a>Implantar os farms do SharePoint

Os farms do SharePoint foram implantados em dois estágios para simplificar a estabilização do ambiente e a solução de problemas, se necessário. Durante o primeiro estágio, cada farm foi implantado no número mínimo de servidores para cada camada da topologia para dar suporte à funcionalidade necessária.
  
Criamos os servidores de banco de dados com SQL Server instalados antes de criar os servidores do SharePoint 2013. Como essa era uma nova implantação, criamos os grupos de disponibilidade antes de implantar o SharePoint. Criamos três grupos com base nas diretrizes de práticas práticas do MCS. 
  
> [!NOTE]
> Crie bancos de dados de espaço reservado para que você possa criar grupos de disponibilidade antes da instalação do SharePoint. Para obter mais informações, [consulte Configure SQL Server 2012 AlwaysOn Availability Groups for SharePoint 2013](/SharePoint/administration/configure-an-alwayson-availability-group)
  
Criamos o farm e ingressemos em servidores adicionais na seguinte ordem:
  
- Provisione SP-SQL-HA1 e SP-SQL-HA2.
    
- Configure AlwaysOn e crie os três grupos de disponibilidade para o farm. 
    
- Provisione o SP-APP1 para hospedar a Administração Central.
    
- Provisione SP-WFE1 e SP-WFE2 para hospedar o cache distribuído. 
    
Utilizamos o  _parâmetro skipRegisterAsDistributedCachehost_ quandopsconfig.exe **na** linha de comando. Para obter mais informações, [consulte Plan for feeds and the Distributed Cache service in SharePoint Server 2013](/sharepoint/administration/plan-for-feeds-and-the-distributed-cache-service). 
  
Repetimos as seguintes etapas no ambiente de recuperação:
  
- Provisione o AZ-SQL-HA1 e o AZ-SQL-HA2.
    
- Configure AlwaysOn e crie os três grupos de disponibilidade para o farm.
    
- Provisione o AZ-APP1 para hospedar a Administração Central.
    
- Provisione o AZ-WFE1 e o AZ-WFE2 para hospedar o cache distribuído.
    
Depois de configurarmos o cache distribuído e adicionamos usuários de teste e conteúdo de teste, iniciamos o estágio dois da implantação. Isso exigia o dimensionamento das camadas e a configuração dos servidores do farm para dar suporte à topologia de alta disponibilidade descrita na arquitetura do farm.
  
A tabela a seguir descreve os conjuntos de disponibilidade, sub-redes e máquinas virtuais que configuramos para nosso farm de recuperação.
  
**Tabela: Infraestrutura de farm de recuperação**

|**Nome do servidor**|**Função**|**Configuração**|**Sub-rede**|**Conjunto de disponibilidade**|
|:-----|:-----|:-----|:-----|:-----|
|spDRAD  <br/> |Controlador de domínio com Active Directory  <br/> |Dois processadores  <br/> De 512 MB a 4 GB de RAM  <br/> Disco rígido de 1 x 127 GB  <br/> |sp-ADservers  <br/> ||
|AZ-SP-FS  <br/> |Servidor de arquivos com compartilhamentos para backups e um ponto de extremidade para DFSR  <br/> | Configuração do A5: <br/>  Dois processadores <br/>  14 GB de RAM <br/>  Disco rígido de 1 x 127 GB <br/>  Disco rígido de 1 x 135 GB <br/>  Disco rígido de 1 x 127 GB <br/>  Disco rígido de 1 x 150 GB <br/> |sp-databaseservers  <br/> |DATA_SET  <br/> |
|AZ-WFE1, AZ -WFE2  <br/> |Servidores Web front-end  <br/> | Configuração do A5: <br/>  Dois processadores <br/>  14 GB de RAM <br/>  Disco rígido de 1 x 127 GB <br/> |sp-webservers  <br/> |WFE_SET  <br/> |
|AZ -APP1, AZ -APP2, AZ -APP3  <br/> |Servidores de aplicativos  <br/> | Configuração do A5: <br/>  Dois processadores <br/>  14 GB de RAM <br/>  Disco rígido de 1 x 127 GB <br/> |sp-applicationservers  <br/> |APP_SET  <br/> |
|AZ -SQL-HA1, AZ -SQL-HA2  <br/> |Servidores de banco de dados e réplicas primárias e secundárias para grupos de disponibilidade AlwaysOn  <br/> | Configuração do A5: <br/>  Dois processadores <br/>  14 GB de RAM <br/> |sp-databaseservers  <br/> |DATA_SET  <br/> |
   
### <a name="operations"></a>Operations

Após a equipe de teste ter estabilizado os ambientes do farm e concluído o teste funcional, eles iniciaram as seguintes tarefas de operações necessárias para configurar o ambiente de recuperação local:
  
- Configure backups completos e diferenciais.
    
- Configure o DFSR nos servidores de arquivos que transferem logs de transação entre o ambiente local e o ambiente do Azure.
    
- Configure o envio de log no servidor de banco de dados principal.
    
- Estabiliza, valida e soluciona problemas de envio de log, conforme necessário. Isso incluía identificar e documentar qualquer comportamento que pudesse causar problemas, como latência de rede, o que causaria falhas de envio de log ou sincronização de arquivos DFSR.
    
### <a name="databases"></a>Bancos de dados

Nossos testes de failover envolviam os seguintes bancos de dados: 
  
- WSS_Content
    
- ManagedMetadata
    
- Profile DB
    
- Sincronizar DB
    
- Social DB
    
- Hub de Tipo de Conteúdo (um banco de dados para um Hub de Syndication de Tipo de Conteúdo dedicado)
    
## <a name="troubleshooting-tips"></a>Dicas de solução de problemas

A seção explica os problemas encontrados durante nossos testes e suas soluções. 
  
### <a name="using-the-term-store-management-tool-caused-the-error-the-managed-metadata-store-or-connection-is-currently-not-available"></a>O uso da Ferramenta de Gerenciamento de Armazenamento de Termos causou o erro: "O Armazenamento de Metadados Gerenciados ou a Conexão não está disponível no momento".

Verifique se a conta do pool de aplicativos usada pelo aplicativo Web tem a permissão Acesso de Leitura ao Armazenamento de Termos.
  
### <a name="custom-term-sets-are-not-available-in-the-site-collection"></a>Conjuntos de termos personalizados não estão disponíveis no conjunto de sites

Verifique se há uma associação de aplicativo de serviço ausente entre seu conjunto de sites de conteúdo e seu hub de tipo de conteúdo. Além disso, na tela **Metadados <site collection name>** Gerenciados - Propriedades de conexão, certifique-se de que essa opção está habilitada: esse aplicativo de serviço é o local de armazenamento padrão para conjuntos de termos **específicos de coluna.**
  
### <a name="the-get-adforest-windows-powershell-command-generates-the-error-the-term-get-adforest-is-not-recognized-as-the-name-of-a-cmdlet-function-script-file-or-operable-program"></a>O Get-ADForest Windows PowerShell gera o erro, "O termo 'Get-ADForest' não é reconhecido como o nome de um cmdlet, função, arquivo de script ou programa operável".

Ao configurar perfis de usuário, você precisa do nome da floresta do Active Directory. No Assistente de Adicionar Funções e Recursos, certifique-se de que você habilitar o Módulo do Active Directory para Windows PowerShell (na seção Ferramentas de Administração do Servidor Remoto>Ferramentas de Administração de Função **>AD DS e Ferramentas AD LDS).** Além disso, execute os seguintes comandos antes de usar **Get-ADForest** para ajudar a garantir que suas dependências de software sejam carregadas.
  
```
Import-module servermanager
Import-module activedirectory

```

### <a name="availability-group-creation-fails-at-starting-the-alwayson_health-xevent-session-on-server-name"></a>A criação do grupo de disponibilidade falha ao iniciar a sessão XEvent 'AlwaysOn_health' em <server name> ' '

Verifique se ambos os nós do cluster de failover estão no Status "Up" e não "Pausado" ou "Parado". 
  
### <a name="sql-server-log-shipping-job-fails-with-access-denied-error-trying-to-connect-to-the-file-share"></a>SQL Server de envio de log falha com o erro de acesso negado ao tentar se conectar ao compartilhamento de arquivos

Verifique se o agente SQL Server está sendo executado sob credenciais de rede, em vez das credenciais padrão.
  
### <a name="sql-server-log-shipping-job-indicates-success-but-no-files-are-copied"></a>SQL Server trabalho de envio de log indica sucesso, mas nenhum arquivo é copiado

Isso acontece porque a preferência de backup padrão para um grupo de disponibilidade é **Prefer Secondary**. Verifique se você executará o trabalho de envio de log do servidor secundário para o grupo de disponibilidade em vez do principal; caso contrário, o trabalho falhará silenciosamente. 
  
### <a name="managed-metadata-service-or-other-sharepoint-service-fails-to-start-automatically-after-installation"></a>O serviço de Metadados Gerenciados (ou outro serviço do SharePoint) falha ao iniciar automaticamente após a instalação

Os serviços podem levar vários minutos para começar, dependendo do desempenho e da carga atual do SharePoint Server. Clique manualmente **em Iniciar** para o serviço e forneça tempo adequado para inicialização enquanto atualize ocasionalmente a tela Serviços no Servidor para monitorar seu status. Caso o serviço permaneça parado, habilita o log de diagnóstico do SharePoint, tente iniciar o serviço novamente e verifique se há erros no log. Para obter mais informações, consulte [Configure diagnostic logging in SharePoint 2013](/sharepoint/administration/configure-diagnostic-logging)
  
### <a name="after-changing-dns-to-the-azure-failover-environment-client-browsers-continue-to-use-the-old-ip-address-for-the-sharepoint-site"></a>Depois de alterar o DNS para o ambiente de failover do Azure, os navegadores do cliente continuam a usar o endereço IP antigo para o site do SharePoint

A alteração de DNS pode não estar visível para todos os clientes imediatamente. Em um cliente de teste, execute o seguinte comando de um prompt de comando elevado e tente acessar o site novamente.
  
```
Ipconfig /flushdns
```

## <a name="additional-resources"></a>Recursos adicionais

[Suporte para as opções de alta disponibilidade e recuperação de desastres para bancos de dados do SharePoint](/sharepoint/administration/supported-high-availability-and-disaster-recovery-options-for-sharepoint-databas)
  
[Configurar SQL Server Grupos de Disponibilidade AlwaysOn do 2012 para SharePoint 2013](/SharePoint/administration/configure-an-alwayson-availability-group)
  
## <a name="see-also"></a>Confira também

[Centro de soluções e arquitetura do Microsoft 365](../solutions/index.yml)