---
title: Roteiro de fim do suporte do Project Server 2007
ms.author: efrene
author: efrene
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
ms.assetid: d379018f-72b7-4284-b40a-6c23c8ae38fe
description: Em 10 de outubro de 2017, o suporte terminou para Project Server 2007, Project Portfolio Server e Project 2007. Use este artigo para planejar sua atualização agora.
ms.openlocfilehash: 12447eb2a021b3f92e3557b2c3ea87e859841346
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927343"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Roteiro de fim do suporte do Project Server 2007

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O suporte terminou para Office 2007 servidores e aplicativos em 2017 e você precisa considerar planos para migração. Se você estiver usando o Project Server 2007 e produtos relacionados, observe as seguintes datas de fim de suporte:
  
|**Produto**|**Data de término do suporte**|
|:-----|:-----|
|Project Server 2007  <br/> |10 de outubro de 2017  <br/> |
|Project Portfolio Server 2007  <br/> |10 de outubro de 2017  <br/> |
|Project 2007 Standard  <br/> |10 de outubro de 2017  <br/> |
|Project 2007 Professional  <br/> |10 de outubro de 2017  <br/> |
   
Para obter mais informações sobre Office servidores 2007 que chegam à aposentadoria, consulte [Upgrade from Office 2007 servers and client products](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-does-end-of-support-mean"></a>O que *significa o fim do suporte?*

A maioria dos produtos Microsoft tem um ciclo de vida de suporte durante o qual eles têm novos recursos, correções de bugs, correções de segurança e assim por diante. Esse ciclo de vida geralmente dura 10 anos a partir da versão inicial do produto. O final desse ciclo de vida é conhecido como o fim do suporte do produto. Como Project Server 2007 atingiu seu fim de suporte em 10 de outubro de 2017, a Microsoft não fornece mais:
  
- Suporte técnico para problemas que podem ocorrer.
    
- Correções de bugs para problemas que podem afetar a estabilidade e a usabilidade do servidor.
    
- Correções de segurança para vulnerabilidades que podem tornar o servidor vulnerável a violações de segurança.
    
- Atualizações de fuso horário.
    
Sua instalação do Project Server 2007 continuará sendo executado após essa data. Porém, devido às alterações listadas anteriormente, recomendamos que você migre do Project Server 2007 assim que prático.
  
## <a name="what-are-my-options"></a>Quais são minhas opções?

Se você estiver usando o Project Server 2007, precisará explorar suas opções de migração, que são:
  
- Migrar para Project Online
    
- Migrar para uma versão local mais recente do Project Server (preferencialmente Project Server 2016)
    
|**Por que eu gostaria de migrar para Project Online**|**Por que eu gostaria de migrar para Project Server 2016**|
|:-----|:-----|
| Tenho usuários móveis.  <br/> <br/>Os custos para migrar são uma preocupação significativa (hardware, software, horas e esforço para implementar). <br/><br/>  Após a migração, os custos para manter meu ambiente são uma grande preocupação (por exemplo, atualizações automáticas, tempo de atividade garantido e assim por diante).  <br/> | As regras de negócios me restringem a operar meus negócios na nuvem.<br/><br/>  Preciso de controle de atualizações para meu ambiente.  |
   
> [!NOTE]
> Para obter mais informações sobre as opções para mover de seus servidores Office 2007, consulte Recursos para ajudá-lo a atualizar Office [2007 servidores](upgrade-from-office-2007-servers-and-products.md)e clientes. Observe que Project Server não dá suporte a uma configuração híbrida, porque o Project Server e Project Online não podem compartilhar o mesmo pool de recursos. 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>Considerações importantes ao migrar do Project Server 2007

Considere o seguinte quando você planeja migrar do Project Server 2007:
  
- **Obter ajuda de um Microsoft Partner** - A atualização do Project Server 2007 pode ser desafiadora e exige muita preparação e planejamento. Pode ser especialmente desafiador se você não foi a pessoa que definiu o Project Server 2007 originalmente. Felizmente, há parceiros microsoft que podem ajudar, se você planeja migrar para Project Server 2016 ou para Project Online. Procure um Microsoft Partner para ajudar na migração no [Microsoft Partner Center.](https://go.microsoft.com/fwlink/p/?linkid=841249) Pesquise o *termo Gold Project e Gerenciamento* de Portfólio para exibir uma lista de todos os Parceiros da Microsoft que têm experiência em Project. 
    
- Planejar suas **personalizações** - Muitas das personalizações feitas em seu ambiente do Project Server 2007 podem não funcionar quando você migrar para Project Server 2016 ou Project Online. Há diferenças significativas na arquitetura Project Server entre versões. Os sistemas operacionais necessários, servidores de banco de dados e navegadores da Web cliente com suporte também são diferentes. Planeje como testar ou reconstruir suas personalizações para o novo ambiente. O planejamento também oferece uma boa oportunidade para considerar se cada personalização ainda é necessária. Para saber mais, confira [Create a plan for current customizations during upgrade to SharePoint 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013). 
    
- **Tempo e paciência** - O planejamento, a execução e o teste de atualização levarão tempo e esforço, especialmente se você atualizar para Project Server 2016. Por exemplo, se você migrar do Project Server 2007 para o Project Server 2016, primeiro precisará migrar para o Project Server 2010, verificar seus dados e, em seguida, fazer o mesmo quando migrar para cada versão sucessiva. Talvez você queira verificar com um Microsoft Partner para obter estimativas de quanto tempo levará e quanto isso custará.
    
## <a name="migrate-to-project-online"></a>Migrar para Project Online

Se você optar por migrar do Project Server 2007 para Project Online, faça o seguinte para migrar manualmente os dados do seu plano de projeto:
  
1. Salve seus planos de projeto do Project Server 2003 para o formato .mpp.
    
2. No Project Professional 2013, Project Professional 2016 ou o cliente de área de trabalho Project Online, abra cada arquivo .mpp e salve e publique-o no Project Online.
    
Você pode criar manualmente sua configuração Microsoft Project Web App (PWA) no Project Online. Por exemplo, recrie quaisquer campos personalizados ou calendários corporativos necessários. Os Parceiros da Microsoft também podem ajudar nesse processo.
  
Principais recursos:
  
|**Recurso**|**Descrição**|
|:-----|:-----|
|[Introdução ao Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Como configurar e usar Project Online <br/> |
|[Project Online Descrições do serviço](/office365/servicedescriptions/project-online-service-description/project-online-service-description) <br/> |Informações sobre os diferentes Project Online que estão disponíveis para você <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrar para uma versão local mais recente do Project Server

Acreditamos fortemente que você tenha o melhor valor e experiência do usuário migrando para Project Online. Mas também entendemos que algumas organizações precisam manter os dados do projeto em um ambiente local. Se você optar por manter seus dados de projeto no local, poderá migrar seu ambiente do Project Server 2007 para o Project Server 2010, Project Server 2013 ou Project Server 2016.
  
Se você não puder migrar para Project Online, recomendamos que você migre para Project Server 2016. Project Server 2016 inclui todos os recursos de versões anteriores do Project Server. Ele corresponde mais de perto à experiência disponível com Project Online, embora alguns recursos estão disponíveis apenas em Project Online.
  
Após cada migração, você deve verificar se seus dados migraram com êxito.
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Como faço para migrar para Project Server 2016?

As diferenças de arquitetura entre Project Server 2007 e Project Server 2016 impedem um caminho de migração direta. Portanto, você precisa migrar seus dados do Project Server 2007 para cada versão sucessiva do Project Server até chegar Project Server 2016.
  
Siga estas etapas para Project Server 2016:
  
1. Migre do Project Server 2007 para Project Server 2010.
    
2. Migre do Project Serve 2010 para Project Server 2013.
    
3. Migre do Project Server 2013 para Project Server 2016.
    
Após cada migração, certifique-se de que seus dados migraram com êxito.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Etapa 1: Migrar do Project Server 2007 para o Project Server 2010

Para uma descrição abrangente do que você precisa fazer para atualizar do Project Server 2007 para o Project Server 2010, consulte [Upgrade to Project Server 2010](/previous-versions/office/project-server-2010/gg502590(v=office.14)).
  
Principais recursos:
  
|**Recurso**|**Descrição**|
|:-----|:-----|
|[Project Visão geral da atualização do Server 2010](/previous-versions/office/project-server-2010/ee662496(v=office.14)) <br/> |Uma exibição de alto nível do que você precisa fazer para atualizar do Project Server 2007 para o Project Server 2010 <br/> |
|[Planejar a atualização para o Project Server 2010](/previous-versions/office/project-server-2010/ff603505(v=office.14)) <br/> |Considerações de planejamento ao atualizar do Project Server 2007 para o Project Server 2010, incluindo requisitos do sistema  <br/> |
   
#### <a name="how-do-i-upgrade"></a>Como faço a atualização?

Para obter detalhes, [consulte Upgrade to Project Server 2010](/previous-versions/office/project-server-2010/gg502590(v=office.14)). Mas é importante entender que existem dois métodos distintos que você pode usar para atualizar:
  
- **Atualização de anexação de banco de dados:** Esse método apenas atualiza o conteúdo do seu ambiente, não as configurações. É necessário se você estiver atualizando do Office Project Server 2007 implantado em hardware que só oferece suporte a um sistema operacional de servidor de 32 bits. Há dois tipos de métodos de atualização de anexação de banco de dados:
    
  - Atualização completa **anexada** ao banco de dados - Migra os dados do projeto armazenados nos bancos de dados do Office Project Server 2007, além dos dados do site do Microsoft Project Web App armazenados em um banco de dados de conteúdo SharePoint.
    
  - **Atualização principal de *anexação de banco de*** dados - Migra somente os dados do projeto armazenados nos bancos de dados Project Server.
    
- **Atualização in-locar**: os dados de configuração do farm e todo o conteúdo no farm são atualizados no hardware existente em uma ordem fixa. Quando você inicia o processo de atualização, a instalação faz com que todo o farm seja offline. Os sites e Microsoft Project web app ficam indisponíveis até que a atualização seja concluída e, em seguida, a instalação reinicia o servidor. Depois de iniciar uma atualização in-locar, não é possível pausar a atualização ou reverter para a versão anterior. É melhor fazer uma imagem espelhada do seu ambiente de produção e fazer a atualização in-locar para esse ambiente, não em seu ambiente de produção. 
    
Recursos adicionais:
  
- [SuperFlow para atualização Microsoft Project Server 2010](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Migração do Project Server 2007 para o Project Server 2010](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Considerações sobre atualização das Web parts do Project Web App](/previous-versions/office/project-server-2010/gg314581(v=office.14))
    
- [Project Kit de Desenvolvimento de Software (SDK)](/previous-versions/office/developer/office-2010/ms481966(v=office.14))
    
### <a name="step-2-migrate-to-project-server-2013"></a>Etapa 2: Migrar para o Project Server 2013

Depois de verificar se os dados migraram com êxito, a próxima etapa é migrar para o Project Server 2013.
  
Para uma descrição abrangente do que você precisa fazer para atualizar do Project Server 2010 para o Project Server 2013, consulte [Upgrade to Project Server 2013](/project/upgrade-to-project-server-2016). 
  
Principais recursos:
  
|**Recurso**|**Descrição**|
|:-----|:-----|
|[Visão geral do processo de atualização do Project Server 2013](/project/upgrade-to-project-server-2016) <br/> |Visão geral do que você precisa fazer para atualizar do Project Server 2010 para o Project Server 2013  <br/> |
|[Planejar a atualização para o Project Server 2013](/project/plan-for-upgrade-to-project-server-2016) <br/> |Considerações de planejamento ao atualizar do Project Server 2010 para o Project Server 2013, incluindo requisitos do sistema <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>O que saber sobre a atualização para esta versão

[Novidades na atualização do Project Server 2013](/project/what-s-new-in-project-server-2013-upgrade) descrevem alterações importantes para a atualização dessa versão. Os mais notáveis são: 
  
- Não há atualização in-locar para o Project Server 2013. O método de anexação de banco de dados é o único método com suporte para atualização do Project Server 2010 para o Project Server 2013.
    
- O processo de atualização não apenas converterá seus dados do Project Server 2010 no formato Project Server 2013, mas também consolidará os quatro bancos de dados do Project Server 2010 em um único banco de dados Project Web App.
    
- Nas versões de 2013, tanto SharePoint Server quanto Project Server foram alterados para autenticação baseada em declarações. Se você estiver usando a autenticação clássica, você precisará considerar esse fator para sua atualização. Para saber mais, confira [Migrar da autenticação de modo clássico para a autenticação baseada em declarações SharePoint 2013](/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server).
    
Recursos adicionais:
  
- [Visão geral do processo de atualização para o Project Server 2013](/project/overview-of-the-project-server-2016-upgrade-process)
    
- [Atualizar seus bancos de dados e conjuntos de sites do Project Web App (Project Server 2013)](/project/upgrading-to-project-server-2016)
    
- [Microsoft Project Diagrama do processo de atualização do servidor](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [A Grande Consolidação de Banco de Dados, Project Server 2010 a 2013 migração em 8 etapas fáceis](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Etapa 3: Migrar para Project Server 2016

Depois de verificar se os dados migraram com êxito, a próxima etapa é migrar para Project Server 2016.
  
Para uma descrição abrangente do que você precisa fazer para atualizar do Project Server 2013 para Project Server 2016, consulte [Upgrade to Project Server 2016](//project/upgrading-to-project-server-2016).
  
Principais recursos:
  
|**Recurso**|**Descrição**|
|:-----|:-----|
|[Visão geral do processo Project Server 2016 atualização](/previous-versions/office/project-server-2010/ee662104(v=office.14)) <br/> |Visão geral do que você precisa fazer para atualizar do Project Server 2013 para Project Server 2016 <br/> |
|[Planejar a atualização para Project Server 2016](/project/plan-for-upgrade-to-project-server-2016) <br/> |Considerações de planejamento que você atualiza do Project Server 2013 para Project Server 2016 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>O que saber sobre a atualização para esta versão

[Coisas que você precisa saber sobre Project Server 2016 atualização](/project/plan-for-upgrade-to-project-server-2016) informa algumas alterações importantes para a atualização desta versão, que incluem:
  
- Ao criar seu ambiente Project Server 2016 para o qual você migrará seus dados do Project Server 2013, os arquivos de instalação do Project Server 2016 são incluídos no SharePoint Server 2016. Para obter mais informações, consulte [Deploy Project Server 2016](/project/deploy-project-server-2016).
    
- Os planos de recursos são preterido no Project Server 2016. Seus Project de recursos do Server 2013 serão migrados para Compromissos de Recursos no Project Server 2016 e no Project Online. Consulte [Visão geral: Compromissos de recursos](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) para obter mais informações. 
    
## <a name="migrate-from-portfolio-server-2007"></a>Migrar do Portfolio Server 2007

Project O Portfolio Server 2007 foi usado com o Project Server 2007 para estratégia de portfólio, priorização e otimização. Nenhuma versão adicional do Project Portfolio Server foi criada após essa versão. No entanto, os recursos de gerenciamento de portfólio estão disponíveis no Project Server 2016 e na Premium do Project Online. Mas os dados do Project Portfolio Server 2007 também não podem ser migrados. Dados como drivers de negócios terão que ser recriados.
  
Outros recursos:
  
- [Project Online Descrições de Serviço:](/office365/servicedescriptions/project-online-service-description/project-online-service-description) Consulte os recursos de gerenciamento de portfólio incluídos no Project Server 2016 e Project Online Premium.
    
- [Microsoft Office Project guia de migração do Portfolio Server 2007.](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Tópicos relacionados

[SharePoint Roteiro de fim de suporte do Servidor 2007](sharepoint-2007-end-of-support.md)
  
[Recursos para ajudá-lo a atualizar Office 2007 servidores e clientes](upgrade-from-office-2007-servers-and-products.md)
