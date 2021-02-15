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
description: O Exchange 2010 atingiu o fim do suporte. Use este mapa de planejamento para preparar a atualização para o Exchange Online ou uma versão mais recente do Exchange Server local.
ms.openlocfilehash: 23384d93c4e65fb25a66ca6f2f0bcbe46b34ee18
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519686"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Roteiro do encerramento de suporte do Exchange 2010

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O Exchange Server 2010 atingiu o fim do suporte em **13 de outubro de 2020.** Se você ainda não começou sua migração do Exchange 2010 para o Microsoft 365, Office 365 ou Exchange 2016, agora é a hora de começar a planejar.

## <a name="what-does-end-of-support-mean"></a>O que *significa o fim do suporte?*

A maioria dos produtos da Microsoft tem um ciclo de vida de suporte durante o qual eles têm novos recursos, correções de bugs, correções de segurança e assim por diante. Esse ciclo de vida geralmente dura 10 anos a partir do lançamento inicial do produto. O fim desse ciclo de vida é conhecido como o fim do suporte do produto. Como o Exchange 2010 atingiu o fim do suporte em 13 de outubro de 2020, a Microsoft não oferece mais:

- Suporte técnico para problemas que podem ocorrer.
- Correções de bugs para problemas que podem afetar a estabilidade e a usabilidade do servidor.
- Correções de segurança para vulnerabilidades que podem tornar o servidor vulnerável a violações de segurança.
- Atualizações de fuso horário.

Sua instalação do Exchange 2010 continuará a ser executado após essa data. Porém, devido às alterações listadas acima, recomendamos que você migre do Exchange 2010 assim que possível.

Para obter mais informações sobre como se aproximar do fim do suporte, consulte Recursos para ajudá-lo a atualizar de servidores e clientes do [Office 2010.](upgrade-from-office-2010-servers-and-products.md)

## <a name="what-are-my-options"></a>Quais são as minhas opções?

É um ótimo momento para explorar suas opções e preparar um plano de migração. Você pode:

- Migre totalmente para o Microsoft 365. Migrar caixas de correio usando migração híbrida mínima ou híbrida completa. Em seguida, remova os servidores locais do Exchange e o Active Directory.
- Migre seus servidores do Exchange 2010 para o Exchange 2016 em seus servidores locais.

> [!IMPORTANT]
> Se sua organização optar por migrar caixas de correio para o Microsoft 365, mas planeja manter o DirSync ou o Azure AD Connect no local para continuar a gerenciar contas de usuário do Active Directory local, você precisa manter pelo menos um servidor do Microsoft Exchange no local. Se você remover todos os servidores do Exchange, não poderá fazer alterações nos destinatários do Exchange no Exchange Online porque a fonte de autoridade permanece em seu Active Directory local. As alterações precisam ser feitas lá. Neste cenário, você tem as seguintes opções:
>
>- *Recomendado:* Se você migrou suas caixas de correio para o Microsoft 365 e atualizou seus servidores até 13 de outubro de 2020, use o Exchange 2010 para se conectar ao Microsoft 365 e migrar caixas de correio. Em seguida, migre o Exchange 2010 para o Exchange 2016 e descomissione todos os servidores restantes do Exchange 2010.
>- Se você não concluiu a migração de caixa de correio e a atualização do servidor local até 13 de outubro de 2020, atualize primeiro os servidores locais do Exchange 2010 para o Exchange 2016. Em seguida, use o Exchange 2016 para se conectar ao Microsoft 365 e migrar caixas de correio.

> [!NOTE]
> É um pouco mais complicado, mas você também pode migrar caixas de correio para o Microsoft 365 enquanto migra seus servidores locais do Exchange 2010 para o Exchange 2016.

Aqui estão os três caminhos que você pode seguir para evitar o fim do suporte para o Exchange Server 2010.

![Caminhos de atualização do Exchange Server 2010](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

As seções a seguir exploram cada opção com mais detalhes.

## <a name="migrate-to-microsoft-365"></a>Migrar para o Microsoft 365

Migrar seu email para o Microsoft 365 é a melhor e mais simples opção para ajudá-lo a retirar sua implantação do Exchange 2010. Com uma migração para o Microsoft 365, você pode fazer um único salto da tecnologia antiga para os recursos atuais, incluindo:

- Recursos de conformidade, como Políticas de retenção, In-Place retenção e retenção de litígio, Descoberta eDiscovery in-loco e muito mais.
- Microsoft Teams.
- Power BI.
- Caixa de Entrada Focada.
- MyAnalytics.

O Microsoft 365 também obtém novos recursos e experiências primeiro, para que sua organização possa começar a usá-los imediatamente. Além disso, você não precisa se preocupar com:

- Compra e manutenção de hardware.
- Pagar para manter seus servidores com temperatura e frio.
- Mantenha-se atualizado sobre correções de segurança, produto e fuso horário.
- Manutenção de armazenamento e software para dar suporte aos requisitos de conformidade.
- Atualizando para uma nova versão do Exchange. Você está sempre na versão mais recente do Exchange no Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>Como migrar para o Microsoft 365?

Dependendo da sua organização, você tem algumas opções para chegar ao Microsoft 365. Primeiro, você precisa considerar algumas coisas, como:
- O número de usuários ou caixas de correio que você precisa mover.
- Quanto tempo você deseja que a migração dura.
- Se você precisa de uma integração perfeita entre sua instalação local e o Microsoft 365 durante a migração.
 
Esta tabela mostra as opções de migração e os fatores mais importantes que determinam qual método usar.

|Opção de migração|Tamanho da organização|Duration|
|---|---|---|
|Migração de substituição|Menos de 150 assentos|Uma semana ou menos|
|Migração híbrida mínima|Menos de 150 assentos|Algumas semanas ou menos|
|Migração híbrida completa|Mais de 150 assentos|Algumas semanas ou mais|

As seções a seguir dão uma visão geral desses métodos. Para obter mais informações, consulte [Decidir sobre um caminho de migração.](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27)

### <a name="cutover-migration"></a>Migração de substituição

Em uma migração de recortar, você migra todas as suas caixas de correio, grupos de distribuição, contatos e assim por diante, para o Office 365 em uma data e hora definidas. Quando terminar, desligue seus servidores locais do Exchange e comece a usar o Microsoft 365 exclusivamente.

A migração de recortar é ótima para pequenas organizações que não têm muitas caixas de correio, querem chegar ao Microsoft 365 rapidamente e não querem lidar com a complexidade dos outros métodos. Mas ele deve ser concluído em uma semana ou menos. E exige que os usuários reconfigurem seus perfis do Outlook. A migração de recortar pode migrar até 2.000 caixas de correio, mas recomendamos que você a use no máximo 150. Se você tentar migrar mais, poderá ficar sem tempo para transferir todas as caixas de correio antes da data limite, e sua equipe de suporte de TI pode ficar sobrecarregada com solicitações para ajudar os usuários a reconfigurar o Outlook.

Aqui estão as coisas a considerar sobre a migração de recortar:

- O Microsoft 365 precisará se conectar aos servidores do Exchange 2010 usando o Outlook em Qualquer Lugar em vez da porta TCP 443.
- Todas as caixas de correio locais serão movidas para o Microsoft 365.
- Você precisará de uma conta de administrador local que tenha acesso de leitura às caixas de correio dos usuários.
- Os domínios aceitos do Exchange 2010 que você deseja usar no Microsoft 365 precisam ser adicionados como domínios verificados no serviço.
- Entre o início da migração e o início da fase de conclusão, o Microsoft 365 sincroniza periodicamente as caixas de correio do Microsoft 365 e as caixas de correio locais. Isso permite concluir a migração sem se preocupar com o email deixado para trás em suas caixas de correio locais.
- Os usuários receberão novas senhas temporárias para sua conta do Microsoft 365. Eles precisarão alterá-los quando entrar em suas caixas de correio pela primeira vez.
- Você precisará de uma licença do Microsoft 365 que inclua o Exchange Online para cada caixa de correio de usuário migrada.
- Os usuários precisarão configurar um novo perfil do Outlook em cada um de seus dispositivos e baixar seus emails novamente. A quantidade de email que o Outlook baixará pode variar. Para saber mais, confira [Trabalhar offline no Outlook.](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633)

Para saber mais sobre migração de corte, confira:

- [O que você precisa saber sobre uma migração de email de recorte](https://docs.microsoft.com/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Executar uma migração de recortar emails para o Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>Migração híbrida mínima

Em uma migração híbrida ou expressa mínima, você move algumas centenas de caixas de correio para o Microsoft 365 dentro de algumas semanas. Esse método não dá suporte a recursos avançados de migração híbrida, como informações de calendário de livre/ocupado compartilhado.

A migração híbrida mínima é ótima para organizações que precisam de mais tempo para migrar suas caixas de correio para o Microsoft 365, mas ainda planejam concluir a migração em algumas semanas. Você pode obter alguns dos benefícios da migração *híbrida completa* mais avançada sem grande parte da complexidade. Você pode controlar quantas e quais caixas de correio migrar em um determinado momento. As caixas de correio do Microsoft 365 serão criadas com os nomes de usuário e senhas das contas locais. E, ao contrário das migrações de recorte, os usuários não têm que recriar seus perfis do Outlook.

Aqui estão as coisas a considerar sobre migração híbrida mínima:

- Você precisará fazer uma sincronização de diretório única entre seus servidores locais do Active Directory e o Microsoft 365.
- Os usuários poderão entrar em suas caixas de correio do Microsoft 365 com o mesmo nome de usuário e senha de antes de suas caixas de correio.
- Você precisará de uma licença do Microsoft 365 que inclua o Exchange Online para cada caixa de correio de usuário que você migrar.
- Os usuários não precisarão configurar um novo perfil do Outlook na maioria dos dispositivos, embora alguns telefones Android mais antigos possam precisar de um novo perfil. Os usuários não precisarão recarregar seus emails.

Para obter mais informações, consulte Usar Híbrido Mínimo para migrar rapidamente caixas de [correio do Exchange para o Office 365.](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)

### <a name="full-hybrid"></a>Híbrido completo

Em uma migração híbrida completa, você tem centenas, até dezenas de milhares, de caixas de correio e move algumas ou todas para o Microsoft 365. Como essas migrações geralmente são de longo prazo, as migrações híbridas possibilitam:

- Mostre aos usuários locais as informações do calendário de livre/ocupado para os usuários no Microsoft 365 e vice-versa.
- Veja uma lista de endereços global unificada que contém destinatários no local e no Microsoft 365.
- Exibir propriedades completas de destinatário do Outlook para todos os usuários, independentemente de eles estar no local ou no Microsoft 365.
- Proteja a comunicação de email entre servidores locais do Exchange e o Office 365 usando TLS e certificados.
- Trate as mensagens enviadas entre servidores locais do Exchange e o Microsoft 365 como internas, permitindo que elas:
  - Ser avaliado corretamente e processado por agentes de transporte e conformidade direcionando mensagens internas.
  - Ignorar filtros anti-spam.

Migrações híbridas completas são melhores para organizações que esperam permanecer em uma configuração híbrida por muitos meses ou mais. Você pode obter os recursos listados anteriormente nesta seção, além da sincronização de diretórios, recursos de conformidade melhor integrados e a capacidade de mover caixas de correio para e do Microsoft 365 usando movimentações de caixa de correio online. O Microsoft 365 se torna uma extensão da sua organização local.

Considerações sobre a migração híbrida completa:

- Eles não são adequados para todas as organizações. Devido à complexidade das migrações híbridas completas, as organizações com menos de algumas centenas de caixas de correio normalmente não veem benefícios que justificam o esforço e o custo envolvidos. Nesses casos, recomendamos que você considere a migração híbrida de substituição ou mínima.
- Você precisa configurar a sincronização de diretório usando o Azure Active Directory (Azure AD) Connect entre seus servidores locais do Active Directory e o Microsoft 365.
- Os usuários poderão entrar na caixa de correio do Microsoft 365 com o mesmo nome de usuário e senha que usam ao entrar na rede local. (Essa funcionalidade requer o Azure AD Connect com sincronização de senha e/ou Serviços de Federação do Active Directory).
- Você precisa de uma licença do Microsoft 365 que inclua o Exchange Online para cada caixa de correio de usuário migrada.
- Os usuários não precisam configurar um novo perfil do Outlook na maioria dos dispositivos, embora alguns telefones Android mais antigos possam precisar de um novo perfil. Os usuários não precisarão recarregar seus emails.

> [!IMPORTANT]
> Se sua organização optar por migrar caixas de correio para o Microsoft 365, mas planeja manter o DirSync ou o Azure AD Connect no local para continuar a gerenciar contas de usuário do Active Directory local, você precisa manter pelo menos um servidor Exchange local. Se todos os servidores do Exchange são removidos, você não poderá fazer alterações nos destinatários do Exchange no Exchange Online. Isso porque a fonte de autoridade permanece em seu Active Directory local e as alterações precisam ser feitas lá.

Se uma migração híbrida completa parecer correta para você, consulte os seguintes recursos úteis:

- [Assistente de Implantação do Exchange](https://aka.ms/exdeploy)
- [Implantações Híbridas do Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid)
- [Assistente de Configuração Híbrida](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)
- [Perguntas frequentes do Assistente de Configuração Híbrida](https://docs.microsoft.com/exchange/hybrid-configuration-wizard-faqs)
- [Pré-requisitos de implantação híbrida](https://docs.microsoft.com/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Atualizar para uma versão mais recente do Exchange Server local

Acreditamos que você tem o melhor valor e experiência do usuário migrando totalmente para o Microsoft 365. Mas entendemos que algumas organizações precisam manter alguns Servidores do Exchange no local. Isso pode ser devido a requisitos regulatórios, para garantir que os dados não sejam armazenados em um datacenter externo, porque você tem configurações ou requisitos exclusivos que não podem ser atendidos na nuvem ou porque precisa do Exchange para gerenciar caixas de correio na nuvem porque você ainda usa o Active Directory no local. De qualquer forma, se você manter o Exchange no local, deverá garantir que seu ambiente do Exchange 2010 seja atualizado para pelo menos o Exchange 2013 ou o Exchange 2016.

Para a melhor experiência, recomendamos que você atualize seu ambiente local restante para o Exchange 2016. Não é necessário instalar o Exchange Server 2013 se você quiser ir diretamente do Exchange Server 2010 para o Exchange Server 2016.

O Exchange 2016 inclui todos os recursos de versões anteriores do Exchange. Ele corresponde mais de perto à experiência disponível com o Microsoft 365, embora alguns recursos só estão disponíveis no Microsoft 365. Confira apenas algumas das coisas que você está perdendo:

|Versão do Exchange|Recursos|
|---|---|
|**Exchange 2013**|A arquitetura simplificada reduz o número de funções de servidor para três (Caixa de Correio, Acesso para Cliente, Transporte de Borda)|
||Políticas de prevenção contra perda de dados (DLP) que ajudam a evitar vazamento de informações confidenciais|
||Experiência aprimorada do Outlook Web App|
|**Exchange 2016**|*Recursos do Exchange 2013 e ...*|
||Funções de servidor mais simplificadas apenas para Caixa de Correio e Transporte de Borda|
||DLP aprimorada, juntamente com a integração com o SharePoint|
||Resiliência de banco de dados aprimorada|
||Colaboração de documentos online|

|Considerações|Mais informações|
|---|---|
|Datas de término do suporte|Assim como o Exchange 2010, cada versão do Exchange tem sua própria data de fim de suporte:<br/><br/>Exchange 2013 – abril de 2023<br/>Exchange 2016 - outubro de 2025<br/><br/>Quanto antes a data de fim do suporte, mais cedo você precisará executar outra migração. Abril de 2023 está muito mais próximo do que você pensa!|
|Caminho de migração para o Exchange 2013 ou 2016|O caminho de migração do Exchange 2010 para uma versão mais recente é o mesmo se você escolher o Exchange 2013 ou o Exchange 2016:<br/><br/>Instale o Exchange 2013 ou 2016 em sua organização existente do Exchange 2010.<br/>Mova serviços e outra infraestrutura para o Exchange 2013 ou 2016.<br/>Mover caixas de correio e pastas públicas para os servidores restantes do Exchange 2013 ou 2016 Do Exchange 2010.|
|Coexistência de versão|Ao migrar para o Exchange 2013 ou o Exchange 2016, você pode instalar qualquer uma das versões em uma organização existente do Exchange 2010. Isso permite que você instale um ou mais servidores Exchange 2013 ou Exchange 2016 e faça sua migração.|
|Hardware de servidor|Os requisitos de hardware do servidor foram alterados do Exchange 2010. Certifique-se de que seu hardware seja compatível. Saiba mais sobre os requisitos de hardware para cada versão aqui:<br/><br/>[Requisitos de sistema do Exchange 2016](https://docs.microsoft.com/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016)<br/>[Requisitos de sistema do Exchange 2013](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)<br/><br/>Com as melhorias significativas no desempenho do Exchange e no aumento da capacidade de computação e de armazenamento em servidores mais novos, você provavelmente precisará de menos servidores para dar suporte ao mesmo número de caixas de correio.|
|Versão do sistema operacional|As versões mínimas do sistema operacional com suporte para cada versão são:<br/><br/>Exchange 2016 - Windows Server 2012<br/>Exchange 2013 - Windows Server 2008 R2 SP1<br/><br/>Você pode encontrar mais informações sobre o suporte ao sistema operacional na Matriz [de Suporte do Exchange.](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix)|
|Nível funcional da floresta do Active Directory|Os níveis funcionais mínimos de floresta do Active Directory com suporte para cada versão são:<br/><br/>Exchange 2016 - Windows Server 2008 R2 SP1<br/>Exchange 2013 - Windows Server 2003<br/><br/>Você pode encontrar mais informações sobre o suporte a nível funcional da floresta na [Matriz de Suporte do Exchange.](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix)|
|Versões de cliente do Office|As versões mínimas de cliente do Office com suporte para cada versão são:<br/><br/>Exchange 2016 - Office 2010 (com as atualizações mais recentes)<br/>Exchange 2013 - Office 2007 SP3<br/><br/>Encontre mais informações sobre o suporte ao cliente do Office na [Matriz de Suporte do Exchange.](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix)||| 


Use os seguintes recursos para ajudar na migração:

- [Assistente de Implantação do Exchange](https://aka.ms/exdeploy)
- Alterações de esquema do Active Directory para o Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- Requisitos do sistema para o Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/system-requirements?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)
- Pré-requisitos do Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/prerequisites?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Resumo das opções para cliente e servidores do Office 2010 e Windows 7

Para obter um resumo visual das opções de atualização, migração e mover para nuvem para clientes e servidores do Office 2010 e Windows 7, confira o [pôster sobre o fim do suporte](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Fim do suporte para clientes e servidores do Office 2010 e cartaz do Windows 7](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Este cartaz de uma página ilustra os vários caminhos que você pode seguir para responder aos produtos de cliente e servidor do Office 2010 e o Windows 7 chegar ao fim do suporte, com caminhos preferenciais e suporte a opções no Microsoft 365 Enterprise realçada.

Você também pode [baixar esse](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) cartaz e imprimi-lo em formato de carta, oficial ou tabloide (11 x 17).

## <a name="what-if-i-need-help"></a>E se eu precisar de ajuda?

Se você estiver migrando para o Microsoft 365, poderá estar qualificado para usar nosso serviço Microsoft FastTrack. O FastTrack fornece práticas recomendadas, ferramentas e recursos para tornar a migração para o Microsoft 365 o mais simples possível. O melhor de tudo, você terá um engenheiro de suporte que o explica desde o planejamento e o projeto até a migração da sua última caixa de correio. Para saber mais sobre o FastTrack, confira [o Microsoft FastTrack.](https://fasttrack.microsoft.com/)

Se você tiver problemas durante a migração para o Microsoft 365 e não estiver usando o FastTrack ou estiver migrando para uma versão mais recente do Exchange Server, aqui estão alguns recursos que você pode usar:

- [Comunidade técnica](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Suporte ao cliente](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>Artigos relacionados

[Recursos para ajudá-lo a atualizar clientes e servidores do Office 2010](upgrade-from-office-2010-servers-and-products.md)
