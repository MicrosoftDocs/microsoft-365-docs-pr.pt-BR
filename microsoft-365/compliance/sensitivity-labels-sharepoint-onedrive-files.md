---
title: Habilitar rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Os administradores podem habilitar o suporte a rótulos de confidencialidade para arquivos do Word, Excel e PowerPoint no SharePoint e no OneDrive.
ms.openlocfilehash: fea28683136ae72603b3e7a6954d7d6ecf0ffbe4
ms.sourcegitcommit: 2eb4539291f5035b7bef746df89fbcc6faa17257
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2020
ms.locfileid: "41263333"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a>Habilitar rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive (visualização pública)

Antes desta visualização, quando você aplicou rótulos de confidencialidade que incluíram criptografia para arquivos do Office armazenados no SharePoint e no OneDrive, o serviço não pôde processar o conteúdo desses arquivos. A coautoria, eDiscovery, prevenção de perda de dados, pesquisa, Delve e outros recursos colaborativos não funcionaram nessas circunstâncias. Essa visualização habilita esses recursos quando a criptografia foi aplicada com uma chave baseada na nuvem:

- O SharePoint reconhece rótulos de confidencialidade aplicados a arquivos do Word, Excel e PowerPoint no SharePoint e no OneDrive. O SharePoint também impõe as configurações que correspondem a cada rótulo.

- Quando você baixa um arquivo do SharePoint ou do OneDrive, o rótulo de confidencialização acompanha o arquivo e as configurações permanecem impostas.

- Aplicar rótulos de confidencialidade a arquivos do Office e abrir e editar arquivos com rótulos de confidencialidade aplicados (se as permissões do rótulo permitirem isso) usando as versões da Web do Word, Excel e PowerPoint. Com o Word na Web, você também pode usar o rotulamento automático ao editar documentos.

- O Office 365 eDiscovery oferece suporte a pesquisa de texto completo em arquivos com rótulos de confidencialidade aplicados. As políticas de prevenção de perda de dados (DLP) abrangem conteúdo nesses arquivos.

- Três novos eventos de auditoria estão disponíveis para monitoramento de rótulos de sensibilidade:
  - FileSensitivityApplied
  - FileSensitivityLabelChanged
  - FileSensitivityLabelRemoved

> [!NOTE]
> Se a criptografia não tiver sido aplicada com uma chave baseada na nuvem, mas uma chave local, uma topologia de gerenciamento de chave freqüentemente chamada de "conter sua própria chave" (HYOK), o comportamento do SharePoint não mudará com esta visualização. 

Agora, você também pode aplicar rótulos de confidencialidade ao Microsoft Teams, grupos do Office 365 e sites do SharePoint. Para obter mais informações sobre essa visualização separada, confira [usar rótulos de sensibilidade com o Microsoft Teams, grupos do Office 365 e sites do SharePoint (visualização pública)](sensitivity-labels-teams-groups-sites.md).

Você sempre tem a opção de cancelar essa visualização a qualquer momento.

Assista ao vídeo a seguir (sem áudio) para ver os novos recursos em ação:

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

## <a name="requirements"></a>Requirements

Esses recursos funcionam somente com [Rótulos de confidencialidade](sensitivity-labels.md) . Se, no momento, você tiver rótulos de proteção de informações do Azure, primeiro migre-os para os rótulos de confidencialização para que você possa habilitar esses recursos para novos arquivos que você carregar. Para obter instruções, consulte [como migrar rótulos de proteção de informações do Azure para rótulos de sensibilidade unificada](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

Para esta visualização, use o aplicativo de sincronização do OneDrive versão 19.002.0121.0008 ou posterior no Windows e versão 19.002.0107.0008 ou posterior no Mac. Essas duas versões foram lançadas em 28 de janeiro de 2019 e foram lançadas atualmente para todos os toques. Para obter mais informações, consulte as [notas de versão do onedrive](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0). Após habilitar essa visualização, os usuários que executam uma versão mais antiga do aplicativo de sincronização são solicitados a atualizá-lo.

## <a name="limitations"></a>Limitações

- Quando você habilita essa visualização, os usuários que alteram um rótulo para um arquivo em uma pasta de sincronização do OneDrive podem não conseguir salvar outras alterações que eles fazem no arquivo.  Os usuários vêem um [círculo vermelho com um erro de ícone de cruz branco](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)e são solicitados a salvar novas alterações como uma cópia separada.  Além das alterações de rótulo que são iniciadas pelos usuários, o mesmo comportamento pode ocorrer se um administrador alterar as configurações de um rótulo publicado já aplicado aos arquivos baixados para o cliente de sincronização dos usuários.
    
    Para evitar a perda de trabalho nesses cenários, execute uma destas ações:
    - Para aplicar rótulos, use as versões Web dos aplicativos do Office.
    - Feche um arquivo depois de aplicar um rótulo e reabra o arquivo para fazer outras alterações.

- O SharePoint não aplica automaticamente os novos rótulos aos arquivos existentes que você já criptografou usando os rótulos de proteção de informações do Azure. Em vez disso, para fazer com que os recursos funcionem depois de habilitar esta visualização, conclua estas tarefas:
    
    1. Certifique-se de ter migrado os rótulos de proteção de informações do Azure para os rótulos de confidencialidade e publicá-los no centro de conformidade do Microsoft 365 ou no centro de administração de rótulo equivalente.
    
    2. Baixe os arquivos e carregue-os no SharePoint.

- O SharePoint não pode processar arquivos criptografados quando o rótulo que aplicou a criptografia tem uma das seguintes configurações de criptografia:
    - **Permitir que os usuários atribuam permissões quando aplicarem o rótulo** e **no Word, PowerPoint e Excel, solicitar que os usuários especifiquem permissões**
    - O **acesso do usuário ao conteúdo expira** é definido como um valor diferente de **nunca**.

- Para um documento criptografado que concede permissões de edição para um usuário, a cópia não pode ser bloqueada nas versões Web dos aplicativos do Office.

- O site de acompanhamento de documentos da proteção de informações do Azure não é suportado.

- Aplicativos de área de trabalho do Office e aplicativos móveis não oferecem suporte à coautoria. Em vez disso, esses aplicativos continuam a abrir arquivos no modo de edição exclusivo.

- Se um rótulo incluir criptografia, o Microsoft Cloud app Security não poderá ler as informações de rótulo dos arquivos no SharePoint.

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a>Preparar o Shell de gerenciamento do SharePoint Online para a visualização

Antes de habilitar a visualização, verifique se você está executando o Shell de gerenciamento do SharePoint Online versão 16.0.19418.12000 ou superior. Se você já tiver a versão mais recente, poderá prosseguir e habilitar a visualização.

1. Se você tiver instalado uma versão anterior do Shell de gerenciamento do SharePoint Online a partir da galeria do PowerShell, você pode atualizar o módulo executando o seguinte cmdlet.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. Como alternativa, se você tiver instalado uma versão anterior do Shell de gerenciamento do SharePoint Online no centro de download da Microsoft, também poderá ir para **Adicionar ou remover programas** e desinstalar o Shell de gerenciamento do SharePoint Online.

3. Em um navegador da Web, acesse a página do centro de download e [Baixe o Shell de gerenciamento do SharePoint Online mais recente](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Escolha o idioma e clique em **Salvar**.

5. Escolha entre o arquivo .msi x64 e x86. Baixe o arquivo x64 se você executar a versão de 64 bits do Windows ou o arquivo x86, se você executar a versão de 32 bits. Se não souber, confira [qual versão do sistema operacional Windows estou executando?](https://support.microsoft.com/help/13443/windows-which-operating-system)


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
