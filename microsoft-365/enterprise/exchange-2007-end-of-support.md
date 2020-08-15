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
description: Saiba mais sobre suas opções depois que o Exchange Server 2007 atingir o fim do suporte e iniciar o planejamento de migração para a Microsoft 365, Office 365 ou Exchange 2016.
ms.openlocfilehash: 864a4bc64f35a12dfea1a98b3d50430cd3e5714b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687465"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Roteiro de fim do suporte do Exchange 2007

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Em **11 de abril de 2017**, o Exchange Server 2007 alcançou o fim do suporte. Se você ainda não começou sua migração do Exchange 2007 para a Microsoft 365, Office 365 ou Exchange 2016, agora é hora de iniciar o planejamento. 
  
## <a name="what-does-end-of-support-mean"></a>O que significa o fim do suporte?

O Exchange Server, como quase todos os produtos da Microsoft, tem um ciclo de vida de suporte durante o qual fornecemos novos recursos, correções de erros, correções de segurança e assim por diante. Esse ciclo de vida normalmente dura 10 anos a partir da data da versão inicial do produto, e o final desse ciclo de vida é conhecido como o fim do suporte do produto. Como o Exchange 2007 atingiu o fim do suporte em 11 de abril de 2017, a Microsoft não fornece mais:
  
- Suporte técnico para problemas que podem ocorrer;
    
- Correções de erros descobertas e que podem afetar a estabilidade e a usabilidade do servidor;
    
- Correções de segurança para vulnerabilidades descobertas e que podem tornar o servidor vulnerável a falhas de segurança;
    
- Atualizações de fuso horário.
    
A instalação do Exchange 2007 continuará a ser executada após essa data. No entanto, devido às alterações listadas acima, é altamente recomendável migrar do Exchange 2007 o mais rápido possível.
  
Para obter mais informações sobre os servidores do Office 2007 próximos ao fim do suporte, consulte [Plan Your Upgrade from Office 2007 Servers and Products](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-are-my-options"></a>Quais são as minhas opções?

Agora que o Exchange 2007 atingiu o fim do suporte, é altamente recomendável explorar suas opções e preparar um plano de migração. Você pode:
  
- Migrar para o Microsoft 365 usando a migração de substituição, em estágios ou híbrida;
    
- Migre seus servidores do Exchange 2007 para uma versão mais recente do Exchange em seus servidores locais.
    
As seções a seguir exploram cada opção em mais detalhes.
  
### <a name="migrate-to-microsoft-365"></a>Migre para o Microsoft 365

Migrar seu email para a Microsoft 365 é a opção mais simples e fácil de ajudá-lo a retirar sua implantação do Exchange 2007. Com uma migração para o Microsoft 365, você pode fazer um único salto da tecnologia de 10 anos de idade para recursos de ponta, como:
  
- Recursos de conformidade, como políticas de retenção, bloqueio in-loco e de litígio, descoberta eletrônica in-loco e mais;
    
- Grupos do Microsoft 365;
    
- Caixa de entrada destaques;
    
- MyAnalytics
    
- APIs REST para acesso programático a emails, calendários, contatos e assim por diante.
    
O Microsoft 365 também obtém novos recursos e experiências primeiro, e você e seus usuários podem começar a usá-los imediatamente. Além de novos recursos, você não precisa se preocupar com:
  
- Compra e manutenção de hardware;
    
- Pagar a calefação e refrigeração de seus servidores;
    
- Manter-se atualizado sobre correções de segurança, produtos e fuso horário;
    
- Manutenção de armazenamento e software para atender aos requisitos de conformidade;
    
- Atualizando para uma nova versão do Exchange-você está sempre na versão mais recente do Exchange no Microsoft 365.
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>Como migrar para o Microsoft 365?

Dependendo da sua organização, você tem algumas opções que o ajudarão a acessar o Microsoft 365. Ao escolher uma opção de migração, você precisa considerar algumas coisas como o número de assentos ou caixas de correio que precisa mover, quanto tempo deseja que a migração seja a última e se precisa de uma integração perfeita entre a sua instalação local e o Microsoft 365 durante a migração. Esta tabela mostra as opções de migração e os fatores mais importantes que determinarão o método que você usará.
  
| |
|**Opção de migração**|**Tamanho da organização**|**Duration**|
|:-----|:-----|:-----|
|Migração de substituição  <br/> |Menos de 150 estações  <br/> |Uma semana ou menos  <br/> |
|Migração em estágios  <br/> |Mais de 150 assentos  <br/> |Algumas semanas  <br/> |
|Migração híbrida completa  <br/> |Várias centenas de milhares de estações  <br/> |Alguns meses ou mais  <br/> |
   
As seções a seguir fornecem uma visão geral desses métodos. Confira [decida em um caminho de migração](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27) para aprender os detalhes de cada método. 
  
#### <a name="cutover-migration"></a>Migração de substituição

Uma migração de substituição é aquela em que, em uma data e hora previamente selecionadas, você migrará todas as suas caixas de correio, grupos de distribuição, contatos e assim por diante, para a Microsoft 365; Quando tiver terminado, você desligará seus servidores locais do Exchange e começará a usar o Microsoft 365 exclusivamente.
  
O método de migração de substituição é ótimo para pequenas organizações que não têm muitas caixas de correio, que desejam obter o Microsoft 365 rapidamente e não querem lidar com algumas das complexidades dos outros métodos. Mas também é um tanto limitado porque deve ser concluída em uma semana ou menos, pois requer que os usuários reconfigurem seus perfis do Outlook. Embora a migração de substituição possa lidar com até 2.000 caixas de correio, é altamente recomendável migrar um máximo de 150 caixas de correio com esse método. Se você tentar migrar mais de 150 caixas de correio, você pode ficar sem tempo para transferir todas as caixas de correio antes do seu prazo, e sua equipe de suporte de ti pode se tornar sobrecarregado para ajudar os usuários a reconfigurar o Outlook.
  
Se você estiver pensando em realizar uma migração de substituição, aqui estão alguns pontos a considerar:
  
- O Microsoft 365 precisará se conectar aos seus servidores do Exchange 2007 usando o Outlook Anywhere pela porta TCP 443;
    
- Todas as caixas de correio locais serão movidas para o Microsoft 365;
    
- Você precisará de uma conta de administrador local que tenha acesso para ler o conteúdo das caixas de correio dos usuários;
    
- Os domínios aceitos do Exchange 2007 que você deseja usar no Microsoft 365 precisam ser adicionados como domínios verificados no serviço;
    
- Entre o momento em que você iniciar a migração e quando começar a fase de conclusão, o Microsoft 365 sincronizará periodicamente as caixas de correio locais e 365 da Microsoft. Isso permite que você conclua a migração sem se preocupar com emails que estão sendo deixados em suas caixas de correio locais;
    
- Os usuários receberão novas senhas temporárias para sua conta do Microsoft 365 que eles precisarão alterar quando fizerem logon em suas caixas de correio pela primeira vez;
    
- Você precisará de uma licença do Microsoft 365 que inclua o Exchange Online para cada caixa de correio de usuário que você migrar;
    
- Os usuários precisarão configurar um novo perfil do Outlook em cada um dos seus dispositivos e baixar seus emails novamente. A quantidade de email que o Outlook fará download pode variar. Para obter mais informações, confira [alterar a quantidade de emails que serão mantidas offline](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Para saber mais sobre a migração de substituição, confira:
  
- [O que você precisa saber sobre uma migração de substituição de emails](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [Executar uma migração de substituição de email](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>Migração em estágios

Uma migração em estágios é aquela onde você tem algumas centenas ou algumas mil caixas de correio que você deseja migrar para o Microsoft 365, precisa levar uma semana ou mais para concluir a migração e não precisa de qualquer um dos recursos de migração híbrida avançados, como informações de calendário de disponibilidade compartilhadas.
  
Migração em estágios é excelente para organizações que precisam levar mais tempo para migrar suas caixas de correio para a Microsoft 365, mas ainda planeja concluir a migração dentro de algumas semanas. Você pode migrar caixas de correio em "lotes" que permitem controlar quantas e quais caixas de correio são migradas em um determinado momento. Você pode fazer o lote de caixas de correio de usuários no mesmo departamento, por exemplo, para garantir que todas elas sejam movidas ao mesmo tempo. Ou você pode deixar caixas de correio executivas até o último lote. Assim como ocorre com as migrações de substituição, os usuários precisarão recriar seus perfis do Outlook.
  
Se você estiver pensando em realizar uma migração em estágios, aqui estão alguns pontos a considerar:
  
- O Microsoft 365 precisará se conectar aos seus servidores do Exchange 2007 usando o Outlook Anywhere pela porta TCP 443;
    
- Você precisará de uma conta de administrador local que tenha acesso para ler o conteúdo das caixas de correio dos usuários;
    
- Os domínios aceitos do Exchange 2007 que você deseja usar no Microsoft 365 precisam ser adicionados como domínios verificados no serviço;
    
- Você precisará criar um arquivo CSV com o nome completo e o endereço de email de cada caixa de correio que você deseja migrar em um lote. Você também precisará incluir uma nova senha para cada caixa de correio que estiver migrando e, em seguida, enviar a senha para cada usuário. O usuário será solicitado a alterar a senha na primeira vez que fizer logon na nova caixa de correio do Microsoft 365;
    
- Entre o momento em que você inicia o lote de migração e quando você começa a fase de conclusão, a Microsoft 365 sincronizará periodicamente as caixas de correio locais e 365 da Microsoft incluídas no lote. Isso permite que você conclua a migração sem se preocupar com emails que estão sendo deixados em suas caixas de correio locais;
    
- Os usuários receberão novas senhas temporárias para sua conta do Microsoft 365 que eles precisarão alterar quando fizerem logon na caixa de correio pela primeira vez;
    
- Você precisará de uma licença do Microsoft 365 que inclua o Exchange Online para cada caixa de correio de usuário que você migrar;
    
- Os usuários precisarão configurar um novo perfil do Outlook em cada um dos seus dispositivos e baixar seus emails novamente. A quantidade de email que o Outlook fará download pode variar. Para obter mais informações, confira [alterar a quantidade de emails que serão mantidas offline](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Para saber mais sobre migração em estágios, confira:
  
- [O que você precisa saber sobre uma migração de email em estágios](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [Executar uma migração em estágios de email](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>Híbrido completo

Uma migração híbrida completa é aquela em que sua organização tem muitas centenas, até dezenas de milhares, de caixas de correio e você deseja mover algumas ou todas elas para a Microsoft 365. Como essas migrações são geralmente de longo prazo, as migrações híbridas tornam possível:
  
- Mostrar usuários locais as informações de calendário de disponibilidade para usuários no Microsoft 365 e vice-versa;
    
- Veja uma lista de endereços global unificada que contém destinatários no local e no Microsoft 365;
    
- Exibir Propriedades completas de destinatários do Outlook para todos os usuários, independentemente de eles estarem no local ou no Microsoft 365;
    
- Comunicação segura de email entre servidores locais do Exchange e o Microsoft 365 usando TLS e certificados;
    
- Tratar mensagens enviadas entre os servidores locais do Exchange e o Microsoft 365 como interno, permitindo que eles:
    
  - Ser avaliado e processado corretamente por agentes de conformidade e de conformidade direcionados a mensagens internas;
    
  - Ignorar filtros antispam.
    
As migrações híbridas completas são melhores para as organizações que esperam permanecer em uma configuração híbrida por muitos meses ou mais. Você receberá os recursos listados anteriormente nesta seção, além de sincronização de diretórios, melhores recursos de conformidade integrados e a capacidade de mover caixas de correio de e para a Microsoft 365 usando movimentações de caixa de correio online. O Microsoft 365 se torna uma extensão de sua organização local.
  
Se você estiver pensando em realizar uma migração híbrida completa, aqui estão alguns pontos a considerar:
  
- As migrações híbridas completas não são adequadas a todos os tipos de organizações. Devido à complexidade de migrações híbridas completas, as organizações com menos de algumas cem caixas de correio não costumam ver benefícios que justificam o esforço e o custo necessário para definir um. Se isso soa como sua organização, recomendamos enfaticamente que você considere migrações de substituição ou em estágios.
    
- Você precisará implantar pelo menos um servidor do Exchange 2013 em sua organização do Exchange 2007 para atuar como um "servidor híbrido". Este servidor se comunicará com o Microsoft 365 em nome dos seus servidores do Exchange 2007;
    
- O Microsoft 365 precisará se conectar ao "servidor híbrido" usando o Outlook Anywhere pela porta TCP 443;
    
- Você precisará configurar a sincronização de diretório usando o Azure Active Directory (Azure AD) se conectar entre seus servidores do Active Directory local e o Microsoft 365;
    
- Os usuários poderão fazer logon em sua caixa de correio do Microsoft 365 usando o mesmo nome de usuário e senha que eles usam ao fazer logon na rede local (requer o Azure AD Connect com sincronização de senha e/ou serviços de Federação do Active Directory);
    
- Você precisará de uma licença do Microsoft 365 que inclua o Exchange Online para cada caixa de correio de usuário que você migrar;
    
- Os usuários não precisam configurar um novo perfil do Outlook na maioria de seus dispositivos (alguns telefones Android antigos podem precisar de um novo perfil) e não precisam baixar novamente seus emails.
    
Se uma migração híbrida completa for adequada para você, dê uma olhada nos seguintes recursos para ajudá-lo com a migração:
  
- [Assistente de implantação do Exchange](https://aka.ms/exdeploy)
    
- [Implantações híbridas do Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx)
    
- [Assistente de Configuração Híbrida](https://technet.microsoft.com/library/hh529921%28v=exchg.150%29.aspx)
    
- [Perguntas frequentes do Assistente de Configuração Híbrida](https://technet.microsoft.com/library/mt488940%28v=exchg.150%29.aspx)
    
- [Pré-requisitos de implantação híbrida](https://technet.microsoft.com/library/hh534377%28v=exchg.150%29.aspx)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>Migrar para uma versão mais recente do Exchange Server

Embora acreditemos que você possa obter o melhor valor e a experiência de usuário migrando para a Microsoft 365, também entendemos que algumas organizações precisam manter seus emails no local. Isso pode ser devido a requisitos normativos, para garantir que os dados não sejam armazenados em um Datacenter localizado em outro país e assim por diante. Se você optar por manter seu email no local, poderá migrar seu ambiente do Exchange 2007 para o Exchange 2010, Exchange 2013 ou Exchange 2016.
  
Recomendamos migrar para o Exchange 2016 se não for possível migrar para o Microsoft 365. O Exchange 2016 inclui todos os recursos e avanços incluídos nas versões anteriores do Exchange e mais uma delas corresponde à experiência disponível com o Microsoft 365 (embora alguns recursos estejam disponíveis somente no Microsoft 365). Confira apenas algumas das coisas que você esteve perdendo:
  
|**Versão do Exchange**|**Recursos**|
|:-----|:-----|
|Exchange 2010  <br/> | Controle de acesso baseado em função (permissões sem ACLs)  <br/>  Políticas de caixa de correio do Outlook Web App  <br/>  Capacidade de compartilhar calendários de disponibilidade e de destino entre organizações  <br/> |
|Exchange 2013  <br/> | *Recursos do Exchange 2010 e...*  <br/>  Arquitetura simplificada reduzindo o número de funções de servidor para três (caixa de correio, acesso para cliente, transporte de borda)  <br/>  Políticas de prevenção contra perda de dados (DLP) que ajudam a manter informações confidenciais contra vazamento  <br/>  Experiência do Outlook Web App significativamente aprimorada  <br/> |
|Exchange 2016  <br/> | *Recursos do Exchange 2013 e...*  <br/>  Funções de servidor simplificadas para apenas o transporte de borda e caixa de correio  <br/>  DLP aprimorado junto com a integração com o SharePoint  <br/>  Resiliência de banco de dados aprimorada  <br/>  Colaboração de documentos online  <br/> |
   
#### <a name="which-version-should-i-migrate-to"></a>Para qual versão devo migrar?

Recomendamos que você considere inicialmente que você migrará para o Exchange 2016. Em seguida, use as seguintes informações para confirmar sua suposição ou para descartar o Exchange 2016. Se você não conseguir migrar para o Exchange 2016 por um motivo ou outro, faça o mesmo processo com o Exchange 2013 e assim por diante.
  
|**Relação**|**Mais informações**|
|:-----|:-----|
|Datas de fim de suporte  <br/> | Como o Exchange 2007, cada versão do Exchange tem seu próprio fim de data de suporte:  <br/> **Exchange 2010** -janeiro de 2020  <br/> **Exchange 2013** -abril de 2023  <br/> **Exchange 2016** -outubro de 2025  <br/>  Antes do fim da data de suporte, mais cedo você precisará executar outra migração. Janeiro de 2020 é muito mais próximo do que você imagina!  <br/> |
|Caminho de migração para o Exchange 2010 e 2013  <br/> |Aqui estão as fases gerais para migrar para o Exchange 2010 ou o Exchange 2013:  <br/> Instalar o Exchange 2010 ou 2013 em seus serviços de movimentação de organização do Exchange 2007 existente e outra infraestrutura para o Exchange 2010 ou 2013 mover caixas de correio e pastas públicas para o Exchange 2010 ou 2013 encerrar servidores Exchange 2007 restantes |
|Caminho de migração para o Exchange 2016  <br/> |Aqui estão as fases gerais de migração para o Exchange 2016:  <br/> Instale o Exchange 2013 em seus serviços de movimentação de organização do Exchange 2007 existentes e outra infraestrutura para o Exchange 2013 mover caixas de correio e pastas públicas para o Exchange 2013 encerrar os servidores do Exchange 2007. Instale o Exchange 2016 em sua organização existente do Exchange 2013. Mover caixas de correio, pastas públicas, serviços e outras infra-estruturas para o Exchange 2016 (ordem não importa). Encerrar os servidores do Exchange 2013 restantes > [!NOTE]> migrar do exchange 2013 para o exchange 2016 é simples. Ambas as versões têm quase os mesmos requisitos de hardware. Isso e o fato de que essas versões são tão compatíveis, significa que você pode recriar um servidor que comprou o Exchange 2013 e instalar o Exchange 2016 nele. E, com as movimentações de caixa de correio online, a maioria dos usuários nunca perceberá que a caixa de correio está sendo movida do servidor e depois novamente após você tê-la reconstruída com o Exchange 2016.           |
|Coexistência de versões  <br/> | Ao migrar para:  <br/> **Exchange 2016** O Exchange 2016 não pode ser instalado em uma organização que inclui um servidor Exchange 2007. Primeiro, você precisará migrar para o Exchange 2010 ou 2013 (é altamente recomendável o Exchange 2013), remover todos os servidores do Exchange 2007 e migrar para o Exchange 2016.  <br/> **Exchange 2010 ou exchange 2013** Você pode instalar o Exchange 2010 ou o Exchange 2013 em uma organização existente do Exchange 2007. Isso permite que você instale um ou mais servidores do Exchange 2010 ou 2013 e realize sua migração.  <br/> |
|Hardware de servidor  <br/> | Os requisitos de hardware do servidor foram alterados do Exchange 2007. Você precisará certificar-se de que o hardware que você vai usar é compatível. Você pode saber mais sobre os requisitos de hardware para cada versão aqui:  <br/> [Requisitos de sistema do Exchange 2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx) <br/> [Requisitos de sistema do Exchange 2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx) <br/> [Requisitos de sistema do Exchange 2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx) <br/>  Você descobrirá que com os aprimoramentos significativos no desempenho do Exchange e com a capacidade de armazenamento e o aumento de energia em servidores mais recentes, provavelmente precisará de menos servidores para suportar o mesmo número de caixas de correio.  <br/> |
|Versão do sistema operacional  <br/> | As versões mínimas de sistema operacional com suporte para cada versão são:  <br/> **Exchange 2016** Windows Server 2012  <br/> **Exchange 2013** Windows Server 2008 R2 SP1  <br/> **Exchange 2010** Windows Server 2008 SP2  <br/>  Você pode encontrar mais informações sobre o suporte do sistema operacional na [matriz de suporte do Exchange](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
|Nível funcional da floresta do Active Directory  <br/> | Os níveis mínimos funcionais de floresta do Active Directory com suporte para cada versão são:  <br/> **Exchange 2016** Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  Você pode encontrar mais informações sobre o suporte de nível funcional da floresta na [matriz de suporte do Exchange](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
|Versões de cliente do Office  <br/> | As versões mínimas compatíveis do cliente do Office para cada versão são:  <br/> **Exchange 2016** Office 2010 (com as atualizações mais recentes)  <br/> **Exchange 2013** Office 2007 SP3  <br/> **Exchange 2010** Office 2003  <br/>  Você pode encontrar mais informações sobre o suporte do cliente do Office na [matriz de suporte do Exchange](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
   
#### <a name="how-do-i-migrate"></a>Como faço para migrar?

Se você quiser manter seu email no local, poderá usar os seguintes recursos para ajudá-lo com a migração:
  
- [Assistente de implantação do Exchange](https://aka.ms/exdeploy)
    
- Alterações de esquema do Active Directory para o Exchange [2016](https://technet.microsoft.com/library/bb738144%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb738144%28v=exchg.150%29.aspx), [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)
    
- Requisitos do sistema para o Exchange [2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx)
    
- Pré-requisitos para o Exchange [2016](https://technet.microsoft.com/library/bb691354%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb691354%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/bb691354%28v=exchg.141%29.aspx)
    
## <a name="what-if-i-need-help"></a>E se eu precisar de ajuda?

Se você estiver migrando para o Microsoft 365, poderá estar qualificado para usar nosso serviço Microsoft FastTrack. O FastTrack oferece práticas recomendadas, ferramentas e recursos para tornar sua migração para a Microsoft 365 o mais simples possível. O melhor de tudo é que você terá um engenheiro de suporte real que orientará você durante a migração, do planejamento e do design de toda a forma de migração da última caixa de correio. Se você quiser saber mais sobre o FastTrack, dê uma olhada no [Microsoft FastTrack](https://fasttrack.microsoft.com/).
  
Se você tiver problemas durante a migração para o Microsoft 365 e não estiver usando o FastTrack ou sua migração para uma versão mais recente do Exchange Server, estamos aqui para ajudar. Veja alguns recursos que você pode usar:
  
- [Comunidade técnica](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [Suporte ao cliente](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>Tópicos relacionados

[Recursos para ajudá-lo a atualizar seus servidores e clientes do Office 2007](upgrade-from-office-2007-servers-and-products.md)