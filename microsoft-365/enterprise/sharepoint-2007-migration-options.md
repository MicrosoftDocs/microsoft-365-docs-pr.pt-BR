---
title: SharePoint opções de migração de 2007 a considerar
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
description: Este artigo contém informações para usuários que usam SharePoint Server 2007 para ajudá-los a planejar a atualização.
ms.openlocfilehash: 38c4713b7dfb705c99d970c5f68a37b031c951a5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924875"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>SharePoint opções de migração de 2007 a considerar

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O Microsoft SharePoint 2007 e o SharePoint Server 2007 chegaram ao fim do suporte. É hora de atualizar! Este artigo fornece informações sobre suas opções de migração.
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>Estratégias comuns de atualização para SharePoint

Há vários métodos para atualizar um ambiente SharePoint Server. Se você tiver um farm Microsoft Office SharePoint Server 2007, veja alguns exemplos dos métodos de atualização:
  
- Anexar banco de dados
    
- Atualização lado a lado
    
- Atualização in-loco
    
- Atualização híbrida (in-place com bancos de dados desvinculados /anexação de banco de dados separada)
    
- SharePoint híbridos (conectar-se online a SharePoint)
    
- Mover dados manualmente entre coleções de sites ou bibliotecas
    
- Atualização do Assistente do FastTrack para Microsoft 365 ([SharePoint de implantação online](https://aka.ms/spoguidance))
    
- API de migração para SharePoint Online (SPO) no Microsoft 365
    
O que funciona melhor para você?
  
Seu conhecimento sobre o que seu farm faz e é usado é uma força tática quando se trata de atualização. A maneira como as pessoas usam SharePoint Farm ajudarão você a escolher entre suas opções.
  
> [!TIP]
> Microsoft Office SharePoint Server 2007 também tem uma atualização gradual não abordada aqui. Para ver uma lista de artigos de atualização específicos de etapa, consulte o [SharePoint server 2007 end of support Roadmap](sharepoint-2007-end-of-support.md). 
  
Lembre-se de verificar [o Ciclo](https://support.microsoft.com/lifecycle/search) de Vida do Produto e os Requisitos do Sistema para qualquer versão SharePoint que você está atualizando. Isso é para que você esteja ciente quando a próxima atualização será necessária (por exemplo, se você pausar em um produto herdado como o SharePoint Server 2010 para planejar mais atualizações, certifique-se de saber a data de término do suporte) e ter certeza de que você tem hardware compatível com seu plano. 
  
Se você estiver planejando fazer a transição de alguns, ou todos, de seus sites SharePoint para Microsoft 365 na Nuvem, este é um momento para marcar um link para as descrições de serviço Microsoft 365 e [Office 365.](/office365/servicedescriptions/office-365-service-descriptions-technet-library) Você precisará das Descrições de Serviço para saber mais sobre os recursos SharePoint Online e como eles podem diferir do servidor SharePoint local. Atualize farms Microsoft Office SharePoint Server 2007. Se a instalação tiver sites quebrados, corrige-os antes da atualização.
  
## <a name="a-note-about-managing-risk"></a>Uma observação sobre o gerenciamento de riscos

Métodos como "lado a lado" são importantes no esquema de lógica de atualização. Ao atualizar lado a lado, você mantém seu farm do Microsoft Office SharePoint Server 2007, mas cria um farm com a próxima versão (SharePoint Server 2010) em um novo hardware. Isso ajuda de três maneiras:
  
1. Você tem um lugar para fazer backups de seus bancos de dados do Microsoft Office SharePoint Server 2007 para atualize-os separadamente, usando anexação de banco de dados.
    
2. Se você descobrir que apenas um pequeno número de bibliotecas de documentos críticas e outras informações estão em uso no farm do Microsoft Office SharePoint Server 2007, você pode optar por mover manualmente dados do Microsoft Office SharePoint Server 2007 para o SharePoint Server 2010 ou levar apenas sites e webs específicos para a próxima versão (o que pode facilitar seu trabalho).
    
3. Quanto menos você fizer no farm de servidores do Microsoft Office SharePoint Server 2007, mais seguro serão os dados que o farm contém à medida que você atualiza.
    
Métodos como In-Place atualização atuarão diretamente no farm do Microsoft Office SharePoint Server 2007, dando menos opções fáceis para você abandonar um caminho e começar novamente com seu ambiente puro. O máximo possível, crie algumas medidas de segurança (como fazer e testar backups do ambiente original). Por exemplo, se o farm do Microsoft Office SharePoint Server 2007 for virtual e for duplicado para fins de backup e restauração, faça backup e restaure os bancos de dados mais atuais antes da janela de serviço para a atualização. Saber que você tem a opção de restaurar backups de banco de dados não só lhe dará um failsafe, ele pode lhe dar tranquilidade.
  
> [!TIP]
> Os documentos de práticas recomendadas para atualização existem para [Microsoft Office SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc261992(v=office.12)), [SharePoint Server 2010,](/previous-versions/office/sharepoint-server-2010/cc261992(v=office.14)) [SharePoint Server 2013](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)e [SharePoint Server 2016](/SharePoint/upgrade-and-update/best-practices-for-upgrade). Você também pode pesquisar parceiros [microsoft que](https://partnercenter.microsoft.com/pcv/search) têm experiência com atualizações ou Microsoft 365 migrações. 
  
## <a name="make-your-plan"></a>Fazer seu plano

Se você precisar atualizar, precisará de um plano e um tamanho único não se encaixa em todos esses casos. Seu plano pode ser tão simples quanto "Criar uma assinatura Microsoft 365 com o SharePoint Online, registrar um domínio e redirecionar pessoas para salvar seus arquivos lá". E pode não ser. Essa decisão é sua e está abaixo do que você e seus usuários realmente precisam.
  
> [!NOTE]
> É arriscado executar em software cujo ciclo de vida terminou. Os produtos que estão sem suporte não são mais remendados quando os problemas são encontrados. Isso também significa que, se novas ameaças de segurança surgirem, não haverá correções ou patches de segurança porque os produtos de fim de ciclo de vida não são mais suportados. Evite essa situação! 
  
### <a name="first-know-your-farm"></a>Primeiro, conheça seu farm

Ao atualizar, sua tomada de decisão deve se basear no que seu farm faz para sua organização. Qual é a necessidade? Qual é a função dele? Cada farm em sua empresa pode ter uma função diferente. Alguns de seus farms SharePoint podem *ser* críticos , alguns podem ser arquivos de arquivos - lá para manter a segurança. Ou, se o farm preencher várias funções de uma só vez, talvez seja necessário saber o que os conjunto de sites, webs ou até mesmo bibliotecas de documentos fazem, quaisquer personalizações e a importância que elas são. Analisar seus dados nesse nível pode parecer muito trabalho, mas economiza tempo e esforço para dominar seu domínio antes de atualizar ou migrar. Depois de conhecer todas as partes móveis e as partes mais importantes, você também sabe o que cresceu e pode deixar para trás. Esse conhecimento só beneficiará você no futuro. 
  
Então, o que os usuários estão dizendo é mais importante sobre seu farm SharePoint Server?
  
- Recursos de SharePoint integrados
    
- O corpus de dados grandes (como um arquivo morto de arquivos)
    
- Disponibilidade
    
- Aplicativos críticos, web parts ou documentos no farm (farm crítico da missão)
    
- Os padrões de conformidade atendidos
    
- Personalizações
    
Se você executar algo essencial para sua empresa a partir de seu farm do SharePoint, diga que ele age como um grande catálogo de dados críticos sobre os requisitos de serviço do cliente, você pode colocar um tick ao lado de "Aplicativos críticos", mas também "Disponibilidade", ou seja, sua empresa seria impactada se você não pudesse usar o SharePoint por um tempo. Da mesma forma, você pode verificar "Personalizações" porque os serviços críticos que seu farm oferece se baseiam em código personalizado, definições de site ou várias personalizações que funcionam em conjunto.
  
Se SharePoint atendia a essas necessidades sem que você tivesse que fazer nada além de usar o que é integrado ao software, e você geralmente atualizá-lo e realizar a administração e a manutenção normais, você pode ter escolhido 'Built-in SharePoint' - isso também pode ser o motivo para se sentar em uma versão mais antiga do SharePoint. Em outras palavras, ele já faz o que você precisa e você não precisa atualizar até agora, no Microsoft Office SharePoint server 2007 final do suporte.
  
Quando você lista essas coisas, cria critérios para a atualização. Em outras palavras, qualquer atualização teria que atender a essa barra a ser considerada. Isso oferece uma maneira de excluir métodos que não se ajustam às suas necessidades no momento.
  
### <a name="a-simple-sample-plan"></a>Um plano de exemplo simples

Talvez seja necessário haver um consenso maior com a liderança e outros administradores sobre o caminho que sua atualização SharePoint tomar. SharePoint Os administradores de servidores geralmente cooperam com Microsoft SQL Server administradores, trabalham com equipes de Rede e Segurança e muito mais. Onde há muitas partes interessadas, talvez seja necessário criar um contrato para, ou ajustar, seu plano de atualização e migração. Por exemplo, se você migrar dados para que parte da sua empresa use o SharePoint Online no Microsoft 365, provavelmente haverá ajuste de desempenho ou teste dentro da sua rede. As equipes afetadas devem ser informadas com antecedência.
  
No meu exemplo simples, eu mostrarei uma SharePoint proposta do administrador e listo o plano que todas as partes interessadas aceitaram. Para esclarecer, documente seus acordos e decisões.
  
O plano começa após uma análise detalhada de um farm e tenta identificar a função do farm, pontos de dor e outras informações importantes que levarão ao estreitamento de algumas opções de atualização. Posteriormente, uma proposta de atualização é feita SharePoint administrador, e as partes interessadas concordam em um plano de ação.
  
Minha lista de marcador "mais importantes":
  
- Disponibilidade, recursos integrados aos SharePoint e padrões de Conformidade.
    
- A maioria dos dados está em três coleções de sites, com um Espaço de Trabalho de Reunião usado por uma equipe de Dev particularmente importante e em uso intenso em vários fusos horário em todo o mundo.
    
- Há outros 17 sites amplamente usados.
    
- Duas bibliotecas de documentos (Espaço de Trabalho de Reunião e Documentos no conjunto de sites raiz) são maiores (mais de 8.000 documentos cada). Temos um grande número de documentos arquivados e lista com anexos de planilha.
    
- Há quatorze listas de bibliotecas que têm dados confidenciais que DEVEM permanecer em Conformidade.
    
- Devemos ter a capacidade de fazer ressarcimentos e descoberta por e-discovery onde quer que vá.
    
- Alguns desses dados devem permanecer no local, devido às regras do InfoSec.
    
 **Minhas opções de atualização e migração:**
  
| Sim | Não |
|:-----|:-----|
|Atualizar bancos de dados com anexação de banco de dados  <br/> |Atualização in-loco  <br/> |
|Atualizar com farms lado a lado  <br/> |Atualização híbrida  <br/> |
|API de migração para SPO em Microsoft 365 (para dados pessoais do site)  <br/> |SharePoint Híbrido (ainda não necessário)  <br/> |
|Algumas migrações manuais de dados para SharePoint Online para dados críticos  <br/> |Atualização do assistente do FastTrack para Microsoft 365  <br/> |
   
 **Meu plano proposto:**
  
Atualize no local, com versões SharePoint lado a lado, algumas virtualizadas, para que possamos atualizar os bancos de dados primeiro. Vá de SharePoint 2007 para SharePoint 2010. Os administradores e os Devs testam o farm resultante. Os usuários testam o farm resultante. Correção de problemas de interrupção de exibição durante esse tempo. Novamente, lado a lado, atualize SharePoint bancos de dados 2010 para SharePoint 2013. Testar. Teste/piloto do usuário. Correção de problemas de interrupção de exibição durante esse tempo.
  
- Considere se um Híbrido Federado de Pesquisa com SPO atende às suas necessidades.
    
- Considere [a assistência do FastTrack](https://fasttrack.microsoft.com) se quiser atualizar para o SharePoint Online a partir daqui. 
    
- Determine se qualquer conjunto de sites pode ser descarregado para uma assinatura Microsoft 365. (Microsoft 365 atende a muitos [padrões de Conformidade.](/compliance/regulatory/offering-home) Microsoft 365 tem [Descoberta E e](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) pode fazer [Retém](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) por meio do Centro de Conformidade.) 
    
Caso contrário, continue com uma atualização lado a lado para SharePoint Server 2016.
  
> [!NOTE]
> Entre as recomendações feitas pelos administradores que planejam a atualização e o processo real estão as conversas que ocorrem com outras partes interessadas nas quais a atualização depende. Por exemplo, às vezes, a economia força os administradores a alterar seus planos. Seja qual for a decisão final, você deve documentar qual é o plano acordado, em frente. Pode ter uma aparência assim: 
  
 **Meu plano de ação:**
  
No local, usamos um ambiente virtual para criar o SharePoint Server 2010 e 2013 padrão. SharePoint O Server 2016 será criado em um novo hardware que atenda aos requisitos do sistema para 2016. Faremos anexações de banco de dados para atualizar bancos de dados do SharePoint 2007 por todas as versões entre ele e o SharePoint Server 2016. As personalizações principais estão sendo recriadas e testadas no ambiente do SharePoint Server 2016 no momento, se os recursos nativos ainda não atenderem às nossas necessidades. Se for bem-sucedido, teremos um farm local em novo hardware com bancos de dados atualizados e menos personalizações. Anexamos os bancos de dados de conteúdo atualizados a novos conjunto de sites no SharePoint Server 2013, testaremos, testaremos o usuário/piloto e faremos um recorte DNS no novo ambiente do SharePoint Server 2016 para uso ao vivo.
  
- Não consideraremos o Híbrido Federado entre SharePoint Server 2016 e SharePoint Online agora.
    
- Estima-se que 35% dos nossos sites podem ser transformados em novos sites SPO com domínios falsos ou, por fim, tornar-se OneDrive for Business armazenamento. Procurando outras oportunidades para converter sites ou rotear novos sites para o SPO.
    
- Parte dessa parte da migração será manual, arrastando e soltando para OneDrive for Business sites pessoais e alguns por API de migração.
    
Etapas mais detalhadas ou vários links para direções de atualização específicas devem seguir um plano. O computador MOSS 2007 não deve ser desativado e os ambientes virtuais devem ser mantidos para fins de comparação; no entanto, a atualização será concluída quando os usuários são redirecionados para SharePoint Server 2016.
  
Muitas vezes, os principais fatores na escolha de um método são o custo total da atualização e o custo no tempo (você verá mais sobre isso no artigo roteiro de migração do SharePoint). No entanto, planejar com antecedência o beneficiará bastante na definição de expectativas, na escolha e no enquadramento da aparência do sucesso.
  
## <a name="related-links"></a>Links relacionados

[Recursos para ajudá-lo a atualizar Office 2007 servidores e clientes](upgrade-from-office-2007-servers-and-products.md)
  
[Pesquisa de Política de Ciclo de Vida e Ciclo de Vida da Microsoft](https://support.microsoft.com/lifecycle)
  
[Pesquisar parceiros da Microsoft que podem ajudar na atualização ou migração](https://partnercenter.microsoft.com/pcv/search)
