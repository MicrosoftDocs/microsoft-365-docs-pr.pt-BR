---
title: Ferramenta de avaliação de prontidão
description: Explica as verificações em que a ferramenta é executada e o significado dos resultados
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c574be6d171a230479d8b6c96e2e0a1dec8a87ac
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656125"
---
# <a name="readiness-assessment-tool"></a>Ferramenta de avaliação de prontidão

Para uma experiência mais suave possível quando você se inscreve na área de trabalho gerenciada da Microsoft, há várias configurações e outros parâmetros que devem ser definidos antes do tempo. Você pode usar essa ferramenta para verificar as configurações e receber etapas detalhadas para corrigir qualquer um que não seja o direito.

A ferramenta verifica as configurações no Microsoft Endpoint Manager (especificamente, Microsoft Intune), Azure Active Directory (Azure AD) e Microsoft 365 para garantir que elas funcionarão com a área de trabalho gerenciada da Microsoft. A área de trabalho gerenciada da Microsoft retém os dados associados a essas verificações por 12 meses após a última vez que você executa um check-in em sua organização do AD do Azure (locatário).  Após 12 meses, retida-a na forma de não identificado.  Você pode optar por excluir os dados que coletamos.
 
A ferramenta de avaliação verifica estes itens:

## <a name="microsoft-intune-settings"></a>Configurações do Microsoft Intune

|Verificar  |Descrição  |
|---------|---------|
|Perfil de implantação do piloto automático     | Verifica se a atribuição do perfil de implantação do piloto automático não se aplica a todos os dispositivos (o perfil *não* deve ser atribuído a nenhum dispositivo de área de trabalho gerenciado da Microsoft).       |
|Conectores de certificado     | Verifica o estado dos conectores de certificado para garantir que eles estejam ativos   |
|Acesso Condicional     | Verifica se as políticas de acesso condicional não estão atribuídas a todos os usuários (as políticas de acesso condicional *não* devem ser atribuídas às contas de serviço de área de trabalho gerenciada da Microsoft).    |
|Políticas de conformidade do dispositivo     | Verifica se as políticas de conformidade do Intune não estão atribuídas a todos os usuários (as políticas *não* devem ser atribuídas a nenhum dispositivo de área de trabalho gerenciado da Microsoft).    |
|Perfis de configuração de dispositivo     | Confirma que os perfis de configuração não são atribuídos a todos os usuários ou dispositivos (os perfis de configuração *não* devem ser atribuídos a nenhum dispositivo de área de trabalho gerenciado da Microsoft).     |
|Restrições de tipo de dispositivo     | Verifica se os dispositivos Windows 10 em sua organização têm permissão para se inscrever no Intune        |
|Página de status do registro     | Confirma se a página de status do registro não está habilitada      |
|Registro do Intune     | Verifica se os dispositivos Windows 10 em sua organização do Azure AD estão registrados automaticamente no Intune         |
|Microsoft Store para empresas     | Confirma se o Microsoft Store para empresas está habilitado e sincronizado com o Intune        |
|Autenticação multifator | Verifica se a autenticação multifator não é aplicada às contas de serviço de área de trabalho gerenciada da Microsoft.
|Scripts do PowerShell     | Verifica se os scripts do Windows PowerShell *não* estão atribuídos de uma maneira que direcione dispositivos de área de trabalho gerenciada da Microsoft    |
|Região     | Verifica se a sua região é compatível com a área de trabalho gerenciada da Microsoft        |
|Linhas de base de segurança     | Verifica se o perfil da linha de base de segurança não tem como destino todos os usuários ou todos os dispositivos (as diretivas de linha de base de segurança *não* devem ser direcionadas a dispositivos da Microsoft gerenciado       |
|Aplicativos do Windows     | Revise quais aplicativos você deseja atribuir aos dispositivos de área de trabalho gerenciada da Microsoft      |
|Windows Hello para Empresas     | Verifica se o Windows Hello para empresas está habilitado        |
|Anel de atualização do Windows 10     | Verifica se a política "anel de atualização do Windows 10" do Intune não tem como destino todos os usuários ou todos os dispositivos (a política *não* deve ser direcionada a nenhum dispositivo de área de trabalho gerenciado da Microsoft).     |


## <a name="azure-active-directory-settings"></a>Configurações do Azure Active Directory

|Verificar  |Descrição  |
|---------|---------|
|Assinaturas "ad hoc" para roaming de estado empresarial     | Aconselha a verificar uma configuração que (se definida como "false") pode impedir que o roaming de estado corporativo funcione corretamente  |
|Roaming de Estado da Empresa     | Aconselha a verificar se o roaming de estado corporativo está habilitado       |
|Licenças     | Verifica se você obteve as [licenças](prerequisites.md#more-about-licenses) necessárias         |
|Autenticação multifator     | Verifica se a autenticação multifator não é aplicada a todos os usuários (a autenticação multifator não deve ser aplicada acidentalmente às contas de serviço de área de trabalho gerenciada da Microsoft).|
|Nomes de contas de segurança   | Verifica se nenhum nome de usuário está em conflito com aqueles que a área de trabalho gerenciada da Microsoft reserva para seu próprio uso        |
|Funções de administrador de segurança     | Confirma se os usuários com o leitor de segurança, o operador de segurança ou as funções de leitor global receberam essas funções no Microsoft defender para ponto de extremidade         |
|Padrões de segurança | Verifica se a sua organização do Azure AD tem padrões de segurança habilitados no Azure Active Directory |
|Redefinição de senha por autoatendimento     | Confirma se a redefinição de senha de autoatendimento está habilitada        |
|Função de usuário padrão     | Verifica se os usuários são usuários padrão e se não têm direitos de administrador local         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Microsoft 365 aplicativos para configurações corporativas

|Verificar  |Descrição  |
|---------|---------|
|OneDrive for Business     | Verifica se o OneDrive for Business está usando configurações não suportadas.        |


Para cada verificação, a ferramenta relatará um dos três resultados possíveis:


|Resultado  |Significado  |
|---------|---------|
|Pronto     | Nenhuma ação é necessária antes de concluir o registro.        |
|Recomendações    | Siga as etapas na ferramenta para obter a melhor experiência com o registro e os usuários. Você *pode* concluir o registro, mas deve corrigir esses problemas antes de implantar o primeiro dispositivo.        |
|Não está pronto | O *registro falhará* se você não corrigir esses problemas. Siga as etapas na ferramenta para resolvê-los.        |