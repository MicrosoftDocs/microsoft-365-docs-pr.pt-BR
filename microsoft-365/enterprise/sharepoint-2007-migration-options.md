---
title: Opções de migração do SharePoint 2007 a serem consideradas
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPS150
- OSU140
- SPO160
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: 66325a43-5816-4f8e-81ba-c11b71345b7c
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: Este artigo contém informações para usuários que usam o SharePoint Server 2007 para ajudá-los a planejar a atualização.
ms.openlocfilehash: 3e37a01f1a2d387cda6723a8df1f73734fa3ba9d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694949"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>Opções de migração do SharePoint 2007 a serem consideradas

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O Microsoft SharePoint 2007 e o SharePoint Server 2007 chegaram ao fim do suporte. É hora de atualizar! Este artigo fornece informações sobre as opções de migração.
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>Estratégias comuns de atualização para o SharePoint

Há vários métodos para atualizar um ambiente do SharePoint Server. Se você tiver um farm do Microsoft Office SharePoint Server 2007, estes são alguns exemplos dos métodos de atualização:
  
- Anexar banco de dados
    
- Atualização lado a lado
    
- Atualização in-loco
    
- Atualização híbrida (in-loco com bancos de dados desanexados/anexação de banco de dados separado)
    
- Híbridas do SharePoint (conectar online ao SharePoint local)
    
- Mover dados manualmente entre conjuntos de sites ou bibliotecas
    
- Atualização do assistente do FastTrack para o Microsoft 365 ([supervisor de implantação do SharePoint Online](https://aka.ms/spoguidance))
    
- API de migração para o SharePoint Online (SPO) no Microsoft 365
    
O que funciona melhor para você?
  
Seu conhecimento sobre o que o seu farm faz e é usado é uma força tática quando se trata de uma atualização. O modo como as pessoas usam o farm do SharePoint o ajudarão a escolher entre suas opções.
  
> [!TIP]
> O Microsoft Office SharePoint Server 2007 também tem uma atualização gradual não abordada aqui. Para ver uma lista de artigos de atualização específicos da etapa, consulte o [mapa de suporte final do SharePoint Server 2007](sharepoint-2007-end-of-support.md). 
  
Lembre-se de verificar o [ciclo de vida do produto](https://support.microsoft.com/lifecycle/search) e os requisitos do sistema para qualquer versão do SharePoint para a qual você está atualizando. Isso é necessário para que você se lembre de quando a próxima atualização será necessária (por exemplo, se você pausar em um produto herdado como o SharePoint Server 2010 para planejar mais atualizações, certifique-se de que você conhece o fim da data de suporte) e para ter certeza de que tem o hardware que oferece suporte ao seu plano. 
  
Se você estiver planejando fazer a transição de alguns, ou todos, de seus sites do SharePoint para o Microsoft 365 na nuvem, essa é uma hora para indicar um link para as [descrições de serviço do Microsoft 365 e do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library). Você precisará das descrições de serviço para saber mais sobre os recursos do SharePoint Online e como eles podem diferir do SharePoint Server local. Atualizar farms funcionais do Microsoft Office SharePoint Server 2007. Se sua instalação tiver sites desfeitos, corrija-os antes de atualizar.
  
## <a name="a-note-about-managing-risk"></a>Uma nota sobre o gerenciamento de riscos

Métodos como ' lado a lado ' são importantes no esquema de lógica de atualização. Ao atualizar lado a lado, você mantém seu farm do Microsoft Office SharePoint Server 2007, mas cria um farm com a próxima versão acima dele (SharePoint Server 2010) em novo hardware. Isso ajuda de três maneiras:
  
1. Você tem um local para fazer backups dos seus bancos de dados do Microsoft Office SharePoint Server 2007 para atualizá-los separadamente usando anexar banco de dados.
    
2. Se você descobrir que apenas um pequeno número de bibliotecas de documentos críticas e outras informações estão em uso no seu farm do Microsoft Office SharePoint Server 2007, você pode optar por mover manualmente os dados do Microsoft Office SharePoint Server 2007 para o SharePoint Server 2010 ou fazer apenas sites e Webs específicos para a próxima versão (o que pode facilitar o trabalho).
    
3. Quanto menos você fizer para o farm de servidores do Microsoft Office SharePoint Server 2007, diretamente, mais seguro serão os dados que o farm contém conforme você atualiza.
    
Métodos como a atualização in-loco atuarão diretamente no seu farm do Microsoft Office SharePoint Server 2007, fornecendo menos opções fáceis para abandonar um caminho e começar novamente com seu ambiente do pristine. Tanto quanto possível, crie algumas medidas de segurança (como fazer e testar backups do ambiente original). Por exemplo, se o seu farm do Microsoft Office SharePoint Server 2007 for virtual e estiver duplicado para fins de backup e restauração, faça backup e restaure os bancos de dados mais recentes antes da janela de serviço para a atualização. Sabendo que você tem a opção de restaurar backups de banco de dados não só dará uma falha na FailSafe, pode dar tranqüilidade.
  
> [!TIP]
> Os documentos de práticas recomendadas para atualização existem para [o Microsoft Office SharePoint server 2007, o](https://technet.microsoft.com/library/cc261992%28v=office.12%29.aspx) [SharePoint Server 2010](https://technet.microsoft.com/library/cc261992%28v=office.14%29.aspx), o [SharePoint Server 2013](https://technet.microsoft.com/library/cc261992%28v=office.15%29.aspx)e o [SharePoint Server 2016](https://technet.microsoft.com/library/cc261992%28v=office.16%29.aspx). Você também pode procurar [parceiros da Microsoft](https://partnercenter.microsoft.com/pcv/search) que tenham experiência com atualizações ou migrações do Microsoft 365. 
  
## <a name="make-your-plan"></a>Faça seu plano

Se for necessário atualizar, você precisará de um plano e ele não se ajustar a todos esses casos. Seu plano pode ser tão simples quanto ' criar uma assinatura do Microsoft 365 com o SharePoint Online, registrar um domínio e redirecionar as pessoas para salvar seus arquivos nesse local. E pode não ser. Essa decisão é sua e está inativa para o que você e seus usuários realmente precisam.
  
> [!NOTE]
> É arriscado executar em software, cujo ciclo de vida terminou. Os produtos sem suporte não são mais corrigidos quando os problemas são encontrados. Isso também significa que, se surgirem novas ameaças à segurança, não haverá patches ou correções de segurança porque os produtos de fim de ciclo de vida não são mais suportados. Evite essa situação! 
  
### <a name="first-know-your-farm"></a>Primeiro, conheça o farm

Ao atualizar, sua tomada de decisão deve se basear no que o seu farm faz para sua organização. Qual é a necessidade de satisfazer? Qual é sua função? Cada farm em sua empresa pode ter uma função diferente. Alguns dos seus farms do SharePoint podem ser  *críticos*  , alguns podem ser arquivos mortos: para manter a segurança. Ou, se o seu farm preencher muitas funções de uma só vez, talvez você precise saber quais conjuntos de sites, Webs ou até mesmo bibliotecas de documentos, quaisquer personalizações e o que são importantes. A análise de seus dados nesse nível pode parecer muito trabalho, mas poupa tempo e esforço para dominar o seu domínio antes de atualizar ou migrar. Quando você souber todas as partes em movimento e os bits mais importantes, você também saberá o que você está crescendo e pode deixar de trás. Esse conhecimento só beneficiará você no futuro. 
  
Portanto, o que os usuários dizem é mais importante em relação ao seu farm do SharePoint Server?
  
- Recursos internos do SharePoint
    
- O corpus de dados grande (como um arquivo morto de arquivos)
    
- Disponibilidade
    
- Aplicativos, Web Parts ou documentos críticos no farm (farm de missão crítica)
    
- Os padrões de conformidade atendidos
    
- Personalizações
    
Se você executar algo essencial à sua empresa a partir do seu farm do SharePoint, digamos que ele atue como um grande catálogo de dados críticos sobre os requisitos de serviço de cliente, você pode colocar uma marcação ao lado de "aplicativos críticos", mas também a ' disponibilidade '--ou seja, sua empresa será afetada se você não puder usar o SharePoint por algum tempo. Da mesma forma, você pode verificar ' personalizações ' porque os serviços críticos que seu farm oferece são baseados em código personalizado, definições de site ou várias personalizações que funcionam juntas.
  
Se o SharePoint atender a essas necessidades sem que você tenha que fazer nada fora do uso do que é integrado ao software e, em geral, você a atualize e execute a administração e a manutenção normais, talvez tenha escolhido ' SharePoint interno '--isso também pode ser o motivo de participar de uma versão mais antiga do SharePoint. Em outras palavras, ela já faz o que você precisa e não precisou atualizar até agora, no Microsoft Office SharePoint Server 2007 fim do suporte.
  
Ao listar itens com marcadores, você cria critérios para a atualização. Em outras palavras, qualquer atualização teria que atender a essa barra para ser considerada. Isso oferece uma maneira de descartar métodos que não atendam às suas necessidades no momento.
  
### <a name="a-simple-sample-plan"></a>Um plano de amostra simples

Talvez seja necessário ter um consenso mais amplo com liderança e outros administradores no caminho que a atualização do SharePoint terá. Os administradores do SharePoint Server costumam cooperar com os administradores do Microsoft SQL Server, trabalhar com equipes de segurança e de rede e muito mais. Onde há muitos participantes, talvez seja necessário criar um contrato para, ou ajustar, seu plano de atualização e migração. Por exemplo, se você migrar dados para que parte da sua empresa use o SharePoint Online no Microsoft 365, provavelmente precisará de ajuste de desempenho ou teste dentro da sua rede. Teams afetados devem ser informados antes do tempo.
  
Em minha amostra simples, mostrarei uma proposta de administrador do SharePoint e, em seguida, listamos o plano que todos os participantes participaram. Para maior clareza, documente seus contratos e decisões.
  
O plano é iniciado após uma análise detalhada de um farm e tenta identificar a função do farm, dos pontos problemáticos e de outras informações importantes que levarão a restringir algumas opções de atualização. Depois disso, uma proposta de atualização é feita pelo administrador do SharePoint e os stakeholders concordam em um plano de ação.
  
Minha lista de marcadores "mais importante":
  
- Disponibilidade, recursos internos do SharePoint e padrões de conformidade.
    
- A maioria dos dados está em três conjuntos de sites, com um espaço de trabalho de reunião usado por uma equipe de desenvolvimento, especialmente importante, e em uso pesado em vários fusos horários em todo o mundo.
    
- Há Seventeen outros sites amplamente usados.
    
- Duas bibliotecas de documentos (espaço de trabalho de reunião e documentos no conjunto de sites raiz) são maiores (mais de 8000 docs cada). Temos vários documentos e listas arquivados com anexos de planilha.
    
- Há 14 listas de bibliotecas que possuem dados confidenciais que devem permanecer em conformidade.
    
- É necessário ter a capacidade de manter e descoberta eletrônica onde quer que possamos.
    
- Alguns desses dados devem permanecer no local, devido às regras do InfoSec.
    
 **Minhas opções de migração e atualização:**
  
| Sim | Não |
|:-----|:-----|
|Atualizar bancos de dados com anexação de banco de dados  <br/> |Atualização in-loco  <br/> |
|Atualização com farms lado a lado  <br/> |Atualização híbrida  <br/> |
|API de migração para o SPO no Microsoft 365 (para dados de site pessoal)  <br/> |SharePoint híbrido (ainda não necessário)  <br/> |
|Algumas migrações manuais de dados para o SharePoint Online para dados críticos  <br/> |Atualização do assistente do FastTrack para o Microsoft 365  <br/> |
   
 **Meu plano proposto:**
  
Atualização no local, com as versões do SharePoint lado a lado, algumas virtualizadas, para que possamos atualizar primeiro os bancos de dados. Vá do SharePoint 2007 para o SharePoint 2010. Administradores e desenvolvedores testam o farm resultante. Os usuários testam o farm resultante. Correção de problemas de parada de apresentação durante esse tempo. Novamente, lado a lado, atualiza os bancos de dados do SharePoint 2010 para o SharePoint 2013. Test. Teste/piloto do usuário. Correção de problemas de parada de apresentação durante esse tempo.
  
- Considere se uma pesquisa híbrida federada com SPO atende às suas necessidades.
    
- Considere a [assistência do FastTrack](https://fasttrack.microsoft.com) se quiser atualizar para o SharePoint Online aqui. 
    
- Determine se os conjuntos de sites podem ser descarregados para uma assinatura do Microsoft 365. (A Microsoft 365 atende a vários [padrões de conformidade](https://technet.microsoft.com/library/office-365-compliance.aspx). O Microsoft 365 tem [eDiscovery](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) e pode fazer [suspensões](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) através do centro de conformidade.) 
    
Caso contrário, continue com uma atualização lado a lado para o SharePoint Server 2016.
  
> [!NOTE]
> Entre as recomendações feitas pelos administradores que planejam a atualização e o processo real são as conversas que ocorrem com outros participantes em que a atualização depende. Por exemplo, às vezes, a economia força os administradores a alterar seus planos. Seja qual for a decisão final, você deve documentar o que é o plano acordado, em frente. Pode ser algo assim: 
  
 **Meu plano de ação:**
  
No local, usamos um ambiente virtual para criar o SharePoint Server 2010 e o 2013 padrão. O SharePoint Server 2016 será criado em novo hardware que atenda aos requisitos do sistema para 2016. Faremos anexações de banco de dados para atualizar os bancos de dados do SharePoint 2007 por meio de todas as versões entre ele e o SharePoint Server 2016. As personalizações principais estão sendo recriadas e testadas no ambiente do SharePoint Server 2016 neste momento, se os recursos nativos ainda não atenderem às nossas necessidades. Se tivermos êxito, teremos um farm local em novo hardware com bancos de dados atualizados e menos personalizações. Anexaremos os bancos de dados de conteúdo atualizados a novos conjuntos de sites no SharePoint Server 2013, teste, teste de usuário/piloto e, em seguida, faça o recorte de DNS para o novo ambiente do SharePoint Server 2016 para uso em tempo real.
  
- No momento, não consideramos o híbrido federado entre o SharePoint Server 2016 e o SharePoint Online.
    
- Um estimado de 35% de nossos sites pode ser transformado em novos sites do SPO com domínios do personalizado ou, por fim, se torna o armazenamento do OneDrive for Business. Procurando outras oportunidades de converter sites ou rotear novos sites para o SPO.
    
- Parte dessa parte da migração será manual, arrastando e soltando para sites pessoais do OneDrive for Business e alguns pela API de migração.
    
Etapas mais detalhadas ou um número de links para orientações de atualização específicas devem seguir um plano. O computador MOSS 2007 não deve ser descomissionado, e os ambientes virtuais devem ser mantidos para fins de comparação; no entanto, a atualização estará concluída quando os usuários forem redirecionados para o SharePoint Server 2016.
  
Geralmente, os principais fatores na escolha de um método são o custo total da atualização e o custo no tempo (você verá mais informações sobre isso no artigo do mapa de migração do SharePoint). No entanto, o planejamento para o futuro o ajudará a definir as expectativas, escolhendo de forma inteligente e enquadrar qual será a aparência do sucesso.
  
## <a name="related-links"></a>Links relacionados

[Recursos para ajudá-lo a atualizar de clientes e servidores do Office 2007](upgrade-from-office-2007-servers-and-products.md)
  
[Política de ciclo de vida e pesquisa de ciclo de vida Microsoft](https://support.microsoft.com/lifecycle)
  
[Procurar parceiros da Microsoft que podem ajudar na atualização ou migração](https://partnercenter.microsoft.com/pcv/search)
  

