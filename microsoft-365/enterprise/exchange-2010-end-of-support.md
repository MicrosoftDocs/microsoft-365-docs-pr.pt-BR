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
description: Exchange 2010 chegou ao fim do suporte. Use este roteiro de planejamento para se preparar para atualizar para Exchange Online ou uma versão mais recente do Exchange Server local.
ms.openlocfilehash: f3531802283368e533ba6646415d4acc019687bd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926989"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Roteiro do encerramento de suporte do Exchange 2010

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Exchange Server 2010 atingiu seu fim de suporte em 13 de outubro de **2020**. Se você ainda não iniciou sua migração do Exchange 2010 para Microsoft 365, Office 365 ou Exchange 2016, agora é a hora de começar a planejar.

## <a name="what-does-end-of-support-mean"></a>O que *significa o fim do suporte?*

A maioria dos produtos Microsoft tem um ciclo de vida de suporte durante o qual eles têm novos recursos, correções de bugs, correções de segurança e assim por diante. Esse ciclo de vida geralmente dura 10 anos a partir da versão inicial do produto. O final desse ciclo de vida é conhecido como o fim do suporte do produto. Como Exchange 2010 atingiu o fim do suporte em 13 de outubro de 2020, a Microsoft não fornece mais:

- Suporte técnico para problemas que podem ocorrer.
- Correções de bugs para problemas que podem afetar a estabilidade e a usabilidade do servidor.
- Correções de segurança para vulnerabilidades que podem tornar o servidor vulnerável a violações de segurança.
- Atualizações de fuso horário.

Sua instalação do Exchange 2010 continuará sendo executado após essa data. Porém, devido às alterações listadas acima, recomendamos que você migre do Exchange 2010 assim que possível.

Para obter mais informações sobre como chegar ao fim do suporte, consulte Recursos para ajudá-lo a atualizar de Office [2010 servidores e clientes](upgrade-from-office-2010-servers-and-products.md).

## <a name="what-are-my-options"></a>Quais são minhas opções?

É uma ótima hora para explorar suas opções e preparar um plano de migração. Você pode:

- Migre totalmente para Microsoft 365. Migre caixas de correio usando transferência, migração híbrida mínima ou híbrida completa. Em seguida, remova os servidores Exchange locais e o Active Directory.
- Migre seus servidores Exchange 2010 para Exchange 2016 em seus servidores locais.

> [!IMPORTANT]
> Se sua organização optar por migrar caixas de correio para o Microsoft 365, mas planeja manter o DirSync ou o Azure AD Conexão no local para continuar a gerenciar contas de usuário do Active Directory local, você precisará manter pelo menos um servidor do Microsoft Exchange local. Se você remover todos os servidores Exchange, não poderá fazer alterações nos destinatários Exchange no Exchange Online porque a fonte de autoridade permanece no Active Directory local. As alterações precisam ser feitas lá. Neste cenário, você tem as seguintes opções:
>
>- *Recomendado:* Se você migrou suas caixas de correio para Microsoft 365 e atualizou seus servidores até 13 de outubro de 2020, use o Exchange 2010 para se conectar ao Microsoft 365 e migrar caixas de correio. Em seguida, migre Exchange 2010 para Exchange 2016 e desative todos os servidores Exchange 2010 restantes.
>- Se você não concluiu a migração de caixa de correio e a atualização do servidor local até 13 de outubro de 2020, atualize seus servidores locais do Exchange 2010 para Exchange 2016 primeiro. Em seguida, Exchange 2016 para se conectar Microsoft 365 e migrar caixas de correio.

> [!NOTE]
> É um pouco mais complicado, mas você também pode migrar caixas de correio para Microsoft 365 enquanto migra seus servidores locais Exchange 2010 para Exchange 2016.

Aqui estão os três caminhos que você pode seguir para evitar o fim do suporte para Exchange Server 2010.

![Exchange Server de atualização 2010](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

As seções a seguir exploram cada opção com mais detalhes.

## <a name="migrate-to-microsoft-365"></a>Migrar para o Microsoft 365

Migrar seu email para Microsoft 365 é a melhor e mais simples opção para ajudá-lo a retirar sua implantação Exchange 2010. Com uma migração para Microsoft 365, você pode fazer um salto único da tecnologia antiga para os recursos atuais, incluindo:

- Recursos de conformidade, como Políticas de Retenção, In-Place e Retenção de Litígio, Descoberta eDiscovery in-loco e muito mais.
- Microsoft Teams.
- Power BI.
- Caixa de Entrada Focalizada.
- MyAnalytics.

Microsoft 365 também obtém novos recursos e experiências primeiro, para que sua organização possa começar a usá-los imediatamente. Além disso, você não precisa se preocupar com:

- Compra e manutenção de hardware.
- Pagar para aqueça e esfrie seus servidores.
- Mantendo-se atualizado sobre correções de segurança, produto e fuso horário.
- Manutenção de armazenamento e software para dar suporte aos requisitos de conformidade.
- Atualizando para uma nova versão do Exchange. Você está sempre na versão mais recente do Exchange no Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>Como migrar para Microsoft 365?

Dependendo da sua organização, você tem algumas opções para Microsoft 365. Primeiro, você precisa considerar algumas coisas, como:
- O número de bancos ou caixas de correio que você precisa mover.
- Quanto tempo você deseja que a migração durar.
- Se você precisa de uma integração perfeita entre sua instalação local e Microsoft 365 durante a migração.
 
Esta tabela mostra suas opções de migração e os fatores mais importantes que determinam qual método usar.

|Opção de migração|Tamanho da organização|Duration|
|---|---|---|
|Migração de substituição|Menos de 150 lugares|Uma semana ou menos|
|Migração híbrida mínima|Menos de 150 lugares|Algumas semanas ou menos|
|Migração híbrida completa|Mais de 150 lugares|Algumas semanas ou mais|

As seções a seguir dão uma visão geral desses métodos. Para obter mais informações, [consulte Decidir sobre um caminho de migração](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27).

### <a name="cutover-migration"></a>Migração de substituição

Em uma migração de recortamento, você migra todas as suas caixas de correio, grupos de distribuição, contatos e assim por diante, para Office 365 em uma data e hora definidas. Quando terminar, desligue seus servidores Exchange locais e comece a usar Microsoft 365 exclusivamente.

A migração de recortamento é ótima para pequenas organizações que não têm muitas caixas de correio, querem chegar Microsoft 365 rapidamente e não querem lidar com a complexidade dos outros métodos. Mas ele deve ser concluído em uma semana ou menos. E exige que os usuários reconfigurem seus perfis Outlook de usuário. A migração de recortamento pode migrar até 2.000 caixas de correio, mas recomendamos que você a use no máximo 150. Se você tentar migrar mais, poderá ficar sem tempo para transferir todas as caixas de correio antes do prazo, e sua equipe de suporte de TI pode ficar sobrecarregada com solicitações para ajudar os usuários a reconfigurar Outlook.

Aqui estão as coisas a considerar sobre a migração de recortamento:

- Microsoft 365 precisar se conectar aos servidores Exchange 2010 usando o Outlook em Qualquer Lugar sobre a porta TCP 443.
- Todas as caixas de correio locais serão movidas para Microsoft 365.
- Você precisará de uma conta de administrador local que tenha acesso de leitura às caixas de correio de seus usuários.
- Os Exchange 2010 aceitos que você deseja usar no Microsoft 365 precisam ser adicionados como domínios verificados no serviço.
- Entre quando você iniciar a migração e quando começar a fase de conclusão, Microsoft 365 sincronizar periodicamente as caixas de correio Microsoft 365 e locais. Isso permite que você conclua a migração sem se preocupar com o email que está sendo deixado para trás em suas caixas de correio locais.
- Os usuários receberão novas senhas temporárias para sua Microsoft 365 conta. Eles precisarão alterá-los quando entrar em suas caixas de correio pela primeira vez.
- Você precisará de uma licença Microsoft 365 que inclua Exchange Online para cada caixa de correio de usuário que você migrar.
- Os usuários precisarão configurar um novo perfil de Outlook em cada um de seus dispositivos e baixar seus emails novamente. A quantidade de emails que Outlook baixar pode variar. Para obter mais informações, consulte [Trabalhar offline em Outlook](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

Para saber mais sobre a migração de recortamento, consulte:

- [O que você precisa saber sobre uma migração de email de recortamento](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Executar uma migração de recortamento de email para Office 365](/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>Migração híbrida mínima

Em uma migração híbrida ou expressa mínima, você move algumas centenas de caixas de correio para Microsoft 365 em algumas semanas. Esse método não oferece suporte a recursos avançados de migração híbrida, como informações compartilhadas de calendário livre/ocupado.

A migração híbrida mínima é ótima para organizações que precisam levar mais tempo para migrar suas caixas de correio para Microsoft 365, mas ainda planejam concluir a migração em algumas semanas. Você tem alguns dos benefícios da migração híbrida completa mais *avançada* sem grande parte da complexidade. Você pode controlar quantas caixas de correio e quais caixas de correio migrar em um determinado momento. Microsoft 365 caixas de correio serão criadas com os nomes de usuário e senhas das contas locais. E, ao contrário das migrações de recortamento, os usuários não têm que recriar seus perfis Outlook de recortar.

Aqui estão as coisas a considerar sobre a migração híbrida mínima:

- Você precisará fazer uma sincronização de diretório única entre seus servidores do Active Directory local e Microsoft 365.
- Os usuários poderão entrar na caixa de correio Microsoft 365 com o mesmo nome de usuário e senha que antes da caixa de correio.
- Você precisará de uma licença Microsoft 365 que inclua Exchange Online para cada caixa de correio de usuário que você migrar.
- Os usuários não precisarão configurar um novo perfil de Outlook na maioria de seus dispositivos, embora alguns telefones Android mais antigos possam precisar de um novo perfil. Os usuários não precisarão recarregar seus emails.

Para obter mais informações, [consulte Use Minimal Hybrid to quickly migrate Exchange mailboxes to Office 365](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate).

### <a name="full-hybrid"></a>Híbrido completo

Em uma migração híbrida completa, você tem muitas centenas, até dezenas de milhares, de caixas de correio e move algumas ou todas para Microsoft 365. Como essas migrações geralmente são de longo prazo, as migrações híbridas possibilitam:

- Mostrar aos usuários locais as informações de calendário de livre/ocupado para os usuários no Microsoft 365 e vice-versa.
- Consulte uma lista de endereços global unificada que contém destinatários no local e Microsoft 365.
- Exibir propriedades Outlook destinatários completos para todos os usuários, independentemente de eles estar no local ou Microsoft 365.
- Proteja a comunicação de email entre servidores Exchange locais e Office 365 usando TLS e certificados.
- Trate as mensagens enviadas entre servidores Exchange locais e Microsoft 365 como internas, permitindo que elas:
  - Ser avaliado corretamente e processado por agentes de transporte e conformidade destinados a mensagens internas.
  - Ignorar filtros anti-spam.

As migrações híbridas completas são melhores para organizações que esperam permanecer em uma configuração híbrida por muitos meses ou mais. Você pode obter os recursos listados anteriormente nesta seção, além de sincronização de diretórios, recursos de conformidade melhor integrados e a capacidade de mover caixas de correio para e de Microsoft 365 usando movimentações de caixa de correio online. Microsoft 365 se torna uma extensão da sua organização local.

Coisas a considerar sobre a migração híbrida completa:

- Eles não são adequados para todas as organizações. Devido à complexidade das migrações híbridas completas, as organizações com menos de algumas centenas de caixas de correio geralmente não veem benefícios que justifiquem o esforço e o custo envolvidos. Nesses casos, recomendamos que você considere a substituição ou a migração híbrida mínima.
- Você precisa configurar a sincronização de diretório usando o Azure Active Directory (Azure AD) Conexão entre seus servidores do Active Directory local e Microsoft 365.
- Os usuários poderão entrar na caixa de correio Microsoft 365 com o mesmo nome de usuário e senha que usam ao entrar na rede local. (Essa funcionalidade requer o Azure AD Conexão com sincronização de senha e/ou Serviços de Federação do Active Directory).
- Você precisa de uma Microsoft 365 que inclua Exchange Online para cada caixa de correio de usuário que você migrar.
- Os usuários não precisam configurar um novo perfil de Outlook na maioria de seus dispositivos, embora alguns telefones Android mais antigos possam precisar de um novo perfil. Os usuários não precisarão recarregar seus emails.

> [!IMPORTANT]
> Se sua organização optar por migrar caixas de correio para o Microsoft 365, mas planeja manter o DirSync ou o Azure AD Conexão no local para continuar a gerenciar contas de usuário do Active Directory local, você precisará manter pelo menos um servidor Exchange local. Se todos Exchange servidores foram removidos, você não poderá fazer alterações em Exchange destinatários no Exchange Online. Isso porque a fonte de autoridade permanece no Active Directory local e as alterações precisam ser feitas lá.

Se uma migração híbrida completa parecer correta para você, consulte os seguintes recursos úteis:

- [Exchange Assistente de Implantação](/exchange/exchange-deployment-assistant)
- [Implantações híbridas do Exchange Server](/exchange/exchange-hybrid)
- [Assistente de Configuração Híbrida](/exchange/hybrid-configuration-wizard)
- [Perguntas frequentes do Assistente de Configuração Híbrida](/exchange/hybrid-configuration-wizard-faqs)
- [Pré-requisitos de implantação híbrida](/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Atualizar para uma versão mais recente do Exchange Server local

Acreditamos fortemente que você tenha o melhor valor e experiência do usuário migrando totalmente para Microsoft 365. Mas entendemos que algumas organizações precisam manter alguns servidores Exchange locais. Isso pode ser devido aos requisitos regulatórios, para garantir que os dados não sejam armazenados em um datacenter externo, porque você tem configurações ou requisitos exclusivos que não podem ser atendidos na nuvem ou porque você precisa Exchange gerenciar caixas de correio de nuvem porque você ainda usa o Active Directory local. Em qualquer caso, se você manter o Exchange local, certifique-se de que seu ambiente do Exchange 2010 seja atualizado para pelo menos Exchange 2013 ou Exchange 2016.

Para a melhor experiência, recomendamos que você atualize seu ambiente local restante para Exchange 2016. Você não precisa instalar o Exchange Server 2013 se quiser ir direto do Exchange Server 2010 para o Exchange Server 2016.

Exchange 2016 inclui todos os recursos de versões anteriores do Exchange. Ele corresponde mais de perto à experiência disponível com Microsoft 365, embora alguns recursos estão disponíveis apenas em Microsoft 365. Confira apenas algumas das coisas que você está perdendo:

|Exchange versão|Recursos|
|---|---|
|**Exchange 2013**|A arquitetura simplificada reduz o número de funções de servidor para três (Caixa de Correio, Acesso para Cliente, Transporte de Borda)|
||Políticas de prevenção contra perda de dados (DLP) que ajudam a manter informações confidenciais contra vazamentos|
||Experiência Outlook Web App aprimorada|
|**Exchange 2016**|*Recursos do Exchange 2013 e ...*|
||Funções de servidor mais simplificadas apenas para Caixa de Correio e Transporte de Borda|
||DLP aprimorada juntamente com a integração com SharePoint|
||Resiliência de banco de dados aprimorada|
||Colaboração de documentos online|

|Considerações|Mais informações|
|---|---|
|Datas de término do suporte|Como Exchange 2010, cada versão do Exchange tem sua própria data de fim de suporte:<br/><br/>Exchange 2013 - abril de 2023<br/>Exchange 2016 - outubro de 2025<br/><br/>Quanto antes a data de término do suporte, mais cedo você precisará executar outra migração. Abril de 2023 é muito mais próximo do que você pensa!|
|Caminho de migração para Exchange 2013 ou 2016|O caminho de migração Exchange 2010 para uma versão mais recente é o mesmo se você escolher Exchange 2013 ou Exchange 2016:<br/><br/>Instale Exchange 2013 ou 2016 em sua organização Exchange 2010 existente.<br/>Mova serviços e outra infraestrutura para Exchange 2013 ou 2016.<br/>Mova caixas de correio e pastas públicas para Exchange 2013 ou 2016 Desativação restante Exchange servidores 2010.|
|Coexistência de versão|Ao migrar para Exchange 2013 ou Exchange 2016, você pode instalar qualquer versão em uma organização Exchange 2010 existente. Isso permite que você instale um ou mais servidores Exchange 2013 ou Exchange 2016 e faça sua migração.|
|Hardware de servidor|Os requisitos de hardware do servidor foram alterados Exchange 2010. Certifique-se de que o hardware seja compatível. Saiba mais sobre os requisitos de hardware para cada versão aqui:<br/><br/>[Requisitos de sistema do Exchange 2016](/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016)<br/>[Requisitos de sistema do Exchange 2013](/Exchange/exchange-2013-system-requirements-exchange-2013-help)<br/><br/>Com as melhorias significativas no Exchange e a maior capacidade de computação e armazenamento em servidores mais novos, você provavelmente precisará de menos servidores para dar suporte ao mesmo número de caixas de correio.|
|Versão do sistema operacional|As versões mínimas do sistema operacional com suporte para cada versão são:<br/><br/>Exchange 2016 - Windows Server 2012<br/>Exchange 2013 - Windows Server 2008 R2 SP1<br/><br/>Você pode encontrar mais informações sobre o suporte ao sistema operacional [em Exchange Supportability Matrix](/exchange/plan-and-deploy/supportability-matrix).|
|Nível funcional da floresta do Active Directory|Os níveis funcionais mínimos de floresta do Active Directory com suporte para cada versão são:<br/><br/>Exchange 2016 - Windows Server 2008 R2 SP1<br/>Exchange 2013 - Windows Server 2003<br/><br/>Você pode encontrar mais informações sobre o suporte ao nível funcional da floresta [Exchange Supportability Matrix](/exchange/plan-and-deploy/supportability-matrix).|
|Office cliente|As versões Office cliente mínimas com suporte para cada versão são:<br/><br/>Exchange 2016 - Office 2010 (com as atualizações mais recentes)<br/>Exchange 2013 - Office 2007 SP3<br/><br/>Encontre mais informações sobre o Office cliente em [Exchange Supportability Matrix.](/exchange/plan-and-deploy/supportability-matrix)||| 


Use os seguintes recursos para ajudar na migração:

- [Exchange Assistente de Implantação](/exchange/exchange-deployment-assistant)
- Alterações de esquema do Active Directory Exchange [2016](/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016), [2013](/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- Requisitos do sistema Exchange [2016](/exchange/plan-and-deploy/system-requirements?view=exchserver-2016), [2013](/Exchange/exchange-2013-system-requirements-exchange-2013-help)
- Pré-requisitos para Exchange [2016](/exchange/plan-and-deploy/prerequisites?view=exchserver-2016), [2013](/Exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Resumo das opções para Office 2010 clientes e servidores e Windows 7

Para obter um resumo visual das opções de atualização, migração e mover para nuvem para clientes e servidores do Office 2010 e Windows 7, confira o [pôster sobre o fim do suporte](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Fim do suporte para clientes e servidores Office 2010 e Windows cartaz 7](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Este cartaz de uma página ilustra os vários caminhos que você pode seguir para responder aos produtos de cliente e servidor do Office 2010 e Windows 7 chegando ao fim do suporte, com caminhos preferenciais e suporte a opções Microsoft 365 Enterprise realçadas.

Você também pode [baixar](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) esse cartaz e imprimi-lo em formato de carta, legal ou tablóide (11 x 17).

## <a name="what-if-i-need-help"></a>E se eu precisar de ajuda?

Se você estiver migrando para Microsoft 365, talvez esteja qualificado para usar nosso serviço Do Microsoft FastTrack. O FastTrack fornece práticas recomendadas, ferramentas e recursos para tornar sua migração Microsoft 365 o mais perfeita possível. O melhor de tudo é que você terá um engenheiro de suporte que o explica desde o planejamento e o design até a migração da última caixa de correio. Para saber mais sobre o FastTrack, consulte [Microsoft FastTrack](https://fasttrack.microsoft.com/).

Se você tiver problemas durante a migração para Microsoft 365 e não estiver usando o FastTrack ou estiver migrando para uma versão mais recente do Exchange Server, veja alguns recursos que você pode usar:

- [Comunidade técnica](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Suporte ao cliente](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>Artigos relacionados

[Recursos para ajudá-lo a atualizar clientes e servidores do Office 2010](upgrade-from-office-2010-servers-and-products.md)