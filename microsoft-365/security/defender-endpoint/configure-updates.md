---
title: Criar um processo de lançamento gradual personalizado para atualizações do Microsoft Defender
description: Saiba como usar ferramentas com suporte para criar um processo de lançamento gradual personalizado para atualizações
keywords: ferramentas de atualização, gpo, intune, mdm, microsoft endpoint manager, policy, powershell
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: a7a560cb33190105f8df5922e04aeada4d75f398
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290034"
---
# <a name="create-a-custom-gradual-rollout-process-for-microsoft-defender-updates"></a>Criar um processo de lançamento gradual personalizado para atualizações do Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> Essa funcionalidade requer Microsoft Defender Antivírus versão 4.18.2106.X ou mais recente.

Para criar seu próprio processo de lançamento gradual personalizado para atualizações do Defender, você pode usar a Política de Grupo, Microsoft Endpoint Manager e o PowerShell.

A tabela a seguir lista as configurações de política de grupo disponíveis para configurar canais de atualização:

| Definindo título  | Descrição  | Local  |
|:---|:---|:---|
| Selecionar canal de distribuição de atualização mensal da plataforma do Microsoft Defender gradual  | Habilita essa política para especificar quando os dispositivos recebem atualizações da plataforma do Microsoft Defender durante a lançamento gradual mensal. Canal Beta: os dispositivos definidos para esse canal serão os primeiros a receber novas atualizações. Selecione Canal Beta para participar da identificação e relatórios de problemas para a Microsoft. Dispositivos no programa Windows Insider são inscritos neste canal por padrão. Para uso somente em ambientes de teste (manuais) e um número limitado de dispositivos.  <br><br>  Canal Atual (Visualização): os dispositivos definidos para esse canal receberão atualizações mais cedo durante o ciclo de lançamento gradual mensal. Sugerido para ambientes de pré-produção/validação.  <br><br>  Canal Atual (Em estágios): os dispositivos serão oferecidos atualizações após o ciclo de lançamento gradual mensal. Sugerida a aplicação a uma pequena parte representativa da sua população de produção (~10%).  <br><br>  Canal Atual (Amplo): os dispositivos serão oferecidos atualizações somente após a conclusão do ciclo gradual de lançamento. Sugerida a aplicação a um amplo conjunto de dispositivos em sua população de produção (~10-100%).  <br><br>   Se você desabilitar ou não configurar essa política, o dispositivo ficará atualizado automaticamente durante o ciclo gradual de lançamento. Adequado para a maioria dos dispositivos.  | Windows Components\Microsoft Defender Antivírus  |
| Selecionar canal de distribuição de atualização mensal do mecanismo do Microsoft Defender gradual  | Habilita essa política a especificar quando os dispositivos recebem atualizações do mecanismo do Microsoft Defender durante a lançamento gradual mensal.  <br><br>  Canal Beta: os dispositivos definidos para esse canal serão os primeiros a receber novas atualizações. Selecione Canal Beta para participar da identificação e relatórios de problemas para a Microsoft. Dispositivos no programa Windows Insider são inscritos neste canal por padrão. Para uso somente em ambientes de teste (manuais) e um número limitado de dispositivos.  <br><br>  Canal Atual (Visualização): os dispositivos definidos para esse canal receberão atualizações mais cedo durante o ciclo de lançamento gradual mensal. Sugerido para ambientes de pré-produção/validação.  <br><br>  Canal Atual (Em estágios): os dispositivos serão oferecidos atualizações após o ciclo de lançamento gradual mensal. Sugerida a aplicação a uma pequena parte representativa da sua população de produção (~10%).  <br><br>  Canal Atual (Amplo): os dispositivos serão oferecidos atualizações somente após a conclusão do ciclo gradual de lançamento. Sugerida a aplicação a um amplo conjunto de dispositivos em sua população de produção (~10-100%).  <br><br>  Se você desabilitar ou não configurar essa política, o dispositivo ficará atualizado automaticamente durante o ciclo gradual de lançamento. Adequado para a maioria dos dispositivos.  | Windows Components\Microsoft Defender Antivírus  |
| Selecionar canal de distribuição de atualizações diárias de definição gradual do Microsoft Defender  | Habilita essa política a especificar quando os dispositivos recebem atualizações de definição do Microsoft Defender durante a lançamento gradual diário. <br><br> Canal Atual (Em estágios): os dispositivos serão oferecidos atualizações após o ciclo de lançamento. Sugerida a aplicação a uma pequena parte representativa da população de produção (~10%). <br><br>   Canal Atual (Amplo): os dispositivos serão oferecidos atualizações somente após a conclusão do ciclo gradual de lançamento. Sugerida a aplicação a um amplo conjunto de dispositivos em sua população de produção (~10-100%). <br><br>   Se você desabilitar ou não configurar essa política, o dispositivo ficará atualizado automaticamente durante o ciclo de lançamento diário. Adequado para a maioria dos dispositivos.  | Windows Components\Microsoft Defender Antivírus  |
| Desabilitar a liberação gradual de atualizações do Microsoft Defender  | Habilita essa política para desabilitar a liberação gradual de atualizações do Defender. <br><br> Canal Atual (Amplo): os dispositivos definidos para esse canal receberão atualizações por último durante o ciclo gradual de lançamento. O melhor para máquinas de datacenter que recebem apenas atualizações limitadas. <br><br> Observação: essa configuração se aplica a atualizações mensais e diárias do Defender e substituirá todas as seleções de canal configuradas anteriormente para atualizações de plataforma e mecanismo. <br><br> Se você desabilitar ou não configurar essa política, o dispositivo permanecerá no Canal Atual (Padrão), a menos que especificado de outra forma em canais específicos para atualizações de plataforma e mecanismo. Mantenha-se atualizado automaticamente durante o ciclo gradual de lançamento. Adequado para a maioria dos dispositivos.  | Windows Components\Microsoft Defender Antivírus  |

## <a name="group-policy"></a>Política de Grupo

> [!NOTE]
> Um modelo atualizado do Defender ADMX será publicado junto com a versão 21H2 do Windows 10. Uma versão não localizada está disponível para download em https://github.com/microsoft/defender-updatecontrols .

Você pode usar [a Política de Grupo](/windows/win32/srvnodes/group-policy?redirectedfrom=MSDN)para configurar e gerenciar Microsoft Defender Antivírus em seus pontos de   extremidade.

Em geral, você pode usar o procedimento a seguir para configurar ou alterar Microsoft Defender Antivírus de política de grupo:

1. Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de **Grupo**, clique com o botão direito do mouse no Objeto de Política de Grupo (GPO) que você deseja configurar e clique em **Editar**. 

2. Usando o Editor de Gerenciamento de Política de Grupo, vá para **Configuração do computador.**

3. Clique **em Modelos Administrativos**.

4. Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus**.

5. Expanda a seção (conhecida como **Local** na tabela neste tópico) que contém a configuração que você deseja configurar, clique duas vezes na configuração para abri-la e faça alterações na   configuração.

6. [Implante o GPO atualizado como você normalmente faz](https://msdn.microsoft.com/library/ee663280(v=vs.85).aspx).

## <a name="intune"></a>Intune

Siga as instruções no link abaixo para criar uma política personalizada no Intune:

[Adicionar configurações personalizadas para Windows 10 dispositivos Microsoft Intune - Microsoft Docs do Azure \|](/mem/intune/configuration/custom-settings-windows-10)

Para obter mais informações sobre os CSPs do Defender usados para o processo de lançamento gradual, consulte [Defender CSP](/windows/client-management/mdm/defender-csp).

## <a name="powershell"></a>Windows PowerShell

Use o `Set-MpPreference` cmdlet para configurar o lançamento das atualizações graduais.

Use os seguintes parâmetros:

```powershell
Set-MpPreference
-PlatformUpdatesChannel Beta|Preview|Staged|Broad|NotConfigured
-EngineUpdatesChannel Beta|Preview|Staged|Broad|NotConfigured
-DisableGradualRelease True|False
-SignaturesUpdatesChannel Staged|Broad|NotConfigured
```

Exemplo:

Use `Set-MpPreference -PlatformUpdatesChannel Beta` para configurar as atualizações da plataforma para chegar do Canal Beta.

Para obter mais informações sobre os parâmetros e como configurá-los, consulte [Set-MpPreference (Defender) | Microsoft Docs](/powershell/module/defender/set-mppreference).
