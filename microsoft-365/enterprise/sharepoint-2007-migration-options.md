---
title: Opções de migração do SharePoint 2007 a considerar
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
# <a name="sharepoint-2007-migration-options-to-consider"></a>Opções de migração do SharePoint 2007 a considerar

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O Microsoft SharePoint 2007 e o SharePoint Server 2007 chegaram ao fim do suporte. Está na hora de atualizar! Este artigo fornece informações sobre suas opções de migração.
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>Estratégias comuns de atualização para o SharePoint

Há vários métodos para atualizar um ambiente do SharePoint Server. Se você tiver um farm do Microsoft Office SharePoint Server 2007, aqui estão alguns exemplos dos métodos de atualização:
  
- Anexar banco de dados
    
- Atualização lado a lado
    
- Atualização in-loco
    
- Atualização híbrida (in-place com bancos de dados desvinculados/anexação de banco de dados separada)
    
- Híbridos do SharePoint (conectar-se online ao SharePoint local)
    
- Mover dados manualmente entre coleções de sites ou bibliotecas
    
- Atualização do Assistente do FastTrack para o Microsoft 365 (consultor[de implantação do SharePoint Online)](https://aka.ms/spoguidance)
    
- API de migração para o SharePoint Online (SPO) no Microsoft 365
    
O que funciona melhor para você?
  
Seu conhecimento sobre o que seu farm faz e é usado é uma força tática quando se trata de atualização. A maneira como as pessoas usam o Farm do SharePoint ajudará você a escolher entre suas opções.
  
> [!TIP]
> O Microsoft Office SharePoint Server 2007 também tem uma atualização gradual não abordada aqui. Para ver uma lista de artigos de atualização específicos de etapas, consulte o Roteiro de fim do suporte do [SharePoint Server 2007.](sharepoint-2007-end-of-support.md) 
  
Lembre-se de verificar o [Ciclo](https://support.microsoft.com/lifecycle/search) de Vida do Produto e os Requisitos do Sistema para qualquer versão do SharePoint para a qual você está atualizando. Isso é para que você esteja ciente quando a próxima atualização será necessária (por exemplo, se você pausar em um produto herdado como o SharePoint Server 2010 para planejar mais atualizações, certifique-se de saber sua data de fim de suporte) e para ter certeza de que tem hardware compatível com seu plano. 
  
Se você estiver planejando fazer a transição de alguns ou todos os sites do SharePoint para o Microsoft 365 na nuvem, este é um momento para marcar um link para as descrições de serviço do [Microsoft 365 e office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library) Você precisará das Descrições do Serviço para saber mais sobre os recursos do SharePoint Online e como eles podem diferir do SharePoint Server local. Atualize farms funcionais do Microsoft Office SharePoint Server 2007. Se a instalação tiver sites desfeitos, corrige-os antes da atualização.
  
## <a name="a-note-about-managing-risk"></a>Uma observação sobre o gerenciamento de riscos

Métodos como "lado a lado" são importantes no esquema de lógica de atualização. Ao atualizar lado a lado, você mantém seu farm do Microsoft Office SharePoint Server 2007, mas cria um farm a próxima versão dele (SharePoint Server 2010) em um novo hardware. Isso ajuda de três maneiras:
  
1. Você tem um local para fazer backups dos seus bancos de dados do Microsoft Office SharePoint Server 2007 para atualize-os separadamente, usando anexação de banco de dados.
    
2. Se você descobrir que apenas um pequeno número de bibliotecas de documentos críticos e outras informações estão em uso em seu farm do Microsoft Office SharePoint Server 2007, você pode optar por mover manualmente dados do Microsoft Office SharePoint Server 2007 para o SharePoint Server 2010 ou levar apenas sites e webs específicos para a próxima versão (o que pode facilitar seu trabalho).
    
3. Quanto menos você fizer no farm de servidores do Microsoft Office SharePoint Server 2007, diretamente, mais seguro os dados desse farm conterão à medida que você atualiza.
    
Métodos como In-Place atualização agirão diretamente em seu farm do Microsoft Office SharePoint Server 2007, dando a você menos opções fáceis para abandonar um caminho e começar novamente com seu ambiente de pristine. Tanto quanto possível, crie algumas medidas de segurança (como fazer e testar backups do ambiente original). Por exemplo, se seu farm do Microsoft Office SharePoint Server 2007 for virtual e estiver duplicado para fins de backup e restauração, faça backup e restaure os bancos de dados mais atuais antes da janela de serviço para a atualização. Saber que você tem a opção de restaurar backups de banco de dados não só lhe dará uma segurança de falha, isso pode dar uma boa ideia.
  
> [!TIP]
> Documentos de práticas recomendadas para atualização existem [para Microsoft Office SharePoint Server 2007](https://technet.microsoft.com/library/cc261992%28v=office.12%29.aspx), [SharePoint Server 2010](https://technet.microsoft.com/library/cc261992%28v=office.14%29.aspx), [SharePoint Server 2013](https://technet.microsoft.com/library/cc261992%28v=office.15%29.aspx)e [SharePoint Server 2016](https://technet.microsoft.com/library/cc261992%28v=office.16%29.aspx). Você também pode procurar parceiros [da Microsoft que](https://partnercenter.microsoft.com/pcv/search) tenham experiência com atualizações ou migrações do Microsoft 365. 
  
## <a name="make-your-plan"></a>Faça seu plano

Se você precisar atualizar, precisará de um plano, e um único tamanho não se encaixa em todos esses casos. Seu plano pode ser tão simples quanto "Criar uma assinatura do Microsoft 365 com o SharePoint Online, registrar um domínio e redirecionar pessoas para salvar seus arquivos lá". E pode não ser. Essa decisão é sua, e é o que você e seus usuários realmente precisam.
  
> [!NOTE]
> É arriscado executar em um software cujo ciclo de vida foi encerrado. Produtos que não têm suporte não são mais corrigidas quando os problemas são encontrados. Isso também significa que, se surgirem novas ameaças à segurança, não haverá correções ou correções de segurança porque os produtos de fim do ciclo de vida não são mais suportados. Evite essa situação! 
  
### <a name="first-know-your-farm"></a>Primeiro, conheça seu farm

Ao atualizar, sua tomada de decisão deve ser baseada no que seu farm faz para sua organização. Qual é a necessidade que isso satisfaz? Qual é a função dele? Cada farm em sua empresa pode ter uma função diferente. Alguns de seus farms do SharePoint podem  *ser*  críticos, alguns podem ser arquivos arquivados, para manter a segurança. Ou, se o farm preencher várias funções ao mesmo tempo, talvez seja necessário saber quais são os sites, as webs ou até mesmo as bibliotecas de documentos, as personalizações e a importância deles. Analisar seus dados nesse nível pode parecer muito trabalho, mas economiza tempo e esforço para domine seu domínio antes de atualiza-lo ou migrá-lo. Depois de conhecer todas as partes em movimento e os bits mais importantes, você também saberá o que foi ultrapassado e pode deixar para trás. Esse conhecimento só beneficiará você no futuro. 
  
Então, o que os usuários estão dizendo é mais importante sobre seu farm do SharePoint Server?
  
- Recursos integrados do SharePoint
    
- O corpus de dados grande (como um arquivo de arquivos)
    
- Disponibilidade
    
- Aplicativos críticos, web parts ou documentos no farm (farm crítico de missão)
    
- Os padrões de conformidade atendidos
    
- Personalizações
    
Se você executar algo essencial para sua empresa a partir de seu farm do SharePoint, digamos que ele aja como um catálogo grande de dados críticos sobre os requisitos de serviço do cliente, você pode colocar um tick ao lado de 'Aplicativos críticos', mas também 'Disponibilidade' - ou seja, sua empresa seria impactada se você não pudesse usar o SharePoint por um tempo. Da mesma forma, você pode verificar "Personalizações" porque os serviços críticos que seu farm oferece são baseados em código personalizado, definições de site ou várias personalizações que funcionam em conjunto.
  
Se o SharePoint atendeu a essas necessidades sem que você precise fazer nada além de usar o que é integrado ao software, e você geralmente atualizá-lo e realizar a administração e a manutenção normais, você pode ter escolhido "SharePoint integrado" – esse também pode ser seu motivo para estar em uma versão mais antiga do SharePoint. Em outras palavras, ele já faz o que você precisa e você não precisa atualizar até agora, no fim do suporte do Microsoft Office SharePoint Server 2007.
  
Ao listar essas coisas com marcador, você cria critérios para a atualização. Em outras palavras, qualquer atualização teria que atender a essa barra para ser considerada. Isso oferece uma maneira de descartar métodos que atualmente não se ajustam às suas necessidades.
  
### <a name="a-simple-sample-plan"></a>Um plano de exemplo simples

Talvez seja necessário haver um consenso maior com a liderança e com outros administradores sobre o caminho que sua Atualização do SharePoint tomará. Os administradores do SharePoint Server frequentemente cooperam com os administradores do Microsoft SQL Server, trabalham com as equipes de Rede e Segurança e muito mais. Quando houver muitos participantes, talvez seja necessário criar um contrato para, ou ajustar, seu plano de atualização e migração. Por exemplo, se você migrar dados para que parte da sua empresa use o SharePoint Online no Microsoft 365, provavelmente haverá ajuste de desempenho ou teste dentro de sua rede. As equipes afetadas devem ser informadas com antecedência.
  
No meu exemplo simples, mostrarei a proposta de um administrador do SharePoint e listo o plano que todos os participantes concordaram. Para maior clareza, documente seus acordos e decisões.
  
O plano começa após uma análise profunda de um farm e tenta identificar a função do farm, pontos de problemas e outras informações importantes que levarão a restringir algumas opções de atualização. Posteriormente, uma proposta de atualização é feita pelo administrador do SharePoint, e os participantes concordam em um plano de ação.
  
Minha lista de marcador "mais importante":
  
- Disponibilidade, recursos integrados aos padrões de Conformidade e SharePoint.
    
- A maioria dos dados está em três coleções de sites, com um Espaço de Trabalho de Reunião usado por uma equipe de Dev particularmente importante e em uso intenso em vários fusos horário em todo o mundo.
    
- Há cerca de dez outros sites amplamente usados.
    
- Duas bibliotecas de documentos (Espaço de Trabalho de Reunião e Documentos no conjunto de sites raiz) são maiores (mais de 8.000 documentos cada). Temos um grande número de documentos arquivados e lista com anexos de planilha.
    
- Há 14 listas de bibliotecas que têm dados confidenciais que DEVEM permanecer em Conformidade.
    
- DEVEMOS ter a capacidade de fazer retém e descoberta de e-discovery onde quer que vamos.
    
- Alguns desses dados DEVEM permanecer no local, devido às regras do InfoSec.
    
 **Minhas opções de atualização e migração:**
  
| Sim | Não |
|:-----|:-----|
|Atualizar bancos de dados com anexação de banco de dados  <br/> |Atualização in-loco  <br/> |
|Atualizar com farms lado a lado  <br/> |Atualização híbrida  <br/> |
|API de migração para o SPO no Microsoft 365 (para dados de site pessoal)  <br/> |SharePoint Híbrido (não necessário ainda)  <br/> |
|Algumas migrações de dados manuais para o SharePoint Online para dados críticos  <br/> |Atualização do assistente do FastTrack para o Microsoft 365  <br/> |
   
 **Meu plano proposto:**
  
Atualize no local, com versões do SharePoint lado a lado, algumas virtualizadas, para que possamos atualizar os bancos de dados primeiro. Vá do SharePoint 2007 para o SharePoint 2010. Os administradores e os devs testam o farm resultante. Os usuários testam o farm resultante. Corrige todos os problemas de interrupção de apresentação durante esse período. Novamente, lado a lado, atualize os bancos de dados do SharePoint 2010 para o SharePoint 2013. Teste. Teste/piloto do usuário. Corrige todos os problemas de interrupção de apresentação durante esse período.
  
- Considere se um Híbrido Federado de Pesquisa com SPO atende às suas necessidades.
    
- Considere [a assistência do FastTrack](https://fasttrack.microsoft.com) se quiser atualizar para o SharePoint Online a partir daqui. 
    
- Determine se algum conjunto de sites pode ser descarregado para uma Assinatura do Microsoft 365. (O Microsoft 365 atende a muitos [padrões de conformidade.](https://technet.microsoft.com/library/office-365-compliance.aspx) O Microsoft 365 tem [Descoberta e](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) pode [fazer](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) Retém por meio do Centro de Conformidade.) 
    
Caso contrário, continue com uma atualização lado a lado para o SharePoint Server 2016.
  
> [!NOTE]
> Entre as recomendações feitas pelos administradores que planejam a atualização e o processo real estão as conversas que ocorrem com outros participantes nas quais a atualização depende. Por exemplo, às vezes, a economia força os administradores a alterar seus planos. Seja qual for a decisão final, você deve documentar qual é o plano acordado, no futuro. Pode ser algo parecido com isto: 
  
 **Meu plano de ação:**
  
No local, usamos um ambiente virtual para criar o SharePoint Server 2010 e 2013 padrão. O SharePoint Server 2016 será criado com base no novo hardware que atende aos requisitos do sistema para 2016. Faremos anexações de banco de dados para atualizar bancos de dados do SharePoint 2007 por meio de todas as versões entre ele e o SharePoint Server 2016. As personalizações principais estão sendo recriadas e testadas no ambiente do SharePoint Server 2016 no momento, se os recursos nativos ainda não atenderem às nossas necessidades. Se bem-sucedidos, teremos um farm local no novo hardware com bancos de dados atualizados e menos personalizações. Anexaremos os bancos de dados de conteúdo atualizados aos novos conjunto de sites no SharePoint Server 2013, testaremos, testaremos/testaremos o usuário e faremos um corte DNS para o novo ambiente do SharePoint Server 2016 para uso ao vivo.
  
- Não consideraremos o Híbrido Federado entre o SharePoint Server 2016 e o SharePoint Online no momento.
    
- Cerca de 35% dos nossos sites podem se transformar em novos sites SPO com domínios sem valor ou, por fim, se tornar armazenamento do OneDrive for Business. Procurando outras oportunidades para converter sites ou rotear novos sites para o SPO.
    
- Parte dessa parte da migração será manual, arrastando e soltando para sites pessoais do OneDrive for Business e outras pela API de migração.
    
Etapas mais detalhadas ou vários links para trajetos de atualização específicos devem seguir um plano. O computador moss 2007 não deve ser descomissionado, e os ambientes virtuais devem ser mantidos para fins de comparação; No entanto, a atualização será concluída quando os usuários são redirecionados para o SharePoint Server 2016.
  
Geralmente, os principais fatores na escolha de um método são o custo total da atualização e o custo no tempo (você verá mais sobre isso no artigo roteiro de migração do SharePoint). No entanto, planejar com antecedência o beneficiará muito em definir as expectativas, escolher com cuidado e enquadrar a aparência de sucesso.
  
## <a name="related-links"></a>Links relacionados

[Recursos para ajudá-lo a atualizar de servidores e clientes do Office 2007](upgrade-from-office-2007-servers-and-products.md)
  
[Pesquisa de Política de Ciclo de Vida e Ciclo de Vida da Microsoft](https://support.microsoft.com/lifecycle)
  
[Pesquisar parceiros da Microsoft que podem ajudar na atualização ou migração](https://partnercenter.microsoft.com/pcv/search)
  

