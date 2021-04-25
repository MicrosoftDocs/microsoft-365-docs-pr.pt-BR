---
title: Criar indicadores para arquivos
ms.reviewer: ''
description: Crie indicadores para um hash de arquivo que define a detecção, a prevenção e a exclusão de entidades.
keywords: file, hash, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 103f5d0ad9d12a37f3a3b8065f39c24d592cc252
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995052"
---
# <a name="create-indicators-for-files"></a>Criar indicadores para arquivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Impedir a propagação de um ataque em sua organização proibindo arquivos potencialmente mal-intencionados ou malwares suspeitos. Se você conhecer um arquivo executável portátil potencialmente mal-intencionado (PE), poderá bloqueá-lo. Essa operação impedirá que ela seja lida, escrita ou executada em dispositivos em sua organização.

Há três maneiras de criar indicadores para arquivos:

- Criando um indicador por meio da página de configurações
- Criando um indicador contextual usando o botão adicionar indicador na página de detalhes do arquivo
- Criando um indicador por meio da [API de indicador](ti-indicator.md)

## <a name="before-you-begin"></a>Antes de começar

É importante entender os seguintes pré-requisitos antes da criação de indicadores para arquivos:

- Esse recurso estará disponível se sua organização usar **o Microsoft Defender Antivírus (no** modo ativo) e a proteção baseada em **nuvem estiver habilitada.** Para obter mais informações, consulte [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).

- A versão do cliente Antimalware deve ser 4.18.1901.x ou posterior. Consulte [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

- Compatível com dispositivos com Windows 10, versão 1703 ou posterior, Windows Server 2016 e 2019.

- Para começar a bloquear arquivos, primeiro você precisa ativar o [recurso "bloquear ou permitir"](advanced-features.md) em Configurações.

Esse recurso foi projetado para impedir que o malware suspeito (ou arquivos potencialmente mal-intencionados) seja baixado da Web. Atualmente, ele dá suporte a arquivos executáveis portáteis (PE), incluindo arquivos .exe e .dll. A cobertura será estendida ao longo do tempo.

## <a name="create-an-indicator-for-files-from-the-settings-page"></a>Criar um indicador para arquivos na página de configurações

1. No painel de navegação, selecione **Configurações > Indicadores**.

2. Selecione a **guia Hash de**   arquivo.

3. Selecione **Adicionar indicador**.

4. Especifique os seguintes detalhes:
    - Indicador - Especifique os detalhes da entidade e defina a expiração do indicador.
    - Ação - Especifique a ação a ser tomada e forneça uma descrição.
    - Escopo - Definir o escopo do grupo de dispositivos.

5. Revise os detalhes na guia Resumo e selecione **Salvar**.

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a>Criar um indicador contextual na página de detalhes do arquivo

Uma das opções ao tomar ações [de resposta em um arquivo é](respond-file-alerts.md)adicionar um indicador para o   arquivo. Quando você adiciona um hash de indicador para um arquivo, você pode optar por levantar um alerta e bloquear o arquivo sempre que um dispositivo em sua organização tentar execute-o.

Os arquivos bloqueados automaticamente por um indicador não aparecerão no Centro de Ações do arquivo, mas os alertas ainda estarão visíveis na fila alertas.

>[!IMPORTANT]
>- Normalmente, os blocos de arquivos são impostos e removidos em alguns minutos, mas podem levar mais de 30 minutos.
>- Se houver políticas de indicador de arquivo conflitantes, a política de imposição da política mais segura será aplicada. Por exemplo, uma política de indicador de hash de arquivo SHA-256 tem precedência sobre uma política de indicador de hash de arquivo MD5 se ambos os tipos de hash definirem o mesmo arquivo.
>- Se a política de grupo EnableFileHashComputation estiver desabilitada, a precisão de bloqueio do IoC de arquivo será reduzida. No entanto, habilitar EnableFileHashComputation pode afetar o desempenho do dispositivo.
>    - Por exemplo, copiar arquivos grandes de um compartilhamento de rede em seu dispositivo local, especialmente em uma conexão VPN, pode ter um efeito no desempenho do dispositivo.
>    - Para obter mais informações sobre a política de grupo EnableFileHashComputation, consulte [Defender CSP](/windows/client-management/mdm/defender-csp)

## <a name="policy-conflict-handling"></a>Tratamento de conflitos de política  

O conflito de tratamento de política de Certificado e IoC de arquivo seguirá a seguinte ordem:

- Se o arquivo não for permitido Windows Defender Controle de Aplicativo e AppLocker impor políticas/políticas de modo, **então Bloquear**

- Se o arquivo for permitido pela Exclusão antivírus do Defender, **então Permitir**

- Se o arquivo for bloqueado ou avisado por um IoC de arquivo de bloqueio ou aviso, **bloquear/avisar**

- Se o arquivo for permitido por uma política de IOC de arquivo permitido, **então Permitir**

- Senão, se o arquivo for bloqueado por regras ASR, CFA, AV, SmartScreen **e,** em seguida, Bloquear  

- Else **Allow** (passa Windows Defender controle de aplicativo & política appLocker, nenhuma regra IoC se aplica a ela)

Se houver políticas de IoC de arquivo conflitantes com o mesmo tipo de imposição e destino, a política do hash mais seguro (ou seja, mais longo) será aplicada. Por exemplo, uma política de IoC de hash de arquivo SHA-256 vencerá uma política de IoC de hash de arquivo MD5 se ambos os tipos de hash definirem o mesmo arquivo.

Observe que os recursos de aplicativos vulneráveis do gerenciamento de ameaças e vulnerabilidades usam os IoCs de arquivo para imposição e seguirão a ordem de tratamento de conflitos acima.

### <a name="examples"></a>Exemplos

|Componente |Imposição de componentes |Ação do indicador de arquivo |Resultado
|--|--|--|--|
|Exclusão do caminho do arquivo de redução de superfície de ataque |Permitir |Bloquear |Bloquear
|Regra de redução de superfície de ataque |Bloquear |Permitir |Permitir
|Controle de Aplicativos do Windows Defender |Permitir |Bloquear |Permitir |
|Controle de Aplicativos do Windows Defender |Bloquear |Permitir |Bloquear
|Exclusão do Microsoft Defender Antivírus |Permitir |Bloquear |Permitir

## <a name="see-also"></a>Confira também

- [Criar indicadores](manage-indicators.md)
- [Criar indicadores para IPs e URLs/domínios](indicator-ip-domain.md)
- [Criar indicadores com base em certificados](indicator-certificates.md)
- [Gerenciar indicadores](indicator-manage.md)
