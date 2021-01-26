---
title: Habilitar rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive
f1.keywords:
- NOCSH
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
description: Os administradores podem habilitar o suporte a rótulos de sensibilidade para arquivos do Word, Excel e PowerPoint no SharePoint e no OneDrive.
ms.openlocfilehash: 0b5f17286456a364c6a8b4c5bdb397c5b0263b73
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975894"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>Habilitar rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

Habilita os rótulos de sensibilidade para arquivos do Office no SharePoint e no OneDrive para que os usuários possam aplicar seus rótulos de [sensibilidade](sensitivity-labels.md) no Office na Web. Quando esse recurso estiver habilitado,  os usuários verão o botão Sensibilidade na faixa de opções para que possam aplicar rótulos e ver qualquer nome de rótulo aplicado na barra de status. 

A habilitação desse recurso também faz com que o SharePoint e o OneDrive processem o conteúdo dos arquivos que foram criptografados usando um rótulo de sensibilidade. O rótulo pode ser aplicado no Office para a Web ou em aplicativos da área de trabalho do Office e carregado ou salvo no SharePoint e no OneDrive. Até você habilitar esse recurso, esses serviços não poderão processar arquivos criptografados, o que significa que a coautoria, a Descoberta EDiscovery, a Prevenção contra Perda de Dados, a pesquisa e outros recursos colaborativos não funcionarão para esses arquivos.

Depois de habilitar rótulos de sensibilidade para arquivos do Office no SharePoint e no OneDrive, para arquivos novos e alterados que têm um rótulo de sensibilidade que aplica criptografia com uma chave baseada em nuvem (e não [usa](double-key-encryption.md)Criptografia de Chave Dupla):

- Para arquivos do Word, Excel e PowerPoint, o SharePoint e o OneDrive reconhecem o rótulo e agora podem processar o conteúdo do arquivo criptografado.

- Quando os usuários baixam ou acessam esses arquivos do SharePoint ou do OneDrive, o rótulo de confidencialidade e as configurações de criptografia do rótulo são impostas e permanecem com o arquivo, onde quer que ele esteja armazenado. Certifique-se de fornecer orientação ao usuário para usar apenas rótulos para proteger documentos. Para obter mais informações, consulte opções de Gerenciamento de Direitos [de Informação (IRM) e rótulos de sensibilidade.](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)

- Quando os usuários carregam arquivos rotulados e criptografados no SharePoint ou no OneDrive, eles devem ter pelo menos direitos de exibição para esses arquivos. Por exemplo, eles podem abrir os arquivos fora do SharePoint. Se eles não têm esse direito de uso mínimo, o upload é bem-sucedido, mas o serviço não reconhece o rótulo e não pode processar o conteúdo do arquivo.

- Use o Office na Web (Word, Excel, PowerPoint) para abrir e editar arquivos do Office com rótulos de sensibilidade que aplicam criptografia. As permissões que foram atribuídas com a criptografia são impostas. Você também pode usar [a rotulagem automática](apply-sensitivity-label-automatically.md) para esses documentos.

- Os usuários externos podem acessar documentos rotulados com criptografia usando contas de convidado. Para obter mais informações, [consulte Suporte para usuários externos e conteúdo rotulado.](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content) 

- A Descoberta Pública do Office 365 dá suporte à pesquisa de texto completo para esses arquivos e as políticas de Prevenção contra Perda de Dados (DLP) suportam conteúdo nesses arquivos.

> [!NOTE]
> Se a criptografia tiver sido aplicada com uma chave local (uma topologia de gerenciamento de chaves geralmente chamada de "manter sua própria chave" ou HYOK) ou usando a Criptografia de Chave [Dupla,](double-key-encryption.md)o comportamento do serviço para processar o conteúdo do arquivo não será diferente. Portanto, para esses arquivos, a coautoria, a Descoberta EDiscovery, a Prevenção contra Perda de Dados, a pesquisa e outros recursos colaborativos não funcionarão.
>
> O comportamento do SharePoint e do OneDrive também não muda para arquivos existentes nesses locais que são rotulados com criptografia usando uma única chave baseada no Azure. Para que esses arquivos se beneficiem dos novos recursos depois que você habilitar os rótulos de sensibilidade para arquivos do Office no SharePoint e no OneDrive, os arquivos devem ser baixados e carregados novamente ou editados.

Depois de habilitar rótulos de sensibilidade para arquivos [](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) do Office no SharePoint e no OneDrive, três novos eventos de auditoria estarão disponíveis para monitorar rótulos de sensibilidade aplicados a documentos no SharePoint e no OneDrive:
- **Rótulo de sensibilidade aplicado ao site**
- **Rótulo de sensibilidade alterado aplicado ao arquivo**
- **Rótulo de sensibilidade removido do site**

Assista ao vídeo a seguir (sem áudio) para ver os novos recursos em ação:

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

Você sempre tem a opção de desabilitar os rótulos de sensibilidade para arquivos do Office no SharePoint e no OneDrive[(](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out)desativar) a qualquer momento.

Se você estiver protegendo documentos no SharePoint usando o Gerenciamento de Direitos de Informação do SharePoint (IRM), certifique-se de verificar a seção gerenciamento de direitos de informação [(IRM)](#sharepoint-information-rights-management-irm-and-sensitivity-labels) do SharePoint e rótulos de sensibilidade nesta página. 

## <a name="requirements"></a>Requisitos

Esses novos recursos funcionam apenas [com rótulos de sensibilidade.](sensitivity-labels.md) Se você tiver atualmente os rótulos da Proteção de Informações do Azure, primeiro migre-os para rótulos de sensibilidade para que você possa habilitar esses recursos para novos arquivos carregados. Para obter instruções, confira Como migrar os rótulos da Proteção de Informações do [Azure para rótulos de sensibilidade unificados.](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

Use o aplicativo de sincronização do OneDrive versão 19.002.0121.0008 ou posterior no Windows e a versão 19.002.0107.0008 ou posterior no Mac. Essas duas versões foram lançadas em 28 de janeiro de 2019 e estão lançadas atualmente para todos os anéis. Para saber mais, confira as notas [de versão do OneDrive.](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0) Depois de habilitar os rótulos de sensibilidade para arquivos do Office no SharePoint e no OneDrive, os usuários que executarem uma versão mais antiga do aplicativo de sincronização serão solicitados a atualizá-lo.

## <a name="limitations"></a>Limitações

- O SharePoint e o OneDrive não aplicam automaticamente rótulos de sensibilidade a arquivos existentes que você já criptografou usando rótulos da Proteção de Informações do Azure. Em vez disso, para que os recursos funcionem depois que você habilitar os rótulos de sensibilidade para arquivos do Office no SharePoint e no OneDrive, conclua estas tarefas:
    
    1. Certifique-se de migrar os rótulos da Proteção [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) de Informações do [Azure](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) para rótulos de sensibilidade e publicá-los no centro de conformidade do Microsoft 365 ou no centro de administração de rotulagem equivalente.
    
    2. Baixe os arquivos e carregue-os no SharePoint.

- O SharePoint e o OneDrive não podem processar arquivos criptografados quando o rótulo que aplicou a criptografia tem uma das seguintes configurações [de criptografia:](encryption-sensitivity-labels.md#configure-encryption-settings)
    - **Permitir que os usuários atribuam** permissões quando aplicarem o rótulo e a caixa de seleção no **Word, PowerPoint** e Excel, solicitar que os usuários especifiquem permissões está selecionada. Às vezes, essa configuração é conhecida como "permissões definidas pelo usuário".
    - **O acesso do usuário ao conteúdo expira** é definido para um valor diferente de **Nunca.**
    - **A Criptografia de Chave** Dupla está selecionada.
    
    Para rótulos com qualquer uma dessas configurações de criptografia, os rótulos não são exibidos para os usuários no Office na Web. Além disso, os novos recursos não podem ser usados com documentos rotulados que já têm essas configurações de criptografia. Por exemplo, esses documentos não serão retornados nos resultados da pesquisa, mesmo que sejam atualizados.

- Para um documento criptografado que concede permissões de edição a um usuário, a cópia não pode ser bloqueada nas versões web dos aplicativos do Office.

- O site de rastreamento de documentos da Proteção de Informações do Azure não é suportado.

- Os aplicativos da área de trabalho do Office e os aplicativos móveis não são suportados para coautoria para arquivos rotulados com criptografia. Esses aplicativos continuam a abrir arquivos rotulados e criptografados no modo de edição exclusivo.

- Se um administrador mudar as configurações de um rótulo publicado que já tenha sido aplicado aos arquivos baixados para o cliente de sincronização dos usuários, os usuários poderão não conseguir salvar as alterações feitas no arquivo na pasta sincronização do OneDrive. Esse cenário se aplica a arquivos rotulados com criptografia e também quando a alteração de rótulo é de um rótulo que não aplicou criptografia a um rótulo que não aplica criptografia. Os usuários veem [um círculo vermelho com um erro de](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)ícone cruzado branco e são solicitados a salvar novas alterações como uma cópia separada. Em vez disso, eles podem fechar e reabrir o arquivo ou usar o Office na Web.

- Se um documento rotulado for carregado no SharePoint ou no OneDrive e o rótulo aplicar criptografia usando uma conta de um nome de entidade de serviço, o documento não poderá ser aberto no Office na Web. Os cenários de exemplo incluem o Microsoft Cloud App Security e um arquivo enviado ao Teams por email.

- Os usuários podem experimentar problemas para salvar depois de ficar offline ou entrar em um modo de compartilhamento quando, em vez de usar o Office para a Web, eles usam os aplicativos da área de trabalho e móveis para Word, Excel ou PowerPoint. Para esses usuários, quando eles retomam a sessão do aplicativo do Office e tentam salvar as alterações, eles veem uma mensagem de falha de upload com a opção de salvar uma cópia em vez de salvar o arquivo original. 

- Os documentos que foram criptografados das seguintes maneiras não podem ser abertos no Office na Web:
    - Criptografia que usa uma chave local ("mantenha sua própria chave" ou HYOK)
    - Criptografia que foi aplicada usando a Criptografia [de Chave Dupla](double-key-encryption.md)
    - Criptografia que foi aplicada independentemente de um rótulo, por exemplo, aplicando diretamente um modelo de proteção de Gerenciamento de Direitos.

- Rótulos configurados [para outros idiomas](create-sensitivity-labels.md#additional-label-settings-with-security--compliance-center-powershell) não são suportados e exibem apenas o idioma original.

- Se você excluir um rótulo que foi aplicado a um documento no SharePoint ou no OneDrive, em vez de remover o rótulo da política de rótulo aplicável, o documento quando baixado não será rotulado ou criptografado. Em comparação, se o documento rotulado estiver armazenado fora do SharePoint ou do OneDrive, o documento permanecerá criptografado se o rótulo for excluído. Observe que, embora você possa excluir rótulos durante uma fase de teste, é muito raro excluir um rótulo em um ambiente de produção.

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>Como habilitar rótulos de sensibilidade para o SharePoint e o OneDrive (aceitação)

Você pode habilitar os novos recursos usando o centro de conformidade do Microsoft 365 ou o PowerShell. Assim como acontece com todas as alterações de configuração no nível do locatário para o SharePoint e o OneDrive, leva cerca de 15 minutos para que a alteração entre em vigor.

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>Usar o centro de conformidade para habilitar o suporte a rótulos de sensibilidade

Essa opção é a maneira mais fácil de habilitar rótulos de sensibilidade para o SharePoint e o OneDrive, mas você deve entrar como um administrador global do seu locatário.

1. Entre no centro de conformidade [do Microsoft 365](https://compliance.microsoft.com/) como um administrador global e navegue até **a** Proteção de  >  **Informações de Soluções**
    
    Se você não vir essa opção imediatamente, selecione primeiro **Mostrar tudo**. 

2. Se você vir uma mensagem para ativar a capacidade de processar conteúdo em arquivos do Office online, selecione **Ativar agora:**
    
    ![Botão Ativar agora para habilitar rótulos de sensibilidade para o Office Online](../media/sensitivity-labels-turn-on-banner.png)
    
    O comando é executado imediatamente e, quando a página for atualizada pela próxima vez, você não verá mais a mensagem ou o botão.

> [!NOTE]
> Se você tiver o Microsoft 365 Multi-Geo, deverá usar o PowerShell para habilitar esses recursos para todas as localizações geográficas. Veja mais detalhes na próxima seção.

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>Usar o PowerShell para habilitar o suporte a rótulos de sensibilidade

Como alternativa ao uso do centro de conformidade, você pode habilitar o suporte para rótulos de sensibilidade usando o cmdlet [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant) do PowerShell do SharePoint Online. 

Se você tiver o Microsoft 365 Multi-Geo, deverá usar o PowerShell para habilitar esse suporte para todas as localizações geográficas.

#### <a name="prepare-the-sharepoint-online-management-shell"></a>Preparar o Shell de Gerenciamento do SharePoint Online

Antes de executar o comando do PowerShell para habilitar rótulos de sensibilidade para arquivos do Office no SharePoint e no OneDrive, verifique se você está executando o Shell de Gerenciamento do SharePoint Online versão 16.0.19418.12000 ou posterior. Se você já tiver a versão mais recente, poderá pular para o [próximo procedimento](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) para executar o comando do PowerShell.

1. Se você tiver instalado uma versão anterior do Shell de Gerenciamento do SharePoint Online na galeria do PowerShell, poderá atualizar o módulo executando o cmdlet a seguir.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. Como alternativa, se você tiver instalado uma versão anterior do Shell de Gerenciamento do  SharePoint Online do Centro de Download da Microsoft, também poderá ir para Adicionar ou remover programas e desinstalar o Shell de Gerenciamento do SharePoint Online.

3. Em um navegador da Web, acesse a página do centro de download e [Baixe o Shell de gerenciamento do SharePoint Online mais recente](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Escolha o idioma e clique em **Salvar**.

5. Escolha entre o arquivo .msi x64 e x86. Baixe o arquivo x64 se você executar a versão de 64 bits do Windows ou o arquivo x86 se executar a versão de 32 bits. Se você não sabe, veja Qual versão do sistema operacional [Windows estou executando?](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. Depois de baixar o arquivo, execute o arquivo e siga as etapas do Assistente de Instalação.

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>Execute o comando do PowerShell para habilitar o suporte a rótulos de sensibilidade

Para habilitar os novos recursos, use o cmdlet [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant) com o *parâmetro EnableAIPIntegration:*

1. Usando uma conta de trabalho ou de estudante que tenha privilégios de administrador global ou administrador do SharePoint no Microsoft 365, conecte-se ao SharePoint. Para saber como, consulte [Introdução ao Shell de Gerenciamento do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
    
    Observação: se você tiver o Microsoft 365 Multi-Geo, use o parâmetro -Url com [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice)e especifique a URL do site do Centro de Administração do SharePoint Online para uma de suas localizações geográficas.

2. Execute o seguinte comando e pressione **Y** para confirmar:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true
    ```
3. Para o Microsoft 365 Multi-Geo: repita as etapas 1 e 2 para cada uma das localizações geográficas restantes.

## <a name="publishing-and-changing-sensitivity-labels"></a>Publicar e alterar rótulos de sensibilidade

Ao usar rótulos de sensibilidade com o SharePoint e o OneDrive, tenha em mente que você precisa permitir o tempo de replicação ao publicar novos rótulos de sensibilidade ou atualizar os rótulos de sensibilidade existentes. Isso é especialmente importante para novos rótulos que aplicam criptografia.

Por exemplo: você cria e publica um novo rótulo de sensibilidade que aplica criptografia e aparece muito rapidamente no aplicativo da área de trabalho de um usuário. O usuário aplica esse rótulo a um documento e o carrega no SharePoint ou no OneDrive. Se a replicação de rótulo não tiver sido concluída para o serviço, os novos recursos não serão aplicados a esse documento ao carregar. Como resultado, o documento não será retornado na pesquisa ou na Descoberta e o documento não poderá ser aberto no Office para a Web.  

As seguintes alterações são replicadas em uma hora: rótulos de sensibilidade novos e excluídos e configurações de política de rótulo de sensibilidade que incluem quais rótulos estão na política.

As seguintes alterações são replicadas dentro de 24 horas: Alterações nas configurações de rótulos de sensibilidade para rótulos existentes.

Como o atraso de replicação é de apenas uma hora para novos rótulos de sensibilidade, é improvável que você entre no cenário no exemplo. Mas como uma proteção, recomendamos publicar novos rótulos para apenas alguns usuários de teste primeiro, aguarde uma hora e, em seguida, verifique o comportamento do rótulo no SharePoint e no OneDrive. Como etapa final, disponibilizar o rótulo para mais usuários adicionando mais usuários à política de rótulo existente ou adicionando o rótulo a uma política de rótulo existente para seus usuários padrão. No momento em que os usuários padrão veem o rótulo, ele já está sincronizado com o SharePoint e o OneDrive.

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>Gerenciamento de Direitos de Informação do SharePoint (IRM) e rótulos de sensibilidade

O Gerenciamento de Direitos de Informação [do SharePoint (IRM)](set-up-irm-in-sp-admin-center.md) é uma tecnologia mais antiga para proteger arquivos no nível de lista e biblioteca aplicando criptografia e restrições quando os arquivos são baixados. Essa tecnologia de proteção mais antiga foi projetada para impedir que usuários não autorizados abriam o arquivo enquanto ele está fora do SharePoint.

Em comparação, os rótulos de sensibilidade fornecem as configurações de proteção de marcações visuais (headers, rodapés, marcas d'água) além de criptografia. As configurações de criptografia [](https://docs.microsoft.com/azure/information-protection/configure-usage-rights) suportam a gama completa de direitos de uso para restringir o que os usuários podem fazer com o conteúdo, e os mesmos rótulos de sensibilidade são suportados para [muitos cenários.](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels) Usar o mesmo método de proteção com configurações consistentes entre cargas de trabalho e aplicativos resulta em uma estratégia de proteção consistente.

No entanto, você pode usar as soluções de proteção juntas e o comportamento é o seguinte: 

- Se você carregar um arquivo com um rótulo de confidencialidade que aplica criptografia, o SharePoint não poderá processar o conteúdo desses arquivos, portanto, não há suporte para coautoria, Descobertas EDiscovery, DLP e pesquisa para esses arquivos.

- Se você rotular um arquivo usando o Office na Web, todas as configurações de criptografia do rótulo serão aplicadas. Para esses arquivos, há suporte para coautoria, Descoberta e DLP e pesquisa.

- Se você baixar um arquivo rotulado usando o Office na Web, o rótulo será mantido e quaisquer configurações de criptografia do rótulo serão aplicadas em vez das configurações de restrição de IRM.

- Se você baixar um arquivo do Office ou PDF que não seja criptografado com um rótulo de confidencialidade, as configurações do IRM serão aplicadas.

- Se você tiver habilitado qualquer uma das configurações adicionais da biblioteca do IRM, que incluem impedir que os usuários carreguem documentos que não suportam IRM, essas configurações serão aplicadas.

Com esse comportamento, você pode ter certeza de que todos os arquivos do Office e PDF estão protegidos contra acesso não autorizado se eles são baixados, mesmo que não sejam rotulados. No entanto, os arquivos rotulados que são carregados não se beneficiarão dos novos recursos.


## <a name="search-for-documents-by-sensitivity-label"></a>Pesquisar documentos por rótulo de sensibilidade    

Use a propriedade gerenciada **InformationProtectionLabelId** para encontrar todos os documentos no SharePoint ou no OneDrive que tenham um rótulo de sensibilidade específico. Use a seguinte sintaxe: `InformationProtectionLabelId:<GUID>`

Por exemplo, para pesquisar todos os documentos que foram rotulados como "Confidenciais" e esse rótulo tem um GUID de "8faca7b8-8d20-48a3-8ea2-0f96310a848e", na caixa de pesquisa, digite:

`InformationProtectionLabelId: 8faca7b8-8d20-48a3-8ea2-0f96310a848e`    

Para obter os GUIDs dos rótulos de sensibilidade, use o cmdlet [Get-Label:](https://docs.microsoft.com/powershell/module/exchange/get-label)  

1. Primeiro, [conecte-se ao PowerShell do Centro de Conformidade e Segurança do Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell). 
   
    Por exemplo, em uma sessão do PowerShell que você executa como administrador, entre com uma conta de administrador global.    

2. Em seguida, execute o seguinte comando:  

    ```powershell   
    Get-Label |ft Name, Guid    
    ``` 

Para saber mais sobre como usar propriedades gerenciadas, confira [Gerenciar o esquema de pesquisa no SharePoint.](https://docs.microsoft.com/sharepoint/manage-search-schema)

## <a name="remove-encryption-for-a-labeled-document"></a>Remover a criptografia de um documento rotulado

Pode haver raras ocasiões em que um administrador do SharePoint precise remover a criptografia de um documento armazenado no SharePoint. Qualquer usuário que [](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) tenha o direito de uso Gerenciamento de Direitos de Exportação ou Controle Total atribuído a ele para esse documento pode remover a criptografia que foi aplicada pelo serviço Azure Rights Management da Proteção de Informações do Azure. Por exemplo, os usuários com qualquer um desses direitos de uso podem substituir um rótulo que aplica criptografia por um rótulo sem criptografia. Como alternativa, um [super usuário](https://docs.microsoft.com/azure/information-protection/configure-super-users) pode baixar o arquivo e salvar uma cópia local sem a criptografia.

Como alternativa, um administrador global ou administrador do [SharePoint](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) pode executar o cmdlet [Unlock-SPOSensitivityLabelEncryptedFile,](https://docs.microsoft.com/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile) que remove o rótulo de sensibilidade e a criptografia. Esse cmdlet é executado mesmo se o administrador não tiver permissões de acesso ao site ou arquivo ou se o serviço Azure Rights Management não estiver disponível. 

Por exemplo:

```powershell
Unlock-SPOSensitivityLabelEncryptedFile -FileUrl "https://contoso.com/sites/Marketing/Shared Documents/Doc1.docx" -JustificationText "Need to decrypt this file"
```

Requisitos:

- Shell de Gerenciamento do SharePoint Online versão 16.0.20616.12000 ou posterior.

- A criptografia foi aplicada por um rótulo de sensibilidade com configurações de criptografia definidas pelo administrador (as configurações de atribuir permissões [agora rotulam).](encryption-sensitivity-labels.md#assign-permissions-now) [Não há suporte para](encryption-sensitivity-labels.md#double-key-encryption) a Criptografia de Chave Dupla para este cmdlet.

O texto de justificativa [](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) é adicionado ao evento de auditoria do rótulo de confidencialidade Removido do **arquivo,** e a ação de descriptografia também é registrada no log de uso de proteção para a Proteção de Informações do [Azure.](https://docs.microsoft.com/azure/information-protection/log-analyze-usage)

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>Como desabilitar rótulos de sensibilidade para o SharePoint e o OneDrive (desativar)

Se você desabilitar esses novos recursos, os arquivos carregados depois de habilitar os rótulos de sensibilidade para o SharePoint e o OneDrive continuarão protegidos pelo rótulo porque as configurações de rótulo continuam a ser impostas. Quando você aplica rótulos de sensibilidade a novos arquivos depois de desabilitar esses novos recursos, a pesquisa de texto completo, a Descoberta e a coautoria não funcionarão mais.

Para desabilitar esses novos recursos, você deve usar o PowerShell. Usando o Shell de Gerenciamento do SharePoint Online e o cmdlet [Set-SPOTenant,](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant) especifique o mesmo parâmetro *EnableAIPIntegration* conforme descrito na seção Usar [o PowerShell](#use-powershell-to-enable-support-for-sensitivity-labels) para habilitar o suporte para rótulos de sensibilidade. Mas, desta vez, de definir o valor do parâmetro como falso e pressione **Y** para confirmar:

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

Se você tiver o Microsoft 365 Multi-Geo, deverá executar este comando para cada uma de suas localizações geográficas.

## <a name="next-steps"></a>Próximas etapas

Depois de habilitar os rótulos de sensibilidade para arquivos do Office no SharePoint e no OneDrive, considere rotular automaticamente esses arquivos usando políticas de rotulagem automática. Para obter mais informações, [consulte Aplicar um rótulo de sensibilidade ao conteúdo automaticamente.](apply-sensitivity-label-automatically.md)

Precisa compartilhar os seus documentos rotulados e criptografados com pessoas fora de sua organização?  Consulte [Compartilhamento de documentos criptografados com usuários externos](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users).
