---
title: O novo Microsoft Edge
description: Explica como o novo navegador de Borda é implantado e atualizado
keywords: browser, Microsoft Managed Desktop, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 033826a7f82278f6e36b422284a1076cba57d584
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921973"
---
# <a name="new-microsoft-edge-app"></a>Novo aplicativo do Microsoft Edge

O novo [navegador do Microsoft Edge](https://www.microsoft.com/edge) fornece desempenho de classe mundial com mais privacidade, mais produtividade e mais valor enquanto você navega. A Área de Trabalho Gerenciada da Microsoft está oferecendo uma visualização pública da implantação do novo navegador de Borda em seu ambiente.

## <a name="initial-deployment"></a>Implantação inicial

Para migrar seus dispositivos da Área de Trabalho Gerenciada da Microsoft para o novo navegador do Microsoft Edge, arquivo um Tíquete de Suporte de IT por meio do Portal da Área de Trabalho Gerenciada da Microsoft. Implantaremos o canal Estável de Borda no Grupo de Teste quando você arquivar o tíquete e implantá-lo em cada grupo de implantação subsequente a cada 24 horas. Para pausar a implantação, arquiva outro tíquete solicitando a ressarção de Operações.

O [Canal Beta](/deployedge/microsoft-edge-channels#beta-channel) também está disponível mediante solicitação de validação representativa em sua organização. A Área de Trabalho Gerenciada da Microsoft implantará o aplicativo conforme necessário para o Test and First Groups para que todos esses usuários tenham o Canal Beta, além do Canal Estável. Para quaisquer outros usuários que precisem de acesso ao Canal Beta, adicione-os ao grupo Locais de Trabalho Moderno - Usuários **Beta** de Borda e instale-os no Portal da Empresa

## <a name="updates-to-microsoft-edge"></a>Atualizações do Microsoft Edge

A Área de Trabalho Gerenciada da Microsoft implanta [o canal Estável](/deployedge/microsoft-edge-channels#stable-channel) do Microsoft Edge, que é atualizado automaticamente a cada seis semanas. As atualizações no canal Estável [](/deployedge/microsoft-edge-update-progressive-rollout) são progressivamente roladas pelo grupo de produtos do Microsoft Edge para garantir a melhor experiência para os clientes. 

O [Canal Beta é](/deployedge/microsoft-edge-channels#beta-channel) implantado em dispositivos nos grupos Test e First para validação representativa dentro da organização. Esse canal tem suporte total e é atualizado automaticamente com novos recursos aproximadamente a cada seis semanas.

Para garantir que o Microsoft Edge seja atualizado corretamente, não modifique as políticas de atualização [do](/deployedge/microsoft-edge-update-policies)Microsoft Edge.



## <a name="settings-managed-by-microsoft-managed-desktop"></a>Configurações gerenciadas pela Área de Trabalho Gerenciada da Microsoft

A Área de Trabalho Gerenciada da Microsoft criou um conjunto padrão de políticas para o Microsoft Edge proteger o navegador. As configurações padrão do navegador são as seguinte:

### <a name="microsoft-edge-extensions"></a>Extensões do Microsoft Edge

A linha de base de segurança do Microsoft Edge em dispositivos da Área de Trabalho Gerenciada da Microsoft define duas políticas para desabilitar todas as extensões do Chrome e proteger usuários. Para habilitar e implantar extensões em seu ambiente, consulte Configurações gerenciadas. 

#### <a name="extension-installation-blocklist"></a>Lista de bloqueios de instalação de extensão
**Valor padrão:** Todos

A Área de Trabalho Gerenciada da Microsoft define essa política para impedir que as extensões do Chrome seja instalada em pontos de extremidade gerenciados. Há riscos conhecidos associados ao modelo de extensão do Chromium, incluindo proteção contra perda de dados, privacidade e outros riscos que podem comprometer dispositivos. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Permitir hosts de mensagens nativos no nível do usuário (instalados sem permissões de administrador)

**Valor padrão:** Desabilitado

Ao desabilitar essa política, o Microsoft Edge usará somente hosts de mensagens nativos instalados no nível do sistema. Hosts de mensagens nativos fazem parte das extensões do Chrome, que permitem que o navegador interaja com outras partes do ponto de extremidade do usuário, criando uma variedade de preocupações de segurança.  

### <a name="secure-sockets-layer-tlsssl"></a>Camada de Soquetes Seguros (TLS/SSL)

#### <a name="minimum-tls-version"></a>Versão TLS mínima

**Valor padrão:** TLS 1.2 mínimo suportado

Se você quiser usar o TLS 1.1 menos seguro, poderá fazer uma solicitação para fazer isso.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Permite que os usuários prossigam da página de aviso SSL

**Valor padrão:** Desabilitado

Não recomendamos a habilitação dessa configuração, pois permite que os usuários visite sites com erros TSL.

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>Configurar Windows Defender SmartScreen

**Valor padrão:** Habilitado

Habilitado por padrão para ajudar a proteger os usuários.

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender prompts do SmartScreen para sites

**Valor padrão:** Habilitado

Não recomendamos desabilitar essa configuração, pois isso permitiria que os usuários ignorassem os avisos e continuassem a sites potencialmente mal-intencionados.

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>Impedir o desvio de Windows Defender avisos do SmartScreen sobre downloads

**Valor padrão:** Habilitado

Não recomendamos desabilitar essa configuração, pois isso permitiria aos usuários ignorar avisos e concluir downloads não verificados.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Configuração padrão do Adobe Flash

**Valor padrão:** Desabilitado

Não recomendamos o uso do Flash devido aos riscos de segurança associados. Se você ainda tiver processos que dependem do Flash, defina a **[política PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** para habilitar o Flash para sites que precisam dele. Se você não puder manter uma lista de sites permitidos para usar o Flash, arquiva uma solicitação de alteração para alterar o valor para **Clique** para Reproduzir , o que permite que os usuários escolham quando é apropriado executar o Flash.

### <a name="password-manager"></a>Gerenciador de senhas

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Habilitar salvar senhas para o gerenciador de senhas

**Valor padrão:** Desabilitado

Não recomendamos permitir que os usuários salvem senhas em seus dispositivos.

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Modo Internet Explorer no Microsoft Edge
O modo IE no Microsoft Edge facilita o uso de todos os sites de que sua organização precisa em um único navegador. Ele usa o mecanismo Chromium integrado para sites compatíveis com o mecanismo de renderização do Chromium e usa o mecanismo Trident MSHTML do Internet Explorer 11 (IE11) para sites que não são ou têm dependências da funcionalidade do IE. [Saiba mais] (https://docs.microsoft.com/DeployEdge/edge-ie-mode) 

A Área de Trabalho Gerenciada da Microsoft habilita o modo Internet Explorer para seus dispositivos por padrão 

#### <a name="internet-explorer-mode-integration"></a>Integração do modo Internet Explorer
**Valor padrão:** Modo Internet Explorer

Por padrão, os dispositivos são definidos para usar o modo Internet Explorer, mas você pode defini-los para abrir sites em uma janela autônoma do Internet Explorer 11. Para alterar esse comportamento, arquivar uma solicitação de suporte.

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>Adicionar sites à lista de Sites do Modo Empresarial
Para que os sites abram no modo Internet Explorer, você deve incluí-los na lista [Site da Empresa.](/DeployEdge/edge-ie-mode-sitelist) Manter e implantar a lista de Sites corporativos é sua responsabilidade. Para obter detalhes, consulte [Configure using the Enterprise Mode Site List policy](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>Outras configurações

#### <a name="enable-site-isolation-for-every-site"></a>Habilitar o isolamento de site para cada site

**Valor padrão:** Habilitado

Quando essa política é habilitada, os usuários não podem optar pelo comportamento padrão no qual cada site é executado em seu próprio processo.

#### <a name="supported-authentication-schemes"></a>Esquemas de autenticação com suporte

**Valor padrão:** NTLM, Negociar

A Área de Trabalho Gerenciada da Microsoft não dá suporte a esquemas de Autenticação Básica ou Digest.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Importar automaticamente os dados e configurações de outro navegador na primeira executar

**Valor padrão:** Importar automaticamente todos os tipos de dados e configurações com suporte do navegador padrão 

Com essa política aplicada, a Experiência de Primeira Executar ignorará a seção de importação, minimizando a interação do usuário. Os dados do navegador de versões mais antigas do Microsoft Edge sempre serão migrados silenciosamente na primeira executar, independentemente dessa configuração. 


## <a name="settings-you-manage"></a>Configurações gerenciadas

Você pode implantar as configurações do Microsoft Edge não descritas anteriormente usando o perfil Modelos Administrativos no Microsoft Intune. Para obter detalhes, consulte [Configure Microsoft Edge policy settings with Microsoft Intune](/deployedge/configure-edge-with-intune). Se você quiser avaliar uma política que não está incluída no momento nos Modelos Administrativos do Microsoft Edge no Intune, você pode usar configurações personalizadas para dispositivos Windows 10 no Intune.

### <a name="enabling-specific-chrome-extensions"></a>Habilitando extensões específicas do Chrome

O Modelo Administrativo oferece uma configuração para implantar extensões específicas do Chrome com o Microsoft Intune. Você pode encontrá-lo em Configuração do Computador > Microsoft Edge > Extensões > Permitir que **extensões específicas sejam instaladas.**

### <a name="install-extensions-silently"></a>Instalar extensões silenciosamente

Você também pode usar o Modelo Administrativo para definir o Microsoft Edge para instalar extensões sem alertar o usuário. Você pode encontrá-lo em Configuração do Computador > Microsoft Edge > Extensões > Controlar quais extensões são **instaladas silenciosamente.**

### <a name="microsoft-edge-update-policies"></a>Políticas de atualização do Microsoft Edge
Para garantir que o Microsoft Edge seja atualizado corretamente, não modifique as políticas de atualização [do](/deployedge/microsoft-edge-update-policies)Microsoft Edge.

### <a name="other-common-enterprise-policies"></a>Outras políticas corporativas comuns

O Microsoft Edge oferece muitas outras políticas. Estas são algumas das mais comuns:
 
- [Configurar sites na lista de sites corporativos e no modo IE](/deployedge/edge-ie-mode-sitelist)
- [Configurar configurações de página inicial, página inicial e nova guia](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Configurar a configuração do jogo de surf](/deployedge/microsoft-edge-policies#allowsurfgame)
- [Configurar configurações de servidor proxy](/deployedge/microsoft-edge-policies#proxy-server)