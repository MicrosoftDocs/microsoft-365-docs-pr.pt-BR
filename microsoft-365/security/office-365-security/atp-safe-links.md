---
title: Links seguros
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: Neste artigo, os administradores podem aprender sobre a proteção de Links Seguros no Defender para Office 365 para proteger sua organização contra phishing e outros ataques que usam URLs mal-intencionadas.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b8e184930e0891844a2a6f3b7b60cf5122ca4597
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727526"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>Links seguros no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](office-365-atp.md). Se você estiver usando o Outlook.com, a Família do Microsoft 365 ou o Microsoft 365 Personal e estiver procurando informações sobre Safelinks no Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Links Seguros é um recurso no [Defender para Office 365](office-365-atp.md) que fornece verificação de URL e reescrita de mensagens de email de entrada no fluxo de emails e verificação de tempo de clique de URLs e links em mensagens de email e outros locais. A verificação de Links Seguros ocorre além da proteção [anti-spam e anti-malware](anti-spam-and-anti-malware-protection.md) regular em mensagens de email de entrada no Exchange Online Protection (EOP). A verificação de Links Seguros pode ajudar a proteger sua organização contra links mal-intencionados usados em phishing e outros ataques.

A proteção de Links Seguros está disponível nos seguintes locais:

- **Mensagens de email**: a proteção de links seguros para links em mensagens de email é controlada por políticas de Links Seguros. Não há política de Links Seguros padrão, portanto, para obter a proteção de Links Seguros em mensagens de email, você precisa criar uma ou mais políticas de **Links Seguros.** Para obter instruções, consulte [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).

  Para obter mais informações sobre a proteção de Links Seguros para mensagens de email, consulte a seção Links Seguros para mensagens de [email](#safe-links-settings-for-email-messages) mais adiante neste artigo.

- **Microsoft Teams** (atualmente no TAP Preview): a proteção de links seguros para links em conversas do Teams, chats de grupo ou de canais também é controlada por políticas de Links Seguros. Não há nenhuma política padrão de Links Seguros, portanto, para obter a proteção de Links Seguros no Teams, você precisa criar uma ou mais políticas de **Links Seguros.**

  Para obter mais informações sobre a proteção de Links Seguros no Teams, consulte a seção Links Seguros [para o Microsoft Teams](#safe-links-settings-for-microsoft-teams) mais adiante neste artigo.

- **Aplicativos do Office 365**: a proteção de Links Seguros para aplicativos do Office 365 está disponível em computadores, dispositivos móveis e web com suporte. Configure **a** proteção de Links Seguros para aplicativos do Office 365 na configuração global que estão **fora das** políticas de Links Seguros. Para obter instruções, consulte [Configure global settings for Safe Links settings in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).

  No entanto, a proteção de Links Seguros  para aplicativos do Office 365 só é aplicada aos usuários incluídos em políticas de Links Seguros ativos. Se um usuário não estiver incluído em uma política de Links Seguros ativos, o usuário não obterá proteção de Links Seguros em aplicativos do Office 365 com suporte.

  Para obter mais informações sobre a proteção de Links Seguros nos aplicativos do Office 365, consulte a seção Configurações de Links Seguros para aplicativos do [Office 365](#safe-links-settings-for-office-365-apps) posteriormente neste artigo.

Este artigo inclui descrições detalhadas dos seguintes tipos de configurações de Links Seguros:

- **Configurações em políticas de Links Seguros**: Essas configurações se aplicam somente aos usuários incluídos nas políticas específicas, e as configurações podem ser diferentes entre as políticas. Essas configurações incluem:

  - [Configurações de Links Seguros para mensagens de email](#safe-links-settings-for-email-messages)
  - [Configurações de Links Seguros para o Microsoft Teams](#safe-links-settings-for-microsoft-teams)
  - ["Não reescrever as seguintes URLs" em políticas de Links Seguros](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **Configurações de Links Seguros Globais**: Essas configurações são configuradas globalmente, não em políticas de Links Seguros. Porém, as configurações se aplicam apenas aos usuários incluídos em políticas ativas de Links Seguros. Essas configurações incluem:

  - [Configurações de Links Seguros para aplicativos do Office 365](#safe-links-settings-for-office-365-apps)
  - ["Bloquear a lista de URLs a seguir" para Links Seguros](#block-the-following-urls-list-for-safe-links)

A tabela a seguir descreve cenários para Links Seguros nas organizações do Microsoft 365 e do Office 365 que incluem o Defender para Office 365 (em outras palavras, a falta de licenciamento nunca é um problema nos exemplos).

****

|Cenário|Resultado|
|---|---|
|O Jean é membro do departamento de marketing. A proteção de Links Seguros para aplicativos do Office 365 está ativas nas configurações globais para Links Seguros, e existe uma política de Links Seguros que se aplica a membros do departamento de marketing. João abre uma apresentação do PowerPoint em uma mensagem de email e clica em uma URL na apresentação.|O Jean é protegido por Links Seguros. <p> O Jean está incluído em uma política de Links Seguros e a proteção de Links Seguros para aplicativos do Office 365 está conexões. <p> Para obter mais informações sobre os requisitos para a proteção de Links Seguros em aplicativos do Office 365, consulte a seção Configurações de Links Seguros para aplicativos do [Office 365](#safe-links-settings-for-office-365-apps) posteriormente neste artigo.|
|A organização do Microsoft 365 E5 do Chris não tem políticas de Links Seguros configuradas. Chris recebe um email de um remetente externo que contém uma URL para um site mal-intencionado que ele finalmente clica.|Chris não está protegido por Links Seguros. <p> Um administrador deve criar pelo menos uma política de Links Seguros para qualquer pessoa obter proteção de Links Seguros em mensagens de email de entrada. Chris deve ser incluído nas condições da política para obter proteção de Links Seguros.|
|Na organização do Pat, nenhum administrador criou nenhuma política de Links Seguros, mas a proteção de Links Seguros para aplicativos do Office 365 está conexões ativas. Pat abre um documento do Word e clica em uma URL no arquivo.|O Pat não está protegido por Links Seguros. <p> Embora a proteção de Links Seguros para aplicativos do Office 365 seja ativa globalmente, o Pat não está incluído em nenhuma política ativa de Links Seguros, portanto, a proteção não pode ser aplicada.|
|Na organização de Lee, é configurado na lista Bloquear as URLs a seguir nas configurações `https://tailspintoys.com` globais para Links Seguros.  Uma política de Links Seguros que inclui Lee já existe. Lee recebe uma mensagem de email que contém a URL `https://tailspintoys.com/aboutus/trythispage` . Lee clica na URL.|A URL pode ser bloqueada automaticamente para Lee; depende da entrada da URL na lista e do cliente de email que Lee usou. Para obter mais informações, consulte a [seção "Bloquear as URLs a seguir" para Links](#block-the-following-urls-list-for-safe-links) Seguros mais adiante neste artigo.|
|O Jamie e a Julia trabalham para contoso.com. Há muito tempo, os administradores configuram políticas de Links Seguros que se aplicam a Ambos de Jamie e Julia. O Jamie envia um email para a Julia, sem saber que o email contém uma URL mal-intencionada.|A Julia será protegida por **Links** Seguros se a política de Links Seguros que se aplica a ela estiver configurada para aplicar-se a mensagens entre destinatários internos. Para obter mais informações, consulte a seção [Configurações de Links Seguros para mensagens de email](#safe-links-settings-for-email-messages) posteriormente neste artigo.|

## <a name="safe-links-settings-for-email-messages"></a>Configurações de Links Seguros para mensagens de email

Links seguros verifica emails de entrada para hiperlinks mal-intencionados conhecidos. As URLs digitalizados são reescritas usando o prefixo de URL padrão da Microsoft: `https://nam01.safelinks.protection.outlook.com` . Depois que o link é reescrito, ele é analisado para conteúdo potencialmente mal-intencionado.

Depois que Links Seguros reescrever uma URL, a URL permanecerá reescrito mesmo que a mensagem seja *encaminhada manualmente* ou respondida (para destinatários internos e externos). Links adicionais adicionados à mensagem encaminhada ou respondida não são reescritos. No entanto, no  caso de encaminhamento automático por regras de Caixa de Entrada ou encaminhamento SMTP, a  URL não será regravada na mensagem que se destina ao destinatário final, a menos que esse destinatário também esteja protegido por Links Seguros ou a URL já tenha sido regravada em uma comunicação anterior. 

As configurações em políticas de Links Seguros que se aplicam a mensagens de email são descritas na lista a seguir:

- **Selecione a ação para URLs potencialmente mal-intencionadas** desconhecidas em mensagens : Habilita ou desabilita a verificação de Links Seguros em mensagens de email. O valor recomendado é **On**. A ação dessa configuração resulta nas seguintes ações.

  - A verificação de Links Seguros está habilitada no Outlook (C2R) no Windows.
  - AS URLs são regravadas e os usuários são roteados por meio da proteção de Links Seguros quando clicam em URLs em mensagens.
  - Quando clicadas, as URLs são verificadas em uma lista de URLs mal-intencionadas conhecidas e na lista ["Bloquear as URLs a seguir".](#block-the-following-urls-list-for-safe-links)
  - URLs que não têm uma reputação válida são detonadas de forma assíncrona em segundo plano.

- **Aplicar verificação de URL** em tempo real para links suspeitos e links que apontam para arquivos : Permite a verificação em tempo real de links, incluindo links em mensagens de email que apontam para conteúdo baixável. O valor recomendado está habilitado.

  - **Aguarde a conclusão da verificação de URL antes de entregar a mensagem**:

    - Habilitado: as mensagens que contêm URLs são mantidas até que a verificação seja concluída. As mensagens são entregues somente depois que as URLs são confirmadas como seguras. Esse é o valor recomendado.
    - Desabilitado: se a verificação de URL não puder ser concluída, entregue a mensagem de qualquer maneira.

- **Aplicar Links Seguros** a mensagens de email enviadas dentro da organização : Habilita ou desabilita a verificação de Links Seguros em mensagens enviadas entre destinatários internos e destinatários internos na mesma organização do Exchange Online. O valor recomendado está habilitado.

- **Não rastrear cliques do usuário**: Habilita ou desabilita o armazenamento de Links Seguros clique em dados de clique para URLs clicadas em mensagens de email. O valor recomendado é deixar essa configuração não eleita (para acompanhar os cliques do usuário).

  No momento, não há suporte para o rastreamento de cliques de URL para links em mensagens de email enviadas entre destinatários internos e destinatários internos.

- **Não permita que os usuários cliquem** na URL original : Permite ou impede que os usuários cliquem na página de aviso [para](#warning-pages-from-safe-links) a URL original. O valor recomendado está habilitado.

- **Exibir a identidade visual da organização em páginas** de notificação e aviso: essa opção mostra a identidade visual da sua organização em páginas de aviso. A identidade visual ajuda os usuários a identificar avisos legítimos, pois as páginas de aviso padrão da Microsoft geralmente são usadas por invasores. Para obter mais informações sobre identidade visual personalizada, consulte Adicionar identidade visual à página de login do [Azure Active Directory](/azure/active-directory/fundamentals/customize-branding)da sua organização.

- **Não reescreva as SEGUINTES URLs**: deixa URLs como estão. Mantém uma lista personalizada de URLs seguras que não precisam de verificação. A lista é exclusiva para cada política de Links Seguros. Para obter mais informações sobre a lista Não reescrever as **URLs** a seguir, consulte as listas "Não reescrever as [URLs a seguir"](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) na seção Políticas de Links Seguros mais adiante neste artigo.

Para obter mais informações sobre os valores recomendados para configurações de política padrão e estrita para políticas de Links Seguros, consulte Configurações de política de [Links Seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)

- **Filtros de** destinatário : Você precisa especificar as condições e exceções de destinatário que determinam a quem a política se aplica. Você pode usar essas propriedades para condições e exceções:

  - **O destinatário é**
  - **O domínio do destinatário é**
  - **O destinatário é um membro de**

  Você só pode usar uma condição ou exceção uma vez, mas a condição ou exceção pode conter vários valores. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

- **Prioridade**: se você criar várias políticas, poderá especificar a ordem em que elas são aplicadas. Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.

  Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).

### <a name="how-safe-links-works-in-email-messages"></a>Como os Links Seguros funcionam em mensagens de email

Em alto nível, veja como a proteção de Links Seguros funciona em URLs em mensagens de email:

1. Todos os emails passam pelo EOP, onde o protocolo de Internet (IP) e filtros de envelope, proteção contra malware baseada em assinatura, filtros anti-spam e anti-malware antes da mensagem ser entregue à caixa de correio do destinatário.

2. O usuário abre a mensagem em sua caixa de correio e clica em uma URL na mensagem.

3. Links seguros verifica imediatamente a URL antes de abrir o site:

   - Se a URL for incluída na lista **Bloquear as URLs** a seguir, será aberto um aviso [de URL](#blocked-url-warning) bloqueado.

   - Se a URL aponta para um site que foi determinado como mal-intencionado, uma página de aviso de [site](#malicious-website-warning) mal-intencionado (ou uma página de aviso diferente) será aberta.

   - Se a URL apontar para um arquivo baixável e a verificação de URL aplicar em tempo real para links suspeitos e **links** que apontam para a configuração de arquivos estiver habilitada na política que se aplica ao usuário, o arquivo baixável será verificado.

   - Se a URL for determinada como segura, o site será aberto.

## <a name="safe-links-settings-for-microsoft-teams"></a>Configurações de Links Seguros para o Microsoft Teams

> [!IMPORTANT]
> A partir de março de 2020, esse recurso está no Preview e está disponível apenas para membros do Programa de Adoção de Tecnologia do Microsoft Teams (TAP). Para obter informações sobre o cronograma de lançamento, confira o [roteiro do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams).

Você habilita ou desabilita a proteção de Links Seguros para o Microsoft Teams em políticas de Links Seguros. Especificamente, você usa a configuração Selecionar a ação para **URLs desconhecidas** ou potencialmente mal-intencionadas no Microsoft Teams. O valor recomendado é **On**.

As configurações a seguir em políticas de Links Seguros que se aplicam a links em mensagens de email também se aplicam a links no Teams:

- **Aplicar verificação de URL em tempo real para links suspeitos e links que apontam para arquivos**
- **Não rastrear cliques do usuário**
- **Não permitir que os usuários cliquem na URL original**

Essas configurações são explicadas nas configurações anteriores [de Links Seguros para mensagens de email.](#safe-links-settings-for-email-messages)

Depois de ativar a proteção de Links Seguros para o Microsoft Teams, as URLs no Teams são verificadas em uma lista de links mal-intencionados conhecidos quando o usuário protegido clica no link (proteção de hora em clique). URLs não são regravadas. Se um link for considerado mal-intencionado, os usuários terão as seguintes experiências:

- Se o link foi clicado em uma conversa do Teams, chat em grupo ou de canais, a página de aviso, conforme mostrado na captura de tela abaixo, aparecerá no navegador da Web padrão.
- Se o link foi clicado de uma guia fixada, a página de aviso aparecerá na interface do Teams nessa guia. A opção de abrir o link em um navegador da Web está desabilitada por motivos de segurança.
- Dependendo de como a configuração não permitir que os usuários cliquem até **a URL original** na política está configurada, o usuário poderá ou não clicar na URL original ( Continue de qualquer maneira **(não recomendado)** na captura de tela). Recomendamos que você habilita a configuração não permitir que os usuários cliquem na **URL original** para que os usuários não possam clicar na URL original.

Se o usuário que enviou o link não estiver incluído em uma política de Links Seguros em que a proteção do Teams está habilitada, o usuário poderá clicar na URL original em seu computador ou dispositivo.

![Uma página Links Seguros para o Teams relatando um link mal-intencionado.](../../media/tp-safe-links-for-teams-malicious.png)

Clicar no botão **Voltar** na página de aviso retornará o usuário ao contexto original ou ao local da URL. No entanto, clicar no link original novamente fará com que os Links Seguros reexame a URL, para que a página de aviso reaparecer.

### <a name="how-safe-links-works-in-teams"></a>Como os Links Seguros funcionam no Teams

Em alto nível, veja como funciona a proteção de Links Seguros para URLs no Microsoft Teams:

1. Um usuário inicia o aplicativo do Teams.

2. O Microsoft 365 verifica se a organização do usuário inclui o Microsoft Defender para Office 365 e se o usuário está incluído em uma política de Links Seguros ativos, onde a proteção para o Microsoft Teams está habilitada.

3. AS URLs são validadas no momento do clique para o usuário em chats, chats de grupo, canais e guias.

## <a name="safe-links-settings-for-office-365-apps"></a>Configurações de Links Seguros para aplicativos do Office 365

Proteção de Links Seguros para aplicativos do Office 365 verifica links em documentos do Office, não links em mensagens de email (mas pode verificar links em documentos anexados do Office em mensagens de email após a abertura do documento).

A proteção de Links Seguros para aplicativos do Office 365 tem os seguintes requisitos de cliente:

- Microsoft 365 Apps ou Microsoft 365 Business Premium.
  - Versões atuais do Word, Excel e PowerPoint no Windows, Mac ou em um navegador da Web.
  - Aplicativos do Office em dispositivos iOS ou Android.
  - Visio no Windows.
  - OneNote em um navegador da Web.

- Os aplicativos do Office 365 estão configurados para usar a autenticação moderna. Para obter mais informações, consulte Como funciona a autenticação moderna para aplicativos cliente [do Office 2013, Office 2016 e Office 2019.](../../enterprise/modern-auth-for-office-2013-and-2016.md)

- Os usuários são assinados usando suas contas de trabalho ou de estudante. Para obter mais informações, [consulte Entrar no Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).

Configure a proteção de Links Seguros para aplicativos do Office 365 nas configurações globais para Links Seguros, não em políticas de Links Seguros. No entanto, para que a proteção de Links Seguros para aplicativos do Office 365 seja aplicada, o usuário que abre o documento do Office e clica no link deve ser incluído em uma política de Links Seguros ativos.

As seguintes configurações de Links Seguros estão disponíveis para aplicativos do Office 365:

- **Aplicativos do Office 365**: Habilita ou desabilita a verificação de Links Seguros em aplicativos do Office 365 com suporte. O valor padrão e recomendado é **On**.

- **Não rastreia quando** os usuários clicam em Links Seguros : Habilita ou desabilita o armazenamento de Links Seguros clicam em dados de URLs clicadas nas versões da área de trabalho Word, Excel, PowerPoint e Visio. O valor recomendado é **Off**, o que significa que os cliques do usuário são rastreados.

- Não permita que os usuários cliquem em links seguros para a [](#warning-pages-from-safe-links) **URL original**: Permite ou impede que os usuários cliquem na página de aviso para a URL original nas versões da área de trabalho Word, Excel, PowerPoint e Visio. O valor padrão e recomendado é **On**.

Para definir as configurações de Links Seguros para aplicativos do Office 365, consulte [Configure Safe Links protection for Office 365 apps](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center).

Para obter mais informações sobre os valores recomendados para configurações de política padrão e estrita, [consulte Configurações globais para Links Seguros.](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links)

### <a name="how-safe-links-works-in-office-365-apps"></a>Como funcionam os Links Seguros em aplicativos do Office 365

Em alto nível, veja como funciona a proteção de Links Seguros para URLs em aplicativos do Office 365. Os aplicativos do Office 365 com suporte são descritos na seção anterior.

1. Um usuário se ins signa em usar sua conta de estudante ou de trabalho em uma organização que inclui o Microsoft 365 Apps ou o Microsoft 365 Business Premium.

2. O usuário abre e clica em um link de um documento do Office em um aplicativo do Office com suporte.

3. Links seguros verifica imediatamente a URL antes de abrir o site de destino:

   - Se a URL estiver incluída na lista que ignora a verificação de Links Seguros (a lista Bloquear as **URLs** a seguir) será aberta uma página de aviso de [URL](#blocked-url-warning) bloqueada.

   - Se a URL aponta para um site que foi determinado como mal-intencionado, uma página de aviso de [site](#malicious-website-warning) mal-intencionado (ou uma página de aviso diferente) será aberta.

   - Se a URL apontar para um arquivo baixável e a política links seguros que se aplica ao usuário estiver configurada para verificar links para conteúdo baixável ( Aplicar verificação de URL em tempo real para links suspeitos e **links** que apontam para arquivos ), o arquivo baixável será verificado.

   - Se a URL for considerada segura, o usuário será levado para o site.

   - Se a verificação de Links Seguros não puder ser concluída, a proteção de Links Seguros não será acionada. Nos clientes da área de trabalho do Office, o usuário será avisado antes de prosseguir para o site de destino.

> [!NOTE]
> Pode levar vários segundos no início de cada sessão para verificar se o usuário tem links seguros para o Office habilitados.

## <a name="block-the-following-urls-list-for-safe-links"></a>"Bloquear a lista de URLs a seguir" para Links Seguros

A **lista Bloquear as URLs** a seguir define os links que sempre são bloqueados pela verificação de Links Seguros nos seguintes locais:

- Mensagens de email.
- Documentos em aplicativos do Office 365 no Windows e No Mac.
- Documentos no Office para iOS e Android.

Quando um usuário em uma política de Links Seguros ativo clica em um link bloqueado em um aplicativo com suporte, ele é levado para a página de aviso [de URL bloqueada.](#blocked-url-warning)

Você configura a lista de URLs nas configurações globais para Links Seguros. Para obter instruções, [consulte Configure the "Block the following URLs" list](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center).

**Observações**:

- Para uma lista verdadeiramente universal de URLs bloqueadas em todos os lugares, consulte [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).

- Limites:
  - O número máximo de entradas é 500.
  - O comprimento máximo de uma entrada é de 128 caracteres.
  - Todas as entradas não podem exceder 10.000 caracteres.

- Não inclua uma barra de avanço ( `/` ) no final da URL. Por exemplo, use `https://www.contoso.com` , não `https://www.contoso.com/` .

- Uma URL somente de domínio (por `contoso.com` exemplo ou `tailspintoys.com` ) bloqueará qualquer URL que contenha o domínio.

- Você pode bloquear um subdomínio sem bloquear o domínio completo. Por exemplo, bloqueia qualquer URL que contenha o subdomínio, mas não bloqueia `toys.contoso.com*` URLs que contenham o domínio completo `contoso.com` .

- Você pode incluir até três caracteres curinga ( `*` ) por entrada de URL.

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>Sintaxe de entrada para a lista "Bloquear as URLs a seguir"

Exemplos dos valores que você pode inserir e seus resultados são descritos na tabela a seguir:

****

|Valor|Resultado|
|---|---|
|`contoso.com` <p> ou <p> `*contoso.com*`|Bloqueia o domínio, subdomas e caminhos. Por exemplo, `https://www.contoso.com` , `https://sub.contoso.com` e são `https://contoso.com/abc` bloqueados.|
|`https://contoso.com/a`|Bloqueia, `https://contoso.com/a` mas não subcamados adicionais como `https://contoso.com/a/b` .|
|`https://contoso.com/a*`|Blocos `https://contoso.com/a` e subcamas adicionais como `https://contoso.com/a/b` .|
|`https://toys.contoso.com*`|Bloqueia um subdomínio ( neste exemplo), mas permite clicar em outras URLs de domínio `toys` (como `https://contoso.com` ou `https://home.contoso.com` ).|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>"Não reescrever as seguintes URLs" em políticas de Links Seguros

> [!NOTE]
> Se a sua organização usar políticas de Links Seguros, as listas **de URLs** a seguir não serão o único método suportado para testes de phishing de terceiros.

Cada política de Links Seguros contém uma lista Não reescrever a lista de **URLs** a seguir que você pode usar para especificar URLs que não são reescritas pela verificação de Links Seguros. Em outras palavras, a lista permite que os usuários incluídos na política acessem as URLs especificadas que seriam bloqueadas por Links Seguros. Você pode configurar listas diferentes em diferentes políticas de Links Seguros. O processamento de política é interrompido após a primeira (provavelmente, a política de prioridade mais alta) ser aplicada ao usuário. Portanto, apenas um Não reescreva a lista **de URLs** a seguir é aplicada a um usuário incluído em várias políticas de Links Seguros ativos.

Para adicionar entradas à lista em políticas de Links Seguros novas ou existentes, consulte [Create Safe Links policies](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) or Modify Safe Links [policies](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies).

**Observações**:

- Os clientes a seguir não reconhecem as listas Não reescrever **as SEGUINTES URLs** em políticas de Links Seguros. Os usuários incluídos nas polícias podem ser impedidos de acessar as URLs com base nos resultados da verificação de Links Seguros nesses clientes:

  - Microsoft Teams
  - Aplicativos web do Office

  Para uma lista verdadeiramente universal de URLs permitidas em todos os lugares, consulte [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).

- Considere adicionar URLs internas comumente usadas à lista para melhorar a experiência do usuário. Por exemplo, se você tiver serviços locais, como Skype for Business ou SharePoint, poderá adicionar essas URLs para exclui-las da verificação.

- Se você já tiver Não reescreve as seguintes entradas **URLs** em suas políticas de Links Seguros, não deixe de revisar as listas e adicionar curingas conforme necessário. Por exemplo, sua lista tem uma entrada como e você decide incluir `https://contoso.com/a` subcaminho como `https://contoso.com/a/b` . Em vez de adicionar uma nova entrada, adicione um caractere curinga à entrada existente para que ela se torne `https://contoso.com/a/*` .

- Você pode incluir até três caracteres curinga ( `*` ) por entrada de URL. Caracteres curinga incluem explicitamente prefixos ou subdomas. Por exemplo, a entrada não é igual a , porque permite que as pessoas `contoso.com` `*.contoso.com/*` `*.contoso.com/*` visitem subdomas e caminhos no domínio especificado.

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>Sintaxe de entrada para a lista "Não reescrever as URLs a seguir"

Exemplos dos valores que você pode inserir e seus resultados são descritos na tabela a seguir:

****

|Valor|Resultado|
|---|---|
|`contoso.com`|Permite o acesso a `https://contoso.com` subdomas ou caminhos, mas não a caminhos.|
|`*.contoso.com/*`|Permite o acesso a um domínio, subdomas e caminhos (por exemplo, `https://www.contoso.com` , `https://www.contoso.com` , ou `https://maps.contoso.com` `https://www.contoso.com/a` ). <p> Essa entrada é inerentemente melhor do que , porque não permite sites `*contoso.com*` potencialmente fraudulentos, como `https://www.falsecontoso.com` ou `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Permite o acesso `https://contoso.com/a` a , mas não subcaminho como `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Permite acesso a `https://contoso.com/a` e subcaminhos como `https://contoso.com/a/b`|
|

## <a name="warning-pages-from-safe-links"></a>Páginas de aviso de Links Seguros

Esta seção contém exemplos das várias páginas de aviso que são disparadas pela proteção de Links Seguros quando você clica em uma URL.

Observe que várias páginas de aviso foram atualizadas. Se você ainda não estiver vendo as páginas atualizadas, em breve. As páginas atualizadas incluem um novo esquema de cores, mais detalhes e a capacidade de prosseguir para um site, apesar do aviso e das recomendações.

### <a name="scan-in-progress-notification"></a>Notificação de verificação em andamento

A URL clicada está sendo digitalizada por Links Seguros. Talvez seja necessário aguardar alguns instantes antes de tentar o link novamente.

![Notificação "O link está sendo verificado"](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

A página de notificação original era assim:

![Notificação original "O link está sendo verificado"](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a>Aviso de mensagem suspeito

A URL clicada estava em uma mensagem de email semelhante a outras mensagens suspeitas. Recomendamos que você verifique a mensagem de email duas vezes antes de prosseguir para o site.

![Aviso "Um link foi clicado de uma mensagem suspeita"](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a>Aviso de tentativa de phishing

A URL clicada estava em uma mensagem de email que foi identificada como um ataque de phishing. Como resultado, todas as URLs na mensagem de email são bloqueadas. Recomendamos que você não prossiga para o site.

![Aviso "O link foi clicado de uma mensagem de phishing"](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a>Aviso de site mal-intencionado

A URL clicada aponta para um site identificado como mal-intencionado. Recomendamos que você não prossiga para o site.

![Aviso "Este site é classificado como mal-intencionado"](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

A página de aviso original era assim:

![Aviso original "Este site foi classificado como mal-intencionado"](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a>Aviso de URL bloqueado

A URL clicada foi bloqueada manualmente por um administrador em sua organização (a lista Bloquear as **URLs** a seguir nas configurações globais para Links Seguros). O link não foi verificado por Links Seguros porque foi bloqueado manualmente.

Há vários motivos pelos quais um administrador bloquearia manualmente URLs específicas. Se você acha que o site não deve ser bloqueado, entre em contato com o administrador.

![Aviso "Este site foi bloqueado pelo administrador"](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

A página de aviso original era assim:

![Aviso original "Este site foi bloqueado por política de URL da sua organização"](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a>Aviso de erro

Ocorreu algum tipo de erro e a URL não pode ser aberta.

!["A página que você está tentando acessar não pode ser carregada" aviso](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

A página de aviso original era assim:

![Aviso original "Esta página da Web não pôde ser carregada"](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
