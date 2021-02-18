---
title: Links seguros
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
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
description: Neste artigo, os administradores podem aprender sobre a proteção de Links seguros no Defender for Office 365 para proteger sua organização contra phishing e outros ataques que usam URLs mal-intencionadas.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 15168f2fff5ce1e4afbef5ff71a780de896f0bbf
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288688"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>Links seguros no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](office-365-atp.md). Se você estiver usando o Outlook.com, o Microsoft 365 Family ou o Microsoft 365 Personal e estiver procurando informações sobre Safelinks no Outlook, confira Segurança avançada [Outlook.com.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Links Seguros é um recurso no [Defender para Office 365](office-365-atp.md) que fornece verificação de URL e reescrita de mensagens de email de entrada no fluxo de emails e verificação de tempo de clique de URLs e links em mensagens de email e outros locais. A verificação de Links seguros ocorre além da proteção [anti-spam e anti-malware](anti-spam-and-anti-malware-protection.md) regular em mensagens de email de entrada no Exchange Online Protection (EOP). A verificação de Links seguros pode ajudar a proteger sua organização contra links mal-intencionados usados em phishing e outros ataques.

A Proteção de Links Seguros está disponível nos seguintes locais:

- **Mensagens de email:** a proteção de Links seguros para links em mensagens de email é controlada pelas políticas de Links seguros. Não há uma política de Links seguros padrão, portanto, para obter a proteção de Links seguros em mensagens de email, você precisa criar uma ou mais políticas de **Links seguros.** Para obter instruções, consulte [Configurar políticas de Links seguros no Microsoft Defender para Office 365.](set-up-atp-safe-links-policies.md)

  Para obter mais informações sobre a proteção de Links seguros para mensagens de email, consulte a seção Configurações de Links seguros para mensagens de [email](#safe-links-settings-for-email-messages) posteriormente neste artigo.

- **Microsoft Teams** (atualmente no TAP Preview): a proteção de Links seguros para links em conversas do Teams, chats em grupo ou de canais também é controlada pelas políticas de Links seguros. Não há uma política de Links seguros padrão, portanto, para obter a proteção de Links seguros no Teams, você precisa criar uma ou mais políticas de **Links seguros.**

  Para obter mais informações sobre a proteção de Links seguros no Teams, consulte as configurações de Links seguros para [a seção do Microsoft Teams](#safe-links-settings-for-microsoft-teams) posteriormente neste artigo.

- **Aplicativos do Office 365:** a proteção de Links Seguros para aplicativos do Office 365 está disponível em área de trabalho, dispositivos móveis e web com suporte. Você **configura a** proteção de Links seguros para aplicativos do Office 365 na configuração global que está **fora** das políticas de Links seguros. Para obter instruções, consulte [Definir configurações globais para configurações de Links seguros no Microsoft Defender para Office 365.](configure-global-settings-for-safe-links.md)

  No entanto, a proteção de Links seguros  para aplicativos do Office 365 só é aplicada aos usuários incluídos nas políticas de Links seguros ativos. Se um usuário não estiver incluído em uma política de Links seguros ativa, ele não obterá a proteção de Links seguros nos aplicativos do Office 365 com suporte.

  Para obter mais informações sobre a proteção de Links seguros em aplicativos do Office 365, consulte a seção Configurações de Links seguros para aplicativos do [Office 365](#safe-links-settings-for-office-365-apps) posteriormente neste artigo.

Este artigo inclui descrições detalhadas dos seguintes tipos de configurações de Links seguros:

- **Configurações nas políticas de Links** seguros: essas configurações se aplicam somente aos usuários incluídos nas políticas específicas, e as configurações podem ser diferentes entre as políticas. Essas configurações incluem:

  - [Configurações de Links Seguros para mensagens de email](#safe-links-settings-for-email-messages)
  - [Configurações de Links Seguros para o Microsoft Teams](#safe-links-settings-for-microsoft-teams)
  - ["Não reescrever as seguintes URLs" nas políticas de Links seguros](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **Configurações globais de Links seguros:** essas configurações são configuradas globalmente, não em políticas de Links seguros. Porém, as configurações se aplicam somente aos usuários incluídos nas políticas ativas de Links seguros. Essas configurações incluem:

  - [Configurações de Links Seguros para aplicativos do Office 365](#safe-links-settings-for-office-365-apps)
  - [Lista "Bloquear as URLs a seguir" para Links Seguros](#block-the-following-urls-list-for-safe-links)

A tabela a seguir descreve cenários de Links Seguros em organizações do Microsoft 365 e office 365 que incluem o Defender para Office 365 (em outras palavras, a falta de licenciamento nunca é um problema nos exemplos).

****

|Cenário|Resultado|
|---|---|
|Ela é membro do departamento de marketing. A proteção de Links seguros para aplicativos do Office 365 está conexões globais para Links seguros, e existe uma política de Links seguros que se aplica a membros do departamento de marketing. Clara abre uma apresentação do PowerPoint em uma mensagem de email e clica em uma URL da apresentação.|A empresa está protegida por Links Seguros. <p> Ela está incluída em uma política de Links seguros, e a proteção de Links seguros para aplicativos do Office 365 está conexões. <p> Para obter mais informações sobre os requisitos para a proteção de Links seguros em aplicativos do Office 365, consulte a seção Configurações de Links Seguros para aplicativos do [Office 365](#safe-links-settings-for-office-365-apps) posteriormente neste artigo.|
|A organização do Microsoft 365 E5 de Chris não tem políticas de Links seguros configuradas. Chris recebe um email de um remetente externo que contém uma URL para um site mal-intencionado em que, por fim, ele clica.|Chris não está protegido por Links seguros. <p> Um administrador deve criar pelo menos uma política de Links seguros para qualquer pessoa obter a proteção de Links seguros em mensagens de email de entrada. Chris deve ser incluído nas condições da política para obter a proteção de Links seguros.|
|Na organização do Pat, nenhum administrador criou nenhuma política de Links seguros, mas a proteção de Links seguros para aplicativos do Office 365 está conexões. Pat abre um documento do Word e clica em uma URL no arquivo.|Pat não está protegido por Links Seguros. <p> Embora a proteção de Links Seguros para aplicativos do Office 365 seja ativado globalmente, Pat não está incluído em nenhuma política de Links seguros ativa, portanto, a proteção não pode ser aplicada.|
|Na organização de Lee, é configurado na lista Bloquear as URLs a seguir nas configurações `https://tailspintoys.com` globais de Links Seguros.  Já existe uma política de Links seguros que inclui Lee. Lee recebe uma mensagem de email que contém a URL `https://tailspintoys.com/aboutus/trythispage` . Lee clica na URL.|A URL pode ser bloqueada automaticamente para Lee; depende da entrada da URL na lista e do cliente de email que Lee usou. Para obter mais informações, consulte [a lista "Bloquear as URLs a seguir"](#block-the-following-urls-list-for-safe-links) para a seção Links seguros posteriormente neste artigo.|
|Ela e Julia trabalham para contoso.com. Há muito tempo, os administradores configuraram políticas de Links seguros que se aplicam a Ela e à Julia. Ela envia um email para Julia, sem saber que o email contém uma URL mal-intencionada.|Julia será protegida por **Links** seguros se a política de Links seguros que se aplica a ela estiver configurada para ser aplicada a mensagens entre destinatários internos. Para obter mais informações, consulte a seção [Configurações de Links seguros](#safe-links-settings-for-email-messages) para mensagens de email posteriormente neste artigo.|

## <a name="safe-links-settings-for-email-messages"></a>Configurações de Links Seguros para mensagens de email

Links seguros examina emails de entrada em busca de hiperlinks mal-intencionados conhecidos. As URLs digitalizados são reescritas usando o prefixo de URL padrão da Microsoft: `https://nam01.safelinks.protection.outlook.com` . Depois que o link é reescrito, ele é analisado para conteúdo potencialmente mal-intencionado.

Depois que o link seguro regrava uma URL, a URL permanece reescrita mesmo se a mensagem for *encaminhada ou* respondida manualmente (a destinatários internos e externos). Links adicionais que são adicionados à mensagem encaminhada ou respondida não são regravados. No entanto, no  caso de encaminhamento automático por regras de Caixa de Entrada ou encaminhamento SMTP, a  URL não será regravada na mensagem destinada ao destinatário final, a menos que esse destinatário também esteja protegido por Links seguros ou a URL já tenha sido reescrita em uma comunicação anterior. 

As configurações nas políticas de Links seguros que se aplicam a mensagens de email são descritas na lista a seguir:

- **Selecione a ação para URLs** potencialmente mal-intencionadas desconhecidas em mensagens: Habilita ou desabilita a verificação de Links Seguros em mensagens de email. O valor recomendado é **On**. A adoção dessa configuração resulta nas seguintes ações.

  - A verificação de Links seguros está habilitada no Outlook (C2R) no Windows.
  - As URLs são regravadas e os usuários são roteados através da proteção de Links seguros quando clicam em URLs nas mensagens.
  - Quando clicado, as URLs são verificadas em relação a uma lista de URLs mal-intencionadas conhecidas e à lista ["Bloquear as URLs a seguir".](#block-the-following-urls-list-for-safe-links)
  - As URLs que não têm uma reputação válida são acionada de forma assíncrona em segundo plano.

- **Aplique a verificação** de URL em tempo real para links suspeitos e links que apontem para arquivos: permite a verificação em tempo real de links, incluindo links em mensagens de email que apontam para conteúdo baixável. O valor recomendado está habilitado.

  - **Aguarde a conclusão da verificação de URL antes de entregar a mensagem:**

    - Habilitado: as mensagens que contêm URLs são mantidas até que a verificação seja concluída. As mensagens são entregues somente depois que as URLs são confirmadas como seguras. Esse é o valor recomendado.
    - Desabilitado: se a verificação de URL não puder ser concluída, entregue a mensagem mesmo assim.

- **Aplicar Links** Seguros a mensagens de email enviadas dentro da organização: Habilita ou desabilita a verificação de Links Seguros em mensagens enviadas entre os destinatários internos e os destinatários internos dentro da mesma organização do Exchange Online. O valor recomendado está habilitado.

- **Não rastreia cliques do** usuário: Habilita ou desabilita o armazenamento de dados de clique de Links seguros para URLs clicadas em mensagens de email. O valor recomendado é deixar essa configuração deseleitada (para acompanhar cliques do usuário).

  Atualmente, não há suporte para o rastreamento de cliques de URL para links em mensagens de email enviadas entre os destinatários internos e os destinatários internos.

- **Não permita que os usuários cliquem** na URL original: permite ou impede que os usuários cliquem na página de aviso [para](#warning-pages-from-safe-links) a URL original. O valor recomendado está habilitado.

- **Não reescreva as seguintes URLs:** deixa as URLs como estão. Mantém uma lista personalizada de URLs seguras que não precisam de verificação. A lista é exclusiva para cada política de Links seguros. Para obter mais informações sobre a lista De não reescrever a lista de **URLs** a seguir, consulte as listas "Não reescrever as [seguintes URLs"](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) na seção políticas de Links seguros mais adiante neste artigo.

Para obter mais informações sobre os valores recomendados para as configurações de política Padrão e Estrito para políticas de Links Seguros, consulte as configurações de política [de Links seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)

- **Filtros de** destinatário: você precisa especificar as condições e exceções de destinatário que determinam a quem a política se aplica. Você pode usar essas propriedades para condições e exceções:

  - **O destinatário é**
  - **O domínio do destinatário é**
  - **O destinatário é um membro de**

  Você só pode usar uma condição ou exceção uma vez, mas a condição ou exceção pode conter vários valores. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

- **Prioridade:** se você criar várias políticas, poderá especificar a ordem em que elas serão aplicadas. Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.

  Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).

### <a name="how-safe-links-works-in-email-messages"></a>Como os Links Seguros funcionam em mensagens de email

Em um nível alto, veja como a proteção de Links seguros funciona em URLs em mensagens de email:

1. Todos os emails passam pelo EOP, onde os filtros de protocolo IP (IP) e envelope, proteção contra malware baseada em assinatura, filtros anti-spam e anti-malware antes da mensagem ser entregue à caixa de correio do destinatário.

2. O usuário abre a mensagem em sua caixa de correio e clica em uma URL na mensagem.

3. Os Links seguros verificam imediatamente a URL antes de abrir o site:

   - Se a URL estiver incluída na lista Bloquear **a lista de URLs** a seguir, um aviso [de URL bloqueado será](#blocked-url-warning) aberto.

   - Se a URL aponta para um site que foi determinado como mal-intencionado, uma página de aviso de [site](#malicious-website-warning) mal-intencionado (ou uma página de aviso diferente) é aberta.

   - Se a URL apontar para um arquivo baixável e a verificação da URL aplicar em tempo real para links suspeitos e **links** que apontam para a configuração de arquivos estiver habilitada na política que se aplica ao usuário, o arquivo baixável será verificado.

   - Se a URL for determinada como segura, o site será aberto.

## <a name="safe-links-settings-for-microsoft-teams"></a>Configurações de Links Seguros para o Microsoft Teams

> [!IMPORTANT]
> A partir de março de 2020, esse recurso está na visualização e está disponível somente para membros do Tap (Programa de Adoção de Tecnologia) do Microsoft Teams. Para obter informações sobre o cronograma de lançamento, confira o [mapa do Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)

Você habilita ou desabilita a proteção de Links seguros para o Microsoft Teams nas políticas de Links seguros. Especificamente, você usa a ação Selecionar a ação para **URLs desconhecidas ou potencialmente mal-intencionadas na configuração do Microsoft Teams.** O valor recomendado é **On**.

As seguintes configurações nas políticas de Links seguros que se aplicam a links em mensagens de email também se aplicam a links no Teams:

- **Aplicar verificação de URL em tempo real para links suspeitos e links que apontam para arquivos**
- **Não rastrear cliques do usuário**
- **Não permitir que os usuários cliquem na URL original**

Essas configurações são explicadas nas configurações anteriores [de Links seguros para mensagens de email.](#safe-links-settings-for-email-messages)

Depois de ativar a proteção de Links seguros para o Microsoft Teams, as URLs no Teams são verificadas em relação a uma lista de links mal-intencionados conhecidos quando o usuário protegido clica no link (proteção de hora de clique). AS URLs não são regravadas. Se um link for considerado mal-intencionado, os usuários terão as seguintes experiências:

- Se o link foi clicado em uma conversa do Teams, chat em grupo ou de canais, a página de aviso, conforme mostrado na captura de tela abaixo, aparecerá no navegador da Web padrão.
- Se o link foi clicado em uma guia fixada, a página de aviso aparecerá na interface do Teams dentro dessa guia. A opção de abrir o link em um navegador da Web está desabilitada por motivos de segurança.
- Dependendo de como a configuração da **URL original** não permitir que os usuários cliquem na política estiver configurada, o usuário poderá ou não clicar na URL original ( Continue mesmo assim **(não recomendado)** na captura de tela). Recomendamos que você habilita a configuração Não permitir que os usuários cliquem na **url original** para que os usuários não possam clicar na URL original.

Se o usuário que enviou o link não estiver incluído em uma política de Links seguros onde a proteção do Teams está habilitada, o usuário poderá clicar na URL original em seu computador ou dispositivo.

![Uma página Links seguros para o Teams que relata um link mal-intencionado.](../../media/tp-safe-links-for-teams-malicious.png)

Clicar no botão **Voltar na** página de aviso retornará o usuário ao seu contexto original ou local da URL. No entanto, clicar no link original novamente fará com que os Links Seguros rescanm a URL, para que a página de aviso reaparecer.

### <a name="how-safe-links-works-in-teams"></a>Como os Links Seguros funcionam no Teams

Em um nível alto, veja como a proteção de Links seguros funciona para URLs no Microsoft Teams:

1. Um usuário inicia o aplicativo Teams.

2. O Microsoft 365 verifica se a organização do usuário inclui o Microsoft Defender para Office 365 e se o usuário está incluído em uma política de Links seguros ativa onde a proteção do Microsoft Teams está habilitada.

3. As URLs são validadas no momento do clique para o usuário em chats, chats em grupo, canais e guias.

## <a name="safe-links-settings-for-office-365-apps"></a>Configurações de Links Seguros para aplicativos do Office 365

A Proteção de Links Seguros para aplicativos do Office 365 verifica links em documentos do Office, não links em mensagens de email (mas pode verificar links em documentos anexados do Office em mensagens de email após o documento ser aberto).

A Proteção de Links Seguros para aplicativos do Office 365 tem os seguintes requisitos de cliente:

- Microsoft 365 Apps ou Microsoft 365 Business Premium.
  - Versões atuais do Word, Excel e PowerPoint no Windows, Mac ou em um navegador da Web.
  - Aplicativos do Office em dispositivos iOS ou Android.
  - Visio no Windows.
  - OneNote em um navegador da Web.

- Os aplicativos do Office 365 estão configurados para usar a autenticação moderna. Para saber mais, confira Como funciona a autenticação moderna para aplicativos cliente do [Office 2013, Office 2016 e Office 2019.](../../enterprise/modern-auth-for-office-2013-and-2016.md)

- Os usuários são assinados usando suas contas de trabalho ou de estudante. Para saber mais, confira [Entrar no Office.](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)

Você configura a proteção de Links seguros para aplicativos do Office 365 nas configurações globais de Links seguros, não nas políticas de Links seguros. Porém, para que a proteção de Links seguros para aplicativos do Office 365 seja aplicada, o usuário que abre o documento do Office e clica no link deve estar incluído em uma política de Links seguros ativa.

As seguintes configurações de Links seguros estão disponíveis para aplicativos do Office 365:

- **Aplicativos do Office 365:** Habilita ou desabilita a verificação de Links Seguros em aplicativos do Office 365 com suporte. O valor padrão e recomendado é **On**.

- **Não rastreia** quando os usuários clicam em Links Seguros: Habilita ou desabilita o armazenamento de dados de clique de Links seguros para URLs clicadas nas versões da área de trabalho Word, Excel, PowerPoint e Visio. O valor recomendado é **Desligado,** o que significa que os cliques do usuário são rastreados.

- Não permita que os usuários cliquem em links seguros para a [](#warning-pages-from-safe-links) **URL original:** permite ou impede que os usuários cliquem na página de aviso para a URL original nas versões da área de trabalho Word, Excel, PowerPoint e Visio. O valor padrão e recomendado é **On**.

Para definir as configurações de Links seguros para aplicativos do Office 365, confira Configurar a proteção de Links seguros para aplicativos [do Office 365.](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)

Para obter mais informações sobre os valores recomendados para as configurações de política Padrão e Estrito, consulte [Configurações globais para Links seguros.](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links)

### <a name="how-safe-links-works-in-office-365-apps"></a>Como os Links Seguros funcionam em aplicativos do Office 365

Em um nível alto, veja como funciona a proteção de Links seguros para URLs em aplicativos do Office 365. Os aplicativos do Office 365 com suporte são descritos na seção anterior.

1. Um usuário se ins loco usando sua conta comercial ou de estudante em uma organização que inclui o Microsoft 365 Apps ou o Microsoft 365 Business Premium.

2. O usuário abre e clica em um link de um documento do Office em um aplicativo do Office com suporte.

3. Os Links seguros verificam imediatamente a URL antes de abrir o site de destino:

   - Se a URL estiver incluída na lista que ignora a verificação de Links seguros (a lista bloquear a lista de **URLs** a seguir), uma página de aviso de [URL bloqueada](#blocked-url-warning) será aberta.

   - Se a URL aponta para um site que foi determinado como mal-intencionado, uma página de aviso de [site](#malicious-website-warning) mal-intencionado (ou uma página de aviso diferente) é aberta.

   - Se a URL apontar para um arquivo baixável e a política de Links seguros que se aplica ao usuário estiver configurada para verificar links para conteúdo baixável ( Aplicar verificação de URL em tempo real para links suspeitos e **links** que apontem para arquivos), o arquivo baixável será verificado.

   - Se a URL for considerada segura, o usuário será levado para o site.

   - Se a verificação de Links seguros não puder ser concluída, a proteção de Links seguros não será disparada. Nos clientes da área de trabalho do Office, o usuário será avisado antes de prosseguir para o site de destino.

> [!NOTE]
> Pode levar alguns segundos no início de cada sessão para verificar se o usuário tem links seguros para o Office habilitados.

## <a name="block-the-following-urls-list-for-safe-links"></a>Lista "Bloquear as URLs a seguir" para Links Seguros

A **lista Bloquear as URLs** a seguir define os links que sempre são bloqueados pela verificação de Links seguros nos seguintes locais:

- Mensagens de email.
- Documentos em aplicativos do Office 365 no Windows e Mac.
- Documentos no Office para iOS e Android.

Quando um usuário em uma política de Links seguros ativa clica em um link bloqueado em um aplicativo suportado, ele é levado para a página de aviso [da URL bloqueada.](#blocked-url-warning)

Defina a lista de URLs nas configurações globais de Links seguros. Para obter instruções, [consulte Configurar a lista "Bloquear as URLs a seguir".](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)

**Observações**:

- Para uma lista realmente universal de URLs bloqueadas em todos os lugares, consulte Gerenciar a Lista de [Bloqueios/Permitir Locatários.](tenant-allow-block-list.md)

- Limites:
  - O número máximo de entradas é 500.
  - O comprimento máximo de uma entrada é de 128 caracteres.
  - Todas as entradas não podem exceder 10.000 caracteres.

- Não inclua uma barra ( `/` ) no final da URL. Por exemplo, use `https://www.contoso.com` , não `https://www.contoso.com/` .

- Uma URL somente de domínio (por exemplo `contoso.com` ou `tailspintoys.com` ) bloqueará qualquer URL que contenha o domínio.

- Você pode bloquear um subdomínio sem bloquear o domínio completo. Por exemplo, bloqueia qualquer URL que contenha o subdomínio, mas não bloqueia `toys.contoso.com*` URLs que contenham o domínio `contoso.com` completo.

- Você pode incluir até três caracteres curinga ( `*` ) por entrada de URL.

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>Sintaxe de entrada para a lista "Bloquear as URLs a seguir"

Exemplos dos valores que você pode inserir e seus resultados são descritos na tabela a seguir:

****

|Valor|Resultado|
|---|---|
|`contoso.com` <p> ou <p> `*contoso.com*`|Bloqueia o domínio, sub-domínios e caminhos. Por exemplo, `https://www.contoso.com` , `https://sub.contoso.com` e são `https://contoso.com/abc` bloqueados.|
|`https://contoso.com/a`|Bloqueia, `https://contoso.com/a` mas não subcaminhos adicionais como `https://contoso.com/a/b` .|
|`https://contoso.com/a*`|Blocos `https://contoso.com/a` e subcaminhos adicionais como `https://contoso.com/a/b` .|
|`https://toys.contoso.com*`|Bloqueia um subdomínio (neste exemplo), mas permite cliques em outras `toys` URLs de domínio (como `https://contoso.com` ou `https://home.contoso.com` ).|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>"Não reescrever as seguintes URLs" nas políticas de Links seguros

> [!NOTE]
> Se sua organização usa políticas de Links seguros, as listas de **URLs** a seguir não são o único método com suporte para testes de phishing de terceiros.

Cada política de Links Seguros contém uma lista Não reescrever a lista de **URLs** a seguir, que você pode usar para especificar URLs que não são regravadas pela verificação de Links seguros. Em outras palavras, a lista permite que os usuários incluídos na política acessem as URLs especificadas que, de outra forma, seriam bloqueadas por Links seguros. Você pode configurar listas diferentes em diferentes políticas de Links seguros. O processamento de políticas é interrompido após a primeira política (provavelmente, a prioridade mais alta) ser aplicada ao usuário. Portanto, apenas uma **lista de URLs** a seguir não é aplicada a um usuário incluído em várias políticas de Links seguros ativas.

Para adicionar entradas à lista em políticas de Links seguros novas ou existentes, consulte Criar políticas de [Links](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) seguros ou modificar políticas [de Links seguros.](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)

**Observações**:

- Os clientes a seguir não reconhecem as listas De não reescrever **as seguintes URLs** nas políticas de Links seguros. Os usuários incluídos nas polícias podem ser impedidos de acessar as URLs com base nos resultados da verificação de Links seguros nesses clientes:

  - Microsoft Teams
  - Aplicativos Web do Office

  Para uma lista realmente universal de URLs que são permitidas em todos os lugares, consulte Gerenciar a [lista de permissão/bloqueio do locatário.](tenant-allow-block-list.md)

- Considere adicionar URLs internas comumente usadas à lista para melhorar a experiência do usuário. Por exemplo, se você tiver serviços locais, como o Skype for Business ou o SharePoint, poderá adicionar essas URLs para exclui-las da verificação.

- Se você ainda não reescreve as seguintes entradas de **URLs** em suas políticas de Links seguros, revise as listas e adicione caracteres curinga conforme necessário. Por exemplo, sua lista tem uma entrada como e, mais tarde, você `https://contoso.com/a` decide incluir subcaminhos como `https://contoso.com/a/b` . Em vez de adicionar uma nova entrada, adicione um caractere curinga à entrada existente para que ela se `https://contoso.com/a/*` torne.

- Você pode incluir até três caracteres curinga ( `*` ) por entrada de URL. Caracteres curinga incluem explicitamente prefixos ou sub-vírgulas. Por exemplo, a entrada não é a mesma que , porque permite que as pessoas visite `contoso.com` `*.contoso.com/*` `*.contoso.com/*` subdomains e caminhos no domínio especificado.

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>Sintaxe de entrada para a lista "Não reescrever as URLs a seguir"

Exemplos dos valores que você pode inserir e seus resultados são descritos na tabela a seguir:

****

|Valor|Resultado|
|---|---|
|`contoso.com`|Permite o acesso a `https://contoso.com` sub-vírgulas ou caminhos, mas não a eles.|
|`*.contoso.com/*`|Permite o acesso a um domínio, sub-domínios e caminhos (por exemplo, `https://www.contoso.com` `https://www.contoso.com` , ou `https://maps.contoso.com` `https://www.contoso.com/a` ). <p> Essa entrada é inerentemente melhor do que `*contoso.com*` , porque não permite sites potencialmente fraudulentos, como `https://www.falsecontoso.com` ou `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Permite o acesso `https://contoso.com/a` a, mas não subcaminhos como `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Permite o acesso a `https://contoso.com/a` e subcaminhos como `https://contoso.com/a/b`|
|

## <a name="warning-pages-from-safe-links"></a>Páginas de aviso de Links seguros

Esta seção contém exemplos das várias páginas de aviso que são acionadas pela proteção de Links seguros quando você clica em uma URL.

Observe que várias páginas de aviso foram atualizadas. Se você ainda não estiver vendo as páginas atualizadas, você o fará em breve. As páginas atualizadas incluem um novo esquema de cores, mais detalhes e a capacidade de prosseguir para um site apesar do aviso e recomendações determinados.

### <a name="scan-in-progress-notification"></a>Notificação de verificação em andamento

A URL clicada está sendo examinada por Links Seguros. Talvez seja necessário aguardar alguns instantes antes de tentar o link novamente.

![Notificação "O link está sendo verificado"](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

A página de notificação original era assim:

![Notificação original "O link está sendo verificado"](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a>Aviso de mensagem suspeita

A URL clicada estava em uma mensagem de email semelhante a outras mensagens suspeitas. Recomendamos que você verifique a mensagem de email antes de prosseguir para o site.

![Aviso "Um link foi clicado de uma mensagem suspeita"](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a>Aviso de tentativa de phishing

A URL clicada estava em uma mensagem de email que foi identificada como um ataque de phishing. Como resultado, todas as URLs na mensagem de email são bloqueadas. Recomendamos que você não prossiga para o site.

![Aviso "O link foi clicado em uma mensagem de phishing"](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a>Aviso de site mal-intencionado

A URL clicada aponta para um site que foi identificado como mal-intencionado. Recomendamos que você não prossiga para o site.

![Aviso "Este site é classificado como mal-intencionado"](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

A página de aviso original era assim:

![Aviso original "Este site foi classificado como mal-intencionado"](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a>Aviso de URL bloqueada

A URL clicada foi bloqueada manualmente por um administrador em sua organização (a lista Bloquear as **URLs** a seguir nas configurações globais de Links Seguros). O link não foi verificado por Links Seguros porque foi bloqueado manualmente.

Há vários motivos pelos quais um administrador bloquearia manualmente URLs específicas. Se você acha que o site não deve ser bloqueado, entre em contato com o administrador.

![Aviso "Este site foi bloqueado por seu administrador"](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

A página de aviso original era assim:

![Aviso original "Este site foi bloqueado de acordo com a política de URL da sua organização"](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a>Aviso de erro

Ocorreu algum tipo de erro e a URL não pode ser aberta.

![Aviso "A página que você está tentando acessar não pode ser carregada"](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

A página de aviso original era assim:

![Aviso original "Esta página da Web não pôde ser carregada"](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
