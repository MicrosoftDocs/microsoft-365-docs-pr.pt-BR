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
ms.openlocfilehash: 4edff7a9c7f541e31363519e4bafc2a21602e011
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054273"
---
# <a name="create-indicators-for-files"></a>Criar indicadores para arquivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Você pode impedir a propagação posterior de um ataque em sua organização, proibindo arquivos potencialmente mal-intencionados ou malwares suspeitos. Se você conhecer um arquivo executável portátil potencialmente mal-intencionado (PE), poderá bloqueá-lo. Essa operação impedirá que ela seja lida, escrita ou executada em máquinas em sua organização.

Há duas maneiras de criar indicadores para arquivos:
- Criando um indicador por meio da página de configurações
- Criando um indicador contextual usando o botão adicionar indicador na página de detalhes do arquivo

### <a name="before-you-begin"></a>Antes de começar
É importante entender os seguintes pré-requisitos antes da criação de indicadores para arquivos:

- Esse recurso estará disponível se sua organização usar Windows Defender proteção baseada em antivírus e nuvem está habilitada. Para obter mais informações, [consulte Use next-generation technologies in Microsoft Defender Antivírus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).
- A versão do cliente Antimalware deve ser 4.18.1901.x ou posterior.
- Suportado em computadores no Windows 10, versão 1703 ou posterior, Windows server 2016 e 2019.
- Para começar a bloquear arquivos, primeiro você precisa ativar o [ **recurso Bloquear ou** permitir](advanced-features.md) em Configurações.
- Esse recurso foi projetado para impedir que o malware suspeito (ou arquivos potencialmente mal-intencionados) seja baixado da Web. Atualmente, ele dá suporte a arquivos executáveis portáteis (PE), incluindo _arquivos .exe_ e _.dll._ A cobertura será estendida ao longo do tempo.

>[!IMPORTANT]
>- A função permitir ou bloquear não pode ser feita em arquivos se a classificação do arquivo existir no cache do dispositivo antes da ação permitir ou bloquear 
>- Os arquivos assinados confiáveis serão tratados de forma diferente. O Defender for Endpoint é otimizado para manipular arquivos mal-intencionados. Tentar bloquear arquivos assinados confiáveis, em alguns casos, pode ter implicações de desempenho.

 
>[!NOTE]
>Normalmente, os blocos de arquivos são imposto dentro de alguns minutos, mas podem levar mais de 30 minutos.

### <a name="create-an-indicator-for-files-from-the-settings-page"></a>Criar um indicador para arquivos na página de configurações

1. No painel de navegação, selecione **Indicadores de**  >  **Configurações**.  

2. Selecione a **guia Hash de** arquivo.

3. Selecione **Adicionar indicador**.

4. Especifique os seguintes detalhes:
   - Indicador - Especifique os detalhes da entidade e defina a expiração do indicador.
   - Ação - Especifique a ação a ser tomada e forneça uma descrição.
   - Escopo - Definir o escopo do grupo de máquinas.

5. Revise os detalhes na guia Resumo e clique em **Salvar**.

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a>Criar um indicador contextual na página de detalhes do arquivo
Uma das opções ao tomar ações [de resposta em um arquivo é](respond-file-alerts.md) adicionar um indicador para o arquivo. 

Quando você adiciona um hash de indicador para um arquivo, você pode optar por levantar um alerta e bloquear o arquivo sempre que um computador em sua organização tentar execute-o.

Os arquivos bloqueados automaticamente por um indicador não aparecerão no Centro de Ações do arquivo, mas os alertas ainda estarão visíveis na fila alertas.


## <a name="related-topics"></a>Tópicos relacionados
- [Criar indicadores](manage-indicators.md)
- [Criar indicadores para IPs e URLs/domínios](indicator-ip-domain.md)
- [Criar indicadores com base em certificados](indicator-certificates.md)
- [Gerenciar indicadores](indicator-manage.md)
