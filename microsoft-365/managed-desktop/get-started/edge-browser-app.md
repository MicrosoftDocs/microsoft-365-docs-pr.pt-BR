---
title: O novo Microsoft Edge
description: Explica como o novo navegador de Borda é implantado e atualizado
keywords: browser, Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 2bf1fab504ae77a1e66235f49333c3b123e38904
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822245"
---
# <a name="new-microsoft-edge-app"></a>Novo Microsoft Edge app

O novo [Microsoft Edge oferece](https://www.microsoft.com/edge) um desempenho de classe mundial com mais privacidade, mais produtividade e mais valor enquanto você navega. Área de Trabalho Gerenciada da Microsoft está oferecendo uma visualização pública da implantação do novo navegador de Borda em seu ambiente.

## <a name="initial-deployment"></a>Implantação inicial

Para migrar seus dispositivos Área de Trabalho Gerenciada da Microsoft para o novo navegador Microsoft Edge, arquiva um Tíquete de Suporte de IT por meio do portal Área de Trabalho Gerenciada da Microsoft. Implantaremos o canal Estável de Borda no Grupo de Teste quando você arquivar o tíquete e implantá-lo em cada grupo de implantação subsequente a cada 24 horas. Para pausar a implantação, arquiva outro tíquete solicitando a ressarção de Operações.

O [Canal Beta](/deployedge/microsoft-edge-channels#beta-channel) também está disponível mediante solicitação de validação representativa em sua organização. Área de Trabalho Gerenciada da Microsoft implantará o aplicativo conforme necessário para o Test and First Groups para que todos esses usuários tenham o Canal Beta, além do Canal Estável. Para qualquer outro usuário que precise de acesso ao Canal Beta, adicione-os ao grupo Local de Trabalho Moderno - Usuários **Beta** de Borda e instale-o a partir do Portal da Empresa

## <a name="updates-to-microsoft-edge"></a>Atualizações para Microsoft Edge

Área de Trabalho Gerenciada da Microsoft implanta o [canal estável](/deployedge/microsoft-edge-channels#stable-channel) do Microsoft Edge, que é atualizado automaticamente a cada seis semanas. As atualizações no canal Estável [](/deployedge/microsoft-edge-update-progressive-rollout) são roladas progressivamente pelo grupo de produtos Microsoft Edge para garantir a melhor experiência para os clientes. 

O [Canal Beta é](/deployedge/microsoft-edge-channels#beta-channel) implantado em dispositivos nos grupos Test e First para validação representativa dentro da organização. Esse canal tem suporte total e é atualizado automaticamente com novos recursos aproximadamente a cada seis semanas.

Para garantir que Microsoft Edge atualizações corretamente, não modifique as políticas de Microsoft Edge [de atualização.](/deployedge/microsoft-edge-update-policies)



## <a name="settings-managed-by-microsoft-managed-desktop"></a>Configurações gerenciado por Área de Trabalho Gerenciada da Microsoft

Área de Trabalho Gerenciada da Microsoft criou um conjunto padrão de políticas para Microsoft Edge proteger o navegador. As configurações padrão do navegador são as seguinte:

### <a name="microsoft-edge-extensions"></a>Microsoft Edge extensões

A linha de base de segurança para Microsoft Edge em Área de Trabalho Gerenciada da Microsoft define duas políticas para desabilitar todas as extensões do Chrome e proteger usuários. Para habilitar e implantar extensões em seu ambiente, consulte Configurações gerenciar. 

#### <a name="extension-installation-blocklist"></a>Lista de bloqueios de instalação de extensão
**Valor padrão:** Todos

Área de Trabalho Gerenciada da Microsoft essa política para impedir que extensões do Chrome seja instaladas em pontos de extremidade gerenciados. Há riscos conhecidos associados ao modelo de extensão Chromium, incluindo proteção contra perda de dados, privacidade e outros riscos que podem comprometer dispositivos. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Permitir hosts de mensagens nativos no nível do usuário (instalados sem permissões de administrador)

**Valor padrão:** Desabilitado

Ao desabilitar essa política, Microsoft Edge usará somente hosts de mensagens nativos instalados no nível do sistema. Hosts de mensagens nativos fazem parte das extensões do Chrome, que permitem que o navegador interaja com outras partes do ponto de extremidade do usuário, criando uma variedade de preocupações de segurança.  

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

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender Prompts smartScreen para sites

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

O gerenciador de senhas está desabilitado por padrão. Se você estiver como esse recurso habilitado, arquiva uma solicitação de suporte e nossos engenheiros de serviço podem habilitar a configuração em seu ambiente. 

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Modo Internet Explorer no Microsoft Edge
O modo IE no Microsoft Edge facilita o uso de todos os sites de que sua organização precisa em um único navegador. Ele usa o mecanismo de Chromium integrado para sites compatíveis com o mecanismo de renderização Chromium e usa o mecanismo Trident MSHTML do Internet Explorer 11 (IE11) para sites que não são ou têm dependências da funcionalidade do IE. [Saiba Mais](/DeployEdge/edge-ie-mode) 

Área de Trabalho Gerenciada da Microsoft habilita o modo Internet Explorer para seus dispositivos por padrão 

#### <a name="internet-explorer-mode-integration"></a>Integração do modo Internet Explorer
**Valor padrão:** Modo Internet Explorer

Por padrão, os dispositivos são definidos para usar o modo Internet Explorer, mas você pode defini-los para abrir sites em uma janela autônoma do Internet Explorer 11. Para alterar esse comportamento, arquivar uma solicitação de suporte.

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>Adicionar sites à lista de sites Enterprise modo de usuário
Para que os sites abram no modo Internet Explorer, você deve incluí-los na lista [Enterprise Site.](/DeployEdge/edge-ie-mode-sitelist) Manter e implantar a lista Enterprise Site é sua responsabilidade. Para obter detalhes, consulte [Configure using the Configure Enterprise Mode Site List policy](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>Outras configurações

#### <a name="enable-site-isolation-for-every-site"></a>Habilitar o isolamento de site para cada site

**Valor padrão:** Habilitado

Quando essa política é habilitada, os usuários não podem optar pelo comportamento padrão no qual cada site é executado em seu próprio processo.

#### <a name="supported-authentication-schemes"></a>Esquemas de autenticação com suporte

**Valor padrão:** NTLM, Negociar

Área de Trabalho Gerenciada da Microsoft não dá suporte a esquemas de Autenticação Básica ou Digest.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Importar automaticamente os dados e configurações de outro navegador na primeira executar

**Valor padrão:** Importar automaticamente todos os tipos de dados e configurações com suporte do navegador padrão 

Com essa política aplicada, a Experiência de Primeira Executar ignorará a seção de importação, minimizando a interação do usuário. Os dados do navegador de versões mais antigas Microsoft Edge sempre serão migrados silenciosamente na primeira executar, independentemente dessa configuração. 


## <a name="settings-you-manage"></a>Configurações gerenciar

Você pode implantar qualquer configuração Microsoft Edge não descritas anteriormente usando o perfil Modelos Administrativos no Microsoft Intune. Para obter detalhes, [consulte Configure Microsoft Edge policy settings with Microsoft Intune](/deployedge/configure-edge-with-intune). Se você quiser avaliar uma política que não está incluída no Microsoft Edge Modelos Administrativos no Intune, você pode usar configurações personalizadas para dispositivos Windows 10 no Intune.

### <a name="enabling-specific-chrome-extensions"></a>Habilitando extensões específicas do Chrome

O Modelo Administrativo oferece uma configuração para implantar extensões específicas do Chrome com Microsoft Intune. Você pode encontrá-lo em Configuração do **Computador > Microsoft Edge > Extensões > Permitir que Extensões Específicas sejam instaladas.**

### <a name="install-extensions-silently"></a>Instalar extensões silenciosamente

Você também pode usar o Modelo Administrativo para definir Microsoft Edge para instalar extensões sem alertar o usuário. Você pode encontrá-lo em Configuração do Computador > Microsoft Edge > Extensões > Controlar quais extensões **são instaladas silenciosamente**.

### <a name="microsoft-edge-update-policies"></a>Microsoft Edge políticas de atualização
Para garantir que Microsoft Edge atualizações corretamente, não modifique as políticas de Microsoft Edge [de atualização.](/deployedge/microsoft-edge-update-policies)

### <a name="other-common-enterprise-policies"></a>Outras políticas corporativas comuns

Microsoft Edge oferece muitas outras políticas. Estas são algumas das mais comuns:
 
- [Configurar sites na lista Enterprise site e modo IE](/deployedge/edge-ie-mode-sitelist)
- [Configurar configurações de página inicial, página inicial e nova guia](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Configurar a configuração do jogo de surf](/deployedge/microsoft-edge-policies#allowsurfgame)
- [Configurar configurações de servidor proxy](/deployedge/microsoft-edge-policies#proxy-server)
