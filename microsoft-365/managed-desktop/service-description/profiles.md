---
title: Compreender perfis de dispositivo
description: Os vários perfis que os administradores podem atribuir a dispositivos
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 5b5421d2b4001b813d3bcc1e804cae7fb05d0fa7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841997"
---
# <a name="device-profiles"></a>Perfis do dispositivo

Você pode atribuir configurações pré-definidas diferentes ("perfis de dispositivo") a dispositivos, cada uma otimizada para as necessidades de tipos específicos de usuários. Três perfis de dispositivo estão disponíveis:

- Padrão
- Dados Confidenciais
- Usuário do power

Você pode pensar nos perfis de dispositivo como parte de uma hierarquia de opções de configuração de dispositivo.

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="Configurações de dispositivo mostradas como uma pirâmide. Descrição a seguir":::

Fundamentalmente, cada dispositivo Área de Trabalho Gerenciada da Microsoft tem uma base que inclui uma linha de base de segurança padrão, políticas de conformidade, Windows configurações de atualização e grupos. Para trabalhar com Área de Trabalho Gerenciada da Microsoft, todos os dispositivos devem incluir todos esses elementos, que não podem ser alterados pelos administradores sem uma solicitação para Área de Trabalho Gerenciada da Microsoft.

Os perfis de dispositivo aparecem no próximo nível superior. Cada Área de Trabalho Gerenciada da Microsoft dispositivo deve ter um (e apenas um) perfil atribuído. Os administradores podem escolher qual perfil um dispositivo é atribuído.

Em um nível ainda mais alto, há [personalizações adicionais.](customizing.md) Cada dispositivo pode ter uma ou mais personalizações (ou não). Eles podem modificar uma camada de nível inferior (perfis de dispositivo ou a configuração base) ou ser uma solicitação totalmente nova que é em camadas sobre a configuração padrão.

Na parte superior estão suas próprias modificações, como detalhes da rede ou aplicativos. Um dispositivo pode ter qualquer número dessas modificações, que não são gerenciadas ou bloqueadas por Área de Trabalho Gerenciada da Microsoft.


## <a name="device-profile-details"></a>Detalhes do perfil do dispositivo

A tabela a seguir resume as configurações e seus valores padrão para cada configuração configurada por perfis de dispositivo. (Nos bastidores, essas configurações são configuradas com OMA-URIs usando Perfis de Configuração Personalizados Microsoft Endpoint Manager.)

<br>

****

|Recurso|Dados Confidenciais|Power User|Padrão|
|---|:---:|:---:|:---:|
|**Bloquear o Armazenamento**|Sim|Sim|Não|
|**[Nível de bloqueio na nuvem](/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)**|Alto|Alto|Alto|
|**Desabilitar contas da Microsoft**|Sim|Sim|Não|
|**Desabilitar os OneDrive**|Sim|Sim|Não|
|**Alternar para área de trabalho segura para elevação**|Não|Sim|Não|
|**Marca de dispositivo do Microsoft Defender para Ponto de Extremidade**|M365Managed-SensitiveData|M365Managed-PowerUser|M365Managed-Standard|
|**Administrador no dispositivo?**|Não|Sim|Não|
|**Perfil do Piloto Automático**|MMD Standard|Usuário de Energia MMD|MMD Standard|
|**AppLocker**|Sim|Não|Não|
|**Bloquear o Armazenamento Público**|Sim|Sim|Não|
|

Cada perfil de dispositivo também envolve esses itens:

- Um grupo de dispositivos Azure Active Directory (AAD) de associação dinâmica
- Um grupo de dispositivos AAD de associação estática
- Um Microsoft Endpoint Manager de configuração

> [!IMPORTANT]
> Não modifique diretamente a associação desses grupos. Use a interface conforme descrito em [Reatribuir perfis](../working-with-managed-desktop/change-device-profile.md).

## <a name="limitations"></a>Limitações

Você pode solicitar exceções para os perfis de dispositivo e seus detalhes, como faria com qualquer outra política. Lembre-se de que você só pode ter um de cada perfil de dispositivo em sua Azure Active Directory organização ("locatário"). Por exemplo, você não pode solicitar que o perfil do dispositivo de dados confidenciais desabilite o AppLocker para apenas alguns de seus usuários. Todos os dispositivos com o perfil de dados Confidenciais devem ter a mesma configuração.

Cada dispositivo só pode ter um perfil. Se um determinado dispositivo for usado por mais de um usuário, todos os usuários nesse dispositivo terão a mesma configuração.
