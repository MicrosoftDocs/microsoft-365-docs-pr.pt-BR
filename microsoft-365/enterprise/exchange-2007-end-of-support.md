---
title: Roteiro de fim do suporte do Exchange 2007
ms.author: dstrome
author: dstrome
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: c3024358-326b-404e-9fe6-b618e54d977d
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: Saiba mais sobre suas opções após Exchange Server fim do suporte 2007 e comece a planejar a migração para Microsoft 365, Office 365 ou Exchange 2016.
ms.openlocfilehash: d7e8f50118dab6fcb618273f5c28497c80d4a549
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924195"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Roteiro de fim do suporte do Exchange 2007

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Exchange Server 2007 atingiu o fim do suporte em abril de 2017. Se você ainda não iniciou sua migração do Exchange 2007 para Microsoft 365, Office 365 ou Exchange 2016, agora é a hora de começar a planejar.
  
## <a name="what-does-end-of-support-mean"></a>O que *significa o fim do suporte?*

Exchange Server, como quase todos os produtos Microsoft, tem um ciclo de vida de suporte durante o qual fornecemos novos recursos, correções de bugs, correções de segurança e assim por diante. Esse ciclo de vida geralmente dura 10 anos a partir da versão inicial do produto. O final desse ciclo de vida é conhecido como o fim do suporte do produto. Desde Exchange 2007 chegou ao fim do suporte em 11 de abril de 2017, a Microsoft não fornece mais:
  
- Suporte técnico para problemas que podem ocorrer.
    
- Correções de bugs para problemas que podem afetar a estabilidade e a usabilidade do servidor.
    
- Correções de segurança para vulnerabilidades que podem tornar o servidor vulnerável a violações de segurança.
    
- Atualizações de fuso horário.
    
Sua instalação do Exchange 2007 continuará sendo executado após a data de término do suporte. Porém, como não há novas atualizações ou suporte, recomendamos que você migre do Exchange 2007 assim que possível.
  
Para obter mais informações Office servidores 2007 próximos ao final do suporte, consulte Plan your [upgrade from Office 2007 servers and products](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-are-my-options"></a>Quais são minhas opções?

Você pode:
  
- Migre para Microsoft 365 usando a migração de transferência, em estágios ou híbrida.
    
- Migre seus Exchange 2007 para uma versão mais recente do Exchange em seus servidores locais.
    
As seções a seguir exploram cada opção com mais detalhes.
  
### <a name="migrate-to-microsoft-365"></a>Migrar para o Microsoft 365

Migrar seu email para Microsoft 365 é a melhor e mais simples opção para ajudar a retirar sua implantação Exchange 2007. Com uma migração para Microsoft 365, você pode fazer um salto único da tecnologia de 10 anos para os recursos de última geração, incluindo:
  
- Recursos de conformidade, como Políticas de Retenção, In-Place e Retenção de Litígio, Descoberta eDiscovery in-loco e muito mais
    
- Grupos do Microsoft 365
    
- Caixa de Entrada Destaques
    
- MyAnalytics
    
- APIs REST para acesso programático a emails, calendários, contatos e assim por diante
    
Microsoft 365 também obtém novos recursos e experiências primeiro, para que você e seus usuários possam começar a usá-los imediatamente. E você não precisa se preocupar com:
  
- Compra e manutenção de hardware.
    
- Pagar para aqueça e esfrie seus servidores.
    
- Mantendo-se atualizado sobre correções de segurança, produto e fuso horário.
    
- Manutenção de armazenamento e software para dar suporte aos requisitos de conformidade.
    
- Atualizando para uma nova versão do Exchange. Com Microsoft 365, você sempre está na versão mais recente do Exchange.
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>Como migrar para Microsoft 365?

Você tem algumas opções de migração. Você precisa considerar algumas coisas, incluindo:

- O número de bancos ou caixas de correio que você precisa mover.
- Quanto tempo você deseja que a migração durar.
- Se você precisa de uma integração perfeita entre sua instalação local e Microsoft 365 durante a migração.

Esta tabela mostra suas opções de migração e os fatores mais importantes que determinam qual método usar:
  

|**Opção de migração**|**Tamanho da organização**|**Duration**|
|:-----|:-----|:-----|
|Migração de substituição  <br/> |Menos de 150 lugares  <br/> |Uma semana ou menos  <br/> |
|Migração em estágios  <br/> |Mais de 150 lugares  <br/> |Algumas semanas  <br/> |
|Migração híbrida completa  <br/> |Várias centenas a milhares de bancos  <br/> |Alguns meses ou mais  <br/> |
   
As seções a seguir fornecem uma visão geral desses métodos. Para obter mais detalhes, [consulte Decide on a migration path](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27). 
  
#### <a name="cutover-migration"></a>Migração de substituição

Em uma migração de recortamento, você migra todas as caixas de correio, grupos de distribuição, contatos e assim por diante, para Microsoft 365 em uma data e hora pré-selecionadas. Depois que a migração for concluída, você desligará seus servidores Exchange locais e comece a usar Microsoft 365 exclusivamente.
  
A migração de recortamento é ótima para pequenas organizações que não têm muitas caixas de correio, querem chegar Microsoft 365 rapidamente e não querem lidar com algumas das complexidades dos outros métodos. Mas ele deve ser concluído em uma semana ou menos, e exige que os usuários reconfigurem seus perfis Outlook de usuário. A migração de recortamento pode manipular até 2.000 caixas de correio, mas é recomendável usá-la para migrar no máximo 150 caixas de correio. Se você tentar migrar mais, poderá ficar sem tempo para transferir todas as caixas de correio antes do prazo, e sua equipe de suporte de TI pode ficar sobrecarregada com solicitações para ajudar os usuários a reconfigurar Outlook.
  
Se você estiver pensando em fazer uma migração de recortamento, veja algumas coisas a considerar:
  
- Microsoft 365 precisar se conectar aos servidores Exchange 2007 usando Outlook em Qualquer Lugar pela porta TCP 443.
    
- Todas as caixas de correio locais serão movidas para Microsoft 365.
    
- Você precisará de uma conta de administrador local que tenha acesso de leitura às caixas de correio de seus usuários.
    
- Os Exchange 2007 aceitos que você deseja usar no Microsoft 365 precisam ser adicionados como domínios verificados no serviço.
    
- Entre o momento em que você iniciar a migração e quando você iniciar a fase de conclusão, Microsoft 365 sincronizar periodicamente as caixas de correio Microsoft 365 local e local. Isso permite que você conclua a migração sem se preocupar com o email que está sendo deixado para trás em suas caixas de correio locais.
    
- Os usuários receberão novas senhas temporárias para suas Microsoft 365 contas. Eles precisarão alterar a senha quando entrarem na caixa de correio pela primeira vez.
    
- Você precisará de uma licença Microsoft 365 que inclua Exchange Online para cada caixa de correio de usuário que você migrar.
    
- Os usuários precisarão configurar um novo perfil de Outlook em cada um de seus dispositivos e baixar seus emails novamente. A quantidade de emails que Outlook baixar pode variar. Para obter mais informações, [consulte Change how much mail to keep offline](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Para obter mais informações sobre a migração de recortamento, consulte:
  
- [O que você precisa saber sobre uma migração de email de recortamento](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [Executar uma migração de recortamento de email](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>Migração em estágios

Em uma migração em estágios, você tem algumas centenas ou algumas milhares de caixas de correio que deseja migrar para o Microsoft 365, precisa levar uma semana ou mais para concluir a migração e não precisa de nenhum dos recursos avançados de migração híbrida, como informações compartilhadas do calendário de Free/Busy.
  
A migração em estágios é ótima para organizações que precisam levar mais tempo para migrar suas caixas de correio para Microsoft 365 mas ainda planejam concluir a migração dentro de algumas semanas. Você pode migrar caixas de correio em lotes. Você controla quantas e quais caixas de correio são migradas em um determinado momento. Você pode fazer em lotes caixas de correio de usuários no mesmo departamento, por exemplo, para garantir que todas elas são movidas ao mesmo tempo. Ou você pode deixar caixas de correio executivas até o último lote. Assim como nas migrações de recortamento, os usuários precisarão recriar seus perfis Outlook de recortar.
  
Se você estiver pensando em fazer uma migração em estágios, aqui estão as coisas a considerar:
  
- Microsoft 365 precisar se conectar aos servidores Exchange 2007 usando o Outlook Em Qualquer Lugar pela porta TCP 443.
    
- Você precisará de uma conta de administrador local que tenha acesso de leitura às caixas de correio de seus usuários.
    
- Os Exchange 2007 aceitos que você planeja usar no Microsoft 365 precisam ser adicionados como domínios verificados no serviço.
    
- Você precisará criar um arquivo CSV com o nome completo e o endereço de email de cada caixa de correio que você planeja migrar em um lote. Você também precisará incluir uma nova senha para cada caixa de correio que está migrando e enviar essa senha para cada usuário. O usuário será solicitado a alterar a senha na primeira vez em que entrar na nova caixa de correio Microsoft 365 caixa de correio.
    
- Entre o momento em que você iniciar o lote de migração e quando você iniciar a fase de conclusão, Microsoft 365 sincronizar periodicamente as caixas de correio Microsoft 365 e locais incluídas no lote. Isso permite que você conclua a migração sem se preocupar com o email que está sendo deixado para trás em suas caixas de correio locais.
    
- Você precisará de uma licença Microsoft 365 que inclua Exchange Online para cada caixa de correio de usuário que você migrar.
    
- Os usuários precisarão configurar um novo perfil de Outlook em cada um de seus dispositivos e baixar seus emails novamente. A quantidade de emails que Outlook baixar pode variar. Para obter mais informações, [consulte Change how much mail to keep offline](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Para obter mais informações sobre a migração em estágios, consulte:
  
- [O que você precisa saber sobre uma migração em estágios de email](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [Executar uma migração em estágios de email](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>Híbrido completo

Em uma migração híbrida completa, sua organização tem muitas centenas, até dezenas de milhares, de caixas de correio, e você deseja mover algumas ou todas elas para Microsoft 365. Como essas migrações geralmente são de longo prazo, as migrações híbridas possibilitam:
  
- Mostrar aos usuários locais as informações de calendário de livre/ocupado para os usuários no Microsoft 365 e vice-versa.
    
- Consulte uma lista de endereços global unificada que contém destinatários no local e Microsoft 365.
    
- Exibir propriedades Outlook destinatários completos para todos os usuários, independentemente de eles estar no local ou Microsoft 365.
    
- Proteja a comunicação de email entre servidores Exchange locais e Microsoft 365 usando TLS e certificados.
    
- Trate as mensagens enviadas entre servidores Exchange locais e Microsoft 365 como internas, permitindo que elas:
    
  - Ser avaliado corretamente e processado por agentes de transporte e conformidade destinados a mensagens internas.
    
  - Ignorar filtros anti-spam.
    
A migração híbrida completa é melhor para organizações que esperam permanecer em uma configuração híbrida por muitos meses ou mais. Você obterá os recursos listados anteriormente nesta seção, além de sincronização de diretórios, recursos de conformidade melhor integrados e a capacidade de mover caixas de correio de e para Microsoft 365 usando movimentações de caixa de correio online. Microsoft 365 se torna uma extensão da sua organização local.
  
Se você estiver pensando em fazer uma migração híbrida completa, aqui estão as coisas a considerar:
  
- A migração híbrida completa não é adequada a todos os tipos de organizações. Devido à complexidade das migrações híbridas completas, as organizações com menos de algumas centenas de caixas de correio geralmente não veem benefícios que justifiquem o esforço e o custo necessários para configurar uma. Se isso parece com sua organização, recomendamos que você considere uma migração em estágios ou substituição.
    
- Você precisará implantar pelo menos um servidor Exchange 2013 em sua organização Exchange 2007 para atuar como um "servidor híbrido". Este servidor se comunicará com Microsoft 365 em nome dos servidores Exchange 2007.
    
- Microsoft 365 precisar se conectar ao "servidor híbrido" usando Outlook em Qualquer Lugar pela porta TCP 443.
    
- Você precisará configurar a sincronização de diretório usando o Azure Active Directory (Azure AD) Conexão entre seus servidores do Active Directory local e Microsoft 365.
    
- Os usuários poderão entrar na caixa de correio Microsoft 365 usando o mesmo nome de usuário e senha que quando entrarem na rede local. (Essa funcionalidade requer o Azure AD Conexão com sincronização de senha e/ou Serviços de Federação do Active Directory.)
    
- Você precisará de uma licença Microsoft 365 que inclua Exchange Online para cada caixa de correio de usuário que você migrar.
    
- Os usuários não precisam configurar um novo perfil de Outlook na maioria de seus dispositivos, embora alguns telefones Android mais antigos possam precisar de um novo perfil. Os usuários não terão que recarregar seus emails.
    
Se a migração híbrida completa parecer correta para você, consulte os seguintes recursos para ajudar na migração:
  
- [Exchange Assistente de Implantação](/exchange/exchange-deployment-assistant)
    
- [Implantações híbridas do Exchange Server](/exchange/exchange-hybrid)
    
- [Assistente de Configuração Híbrida](/exchange/hybrid-configuration-wizard)
    
- [Perguntas frequentes do Assistente de Configuração Híbrida](/exchange/hybrid-configuration-wizard-faqs)
    
- [Pré-requisitos de implantação híbrida](/exchange/hybrid-deployment-prerequisites)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>Migrar para uma versão mais recente do Exchange Server

Acreditamos fortemente que você pode obter o melhor valor e a experiência do usuário migrando para Microsoft 365. Mas também entendemos que algumas organizações precisam manter seus emails no local. Isso pode ser devido aos requisitos regulatórios, para garantir que os dados não sejam armazenados em um datacenter localizado em outro país ou semelhante. Se você optar por manter seu email no local, poderá migrar seu ambiente do Exchange 2007 para o Exchange 2010, Exchange 2013 ou Exchange 2016.
  
Se você não puder migrar para o Microsoft 365, recomendamos que você migre para o Exchange 2016. Exchange 2016 inclui todos os recursos de versões anteriores do Exchange. Ele também corresponde mais de perto à experiência disponível com Microsoft 365, embora alguns recursos estão disponíveis apenas em Microsoft 365. Confira apenas algumas das coisas que você está perdendo:
  
|**Exchange versão**|**Recursos**|
|:-----|:-----|
|Exchange 2010  <br/> | Role-Based Access Control (permissões sem ACLs)  <br/>  Políticas de caixa de correio do Outlook Web App  <br/>  Capacidade de compartilhar calendários de livre/ocupado e delegar entre organizações  <br/> |
|Exchange 2013  <br/> | *Recursos do Exchange 2010 e ...*  <br/>  Arquitetura simplificada que reduziu o número de funções de servidor para três (Caixa de Correio, Acesso para Cliente, Transporte de Borda)  <br/>  Políticas de prevenção contra perda de dados (DLP) que ajudam a manter informações confidenciais contra vazamentos  <br/>  Experiência Outlook Web App aprimorada  <br/> |
|Exchange 2016  <br/> | *Recursos do Exchange 2013 e ...*  <br/>  Funções de servidor mais simplificadas apenas para Caixa de Correio e Transporte de Borda  <br/>  DLP aprimorada juntamente com a integração com SharePoint  <br/>  Resiliência de banco de dados aprimorada  <br/>  Colaboração de documentos online |
   
#### <a name="which-version-should-i-migrate-to"></a>Para qual versão devo migrar?

Recomendamos inicialmente que você suponha que migrará para o Exchange 2016. Em seguida, use as informações a seguir para confirmar sua suposição ou excluir Exchange 2016. Se você não puder migrar para o Exchange 2016 por algum motivo, faça o mesmo processo com Exchange 2013 e assim por diante.
  
|**Considerações**|**Mais informações**|
|:-----|:-----|
|Datas de término do suporte  <br/> | Como Exchange 2007, cada versão do Exchange tem sua própria data de fim de suporte:  <br/> *Exchange 2010* - janeiro de 2020  <br/> *Exchange 2013* - abril de 2023  <br/> *Exchange 2016* - outubro de 2025  <br/>  Quanto antes o fim do suporte, mais cedo você precisará executar outra migração.<br/> |
|Caminho de migração para Exchange 2010 e 2013.  <br/> |Aqui estão as fases gerais para migrar para Exchange 2010 ou Exchange 2013:  <br/> - Instale Exchange 2010 ou 2013 em sua organização Exchange 2007 existente. <br/>- Mover serviços e outra infraestrutura para Exchange 2010 ou 2013.<br/>- Mover caixas de correio e pastas públicas para Exchange 2010 ou 2013.<br/>- Desativação de servidores Exchange 2007. |
|Caminho de migração para Exchange 2016  <br/> |Aqui estão as fases gerais para migrar para Exchange 2016:  <br/> - Instale Exchange 2013 em sua organização Exchange 2007 existente.<br/>- Mover serviços e outras infraestruturas para Exchange 2013.<br/>- Mover caixas de correio e pastas públicas para Exchange 2013.<br/>- Desativação de servidores Exchange 2007.<br/>- Instale Exchange 2016 em sua organização Exchange 2013 existente.<br/>- Mover caixas de correio, pastas públicas, serviços e outras infraestruturas para Exchange 2016 (a ordem não importa). Desative os servidores restantes Exchange 2013.<br/><br/> **Observação:** Migrar do Exchange 2013 para o Exchange 2016 é simples. As duas versões têm quase os mesmos requisitos de hardware e essas versões são muito compatíveis. Para que você possa recriar um servidor que comprou para Exchange 2013 e instalar Exchange 2016 nele. Para movimentações de caixa de correio online, a maioria dos usuários nem perceberá que sua caixa de correio foi movida do servidor e depois de reconstruí-la com o Exchange 2016.           |
|Coexistência de versão  <br/> | Ao migrar para ...  <br/> **Exchange 2016:** Exchange 2016 não pode ser instalado em uma organização que inclui um servidor Exchange 2007. Primeiro, você precisará migrar para o Exchange 2010 ou 2013 (recomendamos o Exchange 2013), remover todos os servidores Exchange 2007 e migrar para o Exchange 2016.  <br/> **Exchange 2010 ou Exchange 2013:** Você pode instalar Exchange 2010 ou Exchange 2013 em uma organização Exchange 2007 existente. Isso permite que você instale um ou mais servidores Exchange 2010 ou 2013 e execute sua migração.  <br/> |
|Hardware de servidor  <br/> | Os requisitos de hardware do servidor foram alterados Exchange 2007. Certifique-se de que o hardware seja compatível. Veja mais detalhes em:  <br/> [Exchange do sistema 2016](/Exchange/plan-and-deploy/system-requirements) <br/> [Exchange do sistema 2013](/exchange/exchange-2013-system-requirements-exchange-2013-help) <br/> [Exchange requisitos do sistema 2010](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141)) <br/>  Você verá que as melhorias significativas no desempenho Exchange e a maior capacidade de computação e armazenamento em servidores mais novos significam que você provavelmente precisará de menos servidores para dar suporte ao mesmo número de caixas de correio.  <br/> |
|Versão do sistema operacional  <br/> | As versões mínimas do sistema operacional com suporte para cada versão são:  <br/> **Exchange 2016** - Windows Server 2012  <br/> **Exchange 2013** - Windows Server 2008 R2 SP1  <br/> **Exchange 2010** - Windows Server 2008 SP2  <br/>  Encontre mais informações sobre o suporte ao sistema operacional [Exchange Supportability Matrix](/Exchange/plan-and-deploy/supportability-matrix).  <br/> |
|Nível funcional da floresta do Active Directory  <br/> | Os níveis funcionais mínimos de floresta do Active Directory com suporte para cada versão são:  <br/> **Exchange 2016** Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  Encontre mais informações sobre o suporte ao nível funcional da floresta [Exchange Supportability Matrix](/Exchange/plan-and-deploy/supportability-matrix).  <br/> |
|Office cliente  <br/> | As versões Office cliente mínimas com suporte para cada versão são:  <br/> **Exchange 2016** - Office 2010 (com as atualizações mais recentes)  <br/> **Exchange 2013** - Office 2007 SP3  <br/> **Exchange 2010** - Office 2003  <br/>  Encontre mais informações sobre o Office cliente em [Exchange Supportability Matrix.](/Exchange/plan-and-deploy/supportability-matrix)  <br/> |
   
#### <a name="how-do-i-migrate"></a>Como faço para migrar?

Se você decidiu manter seu email no local, use os seguintes recursos para ajudar na migração:
  
- [Exchange Assistente de Implantação](/exchange/exchange-deployment-assistant)
    
- Alterações no esquema do Active Directory Exchange [2016](/Exchange/plan-and-deploy/active-directory/ad-schema-changes), [2013](/exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help), [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)
    
- Requisitos do sistema Exchange [2016](/Exchange/plan-and-deploy/system-requirements), [2013](/exchange/exchange-2013-system-requirements-exchange-2013-help), [2010](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141))
    
- Pré-requisitos para Exchange [2016](/Exchange/plan-and-deploy/prerequisites), [2013](/exchange/exchange-2013-prerequisites-exchange-2013-help), [2010](/previous-versions/office/exchange-server-2010/bb691354(v=exchg.141))
    
## <a name="get-help"></a>Obtenha ajuda

Se você estiver migrando para Microsoft 365, talvez esteja qualificado para usar nosso serviço Do Microsoft FastTrack. O FastTrack fornece práticas recomendadas, ferramentas e recursos para tornar sua migração Microsoft 365 o mais perfeita possível. O melhor de tudo é que um engenheiro de suporte o fará passar por sua migração, desde o planejamento e o design até a migração da última caixa de correio. Para saber mais sobre o FastTrack, consulte [Microsoft FastTrack](https://fasttrack.microsoft.com/).
  
Se você tiver problemas durante sua migração para Microsoft 365 e não estiver usando o FastTrack ou sua migração para uma versão mais recente do Exchange Server, estamos aqui para ajudar. Aqui estão alguns recursos que você pode usar:
  
- [Comunidade técnica](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [Suporte ao cliente](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>Tópicos relacionados

[Recursos para ajudá-lo a atualizar seus Office 2007 servidores e clientes](upgrade-from-office-2007-servers-and-products.md)