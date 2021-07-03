---
title: Configurar e validar as conexões de rede do Microsoft Defender Antivírus
description: Configure e teste sua conexão com o serviço de proteção Microsoft Defender Antivírus nuvem.
keywords: antivírus, Microsoft Defender Antivírus, antimalware, segurança, defensor, nuvem, agressividade, nível de proteção
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 5b6ed22b38d0795073fc72f380bcad89683ada9c
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286808"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Configurar e validar as conexões de rede do Microsoft Defender Antivírus

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Para garantir Microsoft Defender Antivírus proteção entregue na nuvem funcione corretamente, sua equipe de segurança deve configurar sua rede para permitir conexões entre seus pontos de extremidade e determinados servidores Microsoft. Este artigo lista as conexões que devem ser permitidas, como o uso de regras de firewall, e fornece instruções para validar sua conexão. Configurar sua proteção corretamente ajuda a garantir que você receba o melhor valor de seus serviços de proteção entregues na nuvem.

Consulte a postagem do blog Alterações importantes no ponto de extremidade [do Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) para obter alguns detalhes sobre a conectividade de rede.

> [!TIP]
> Visite o site de demonstração do Microsoft Defender para Ponto de Extremidade [no demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar se os seguintes recursos estão funcionando:
>
> - Proteção fornecida na nuvem
> - Aprendizado rápido (incluindo bloquear à primeira vista)
> - Bloqueio de aplicativo potencialmente indesejado

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Permitir conexões com o serviço Microsoft Defender Antivírus nuvem

O Microsoft Defender Antivírus de nuvem oferece proteção rápida e forte para seus pontos de extremidade. A habilitação do serviço de proteção entregue na nuvem é opcional, no entanto, é altamente recomendável porque fornece proteção importante contra malware em seus pontos de extremidade e em toda a sua rede. Consulte [Habilitar](enable-cloud-protection-microsoft-defender-antivirus.md) a proteção entregue na nuvem para obter detalhes sobre como habilitar o serviço com o Intune, Microsoft Endpoint Configuration Manager, Política de Grupo, cmdlets do PowerShell ou em clientes individuais no aplicativo Segurança do Windows. 

Depois de habilitar o serviço, talvez seja necessário configurar sua rede ou firewall para permitir conexões entre ele e seus pontos de extremidade. Como sua proteção é um serviço de nuvem, os computadores devem ter acesso à Internet e acessar o Microsoft Defender para Office 365 de aprendizado de máquina. Não exclua a URL `*.blob.core.windows.net` de nenhum tipo de inspeção de rede.

> [!NOTE]
> O Microsoft Defender Antivírus de nuvem é um mecanismo para fornecer proteção atualizada para sua rede e pontos de extremidade. Embora seja chamado de serviço de nuvem, ele não é simplesmente proteção para arquivos armazenados na nuvem, em vez disso, usa recursos distribuídos e aprendizado de máquina para fornecer proteção aos seus pontos de extremidade em uma taxa muito mais rápida do que as atualizações tradicionais de inteligência de segurança.

## <a name="services-and-urls"></a>Serviços e URLs

A tabela nesta seção lista os serviços e seus endereços de site associados (URLs). 

Certifique-se de que não haja regras de filtragem de rede ou firewall negando o acesso a essas URLs. Caso contrário, talvez seja necessário criar uma regra de autorização especificamente para elas (excluindo a URL `*.blob.core.windows.net` ). As URLs na tabela a seguir usam a porta 443 para comunicação.

| Serviço e descrição | URL |
|----|---- |
| Microsoft Defender Antivírus serviço de proteção entregue na nuvem, também conhecido como Microsoft Active Protection Service (MAPS)<p>Esse serviço é usado pela Microsoft Defender Antivírus para fornecer proteção entregue na nuvem|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
| Serviço de Atualização da Microsoft (MU) e Windows De Atualização (WU) <p>Esses serviços permitem atualizações de produtos e inteligência de segurança |`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> Para obter mais detalhes, consulte [Pontos de extremidade de conexão para Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|Atualizações de inteligência de segurança Local de Download Alternativo (ADL)<p>Este é um local alternativo para Microsoft Defender Antivírus atualizações de inteligência de segurança se a inteligência de segurança instalada estiver desa data (7 ou mais dias atrasadas)| `*.download.microsoft.com`  <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| Armazenamento de envio de malware <p>Este é o local de carregamento para arquivos enviados à Microsoft por meio do formulário de envio ou envio automático de amostra | `ussus1eastprod.blob.core.windows.net` <p>    `ussus2eastprod.blob.core.windows.net` <p>    `ussus3eastprod.blob.core.windows.net` <p>    `ussus4eastprod.blob.core.windows.net` <p>    `wsus1eastprod.blob.core.windows.net` <p>    `wsus2eastprod.blob.core.windows.net` <p>    `ussus1westprod.blob.core.windows.net` <p>    `ussus2westprod.blob.core.windows.net` <p>    `ussus3westprod.blob.core.windows.net` <p>    `ussus4westprod.blob.core.windows.net` <p>    `wsus1westprod.blob.core.windows.net` <p>    `wsus2westprod.blob.core.windows.net` <p>    `usseu1northprod.blob.core.windows.net` <p>    `wseu1northprod.blob.core.windows.net` <p>    `usseu1westprod.blob.core.windows.net` <p>    `wseu1westprod.blob.core.windows.net` <p>    `ussuk1southprod.blob.core.windows.net` <p>    `wsuk1southprod.blob.core.windows.net` <p>    `ussuk1westprod.blob.core.windows.net` <p>    `wsuk1westprod.blob.core.windows.net` |
| Lista de Revogação de Certificados (CRL) <p>Essa lista é usada por Windows ao criar a conexão SSL com MAPS para atualizar a CRL | `http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p>   `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs` |
| Loja de Símbolos <p>O armazenamento de símbolos é usado Microsoft Defender Antivírus restaurar determinados arquivos críticos durante fluxos de correção | `https://msdl.microsoft.com/download/symbols` |
| Cliente de Telemetria Universal <p>Esse cliente é usado pela Windows para enviar dados de diagnóstico do cliente<p> Microsoft Defender Antivírus usa telemetria para fins de monitoramento de qualidade do produto | A atualização usa SSL (Porta TCP 443) para baixar manifestos e carregar dados de diagnóstico para a Microsoft que usa os seguintes pontos de extremidade DNS: <p> `vortex-win.data.microsoft.com` <p>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>Validar conexões entre sua rede e a nuvem

Depois de permitir as URLs listadas acima, você pode testar se você está conectado ao serviço de nuvem Microsoft Defender Antivírus e está relatando corretamente e recebendo informações para garantir que você esteja totalmente protegido.

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a>Use a ferramenta cmdline para validar a proteção entregue na nuvem

Use o seguinte argumento com o utilitário Microsoft Defender Antivírus linha de comando ( ) para verificar se sua rede pode se comunicar com o serviço Microsoft Defender Antivírus `mpcmdrun.exe` nuvem:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> Você precisa abrir uma versão de nível de administrador do prompt de comando. Clique com o botão direito do mouse no item no menu Iniciar, clique em Executar como **administrador** e clique em **Sim** no prompt de permissões. Esse comando funcionará apenas Windows 10 versão 1703 ou superior.

Para obter mais informações, consulte [Manage Microsoft Defender Antivírus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a>Tentar baixar um arquivo de malware falso da Microsoft

Você pode baixar um arquivo de exemplo que Microsoft Defender Antivírus detectar e bloquear se estiver conectado corretamente à nuvem.

Baixe o arquivo visitando [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .

> [!NOTE]
> Esse arquivo não é um malware real. É um arquivo falso projetado para testar se você está conectado corretamente à nuvem.

Se você estiver conectado corretamente, você verá uma notificação de Microsoft Defender Antivírus aviso.

Se você estiver usando Microsoft Edge, você também verá uma mensagem de notificação:

:::image type="content" source="../../media/wdav-bafs-edge.png" alt-text="Captura de tela da notificação de que o malware foi encontrado no Edge":::

Uma mensagem semelhante ocorrerá se você estiver usando o Internet Explorer:

:::image type="content" source="../../media/wdav-bafs-ie.png" alt-text="Notificação do Microsoft Defender AV de que o malware foi encontrado":::

Você também verá uma detecção em **Ameaças em quarentena** na seção **Histórico** de verificação no Segurança do Windows aplicativo:

1. Abra o Segurança do Windows aplicativo clicando no ícone de escudo na barra de tarefas ou pesquisando o menu iniciar para **Segurança**.

2. Selecione **Proteção contra & vírus** e selecione Histórico de **proteção.**

3. Na seção **Ameaças em quarentena,** selecione **Ver histórico completo** para ver o malware falso detectado.

   > [!NOTE]
   > As versões Windows 10 versão 1703 têm uma interface de usuário diferente. Consulte [Microsoft Defender Antivírus no aplicativo Segurança do Windows .](microsoft-defender-security-center-antivirus.md)

   O Windows de eventos também mostrará Windows Defender ID do evento cliente [1116](troubleshoot-microsoft-defender-antivirus.md).
