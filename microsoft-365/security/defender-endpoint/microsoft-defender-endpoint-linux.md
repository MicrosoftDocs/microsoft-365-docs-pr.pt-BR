---
title: Microsoft Defender para Ponto de Extremidade para Linux
ms.reviewer: ''
description: Descreve como instalar e usar o Microsoft Defender ATP para Linux.
keywords: microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: cc2f5be700395f6d88c05481d74501f4d9d92b76
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500669"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a>Microsoft Defender para Ponto de Extremidade para Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Este tópico descreve como instalar, configurar, atualizar e usar o Microsoft Defender para Endpoint para Linux.

> [!CAUTION]
> A execução de outros produtos de proteção de ponto de extremidade de terceiros juntamente com o Microsoft Defender para Ponto de Extremidade para Linux provavelmente levará a problemas de desempenho e efeitos colaterais imprevisíveis. Se a proteção de ponto de extremidade que não é da Microsoft for um requisito absoluto em seu ambiente, você ainda poderá aproveitar com segurança o Defender para a funcionalidade EDR do Ponto de Extremidade para Linux depois de configurar a funcionalidade antivírus para ser executado no modo [Passivo.](linux-preferences.md#enable--disable-passive-mode)

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a>Como instalar o Microsoft Defender para Ponto de Extremidade para Linux

### <a name="prerequisites"></a>Pré-requisitos

- Acesso ao portal do Centro de Segurança do Microsoft Defender
- Distribuição linux usando o [system](https://systemd.io/) manager do sistema
- Experiência de nível iniciante em scripts Linux e BASH
- Privilégios administrativos no dispositivo (em caso de implantação manual)

### <a name="installation-instructions"></a>Instruções de instalação

Há vários métodos e ferramentas de implantação que você pode usar para instalar e configurar o Microsoft Defender para Endpoint para Linux.

Em geral, você precisa seguir as seguintes etapas:

- Verifique se você tem uma assinatura do Microsoft Defender para Ponto de Extremidade e se tem acesso ao portal do [Microsoft Defender para Ponto de Extremidade.](microsoft-defender-security-center.md)
- Implante o Microsoft Defender para Ponto de Extremidade para Linux usando um dos seguintes métodos de implantação:
  - A ferramenta de linha de comando:
    - [Implantação manual](linux-install-manually.md)
  - Ferramentas de gerenciamento de terceiros:
    - [Implantar usando a ferramenta de gerenciamento de configuração do Puppet](linux-install-with-puppet.md)
    - [Implantar usando a ferramenta de gerenciamento de configuração Ansible](linux-install-with-ansible.md)

Se você tiver alguma falha de instalação, consulte [Troubleshooting installation failures in Microsoft Defender for Endpoint for Linux](linux-support-install.md).

### <a name="system-requirements"></a>Requisitos do sistema

- Versões e distribuições de servidor Linux com suporte:

  - Red Hat Enterprise Linux 7.2 ou superior
  - CentOS 7.2 ou superior
  - Ubuntu 16.04 LTS ou LTS superior
  - Debian 9 ou superior
  - SUSE Linux Enterprise Server 12 ou superior
  - Oracle Linux 7.2 ou superior

- Kernel mínimo versão 3.10.0-327
- A `fanotify` opção kernel deve estar habilitada
  > [!CAUTION]
  > Não há suporte para executar o Defender para Ponto de Extremidade para Linux lado a lado com outras soluções `fanotify` de segurança baseadas. Pode levar a resultados imprevisíveis, incluindo a suspensão do sistema operacional.

- Espaço em disco: 1 GB
- /opt/microsoft/mdatp/sbin/wdavdaemon requer permissão executável. Para obter mais informações, consulte "Verifique se o daemon tem permissão executável" em Solucionar problemas de instalação do [Microsoft Defender ATP para Linux](/microsoft-365/security/defender-endpoint/linux-support-install).
- Memória: 1 GB
    > [!NOTE]
    > Verifique se você tem espaço livre em disco no /var.

- Atualmente, a solução fornece proteção em tempo real para os seguintes tipos de sistema de arquivos:

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

Depois de habilitar o serviço, talvez seja necessário configurar sua rede ou firewall para permitir conexões de saída entre ele e seus pontos de extremidade.

- A estrutura de auditoria ( `auditd` ) deve estar habilitada.
  > [!NOTE]
  > Os eventos do sistema capturados por regras `/etc/audit/rules.d/` adicionadas serão adicionados a (s) e poderão afetar a auditoria de host e `audit.log` a coleção upstream. Os eventos adicionados pelo Microsoft Defender para Ponto de Extremidade para Linux serão marcados com `mdatp` chave.

### <a name="network-connections"></a>Conexões de rede

A planilha baixável a seguir lista os serviços e as URLs associadas às quais sua rede deve ser capaz de se conectar. Você deve garantir que não haja regras de filtragem de rede ou firewall que negariam o acesso a essas URLs. Se houver, talvez seja necessário criar uma regra *de* autorização especificamente para elas.

|**Planilha de lista de domínios**|**Descrição**|
|:-----|:-----|
|![Imagem em miniatura da planilha URLs do Microsoft Defender para Endpoint](images/mdatp-urls.png)<br/>  | Planilha de registros DNS específicos para locais de serviço, localizações geográficas e sistema operacional. <br><br>[Baixe a planilha aqui.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> Para obter uma lista de URL mais específica, consulte [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).

O Defender for Endpoint pode descobrir um servidor proxy usando os seguintes métodos de descoberta:
- Proxy transparente
- Configuração de proxy estático manual

Se um proxy ou firewall estiver bloqueando o tráfego anônimo, certifique-se de que o tráfego anônimo seja permitido nas URLs listadas anteriormente. Para proxies transparentes, nenhuma configuração adicional é necessária para o Defender para o Ponto de Extremidade. Para proxy estático, siga as etapas em [Configuração de Proxy Estático Manual](linux-static-proxy-configuration.md).

> [!WARNING]
> Pac, WPAD e proxies autenticados não são suportados. Verifique se apenas um proxy estático ou um proxy transparente está sendo usado.
>
> Os proxies de inspeção e interceptação de SSL também não são suportados por motivos de segurança. Configure uma exceção para a inspeção SSL e seu servidor proxy passar diretamente os dados do Defender para o Ponto de Extremidade para Linux para as URLs relevantes sem interceptação. Adicionar seu certificado de interceptação ao armazenamento global não permitirá interceptação.

Para etapas de solução de problemas, consulte Solucionar problemas de conectividade de nuvem [para o Microsoft Defender para Endpoint para Linux](linux-support-connectivity.md).

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a>Como atualizar o Microsoft Defender para Ponto de Extremidade para Linux

A Microsoft publica regularmente atualizações de software para melhorar o desempenho, a segurança e fornecer novos recursos. Para atualizar o Microsoft Defender para Ponto de Extremidade para Linux, consulte [Deploy updates for Microsoft Defender for Endpoint for Linux](linux-updates.md).

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a>Como configurar o Microsoft Defender para Ponto de Extremidade para Linux

As diretrizes sobre como configurar o produto em ambientes corporativos estão disponíveis em [Definir preferências](linux-preferences.md)do Microsoft Defender para Ponto de Extremidade para Linux .

## <a name="resources"></a>Recursos

- Para obter mais informações sobre log, desinstalação ou outros tópicos, consulte [Resources](linux-resources.md).
