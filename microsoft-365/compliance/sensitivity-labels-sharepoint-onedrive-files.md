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
description: Os administradores podem habilitar o suporte a rótulos de sensibilidade para arquivos word, Excel e PowerPoint no SharePoint e OneDrive.
ms.openlocfilehash: 08ea7c88fffebd4466d81ca18f273281ff74c06a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286544"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>Habilitar rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Habilita a rotulagem interna para arquivos Office com suporte no SharePoint e OneDrive para [](sensitivity-labels.md) que os usuários possam aplicar seus rótulos de sensibilidade Office para a Web. [](sensitivity-labels-office-apps.md#office-file-types-supported) Quando esse recurso estiver habilitado, os usuários verão o botão **Sensibilidade** na faixa de opções para que possam aplicar rótulos e ver qualquer nome de rótulo aplicado na barra de status.

Habilitando esse recurso também resulta SharePoint e OneDrive ser capaz de processar o conteúdo de arquivos Office que foram criptografados usando um rótulo de sensibilidade. O rótulo pode ser aplicado em Office para a Web ou em aplicativos da área de trabalho Office carregados ou salvos em SharePoint e OneDrive. Até você habilitar esse recurso, esses serviços não poderão processar arquivos criptografados, o que significa que a coautoria, a Descoberta Virtual, a Prevenção contra Perda de Dados, a pesquisa e outros recursos colaborativos não funcionarão para esses arquivos.

Depois de habilitar rótulos de sensibilidade para arquivos Office no SharePoint e OneDrive, para arquivos novos e alterados que tenham um rótulo de sensibilidade que aplique criptografia com uma chave baseada em nuvem (e não use Criptografia de Chave Dupla [):](double-key-encryption.md)

- Para arquivos word, Excel e PowerPoint, SharePoint e OneDrive o rótulo e agora podem processar o conteúdo do arquivo criptografado.

- Quando os usuários baixam ou acessam esses arquivos do SharePoint ou OneDrive, o rótulo de confidencialidade e todas as configurações de criptografia do rótulo são impostas e permanecem com o arquivo, onde quer que seja armazenado. Certifique-se de fornecer orientações do usuário para usar somente rótulos para proteger documentos. Para obter mais informações, consulte Opções de Gerenciamento de Direitos de Informação [(IRM) e rótulos de sensibilidade.](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)

- Quando os usuários carregam arquivos rotulados e criptografados para SharePoint ou OneDrive, eles devem ter pelo menos direitos de exibição para esses arquivos. Por exemplo, eles podem abrir os arquivos fora SharePoint. Se eles não têm esse direito de uso mínimo, o carregamento é bem-sucedido, mas o serviço não reconhece o rótulo e não pode processar o conteúdo do arquivo.

- Use Office para a Web (Word, Excel, PowerPoint) para abrir e editar Office arquivos que tenham rótulos de sensibilidade que aplicam criptografia. As permissões atribuídas à criptografia são impostas. Você também pode usar [a rotulagem automática](apply-sensitivity-label-automatically.md) para esses documentos.

- Os usuários externos podem acessar documentos rotulados com criptografia usando contas de convidado. Para obter mais informações, consulte [Suporte para usuários externos e conteúdo rotulado](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content).

- Office 365 eDiscovery oferece suporte à pesquisa de texto completo para esses arquivos e as políticas de Prevenção contra Perda de Dados (DLP) suportam conteúdo nesses arquivos.

> [!NOTE]
> Se a criptografia tiver sido aplicada com uma chave local (uma topologia de gerenciamento de chaves geralmente chamada de "manter sua própria chave" ou HYOK) ou usando a Criptografia de Chave [Dupla,](double-key-encryption.md)o comportamento de serviço para processar o conteúdo do arquivo não muda. Portanto, para esses arquivos, a coautoria, a Descoberta Virtual, a Prevenção contra Perda de Dados, a pesquisa e outros recursos colaborativos não funcionarão.
>
> O SharePoint e OneDrive também não mudam para arquivos existentes nesses locais que são rotulados com criptografia usando uma única chave baseada no Azure. Para que esses arquivos se beneficiem dos novos recursos depois que você habilitar rótulos de sensibilidade para arquivos Office no SharePoint e OneDrive, os arquivos devem ser baixados e carregados novamente ou editados.

Depois de habilitar rótulos de sensibilidade para arquivos Office no SharePoint [](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) e no OneDrive, três novos eventos de auditoria estarão disponíveis para monitorar rótulos de sensibilidade aplicados a documentos no SharePoint e OneDrive:

- **Rótulo de sensibilidade aplicado ao site**
- **Rótulo de sensibilidade alterado aplicado ao arquivo**
- **Rótulo de sensibilidade removido do site**

Assista ao seguinte vídeo (sem áudio) para ver os novos recursos em ação:

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

Você sempre tem a opção de desabilitar rótulos de sensibilidade para Office arquivos em SharePoint e OneDrive ([opt-out](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out)) a qualquer momento.

Se você estiver protegendo documentos no SharePoint usando o IRM (Gerenciamento de Direitos de Informação) do SharePoint, verifique SharePoint seção gerenciamento de direitos de informação [(IRM)](#sharepoint-information-rights-management-irm-and-sensitivity-labels) e rótulos de sensibilidade nesta página.

## <a name="requirements"></a>Requisitos

Esses novos recursos funcionam apenas [com rótulos de sensibilidade.](sensitivity-labels.md) Se você atualmente tiver rótulos da Proteção de Informações do Azure, primeiro migre-os para rótulos de sensibilidade para que você possa habilitar esses recursos para novos arquivos carregados. Para obter instruções, consulte[Como migrar os rótulos de Proteção de Informações do Azure para rótulos de confidencialidade unificada](/azure/information-protection/configure-policy-migrate-labels).

Use o aplicativo Sincronização do OneDrive versão 19.002.0121.0008 ou posterior no Windows e versão 19.002.0107.0008 ou posterior no Mac. Ambas as versões foram lançadas em 28 de janeiro de 2019 e atualmente são lançadas para todos os anéis. Para obter mais informações, consulte as [OneDrive de versão](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0). Depois de habilitar rótulos de sensibilidade para arquivos Office no SharePoint e OneDrive, os usuários que executarem uma versão mais antiga do aplicativo de sincronização serão solicitados a atualizá-lo.

## <a name="limitations"></a>Limitações

- SharePoint e OneDrive não podem processar alguns arquivos rotulados e criptografados de aplicativos de área de trabalho Office quando esses arquivos contêm dados do PowerQuery, dados armazenados por complementos personalizados ou partes XML personalizadas, como Propriedades da Página de Capa, esquemas de tipo de conteúdo, Painel de Informações de Documento personalizado e XSN personalizado. Essa limitação também se aplica a arquivos que tenham uma [ID de documento](https://support.microsoft.com/office/enable-and-configure-unique-document-ids-ea7fee86-bd6f-4cc8-9365-8086e794c984) adicionada quando são carregados.

    Para esses arquivos, aplique um rótulo sem criptografia para que possam ser abertos posteriormente no Office na Web, ou instrua os usuários a abrirem os arquivos em seus aplicativos de área de trabalho. Os arquivos rotulados e criptografados somente Office na Web não são afetados.

- SharePoint e OneDrive não aplicam automaticamente rótulos de sensibilidade a arquivos existentes que você já criptografou usando rótulos da Proteção de Informações do Azure. Em vez disso, para que os recursos funcionem depois que você habilitar rótulos de sensibilidade para arquivos Office no SharePoint e OneDrive, conclua estas tarefas:

    1. Certifique-se de ter [migrado os rótulos](/azure/information-protection/configure-policy-migrate-labels) da [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) Proteção de Informações do Azure para rótulos de sensibilidade e publicados do Centro de conformidade do Microsoft 365.
    2. Baixe os arquivos rotulados e, em seguida, carregue-os em seu local original SharePoint ou OneDrive.

- SharePoint e OneDrive não podem processar arquivos [criptografados](encryption-sensitivity-labels.md#configure-encryption-settings)quando o rótulo que aplicou a criptografia tem qualquer uma das seguintes configurações para criptografia :
  - **Permitir que os usuários atribuam permissões quando aplicarem o rótulo** e a caixa de seleção **no Word, PowerPoint e Excel, solicitar que os usuários especifiquem as permissões** está selecionada. Essa configuração às vezes é conhecida como "permissões definidas pelo usuário".
  - **O acesso do usuário ao conteúdo expira** é definido como um valor diferente de **Nunca**.
  - **Criptografia de Chave Dupla** é selecionada.

    Para rótulos com qualquer uma dessas configurações de criptografia, os rótulos não são exibidos para os usuários em Office para a Web. Além disso, os novos recursos não podem ser usados com documentos rotulados que já têm essas configurações de criptografia. Por exemplo, esses documentos não serão retornados nos resultados da pesquisa, mesmo que sejam atualizados.

- Por motivos de desempenho, quando você carrega ou salva um documento no SharePoint e o rótulo do arquivo não aplica criptografia, a coluna **Confidencialidade** na biblioteca de documentos pode demorar um pouco para exibir o nome do rótulo. Factor in this delay if you use scripts or automation that depend on the label name in this column.

- Os usuários podem ter atrasos ao serem capazes de abrir documentos criptografados no seguinte cenário Salvar como: Usando uma versão da área de trabalho do Office, um usuário escolhe Salvar como para um documento que tem um rótulo de sensibilidade que aplica criptografia. O usuário seleciona SharePoint ou OneDrive para o local e, em seguida, tenta abrir imediatamente esse documento Office para a Web. Se o serviço ainda estiver processamento da criptografia, o usuário verá uma mensagem de que o documento deve ser aberto em seu aplicativo de área de trabalho. Se eles tentarem novamente em alguns minutos, o documento será aberto com êxito Office para a Web.

- Para documentos criptografados, não há suporte para impressão.

- Para um documento criptografado que concede permissões de edição a um usuário, a cópia não pode ser bloqueada nas versões da Web dos aplicativos Office de edição.

- Por padrão, Office aplicativos da área de trabalho e aplicativos móveis não suportam coautor para arquivos rotulados com criptografia. Esses aplicativos continuam a abrir arquivos rotulados e criptografados no modo de edição exclusivo.

    > [!NOTE]
    > A coautoridade agora é suportada na visualização. Para obter mais informações, consulte [Enable co-authoring for files encrypted with sensitivity labels](sensitivity-labels-coauthoring.md).

- Se um administrador mudar as configurações de um rótulo publicado que já tenha sido aplicado aos arquivos baixados ao cliente de sincronização dos usuários, os usuários poderão não conseguir salvar as alterações feitas no arquivo em sua pasta OneDrive Sync. Esse cenário se aplica a arquivos rotulados com criptografia e também quando a alteração de rótulo é de um rótulo que não aplicou criptografia a um rótulo que aplica criptografia. Os usuários veem um [círculo vermelho com um erro](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)de ícone cruzado branco e são solicitados a salvar novas alterações como uma cópia separada. Em vez disso, eles podem fechar e reabrir o arquivo ou usar Office para a Web.

- Os usuários podem experimentar salvar problemas depois de ficar offline ou em um modo de compartilhamento quando, em vez de usar o Office para a Web, eles usam os aplicativos de área de trabalho e móveis para Word, Excel ou PowerPoint. Para esses usuários, quando eles retomam a sessão de Aplicativo do Office e tentam salvar as alterações, eles veem uma mensagem de falha de carregamento com a opção de salvar uma cópia em vez de salvar o arquivo original.

- Os documentos que foram criptografados das seguintes maneiras não podem ser abertos Office para a Web:
  - Criptografia que usa uma chave local ("mantenha sua própria chave" ou HYOK)
  - Criptografia que foi aplicada usando a [Criptografia de Chave Dupla](double-key-encryption.md)
  - A criptografia aplicada independentemente de um rótulo, por exemplo, aplicando-se diretamente um modelo de proteção de Gerenciamento de Direitos.

- Os rótulos configurados [para outros idiomas](create-sensitivity-labels.md#additional-label-settings-with-security--compliance-center-powershell) não são suportados e exibem apenas o idioma original.

- Capturas de tela não podem ser impedidas para documentos criptografados. Para obter mais informações, consulte [O Gerenciamento de Direitos pode impedir capturas de tela?](/azure/information-protection/faqs-rms#can-rights-management-prevent-screen-captures)

- Se você excluir um rótulo que foi aplicado a um documento no SharePoint ou OneDrive, em vez de remover o rótulo da política de rótulo aplicável, o documento quando baixado não será rotulado ou criptografado. Em comparação, se o documento rotulado for armazenado fora SharePoint ou OneDrive, o documento permanecerá criptografado se o rótulo for excluído. Observe que, embora você possa excluir rótulos durante uma fase de teste, é muito raro excluir um rótulo em um ambiente de produção.

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>Como habilitar rótulos de SharePoint e OneDrive (aceitação)

Você pode habilitar os novos recursos usando o Centro de conformidade do Microsoft 365 ou usando o PowerShell. Assim como acontece com todas as alterações de configuração no nível do locatário para SharePoint e OneDrive, leva cerca de 15 minutos para que a alteração entre em vigor.

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>Usar o centro de conformidade para habilitar o suporte a rótulos de sensibilidade

Essa opção é a maneira mais fácil de habilitar rótulos de sensibilidade para SharePoint e OneDrive, mas você deve entrar como um administrador global para seu locatário.

1. Entre no Centro de conformidade do Microsoft 365 [como](https://compliance.microsoft.com/) administrador global e navegue até Proteção **de** Informações  >  **de Soluções**

    Se você não vir essa opção imediatamente, selecione primeiro **Mostrar tudo**.

2. Se você vir uma mensagem para ativar a capacidade de processar conteúdo em arquivos Office online, selecione **Ativar agora**:

    ![Ative o botão agora para habilitar rótulos de sensibilidade para Office Online](../media/sensitivity-labels-turn-on-banner.png)

    O comando é executado imediatamente e quando a página é atualizada, você não vê mais a mensagem ou o botão.

> [!NOTE]
> Se você tiver Microsoft 365 multi-geo, deverá usar o PowerShell para habilitar esses recursos para todas as localizações geográficas. Veja mais detalhes na próxima seção.

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>Usar o PowerShell para habilitar o suporte a rótulos de sensibilidade

Como alternativa ao uso do centro de conformidade, você pode habilitar o suporte a rótulos de sensibilidade usando o cmdlet [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) do SharePoint Online PowerShell.

Se você tiver Microsoft 365 multi-geo, deverá usar o PowerShell para habilitar esse suporte para todas as localizações geográficas.

#### <a name="prepare-the-sharepoint-online-management-shell"></a>Preparar o Shell de Gerenciamento SharePoint Online

Antes de executar o comando do PowerShell para habilitar rótulos de sensibilidade para arquivos Office no SharePoint e no OneDrive, verifique se você está executando o SharePoint Shell de Gerenciamento Online versão 16.0.19418.12000 ou posterior. Se você já tiver a versão mais recente, poderá pular para o [próximo procedimento](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) para executar o comando do PowerShell.

1. Se você tiver instalado uma versão anterior do Shell de Gerenciamento do SharePoint Online na galeria do PowerShell, poderá atualizar o módulo executando o cmdlet a seguir.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. Como alternativa, se você instalou uma versão anterior do Shell de Gerenciamento do SharePoint  Online a partir do Centro de Download da Microsoft, você também pode ir para Adicionar ou remover programas e desinstalar o Shell de Gerenciamento do SharePoint Online.

3. Em um navegador da Web, acesse a página do centro de download e [Baixe o Shell de gerenciamento do SharePoint Online mais recente](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Escolha o idioma e clique em **Salvar**.

5. Escolha entre o arquivo .msi x64 e x86. Baixe o arquivo x64 se você executar a versão de 64 bits do Windows ou o arquivo x86 se você executar a versão de 32 bits. Se você não sabe, consulte Qual versão do sistema [operacional Windows estou executando?](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. Depois de baixar o arquivo, execute o arquivo e siga as etapas no Assistente de Instalação.

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>Execute o comando do PowerShell para habilitar o suporte a rótulos de sensibilidade

Para habilitar os novos recursos, use o cmdlet [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) com o *parâmetro EnableAIPIntegration:*

1. Usando uma conta de estudante ou de trabalho que tenha privilégios de administrador global ou SharePoint administrador no Microsoft 365, conecte-se ao SharePoint. Para saber como, consulte [Introdução ao Shell de Gerenciamento do SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

    > [!NOTE]
    > Se você tiver Microsoft 365 Multi-Geo, use o parâmetro -Url com [Conexão-SPOService](/powershell/module/sharepoint-online/connect-sposervice)e especifique a URL do site do Centro de Administração do SharePoint Online para uma de suas localizações geográficas.

2. Execute o seguinte comando e pressione **Y** para confirmar:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true
    ```
3. Para Microsoft 365 Multi-Geo: repita as etapas 1 e 2 para cada uma das localizações geográficas restantes.

## <a name="publishing-and-changing-sensitivity-labels"></a>Publicar e alterar rótulos de sensibilidade

Quando você usa rótulos de sensibilidade com SharePoint e OneDrive, lembre-se de que você precisa permitir o tempo de replicação quando publicar novos rótulos de sensibilidade ou atualizar rótulos de sensibilidade existentes. Isso é especialmente importante para novos rótulos que aplicam criptografia.

Por exemplo: você cria e publica um novo rótulo de sensibilidade que aplica criptografia e aparece rapidamente no aplicativo da área de trabalho de um usuário. O usuário aplica esse rótulo a um documento e o carrega para SharePoint ou OneDrive. Se a replicação de rótulo não tiver sido concluída para o serviço, os novos recursos não serão aplicados ao documento ao carregar. Como resultado, o documento não será retornado na pesquisa ou na Descoberta Digital e o documento não poderá ser aberto no Office para a Web.

As seguintes alterações se replicam em uma hora: rótulos de sensibilidade novos e excluídos e configurações de política de rótulo de sensibilidade que incluem quais rótulos estão na política.

As seguintes alterações se replicam dentro de 24 horas: Alterações nas configurações do rótulo de sensibilidade para rótulos existentes.

Como o atraso de replicação é de apenas uma hora para novos rótulos de sensibilidade, é improvável que você execute o cenário no exemplo. Porém, como proteção, recomendamos publicar novos rótulos para apenas alguns usuários de teste primeiro, aguardar por uma hora e, em seguida, verificar o comportamento do rótulo no SharePoint e OneDrive. Como etapa final, disponibilizar o rótulo para mais usuários adicionando mais usuários à política de rótulo existente ou adicionando o rótulo a uma política de rótulo existente para seus usuários padrão. No momento em que os usuários padrão veem o rótulo, ele já foi sincronizado com SharePoint e OneDrive.

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePoint Gerenciamento de Direitos de Informação (IRM) e rótulos de sensibilidade

SharePoint Gerenciamento de Direitos de Informação [(IRM)](set-up-irm-in-sp-admin-center.md) é uma tecnologia mais antiga para proteger arquivos no nível de lista e biblioteca aplicando criptografia e restrições quando os arquivos são baixados. Essa tecnologia de proteção mais antiga foi projetada para impedir que usuários não autorizados abriam o arquivo enquanto ele está fora SharePoint.

Em comparação, os rótulos de sensibilidade fornecem as configurações de proteção de marcações visuais (headers, rodapés, marcas d'água) além da criptografia. As configurações de criptografia [](/azure/information-protection/configure-usage-rights) suportam a gama completa de direitos de uso para restringir o que os usuários podem fazer com o conteúdo e os mesmos rótulos de sensibilidade são suportados para [muitos cenários.](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels) Usar o mesmo método de proteção com configurações consistentes entre cargas de trabalho e aplicativos resulta em uma estratégia de proteção consistente.

No entanto, você pode usar soluções de proteção em conjunto e o comportamento é o seguinte:

- Se você carregar um arquivo com um rótulo de confidencialidade que aplique criptografia, SharePoint não poderá processar o conteúdo desses arquivos de forma que a coautoria, a Descoberta EDiscovery, a DLP e a pesquisa não sejam suportadas para esses arquivos.

- Se você rotular um arquivo usando Office para a Web, quaisquer configurações de criptografia do rótulo serão impostas. Para esses arquivos, há suporte para coautoria, Descoberta EDiscovery, DLP e pesquisa.

- Se você baixar um arquivo rotulado usando Office para a Web, o rótulo será mantido e quaisquer configurações de criptografia do rótulo serão impostas em vez das configurações de restrição de IRM.

- Se você baixar um Office ou arquivo PDF que não seja criptografado com um rótulo de confidencialidade, as configurações do IRM serão aplicadas.

- Se você habilitar qualquer uma das configurações adicionais da biblioteca de IRM, que incluem impedir que os usuários carreguem documentos que não suportam IRM, essas configurações serão impostas.

Com esse comportamento, você pode ter certeza de que todos os arquivos Office e PDF estão protegidos contra acesso não autorizado se eles são baixados, mesmo que não sejam rotulados. No entanto, os arquivos rotulados carregados não se beneficiarão dos novos recursos.


## <a name="search-for-documents-by-sensitivity-label"></a>Pesquisar documentos por rótulo de sensibilidade

Use a propriedade gerenciada **InformationProtectionLabelId** para encontrar todos os documentos SharePoint ou OneDrive que tenham um rótulo de sensibilidade específico. Use a seguinte sintaxe: `InformationProtectionLabelId:<GUID>`

Por exemplo, para pesquisar todos os documentos que foram rotulados como "Confidencial", e esse rótulo tem um GUID de "8faca7b8-8d20-48a3-8ea2-0f96310a848e", na caixa de pesquisa, digite:

```
InformationProtectionLabelId:8faca7b8-8d20-48a3-8ea2-0f96310a848e
```

A pesquisa não encontrará documentos rotulados em um arquivo compactado, como um arquivo .zip.

Para obter os GUIDs para seus rótulos de sensibilidade, use o cmdlet [Get-Label:](/powershell/module/exchange/get-label)

1. Primeiro, [conecte-se ao PowerShell do Centro de Conformidade e Segurança do Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

    Por exemplo, em uma sessão do PowerShell que você executa como administrador, entre com uma conta de administrador global.

2. Em seguida, execute o seguinte comando:

    ```powershell
    Get-Label |ft Name, Guid
    ```

Para obter mais informações sobre como usar propriedades gerenciadas, consulte [Manage the search schema in SharePoint](/sharepoint/manage-search-schema).

## <a name="remove-encryption-for-a-labeled-document"></a>Remover criptografia para um documento rotulado

Pode haver raras ocasiões em que um administrador SharePoint precisa remover a criptografia de um documento armazenado em SharePoint. Qualquer usuário que [](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) tenha o direito de uso gerenciamento de direitos de Exportação ou Controle Total atribuído a eles para esse documento pode remover a criptografia que foi aplicada pelo serviço de Gerenciamento de Direitos do Azure da Proteção de Informações do Azure. Por exemplo, os usuários com qualquer um desses direitos de uso podem substituir um rótulo que aplica criptografia por um rótulo sem criptografia. Como alternativa, um [super usuário poderia](/azure/information-protection/configure-super-users) baixar o arquivo e salvar uma cópia local sem a criptografia.

Como alternativa, um administrador global ou SharePoint pode executar o cmdlet [Unlock-SPOSensitivityLabelEncryptedFile,](/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile) que remove o rótulo de sensibilidade e [a](/sharepoint/sharepoint-admin-role) criptografia. Esse cmdlet é executado mesmo se o administrador não tiver permissões de acesso ao site ou arquivo ou se o serviço de Gerenciamento de Direitos do Azure estiver indisponível.

Por exemplo:

```powershell
Unlock-SPOSensitivityLabelEncryptedFile -FileUrl "https://contoso.com/sites/Marketing/Shared Documents/Doc1.docx" -JustificationText "Need to decrypt this file"
```

Requisitos:

- SharePoint Shell de Gerenciamento Online versão 16.0.20616.12000 ou posterior.

- A criptografia foi aplicada por um rótulo de sensibilidade com configurações de criptografia definidas pelo administrador (as configurações [atribuir permissões agora](encryption-sensitivity-labels.md#assign-permissions-now) rotulam). [Não há](encryption-sensitivity-labels.md#double-key-encryption) suporte para Criptografia de Chave Dupla para este cmdlet.

O texto de justificativa [](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) é adicionado ao evento de auditoria do rótulo de confidencialidade removido do arquivo **,** e a ação de descriptografia também é registrada no log de uso de proteção para a Proteção de Informações do [Azure](/azure/information-protection/log-analyze-usage).

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>Como desabilitar rótulos de sensibilidade para SharePoint e OneDrive (desativação)

Se você desabilitar esses novos recursos, os arquivos que você carregou após habilitar rótulos de sensibilidade para SharePoint e OneDrive continuarão protegidos pelo rótulo porque as configurações de rótulo continuarão a ser impostas. Quando você aplica rótulos de sensibilidade a novos arquivos depois de desabilitar esses novos recursos, a pesquisa de texto completo, a Descoberta e a Coautoria não funcionarão mais.

Para desabilitar esses novos recursos, você deve usar o PowerShell. Usando o Shell de Gerenciamento do SharePoint Online e o cmdlet [Set-SPOTenant,](/powershell/module/sharepoint-online/set-spotenant) especifique o mesmo parâmetro *EnableAIPIntegration* conforme descrito na seção [Usar o PowerShell](#use-powershell-to-enable-support-for-sensitivity-labels) para habilitar o suporte para rótulos de sensibilidade. Mas, desta vez, de definir o valor do parâmetro como false e pressione **Y** para confirmar:

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

Se você tiver Microsoft 365 multi-geo, deverá executar esse comando para cada uma de suas localizações geográficas.

## <a name="next-steps"></a>Próximas etapas

Depois de habilitar rótulos de sensibilidade para arquivos Office no SharePoint e OneDrive, considere rotular automaticamente esses arquivos usando políticas de rotulagem automática. Para obter mais informações, [consulte Aplicar um rótulo de sensibilidade ao conteúdo automaticamente](apply-sensitivity-label-automatically.md).

Precisa compartilhar os seus documentos rotulados e criptografados com pessoas fora de sua organização?  Consulte [Compartilhamento de documentos criptografados com usuários externos](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users).
