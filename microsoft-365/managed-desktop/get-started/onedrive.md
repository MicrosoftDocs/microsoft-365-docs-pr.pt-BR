---
title: Microsoft OneDrive
description: Como a Área de Trabalho Gerenciada da Microsoft configura o OneDrive para dispositivos inscritos
keywords: Microsoft Managed Desktop, Microsoft 365, serviço, documentação, aplicativos, aplicativos de linha de negócios, aplicativos LOB
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

A Área de Trabalho Gerenciada da Microsoft usa o [OneDrive for Business](/onedrive/plan-onedrive-enterprise) como um serviço de armazenamento em nuvem para todos os dispositivos da Área de Trabalho Gerenciada da Microsoft para garantir que os dispositivos sejam o mais sem estado possível. O usuário poderá encontrar seus arquivos independentemente do dispositivo em que entrar. Por exemplo, se você substituir um dispositivo da Área de Trabalho Gerenciada da Microsoft por um novo, os arquivos serão sincronizados automaticamente com o novo dispositivo.

Configuramos automaticamente essas configurações por padrão em Dispositivos Gerenciados da Microsoft:

- O OneDrive é configurado silenciosamente com a conta de usuário e entrou automaticamente (sem interação do usuário) na conta de usuário usada para entrar no Windows. Para obter mais informações, consulte [Silently configure user accounts - OneDrive](/onedrive/use-silent-account-configuration)

- O recurso Arquivos sob Demanda está habilitado para que os usuários possam acessar arquivos do armazenamento em nuvem no OneDrive sem precisar usar o espaço em disco desnecessariamente. Para obter mais informações, [consulte Save disk space with OneDrive Files On-Demand for Windows 10](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e).

- O recurso Movimento de Pasta Conhecida é habilitado silenciosamente para fazer o back up dos dados dos usuários na nuvem, o que lhes dá acesso aos arquivos de qualquer dispositivo. Para obter mais informações, [consulte Back up your Documents, Pictures, and Desktop folders with OneDrive](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057).

- Os usuários não podem desabilitar o recurso Movimento de Pasta Conhecida ou alterar o local de pastas conhecidas para garantir uma experiência consistente em dispositivos da Área de Trabalho Gerenciada da Microsoft.

## <a name="user-experience"></a>Experiência do usuário

Quando os usuários da Área de Trabalho Gerenciada da Microsoft recebem um novo dispositivo, eles passam por uma experiência de primeira versão inserindo suas credenciais do Azure durante a configuração do dispositivo. Depois que esse processo for concluído, eles poderão acessar sua área de trabalho e ter a experiência do OneDrive.

1. O sistema informa aos usuários que o OneDrive foi configurado e que eles foram automaticamente assinados no OneDrive.

:::image type="content" source="media/onedrive-sync.png" alt-text="A leitura da notificação agora está sincronizando o OneDrive e você pode editar arquivos no OneDrive. clique aqui para exibir seus arquivos":::

2. O sistema informa aos usuários que a Movimentação de Pasta Conhecida do OneDrive foi configurada para eles.

:::image type="content" source="media/onedrive-folders.png" alt-text="Leitura de notificação Seu departamento de IT fez backup de suas pastas importantes. As pastas agora têm backup no OneDrive e estão disponíveis em outros dispositivos":::

3. Para evitar ícones duplicados na área de trabalho quando os dispositivos estão sendo redefinidos ou reimaginados, o sistema remove automaticamente os ícones do Microsoft Edge e do Microsoft Teams da sincronização do OneDrive, conforme mostrado nesta exibição no Explorador de Arquivos.

:::image type="content" source="media/onedrive-teams.png" alt-text="Explorador de Arquivos mostrando listagem do Teams e borda com caixas de seleção des limpas e leitura de texto de foco Excluído da sincronização.":::


## <a name="onedrive-sync-restrictions"></a>Restrições de sincronização do OneDrive

Se você precisar restringir a sincronização do OneDrive, recomendamos controlar o acesso com uma política de acesso condicional do Azure Active Directory. Para obter mais informações, consulte [Enable conditional access support in the OneDrive sync app](/onedrive/enable-conditional-access).

Se você não puder usar uma política de acesso condicional do Azure AD em sua organização, o administrador de TI deverá seguir estas etapas:

1. Se você ainda não sabe, procure sua ID de locatário, conforme descrito em [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id).
2. Entre no centro de administração do OneDrive e selecione **Sincronizar** no painel esquerdo. Marque a caixa de seleção Permitir sincronização somente em **PCs ingressados em domínios específicos** e adicione a ID do locatário à lista de domínios. Para obter mais informações, consulte [Permitir sincronização somente em computadores ingressados em domínios específicos.](/onedrive/allow-syncing-only-on-specific-domains)

> [!NOTE]
> Essa orientação se aplica somente a locatários na Área de Trabalho Gerenciada da Microsoft. Há outras configurações em uso que não são discutidas neste artigo.