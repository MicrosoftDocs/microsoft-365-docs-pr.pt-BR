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
description: Este artigo descreve como usar o Azure para criar um ambiente de recuperação de desastres para seu farm do SharePoint local.
ms.openlocfilehash: d1643f3fa0275ef9fbb01372869ca551b9fed495
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687045"
---
# <a name="sharepoint-server-2013-disaster-recovery-in-microsoft-azure"></a>Recuperação de Desastre do SharePoint Server 2013 no Microsoft Azure

 Usando o Azure, você pode criar um ambiente de recuperação de desastres para seu farm local do SharePoint. Este artigo descreve como criar e implementar esta solução.

 **Assista ao vídeo visão geral da recuperação de desastre do SharePoint Server 2013**
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1b73ec8f-29bd-44eb-aa3a-f7932784bfd9?autoplay=false]
  
 Quando o desastre ocorrer no ambiente local do SharePoint, sua prioridade máxima é fazer com que o sistema volte a funcionar rapidamente. A recuperação de desastres com o SharePoint é mais rápida e fácil quando você tem um ambiente de backup já em execução no Microsoft Azure. Este vídeo explica os principais conceitos de um ambiente de failover quente do SharePoint e complementa os detalhes completos disponíveis neste artigo.
  
Use este artigo com o modelo de solução a seguir: **recuperação de desastres do SharePoint no Microsoft Azure**.
  
[![Processo de recuperação de desastres do SharePoint para o Azure](../media/SP-DR-Azure.png)](https://go.microsoft.com/fwlink/p/?LinkId=392555)
  
 [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555) |  [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)
  
## <a name="use-azure-infrastructure-services-for-disaster-recovery"></a>Usar os serviços de infraestrutura do Azure para recuperação de desastre

Muitas organizações não têm um ambiente de recuperação de desastres para o SharePoint, que pode ser caro criar e manter no local. Os serviços de infraestrutura do Azure fornecem opções atraentes para ambientes de recuperação de desastres que são mais flexíveis e mais baratos do que as alternativas locais.
  
As vantagens de usar os serviços de infraestrutura do Azure incluem:
  
- **Menos recursos dispendiosos** Manter e pagar menos recursos do que os ambientes de recuperação de desastres locais. O número de recursos depende do ambiente de recuperação de desastres que você escolhe: espera passiva, espera ativa ou espera ativa.
    
- **Melhor flexibilidade de recursos** No caso de um desastre, dimensione facilmente seu farm do SharePoint de recuperação para atender aos requisitos de carga. Expanda quando não precisar mais dos recursos.
    
- **Compromisso de datacenter inferior** Use os serviços de infraestrutura do Azure em vez de investir em um data center secundário em uma região diferente.
    
Há opções menos complexas para organizações que são apenas introdução à recuperação de desastres e opções avançadas para organizações com requisitos de alta resiliência. As definições para ambientes de espera passiva, quente e hot standby são um pouco diferentes quando o ambiente está hospedado em uma plataforma de nuvem. A tabela a seguir descreve esses ambientes para a criação de um farm de recuperação do SharePoint no Azure.
  
**Tabela: ambientes de recuperação**

|**Tipo de ambiente de recuperação**|**Descrição**|
|:-----|:-----|
|Ativos  <br/> |Um farm totalmente dimensionado é provisionado, atualizado e executado no modo de espera.  <br/> |
|Partida  <br/> |O farm é criado e as máquinas virtuais estão em execução e atualizadas.  <br/> A recuperação inclui anexar bancos de dados de conteúdo, aplicativos de serviço de provisionamento e conteúdo de rastreamento.  <br/> O farm pode ser uma versão menor do farm de produção e, em seguida, dimensionado para atender à base de usuários completo.  <br/> |
|Interesse  <br/> |O farm está totalmente construído, mas as máquinas virtuais são interrompidas.  <br/> Manter o ambiente inclui o início das máquinas virtuais, de hora para hora, aplicação de patch, atualização e verificação do ambiente.  <br/> Inicie o ambiente completo em caso de desastre.  <br/> |
   
É importante avaliar os RTOs (objetivos de tempo de recuperação) da sua organização e RPOs (objetivos de ponto de recuperação). Esses requisitos determinam qual ambiente é o investimento mais apropriado para sua organização.
  
As orientações deste artigo descrevem como implementar um ambiente de espera passiva. Você também pode adaptá-lo a um ambiente de espera Cold, embora seja necessário seguir procedimentos adicionais para dar suporte a esse tipo de ambiente. Este artigo não descreve como implementar um ambiente de espera ativa.
  
Para obter mais informações sobre soluções de recuperação de desastres, confira [conceitos de alta disponibilidade e recuperação de desastre no SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkID=393114) e [escolha uma estratégia de recuperação de desastre para o SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=203228).
  
## <a name="solution-description"></a>Descrição da solução

A solução de recuperação de desastres em espera passiva requer o seguinte ambiente:
  
- Um farm de produção do SharePoint local
    
- Um farm de recuperação do SharePoint no Azure
    
- Uma conexão VPN de site a site entre os dois ambientes
    
A figura a seguir ilustra esses três elementos.
  
**Figura: elementos de uma solução de espera passiva no Azure**

![Elementos de uma solução de espera passiva do SharePoint no Azure](../media/AZarch-AZWarmStndby.png)
  
O envio de logs do SQL Server com o DFSR (Distributed File System Replication) é usado para copiar backups de banco de dados e logs de transações para o farm de recuperação no Azure: 
  
- O DFSR transfere logs do ambiente de produção para o ambiente de recuperação. Em um cenário WAN, a DFSR é mais eficiente do que enviar os logs diretamente para o servidor secundário no Azure.
    
- Os logs são repetidos no SQL Server no ambiente de recuperação do Azure.
    
- Você não anexa os bancos de dados de conteúdo do SharePoint enviados por log no ambiente de recuperação até que um exercício de recuperação seja realizado.
    
Execute as seguintes etapas para recuperar o farm:
  
1. Parar o envio de logs.
    
2. Pare de aceitar o tráfego para o farm principal.
    
3. Reproduza os logs de transação finais.
    
4. Anexe os bancos de dados de conteúdo ao farm.
    
5. Restaure os aplicativos de serviço dos bancos de dados de serviços replicados.
    
6. Atualizar registros DNS (sistema de nomes de domínio) para apontar para o farm de recuperação.
    
7. Inicie um rastreamento completo.
    
Recomendamos que você reconheça essas etapas regularmente e documente-as para ajudar a garantir que a recuperação ao vivo seja executada sem problemas. Anexar bancos de dados de conteúdo e restaurar aplicativos de serviço pode levar algum tempo e geralmente envolve algumas configurações manuais.
  
Após a execução da recuperação, esta solução fornece os itens listados na tabela a seguir.
  
**Tabela: objetivos de recuperação de solução**

|**Item**|**Descrição**|
|:-----|:-----|
|Sites e conteúdo  <br/> |Sites e conteúdo estão disponíveis no ambiente de recuperação.  <br/> |
|Uma nova instância de pesquisa  <br/> |Nesta solução de espera passiva, a pesquisa não é restaurada dos bancos de dados de pesquisa. Os componentes de pesquisa no farm de recuperação são configurados da mesma forma possível para o farm de produção. Depois que os sites e o conteúdo são restaurados, um rastreamento completo é iniciado para reconstruir o índice de pesquisa. Você não precisa aguardar a conclusão do rastreamento para disponibilizar os sites e o conteúdo.  <br/> |
|Serviços  <br/> | Os serviços que armazenam dados em bancos de dados são restaurados dos bancos de dados enviados por log. Os serviços que não armazenam dados em bancos de dados são simplesmente iniciados. <br/>  Nem todos os serviços com bancos de dados precisam ser restaurados. Os seguintes serviços não precisam ser restaurados dos bancos de dados e podem ser iniciados após o failover: <br/>  Coleta de Dados de Uso e Integridade <br/>  Serviço de Controle de Sessão <br/>  Automação do Word <br/>  Qualquer outro serviço que não use um banco de dados <br/> |
   
Você pode trabalhar com o MCS (serviços de consultoria da Microsoft) ou um parceiro para tratar de objetivos de recuperação mais complexos. Eles são resumidos na tabela a seguir.
  
**Tabela: outros itens que podem ser tratados pelo MCS ou por um parceiro**

|**Item**|**Descrição**|
|:-----|:-----|
|Sincronizando soluções de farm personalizadas  <br/> |O ideal é que a configuração do farm de recuperação seja idêntica ao farm de produção. Você pode trabalhar com um consultor ou parceiro para avaliar se as soluções de farm personalizadas são replicadas e se o processo está em vigor para manter os dois ambientes sincronizados.  <br/> |
|Conexões com fontes de dados no local  <br/> |Pode não ser prático replicar conexões para sistemas de dados back-end, como conexões de controlador de domínio de backup (BDC) e fontes de conteúdo de pesquisa.  <br/> |
|Cenários de restauração de pesquisa  <br/> |Como as implantações corporativas tendem a ser razoavelmente exclusivas e complexas, a restauração de pesquisa dos bancos de dados requer um maior investimento. Você pode trabalhar com um consultor ou parceiro para identificar e implementar cenários de restauração de pesquisa que sua organização possa exigir.  <br/> |
   
As orientações fornecidas neste artigo pressupõem que o farm local já tenha sido projetado e implantado.
  
## <a name="detailed-architecture"></a>Arquitetura detalhada

O ideal é que a configuração do farm de recuperação no Azure seja idêntica ao farm de produção local, incluindo o seguinte:
  
- A mesma representação de funções de servidor
    
- A mesma configuração de personalizações
    
- A mesma configuração de componentes de pesquisa
    
O ambiente no Azure pode ser uma versão menor do farm de produção. Se você planeja expandir o farm de recuperação após o failover, é importante que cada tipo de função de servidor seja inicialmente representada.
  
Algumas configurações podem não ser práticas para replicar no ambiente de failover. Certifique-se de testar os procedimentos e o ambiente de failover para ajudar a garantir que o farm de failover forneça o nível de serviço esperado.
  
Esta solução não prescreve uma topologia específica para um farm do SharePoint. O foco dessa solução é usar o Azure para o farm de failover e implementar o envio de logs e o DFSR entre os dois ambientes.
  
### <a name="warm-standby-environments"></a>Ambientes de espera passiva

Em um ambiente de espera passiva, todas as máquinas virtuais no ambiente do Azure estão em execução. O ambiente está pronto para um exercício ou evento de failover.
  
A figura a seguir ilustra uma solução de recuperação de desastres de um farm local do SharePoint para um farm do SharePoint baseado no Azure que está configurado como um ambiente de espera passiva.
  
**Figura: topologia e elementos chave de um farm de produção e um farm de recuperação em espera passiva**

![Topologia de um farm do SharePoint e um farm de recuperação em espera passiva](../media/AZarch-AZWarmStndby.png)
  
Neste diagrama:
  
- Dois ambientes são ilustrados lado a lado: o farm do SharePoint local e o farm em espera passiva no Azure.
    
- Cada ambiente inclui um compartilhamento de arquivos.
    
- Cada farm inclui quatro camadas. Para obter alta disponibilidade, cada camada inclui dois servidores ou máquinas virtuais que são configurados de forma idêntica para uma função específica, como serviços de front-end, cache distribuído, serviços de back-end e bancos de dados. Não é importante nesta ilustração para chamar componentes específicos. Os dois farms são configurados de forma idêntica.
    
- A quarta camada é a camada de banco de dados. O envio de logs é usado para copiar logs do servidor de banco de dados secundário no ambiente local para o compartilhamento de arquivos no mesmo ambiente.
    
- A DFSR copia os arquivos do compartilhamento de arquivos no ambiente local para o compartilhamento de arquivos no ambiente Azure.
    
- O envio de logs reproduz os logs do compartilhamento de arquivos no ambiente Azure para a réplica primária no grupo de disponibilidade AlwaysOn do SQL Server no ambiente secundário.
    
### <a name="cold-standby-environments"></a>Ambientes de espera Cold

Em um ambiente de espera Cold, a maioria das máquinas virtuais do farm do SharePoint pode ser desligada. (Recomendamos às vezes iniciar as máquinas virtuais, como a cada duas semanas ou uma vez por mês, para que cada máquina virtual possa sincronizar com o domínio.) As seguintes máquinas virtuais no ambiente de recuperação do Azure devem permanecer em execução para ajudar a garantir operações contínuas de envio de logs e DFSR:
  
- O compartilhamento de arquivos
    
- Servidor de banco de dados principal
    
- Pelo menos uma máquina virtual que executa os serviços de domínio Active Directory do Windows Server e DNS
    
A figura a seguir mostra um ambiente de failover do Azure no qual a máquina virtual de compartilhamento de arquivos e a máquina virtual principal do banco de dados do SharePoint estão em execução. Todas as outras máquinas virtuais do SharePoint são interrompidas. A máquina virtual que está executando o Windows Server Active Directory e o DNS não é exibida.
  
**Figura: farm de recuperação de espera Cold com máquinas virtuais em execução**

![Elementos de uma solução de espera do SharePoint Cold no Azure](../media/AZarch-AZColdStndby.png)
  
Após o failover para um ambiente de espera Cold, todas as máquinas virtuais são iniciadas e o método para obter a alta disponibilidade dos servidores de banco de dados deve ser configurado, como grupos de disponibilidade AlwaysOn do SQL Server.
  
Se vários grupos de armazenamento forem implementados (os bancos de dados são distribuídos em mais de um conjunto de alta disponibilidade do SQL Server), o banco de dados principal de cada grupo de armazenamento deverá estar em execução para aceitar os logs associados ao grupo de armazenamento.
  
### <a name="skills-and-experience"></a>Habilidades e experiência

Várias tecnologias são usadas nesta solução de recuperação de desastres. Para ajudar a garantir que essas tecnologias interajam conforme o esperado, cada componente no ambiente local e do Azure deve estar instalado e configurado corretamente. Recomendamos que a pessoa ou a equipe que configura essa solução tenha um sólido conhecimento de trabalho e habilidades práticas com as tecnologias descritas nos seguintes artigos:
  
- [Serviços de replicação do sistema de arquivos distribuídos (DFS)](https://go.microsoft.com/fwlink/p/?LinkId=392698)
    
- [Clustering de failover do Windows Server (WSFC) com o SQL Server](https://go.microsoft.com/fwlink/p/?LinkId=392701)
    
- [Grupos de Disponibilidade AlwaysOn (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=392725)
    
- [Backup e restauração de bancos de dados do SQL Server](https://go.microsoft.com/fwlink/p/?LinkId=392728)
    
- [Instalação do SharePoint Server 2013 e implantação de farm](https://go.microsoft.com/fwlink/p/?LinkId=393119)
    
- [Microsoft Azure](https://go.microsoft.com/fwlink/p/?LinkId=392729)
    
Por fim, recomendamos habilidades de script que você pode usar para automatizar tarefas associadas a essas tecnologias. É possível usar as interfaces de usuário disponíveis para concluir todas as tarefas descritas nesta solução. No entanto, uma abordagem manual pode consumir tempo e propenso a erros e fornece resultados inconsistentes.
  
Além do Windows PowerShell, há também bibliotecas do Windows PowerShell para o SQL Server, o SharePoint Server e o Azure. Não esqueça o T-SQL, que também pode ajudar a reduzir o tempo para configurar e manter seu ambiente de recuperação de desastres.
  
## <a name="disaster-recovery-roadmap"></a>Roteiro de recuperação de desastre

![Representação visual do mapa de recuperação de desastres do SharePoint.](../media/Azure-DRroadmap.png)
  
Este roteiro pressupõe que você já tem um farm do SharePoint Server 2013 implantado na produção.
  
**Tabela: mapa para recuperação de desastre**

|**Fase**|**Descrição**|
|:-----|:-----|
|Fase 1  <br/> |Projete o ambiente de recuperação de desastres.  <br/> |
|Fase 2  <br/> |Crie a rede virtual do Azure e a conexão VPN.  <br/> |
|Fase 3  <br/> |Implantar o Windows Active Directory e os serviços de nome de domínio na rede virtual do Azure.  <br/> |
|Fase 4  <br/> |Implante o farm de recuperação do SharePoint no Azure.  <br/> |
|Fase 5  <br/> |Configurar o DFSR entre os farms.  <br/> |
|Fase 6  <br/> |Configure o envio de logs para o farm de recuperação.  <br/> |
|Fase 7  <br/> | Validar soluções de failover e recuperação. Isso inclui os seguintes procedimentos e tecnologias: <br/>  Parar o envio de logs. <br/>  Restaure os backups. <br/>  Rastrear conteúdo. <br/>  Recuperar serviços. <br/>  Gerenciar registros DNS. <br/> |
   
## <a name="phase-1-design-the-disaster-recovery-environment"></a>Fase 1: projetar o ambiente de recuperação de desastres

Use as orientações em [arquiteturas do Microsoft Azure para o SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) para projetar o ambiente de recuperação de desastres, incluindo o farm de recuperação do SharePoint. Você pode usar os elementos gráficos da [solução de recuperação de desastres do SharePoint no arquivo do Azure](https://go.microsoft.com/fwlink/p/?LinkId=392554) Visio para iniciar o processo de design. Recomendamos que você projete todo o ambiente antes de iniciar qualquer trabalho no ambiente do Azure.
  
Além da orientação fornecida nas [arquiteturas do Microsoft Azure para o sharepoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) para criar a rede virtual, a conexão VPN, o Active Directory e o farm do SharePoint, não deixe de adicionar uma função de compartilhamento de arquivos ao ambiente do Azure.
  
Para dar suporte ao envio de logs em uma solução de recuperação de desastres, uma máquina virtual de compartilhamento de arquivos é adicionada à sub-rede onde residem as funções de banco de dados. O compartilhamento de arquivos também serve como o terceiro nó de uma maioria de nós para o grupo de disponibilidade AlwaysOn do SQL Server. Esta é a configuração recomendada para um farm padrão do SharePoint que usa os grupos de disponibilidade AlwaysOn do SQL Server. 
  
> [!NOTE]
> É importante revisar os pré-requisitos de um banco de dados para participar de um grupo de disponibilidade AlwaysOn do SQL Server. Para obter mais informações, consulte [pré-requisitos, restrições e recomendações para grupos de disponibilidade AlwaysOn](https://go.microsoft.com/fwlink/p/?LinkId=510870). 
  
**Figura: posicionamento de um servidor de arquivos usado para uma solução de recuperação de desastres**

![Mostra uma VM de compartilhamento de arquivos adicionada ao mesmo serviço de nuvem que contém as funções de servidor de banco de dados do SharePoint.](../media/AZenv-FSforDFSRandWSFC.png)
  
Neste diagrama, uma máquina virtual de compartilhamento de arquivos é adicionada à mesma sub-rede no Azure que contém as funções de servidor de banco de dados. Não adicione a máquina virtual de compartilhamento de arquivos a um conjunto de disponibilidade com outras funções de servidor, como as funções do SQL Server.
  
Se você estiver preocupado com a alta disponibilidade dos logs, considere a possibilidade de realizar uma abordagem diferente usando o [backup e a restauração do SQL Server com o serviço de armazenamento de blob do Azure](https://go.microsoft.com/fwlink/p/?LinkId=393113). Este é um novo recurso no Azure que salva logs diretamente em uma URL de armazenamento BLOB. Esta solução não inclui orientações sobre como usar esse recurso.
  
Ao projetar o farm de recuperação, lembre-se de que um ambiente bem-sucedido de recuperação de desastres reflete precisamente o farm de produção que você deseja recuperar. O tamanho do farm de recuperação não é o mais importante no projeto, implantação e teste do farm de recuperação. A escala do farm varia de organização para organização com base nos requisitos de negócios. Talvez seja possível usar um farm em escala para uma pequena interrupção ou até que as demandas de desempenho e capacidade exijam que você dimensione o farm.
  
Configure o farm de recuperação de forma idêntica ao possível para o farm de produção, de forma que ele atenda aos requisitos de SLA (contrato de nível de serviço) e forneça a funcionalidade de que você precisa para dar suporte à sua empresa. Ao projetar o ambiente de recuperação de desastres, examine também seu processo de gerenciamento de alterações para seu ambiente de produção. Recomendamos que você estenda o processo de gerenciamento de mudanças para o ambiente de recuperação, atualizando o ambiente de recuperação no mesmo intervalo do ambiente de produção. Como parte do processo de gerenciamento de mudanças, recomendamos manter um inventário detalhado da configuração, dos aplicativos e dos usuários do farm. 
  
## <a name="phase-2-create-the-azure-virtual-network-and-vpn-connection"></a>Fase 2: criar a rede virtual do Azure e a conexão VPN

[Conectar uma rede local a uma rede virtual do Microsoft Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md) mostra como planejar e implantar a rede virtual no Azure e como criar a conexão VPN. Siga as orientações no tópico para concluir os seguintes procedimentos:
  
- Planejar o espaço de endereço IP privado da rede virtual.
    
- Planejar as alterações da infraestrutura de roteamento para a rede virtual.
    
- Planejar regras de firewall para o tráfego de e para o dispositivo VPN local.
    
- Crie a rede virtual entre locais no Azure.
    
- Configure o roteamento entre a rede local e a rede virtual.
    
## <a name="phase-3-deploy-active-directory-and-domain-name-services-to-the-azure-virtual-network"></a>Fase 3: implantar o Active Directory e os serviços de nome de domínio na rede virtual do Azure

Esta fase inclui a implantação do Active Directory do Windows Server e do DNS para a rede virtual em um cenário híbrido, conforme descrito nas [arquiteturas do Microsoft Azure para o SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) e, conforme ilustrado na figura a seguir.
  
**Figura: configuração de domínio do Active Directory híbrido**

![Duas máquinas virtuais implantadas para a rede virtual do Azure e a sub-rede do farm do SharePoint são controladores de domínio de réplica e servidores DNS](../media/AZarch-HyADdomainConfig.png)
  
Na ilustração, duas máquinas virtuais são implantadas na mesma sub-rede. Essas máquinas virtuais estão hospedando duas funções: Active Directory e DNS.
  
Antes de implantar o Active Directory no Azure, leia as [diretrizes para implantar o Windows Server Active Directory nas máquinas virtuais do Azure](https://go.microsoft.com/fwlink/p/?linkid=392681). Essas diretrizes ajudam a determinar se você precisa de uma arquitetura diferente ou de definições de configuração diferentes para sua solução.
  
Para obter orientações detalhadas sobre como configurar um controlador de domínio no Azure, confira [instalar um controlador de domínio do Active Directory de réplica nas redes virtuais do Azure](https://go.microsoft.com/fwlink/p/?LinkId=392687).
  
Antes desta fase, você não implantou máquinas virtuais na rede virtual. As máquinas virtuais para hospedar o Active Directory e o DNS provavelmente não são as maiores máquinas virtuais que você precisa para a solução. Antes de implantar essas máquinas virtuais, primeiro crie a maior máquina virtual que você planeja usar em sua rede virtual. Isso ajuda a garantir que sua solução fique em uma marca no Azure que permite o maior tamanho necessário. Você não precisa configurar esta máquina virtual no momento. Basta criá-lo e defini-lo de lado. Se você não fizer isso, poderá ter uma limitação ao tentar criar máquinas virtuais maiores mais tarde, que foi um problema no momento em que este artigo foi escrito. 
  
## <a name="phase-4-deploy-the-sharepoint-recovery-farm-in-azure"></a>Fase 4: implantar o farm de recuperação do SharePoint no Azure

Implante o farm do SharePoint em sua rede virtual de acordo com seus planos de design. Pode ser útil analisar o [planejamento do SharePoint 2013 nos serviços de infraestrutura do Azure](https://go.microsoft.com/fwlink/p/?LinkId=400984) antes de implantar funções do SharePoint no Azure.
  
Considere as seguintes práticas que aprendemos criando nosso ambiente de verificação de conceito:
  
- Crie máquinas virtuais usando o portal do Azure ou o PowerShell.
    
- O Azure e o Hyper-V não oferecem suporte à memória dinâmica. Certifique-se de que isso seja fatorado nos planos de desempenho e capacidade.
    
- Reinicie as máquinas virtuais por meio da interface do Azure, e não do próprio logon na máquina virtual. O uso da interface do Azure funciona melhor e é mais previsível.
    
- Se você deseja desligar uma máquina virtual para salvar custos, use a interface do Azure. Se você desligar do logon da máquina virtual, os encargos continuarão a ser acumulados.
    
- Use uma Convenção de nomenclatura para as máquinas virtuais.
    
- Preste atenção à localização do datacenter das máquinas virtuais que estão sendo implantadas.
    
- O recurso de dimensionamento automático no Azure não é suportado para funções do SharePoint.
    
- Não configure itens no farm que serão restaurados, como conjuntos de sites. 
    
## <a name="phase-5-set-up-dfsr-between-the-farms"></a>Fase 5: configurar o DFSR entre os farms

Para configurar a replicação de arquivos usando o DFSR, use o snap-in de gerenciamento de DNS. No entanto, antes da configuração de DFSR, faça logon no servidor de arquivos local e no servidor de arquivos do Azure e habilite o serviço no Windows.
  
No painel Gerenciador do servidor, conclua as seguintes etapas:
  
- Configure o servidor local.
    
- Inicie o **Assistente de adição de funções e recursos**.
    
- Abra o **arquivo e** o nó serviços de armazenamento.
    
- Selecione **namespaces DFS** e **Replicação DFS**.
    
- Clique em **Avançar** para concluir as etapas do assistente.
    
A tabela a seguir fornece links para artigos de referência DFSR e postagens de blog.
  
**Tabela: artigos de referência para DFSR**

|**Título**|**Descrição**|
|:-----|:-----|
|[CRR](https://go.microsoft.com/fwlink/p/?LinkId=392732) <br/> |Tópico de Gerenciamento DFS TechNet com links para replicação  <br/> |
|[Replicação DFS: guia de sobrevivência](https://go.microsoft.com/fwlink/p/?LinkId=392737) <br/> |Wiki com links para informações do DFS  <br/> |
|[Replicação DFS: perguntas frequentes](https://go.microsoft.com/fwlink/p/?LinkId=392738) <br/> |Tópico TechNet de Replicação DFS  <br/> |
|[Blog de Jose Barreto](https://go.microsoft.com/fwlink/p/?LinkId=392739) <br/> |Blog escrito por um gerente de programa principal na equipe de servidor de arquivos da Microsoft  <br/> |
|[A equipe de armazenamento no blog da Microsoft-arquivo de gabinete](https://go.microsoft.com/fwlink/p/?LinkId=392740) <br/> |Blog sobre serviços de arquivo e recursos de armazenamento no Windows Server  <br/> |
   
## <a name="phase-6-set-up-log-shipping-to-the-recovery-farm"></a>Fase 6: configurar o envio de log para o farm de recuperação

O envio de logs é o componente crítico para configurar a recuperação de desastres nesse ambiente. Você pode usar o envio de logs para enviar automaticamente arquivos de log de transações para bancos de dados de uma instância de servidor de banco de dados principal para uma instância de servidor de banco de dados secundária. Para configurar o envio de logs, confira [Configurar o envio de logs no SharePoint 2013](https://docs.microsoft.com/sharepoint/administration/configure-log-shipping). 
  
> [!IMPORTANT]
> O suporte ao envio de logs no SharePoint Server está limitado a determinados bancos de dados. Confira mais informações em [Opções de alta disponibilidade e recuperação de desastres com suporte para bancos de dados do SharePoint (SharePoint 2013)](https://go.microsoft.com/fwlink/p/?LinkId=393121). 
  
## <a name="phase-7-validate-failover-and-recovery"></a>Fase 7: validar o failover e a recuperação

O objetivo desta fase final é verificar se a solução de recuperação de desastres funciona conforme planejado. Para fazer isso, crie um evento de failover que desliga o farm de produção e inicia o farm de recuperação como uma substituição. Você pode iniciar um cenário de failover manualmente ou usando scripts.
  
A primeira etapa é interromper as solicitações de entrada do usuário para serviços ou conteúdo de farm. Você pode fazer isso desabilitando entradas DNS ou desligando os servidores Web front-end. Depois que o farm estiver "inoperante", você poderá fazer failover para o farm de recuperação.
  
### <a name="stop-log-shipping"></a>Parar envio de logs

Você deve interromper o envio de logs antes da recuperação do farm. Interrompa o envio de log no servidor secundário no Azure primeiro e, em seguida, interrompa-o no servidor primário local. Use o script a seguir para interromper o envio de logs no servidor secundário primeiro e, em seguida, no servidor primário. Os nomes de banco de dados no script podem ser diferentes, dependendo do seu ambiente.
  
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

Os backups devem ser restaurados na ordem em que foram criados. Antes de poder restaurar um backup de log de transação específico, primeiro você deve restaurar os seguintes backups anteriores sem reverter transações não confirmadas (ou seja, usando  `WITH NORECOVERY` ):
  
- O backup completo do banco de dados e o último backup diferencial – restaura esses backups, se houver algum, antes do backup de log de transação específico. Antes do backup do banco de dados completo ou diferencial mais recente ter sido criado, o banco de dados estava usando o modelo de recuperação completa ou o modelo de recuperação de log em massa.
    
- Todos os backups de logs de transações-restaure todos os backups de logs de transações feitos após o backup completo do banco de dados ou o backup diferencial (se você restaurar um) e antes do backup de log de transação específico. Os backups de log devem ser aplicados na sequência em que foram criados, sem qualquer lacuna na cadeia de logs.
    
Para recuperar o banco de dados de conteúdo no servidor secundário para que os sites processem, remova todas as conexões de banco de dados antes da recuperação. Para restaurar o banco de dados, execute a seguinte instrução SQL.
  
```
restore database WSS_Content with recovery

```

> [!IMPORTANT]
> Quando você usa o T-SQL explicitamente, especifique **WITH NORECOVERY** ou **with Recovery** em cada instrução RESTORE para eliminar ambigüidade — isso é muito importante ao escrever scripts. Após a restauração dos backups completos e diferenciais, os logs de transações podem ser restaurados no SQL Server Management Studio. Além disso, como o envio de logs já foi interrompido, o banco de dados de conteúdo está em um estado de espera, portanto, você deve alterar o estado para acesso total.
  
No SQL Server Management Studio, clique com o botão direito do mouse no banco de dados do **WSS_Content** , aponte para restauração de **tarefas**  >  **Restore**e clique em **log de transações** (se você não tiver restaurado o backup completo, isso não estará disponível). Para obter mais informações, consulte[Restore a Transaction log backup (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=392778).
  
### <a name="crawl-the-content-source"></a>Rastrear a fonte de conteúdo

Você deve iniciar um rastreamento completo para cada fonte de conteúdo para restaurar o serviço de pesquisa. Observe que você perde algumas informações de análise do farm local, como recomendações de pesquisa. Antes de iniciar os rastreamentos completos, use o cmdlet **Restore-SPEnterpriseSearchServiceApplication** do Windows PowerShell e especifique o banco de dados de administração de pesquisa enviado e replicado, **Search_Service__DB_ <GUID> **. Este cmdlet fornece a configuração de pesquisa, o esquema, as propriedades gerenciadas, as regras e as fontes e cria um conjunto padrão de outros componentes.
  
Para iniciar um rastreamento completo, conclua as seguintes etapas:
  
1. Na administração central do SharePoint 2013, vá para aplicativos de serviço de **Gerenciamento de aplicativos**  >  **Service Applications**  >  **gerenciar aplicativos de serviço**e clique no aplicativo de serviço de pesquisa que você deseja rastrear.
    
2. Na página **Administração da pesquisa** , clique em **fontes de conteúdo**, aponte para a fonte de conteúdo que você deseja, clique na seta e, em seguida, clique em **Iniciar rastreamento completo**.
    
### <a name="recover-farm-services"></a>Recuperar serviços de farm

A tabela a seguir mostra como recuperar serviços que têm bancos de dados enviados por log, os serviços que têm bancos de dados, mas não são recomendados a restauração com o envio de logs e os serviços que não possuem bancos de dados.
  
> [!IMPORTANT]
> A restauração de um banco de dados do SharePoint local no ambiente do Azure não recuperará os serviços do SharePoint que você ainda não instalou no Azure manualmente. 
  
**Tabela: referência do banco de dados do aplicativo de serviço**

|**Restaurar esses serviços dos bancos de dados enviados por log**|**Esses serviços têm bancos de dados, mas recomendamos que você inicie esses serviços sem restaurar os bancos de dados**|**Esses serviços não armazenam dados em bancos de dados; iniciar esses serviços após o failover**|
|:-----|:-----|:-----|
| Serviço de Tradução Automática <br/>  Serviço de Metadados Gerenciados <br/>  Serviço de Repositório Seguro <br/>  Perfil de usuário. (Apenas o perfil e os bancos de dados de marcação social têm suporte. Não há suporte para o banco de dados de sincronização.) <br/>  Serviço de Configurações de Assinatura do Microsoft SharePoint Foundation <br/> | Coleta de Dados de Uso e Integridade <br/>  Serviço de Controle de Sessão <br/>  Automação do Word <br/> | Serviços do Excel <br/>  Serviços do PerformancePoint <br/>  Conversão do PowerPoint <br/>  Serviço de Gráfico do Visio <br/>  Gerenciamento de Trabalho <br/> |
   
O exemplo a seguir mostra como restaurar o serviço de metadados gerenciados a partir de um banco de dados.
  
Isso usa o banco de dados Managed_Metadata_DB existente. Este banco de dados é enviado por log, mas não há nenhum aplicativo de serviço ativo no farm secundário, portanto, ele precisa ser conectado depois que o aplicativo de serviço está no local.
  
Primeiro, use  `New-SPMetadataServiceApplication` e especifique a  `DatabaseName` opção com o nome do banco de dados restaurado.
  
Em seguida, configure o novo aplicativo de serviço de metadados gerenciados no servidor secundário, da seguinte maneira:
  
- Name: serviço de metadados gerenciados
    
- Servidor de banco de dados: o nome do banco de dados do log de transações de envio
    
- Nome do banco de dados: Managed_Metadata_DB
    
- Pool de aplicativos: aplicativos de serviço do SharePoint 
    
### <a name="manage-dns-records"></a>Gerenciar registros DNS

Você deve criar manualmente registros DNS para apontar para seu farm do SharePoint.
  
Na maioria dos casos em que você tem vários servidores Web front-end, faz sentido aproveitar o recurso de balanceamento de carga de rede no Windows Server 2012 ou um balanceador de carga de hardware para distribuir solicitações entre os servidores Web-front-end em seu farm. O balanceamento de carga de rede também pode ajudar a reduzir o risco por meio da distribuição de solicitações para outros servidores se um dos servidores Web-front-end falhar. 
  
Normalmente, quando você configura o balanceamento de carga de rede, seu cluster recebe um único endereço IP. Em seguida, crie um registro de host DNS no provedor de DNS para sua rede que aponte para o cluster. (Para este projeto, colocamos um servidor DNS no Azure para resiliência em caso de uma falha no datacenter local.) Por exemplo, você pode criar um registro DNS, no Gerenciador DNS no Active Directory, por exemplo, chamado  `https://sharepoint.contoso.com` , que aponta para o endereço IP do seu cluster com balanceamento de carga.
  
Para acesso externo ao seu farm do SharePoint, você pode criar um registro de host em um servidor DNS externo com a mesma URL que os clientes usam na sua intranet (por exemplo, `https://sharepoint.contoso.com` ) que aponta para um endereço IP externo em seu firewall. (Uma prática recomendada, usando esse exemplo, é configurar o DNS dividido para que o servidor DNS interno seja autoritativo `contoso.com` e roteia as solicitações diretamente para o cluster de farm do SharePoint, em vez de rotear as solicitações de DNS para seu servidor de DNS externo). Em seguida, você pode mapear o endereço IP externo para o endereço IP interno do seu cluster local para que os clientes encontrem os recursos que estão procurando.
  
A partir daqui, você pode ter alguns cenários diferentes de recuperação de desastres:
  
 **Cenário de exemplo: o farm do SharePoint local não está disponível devido à falha de hardware no farm do SharePoint local.** Nesse caso, depois de concluir as etapas de failover para o farm do Azure SharePoint, você pode configurar o balanceamento de carga de rede nos servidores Web-end do farm do SharePoint de recuperação, da mesma maneira que você fez com o farm local. Você pode redirecionar o registro de host no seu provedor de DNS interno para apontar para o endereço IP do cluster do farm de recuperação. Observe que pode levar algum tempo para que os registros DNS armazenados em cache nos clientes sejam atualizados e apontar para o farm de recuperação.
  
 **Cenário de exemplo: o datacenter local é perdido completamente.** Esse cenário pode ocorrer devido a um desastre natural, como fogo ou inundação. Nesse caso, para uma empresa, provavelmente você terá um datacenter secundário hospedado em outra região, bem como sua sub-rede do Azure que tenha seus próprios serviços de diretório e DNS. Como no cenário de desastre anterior, você pode redirecionar seus registros DNS internos e externos para apontar para o farm do Azure SharePoint. Novamente, observe que a propagação do registro DNS pode levar algum tempo.
  
Se você estiver usando conjuntos de sites nomeados por host, conforme recomendado em [implantação e arquitetura de conjunto de sites nomeados por host (SharePoint 2013)](https://docs.microsoft.com/SharePoint/administration/host-named-site-collection-architecture-and-deployment), você pode ter vários conjuntos de sites hospedados pelo mesmo aplicativo Web no seu farm do SharePoint, com nomes DNS exclusivos (por exemplo, `https://sales.contoso.com` e `https://marketing.contoso.com` ). Nesse caso, você pode criar registros DNS para cada conjunto de sites que apontem para o endereço IP do cluster. Depois que uma solicitação alcança seus servidores Web-front-end do SharePoint, elas tratam de roteamento de cada solicitação para o conjunto de sites apropriado.
  
## <a name="microsoft-proof-of-concept-environment"></a>Ambiente de verificação de conceito da Microsoft

Projetamos e testamos um ambiente de verificação de conceito para esta solução. O objetivo de design para o nosso ambiente de teste era implantar e recuperar um farm do SharePoint que pode ser encontrado em um ambiente de cliente. Fizemos várias suposições, mas sabíamos que o farm precisava fornecer toda a funcionalidade pronta para uso sem qualquer personalização... A topologia foi projetada para alta disponibilidade usando o guia de práticas recomendadas do grupo de campos e produtos.
  
A tabela a seguir descreve as máquinas virtuais do Hyper-V que criamos e configuramos para o ambiente de teste local.
  
**Tabela: máquinas virtuais para teste no local**

|**Nome do servidor**|**Função**|**Configuração**|
|:-----|:-----|:-----|
|DC1  <br/> |Controlador de domínio com Active Directory.  <br/> |Dois processadores  <br/> De 512 MB a 4 GB de RAM  <br/> 1 disco rígido de 127 GB  <br/> |
|RRAS  <br/> |Servidor configurado com a função serviço de roteamento e acesso remoto (RRAS).  <br/> |Dois processadores  <br/> 2-8 GB de RAM  <br/> 1 disco rígido de 127 GB  <br/> |
|FS1  <br/> |Servidor de arquivos com compartilhamentos para backups e ponto final para DFSR.  <br/> |Quatro processadores  <br/> 2-12 GB de RAM  <br/> 1 disco rígido de 127 GB  <br/> 1 disco rígido de 1 TB (SAN)  <br/> 1 disco rígido de 750 GB  <br/> |
|SP-WFE1, SP-WFE2  <br/> |Servidores Web front-end.  <br/> |Quatro processadores  <br/> 16 GB de RAM  <br/> |
|SP-APP1, SP-APP2, SP-APP3  <br/> |Servidores de aplicativos.  <br/> |Quatro processadores  <br/> 2-16 GB de RAM  <br/> |
|SP-SQL-HA1, SP-SQL-HA2  <br/> |Servidores de banco de dados, configurados com os grupos de disponibilidade AlwaysOn do SQL Server 2012 para fornecer alta disponibilidade. Essa configuração usa o SP-SQL-HA1 e o SP-SQL-HA2 como as réplicas primárias e secundárias.  <br/> |Quatro processadores  <br/> 2-16 GB de RAM  <br/> |
   
A tabela a seguir descreve as configurações de unidade para as máquinas virtuais do Hyper-V criadas e configuradas para os servidores Web front-end e de aplicativos para o ambiente de teste local.
  
**Tabela: requisitos de unidade de máquina virtual para os servidores Web front-end e de aplicativos para o teste local**

|**Letra da unidade**|**Tamanho**|**Nome do diretório**|**Path**|
|:-----|:-----|:-----|:-----|
|C  <br/> |80  <br/> |Unidade do sistema  <br/> |<DriveLetter>: \\ Arquivos de programas \\ Microsoft SQL Server\\  <br/> |
|E  <br/> |80  <br/> |Unidade de log (40 GB)  <br/> |<DriveLetter>: \\ Arquivos de programa \\ do Microsoft SQL Server \\ MSSQL10_50. MSSQLSERVER \\ MSSQL \\ Data  <br/> |
|S  <br/> |80  <br/> |Página (36 GB)  <br/> |<DriveLetter>: \\ Arquivos de programa \\ dados do Microsoft SQL Server \\ MSSQL \\  <br/> |
   
A tabela a seguir descreve as configurações de unidade para as máquinas virtuais do Hyper-V criadas e configuradas para servir como os servidores de banco de dados local. Na página **configuração do mecanismo de banco** de dados, acesse a guia **diretórios de dados** para definir e confirmar as configurações mostradas na tabela a seguir.
  
**Tabela: requisitos de unidade de máquina virtual para o servidor de banco de dados para o teste local**

|**Letra da unidade**|**Tamanho**|**Nome do diretório**|**Path**|
|:-----|:-----|:-----|:-----|
|C  <br/> |80  <br/> |Diretório raiz de dados  <br/> |<DriveLetter>: \\ Arquivos de programas \\ Microsoft SQL Server\\  <br/> |
|E  <br/> |500  <br/> |Diretório do banco de dados do usuário  <br/> |<DriveLetter>: \\ Arquivos de programa \\ do Microsoft SQL Server \\ MSSQL10_50. MSSQLSERVER \\ MSSQL \\ Data  <br/> |
|S  <br/> |500  <br/> |Diretório de log do banco de dados do usuário  <br/> |<DriveLetter>: \\ Arquivos de programa \\ do Microsoft SQL Server \\ MSSQL10_50. MSSQLSERVER \\ MSSQL \\ Data  <br/> |
|G  <br/> |500  <br/> |Diretório Temp DB  <br/> |<DriveLetter>: \\ Arquivos de programa \\ do Microsoft SQL Server \\ MSSQL10_50. MSSQLSERVER \\ MSSQL \\ Data  <br/> |
|H  <br/> |500  <br/> |Diretório de log do banco de BD Temp  <br/> |<DriveLetter>: \\ Arquivos de programa \\ do Microsoft SQL Server \\ MSSQL10_50. MSSQLSERVER \\ MSSQL \\ Data  <br/> |
   
### <a name="setting-up-the-test-environment"></a>Configurando o ambiente de teste

Durante as diferentes fases de implantação, a equipe de teste normalmente trabalhou na arquitetura local primeiro e, em seguida, no ambiente Azure correspondente. Isso reflete os casos gerais do mundo real em que os farms de produção internos já estão em execução. O que é ainda mais importante é que você deve saber a carga de trabalho de produção, a capacidade e o desempenho típicos atuais. Além de criar um modelo de recuperação de desastres que possa atender às necessidades dos negócios, você deve dimensionar os servidores do farm de recuperação para fornecer um nível mínimo de serviço. Em um ambiente de espera frio ou Cold, um farm de recuperação normalmente é menor do que um farm de produção. Depois que o farm de recuperação é estável e em produção, o farm pode ser dimensionado para atender aos requisitos de carga de trabalho.
  
Implantamos nosso ambiente de teste nas três fases a seguir:
  
- Configurar a infraestrutura híbrida
    
- Provisionar os servidores
    
- Implantar farms do SharePoint
    
#### <a name="set-up-the-hybrid-infrastructure"></a>Configurar a infraestrutura híbrida

Esta fase envolveva a configuração de um ambiente de domínio para o farm local e para o farm de recuperação no Azure. Além das tarefas normais associadas à configuração do Active Directory, a equipe de teste implementou uma solução de roteamento e uma conexão VPN entre os dois ambientes.
  
#### <a name="provision-the-servers"></a>Provisionar os servidores

Além dos servidores do farm, era necessário provisionar servidores para os controladores de domínio e configurar um servidor para lidar com o RRAS, bem como a VPN site a site. Dois servidores de arquivos foram provisionados para o serviço DFSR e vários computadores cliente foram provisionados para os testadores.
  
#### <a name="deploy-the-sharepoint-farms"></a>Implantar farms do SharePoint

Os farms do SharePoint foram implantados em dois estágios para simplificar a estabilização do ambiente e solucionar problemas, se necessário. Durante o primeiro estágio, cada farm foi implantado no número mínimo de servidores para cada camada da topologia para suportar a funcionalidade necessária.
  
Criamos os servidores de banco de dados com o SQL Server instalado antes de criar os servidores do SharePoint 2013. Como essa era uma nova implantação, criamos os grupos de disponibilidade antes de implantar o SharePoint. Criamos três grupos com base na orientação de práticas recomendadas de MCS. 
  
> [!NOTE]
> Criar bancos de dados de espaços reservados para que você possa criar grupos de disponibilidade antes da instalação do SharePoint. Para obter mais informações, consulte [Configure SQL Server 2012 AlwaysOn Availability Groups for SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=517626)
  
Criamos o farm e ingressamos em servidores adicionais na seguinte ordem:
  
- Provisionar SP-SQL-HA1 e SP-SQL-HA2.
    
- Configure o AlwaysOn e crie os três grupos de disponibilidade para o farm. 
    
- Provisionar SP-APP1 para hospedar a administração central.
    
- Provisionar SP-WFE1 e SP-WFE2 para hospedar o cache distribuído. 
    
Usamos o parâmetro  _skipRegisterAsDistributedCachehost_ quando executamos **psconfig.exe** na linha de comando. Para obter mais informações, consulte [Plan for feeds and the Distributed cache Service in SharePoint Server 2013](https://docs.microsoft.com/sharepoint/administration/plan-for-feeds-and-the-distributed-cache-service). 
  
Repetimos as seguintes etapas no ambiente de recuperação:
  
- Provisione AZ-SQL-HA1 e AZ-SQL-HA2.
    
- Configure o AlwaysOn e crie os três grupos de disponibilidade para o farm.
    
- Provisione AZ-APP1 para hospedar a administração central.
    
- Provisione AZ-WFE1 e AZ-WFE2 para hospedar o cache distribuído.
    
Depois de configurar o cache distribuído e adicionar os usuários de teste e o conteúdo de teste, começamos o estágio dois da implantação. Isso exigia o dimensionamento das camadas e a configuração dos servidores do farm para dar suporte à topologia de alta disponibilidade descrita na arquitetura do farm.
  
A tabela a seguir descreve as máquinas virtuais, as sub-redes e os conjuntos de disponibilidade configurados para nosso farm de recuperação.
  
**Tabela: infraestrutura de farm de recuperação**

|**Nome do servidor**|**Função**|**Configuração**|**Sub-rede**|**Conjunto de disponibilidade**|
|:-----|:-----|:-----|:-----|:-----|
|spDRAD  <br/> |Controlador de domínio com Active Directory  <br/> |Dois processadores  <br/> De 512 MB a 4 GB de RAM  <br/> 1 disco rígido de 127 GB  <br/> |SP-ADservers  <br/> ||
|AZ-SP-FS  <br/> |Servidor de arquivos com compartilhamentos para backups e um ponto de extremidade para DFSR  <br/> | Configuração de a5: <br/>  Dois processadores <br/>  14 GB de RAM <br/>  1 disco rígido de 127 GB <br/>  1 disco rígido de 135 GB <br/>  1 disco rígido de 127 GB <br/>  1 disco rígido de 150 GB <br/> |SP-databaseservers  <br/> |DATA_SET  <br/> |
|AZ-WFE1, AZ-WFE2  <br/> |Servidores Web front-end  <br/> | Configuração de a5: <br/>  Dois processadores <br/>  14 GB de RAM <br/>  1 disco rígido de 127 GB <br/> |SP-servidores de  <br/> |WFE_SET  <br/> |
|AZ-APP1, AZ-APP2, AZ-APP3  <br/> |Servidores de aplicativos  <br/> | Configuração de a5: <br/>  Dois processadores <br/>  14 GB de RAM <br/>  1 disco rígido de 127 GB <br/> |SP-ApplicationServers  <br/> |APP_SET  <br/> |
|AZ-SQL-HA1, AZ-SQL-HA2  <br/> |Servidores de banco de dados e réplicas primárias e secundárias para grupos de disponibilidade AlwaysOn  <br/> | Configuração de a5: <br/>  Dois processadores <br/>  14 GB de RAM <br/> |SP-databaseservers  <br/> |DATA_SET  <br/> |
   
### <a name="operations"></a>Operations

Depois que a equipe de teste estabilize os ambientes de farm e os testes funcionais concluídos, eles iniciaram as seguintes tarefas de operações necessárias para configurar o ambiente de recuperação local:
  
- Configurar backups completos e diferenciais.
    
- Configure o DFSR nos servidores de arquivos que transferem logs de transações entre o ambiente local e o ambiente do Azure.
    
- Configure o envio de logs no servidor de banco de dados primário.
    
- Estabilize, valide e solucione problemas de envio de logs, conforme necessário. Isso incluiu a identificação e a documentação de qualquer comportamento que possa causar problemas, como latência de rede, que causaria falhas no envio de logs ou na sincronização de arquivos DFSR.
    
### <a name="databases"></a>Bancos de dados

Nossos testes de failover envolveram os seguintes bancos de dados: 
  
- WSS_Content
    
- ManagedMetadata
    
- BD de perfil
    
- Sincronizar BD
    
- BD social
    
- Hub de tipo de conteúdo (um banco de dados para um hub de agregação de tipo de conteúdo dedicado)
    
## <a name="troubleshooting-tips"></a>Dicas de solução de problemas

A seção explica os problemas encontrados durante o teste e suas soluções. 
  
### <a name="using-the-term-store-management-tool-caused-the-error-the-managed-metadata-store-or-connection-is-currently-not-available"></a>Usando a ferramenta de gerenciamento de repositório de termos causou o erro, "o repositório de metadados gerenciados ou a conexão não está disponível no momento."

Certifique-se de que a conta de pool de aplicativos usada pelo aplicativo Web tenha a permissão de acesso de leitura para o repositório de termos.
  
### <a name="custom-term-sets-are-not-available-in-the-site-collection"></a>Os conjuntos de termos personalizados não estão disponíveis no conjunto de sites

Verifique se há uma associação de aplicativo de serviço ausente entre seu conjunto de sites de conteúdo e seu hub de tipo de conteúdo. Além disso, na tela de propriedades de **metadados gerenciados- <site collection name> conexão** , certifique-se de que essa opção está habilitada: **este aplicativo de serviço é o local de armazenamento padrão para conjuntos de termos específicos de coluna.**
  
### <a name="the-get-adforest-windows-powershell-command-generates-the-error-the-term-get-adforest-is-not-recognized-as-the-name-of-a-cmdlet-function-script-file-or-operable-program"></a>O comando Get-ADForest do Windows PowerShell gera o erro "o termo ' Get-ADForest ' não é reconhecido como o nome de um cmdlet, uma função, um arquivo de script ou um programa operável."

Ao configurar perfis de usuário, você precisa do nome da floresta do Active Directory. No Assistente para adicionar funções e recursos, verifique se você habilitou o módulo Active Directory para Windows PowerShell (sob as ferramentas de **Administração de servidor remoto>ferramentas de administração de função>seção ferramentas AD DS e AD LDS** ). Além disso, execute os seguintes comandos antes de usar o **Get-ADForest** para ajudar a garantir que suas dependências de software sejam carregadas.
  
```
Import-module servermanager
Import-module activedirectory

```

### <a name="availability-group-creation-fails-at-starting-the-alwayson_health-xevent-session-on-server-name"></a>A criação do grupo de disponibilidade falha ao iniciar a sessão ' AlwaysOn_health ' XEvent em ' <server name> '

Certifique-se de que ambos os nós do seu cluster de failover estejam no status "up" e não "pausado" ou "interrompido". 
  
### <a name="sql-server-log-shipping-job-fails-with-access-denied-error-trying-to-connect-to-the-file-share"></a>Falha no trabalho de envio de logs do SQL Server com o acesso negado ao tentar se conectar ao compartilhamento de arquivos

Verifique se o seu SQL Server Agent está sendo executado sob as credenciais de rede, em vez das credenciais padrão.
  
### <a name="sql-server-log-shipping-job-indicates-success-but-no-files-are-copied"></a>O trabalho de envio de logs do SQL Server indica êxito, mas não há arquivos copiados

Isso acontece porque a preferência de backup padrão para um grupo de disponibilidade é **prefira secundária**. Certifique-se de executar o trabalho de envio de logs do servidor secundário para o grupo de disponibilidade, em vez do principal; caso contrário, o trabalho falhará silenciosamente. 
  
### <a name="managed-metadata-service-or-other-sharepoint-service-fails-to-start-automatically-after-installation"></a>O serviço de metadados gerenciados (ou outro serviço do SharePoint) falha ao iniciar automaticamente após a instalação

Os serviços podem levar alguns minutos para iniciar, dependendo do desempenho e da carga atual do seu SharePoint Server. Clique manualmente em **Iniciar** para o serviço e forneça o tempo adequado para a inicialização enquanto atualiza ocasionalmente os serviços na tela do servidor para monitorar seu status. Caso o serviço permaneça parado, habilite o log de diagnóstico do SharePoint, tente iniciar o serviço novamente e, em seguida, verifique se há erros no log. Para obter mais informações, consulte [Configurar o log de diagnóstico no SharePoint 2013](https://docs.microsoft.com/sharepoint/administration/configure-diagnostic-logging)
  
### <a name="after-changing-dns-to-the-azure-failover-environment-client-browsers-continue-to-use-the-old-ip-address-for-the-sharepoint-site"></a>Após alterar o DNS para o ambiente de failover do Azure, os navegadores clientes continuam a usar o endereço IP antigo para o site do SharePoint

Sua alteração de DNS pode não estar visível para todos os clientes imediatamente. Em um cliente de teste, execute o seguinte comando a partir de um prompt de comando elevado e tente acessar o site novamente.
  
```
Ipconfig /flushdns
```

## <a name="additional-resources"></a>Recursos adicionais

[Suporte para as opções de alta disponibilidade e recuperação de desastres para bancos de dados do SharePoint](https://docs.microsoft.com/sharepoint/administration/supported-high-availability-and-disaster-recovery-options-for-sharepoint-databas)
  
[Configurar grupos de disponibilidade AlwaysOn do SQL Server 2012 para o SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=393122)
  
## <a name="see-also"></a>Confira também

[Centro de soluções e arquitetura do Microsoft 365](../solutions/solution-architecture-center.md)



