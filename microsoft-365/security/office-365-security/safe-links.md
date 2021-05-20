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
description: Neste artigo, os administradores podem aprender sobre a proteção Cofre Links no Defender para Office 365 proteger sua organização contra phishing e outros ataques que usam URLs mal-intencionadas.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 573fd5b92400996fa595b5953028e20fcecec976
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583575"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>Cofre Links no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](defender-for-office-365.md). Se você estiver usando Outlook.com, Microsoft 365 Family ou Microsoft 365 Personal e estiver procurando informações sobre Safelinks no Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Cofre Links é um recurso no [Defender para](defender-for-office-365.md) Office 365 que fornece verificação de URL e reescrita de mensagens de email de entrada no fluxo de emails e verificação de tempo de clique de URLs e links em mensagens de email e outros locais. Cofre A verificação de links ocorre além da proteção [anti-spam e anti-malware](anti-spam-and-anti-malware-protection.md) regular em mensagens de email de entrada no Proteção do Exchange Online (EOP). Cofre A verificação de links pode ajudar a proteger sua organização contra links mal-intencionados usados em phishing e outros ataques.

Cofre A proteção de links está disponível nos seguintes locais:

- **Mensagens de** email : Cofre proteção de links para links em mensagens de email é controlada por políticas Cofre Links. Não há nenhuma política de links padrão Cofre, portanto, para obter a proteção de links Cofre em mensagens de email, você precisa criar uma ou mais políticas Cofre **Links.** Para obter instruções, [consulte Set up Cofre Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).

  Para obter mais informações sobre Cofre de links para mensagens de email, consulte [Cofre configurações](#safe-links-settings-for-email-messages) de links para mensagens de email mais adiante neste artigo.
  
  > [!NOTE]
  > Links de venda não funcionam em pastas públicas habilitadas para email.

- **Microsoft Teams** (atualmente no TAP Preview): a proteção de links Cofre links para links em conversas de Teams, chats de grupo ou de canais também é controlada por políticas Cofre Links. Não há nenhuma política Cofre links padrão, portanto, para obter a proteção de links Cofre **no Teams, você** precisa criar uma ou mais políticas Cofre Links.

  Para obter mais informações sobre Cofre proteção de links no Teams, consulte [Cofre configurações](#safe-links-settings-for-microsoft-teams) de links para Microsoft Teams mais adiante neste artigo.

- **Office 365 aplicativos**: Cofre proteção de links para aplicativos Office 365 está disponível em aplicativos da web, desktop e móveis com suporte. Você **configura Cofre** proteção de links para Office 365 aplicativos na configuração global que estão fora de Cofre políticas de Links.  Para obter instruções, consulte [Configure global settings for Cofre Links settings in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).

  Cofre A proteção de links para Office 365 aplicativos é aplicada a todos os usuários na organização licenciados para o Defender para Office 365, independentemente de os usuários estar incluídos em políticas Cofre Links ativos ou não.

  Para obter mais informações sobre Cofre de links em aplicativos Office 365, consulte [Cofre Configurações](#safe-links-settings-for-office-365-apps) de links para Office 365 aplicativos posteriormente neste artigo.

Este artigo inclui descrições detalhadas dos seguintes tipos de configurações Cofre Links:

- **Configurações em Cofre Políticas** de Links : Essas configurações se aplicam apenas aos usuários incluídos nas políticas específicas, e as configurações podem ser diferentes entre as políticas. Essas configurações incluem:

  - [Cofre Configurações de links para mensagens de email](#safe-links-settings-for-email-messages)
  - [Cofre Configurações de links para Microsoft Teams](#safe-links-settings-for-microsoft-teams)
  - ["Não reescrever as seguintes URLs" nas políticas Cofre Links](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **Configurações Cofre links** globais : Essas configurações são configuradas globalmente, não em Cofre Políticas de Links. Porém, as configurações se aplicam somente aos usuários incluídos nas políticas Cofre Links ativos. Essas configurações incluem:

  - [Cofre Configurações de links para Office 365 aplicativos](#safe-links-settings-for-office-365-apps)
  - ["Bloquear a lista de URLs a seguir" para Cofre Links](#block-the-following-urls-list-for-safe-links)

A tabela a seguir descreve cenários para as organizações Cofre Links no Microsoft 365 e Office 365 que incluem o Defender para Office 365 (em outras palavras, a falta de licenciamento nunca é um problema nos exemplos).

<br>

****

|Cenário|Resultado|
|---|---|
|O Jean é membro do departamento de marketing. Cofre A proteção de links Office 365 aplicativos está conexões nas configurações globais para links Cofre, e existe uma política de links Cofre que se aplica aos membros do departamento de marketing. João abre uma PowerPoint em uma mensagem de email e clica em uma URL na apresentação.|O Jean é protegido por Cofre Links. <p> O Jean está incluído em uma política Cofre Links e Cofre proteção de links para Office 365 aplicativos está ligado. <p> Para obter mais informações sobre os requisitos para Cofre de links em aplicativos Office 365, consulte Cofre configurações de links para Office 365 [aplicativos](#safe-links-settings-for-office-365-apps) posteriormente neste artigo.|
|A organização de Microsoft 365 E5 chris não tem nenhuma Cofre links configuradas. Chris recebe um email de um remetente externo que contém uma URL para um site mal-intencionado que ele finalmente clica.|Chris não está protegido por Cofre Links. <p> Um administrador deve criar pelo menos uma política Cofre Links para qualquer pessoa obter Cofre de links em mensagens de email de entrada. Chris deve ser incluído nas condições da política para obter Cofre links.|
|Na organização do Pat, nenhum administrador criou nenhuma política Cofre Links, mas Cofre proteção links para Office 365 aplicativos está conexões. Pat abre um documento do Word e clica em uma URL no arquivo.|O Pat não é protegido por Cofre Links. <p> Embora Cofre proteção de links para aplicativos Office 365 seja ativado globalmente, Pat não está incluído em nenhuma política Cofre Links ativas, portanto, a proteção não pode ser aplicada.|
|Na organização de Lee, é configurado na lista Bloquear as URLs a seguir nas configurações globais para Cofre `https://tailspintoys.com` Links.  Uma Cofre de links que inclui Lee já existe. Lee recebe uma mensagem de email que contém a URL `https://tailspintoys.com/aboutus/trythispage` . Lee clica na URL.|A URL pode ser bloqueada automaticamente para Lee; depende da entrada da URL na lista e do cliente de email que Lee usou. Para obter mais informações, consulte a [lista "Bloquear as URLs a seguir"](#block-the-following-urls-list-for-safe-links) para Cofre Links posteriormente neste artigo.|
|O Jamie e a Julia trabalham para contoso.com. Há muito tempo, os administradores configuram Cofre políticas de Links que se aplicam a Ambos de Jamie e Julia. O Jamie envia um email para a Julia, sem saber que o email contém uma URL mal-intencionada.|Ela será protegida por Cofre **Links** se Cofre política de links que se aplica a ela estiver configurada para aplicar-se a mensagens entre destinatários internos. Para obter mais informações, consulte a seção Cofre Links para [mensagens de email](#safe-links-settings-for-email-messages) posteriormente neste artigo.|
|

## <a name="safe-links-settings-for-email-messages"></a>Cofre Configurações de links para mensagens de email

Cofre Links verificam emails de entrada para hiperlinks mal-intencionados conhecidos. As URLs digitalizados são reescritas usando o prefixo de URL padrão da Microsoft: `https://nam01.safelinks.protection.outlook.com` . Depois que o link é reescrito, ele é analisado para conteúdo potencialmente mal-intencionado.

Depois Cofre Links regrava uma URL, a URL permanece reescrita mesmo que a mensagem seja *encaminhada manualmente* ou respondeda (tanto para destinatários internos quanto externos). Links adicionais adicionados à mensagem encaminhada ou respondida não são reescritos. No entanto, no  caso de encaminhamento automático por regras de Caixa de Entrada ou encaminhamento SMTP, a  URL não será regravada na mensagem que se destina ao destinatário final, a menos que esse destinatário também esteja protegido por links Cofre ou a URL já tenha sido regravada em uma comunicação anterior. 

As configurações em Cofre políticas de links que se aplicam a mensagens de email são descritas na lista a seguir:

- **Selecione a ação para URLs** potencialmente mal-intencionadas desconhecidas em mensagens : Habilita ou desabilita Cofre verificação de links em mensagens de email. O valor recomendado é **On**. A ação dessa configuração resulta nas seguintes ações.

  - Cofre A verificação de links está habilitada Outlook (C2R) no Windows.
  - AS URLs são reescritas e os usuários são roteados Cofre proteção de links quando clicam em URLs em mensagens.
  - Quando clicadas, as URLs são verificadas em uma lista de URLs mal-intencionadas conhecidas e na lista ["Bloquear as URLs a seguir".](#block-the-following-urls-list-for-safe-links)
  - URLs que não têm uma reputação válida são detonadas de forma assíncrona em segundo plano.

- **Aplicar verificação de URL** em tempo real para links suspeitos e links que apontam para arquivos : Permite a verificação em tempo real de links, incluindo links em mensagens de email que apontam para conteúdo baixável. O valor recomendado está habilitado.
  - **Aguarde a conclusão da verificação de URL antes de entregar a mensagem**:
    - Habilitado: as mensagens que contêm URLs são mantidas até que a verificação seja concluída. As mensagens são entregues somente depois que as URLs são confirmadas como seguras. Esse é o valor recomendado.
    - Desabilitado: se a verificação de URL não puder ser concluída, entregue a mensagem de qualquer maneira.

- **Aplicar Cofre Links** para mensagens de email enviadas dentro da organização : Habilita ou desabilita Cofre Verificação de links em mensagens enviadas entre destinatários internos e destinatários internos na mesma organização Exchange Online. O valor recomendado está habilitado.

- **Não rastrear cliques do** usuário : Habilita ou desabilita o armazenamento Cofre Links clicam em dados para URLs clicadas em mensagens de email. O valor recomendado é deixar essa configuração não eleita (para acompanhar os cliques do usuário).

  No momento, não há suporte para o rastreamento de cliques de URL para links em mensagens de email enviadas entre destinatários internos e destinatários internos.

- **Não permita que os usuários cliquem** na URL original : Permite ou impede que os usuários cliquem na página de aviso [para](#warning-pages-from-safe-links) a URL original. O valor recomendado está habilitado.

- **Exibir a identidade visual da organização em páginas** de notificação e aviso: essa opção mostra a identidade visual da sua organização em páginas de aviso. A identidade visual ajuda os usuários a identificar avisos legítimos, pois as páginas de aviso padrão da Microsoft geralmente são usadas por invasores. Para obter mais informações sobre a identidade visual personalizada, consulte [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md).

- **Não reescreva as SEGUINTES URLs**: deixa URLs como estão. Mantém uma lista personalizada de URLs seguras que não precisam de verificação. A lista é exclusiva para cada política Cofre Links. Para obter mais informações sobre a lista Não reescrever as **URLs** a seguir, consulte as listas "Não reescrever as [URLs](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) a seguir" na seção Políticas de links Cofre mais adiante neste artigo.

  Para obter mais informações sobre os valores recomendados para configurações de política padrão e estritas para políticas Cofre Links, consulte [Cofre Configurações de](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)política links.

- **Filtros de** destinatário : Você precisa especificar as condições e exceções de destinatário que determinam a quem a política se aplica. Você pode usar essas propriedades para condições e exceções:
  - **O destinatário é**
  - **O domínio do destinatário é**
  - **O destinatário é um membro de**

  Você só pode usar uma condição ou exceção uma vez, mas a condição ou exceção pode conter vários valores. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

- **Prioridade**: se você criar várias políticas, poderá especificar a ordem em que elas são aplicadas. Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.

  Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).
  
### <a name="how-safe-links-works-in-email-messages"></a>Como Cofre links funciona em mensagens de email

Em um nível alto, veja como a proteção Cofre Links funciona em URLs em mensagens de email:

1. Todos os emails passam pelo EOP, onde o protocolo de Internet (IP) e filtros de envelope, proteção contra malware baseada em assinatura, filtros anti-spam e anti-malware antes da mensagem ser entregue à caixa de correio do destinatário.

2. O usuário abre a mensagem em sua caixa de correio e clica em uma URL na mensagem.

3. Cofre Os links verificam imediatamente a URL antes de abrir o site:

   - Se a URL for incluída na lista **Bloquear as URLs** a seguir, será aberto um aviso [de URL](#blocked-url-warning) bloqueado.

   - Se a URL aponta para um site que foi determinado como mal-intencionado, uma página de aviso de [site](#malicious-website-warning) mal-intencionado (ou uma página de aviso diferente) será aberta.

   - Se a URL apontar para um arquivo baixável e a verificação de URL aplicar em tempo real para links suspeitos e **links** que apontam para a configuração de arquivos estiver habilitada na política que se aplica ao usuário, o arquivo baixável será verificado.

   - Se a URL for determinada como segura, o site será aberto.

## <a name="safe-links-settings-for-microsoft-teams"></a>Cofre Configurações de links para Microsoft Teams

> [!IMPORTANT]
> A partir de março de 2020, esse recurso está no Preview e está disponível apenas para membros do Programa de Adoção de Tecnologia Microsoft Teams (TAP). Para obter informações sobre o cronograma de lançamento, confira [o roteiro Microsoft 365 .](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)

Você habilita ou desabilita Cofre proteção de links para Microsoft Teams em Cofre de Links. Especificamente, você usa a configuração Selecionar a ação para URLs desconhecidas ou potencialmente **mal-intencionadas Microsoft Teams.** O valor recomendado é **On**.

As configurações a seguir Cofre políticas de links que se aplicam a links em mensagens de email também se aplicam a links em Teams:

- **Aplicar verificação de URL em tempo real para links suspeitos e links que apontam para arquivos**
- **Não rastrear cliques do usuário**
- **Não permitir que os usuários cliquem na URL original**

Essas configurações são explicadas anteriormente [em Cofre Links para mensagens de email](#safe-links-settings-for-email-messages).

Depois de ativar Cofre proteção de links para Microsoft Teams, as URLs no Teams são verificadas em relação a uma lista de links mal-intencionados conhecidos quando o usuário protegido clica no link (proteção de hora em clique). URLs não são regravadas. Se um link for considerado mal-intencionado, os usuários terão as seguintes experiências:

- Se o link foi clicado em uma conversa Teams, chat em grupo ou de canais, a página de aviso, conforme mostrado na captura de tela abaixo, aparecerá no navegador da Web padrão.
- Se o link foi clicado de uma guia fixada, a página de aviso aparecerá na interface Teams dentro dessa guia. A opção de abrir o link em um navegador da Web está desabilitada por motivos de segurança.
- Dependendo de como a configuração não permitir que os usuários cliquem até **a URL original** na política está configurada, o usuário poderá ou não clicar na URL original ( Continue de qualquer maneira **(não recomendado)** na captura de tela). Recomendamos que você habilita a configuração não permitir que os usuários cliquem na **URL original** para que os usuários não possam clicar na URL original.

Se o usuário que enviou o link não estiver incluído em uma política de links Cofre onde a proteção Teams está habilitada, o usuário poderá clicar na URL original em seu computador ou dispositivo.

![Um Cofre links para Teams página relatando um link mal-intencionado.](../../media/tp-safe-links-for-teams-malicious.png)

Clicar no botão **Voltar** na página de aviso retornará o usuário ao contexto original ou ao local da URL. No entanto, clicar no link original novamente fará com que os links Cofre a URL novamente, de modo que a página de aviso reaparecerá.

### <a name="how-safe-links-works-in-teams"></a>Como Cofre links funciona no Teams

Em um nível alto, veja como a proteção Cofre Links funciona para URLs em Microsoft Teams:

1. Um usuário inicia o Teams aplicativo.

2. Microsoft 365 verifica se a organização do usuário inclui o Microsoft Defender para Office 365 e se o usuário está incluído em uma política de Links Cofre ativa em que Microsoft Teams proteção para Microsoft Teams está habilitada.

3. AS URLs são validadas no momento do clique para o usuário em chats, chats de grupo, canais e guias.

## <a name="safe-links-settings-for-office-365-apps"></a>Cofre Configurações de links para Office 365 aplicativos

Cofre A proteção de links Office 365 aplicativos verifica links em documentos Office, não links em mensagens de email (mas pode verificar links em documentos Office anexados em mensagens de email após a abertura do documento).

Cofre A proteção de links para Office 365 aplicativos tem os seguintes requisitos de cliente:

- Microsoft 365 Apps ou Microsoft 365 Business Premium.
  - Versões atuais do Word, Excel e PowerPoint em Windows, Mac ou em um navegador da Web.
  - Office aplicativos em dispositivos iOS ou Android.
  - Visio no Windows.
  - OneNote em um navegador da Web.

- Office 365 aplicativos são configurados para usar a autenticação moderna. Para obter mais informações, consulte [How modern authentication works for Office 2013, Office 2016, and Office 2019 client apps](../../enterprise/modern-auth-for-office-2013-and-2016.md).

- Os usuários são assinados usando suas contas de trabalho ou de estudante. Para obter mais informações, [consulte Entrar Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).

Você configura Cofre proteção de links para Office 365 aplicativos nas configurações globais para links Cofre, não em políticas Cofre Links. A proteção é aplicada a todos os usuários da organização licenciados para o Defender para Office 365, independentemente de os usuários estar incluídos em políticas Cofre Links ativas ou não.

As configurações Cofre links a seguir estão disponíveis para Office 365 aplicativos:

- **Office 365 aplicativos**: Habilita ou desabilita Cofre verificação de links em aplicativos Office 365 com suporte. O valor padrão e recomendado é **On**.

- Não **rastreia quando** os usuários clicam em Cofre Links : Habilita ou desabilita o armazenamento de links Cofre Clique em dados para URLs clicadas nas versões da área de trabalho Word, Excel, PowerPoint e Visio. O valor recomendado é **Off**, o que significa que os cliques do usuário são rastreados.

- **Não permita que** os usuários cliquem em links seguros para a [](#warning-pages-from-safe-links) URL original : Permite ou impede que os usuários cliquem na página de aviso para a URL original nas versões da área de trabalho Word, Excel, PowerPoint e Visio. O valor padrão e recomendado é **On**.

Para configurar as configurações Cofre links para aplicativos Office 365, consulte [Configure Cofre Links protection for Office 365 apps](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center).

Para obter mais informações sobre os valores recomendados para configurações de política padrão e estrita, consulte [Configurações](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links)globais para links Cofre links .

### <a name="how-safe-links-works-in-office-365-apps"></a>Como Cofre links funciona em Office 365 aplicativos

Em um nível alto, veja como a proteção Cofre Links funciona para URLs em Office 365 aplicativos. Os aplicativos Office 365 com suporte são descritos na seção anterior.

1. Um usuário se ins signa em usar sua conta de trabalho ou de estudante em uma organização que inclui Microsoft 365 Apps ou Microsoft 365 Business Premium.

2. O usuário abre e clica em um link Office documento em um Aplicativo do Office.

3. Cofre Os links verificam imediatamente a URL antes de abrir o site de destino:

   - Se a URL estiver incluída na lista que ignora Cofre verificação de links (a lista Bloquear as **URLs** a seguir) será aberta uma página de aviso de [URL](#blocked-url-warning) bloqueada.

   - Se a URL aponta para um site que foi determinado como mal-intencionado, uma página de aviso de [site](#malicious-website-warning) mal-intencionado (ou uma página de aviso diferente) será aberta.

   - Se a URL apontar para um arquivo baixável e Cofre política de Links do Cofre que se aplica ao usuário estiver configurada para verificar links para conteúdo baixável ( Aplicar verificação de URL em tempo real para links suspeitos e **links** que apontam para arquivos ), o arquivo baixável será verificado.

   - Se a URL for considerada segura, o usuário será levado para o site.

   - Se Cofre verificação links não puder ser concluída, Cofre proteção links não dispara. Em Office clientes da área de trabalho, o usuário será avisado antes de prosseguir para o site de destino.

> [!NOTE]
> Pode levar vários segundos no início de cada sessão para verificar se o usuário Cofre Links para Office habilitados.

## <a name="block-the-following-urls-list-for-safe-links"></a>"Bloquear a lista de URLs a seguir" para Cofre Links

A **lista Bloquear as URLs** a seguir define os links que sempre são bloqueados Cofre verificação de links nos seguintes locais:

- Mensagens de email.
- Documentos em Office 365 aplicativos no Windows e Mac.
- Documentos em Office para iOS e Android.

Quando um usuário em uma política Cofre Links clica em um link bloqueado em um aplicativo com suporte, ele é levado para a página de aviso [url](#blocked-url-warning) bloqueado.

Você configura a lista de URLs nas configurações globais para Cofre Links. Para obter instruções, [consulte Configure the "Block the following URLs" list](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center).

**Observações**:

- Para uma lista verdadeiramente universal de URLs bloqueadas em todos os lugares, consulte [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).
- Limites para a **lista Bloquear as URLs** a seguir:
  - O número máximo de entradas é 500.
  - O comprimento máximo de uma entrada é de 128 caracteres.
  - Todas as entradas não podem exceder 10.000 caracteres.
- Não inclua uma barra de avanço ( `/` ) no final da URL. Por exemplo, use `https://www.contoso.com` , não `https://www.contoso.com/` .
- Uma URL somente de domínio (por `contoso.com` exemplo ou `tailspintoys.com` ) bloqueará qualquer URL que contenha o domínio.
- Você pode bloquear um subdomínio sem bloquear o domínio completo. Por exemplo, bloqueia qualquer URL que contenha o subdomínio, mas não bloqueia `toys.contoso.com*` URLs que contenham o domínio completo `contoso.com` .
- Você pode incluir até três caracteres curinga ( `*` ) por entrada de URL.

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>Sintaxe de entrada para a lista "Bloquear as URLs a seguir"

Exemplos dos valores que você pode inserir e seus resultados são descritos na tabela a seguir:

<br>

****

|Valor|Resultado|
|---|---|
|`contoso.com` <p> ou <p> `*contoso.com*`|Bloqueia o domínio, subdomas e caminhos. Por exemplo, `https://www.contoso.com` , `https://sub.contoso.com` e são `https://contoso.com/abc` bloqueados.|
|`https://contoso.com/a`|Bloqueia, `https://contoso.com/a` mas não subcamados adicionais como `https://contoso.com/a/b` .|
|`https://contoso.com/a*`|Blocos `https://contoso.com/a` e subcamas adicionais como `https://contoso.com/a/b` .|
|`https://toys.contoso.com*`|Bloqueia um subdomínio ( neste exemplo), mas permite clicar em outras URLs de domínio `toys` (como `https://contoso.com` ou `https://home.contoso.com` ).|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>"Não reescrever as seguintes URLs" nas políticas Cofre Links

> [!NOTE]
> Se sua organização usar Cofre políticas de Links, as listas de **URLs** a seguir não serão o único método suportado para testes de phishing de terceiros.

Cada Cofre de links contém uma lista Não reescrever a lista de **URLs** a seguir que você pode usar para especificar URLs que não são regravadas pela verificação de links Cofre links. Em outras palavras, a lista permite que os usuários incluídos na política acessem as URLs especificadas que seriam bloqueadas por links Cofre. Você pode configurar listas diferentes em políticas Cofre Links diferentes. O processamento de política é interrompido após a primeira (provavelmente, a política de prioridade mais alta) ser aplicada ao usuário. Portanto, apenas um Não reescreva a lista **de URLs** a seguir é aplicada a um usuário que está incluído em várias políticas Cofre Links ativas.

Para adicionar entradas à lista em políticas Cofre Links novas ou existentes, consulte [Create Cofre Links policies](set-up-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) ou Modify Cofre Links [policies](set-up-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies).

**Observações**:

- Os clientes a seguir não reconhecem as listas Não reescrever **as URLs** a seguir nas políticas Cofre Links. Os usuários incluídos nas polícias podem ser impedidos de acessar as URLs com base nos resultados Cofre verificação de links nesses clientes:
  - Microsoft Teams
  - Office Web

  Para uma lista verdadeiramente universal de URLs permitidas em todos os lugares, consulte [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).

- Considere adicionar URLs internas comumente usadas à lista para melhorar a experiência do usuário. Por exemplo, se você tiver serviços locais, como Skype for Business ou SharePoint, poderá adicionar essas URLs para exclui-las da verificação.
- Se você já tiver Não reescreve as seguintes entradas **URLs** em suas políticas Cofre Links, revise as listas e adicione caracteres curinga conforme necessário. Por exemplo, sua lista tem uma entrada como e você decide incluir `https://contoso.com/a` subcaminho como `https://contoso.com/a/b` . Em vez de adicionar uma nova entrada, adicione um caractere curinga à entrada existente para que ela se torne `https://contoso.com/a/*` .
- Você pode incluir até três caracteres curinga ( `*` ) por entrada de URL. Caracteres curinga incluem explicitamente prefixos ou subdomas. Por exemplo, a entrada não é igual a , porque permite que as pessoas `contoso.com` `*.contoso.com/*` `*.contoso.com/*` visitem subdomas e caminhos no domínio especificado.
- Se uma URL usa redirecionamento automático para HTTP para HTTPs (por exemplo, redirecionamento 302 para ), e você tenta inserir entradas HTTP e HTTPS para a mesma URL da lista, você pode notar que a segunda entrada de URL substitui a primeira entrada `http://www.contoso.com` `https://www.contoso.com` de URL. Esse comportamento não ocorrerá se as versões HTTP e HTTPS da URL estão completamente separadas.

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>Sintaxe de entrada para a lista "Não reescrever as URLs a seguir"

Exemplos dos valores que você pode inserir e seus resultados são descritos na tabela a seguir:

<br>

****

|Valor|Resultado|
|---|---|
|`contoso.com`|Permite o acesso a `https://contoso.com` subdomas ou caminhos, mas não a caminhos.|
|`*.contoso.com/*`|Permite o acesso a um domínio, subdomas e caminhos (por exemplo, `https://www.contoso.com` , `https://www.contoso.com` , ou `https://maps.contoso.com` `https://www.contoso.com/a` ). <p> Essa entrada é inerentemente melhor do que , porque não permite sites `*contoso.com*` potencialmente fraudulentos, como `https://www.falsecontoso.com` ou `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Permite o acesso `https://contoso.com/a` a , mas não subcaminho como `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Permite acesso a `https://contoso.com/a` e subcaminhos como `https://contoso.com/a/b`|
|

## <a name="warning-pages-from-safe-links"></a>Páginas de aviso de Cofre Links

Esta seção contém exemplos das várias páginas de aviso que são disparadas pela proteção Cofre Links quando você clica em uma URL.

Observe que várias páginas de aviso foram atualizadas. Se você ainda não estiver vendo as páginas atualizadas, em breve. As páginas atualizadas incluem um novo esquema de cores, mais detalhes e a capacidade de prosseguir para um site, apesar do aviso e das recomendações.

### <a name="scan-in-progress-notification"></a>Notificação de verificação em andamento

A URL clicada está sendo digitalizada por Cofre Links. Talvez seja necessário aguardar alguns instantes antes de tentar o link novamente.

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

A URL clicada foi bloqueada manualmente por um administrador em sua organização (a lista Bloquear as **URLs** a seguir nas configurações globais para Cofre Links). O link não foi verificado Cofre Links porque foi bloqueado manualmente.

Há vários motivos pelos quais um administrador bloquearia manualmente URLs específicas. Se você acha que o site não deve ser bloqueado, entre em contato com o administrador.

![Aviso "Este site foi bloqueado pelo administrador"](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

A página de aviso original era assim:

![Aviso original "Este site foi bloqueado por política de URL da sua organização"](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a>Aviso de erro

Ocorreu algum tipo de erro e a URL não pode ser aberta.

!["A página que você está tentando acessar não pode ser carregada" aviso](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

A página de aviso original era assim:

![Aviso original "Esta página da Web não pôde ser carregada"](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
