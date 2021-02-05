---
title: Requisitos do dispositivo
description: Resumo dos requisitos mínimos de hardware e software para dispositivos funcionarem com a Área de Trabalho Gerenciada da Microsoft
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a6b5cbbcb2f48797130b080d9d1dd1e6427d4fb8
ms.sourcegitcommit: fa5659cb66d84dcfeebc03b47bd9d38017d8934d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110046"
---
# <a name="device-requirements"></a>Requisitos do dispositivo

A Área de Trabalho Gerenciada da Microsoft avalia regularmente os requisitos de dispositivo para serem incluídos no serviço. Este artigo descreve os requisitos de hardware e software que um dispositivo deve atender para funcionar com a Área de Trabalho Gerenciada da Microsoft. Você pode revisar uma lista de dispositivos [específicos já aprovados](device-list.md) para uso com o serviço com base nesses requisitos.

> [!NOTE]
> Esses requisitos podem mudar a qualquer momento, mas forneceremos um aviso de 30 dias sobre quaisquer alterações de requisitos de hardware. Os requisitos alterados mais recentemente são marcados com **\*** . 

## <a name="check-hardware-requirements"></a>Verificar requisitos de hardware

Além de analisar as especificações do dispositivo, você também pode usar o verificador de avaliação de preparação para download para verificar se um determinado dispositivo atende aos requisitos necessários. [](../get-ready/readiness-assessment-downloadable.md) Essa ferramenta também verifica as configurações de rede e os pontos de extremidade que também são necessários para o serviço funcionar.

## <a name="minimum-requirements"></a>Requisitos mínimos

Para ser inscrito na Área de Trabalho Gerenciada da Microsoft, um dispositivo deve atender ou exceder todos esses requisitos.

### <a name="manufacturer"></a>Fabricante

O dispositivo deve ter sido feito por um destes fabricantes:

- Dell
- HP
- Lenovo
- Microsoft


### <a name="installed-software"></a>Software instalado

O dispositivo deve ter esse software pré-instalado:

- Edição Windows 10 Enterprise, Pro ou Pro Workstation
- a versão de 64 bits do Clique para Executar do Microsoft Office 
- Todos os drivers de dispositivo aplicáveis


### <a name="physical-features"></a>Recursos físicos

Os dispositivos devem ter estes recursos:

- Habilitado para inicialização segura UEFI 
- Trusted Platform Module 2.0 
- Capaz de segurança baseada em virtualização 
- Dá suporte à integridade de código protegida pelo hipervisor 

Para saber mais sobre esses recursos e as tecnologias relacionadas a eles que o serviço usa, consulte Tecnologias da Área de [Trabalho Gerenciada da Microsoft.](../intro/technologies.md)

> [!NOTE]
> Não há suporte para processadores ARM.

Os dispositivos devem cumprir ou exceder os seguintes limites de armazenamento e memória:

- A unidade de inicialização deve ser de qualquer tipo que não seja um disco rígido. Por exemplo, as unidades SSD, NVMe e eMMC são opções válidas.
- A unidade de inicialização deve ter pelo menos 128 GB.

Se o dispositivo tiver sido feito após 1º de julho de 2020, ele também deverá ter uma câmera DE IR, um leitor de impressão digital ou ambos, para dar suporte ao [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)

## <a name="recommended-requirements"></a>Requisitos recomendados

Embora eles não sejam requisitos absolutos, os usuários terão uma experiência muito melhor se você escolher dispositivos com estes recursos:

- Um processador Intel vPro-platform ou um processador AMD Ryzen Pro
- Unidade de inicialização do tipo SSD com uma capacidade de pelo menos 256 GB
- Suporte para modo de espera moderno
- O dispositivo é do tipo de computador de núcleo protegido
- Dá suporte à proteção DMA de kernel
