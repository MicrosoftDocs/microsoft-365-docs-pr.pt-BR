---
title: Microsoft Defender ATP para Mac
ms.reviewer: ''
description: Saiba como instalar, configurar, atualizar e usar o Microsoft Defender para Ponto de Extremidade para Mac.
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6af8a6e0e23201f3c5861cb6a28b2bffa0f04ea4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186432"
---
# <a name="microsoft-defender-for-endpoint-for-mac"></a>Microsoft Defender para Ponto de Extremidade para Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Este tópico descreve como instalar, configurar, atualizar e usar o Defender para Ponto de Extremidade para Mac.

> [!CAUTION]
> A execução de outros produtos de proteção de ponto de extremidade de terceiros juntamente com o Defender for Endpoint para Mac provavelmente levará a problemas de desempenho e efeitos colaterais imprevisíveis. Se a proteção de ponto de extremidade que não é da Microsoft for um requisito absoluto em seu ambiente, você ainda poderá aproveitar com segurança a funcionalidade MDATP para Mac EDR depois de configurar a funcionalidade de antivírus do MDATP para Mac para ser executado no modo [Passivo.](mac-preferences.md#enable--disable-passive-mode)

## <a name="whats-new-in-the-latest-release"></a>Novidades na versão mais recente

[Novidades no Microsoft Defender para Ponto de Extremidade](whats-new-in-microsoft-defender-atp.md)

[Novidades no Microsoft Defender para Ponto de Extremidade para Mac](mac-whatsnew.md)

> [!TIP]
> Se você tiver algum comentário que gostaria de compartilhar, envie-o abrindo o Microsoft Defender para Ponto de Extremidade para Mac em seu dispositivo e navegando para Ajudar a  >  **enviar comentários.**

Para obter os recursos mais recentes, incluindo recursos de visualização (como detecção de ponto de extremidade e resposta para seus dispositivos Mac), configure seu dispositivo macOS executando o Microsoft Defender para Ponto de Extremidade como um dispositivo "Insider".

## <a name="how-to-install-microsoft-defender-for-endpoint-for-mac"></a>Como instalar o Microsoft Defender para Ponto de Extremidade para Mac

### <a name="prerequisites"></a>Pré-requisitos

- Uma assinatura do Defender para Ponto de Extremidade e acesso ao portal do Centro de Segurança do Microsoft Defender
- Experiência de nível iniciante em scripts macOS e BASH
- Privilégios administrativos no dispositivo (em caso de implantação manual)

### <a name="installation-instructions"></a>Instruções de instalação

Há vários métodos e ferramentas de implantação que você pode usar para instalar e configurar o Defender para Ponto de Extremidade para Mac.

- Ferramentas de gerenciamento de terceiros:
    - [Implantação baseada no Microsoft Intune](mac-install-with-intune.md)
    - [Implantação baseada em JAMF](mac-install-with-jamf.md)
    - [Outros produtos MDM](mac-install-with-other-mdm.md)

- Ferramenta de linha de comando:
    - [Implantação manual](mac-install-manually.md)

### <a name="system-requirements"></a>Requisitos do sistema

As três versões principais mais recentes do macOS são suportadas.

> [!IMPORTANT]
> No macOS 11 (Big Sur), o Microsoft Defender para Endpoint requer perfis de configuração adicionais. Se você for um cliente existente atualizando de versões anteriores do macOS, certifique-se de implantar os perfis de configuração adicionais listados em Novos perfis de configuração para [macOS Catalina](mac-sysext-policies.md)e versões mais recentes do macOS .

> [!IMPORTANT]
> O suporte para macOS 10.13 (High Sierra) será descontinuado em 15 de fevereiro de 2021.

- 11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave), 10.13 (Alta Sierra)
- Espaço em disco: 1 GB

Não há suporte para versões beta do macOS.

Depois de habilitar o serviço, talvez seja necessário configurar sua rede ou firewall para permitir conexões de saída entre ele e seus pontos de extremidade.

### <a name="licensing-requirements"></a>Requisitos de licença

O Microsoft Defender para Ponto de Extremidade para Mac requer uma das seguintes ofertas de Licenciamento por Volume da Microsoft:

- Microsoft 365 E5 (M365 E5)
- Segurança do Microsoft 365 E5
- Microsoft 365 A5 (M365 A5)

> [!NOTE]
> Os usuários licenciados qualificados podem usar o Microsoft Defender para Ponto de Extremidade em até cinco dispositivos simultâneos.
> O Microsoft Defender para Ponto de Extremidade também está disponível para compra de um Provedor de Soluções na Nuvem (CSP). Quando comprado por meio de um CSP, ele não exige ofertas de Licenciamento por Volume da Microsoft listadas.

### <a name="network-connections"></a>Conexões de rede

A planilha baixável a seguir lista os serviços e as URLs associadas às quais sua rede deve ser capaz de se conectar. Você deve garantir que não haja regras de filtragem de rede ou firewall que neguem o acesso *a* essas URLs, ou talvez seja necessário criar uma regra de autorização especificamente para elas.



|**Planilha de lista de domínios**|**Descrição**|
|:-----|:-----|
|![Imagem em miniatura da planilha URLs do Microsoft Defender para Endpoint](images/mdatp-urls.png)<br/>  | Planilha de registros DNS específicos para locais de serviço, localizações geográficas e sistema operacional. <br><br>Baixe a planilha aqui: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).

O Microsoft Defender para Ponto de Extremidade pode descobrir um servidor proxy usando os seguintes métodos de descoberta:
- Configuração automática de proxy (PAC)
- Protocolo de Descoberta Automática de Proxy da Web (WPAD)
- Configuração de proxy estático manual

Se um proxy ou firewall estiver bloqueando o tráfego anônimo, certifique-se de que o tráfego anônimo seja permitido nas URLs listadas anteriormente.

> [!WARNING]
> Proxies autenticados não são suportados. Verifique se apenas PAC, WPAD ou um proxy estático estão sendo usados.
>
> Os proxies de inspeção e interceptação de SSL também não são suportados por motivos de segurança. Configure uma exceção para a inspeção SSL e seu servidor proxy passar diretamente os dados do Microsoft Defender para o Ponto de Extremidade para Mac para as URLs relevantes sem interceptação. Adicionar seu certificado de interceptação ao armazenamento global não permitirá interceptação.

Para testar se uma conexão não está bloqueada, abra [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) e em um navegador.

Se preferir a linha de comando, você também poderá verificar a conexão executando o seguinte comando no Terminal:

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

A saída deste comando deve ser semelhante ao seguinte:

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> Recomendamos que você mantenha [a Proteção de Integridade do Sistema](https://support.apple.com/en-us/HT204899) (SIP) habilitada em dispositivos cliente. SIP é um recurso de segurança do macOS integrado que impede a adulteração de baixo nível no sistema operacional e é habilitado por padrão.

Depois que o Microsoft Defender for Endpoint estiver instalado, a conectividade poderá ser validada executando o seguinte comando no Terminal:
```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-for-mac"></a>Como atualizar o Microsoft Defender para Ponto de Extremidade para Mac

A Microsoft publica regularmente atualizações de software para melhorar o desempenho, a segurança e fornecer novos recursos. Para atualizar o Microsoft Defender para Ponto de Extremidade para Mac, um programa chamado Microsoft AutoUpdate (MAU) é usado. Para saber mais, consulte [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md).

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-mac"></a>Como configurar o Microsoft Defender para Ponto de Extremidade para Mac

As diretrizes sobre como configurar o produto em ambientes corporativos estão disponíveis em [Definir preferências](mac-preferences.md)do Microsoft Defender para Ponto de Extremidade para Mac .

## <a name="macos-kernel-and-system-extensions"></a>Extensões do sistema e kernel do macOS

Em alinhamento com a evolução do macOS, estamos preparando uma atualização do Microsoft Defender para Endpoint para Mac que aproveita extensões do sistema em vez de extensões de kernel. Para obter detalhes relevantes, consulte [Novidades no Microsoft Defender para Ponto de Extremidade para Mac](mac-whatsnew.md).

## <a name="resources"></a>Recursos

- Para obter mais informações sobre log, desinstalação ou outros tópicos, consulte [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md).

- [Privacidade do Microsoft Defender para Ponto de Extremidade para Mac](mac-privacy.md).
