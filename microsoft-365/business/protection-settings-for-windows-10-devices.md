---
title: Editar ou definir configurações de proteção de aplicativos para dispositivos Windows 10
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Saiba como criar ou editar políticas de gerenciamento de aplicativos e proteger arquivos de trabalho em dispositivos Windows 10 pessoais de seus usuários.
ms.openlocfilehash: aa270c563e6bdce6fd48f8713d7db3ce23921925
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580005"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a>Definir ou editar configurações de proteção de aplicativos para dispositivos Windows 10

Este artigo se aplica ao Microsoft 365 Business Premium.

## <a name="edit-an-app-management-policy-for-windows-10"></a>Editar uma política de gerenciamento de aplicativos para o Windows 10

1. Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.     
2. À esquerda, escolha **Políticas** de \> **Dispositivos** .
1. Escolha uma política de aplicativo do Windows existente e **edite**.
1. Escolha **Editar** ao lado de uma configuração que você deseja alterar e, em seguida, **Salvar**.

## <a name="create-an-app-management-policy-for-windows-10"></a>Criar uma política de gerenciamento de aplicativos para Windows 10

Se seus usuários possuírem dispositivos pessoais do Windows 10 nos quais executam tarefas de trabalho, você também pode proteger seus dados nesses dispositivos.
  
1. Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
2. À esquerda, escolha  Políticas de \>  \> **Dispositivos Adicionar**.
3. No painel **Adicionar política**, insira um nome exclusivo para essa política. 
4. Em **Tipo de política**, escolha **Gerenciamento de Aplicativos para Windows 10**.
5. Em **Tipo de dispositivo**, escolha **Personal** ou Company **Owned**.
6. A opção **Criptografar arquivos de trabalho** é ativada automaticamente. 
7. Defina **Impedir que os usuários copiem os dados da empresa para arquivos pessoais e forçar que eles salvem arquivos de trabalho no OneDrive for Business** para **Ativado** se não quiser que os usuários salvem arquivos de trabalho em seus computadores. 
9. Expanda **Recuperar dados em dispositivos Windows.** Recomendamos que você a **a ligue.**
    Antes de poder navegar para o local do certificado do Agente de Recuperação de Dados, você precisa primeiro criar um. Para obter instruções, [consulte Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA).](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate)
    
    Por padrão, os arquivos de trabalho são criptografados usando uma chave secreta que é armazenada no dispositivo e associada ao perfil do usuário. Somente o usuário pode abrir e descriptografar o arquivo. No entanto, se um dispositivo for perdido ou um usuário for removido, um arquivo pode ficar preso em um estado criptografado. Um administrador pode usar o certificado DRA (Agente de Recuperação de Dados) para descriptografar o arquivo.
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. Expanda **Proteger locais** de rede e nuvem adicionais se você quiser adicionar domínios adicionais ou locais do SharePoint Online para garantir que os arquivos em todos os aplicativos listados sejam protegidos. Se desejar inserir mais de um item em um campo, use um ponto e vírgula (;) entre os itens.
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Em seguida, decida **Quem receberá estas configurações?** Se não quiser usar o grupo de segurança padrão **Todos os Usuários**, escolha **Alterar**, escolha o grupo de segurança que deverá receber essas configurações \> **Selecionar**.
12. Por fim, escolha **Adicionar** para salvar a política e atribui-la a dispositivos.