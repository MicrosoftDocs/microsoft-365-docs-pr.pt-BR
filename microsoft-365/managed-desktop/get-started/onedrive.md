---
title: Microsoft OneDrive
description: Como Área de Trabalho Gerenciada da Microsoft configura o OneDrive para dispositivos inscritos
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação, aplicativos, aplicativos de linha de negócios, aplicativos LOB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a26500c1671afffc7b70d509a4242914631b937c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904835"
---
# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Área de Trabalho Gerenciada da Microsoft usa [OneDrive for Business](/onedrive/plan-onedrive-enterprise) como um serviço de armazenamento em nuvem para todos os dispositivos Área de Trabalho Gerenciada da Microsoft para garantir que os dispositivos sejam o mais sem estado possível. O usuário poderá encontrar seus arquivos independentemente do dispositivo em que entrar. Por exemplo, se você substituir um Área de Trabalho Gerenciada da Microsoft por um novo, os arquivos serão sincronizados automaticamente com o novo dispositivo.

Configuramos automaticamente essas configurações por padrão em Dispositivos Gerenciados da Microsoft:

- OneDrive é configurado silenciosamente com a conta de usuário e automaticamente entrou (sem interação do usuário) na conta de usuário que foi usada para entrar Windows. Para obter mais informações, consulte [Silently configure user accounts - OneDrive](/onedrive/use-silent-account-configuration)

- O recurso Arquivos sob Demanda está habilitado para que os usuários possam acessar arquivos do armazenamento na nuvem em OneDrive sem precisar usar o espaço em disco desnecessariamente. Para obter mais informações, consulte [Save disk space with OneDrive Files On-Demand for Windows 10](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e).

- O recurso Movimento de Pasta Conhecida é habilitado silenciosamente para fazer o back up dos dados dos usuários na nuvem, o que lhes dá acesso aos arquivos de qualquer dispositivo. Para obter mais informações, [consulte Back up your Documents, Pictures, and Desktop folders with OneDrive](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057).

- Os usuários não podem desabilitar o recurso Movimento de Pasta Conhecida ou alterar o local de pastas conhecidas para garantir uma experiência consistente entre Área de Trabalho Gerenciada da Microsoft dispositivos.

## <a name="user-experience"></a>Experiência do usuário

Quando Área de Trabalho Gerenciada da Microsoft os usuários recebem um novo dispositivo, eles passam por uma experiência de primeira fase inserindo suas credenciais do Azure durante a configuração do dispositivo. Depois que esse processo for concluído, eles poderão acessar sua área de trabalho e ter OneDrive experiência.

1. O sistema informa aos usuários que OneDrive foram configurados e que eles foram automaticamente OneDrive.

:::image type="content" source="media/onedrive-sync.png" alt-text="A leitura de notificação agora está sincronizando OneDrive e você pode editar arquivos em OneDrive. clique aqui para exibir seus arquivos":::

2. O sistema informa aos usuários que OneDrive Movimento de Pasta Conhecida foi configurado para eles.

:::image type="content" source="media/onedrive-folders.png" alt-text="Leitura de notificação Seu departamento de IT fez backup de suas pastas importantes. As pastas agora são respaldadas para OneDrive e disponíveis em outros dispositivos":::

3. Para evitar ícones duplicados na área de trabalho quando os dispositivos estão sendo redefinidos ou reimaginados, o sistema remove automaticamente os ícones Microsoft Edge e Microsoft Teams da sincronização de OneDrive, conforme mostrado nesta exibição no Explorador de Arquivos.

:::image type="content" source="media/onedrive-teams.png" alt-text="Explorador de Arquivos mostrando Teams e listagem de borda com caixas de seleção des limpas e leitura de texto de foco Excluído da sincronização.":::


## <a name="onedrive-sync-restrictions"></a>OneDrive restrições de sincronização

Se você precisar restringir OneDrive sincronização, recomendamos controlar o acesso com uma política de Azure Active Directory de acesso condicional. Para obter mais informações, consulte [Enable conditional access support in the OneDrive sync app](/onedrive/enable-conditional-access).

Se você não puder usar uma política de acesso condicional do Azure AD em sua organização, o administrador de TI deverá seguir estas etapas:

1. Se você ainda não sabe, procure sua ID de locatário, conforme descrito em [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id).
2. Entre no centro de administração OneDrive e selecione **Sincronizar** no painel esquerdo. Marque a caixa de seleção Permitir sincronização somente em **PCs ingressados em domínios específicos** e adicione a ID do locatário à lista de domínios. Para obter mais informações, consulte [Permitir sincronização somente em computadores ingressados em domínios específicos.](/onedrive/allow-syncing-only-on-specific-domains)

> [!NOTE]
> Essa orientação se aplica somente a locatários Área de Trabalho Gerenciada da Microsoft. Há outras configurações em uso que não são discutidas neste artigo.