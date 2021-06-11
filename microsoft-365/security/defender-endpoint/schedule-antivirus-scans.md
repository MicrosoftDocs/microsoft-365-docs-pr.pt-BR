---
title: Agendar verificações rápidas e completas regulares com Microsoft Defender Antivírus
description: Configurar verificações recorrentes (agendadas), incluindo quando devem ser executados e se são executados como verificações completas ou rápidas
keywords: verificação rápida, verificação completa, rápida versus completa, verificação de agendamento, diariamente, semanal, hora, agendada, recorrente, regular
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 5566050e4a64713f6f8b4ac2cb4a7188d3a241c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879644"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Configurar verificações rápidas ou completas do Microsoft Defender Antivírus agendadas

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Além de proteção sempre em tempo [](run-scan-microsoft-defender-antivirus.md) real e verificações de antivírus sob demanda, você pode configurar verificações de antivírus regulares agendadas. Você pode configurar o tipo de verificação, quando a verificação deve ocorrer e se [a](manage-protection-updates-microsoft-defender-antivirus.md) verificação deve ocorrer após uma atualização de proteção ou quando um ponto de extremidade não está sendo usado. Você também pode configurar verificações especiais para concluir ações de correção, se necessário.

## <a name="what-do-you-want-to-do"></a>O que você deseja fazer?

- [Saiba mais sobre verificações rápidas, verificações completas e verificações personalizadas](#quick-scan-full-scan-and-custom-scan)
- [Usar a Política de Grupo para agendar verificações antivírus](schedule-antivirus-scans-group-policy.md)
- [Usar Windows PowerShell agendar verificações antivírus](schedule-antivirus-scans-powershell.md)
- [Usar Windows Instrumentação de Gerenciamento para agendar verificações antivírus](schedule-antivirus-scans-wmi.md)

## <a name="keep-the-following-points-in-mind"></a>Lembre-se dos seguintes pontos

- Por padrão, Microsoft Defender Antivírus verifica se há uma atualização 15 minutos antes da hora de quaisquer verificações agendadas. Você pode Gerenciar a agenda para quando as atualizações de proteção devem ser baixadas e [aplicadas](manage-protection-update-schedule-microsoft-defender-antivirus.md) para substituir esse padrão. 

- Se um dispositivo for desconectado e estiver sendo executado na bateria durante uma verificação completa agendada, a verificação agendada será interrompida com o evento 1002, que afirma que a verificação parou antes da conclusão. Microsoft Defender Antivírus executará uma verificação completa na próxima hora agendada.

## <a name="quick-scan-full-scan-and-custom-scan"></a>Verificação rápida, verificação completa e verificação personalizada

Ao configurar verificações agendadas, você pode especificar se a verificação deve ser uma verificação completa ou rápida. Na maioria dos casos, recomenda-se uma verificação rápida. 

| Verificação rápida  | Verificação completa  | Verificação personalizada |
|---------|---------|---------|
| (Recomendado) Uma verificação rápida analisa todos os locais onde pode haver malware registrado para começar com o sistema, como chaves de registro e pastas de inicialização Windows conhecidas. <p>Combinado com a proteção sempre em tempo real, que revisa arquivos quando eles são abertos e fechados e sempre que um usuário navega para uma pasta, uma verificação rápida ajuda a fornecer uma proteção forte contra malware que começa com o sistema e malware no nível do kernel. <p>Na maioria dos casos, uma verificação rápida é suficiente e é a opção recomendada para verificações agendadas. | Uma verificação completa é iniciada executando uma verificação rápida e, em seguida, continua com uma verificação de arquivo sequencial de todos os discos fixos montados e unidades removíveis/de rede (se a verificação completa estiver configurada para fazer isso). <p>Uma verificação completa pode levar algumas horas ou dias para ser concluída, dependendo da quantidade e do tipo de dados que precisam ser verificados.<p>Quando a verificação completa estiver concluída, a nova inteligência de segurança estará disponível e uma nova verificação será necessária para garantir que nenhuma outra ameaça seja detectada com a nova inteligência de segurança. <p>Devido ao tempo e recursos envolvidos em uma verificação completa, em geral, a Microsoft não recomenda agendar verificações completas.  | Uma verificação personalizada é uma verificação rápida que é executado nos arquivos e pastas que você especificar. Por exemplo, você pode optar por examinar uma unidade USB ou uma pasta específica na unidade local do dispositivo. <p> | 

> [!NOTE]
> Por padrão, verificações rápidas são executados em dispositivos removíveis montados, como unidades USB.

## <a name="how-do-i-know-which-scan-type-to-choose"></a>Como saber qual tipo de verificação escolher?

Use a tabela a seguir para escolher um tipo de verificação.

| Cenário  | Tipo de verificação recomendado  |
|---------|---------|
| Você deseja configurar verificações regulares agendadas     | Verificação rápida <p>Uma verificação rápida verifica os processos, memória, perfis e determinados locais no dispositivo. Combinado com [a proteção sempre em tempo real,](configure-real-time-protection-microsoft-defender-antivirus.md)uma verificação rápida ajuda a fornecer uma cobertura forte para malware que começa com o sistema e malware no nível do kernel. A proteção em tempo real revisa arquivos quando são abertos e fechados e sempre que um usuário navega para uma pasta.         |
| Ameaças, como malware, são detectadas em um dispositivo individual     | Verificação rápida <p>Na maioria dos casos, uma verificação rápida detectará e limpará o malware detectado.   |
| Você deseja executar uma verificação [sob demanda](run-scan-microsoft-defender-antivirus.md)     | Verificação rápida       |
| Você deseja garantir que um dispositivo portátil, como uma unidade USB, não contenha malware | Verificação personalizada <p>Uma verificação personalizada permite selecionar locais, pastas ou arquivos específicos e executa uma verificação rápida. |

## <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>O que mais preciso saber sobre verificações rápidas e completas?

- Arquivos mal-intencionados podem ser armazenados em locais que não estão incluídos em uma verificação rápida. No entanto, a proteção sempre em tempo real revisa todos os arquivos abertos e fechados e todos os arquivos que estão em pastas acessadas por um usuário. A combinação de proteção em tempo real e uma verificação rápida ajuda a fornecer uma proteção forte contra malware.

- A proteção ao acessar [com](cloud-protection-microsoft-defender-antivirus.md) a proteção entregue na nuvem ajuda a garantir que todos os arquivos acessados no sistema estão sendo verificados com os modelos de aprendizado de máquina de nuvem e inteligência de segurança mais recentes.

- Quando a proteção em tempo real detecta malware e a extensão dos arquivos afetados não é determinada inicialmente, Microsoft Defender Antivírus inicia uma verificação completa como parte do processo de correção.

- Uma verificação completa pode detectar arquivos mal-intencionados que não foram detectados por outras verificações, como uma verificação rápida. No entanto, uma verificação completa pode demorar um pouco e usar recursos valiosos do sistema para ser concluído.

- Se um dispositivo estiver offline por um longo período de tempo, uma verificação completa poderá levar mais tempo para ser concluída. 

