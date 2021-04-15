---
title: Requisitos do dispositivo
description: Resumo dos requisitos mínimos de hardware e software para dispositivos trabalharem com a Área de Trabalho Gerenciada da Microsoft
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: baaebd185389e7ac1f2173aed092141067a5629f
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768885"
---
# <a name="device-requirements"></a>Requisitos do dispositivo

A Área de Trabalho Gerenciada da Microsoft avalia regularmente os requisitos de dispositivo a serem incluídos no serviço. Este artigo descreve os requisitos de hardware e software que um dispositivo deve atender para trabalhar com a Área de Trabalho Gerenciada da Microsoft. Você pode revisar uma lista de dispositivos específicos já [aprovados](device-list.md) para uso com o serviço com base nesses requisitos.

> [!NOTE]
> Esses requisitos podem mudar a qualquer momento, mas forneceremos aviso de 30 dias sobre quaisquer alterações de requisitos de hardware. Os requisitos alterados mais recentemente são marcados com **\*** . 

## <a name="check-hardware-requirements"></a>Verificar requisitos de hardware

Além de revisar as especificações do dispositivo, você também pode usar o verificador de avaliação de preparação para download para verificar se um determinado dispositivo atende aos requisitos necessários. [](../get-ready/readiness-assessment-downloadable.md) Esta ferramenta também verifica configurações de rede e pontos de extremidade que também são necessários para que o serviço funcione.

## <a name="minimum-requirements"></a>Requisitos mínimos

Para estar inscrito na Área de Trabalho Gerenciada da Microsoft, um dispositivo deve atender ou exceder todos esses requisitos.

### <a name="manufacturer"></a>Fabricante

O dispositivo deve ter sido feito por um desses fabricantes:

- Dell
- HP
- Lenovo
- Microsoft


### <a name="installed-software"></a>Software instalado

O dispositivo deve ter esse software pré-instalado:

- Windows 10 Enterprise, Pro ou Pro Workstation edition
- a versão de 64 bits do Microsoft 365 Apps para empresas 
- Todos os drivers de dispositivo aplicáveis


### <a name="physical-features"></a>Recursos físicos

Os dispositivos devem ter esses recursos:

- Habilitado para inicialização segura UEFI 
- Trusted Platform Module 2.0 
- Capaz de segurança baseada em virtualização 
- Integridade de código protegido por [hipervisor](/windows-hardware/drivers/bringup/device-guard-and-credential-guard) com suporte do BIOS

Para saber mais sobre esses recursos e as tecnologias relacionadas a eles que o serviço usa, consulte [Tecnologias da Área de Trabalho Gerenciada da Microsoft.](../intro/technologies.md)

> [!NOTE]
> ARM processadores não são suportados.

Os dispositivos devem atender ou exceder os seguintes limites para armazenamento e memória:

- A unidade de inicialização deve ser qualquer tipo diferente de um disco rígido. Por exemplo, unidades SSD, NVMe e eMMC são opções válidas.
- A unidade de inicialização deve ter uma capacidade de pelo menos 128 GB.
- A memória interna do dispositivo (RAM) deve ser igual ou superior a 8 GB.

Se o dispositivo foi feito após 1º de julho de 2020, ele também deve ter uma câmera DE IR, um leitor de impressão digital ou ambos, para dar suporte ao [Windows Hello.](/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)

## <a name="recommended-features"></a>Recursos recomendados

Seus usuários terão uma experiência muito melhor se você escolher dispositivos com esses recursos:

- Um processador intel vPro-platform ou um processador AMD Ryzen Pro
- Unidade de inicialização do tipo SSD com uma capacidade de pelo menos 256 GB
- Memória interna do dispositivo (RAM) de pelo menos 16 GB
- Suporte para Espera Moderna
- O dispositivo é do tipo de computador protegido
- Oferece suporte à Proteção de DMA kernel
