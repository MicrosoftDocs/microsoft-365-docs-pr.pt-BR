---
title: Adicione e verifique contatos do administrador no portal do Administrador
description: Diga-nos quem contatar para cada área de foco.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8b287200b1c94ff350f7ba00cf0c4e6bc1b4a71f
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289256"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>Adicione e verifique contatos do administrador no portal do Administrador

Há várias maneiras de o serviço área de trabalho gerenciada da Microsoft se comunicar com os clientes. Para simplificar a comunicação e garantir que estamos verificando com as pessoas certas, você precisa fornecer um conjunto de contatos de administrador. As operações de IT da Área de Trabalho Gerenciada da Microsoft entrarão em contato com essas pessoas para ajudar na solução de problemas do seu locatário.

> [!IMPORTANT]
> Talvez você já tenha adicionado esses contatos no portal de administração. Nesse caso, dê um tempo agora para verificar se a lista  de contatos está precisa, pois a Área de Trabalho Gerenciada da Microsoft deve ser capaz de entrar em contato com eles se ocorrer um incidente grave.

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Acesso do Azure Active Directory ao Portal de Administração da Área de Trabalho Gerenciada da Microsoft

O Portal de Administração da Área de Trabalho Gerenciada da Microsoft exige que as pessoas que acessam o portal tenham uma destas funções do Azure Active Directory (AD).
- Administrador Global
- Administrador de Serviços do Intune
- Leitor global
- Administrador de Suporte ao Serviço

O Administrador Global deve ser aquele que registrará sua organização na Área de Trabalho Gerenciada da Microsoft. Todas as cinco funções têm o mesmo acesso no portal de administração para iniciar e exibir tarefas. Para obter mais informações sobre como atribuir essas funções no Azure AD, consulte Permissões de função [de administrador no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 

## <a name="admin-contact-areas-of-focus"></a>Áreas de contato de administrador de foco

Os contatos do administrador devem ser a melhor pessoa ou grupo que pode responder a perguntas e tomar decisões em diferentes áreas de foco. **As Operações da Área de Trabalho Gerenciada da Microsoft entrarão em contato com esses contatos do Administrador para perguntas envolvendo solicitações de suporte arquivadas pelo cliente.** Esses contatos do Administrador receberão notificações de atualizações de solicitação de suporte e novas mensagens. Essas áreas incluem:

Área de foco | Para perguntas sobre
--- | ---
Empacotamento de aplicativos | Solução de problemas de empacotamento de aplicativos
Dispositivos | Saúde do dispositivo, solução de problemas com dispositivos da Área de Trabalho Gerenciada da Microsoft
Segurança | Solução de problemas de segurança com dispositivos da Área de Trabalho Gerenciada da Microsoft
Help desk de IT | nos casos em que nossa equipe de Suporte entrega tíquetes de usuário fora das áreas de suporte da Área de Trabalho Gerenciada da Microsoft 
Outros | Para problemas não cobertos por outras áreas

**Quem escolher para esses contatos precisa ter conhecimento e autoridade para tomar decisões em seu ambiente de Área de Trabalho Gerenciada da Microsoft.** Quando você integra seu ambiente de Área de Trabalho Gerenciada da Microsoft, é solicitado a adicionar contatos para a Helpdesk e a Segurança locais. 

Os contatos do administrador são necessários quando você [envia uma solicitação de suporte.](../service-description/support.md) Você precisará ter um contato de administrador para a área de foco da solicitação de suporte. 

**Para adicionar contatos de administrador**

1.  Entre no [portal de administração da Área de Trabalho Gerenciada da Microsoft.](https://aka.ms/mwaasportal) 

2.  Em **Suporte,** selecione **Contatos do administrador.** 

    ![Menu de suporte, contatos do administrador próximo à parte superior selecionada](../../media/admincontacts.png)

3. Clique em **Adicionar**.

    ![Portal de administração, botão Adicionar à esquerda de Exportar e Atualizar](../../media/adminadd.png)

4.  Selecione uma **área de foco** e insira as informações do contato. 

    ![a lista de áreas de foco, como Outros, Aplicativos e Segurança](../../media/areaoffocus.png)

5. Repita para cada área de foco. 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Etapas para começar a trabalhar com a Área de Trabalho Gerenciada da Microsoft

1. Adicionar e verificar contatos de administrador no portal de administração (este tópico)
2. [Ajustar o acesso condicional](conditional-access.md)
3. [Atribuir licenças](assign-licenses.md)
4. [Instalar o Portal da Empresa do Intune em dispositivos](company-portal.md)
5. [Habilitar Enterprise State Roaming](enterprise-state-roaming.md)
6. [Configurar dispositivos de Área de Trabalho Gerenciada da Microsoft](set-up-devices.md)
7. [Preparar usuários para o uso dos dispositivos](get-started-devices.md)
8. [Implantar aplicativos em dispositivos](deploy-apps.md)
