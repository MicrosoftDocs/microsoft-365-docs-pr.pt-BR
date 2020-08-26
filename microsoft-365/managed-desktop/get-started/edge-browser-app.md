---
title: O novo Microsoft Edge
description: ''
keywords: navegador, área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 089d9dc79da568a43c1d5701d7bc52d9bed0f4f5
ms.sourcegitcommit: c76c025fe75cd9c06eccbf9c7fc887b09da36659
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "46903866"
---
# <a name="new-microsoft-edge-app"></a>Novo aplicativo do Microsoft Edge

O novo [Microsoft Edge browser](https://www.microsoft.com/edge) oferece desempenho de classe internacional com mais privacidade, mais produtividade e mais valor ao navegar. A área de trabalho gerenciada da Microsoft está oferecendo uma visualização pública da implantação do novo navegador de borda em seu ambiente.

## <a name="initial-deployment"></a>Implantação inicial

Para migrar seus dispositivos de área de trabalho gerenciada da Microsoft para o novo navegador da Microsoft Edge, arquivo um tíquete de suporte de ti através do portal do Microsoft Managed desktop. Implantaremos o canal de borda estável no grupo de teste quando você arquivar o tíquete e implantá-lo em cada grupo de implantação subsequente a cada 24 horas. Para pausar a implantação, arquivo outro tíquete pedindo que as operações sejam mantidas.

O [canal beta](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) também está disponível na solicitação de validação representativa em sua organização. A área de trabalho gerenciada da Microsoft implantará o aplicativo conforme necessário para o teste e os primeiros grupos para que todos os usuários tenham o canal Beta além do canal estável. Para qualquer usuário adicional que precise acessar o canal beta, adicione-o ao grupo de **usuários beta de borda de trabalho moderna** e faça com que eles sejam instalados do portal da empresa

## <a name="updates-to-microsoft-edge"></a>Atualizações para o Microsoft Edge

O Microsoft Managed desktop implanta o [canal estável](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) do Microsoft Edge que é atualizado automaticamente a cada seis semanas. As atualizações no canal estável são distribuídas [progressivamente](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) pelo grupo de produtos do Microsoft Edge para garantir a melhor experiência para os clientes. 

O [canal beta](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) é implantado para dispositivos nos primeiros grupos e teste para validação representativa dentro da organização. Este canal é totalmente compatível e é atualizado automaticamente com novos recursos aproximadamente a cada seis semanas.

Para garantir que o Microsoft Edge atualize corretamente, não modifique as políticas de [atualização](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)do Microsoft Edge.

### <a name="microsoft-edge-beta-channel"></a>Canal beta do Microsoft Edge


## <a name="settings-managed-by-microsoft-managed-desktop"></a>Configurações gerenciadas pela área de trabalho gerenciada da Microsoft

A área de trabalho gerenciada da Microsoft criou um conjunto de políticas padrão para o Microsoft Edge para proteger o navegador. As configurações padrão do navegador são as seguintes:

### <a name="microsoft-edge-extensions"></a>Extensões do Microsoft Edge

A linha de base de segurança do Microsoft Edge nos dispositivos de área de trabalho gerenciada da Microsoft define duas diretivas para desabilitar todas as extensões Chrome e usuários finais seguros. Para habilitar e implantar extensões no ambiente, Confira as configurações que você gerencia. 

#### <a name="extension-installation-blocklist"></a>Bloqueio de instalação de extensão
**Valor padrão:** Todos os

O Microsoft Managed desktop define essa política para impedir que as extensões Chrome sejam instaladas em pontos de extremidade gerenciados. Há riscos conhecidos associados ao modelo de extensão do Chromium, incluindo proteção contra perda de dados, privacidade e outros riscos que podem comprometer os dispositivos. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Permitir hosts de mensagens nativas no nível do usuário (instalado sem permissões de administrador)

**Valor padrão:** Deficiência

Ao desabilitar essa política, o Microsoft Edge usará apenas hosts de mensagens nativos instalados no nível do sistema. Os hosts de mensagens nativos fazem parte de extensões Chrome que permitem que o navegador interaja com outras partes do ponto de extremidade do usuário, criando uma variedade de questões de segurança.  

### <a name="secure-sockets-layer-ssl"></a> Secure Sockets Layer (SSL) 

#### <a name="minimum-ssl-version"></a>Versão mínima do SSL

**Valor padrão:** TLS mínimo 1,2 suportado

Se quiser usar o TLS menos seguro 1,1, você pode solicitar isso.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Permite que os usuários continuem na página de aviso de SSL

**Valor padrão:** Deficiência

Não é recomendável habilitar essa configuração, pois ela permite que os usuários visitem sites com erros de SSL.

### <a name="microsoft-defender-smartscreen"></a>Microsoft defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>Configurar o Windows Defender SmartScreen

**Valor padrão:** Permiti

Habilitado por padrão para ajudar a proteger os usuários finais.

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Prompts do Windows Defender SmartScreen para sites

**Valor padrão:** Permiti

Não recomendamos desabilitar essa configuração, pois isso permitiria que os usuários ignorem avisos e continuassem para sites potencialmente mal-intencionados.

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>Evitar o bypass de avisos do Windows Defender SmartScreen sobre downloads

**Valor padrão:** Permiti

Não recomendamos desabilitar essa configuração, pois isso permitirá que os usuários ignorem avisos e concluam os downloads não verificados.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Configuração padrão do Adobe Flash

**Valor padrão:** Deficiência

Não é recomendável usar o flash por causa dos riscos de segurança associados. Se você ainda tiver processos que dependem do flash, defina a política **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** para habilitar o flash para sites que precisam dele. Se você não puder manter uma lista de sites permitidos para usar o flash, execute uma solicitação de alteração para alterar o valor para **clique em reproduzir**, o que permite que os usuários escolham quando for apropriado executar o flash.

### <a name="password-manager"></a>Gerenciador de senhas

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Habilitar o salvamento de senhas no Gerenciador de senhas

**Valor padrão:** Deficiência

Não recomendamos permitir que os usuários finais salvem senhas em seus dispositivos.

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Modo do Internet Explorer no Microsoft Edge
O modo IE no Microsoft Edge facilita o uso de todos os sites que sua organização precisa em um único navegador. Ele usa o mecanismo integrado do Chromium para sites que são compatíveis com o mecanismo de renderização do Chromium e usa o mecanismo Trident MSHTML do Internet Explorer 11 (IE11) para sites que não estão ou que têm dependências na funcionalidade do IE. [Saiba mais] (https://docs.microsoft.com/DeployEdge/edge-ie-mode) 

A área de trabalho gerenciada da Microsoft habilita o modo do Internet Explorer para seus dispositivos por padrão 

#### <a name="internet-explorer-mode-integration"></a>Integração de modo do Internet Explorer
**Valor padrão:** Modo do Internet Explorer

Por padrão, os dispositivos são definidos para usar o modo do Internet Explorer, mas você pode defini-los para abrir sites em uma janela do Internet Explorer 11 independente. Para alterar isso, arquivo a solicitação de suporte.

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>Adicionar sites à lista de sites do modo empresarial
Para que os sites sejam abertos no modo do Internet Explorer, você deve incluí-los na [lista de sites corporativos](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist). Manter e implantar a lista de sites corporativos é sua responsabilidade. Para obter detalhes, consulte [Configurar usando a política de lista de sites do modo empresarial](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>Outras configurações

#### <a name="enable-site-isolation-for-every-site"></a>Habilitar o isolamento de sites para cada site

**Valor padrão:** Permiti

Quando essa política está habilitada, os usuários não podem recusar o comportamento padrão em que cada site é executado em seu próprio processo.

#### <a name="supported-authentication-schemes"></a>Esquemas de autenticação suportados

**Valor padrão:** NTLM, negociar

A área de trabalho gerenciada da Microsoft não suporta esquemas de autenticação básicos ou Digest.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Importar automaticamente os dados e as configurações de outro navegador na primeira execução

**Valor padrão:** Importar automaticamente todos os tipos de DataTipo e configurações compatíveis do navegador padrão 

Com essa política aplicada, a experiência de primeira execução ignorará a seção de importação, minimizando a interação do usuário. Os dados do navegador de versões mais antigas do Microsoft Edge serão sempre migrados silenciosamente na primeira execução, independentemente dessa configuração. 


## <a name="settings-you-manage"></a>Configurações que você gerencia

Você pode implantar qualquer configuração do Microsoft Edge não descrita anteriormente usando o perfil de modelos administrativos no Microsoft Intune. Para obter detalhes, consulte [configurar as configurações de política do Microsoft Edge com o Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune). Se você deseja avaliar uma política que não está incluída atualmente nos modelos administrativos do Microsoft Edge no Intune, é possível usar configurações personalizadas para dispositivos Windows 10 no Intune.

### <a name="enabling-specific-chrome-extensions"></a>Habilitar extensões Chrome específicas

O modelo administrativo oferece uma configuração para implantar extensões Chrome particulares com o Microsoft Intune. Você pode encontrá-lo na **configuração do computador > extensões de > do Microsoft Edge > permitir que extensões específicas sejam instaladas**.

### <a name="install-extensions-silently"></a>Instalar extensões silenciosamente

Você também pode usar o modelo administrativo para definir o Microsoft Edge para instalar extensões sem alertar o usuário. Você pode encontrá-lo na **configuração do computador > extensões de > do Microsoft Edge > controlar quais extensões são instaladas**de modo silencioso.

### <a name="microsoft-edge-update-policies"></a>Políticas de atualização do Microsoft Edge
Para garantir que o Microsoft Edge atualize corretamente, não modifique as políticas de [atualização](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)do Microsoft Edge.

### <a name="other-common-enterprise-policies"></a>Outras políticas corporativas comuns

O Microsoft Edge oferece uma grande quantidade de políticas adicionais. Estes são alguns dos mais comuns:
 
- [Configurar sites na lista de sites corporativos e no modo IE](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [Configurar definições de inicialização, página inicial e nova página de guias](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Definir a configuração de jogo de navegação](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [Definir configurações de servidor proxy](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

