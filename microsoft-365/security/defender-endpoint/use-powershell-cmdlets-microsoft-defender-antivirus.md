---
title: Usar cmdlets do PowerShell para configurar e executar o Microsoft Defender AV
description: Em Windows 10, você pode usar cmdlets do PowerShell para executar verificações, atualizar a inteligência de segurança e alterar configurações em Microsoft Defender Antivírus.
keywords: scan, linha de comando, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: d6fb8dc510e004fa88bf99583cc2cc33ae8c63bb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765294"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a>Usar cmdlets do PowerShell para configurar e gerenciar Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode usar o PowerShell para executar várias funções em Windows Defender. Semelhante ao prompt de comando ou linha de comando, o PowerShell é um shell de linha de comando baseado em tarefas e linguagem de script projetada especialmente para a administração do sistema. Você pode ler mais sobre isso no [hub do PowerShell no MSDN](/previous-versions/msdn10/mt173057(v=msdn.10)).

Para ver uma lista dos cmdlets e suas funções e parâmetros disponíveis, consulte o [tópico cmdlets](/powershell/module/defender) do Defender.

Os cmdlets do PowerShell são mais úteis em ambientes Windows Server que não dependem de uma interface gráfica do usuário (GUI) para configurar o software.

> [!NOTE]
> Os cmdlets do PowerShell não devem ser usados como um substituto para uma infraestrutura completa de gerenciamento de política de rede, [como Microsoft Endpoint Configuration Manager](/configmgr), Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))ou modelos ADMX de política de grupo [Microsoft Defender Antivírus.](https://www.microsoft.com/download/101445)

As alterações feitas com o PowerShell afetarão as configurações locais no ponto de extremidade onde as alterações são implantadas ou feitas. Isso significa que as implantações de política com a Política de Grupo, Microsoft Endpoint Configuration Manager ou Microsoft Intune podem substituir as alterações feitas com o PowerShell.

Você pode [configurar quais configurações podem ser substituidas localmente com substituições de política local.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

O PowerShell normalmente é instalado na pasta `%SystemRoot%\system32\WindowsPowerShell` .

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a>Usar Microsoft Defender Antivírus cmdlets do PowerShell

1. Na barra Windows de pesquisa, digite **powershell**.
2. Selecione **Windows PowerShell** dos resultados para abrir a interface.
3. Insira o comando do PowerShell e todos os parâmetros.

> [!NOTE]
> Talvez seja necessário abrir o PowerShell no modo de administrador. Clique com o botão direito do mouse no item no menu Iniciar, clique em **Executar como administrador** e clique em **Sim** no prompt de permissões.

Para abrir a ajuda online para qualquer um dos cmdlets, digite o seguinte:

```PowerShell
Get-Help <cmdlet> -Online
```

Omita o `-online` parâmetro para obter ajuda em cache local.

## <a name="related-topics"></a>Tópicos relacionados

- [Tópicos de referência para ferramentas de gerenciamento e configuração](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivírus Cmdlets](/powershell/module/defender)