---
title: Habilitar rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/01/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Os administradores podem habilitar o suporte a rótulos de confidencialidade para arquivos do Word, Excel e PowerPoint no SharePoint e no OneDrive.
ms.openlocfilehash: c62db0d77ed805c607e79bf25cb9816a554cb6d2
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802824"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a>Habilitar rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive (visualização pública)

Anteriormente, quando você aplicou rótulos de confidencialidade que incluíram criptografia para arquivos do Office armazenados no SharePoint e no OneDrive, o serviço não pôde processar o conteúdo desses arquivos. A coautoria, eDiscovery, prevenção de perda de dados, pesquisa, Delve e outros recursos colaborativos não funcionaram nessas circunstâncias. Essa visualização habilita estes recursos:

- O SharePoint reconhece rótulos de confidencialidade aplicados a arquivos do Word, Excel e PowerPoint no SharePoint e no OneDrive. O SharePoint também impõe as configurações que correspondem a cada rótulo.

- Quando você baixa um arquivo do SharePoint ou do OneDrive, o rótulo de confidencialização acompanha o arquivo e as configurações permanecem impostas.

- Aplicar rótulos de confidencialidade a arquivos do Office e abrir e editar arquivos com rótulos de confidencialidade aplicados (se as permissões do rótulo permitirem isso) usando as versões da Web do Word, Excel e PowerPoint. Com o Word na Web, você também pode usar o rotulamento automático ao editar documentos.

- O Office 365 eDiscovery oferece suporte a pesquisa de texto completo em arquivos com rótulos de confidencialidade aplicados. As políticas de prevenção de perda de dados (DLP) abrangem conteúdo nesses arquivos.

- Três novos eventos de auditoria estão disponíveis para monitoramento de rótulos de sensibilidade:
  - FileSensitivityApplied
  - FileSensitivityLabelChanged
  - FileSensitivityLabelRemoved

Agora, você também pode aplicar rótulos de confidencialidade ao Microsoft Teams, grupos do Office 365 e sites do SharePoint. [Saiba mais](sensitivity-labels-teams-groups-sites.md).

Se necessário, você pode sair da visualização a qualquer momento.

## <a name="requirements"></a>Requirements

Esses recursos funcionam apenas com [Rótulos de confidencialidade](sensitivity-labels.md). Se você usou os rótulos de proteção de informações do Azure, é possível convertê-los em rótulos de confidencialidade para habilitar esses recursos para novos arquivos que você carregar. [Saiba como](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

Para esta visualização, use o OneDrive Sync app versão 19.002.0121.0008 ou posterior no Windows e versão 19.002.0107.0008 ou posterior no Mac. Essas duas versões foram lançadas em 28 de janeiro de 2019 e foram lançadas atualmente para todos os toques. [Confira as notas de versão do onedrive](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0). Após habilitar essa visualização, os usuários que executam uma versão mais antiga do aplicativo de sincronização serão solicitados a atualizá-lo.

## <a name="limitations"></a>Limitações

- Quando você habilita essa visualização, os usuários que aplicam um rótulo a um arquivo usando a área de trabalho do Office ou aplicativos móveis podem não conseguir salvar outras alterações que eles fazem no arquivo. Em vez disso, o aplicativo solicita que os usuários salvem como ou descartam alterações locais. Para evitar a perda de trabalho, execute uma destas ações:

  - Para aplicar rótulos, use as versões Web dos aplicativos do Office.

  - Feche um arquivo depois de aplicar um rótulo e reabra o arquivo para fazer outras alterações.

- O SharePoint não aplica automaticamente os novos rótulos aos arquivos existentes que você já criptografou usando os rótulos de proteção de informações do Azure. Em vez disso, para fazer com que os recursos funcionem depois de habilitar esta visualização, conclua estas tarefas:

  - Converta os rótulos de proteção de informações do Azure em rótulos de confidencialidade.

  - Baixe os arquivos e carregue-os no SharePoint.

- O SharePoint não pode processar rótulos com permissões e rótulos personalizados com datas de expiração.

- Quando os usuários têm permissões de edição, as versões Web dos aplicativos do Office permitem a cópia, independentemente da configuração de política de cópia no rótulo.

- A revogação, o rastreamento e o relatório do RMS não têm suporte.

- Aplicativos de área de trabalho do Office e aplicativos móveis não oferecem suporte à coautoria. Em vez disso, esses aplicativos continuam a abrir arquivos no modo de edição exclusivo.

- Se um rótulo incluir criptografia, o Microsoft Cloud app Security não poderá ler as informações de rótulo dos arquivos no SharePoint.

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a>Preparar o Shell de gerenciamento do SharePoint Online para a visualização

Antes de habilitar a visualização, verifique se você está executando o Shell de gerenciamento do SharePoint Online versão 16.0.19418.12000 ou superior. Se você já tiver a versão mais recente, poderá prosseguir e habilitar a visualização.

1. Se você tiver instalado uma versão anterior do Shell de gerenciamento do SharePoint Online a partir da galeria do PowerShell, você pode atualizar o módulo executando o seguinte cmdlet.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. Como alternativa, se você tiver instalado uma versão anterior do Shell de gerenciamento do SharePoint Online no centro de download da Microsoft, também poderá ir para **Adicionar ou remover programas** e desinstalar o Shell de gerenciamento do SharePoint Online.

3. Em um navegador da Web, vá até a página centro de download e [Baixe o Shell de gerenciamento do SharePoint Online mais recente](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Selecione seu idioma e clique em **baixar**.

5. Escolha entre o arquivo x64 e x86. msi. Baixe o arquivo x64 se você executar a versão de 64 bits do Windows ou o arquivo x86, se você executar a versão de 32 bits. Se não souber, confira [qual versão do sistema operacional Windows estou executando?](https://support.microsoft.com/help/13443/windows-which-operating-system)


6. Depois de baixar o arquivo, execute o arquivo e siga as etapas no assistente de instalação.

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a>Habilitar a visualização usando o Microsoft PowerShell (aceitar)

Para habilitar a visualização, use o cmdlet Set-SPOTenant:

1. Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global ou de administrador do SharePoint no Office 365, conecte-se ao SharePoint. Veja como em [Introdução ao Shell de Gerenciamento do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

2. Execute o seguinte comando:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a>Agendar a distribuição após criar ou alterar um rótulo de confidencialidade

Após criar ou alterar um rótulo de confidencialidade no centro de conformidade do Microsoft 365, publique-o em estágios. Se você publicar rótulos que não estão totalmente sincronizados, quando os usuários aplicam os rótulos aos arquivos e os carregam no SharePoint, os arquivos não podem ser abertos nas versões Web dos aplicativos do Office. A pesquisa e a descoberta eletrônica também não funcionam para os arquivos.

Recomendamos que você siga estas etapas:

1. Publicar o rótulo de confidencialidade novo ou modificado somente para uma ou duas pessoas.

2. Aguarde pelo menos 24 horas após a publicação inicial. Verifique se o rótulo foi totalmente sincronizado.

3. Publique o rótulo de forma mais ampla.

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a>Desabilitar a visualização usando o Microsoft PowerShell (recusar)

Se você desabilitar essa visualização, os arquivos que você carregou durante a visualização continuam a ser protegidos pelo rótulo. As configurações correspondentes continuam a ser impostas. Quando você aplica rótulos a novos arquivos depois de desabilitar a visualização, a pesquisa de texto completo, a descoberta eletrônica e a coautoria não funcionarão mais.

Para desabilitar a visualização, use o cmdlet Set-SPOTenant:

1. Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global ou de administrador do SharePoint no Office 365, conecte-se ao SharePoint. Veja como em [Introdução ao Shell de Gerenciamento do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

2. Execute o seguinte comando:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
