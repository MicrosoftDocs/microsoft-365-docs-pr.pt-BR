---
title: Configurar e validar as conexões de rede do Microsoft Defender Antivírus
description: Configure e teste sua conexão com o serviço de proteção de nuvem Microsoft Defender Antivírus.
keywords: antivírus, Microsoft Defender Antivírus, antimalware, segurança, defensor, nuvem, agressividade, nível de proteção
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ef5a9ffdf45a2f8e7f262ae7f969cd19e848b7a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572520"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Configurar e validar as conexões de rede do Microsoft Defender Antivírus

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Para garantir que Microsoft Defender Antivírus proteção fornecida pela nuvem funcione corretamente, você precisa configurar sua rede para permitir conexões entre seus pontos finais e certos servidores Microsoft. Este artigo lista as conexões que devem ser permitidas, como usando regras de firewall, e fornece instruções para validar sua conexão. Configurar sua proteção corretamente ajuda a garantir que você receba o melhor valor de seus serviços de proteção entregues na nuvem.

Veja o post no blog [Mudanças importantes no ponto final](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) do Microsoft Active Protection Services para alguns detalhes sobre a conectividade da rede.

> [!TIP]
> Você também pode visitar o site de demonstração do Microsoft Defender for Endpoint [em demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que os seguintes recursos estão funcionando:
>
> - Proteção fornecida na nuvem
> - Aprendizado rápido (incluindo bloco à primeira vista)
> - Bloqueio de aplicativos potencialmente indesejado

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Permitir conexões com o serviço de nuvem Microsoft Defender Antivírus

O serviço de nuvem Microsoft Defender Antivírus oferece proteção rápida e forte para seus pontos finais. A habilitação do serviço de proteção fornecido pela nuvem é opcional, no entanto, é altamente recomendado porque fornece proteção importante contra malware em seus pontos finais e em toda a sua rede.

> [!NOTE]
> O serviço de nuvem Microsoft Defender Antivírus é um mecanismo para fornecer proteção atualizada à sua rede e pontos finais. Embora seja chamado de serviço de nuvem, não é simplesmente proteção para arquivos armazenados na nuvem, mas usa recursos distribuídos e aprendizado de máquina para fornecer proteção aos seus pontos finais a uma taxa muito mais rápida do que as atualizações tradicionais de inteligência de segurança.

Consulte [Ativar proteção fornecida pela nuvem](enable-cloud-protection-microsoft-defender-antivirus.md) para obter detalhes sobre como habilitar o serviço com Intune, Microsoft Endpoint Configuration Manager, Política de Grupo, cmdlets PowerShell ou em clientes individuais no aplicativo Segurança do Windows. 

Depois de habilitar o serviço, talvez seja necessário configurar sua rede ou firewall para permitir conexões entre ele e seus pontos finais.

Como sua proteção é um serviço em nuvem, os computadores devem ter acesso à internet e acessar o Microsoft Defender para Office 365 serviços de machine learning. Não exclua a URL `*.blob.core.windows.net` de qualquer tipo de inspeção de rede. 

A tabela abaixo lista os serviços e suas URLs associadas. Certifique-se de que não há regras de filtragem de firewall ou rede que neguem acesso a esses URLs, ou você pode precisar criar uma regra de perdoeamento especificamente para eles (excluindo a URL `*.blob.core.windows.net` ). Abaixo mencione os URLs estão usando a porta 443 para comunicação.


| **Serviço**| **Descrição** |**URL** |
| :--: | :-- | :-- |
| Microsoft Defender Antivírus serviço de proteção fornecido pela nuvem, também chamado de Microsoft Active Protection Service (MAPS)|Usado por Microsoft Defender Antivírus para fornecer proteção fornecida pela nuvem|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| Serviço de atualização da Microsoft (MU) <br/> Windows Serviço de atualização (WU)|  Inteligência de segurança e atualizações de produtos   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> Para obter [detalhes, consulte pontos finais de conexão para atualização de Windows](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|Inteligência de segurança atualiza Local de Download Alternativo (ADL)|   Local alternativo para Microsoft Defender Antivírus atualizações de inteligência de segurança se a inteligência de segurança instalada estiver desatualizada (7 ou mais dias atrás)|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| Armazenamento de envio de malware|Upload localização para arquivos submetidos à Microsoft através do formulário submission ou envio automático de amostras    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| Lista de Revogação de Certificados (CRL)|Usado por Windows ao criar a conexão SSL ao MAPS para atualizar o CRL   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| Loja de Símbolos|Usado por Microsoft Defender Antivírus para restaurar certos arquivos críticos durante fluxos de remediação  | `https://msdl.microsoft.com/download/symbols` |
| Cliente de Telemetria Universal| Usado por Windows para enviar dados de diagnóstico do cliente; Microsoft Defender Antivírus usa telemetria para fins de monitoramento da qualidade do produto   | A atualização usa o SSL (TCP Port 443) para baixar manifestos e enviar dados de diagnóstico para a Microsoft que usa os seguintes pontos finais de DNS:   `vortex-win.data.microsoft.com` <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>Validar conexões entre sua rede e a nuvem

Depois de permitir os URLs listados acima, você pode testar se você está conectado ao serviço de nuvem Microsoft Defender Antivírus e está relatando e recebendo informações corretamente para garantir que você esteja totalmente protegido.

**Use a ferramenta cmdline para validar a proteção fornecida pela nuvem:**

Use o seguinte argumento com o utilitário de linha de comando Microsoft Defender Antivírus `mpcmdrun.exe` () para verificar se sua rede pode se comunicar com o serviço de nuvem Microsoft Defender Antivírus:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> Você precisa abrir uma versão de nível de administrador do prompt de comando. Clique com o botão direito do mouse no menu Iniciar, clique em **Executar como administrador** e clique em **Sim** no prompt de permissões. Este comando só funcionará em Windows 10, versão 1703 ou superior.

Para obter mais informações, consulte [Gerenciar Microsoft Defender Antivírus com a ferramenta mpcmdrun.exe linha de comando](command-line-arguments-microsoft-defender-antivirus.md).

**Tentativa de baixar um arquivo de malware falso da Microsoft:**

Você pode baixar um arquivo de amostra que Microsoft Defender Antivírus detectará e bloqueará se estiver conectado corretamente à nuvem.

Baixe o arquivo visitando [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .

> [!NOTE]
> Este arquivo não é um pedaço real de malware. É um arquivo falso que foi projetado para testar se você está conectado corretamente à nuvem.

Se estiver conectado corretamente, verá um aviso Microsoft Defender Antivírus notificação.

Se você estiver usando Microsoft Edge, você também verá uma mensagem de notificação:

![Microsoft Edge informar o usuário que o malware foi encontrado](images/defender/wdav-bafs-edge.png)

Uma mensagem semelhante ocorre se você estiver usando o Internet Explorer:

![Microsoft Defender Antivírus notificação informando ao usuário que o malware foi encontrado](images/defender/wdav-bafs-ie.png)

Você também verá uma detecção sob **ameaças em quarentena** na seção Histórico de **varredura** no aplicativo Segurança do Windows:

1. Abra o aplicativo Segurança do Windows clicando no ícone do escudo na barra de tarefas ou pesquisando no menu iniciar para **segurança**.

2. Selecione **Proteção contra ameaças & vírus** e, em seguida, selecione Histórico de **proteção**.

3. Na seção **Ameaças em quarentena,** selecione **Ver histórico completo** para ver o malware falso detectado.

   > [!NOTE]
   > Versões de Windows 10 antes da versão 1703 têm uma interface de usuário diferente. Veja [Microsoft Defender Antivírus no aplicativo Segurança do Windows](microsoft-defender-security-center-antivirus.md).

   O registro do evento Windows também mostrará [Windows Defender iD do evento cliente 1116](troubleshoot-microsoft-defender-antivirus.md).

## <a name="related-articles"></a>Artigos relacionados

- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)

- [Ativar proteção fornecida pela nuvem](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Argumentos da linha de comando](command-line-arguments-microsoft-defender-antivirus.md)

- [Mudanças importantes no ponto final do Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
