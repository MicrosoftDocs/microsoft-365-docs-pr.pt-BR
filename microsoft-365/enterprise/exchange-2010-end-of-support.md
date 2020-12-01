---
title: Roteiro do encerramento de suporte do Exchange 2010
ms.author: dstrome
author: dstrome
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: e150e7b9-c432-4c8d-a0ae-c11847129a7d
f1.keywords:
- NOCSH
description: O Exchange 2010 atingiu o fim do suporte. Use este mapa de planejamento para preparar a atualização para o Exchange Online ou uma versão mais recente do Exchange Server no local.
ms.openlocfilehash: 23384d93c4e65fb25a66ca6f2f0bcbe46b34ee18
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519686"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Roteiro do encerramento de suporte do Exchange 2010

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

O Exchange Server 2010 atingiu o fim do suporte em **13 de outubro de 2020**. Se você ainda não começou sua migração do Exchange 2010 para a Microsoft 365, Office 365 ou Exchange 2016, agora é hora de começar a planejar.

## <a name="what-does-end-of-support-mean"></a>O que significa o *fim do suporte* ?

A maioria dos produtos da Microsoft tem um ciclo de vida de suporte durante o qual eles obtêm novos recursos, correções de erros, correções de segurança e assim por diante. Esse ciclo de vida normalmente dura 10 anos da versão inicial do produto. O final desse ciclo de vida é conhecido como o fim do suporte do produto. Como o Exchange 2010 atingiu o fim do suporte em 13 de outubro de 2020, a Microsoft não fornece mais:

- Suporte técnico para problemas que podem ocorrer.
- Correções de erros que podem afetar a estabilidade e a usabilidade do servidor.
- Correções de segurança para vulnerabilidades que podem tornar o servidor vulnerável a brechas de segurança.
- Atualizações de fuso horário.

A instalação do Exchange 2010 continuará a ser executada após essa data. Mas devido às alterações listadas acima, é altamente recomendável migrar do Exchange 2010 o mais rápido possível.

Para obter mais informações sobre o fim do suporte, consulte [recursos para ajudá-lo a atualizar de clientes e servidores do Office 2010](upgrade-from-office-2010-servers-and-products.md).

## <a name="what-are-my-options"></a>Quais são as minhas opções?

É um ótimo momento para explorar suas opções e preparar um plano de migração. Você pode:

- Migre totalmente para a Microsoft 365. Migrar caixas de correio usando transferência, uma migração híbrida mínima ou completa. Em seguida, remova os servidores locais do Exchange e o Active Directory.
- Migre seus servidores Exchange 2010 para o Exchange 2016 em seus servidores locais.

> [!IMPORTANT]
> Se sua organização optar por migrar caixas de correio para a Microsoft 365, mas planeja manter o DirSync ou o Azure AD Connect in-loco para continuar Gerenciando contas de usuário do Active Directory local, você precisará manter pelo menos um servidor do Microsoft Exchange no local. Se você remover todos os servidores do Exchange, não será possível fazer alterações nos destinatários do Exchange no Exchange Online porque a fonte de autoridade permanece no seu Active Directory local. As alterações precisam ser feitas ali. Neste cenário, você tem as seguintes opções:
>
>- *Recomendado:* Se você migrou suas caixas de correio para a Microsoft 365 e atualizou seus servidores de 13 de outubro de 2020, use o Exchange 2010 para se conectar ao Microsoft 365 e migrar caixas de correio. Em seguida, migre o Exchange 2010 para o Exchange 2016 e desative todos os servidores do Exchange 2010 restantes.
>- Se você não concluiu a migração de caixa de correio e a atualização do servidor local em 13 de outubro de 2020, atualize seus servidores locais do Exchange 2010 para o Exchange 2016 primeiro. Em seguida, use o Exchange 2016 para se conectar ao Microsoft 365 e migrar caixas de correio.

> [!NOTE]
> É pouco mais complicado, mas você também pode migrar caixas de correio para a Microsoft 365 enquanto migra seus servidores locais do Exchange 2010 para o Exchange 2016.

Estes são os três caminhos que você pode executar para evitar o fim do suporte para o Exchange Server 2010.

![Caminhos de atualização do Exchange Server 2010](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

As seções a seguir exploram cada opção em mais detalhes.

## <a name="migrate-to-microsoft-365"></a>Migrar para o Microsoft 365

Migrar seu email para a Microsoft 365 é a melhor opção e mais simples para ajudá-lo a retirar sua implantação do Exchange 2010. Com uma migração para o Microsoft 365, você pode fazer um único salto da tecnologia antiga para os recursos atuais, incluindo:

- Recursos de conformidade, como políticas de retenção, In-Place e retenção de litígio, descoberta eletrônica in-loco e muito mais.
- Microsoft Teams.
- Power BI.
- Caixa de entrada destaques.
- MyAnalytics.

O Microsoft 365 também obtém novos recursos e experiências primeiro, para que sua organização possa começar a usá-los imediatamente. Além disso, você não precisa se preocupar em:

- Compra e manutenção de hardware.
- Pagar ao aquecimento e resfriar seus servidores.
- Manter-se atualizado sobre correções de segurança, produtos e fuso horário.
- Manutenção de armazenamento e software para atender aos requisitos de conformidade.
- Atualização para uma nova versão do Exchange. Você está sempre na versão mais recente do Exchange no Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>Como migrar para o Microsoft 365?

Dependendo da sua organização, você tem algumas opções para acessar o Microsoft 365. Primeiro, você precisa considerar algumas coisas, como:
- O número de estações ou caixas de correio que você precisa mover.
- Quanto tempo você deseja para a migração por último.
- Se você precisa de uma integração perfeita entre a sua instalação local e o Microsoft 365 durante a migração.
 
Esta tabela mostra as opções de migração e os fatores mais importantes que determinam o método a ser usado.

|Opção de migração|Tamanho da organização|Duração|
|---|---|---|
|Migração de substituição|Menos de 150 estações|Uma semana ou menos|
|Migração híbrida mínima|Menos de 150 estações|Algumas semanas ou menos|
|Migração híbrida completa|Mais de 150 assentos|Algumas semanas ou mais|

As seções a seguir fornecem uma visão geral desses métodos. Para obter mais informações, consulte [decidir sobre um caminho de migração](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27).

### <a name="cutover-migration"></a>Migração de substituição

Em uma migração de transferência, você migra todas as suas caixas de correio, grupos de distribuição, contatos e assim por diante, para o Office 365 em um conjunto de data e hora. Quando você terminar, desligue seus servidores locais do Exchange e comece a usar o Microsoft 365 exclusivamente.

Migração de substituição é excelente para pequenas organizações que não têm muitas caixas de correio, deseja obter o Microsoft 365 rapidamente e não querem lidar com a complexidade dos outros métodos. Mas deve ser concluída em uma semana ou menos. E exige que os usuários reconfigurem seus perfis do Outlook. A migração de substituição pode migrar até 2.000 caixas de correio, mas recomendamos que você use-a para um máximo de 150. Se você tentar migrar mais, pode ficar sem tempo para transferir todas as caixas de correio antes do seu prazo, e sua equipe de suporte de ti pode ficar sobrecarregada com solicitações para ajudar os usuários a reconfigurar o Outlook.

Veja algumas coisas a considerar a migração de substituição:

- O Microsoft 365 precisará se conectar aos seus servidores do Exchange 2010 usando o Outlook em qualquer lugar da porta TCP 443.
- Todas as caixas de correio locais serão movidas para o Microsoft 365.
- Você precisará de uma conta de administrador local que tenha acesso de leitura às caixas de correio dos seus usuários.
- Os domínios aceitos do Exchange 2010 que você deseja usar no Microsoft 365 precisam ser adicionados como domínios verificados no serviço.
- Entre quando você iniciar a migração e quando começar a fase de conclusão, o Microsoft 365 sincronizará periodicamente as caixas de correio locais e 365 da Microsoft. Isso permite que você conclua a migração sem se preocupar com os emails que estão sendo deixados em suas caixas de correio locais.
- Os usuários receberão novas senhas temporárias para sua conta do Microsoft 365. Eles precisarão alterá-los quando entrarem em suas caixas de correio pela primeira vez.
- Você precisará de uma licença do Microsoft 365 que inclua o Exchange Online para cada caixa de correio de usuário que você migrar.
- Os usuários precisarão configurar um novo perfil do Outlook em cada um dos seus dispositivos e baixar seus emails novamente. A quantidade de email que o Outlook fará download pode variar. Para obter mais informações, consulte [trabalhar offline no Outlook](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

Para saber mais sobre a migração de transferência, consulte:

- [O que você precisa saber sobre uma migração de substituição de emails](https://docs.microsoft.com/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Executar uma migração de substituição de email para o Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>Migração híbrida mínima

Em uma migração mínima híbrida ou expressa, você move algumas centenas de caixas de correio para a Microsoft 365 dentro de algumas semanas. Este método não oferece suporte a recursos de migração híbrida avançados, como informações de calendário de disponibilidade compartilhadas.

A migração híbrida mínima é excelente para as organizações que precisam levar mais tempo para migrar suas caixas de correio para a Microsoft 365, mas ainda planeja concluir a migração dentro de algumas semanas. Você obtém alguns dos benefícios da *migração completa e híbrida* mais avançada sem muita complexidade. Você pode controlar quantas e quais caixas de correio serão migradas em um determinado momento. As caixas de correio do Microsoft 365 serão criadas com os nomes de usuário e senhas das contas locais. E, diferentemente das migrações de substituição, os usuários não precisam recriar os perfis do Outlook.

Aqui estão algumas coisas a considerar sobre a migração híbrida mínima:

- Você precisará fazer uma sincronização de diretório única entre seus servidores do Active Directory local e o Microsoft 365.
- Os usuários poderão entrar em sua caixa de correio do Microsoft 365 com o mesmo nome de usuário e senha que antes da caixa de correio.
- Você precisará de uma licença do Microsoft 365 que inclua o Exchange Online para cada caixa de correio de usuário que você migrar.
- Os usuários não precisarão configurar um novo perfil do Outlook na maioria dos dispositivos, embora alguns telefones Android antigos precisem de um novo perfil. Os usuários não precisarão baixar novamente seus emails.

Para obter mais informações, consulte [usar o mínimo híbrido para migrar rapidamente as caixas de correio do Exchange para o Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate).

### <a name="full-hybrid"></a>Híbrido completo

Em uma migração híbrida completa, você tem muitas centenas, até dezenas de milhares, de caixas de correio e move algumas ou todas para o Microsoft 365. Como essas migrações são geralmente de longo prazo, as migrações híbridas tornam possível:

- Mostrar usuários locais as informações de calendário de disponibilidade para usuários no Microsoft 365 e vice-versa.
- Veja uma lista de endereços global unificada que contém destinatários no local e no Microsoft 365.
- Exibir Propriedades completas de destinatários do Outlook para todos os usuários, independentemente de eles estarem no local ou no Microsoft 365.
- Comunicação segura de email entre servidores locais do Exchange e o Office 365 usando TLS e certificados.
- Tratar mensagens enviadas entre os servidores locais do Exchange e o Microsoft 365 como interno, permitindo que eles:
  - Ser avaliado e processado corretamente por agentes de conformidade e transporte direcionados a mensagens internas.
  - Ignorar filtros antispam.

As migrações híbridas completas são melhores para as organizações que esperam permanecer em uma configuração híbrida por muitos meses ou mais. Você Obtém os recursos listados anteriormente nesta seção, além de sincronização de diretório, melhores recursos de conformidade integrados e a capacidade de mover caixas de correio de e para a Microsoft 365 usando movimentações de caixa de correio online. O Microsoft 365 se torna uma extensão de sua organização local.

Aspectos a serem considerados sobre a migração híbrida completa:

- Eles não são adequados para todas as organizações. Devido à complexidade de migrações híbridas completas, as organizações com menos de algumas cem caixas de correio não costumam ver benefícios que justificam o esforço e o custo envolvido. Nesses casos, recomendamos que você considere a substituição ou a migração híbrida mínima.
- Você precisa configurar a sincronização de diretório usando o Azure Active Directory (Azure AD) se conectar entre seus servidores do Active Directory local e o Microsoft 365.
- Os usuários poderão entrar em sua caixa de correio do Microsoft 365 com o mesmo nome de usuário e senha que eles usam ao entrar na rede local. (Essa funcionalidade requer o Azure AD Connect com sincronização de senha e/ou serviços de Federação do Active Directory).
- Você precisa de uma licença do Microsoft 365 que inclua o Exchange Online para cada caixa de correio de usuário que você migrar.
- Os usuários não precisam configurar um novo perfil do Outlook na maioria dos seus dispositivos, embora alguns telefones Android antigos precisem de um novo perfil. Os usuários não precisarão baixar novamente seus emails.

> [!IMPORTANT]
> Se sua organização optar por migrar as caixas de correio para a Microsoft 365, mas planeja manter o DirSync ou o Azure AD Connect in-loco para continuar Gerenciando contas de usuário do Active Directory local, você precisará manter pelo menos um servidor Exchange local. Se todos os servidores do Exchange forem removidos, você não poderá fazer alterações nos destinatários do Exchange no Exchange Online. Isso ocorre porque a fonte de autoridade permanece no Active Directory local e as alterações precisam ser feitas ali.

Se uma migração híbrida completa for adequada para você, consulte os seguintes recursos úteis:

- [Assistente de implantação do Exchange](https://aka.ms/exdeploy)
- [Implantações Híbridas do Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid)
- [Assistente de Configuração Híbrida](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)
- [Perguntas frequentes do Assistente de Configuração Híbrida](https://docs.microsoft.com/exchange/hybrid-configuration-wizard-faqs)
- [Pré-requisitos de implantação híbrida](https://docs.microsoft.com/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Atualizar para uma versão mais recente do Exchange Server local

Acreditamos que você obtém o melhor valor e a experiência do usuário migrando totalmente para o Microsoft 365. Mas entendemos que algumas organizações precisam manter alguns servidores do Exchange locais. Isso pode ser devido a requisitos normativos, para garantir que os dados não sejam armazenados em um datacenter externo, porque você tem configurações ou requisitos exclusivos que não podem ser atendidos na nuvem ou porque você precisa do Exchange para gerenciar caixas de correio na nuvem porque você ainda usa o Active Directory no local. Em qualquer caso, se você mantiver o Exchange no local, verifique se o seu ambiente do Exchange 2010 foi atualizado para pelo menos o Exchange 2013 ou o Exchange 2016.

Para obter a melhor experiência, recomendamos que você atualize seu ambiente local restante para o Exchange 2016. Você não precisa instalar o Exchange Server 2013 se quiser ir diretamente do Exchange Server 2010 para o Exchange Server 2016.

O Exchange 2016 inclui todos os recursos de versões anteriores do Exchange. Ele atende melhor à experiência disponível com o Microsoft 365, embora alguns recursos estejam disponíveis somente no Microsoft 365. Confira apenas algumas das coisas que você esteve perdendo:

|Versão do Exchange|Recursos|
|---|---|
|**Exchange 2013**|A arquitetura simplificada reduz o número de funções de servidor para três (caixa de correio, acesso para cliente, transporte de borda)|
||Políticas de prevenção contra perda de dados (DLP) que ajudam a manter informações confidenciais contra vazamento|
||Experiência aprimorada do Outlook Web App|
|**Exchange 2016**|*Recursos do Exchange 2013 e...*|
||Funções de servidor simplificadas para apenas o transporte de borda e caixa de correio|
||DLP aprimorado junto com a integração com o SharePoint|
||Resiliência de banco de dados aprimorada|
||Colaboração de documentos online|

|Considerações|Mais informações|
|---|---|
|Datas de fim de suporte|Como o Exchange 2010, cada versão do Exchange tem sua própria data de fim de suporte:<br/><br/>Exchange 2013-abril de 2023<br/>Exchange 2016-outubro de 2025<br/><br/>Antes da data de fim de suporte, mais cedo você precisará executar outra migração. Abril de 2023 é muito mais próximo do que você imagina!|
|Caminho de migração para o Exchange 2013 ou 2016|O caminho de migração do Exchange 2010 para uma versão mais recente é o mesmo se você escolher o Exchange 2013 ou o Exchange 2016:<br/><br/>Instale o Exchange 2013 ou 2016 em sua organização existente do Exchange 2010.<br/>Mover serviços e outra infraestrutura para o Exchange 2013 ou 2016.<br/>Mover caixas de correio e pastas públicas para o Exchange 2013 ou 2016 encerrar os servidores do Exchange 2010.|
|Coexistência de versões|Ao migrar para o Exchange 2013 ou o Exchange 2016, você pode instalar a versão em uma organização existente do Exchange 2010. Isso permite que você instale um ou mais servidores do Exchange 2013 ou do Exchange 2016 e faça sua migração.|
|Hardware de servidor|Os requisitos de hardware do servidor foram alterados do Exchange 2010. Verifique se o hardware é compatível. Saiba mais sobre os requisitos de hardware para cada versão aqui:<br/><br/>[Requisitos de sistema do Exchange 2016](https://docs.microsoft.com/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016)<br/>[Requisitos de sistema do Exchange 2013](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)<br/><br/>Com os aprimoramentos significativos no desempenho do Exchange e a capacidade de computação e de armazenamento aumentada em servidores mais recentes, provavelmente você precisará de menos servidores para suportar o mesmo número de caixas de correio.|
|Versão do sistema operacional|As versões mínimas de sistema operacional com suporte para cada versão são:<br/><br/>Exchange 2016-Windows Server 2012<br/>Exchange 2013-Windows Server 2008 R2 SP1<br/><br/>Você pode encontrar mais informações sobre o suporte do sistema operacional na [matriz de suporte do Exchange](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).|
|Nível funcional da floresta do Active Directory|Os níveis mínimos funcionais de floresta do Active Directory com suporte para cada versão são:<br/><br/>Exchange 2016-Windows Server 2008 R2 SP1<br/>Exchange 2013-Windows Server 2003<br/><br/>Você pode encontrar mais informações sobre o suporte de nível funcional da floresta na [matriz de suporte do Exchange](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).|
|Versões de cliente do Office|As versões mínimas compatíveis do cliente do Office para cada versão são:<br/><br/>Exchange 2016-Office 2010 (com as atualizações mais recentes)<br/>Exchange 2013-Office 2007 SP3<br/><br/>Encontre mais informações sobre o suporte do cliente do Office na [matriz de suporte do Exchange](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).||| 


Use os seguintes recursos para ajudá-lo com a migração:

- [Assistente de implantação do Exchange](https://aka.ms/exdeploy)
- Alterações de esquema do Active Directory para o Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- Requisitos do sistema para o Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/system-requirements?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)
- Pré-requisitos para o Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/prerequisites?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Resumo das opções de cliente e servidores do Office 2010 e do Windows 7

Para obter um resumo visual das opções de atualização, migração e mover para nuvem para clientes e servidores do Office 2010 e Windows 7, confira o [pôster sobre o fim do suporte](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Fim do suporte para clientes e servidores do Office 2010 e pôster do Windows 7](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Este cartaz de uma página ilustra os vários caminhos que você pode tomar para responder aos produtos de servidor e cliente do Office 2010 e o Windows 7 alcançando o fim do suporte, com caminhos preferidos e suporte a opções no Microsoft 365 Enterprise realçado.

Você também pode [baixar](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) este cartaz e imprimi-lo no formato carta, legal ou tablóide (11 x 17).

## <a name="what-if-i-need-help"></a>E se eu precisar de ajuda?

Se você estiver migrando para o Microsoft 365, poderá estar qualificado para usar nosso serviço Microsoft FastTrack. O FastTrack oferece práticas recomendadas, ferramentas e recursos para tornar sua migração para a Microsoft 365 o mais simples possível. Melhor de tudo, você terá um engenheiro de suporte para orientá-lo no planejamento e design para migrar sua última caixa de correio. Para saber mais sobre o FastTrack, confira [Microsoft FastTrack](https://fasttrack.microsoft.com/).

Se você tiver problemas durante a migração para o Microsoft 365 e não estiver usando o FastTrack ou estiver migrando para uma versão mais recente do Exchange Server, aqui estão alguns recursos que podem ser usados:

- [Comunidade técnica](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Suporte ao cliente](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>Artigos relacionados

[Recursos para ajudá-lo a atualizar clientes e servidores do Office 2010](upgrade-from-office-2010-servers-and-products.md)
