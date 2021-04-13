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
ms.openlocfilehash: e6b0c96d4e145a2e5df7c7555e262aefe891e483
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689866"
---
# <a name="device-profiles"></a>Perfis de dispositivo

Você pode atribuir configurações pré-definidas diferentes ("perfis de dispositivo") a dispositivos, cada uma otimizada para as necessidades de tipos específicos de usuários. Três perfis de dispositivo estão disponíveis:

- Padrão
- Dados Confidenciais
- Usuário do power

Você pode pensar nos perfis de dispositivo como parte de uma hierarquia de opções de configuração de dispositivo.

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="Configurações de dispositivo mostradas como uma pirâmide. Descrição a seguir":::

Fundamentalmente, todos os dispositivos da Área de Trabalho Gerenciada da Microsoft têm uma base que inclui uma linha de base de segurança padrão, políticas de conformidade, configurações e grupos do Windows Update. Para trabalhar com a Área de Trabalho Gerenciada da Microsoft, todos os dispositivos devem incluir todos esses elementos, que não podem ser alterados pelos administradores sem uma solicitação para a Área de Trabalho Gerenciada da Microsoft.

Os perfis de dispositivo aparecem no próximo nível superior. Cada dispositivo da Área de Trabalho Gerenciada da Microsoft deve ter um (e apenas um) perfil atribuído. Os administradores podem escolher qual perfil um dispositivo é atribuído.

Em um nível ainda mais alto, há [personalizações adicionais.](customizing.md) Cada dispositivo pode ter uma ou mais personalizações (ou não). Eles podem modificar uma camada de nível inferior (perfis de dispositivo ou a configuração base) ou ser uma solicitação totalmente nova que é em camadas sobre a configuração padrão.

Na parte superior estão suas próprias modificações, como detalhes da rede ou aplicativos. Um dispositivo pode ter qualquer número dessas modificações, que não são gerenciadas ou bloqueadas pela Área de Trabalho Gerenciada da Microsoft.


## <a name="device-profile-details"></a>Detalhes do perfil do dispositivo

A tabela a seguir resume as configurações e seus valores padrão para cada configuração configurada por perfis de dispositivo. (Nos bastidores, essas configurações são configuradas com OMA-URIs usando perfis de configuração personalizados no Microsoft Endpoint Manager.)

| Recurso | Dados Confidenciais | Power User | Padrão |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------|------------------------|-----------------------|
| **Bloquear Armazenamento Externo**                                                                                                                               | Sim                       | Sim                   | Não                   |
| **[Nível de bloqueio na nuvem](https://docs.microsoft.com/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)** | Alto                      | Alto                  | Alto                 |
| **Desabilitar contas da Microsoft**                                                                                                                           | Sim                       | Sim                   | Não                   |
| **Desabilitar o OneDrive pessoal**                                                                                                                            | Sim                       | Sim                   | Não                   |
| **Alternar para área de trabalho segura para elevação**                                                                                                               | Não                        | Sim                   | Não                   |
| **Marca de dispositivo do Microsoft Defender para Ponto de Extremidade**                                                                                                           | M365Managed-SensitiveData | M365Managed-PowerUser | M365Managed-Standard |
| **Administrador no dispositivo?**                                                                                                                                 | Não                        | Sim                   | Não                   |
| **Perfil do Piloto Automático**                                                                                                                                     | MMD Standard               | Usuário de Energia MMD         | MMD Standard          |
| **AppLocker**                                                                                                                                            | Sim                       | Não                    | Não                   |
| **Bloquear o Armazenamento Público**                                                                                                                                   | Sim                       | Sim                   | Não                   |

Cada perfil de dispositivo também envolve esses itens:

- Um grupo de dispositivos do Azure Active Directory (AAD) de associação dinâmica
- Um grupo de dispositivos AAD de associação estática
- Um perfil de configuração do Microsoft Endpoint Manager

> [!IMPORTANT]
> Não modifique diretamente a associação desses grupos. Use a interface conforme descrito em [Reatribuir perfis](../working-with-managed-desktop/change-device-profile.md).

## <a name="limitations"></a>Limitações

Você pode solicitar exceções para os perfis de dispositivo e seus detalhes, como faria com qualquer outra política. Lembre-se de que você só pode ter um de cada perfil de dispositivo em sua organização do Azure Active Directory ("locatário"). Por exemplo, você não pode solicitar que o perfil do dispositivo de dados confidenciais desabilite o AppLocker para apenas alguns de seus usuários. Todos os dispositivos com o perfil de dados Confidenciais devem ter a mesma configuração.

Cada dispositivo só pode ter um perfil. Se um determinado dispositivo for usado por mais de um usuário, todos os usuários nesse dispositivo terão a mesma configuração.
