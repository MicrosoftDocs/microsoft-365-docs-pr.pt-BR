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
description: Saiba mais sobre suas opções após o fim do suporte do Exchange Server 2007 e comece a planejar a migração para o Microsoft 365, Office 365 ou Exchange 2016.
ms.openlocfilehash: 3f0a5c8ef9765a184358b932548eaa2ae7c59adc
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519840"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Roteiro de fim do suporte do Exchange 2007

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O Exchange Server 2007 atingiu o fim do suporte em abril de 2017. Se você ainda não iniciou a migração do Exchange 2007 para o Microsoft 365, Office 365 ou Exchange 2016, agora é a hora de começar a planejar.
  
## <a name="what-does-end-of-support-mean"></a>O que *significa o fim do suporte?*

O Exchange Server, como quase todos os produtos da Microsoft, tem um ciclo de vida de suporte durante o qual fornecemos novos recursos, correções de bugs, correções de segurança e assim por diante. Esse ciclo de vida geralmente dura 10 anos a partir do lançamento inicial do produto. O fim desse ciclo de vida é conhecido como o fim do suporte do produto. Como o Exchange 2007 atingiu o fim do suporte em 11 de abril de 2017, a Microsoft não oferece mais:
  
- Suporte técnico para problemas que podem ocorrer.
    
- Correções de bugs para problemas que podem afetar a estabilidade e a usabilidade do servidor.
    
- Correções de segurança para vulnerabilidades que podem tornar o servidor vulnerável a violações de segurança.
    
- Atualizações de fuso horário.
    
Sua instalação do Exchange 2007 continuará a ser executado após a data de término do suporte. No entanto, como não há novas atualizações ou suporte, recomendamos que você migre do Exchange 2007 assim que possível.
  
Para obter mais informações sobre os servidores do Office 2007 próximos ao fim do suporte, consulte Planejar a atualização de servidores e produtos do [Office 2007.](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-are-my-options"></a>Quais são as minhas opções?

Você pode:
  
- Migre para o Microsoft 365 usando a migração de transferência, em estágios ou híbrida.
    
- Migre seus servidores do Exchange 2007 para uma versão mais recente do Exchange em seus servidores locais.
    
As seções a seguir exploram cada opção com mais detalhes.
  
### <a name="migrate-to-microsoft-365"></a>Migrar para o Microsoft 365

Migrar seu email para o Microsoft 365 é a melhor e mais simples opção para ajudar a retirar sua implantação do Exchange 2007. Com uma migração para o Microsoft 365, você pode fazer um único salto da tecnologia de 10 anos para os recursos de última geração, incluindo:
  
- Recursos de conformidade, como políticas de retenção, In-Place retenção e retenção de litígio, descoberta in-loco e muito mais
    
- Grupos do Microsoft 365
    
- Caixa de Entrada Destaques
    
- MyAnalytics
    
- APIs REST para acesso programático a emails, calendários, contatos e assim por diante
    
O Microsoft 365 também obtém novos recursos e experiências primeiro, para que você e seus usuários possam começar a usá-los imediatamente. E você não precisa se preocupar com:
  
- Compra e manutenção de hardware.
    
- Pagar para manter seus servidores com temperatura e frio.
    
- Mantenha-se atualizado sobre correções de segurança, produto e fuso horário.
    
- Manutenção de armazenamento e software para dar suporte aos requisitos de conformidade.
    
- Atualizando para uma nova versão do Exchange. Com o Microsoft 365, você está sempre na versão mais recente do Exchange.
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>Como migrar para o Microsoft 365?

Você tem algumas opções de migração. Você precisa considerar algumas coisas, incluindo:

- O número de usuários ou caixas de correio que você precisa mover.
- Quanto tempo você deseja que a migração dura.
- Se você precisa de integração perfeita entre sua instalação local e o Microsoft 365 durante a migração.

Esta tabela mostra as opções de migração e os fatores mais importantes que determinam qual método usar:
  

|**Opção de migração**|**Tamanho da organização**|**Duration**|
|:-----|:-----|:-----|
|Migração de substituição  <br/> |Menos de 150 assentos  <br/> |Uma semana ou menos  <br/> |
|Migração em estágios  <br/> |Mais de 150 assentos  <br/> |Algumas semanas  <br/> |
|Migração híbrida completa  <br/> |Centenas a milhares de assentos  <br/> |Alguns meses ou mais  <br/> |
   
As seções a seguir fornecem uma visão geral desses métodos. Para obter mais detalhes, consulte [Decidir sobre um caminho de migração.](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27) 
  
#### <a name="cutover-migration"></a>Migração de substituição

Em uma migração de recortar, você migra todas as suas caixas de correio, grupos de distribuição, contatos e assim por diante, para o Microsoft 365 em uma data e hora pré-selecionadas. Depois que a migração for concluída, você desligará seus servidores locais do Exchange e começará a usar o Microsoft 365 exclusivamente.
  
A migração de recortar é ótima para pequenas organizações que não têm muitas caixas de correio, querem chegar ao Microsoft 365 rapidamente e não querem lidar com algumas das complexidades dos outros métodos. Mas ele deve ser concluído em uma semana ou menos e exige que os usuários reconfigurem seus perfis do Outlook. A migração de recortar pode lidar com até 2.000 caixas de correio, mas é recomendável usá-la para migrar no máximo 150 caixas de correio. Se você tentar migrar mais, poderá ficar sem tempo para transferir todas as caixas de correio antes da data limite, e sua equipe de suporte de TI pode ficar sobrecarregada com solicitações para ajudar os usuários a reconfigurar o Outlook.
  
Se você estiver pensando em fazer uma migração de recortar, aqui estão algumas coisas a considerar:
  
- O Microsoft 365 precisará se conectar aos servidores do Exchange 2007 usando o Outlook em Qualquer Lugar em vez da porta TCP 443.
    
- Todas as caixas de correio locais serão movidas para o Microsoft 365.
    
- Você precisará de uma conta de administrador local que tenha acesso de leitura às caixas de correio dos usuários.
    
- Os domínios aceitos do Exchange 2007 que você deseja usar no Microsoft 365 precisam ser adicionados como domínios verificados no serviço.
    
- Entre o início da migração e o início da fase de conclusão, o Microsoft 365 sincroniza periodicamente as caixas de correio do Microsoft 365 e locais. Isso permite concluir a migração sem se preocupar com o email deixado para trás em suas caixas de correio locais.
    
- Os usuários receberão novas senhas temporárias para suas contas do Microsoft 365. Eles precisarão alterar a senha ao entrar na caixa de correio pela primeira vez.
    
- Você precisará de uma licença do Microsoft 365 que inclua o Exchange Online para cada caixa de correio de usuário migrada.
    
- Os usuários precisarão configurar um novo perfil do Outlook em cada um de seus dispositivos e baixar seus emails novamente. A quantidade de email que o Outlook baixará pode variar. Para obter mais informações, [consulte Alterar a quantos emails manter offline.](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)
    
Para obter mais informações sobre migração de cutover, consulte:
  
- [O que você precisa saber sobre uma migração de email de recorte](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [Executar uma migração de recortar de email](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>Migração em estágios

Em uma migração em estágios, você tem algumas centenas ou algumas milhares de caixas de correio que deseja migrar para o Microsoft 365, precisa levar uma semana ou mais para concluir a migração e não precisa de nenhum dos recursos avançados de migração híbrida, como informações compartilhadas do calendário de Livre/Ocupado.
  
A migração em estágios é ótima para organizações que precisam de mais tempo para migrar suas caixas de correio para o Microsoft 365, mas ainda planejam concluir a migração em algumas semanas. Você pode migrar caixas de correio em lotes. Você controla quantas e quais caixas de correio são migradas em um determinado momento. Você pode fazer o lote de caixas de correio de usuários no mesmo departamento, por exemplo, para garantir que todas elas serão movidas ao mesmo tempo. Ou você pode deixar caixas de correio executivas até o último lote. Assim como nas migrações de corte, os usuários precisarão recriar seus perfis do Outlook.
  
Se você estiver pensando em fazer uma migração em estágios, aqui estão algumas coisas a considerar:
  
- O Microsoft 365 precisará se conectar aos servidores do Exchange 2007 usando o Outlook em Qualquer Lugar em vez da porta TCP 443.
    
- Você precisará de uma conta de administrador local que tenha acesso de leitura às caixas de correio dos usuários.
    
- Os domínios aceitos do Exchange 2007 que você planeja usar no Microsoft 365 precisam ser adicionados como domínios verificados no serviço.
    
- Você precisará criar um arquivo CSV com o nome completo e o endereço de email de cada caixa de correio que planeja migrar em um lote. Você também precisará incluir uma nova senha para cada caixa de correio que está migrando e enviar essa senha para cada usuário. O usuário será solicitado a alterar a senha na primeira vez que entrar em sua nova caixa de correio do Microsoft 365.
    
- Entre o momento em que você inicia o lote de migração e quando você inicia a fase de conclusão, o Microsoft 365 sincroniza periodicamente as caixas de correio do Microsoft 365 e as caixas de correio locais incluídas no lote. Isso permite concluir a migração sem se preocupar com o email deixado para trás em suas caixas de correio locais.
    
- Você precisará de uma licença do Microsoft 365 que inclua o Exchange Online para cada caixa de correio de usuário migrada.
    
- Os usuários precisarão configurar um novo perfil do Outlook em cada um de seus dispositivos e baixar seus emails novamente. A quantidade de email que o Outlook baixará pode variar. Para obter mais informações, [consulte Alterar a quantos emails manter offline.](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)
    
Para obter mais informações sobre a migração em estágios, consulte:
  
- [O que você precisa saber sobre uma migração de email em estágios](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [Executar uma migração em estágios de email](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>Híbrido completo

Em uma migração híbrida completa, sua organização tem muitas centenas, até dezenas de milhares, de caixas de correio e você deseja mover algumas ou todas elas para o Microsoft 365. Como essas migrações geralmente são de longo prazo, as migrações híbridas possibilitam:
  
- Mostre aos usuários locais as informações do calendário de livre/ocupado para os usuários no Microsoft 365 e vice-versa.
    
- Veja uma lista de endereços global unificada que contém destinatários no local e no Microsoft 365.
    
- Exibir propriedades completas de destinatário do Outlook para todos os usuários, independentemente de eles estar no local ou no Microsoft 365.
    
- Proteja a comunicação de email entre servidores locais do Exchange e o Microsoft 365 usando TLS e certificados.
    
- Trate as mensagens enviadas entre servidores locais do Exchange e o Microsoft 365 como internas, permitindo que elas:
    
  - Ser avaliado corretamente e processado por agentes de transporte e conformidade direcionando mensagens internas.
    
  - Ignorar filtros anti-spam.
    
A migração híbrida completa é melhor para organizações que esperam permanecer em uma configuração híbrida por muitos meses ou mais. Você terá os recursos listados anteriormente nesta seção, além da sincronização de diretórios, recursos de conformidade melhor integrados e a capacidade de mover caixas de correio para e do Microsoft 365 usando movimentações de caixa de correio online. O Microsoft 365 se torna uma extensão da sua organização local.
  
Se você estiver pensando em fazer uma migração híbrida completa, aqui estão algumas coisas a considerar:
  
- A migração híbrida completa não é adequada para todos os tipos de organizações. Devido à complexidade das migrações híbridas completas, as organizações com menos de algumas centenas de caixas de correio normalmente não veem benefícios que justificam o esforço e o custo necessários para configurar uma. Se isso parece com sua organização, recomendamos que você considere uma migração de substituição ou em estágios.
    
- Você precisará implantar pelo menos um servidor do Exchange 2013 em sua organização do Exchange 2007 para agir como um "servidor híbrido". Este servidor se comunicará com o Microsoft 365 em nome de seus servidores Exchange 2007.
    
- O Microsoft 365 precisará se conectar ao "servidor híbrido" usando o Outlook em Qualquer Lugar em vez da porta TCP 443.
    
- Você precisará configurar a sincronização de diretório usando o Azure Active Directory (Azure AD) Connect entre seus servidores locais do Active Directory e o Microsoft 365.
    
- Os usuários poderão entrar em suas caixas de correio do Microsoft 365 usando o mesmo nome de usuário e senha de quando entrarem na rede local. (Essa funcionalidade requer o Azure AD Connect com sincronização de senha e/ou Serviços de Federação do Active Directory.)
    
- Você precisará de uma licença do Microsoft 365 que inclua o Exchange Online para cada caixa de correio de usuário migrada.
    
- Os usuários não precisam configurar um novo perfil do Outlook na maioria dos dispositivos, embora alguns telefones Android mais antigos possam precisar de um novo perfil. Os usuários não terão que recarregar seus emails.
    
Se a migração híbrida completa estiver correta para você, consulte os seguintes recursos para ajudar na migração:
  
- [Assistente de Implantação do Exchange](https://aka.ms/exdeploy)
    
- [Implantações Híbridas do Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx)
    
- [Assistente de Configuração Híbrida](https://technet.microsoft.com/library/hh529921%28v=exchg.150%29.aspx)
    
- [Perguntas frequentes do Assistente de Configuração Híbrida](https://technet.microsoft.com/library/mt488940%28v=exchg.150%29.aspx)
    
- [Pré-requisitos de implantação híbrida](https://technet.microsoft.com/library/hh534377%28v=exchg.150%29.aspx)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>Migrar para uma versão mais recente do Exchange Server

Acreditamos que você pode obter o melhor valor e a experiência do usuário migrando para o Microsoft 365. Mas também entendemos que algumas organizações precisam manter seus emails no local. Isso pode ser devido a requisitos regulatórios, para garantir que os dados não sejam armazenados em um datacenter localizado em outro país ou semelhante. Se você optar por manter seu email local, poderá migrar seu ambiente do Exchange 2007 para o Exchange 2010, o Exchange 2013 ou o Exchange 2016.
  
Se não for possível migrar para o Microsoft 365, recomendamos migrar para o Exchange 2016. O Exchange 2016 inclui todos os recursos de versões anteriores do Exchange. Ele também corresponde mais de perto à experiência disponível no Microsoft 365, embora alguns recursos só estão disponíveis no Microsoft 365. Confira apenas algumas das coisas que você está perdendo:
  
|**Versão do Exchange**|**Recursos**|
|:-----|:-----|
|Exchange 2010  <br/> | Role-Based Controle de Acesso (permissões sem ACLs)  <br/>  Políticas de caixa de correio do Outlook Web App  <br/>  Capacidade de compartilhar a livre/ocupado e delegar calendários entre organizações  <br/> |
|Exchange 2013  <br/> | *Recursos do Exchange 2010 e ...*  <br/>  Arquitetura simplificada que reduziu o número de funções de servidor para três (Caixa de Correio, Acesso para Cliente, Transporte de Borda)  <br/>  Políticas de prevenção contra perda de dados (DLP) que ajudam a evitar vazamento de informações confidenciais  <br/>  Experiência aprimorada do Outlook Web App  <br/> |
|Exchange 2016  <br/> | *Recursos do Exchange 2013 e ...*  <br/>  Funções de servidor mais simplificadas apenas para Caixa de Correio e Transporte de Borda  <br/>  DLP aprimorada, juntamente com a integração com o SharePoint  <br/>  Resiliência de banco de dados aprimorada  <br/>  Colaboração de documentos online |
   
#### <a name="which-version-should-i-migrate-to"></a>Para qual versão devo migrar?

Recomendamos que você inicialmente suponha que migrará para o Exchange 2016. Em seguida, use as informações a seguir para confirmar sua suposição ou descartar o Exchange 2016. Se você não puder migrar para o Exchange 2016 por algum motivo, faça o mesmo processo com o Exchange 2013 e assim por diante.
  
|**Considerações**|**Mais informações**|
|:-----|:-----|
|Datas de término do suporte  <br/> | Assim como o Exchange 2007, cada versão do Exchange tem sua própria data de fim de suporte:  <br/> *Exchange 2010* – janeiro de 2020  <br/> *Exchange 2013* – abril de 2023  <br/> *Exchange 2016* - outubro de 2025  <br/>  Quanto mais cedo o fim do suporte, mais cedo você precisará executar outra migração.<br/> |
|Caminho de migração para o Exchange 2010 e 2013.  <br/> |Aqui estão as fases gerais para migrar para o Exchange 2010 ou Exchange 2013:  <br/> - Instale o Exchange 2010 ou 2013 em sua organização existente do Exchange 2007. <br/>- Mover serviços e outra infraestrutura para o Exchange 2010 ou 2013.<br/>- Mover caixas de correio e pastas públicas para o Exchange 2010 ou 2013.<br/>- Desative os servidores restantes do Exchange 2007. |
|Caminho de migração para o Exchange 2016  <br/> |Aqui estão as fases gerais para migrar para o Exchange 2016:  <br/> - Instale o Exchange 2013 em sua organização existente do Exchange 2007.<br/>- Mover serviços e outra infraestrutura para o Exchange 2013.<br/>- Mover caixas de correio e pastas públicas para o Exchange 2013.<br/>- Desative os servidores restantes do Exchange 2007.<br/>- Instale o Exchange 2016 em sua organização existente do Exchange 2013.<br/>- Mover caixas de correio, pastas públicas, serviços e outras infraestruturas para o Exchange 2016 (a ordem não importa). Desative os servidores restantes do Exchange 2013.<br/><br/> **Observação:** É simples migrar do Exchange 2013 para o Exchange 2016. As duas versões têm quase os mesmos requisitos de hardware, e essas versões são muito compatíveis. Assim, você pode recriar um servidor que comprou para o Exchange 2013 e instalar o Exchange 2016 nele. Para movimentações de caixa de correio online, a maioria dos usuários nem perceberá que suas caixas de correio foram movidas do servidor e depois refeitas com o Exchange 2016.           |
|Coexistência de versão  <br/> | Ao migrar para...  <br/> **Exchange 2016:** O Exchange 2016 não pode ser instalado em uma organização que inclui um servidor Exchange 2007. Primeiro, você precisará migrar para o Exchange 2010 ou 2013 (é fortemente recomendável o Exchange 2013), remover todos os servidores do Exchange 2007 e depois migrar para o Exchange 2016.  <br/> **Exchange 2010 ou Exchange 2013:** Você pode instalar o Exchange 2010 ou o Exchange 2013 em uma organização existente do Exchange 2007. Isso permite que você instale um ou mais servidores Exchange 2010 ou 2013 e execute sua migração.  <br/> |
|Hardware de servidor  <br/> | Os requisitos de hardware do servidor foram alterados do Exchange 2007. Certifique-se de que seu hardware seja compatível. Veja mais detalhes em:  <br/> [Requisitos de sistema do Exchange 2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx) <br/> [Requisitos de sistema do Exchange 2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx) <br/> [Requisitos de sistema do Exchange 2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx) <br/>  Você verá que as melhorias significativas no desempenho do Exchange e o aumento da capacidade de computação e armazenamento em servidores mais novos significam que você provavelmente precisará de menos servidores para dar suporte ao mesmo número de caixas de correio.  <br/> |
|Versão do sistema operacional  <br/> | As versões mínimas do sistema operacional com suporte para cada versão são:  <br/> **Exchange 2016** - Windows Server 2012  <br/> **Exchange 2013** - Windows Server 2008 R2 SP1  <br/> **Exchange 2010** - Windows Server 2008 SP2  <br/>  Encontre mais informações sobre o suporte ao sistema operacional na Matriz [de Suporte do Exchange.](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx)  <br/> |
|Nível funcional da floresta do Active Directory  <br/> | Os níveis funcionais mínimos de floresta do Active Directory com suporte para cada versão são:  <br/> **Exchange 2016** Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  Encontre mais informações sobre o suporte a nível funcional da floresta na [Matriz de Suporte do Exchange.](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx)  <br/> |
|Versões de cliente do Office  <br/> | As versões mínimas de cliente do Office com suporte para cada versão são:  <br/> **Exchange 2016** - Office 2010 (com as atualizações mais recentes)  <br/> **Exchange 2013** - Office 2007 SP3  <br/> **Exchange 2010** - Office 2003  <br/>  Encontre mais informações sobre o suporte ao cliente do Office na [Matriz de Suporte do Exchange.](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx)  <br/> |
   
#### <a name="how-do-i-migrate"></a>Como faço para migrar?

Se você decidiu manter seu email no local, use os seguintes recursos para ajudar na migração:
  
- [Assistente de Implantação do Exchange](https://aka.ms/exdeploy)
    
- Alterações de esquema do Active Directory para o Exchange [2016](https://technet.microsoft.com/library/bb738144%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb738144%28v=exchg.150%29.aspx), [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)
    
- Requisitos do sistema para o Exchange [2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx)
    
- Pré-requisitos do Exchange [2016](https://technet.microsoft.com/library/bb691354%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb691354%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/bb691354%28v=exchg.141%29.aspx)
    
## <a name="get-help"></a>Obtenha ajuda

Se você estiver migrando para o Microsoft 365, poderá estar qualificado para usar nosso serviço Microsoft FastTrack. O FastTrack fornece práticas recomendadas, ferramentas e recursos para tornar a migração para o Microsoft 365 o mais simples possível. O melhor de tudo, um engenheiro de suporte o passará pela migração, desde o planejamento e o design até a migração da sua última caixa de correio. Para saber mais sobre o FastTrack, confira [o Microsoft FastTrack.](https://fasttrack.microsoft.com/)
  
Se você tiver problemas durante a migração para o Microsoft 365 e não estiver usando o FastTrack ou sua migração para uma versão mais recente do Exchange Server, estamos aqui para ajudar. Aqui estão alguns recursos que você pode usar:
  
- [Comunidade técnica](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [Suporte ao cliente](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>Tópicos relacionados

[Recursos para ajudá-lo a atualizar seus servidores e clientes do Office 2007](upgrade-from-office-2007-servers-and-products.md)
